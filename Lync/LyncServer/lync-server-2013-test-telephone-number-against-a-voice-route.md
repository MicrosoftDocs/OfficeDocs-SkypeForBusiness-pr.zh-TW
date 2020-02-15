---
title: Lync Server 2013： 測試對語音路由的電話號碼
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
ms.openlocfilehash: 3fccdcb5dfc0fe52c2c0dcf80f7f6a374e35a39e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-telephone-number-against-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="ca981-102">針對 Lync Server 2013 中的語音路由測試電話號碼</span><span class="sxs-lookup"><span data-stu-id="ca981-102">Test telephone number against a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca981-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="ca981-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca981-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ca981-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ca981-105">每月</span><span class="sxs-lookup"><span data-stu-id="ca981-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca981-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="ca981-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ca981-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ca981-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca981-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="ca981-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ca981-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ca981-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ca981-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoiceRoute cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ca981-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceRoute cmdlet.</span></span> <span data-ttu-id="ca981-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca981-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceRoute&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ca981-112">描述</span><span class="sxs-lookup"><span data-stu-id="ca981-112">Description</span></span>

<span data-ttu-id="ca981-113">語音路由配合語音原則，以協助將 Enterprise Voice 通話路由傳送至 PSTN 網路。</span><span class="sxs-lookup"><span data-stu-id="ca981-113">Voice routes work together with voice policies to help route Enterprise Voice calls to the PSTN network.</span></span> <span data-ttu-id="ca981-114">每個語音路由包含規則運算式 （數字模式），識別會路由傳送到特定的語音路由的電話號碼： 路由能夠處理任何符合此規則運算式的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-114">Each voice route includes a regular expression (a number pattern) that identifies the phone numbers that will be routed through a given voice route: the route will be able to handle any phone numbers that match this regular expression.</span></span> <span data-ttu-id="ca981-115">例如，語音路由可能需要規則運算式，可讓它來處理任何 10 位數的數字。</span><span class="sxs-lookup"><span data-stu-id="ca981-115">For example, a voice route might have a regular expression that enables it to handle any 10-digit number.</span></span> <span data-ttu-id="ca981-116">這表示路由就能夠處理的電話號碼，例如此：</span><span class="sxs-lookup"><span data-stu-id="ca981-116">That means the route would be able to handle a phone number such as this:</span></span>

  - <span data-ttu-id="ca981-117">2065551219</span><span class="sxs-lookup"><span data-stu-id="ca981-117">2065551219</span></span>

<span data-ttu-id="ca981-118">路由會無法未處理下列兩個數字，其中一種有 10 位數：</span><span class="sxs-lookup"><span data-stu-id="ca981-118">The route would not be able to handle either of the following two numbers, neither of which has 10 digits:</span></span>

  - <span data-ttu-id="ca981-119">5551219</span><span class="sxs-lookup"><span data-stu-id="ca981-119">5551219</span></span>

  - <span data-ttu-id="ca981-120">12065551219</span><span class="sxs-lookup"><span data-stu-id="ca981-120">12065551219</span></span>

<span data-ttu-id="ca981-121">測試 CsVoiceRoute cmdlet 會驗證指定的語音路由是否可以路由傳送的指定的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-121">The Test-CsVoiceRoute cmdlet verifies whether a given voice route can route a specified phone number.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ca981-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="ca981-122">Running the test</span></span>

<span data-ttu-id="ca981-123">確認語音路由至路由的能力的指定的電話號碼是雙步驟程序。</span><span class="sxs-lookup"><span data-stu-id="ca981-123">Verifying the ability of a voice route to route a specified phone number is a two-step process.</span></span> <span data-ttu-id="ca981-124">您必須先使用 Get-csvoiceroute cmdlet 可傳回該語音路由] 中，執行個體，然後您必須使用測試 CsVoiceRoute cmdlet 來確認該路由能夠處理的目標電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-124">First you have to use the Get-CsVoiceRoute cmdlet to return an instance of that voice route, and then you have to use the Test-CsVoiceRoute cmdlet to verify the ability of that route to handle the target phone number.</span></span> <span data-ttu-id="ca981-125">例如，此命令會驗證 RedmondVoiceRoute 語音路由是否可以路由傳送的電話號碼 2065551219:</span><span class="sxs-lookup"><span data-stu-id="ca981-125">For example, this command verifies whether the RedmondVoiceRoute voice route can route the phone number 2065551219:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ca981-126">請注意如您預期使用者撥打該號碼應該輸入的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-126">Note that the phone number should be typed as you expect users to dial that number.</span></span> <span data-ttu-id="ca981-127">例如，如果您未預期設為包含國碼/地區碼和區域的程式碼時撥打的使用者，然後使用類似如下的語法：</span><span class="sxs-lookup"><span data-stu-id="ca981-127">For example, if you do not expect users to include the country code and area code when dialing, then use syntax similar to this:</span></span>

