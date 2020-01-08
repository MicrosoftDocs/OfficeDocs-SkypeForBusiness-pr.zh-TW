---
title: Lync Server 2013：根據語音路線測試電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed50971c9656d454a44eeee627de95c187ef008f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="ce378-102">在 Lync Server 2013 中根據語音路線測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="ce378-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce378-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ce378-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce378-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ce378-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ce378-105">次</span><span class="sxs-lookup"><span data-stu-id="ce378-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce378-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="ce378-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ce378-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ce378-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce378-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="ce378-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ce378-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ce378-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ce378-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceRoute Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ce378-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="ce378-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ce378-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ce378-112">描述</span><span class="sxs-lookup"><span data-stu-id="ce378-112">Description</span></span>

<span data-ttu-id="ce378-113">語音路由可搭配語音原則共同作業，協助將企業語音通話路由至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="ce378-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="ce378-114">每個語音路線都包含一個正則運算式（數位模式），可識別將透過特定語音路線路由的電話號碼：路線將能夠處理符合此正則運算式的任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="ce378-115">例如，語音路由可能有一個正則運算式，可讓它處理任何10位數的數位。</span><span class="sxs-lookup"><span data-stu-id="ce378-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="ce378-116">這表示路由可以處理如下所示的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="ce378-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="ce378-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="ce378-117">2065551219</span></span>

<span data-ttu-id="ce378-118">此路線將無法處理下列兩個數字中的任一個，兩者都沒有10位數：</span><span class="sxs-lookup"><span data-stu-id="ce378-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="ce378-119">5551219</span><span class="sxs-lookup"><span data-stu-id="ce378-119">5551219</span></span>

  - <span data-ttu-id="ce378-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="ce378-120">12065551219</span></span>

<span data-ttu-id="ce378-121">CsVoiceRoute Cmdlet 會驗證指定的語音路線是否可以傳送指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ce378-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="ce378-122">Running the test</span></span>

<span data-ttu-id="ce378-123">驗證語音路線路由指定電話號碼的能力有兩個步驟。</span><span class="sxs-lookup"><span data-stu-id="ce378-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="ce378-124">首先，您必須使用 CsVoiceRoute Cmdlet 來傳回該語音路由的實例，然後您必須使用 CsVoiceRoute Cmdlet 來驗證該路由處理目標電話號碼的能力。</span><span class="sxs-lookup"><span data-stu-id="ce378-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="ce378-125">例如，這個命令會驗證 RedmondVoiceRoute voice 路線是否可以傳送電話號碼2065551219：</span><span class="sxs-lookup"><span data-stu-id="ce378-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ce378-126">請注意，電話號碼應該會輸入為您希望使用者撥打該號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="ce378-127">例如，如果您不希望使用者在撥入時包含國家/地區代碼和區功能變數代碼，請使用類似以下的語法：</span><span class="sxs-lookup"><span data-stu-id="ce378-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="ce378-128">在這種情況下，目標號碼會留下國家/地區代碼和區號。</span><span class="sxs-lookup"><span data-stu-id="ce378-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="ce378-129">若要使用單一命令來測試特定目標號碼的所有語音路線，請使用如下所示的語法：</span><span class="sxs-lookup"><span data-stu-id="ce378-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ce378-130">如需詳細資訊，請參閱 Test CsVoiceRoute Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ce378-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ce378-131">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ce378-131">Determining success or failure</span></span>

<span data-ttu-id="ce378-132">如果語音路由可以傳送目標電話號碼，CsVoiceRoute Cmdlet 只會傳回值 True：</span><span class="sxs-lookup"><span data-stu-id="ce378-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="ce378-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ce378-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ce378-134">滿足</span><span class="sxs-lookup"><span data-stu-id="ce378-134">True</span></span>

<span data-ttu-id="ce378-135">這表示路由可以處理與目標號碼類似的號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="ce378-136">如果語音路由無法處理目標號碼，則 Test CsVoiceRoute 會傳回值 False：</span><span class="sxs-lookup"><span data-stu-id="ce378-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="ce378-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ce378-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ce378-138">虛假</span><span class="sxs-lookup"><span data-stu-id="ce378-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ce378-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ce378-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="ce378-140">測試語音路由時，「失敗」是相對的詞彙。</span><span class="sxs-lookup"><span data-stu-id="ce378-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="ce378-141">在這種情況下，它不表示路由是「中斷;」，而是表示路由無法處理目標號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="ce378-142">這可能是因為語音路由設定不正確。</span><span class="sxs-lookup"><span data-stu-id="ce378-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="ce378-143">這也可能表示路由決不是使用這種模式來處理數位。</span><span class="sxs-lookup"><span data-stu-id="ce378-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="ce378-144">例如，如果您不想將呼叫路由至特定路線上的其他國家/地區，可以將路由設定為拒絕包含國家/地區碼的所有電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ce378-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="ce378-145">如果 CsVoiceRoute 在您預期傳回 True 時傳回 False，請確認您輸入的目標號碼正確無誤。</span><span class="sxs-lookup"><span data-stu-id="ce378-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="ce378-146">如果您這麼做，請使用類似這個的命令來查看為路線設定的 NumberPattern：</span><span class="sxs-lookup"><span data-stu-id="ce378-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce378-147">請參閱</span><span class="sxs-lookup"><span data-stu-id="ce378-147">See Also</span></span>


[<span data-ttu-id="ce378-148">Test-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="ce378-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

