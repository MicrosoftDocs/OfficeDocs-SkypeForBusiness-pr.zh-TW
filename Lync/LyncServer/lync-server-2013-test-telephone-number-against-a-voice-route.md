---
title: Lync Server 2013：對照語音路由測試電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test telephone number against a voice route
ms:assetid: 9a77ed6d-9394-4bef-9344-3d91b6959b97
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725211(v=OCS.15)
ms:contentKeyID: 63969631
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e2db63b7f8c4d801c7e2e89da93593a5745c9c6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519120"
---
# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="bedd1-102">在 Lync Server 2013 中對照語音路由測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="bedd1-102">Test telephone number against a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bedd1-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="bedd1-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bedd1-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="bedd1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bedd1-105">每月</span><span class="sxs-lookup"><span data-stu-id="bedd1-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd1-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="bedd1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bedd1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bedd1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd1-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="bedd1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bedd1-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="bedd1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bedd1-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceRoute Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="bedd1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="bedd1-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="bedd1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bedd1-112">描述</span><span class="sxs-lookup"><span data-stu-id="bedd1-112">Description</span></span>

<span data-ttu-id="bedd1-113">語音路由可搭配語音原則搭配使用，以協助將 Enterprise Voice 通話路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="bedd1-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="bedd1-114">每個語音路由都包含一個正則運算式 (數位模式) ，用以識別將透過指定之語音路由路由傳送的電話號碼：此路由將可以處理符合此正則運算式的任何電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="bedd1-115">例如，語音路由可能有一個正則運算式，可讓它處理任何10位數的數位。</span><span class="sxs-lookup"><span data-stu-id="bedd1-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="bedd1-116">這表示路由可以處理如下的電話號碼：</span><span class="sxs-lookup"><span data-stu-id="bedd1-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="bedd1-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="bedd1-117">2065551219</span></span>

<span data-ttu-id="bedd1-118">路由將無法處理下列兩個數字中的任何一個，兩者都沒有10位數：</span><span class="sxs-lookup"><span data-stu-id="bedd1-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="bedd1-119">5551219</span><span class="sxs-lookup"><span data-stu-id="bedd1-119">5551219</span></span>

  - <span data-ttu-id="bedd1-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="bedd1-120">12065551219</span></span>

<span data-ttu-id="bedd1-121">Test-CsVoiceRoute Cmdlet 會驗證指定的語音路由是否可以路由指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bedd1-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="bedd1-122">Running the test</span></span>

<span data-ttu-id="bedd1-123">驗證語音路由路由指定之電話號碼的功能是兩步驟的處理常式。</span><span class="sxs-lookup"><span data-stu-id="bedd1-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="bedd1-124">首先，您必須使用 Get-CsVoiceRoute Cmdlet 傳回該語音路由的實例，然後必須使用 Test-CsVoiceRoute Cmdlet 來驗證該路由的功能，以處理目標電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="bedd1-125">例如，此命令會驗證 RedmondVoiceRoute voice 路由是否可以路由傳送電話號碼2065551219：</span><span class="sxs-lookup"><span data-stu-id="bedd1-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="bedd1-126">請注意，應輸入的電話號碼應為您期望的使用者撥打該號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="bedd1-127">例如，如果您不想讓使用者在撥號時包含國家代碼和區號，請使用類似下列的語法：</span><span class="sxs-lookup"><span data-stu-id="bedd1-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="bedd1-128">在此情況下，目標號碼會同時留下國家/地區代碼和區號。</span><span class="sxs-lookup"><span data-stu-id="bedd1-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="bedd1-129">若要使用單一命令來測試指定目標號碼的所有語音路由，請使用下列語法：</span><span class="sxs-lookup"><span data-stu-id="bedd1-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="bedd1-130">如需詳細資訊，請參閱 Test-CsVoiceRoute Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="bedd1-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="bedd1-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="bedd1-131">Determining success or failure</span></span>

<span data-ttu-id="bedd1-132">如果語音路由可路由傳送目標電話號碼 Test-CsVoiceRoute Cmdlet 只會傳回值 True：</span><span class="sxs-lookup"><span data-stu-id="bedd1-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="bedd1-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="bedd1-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="bedd1-134">是</span><span class="sxs-lookup"><span data-stu-id="bedd1-134">True</span></span>

<span data-ttu-id="bedd1-135">這表示路由可以處理類似于目標號碼的數位。</span><span class="sxs-lookup"><span data-stu-id="bedd1-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="bedd1-136">如果語音路由無法處理目標號碼，則 Test-CsVoiceRoute 會傳回值 False：</span><span class="sxs-lookup"><span data-stu-id="bedd1-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="bedd1-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="bedd1-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="bedd1-138">False</span><span class="sxs-lookup"><span data-stu-id="bedd1-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="bedd1-139">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="bedd1-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="bedd1-140">測試語音路由時，"失敗" 為相對字詞。</span><span class="sxs-lookup"><span data-stu-id="bedd1-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="bedd1-141">在此情況下，並不表示路由是以「中斷」，而是表示路由無法處理目標號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="bedd1-142">這可能是因為語音路由設定不正確。</span><span class="sxs-lookup"><span data-stu-id="bedd1-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="bedd1-143">也可能表示路由絕對不打算使用此模式來處理數位。</span><span class="sxs-lookup"><span data-stu-id="bedd1-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="bedd1-144">例如，如果您不想要透過指定的路由將來電路由傳送至其他國家/地區，該路由可能會設定為拒絕所有包含國家/地區代碼的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="bedd1-145">如果 Test-CsVoiceRoute 傳回 False，當您期望它傳回 True 時，請確認您已正確輸入目標號碼。</span><span class="sxs-lookup"><span data-stu-id="bedd1-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="bedd1-146">如果您這麼做，請使用類似下列的命令，以查看為路由設定的 NumberPattern：</span><span class="sxs-lookup"><span data-stu-id="bedd1-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bedd1-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="bedd1-147">See Also</span></span>


[<span data-ttu-id="bedd1-148">測試-Get-csvoiceroute</span><span class="sxs-lookup"><span data-stu-id="bedd1-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