`-TargetNumber "5551219"`

<span data-ttu-id="ca981-128">在此情況下，目標號碼保留延展國碼/地區碼及區域碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-128">In this case, the target number leaves out both the country code and the area code.</span></span>

<span data-ttu-id="ca981-129">若要使用單一命令，以測試對指定的目標數字的所有語音路由，使用語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca981-129">To use a single command to test all the voice routes against a specified target number, use syntax such as the following:</span></span>

`Get-CsVoiceRoute | Test-CsVoiceRoute -TargetNumber "2065551219"`

<span data-ttu-id="ca981-130">如需詳細資訊，請參閱 < 測試 CsVoiceRoute cmdlet 的說明 」 文件。</span><span class="sxs-lookup"><span data-stu-id="ca981-130">For more information, see the Help documentation for the Test-CsVoiceRoute cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ca981-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ca981-131">Determining success or failure</span></span>

<span data-ttu-id="ca981-132">如果語音路由可以路由傳送的目標電話號碼測試 CsVoiceRoute 指令程式只會傳回值為 True:</span><span class="sxs-lookup"><span data-stu-id="ca981-132">If the voice route can route the target phone number the Test-CsVoiceRoute cmdlet just returns the value True:</span></span>

<span data-ttu-id="ca981-133">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ca981-133">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ca981-134">True</span><span class="sxs-lookup"><span data-stu-id="ca981-134">True</span></span>

<span data-ttu-id="ca981-135">這表示該路由可以處理類似的目標號碼的數字。</span><span class="sxs-lookup"><span data-stu-id="ca981-135">That means that route can handle numbers similar to the target number.</span></span> <span data-ttu-id="ca981-136">語音路由時無法處理的目標號碼，然後測試 CsVoiceRoute 傳回的值為 False:</span><span class="sxs-lookup"><span data-stu-id="ca981-136">If the voice route is can't handle the target number then Test-CsVoiceRoute returns the value False:</span></span>

<span data-ttu-id="ca981-137">MatchesPattern</span><span class="sxs-lookup"><span data-stu-id="ca981-137">MatchesPattern</span></span>

\--------------

<span data-ttu-id="ca981-138">False</span><span class="sxs-lookup"><span data-stu-id="ca981-138">False</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ca981-139">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ca981-139">Reasons why the test might have failed</span></span>

<span data-ttu-id="ca981-140">在測試語音路由時，「 失敗 」 是相對的字詞。</span><span class="sxs-lookup"><span data-stu-id="ca981-140">When testing voice routes, “failure” is a relative term.</span></span> <span data-ttu-id="ca981-141">在此情況下，它並不表示路由以某種方式將 「 中斷 」; 相反地，這只是路由無法處理的目標號碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-141">In this case, it doesn’t mean that the route is somehow “broken;” instead, it just means that the route can't handle the target number.</span></span> <span data-ttu-id="ca981-142">可能是因為語音路由未正確設定。</span><span class="sxs-lookup"><span data-stu-id="ca981-142">That could be because the voice route was configured incorrectly.</span></span> <span data-ttu-id="ca981-143">它也可能表示路由已永不設計用來處理使用這種模式的數字。</span><span class="sxs-lookup"><span data-stu-id="ca981-143">It could also mean that the route was never intended to handle numbers using this pattern.</span></span> <span data-ttu-id="ca981-144">例如，如果您不想以其他國家/地區的電話路由透過指定路由至該路由可能會設定為拒絕所有電話號碼，包含國碼/地區碼。</span><span class="sxs-lookup"><span data-stu-id="ca981-144">For example, if you do not want to route calls to other countries over a given route that route might be configured to reject all phone numbers that include a country code.</span></span> <span data-ttu-id="ca981-145">如果測試 CsVoiceRoute 會傳回 False，當您預期它傳回 True，請確認您正確輸入中的目標數字。</span><span class="sxs-lookup"><span data-stu-id="ca981-145">If Test-CsVoiceRoute returns False when you expected it to return True, verify that you typed the target number in correctly.</span></span> <span data-ttu-id="ca981-146">如果您這樣做，然後使用類似以下的命令來檢視 NumberPattern 設定路由：</span><span class="sxs-lookup"><span data-stu-id="ca981-146">If you did, then use a command similar to this one to view the NumberPattern configured for the route:</span></span>

`Get-CsVoiceRoute -Identity "RedmondVoiceRoute" | Select-Object NumberPattern`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ca981-147">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ca981-147">See Also</span></span>


[<span data-ttu-id="ca981-148">測試 CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="ca981-148">Test-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

