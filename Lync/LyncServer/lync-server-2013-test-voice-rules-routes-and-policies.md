---
title: Lync Server 2013： 測試語音規則、 路由和原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbf04728db30bada37e43f14b33420ede1ce9258
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="30170-102">測試語音規則、 路由和 Lync Server 2013 中的原則</span><span class="sxs-lookup"><span data-stu-id="30170-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30170-103">_**上次修改主題：** 2014年-05-20 個_</span><span class="sxs-lookup"><span data-stu-id="30170-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30170-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="30170-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="30170-105">每月</span><span class="sxs-lookup"><span data-stu-id="30170-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30170-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="30170-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="30170-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="30170-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30170-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="30170-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="30170-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="30170-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="30170-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有可執行此測試 CsVoiceUser cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="30170-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="30170-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="30170-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="30170-112">說明</span><span class="sxs-lookup"><span data-stu-id="30170-112">Description</span></span>

<span data-ttu-id="30170-113">當使用者進行的通話時，呼叫會採用到達其目的地的路由會依的原則和撥號對應表指派給該使用者而定。</span><span class="sxs-lookup"><span data-stu-id="30170-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="30170-114">指定使用者的 SIP 地址和電話號碼，測試 CsVoiceUser cmdlet，驗證是否有問題的使用者可以完成該號碼。</span><span class="sxs-lookup"><span data-stu-id="30170-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="30170-115">如果測試成功，測試 CsVoiceUser 傳回下列結果：</span><span class="sxs-lookup"><span data-stu-id="30170-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="30170-116">號碼轉譯成 E.164 格式 （根據使用者的撥號對應表）</span><span class="sxs-lookup"><span data-stu-id="30170-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="30170-117">提供的翻譯正規化規則</span><span class="sxs-lookup"><span data-stu-id="30170-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="30170-118">使用的語音路由 （根據路由優先順序）;</span><span class="sxs-lookup"><span data-stu-id="30170-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="30170-119">連結至語音路由的使用者的語音原則電話使用方式。</span><span class="sxs-lookup"><span data-stu-id="30170-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="30170-120">測試 CsVoiceUser 可讓您判斷特定的電話號碼是否會路由傳送翻譯不如預期，並可協助您針對個別使用者所遇到的通話相關問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="30170-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="30170-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="30170-121">Running the test</span></span>

<span data-ttu-id="30170-122">執行測試 CsVoiceUser 指令程式時，您就必須提供兩項資訊： 正在撥打 (DialedNumber) 以及要測試的使用者帳戶的身分識別號碼。</span><span class="sxs-lookup"><span data-stu-id="30170-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="30170-123">例如，此命令還能測試能力具有要撥打的電話號碼 +1206555 SIP 位址 sip:kenmyer@litwareinc.com 的使用者-1219年:</span><span class="sxs-lookup"><span data-stu-id="30170-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="30170-124">您所預期要撥打的方式應格式化的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="30170-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="30170-125">例如，如果使用者通常不要撥接 1 之前撥長途電話打電話您應該使用此格式：</span><span class="sxs-lookup"><span data-stu-id="30170-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="30170-126">當然，在此情況下，測試將會失敗如果您沒有可以正確地轉譯成 Lync 伺服器所使用的 E.164 電話格式數字 2065551219 正規化規則。</span><span class="sxs-lookup"><span data-stu-id="30170-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="30170-127">如需詳細資訊，請參閱說明主題 New-csvoicenormalizationrule cmdlet。</span><span class="sxs-lookup"><span data-stu-id="30170-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="30170-128">如果您想要針對每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="30170-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="30170-129">如需詳細資訊，請參閱 < 測試 CsVoiceUser cmdlet 的說明 」 文件。</span><span class="sxs-lookup"><span data-stu-id="30170-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="30170-130">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="30170-130">Determining success or failure</span></span>

<span data-ttu-id="30170-131">如果測試成功完成時 （亦即，如果使用者可以撥打電話到指定的數字），輸出會顯示類似的轉譯的電話號碼和相符的正規化規則，以及語音路由的資訊：</span><span class="sxs-lookup"><span data-stu-id="30170-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="30170-132">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="30170-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="30170-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="30170-133">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="30170-134">\+12065551219 Descripti...]   LocalRoute 本機</span><span class="sxs-lookup"><span data-stu-id="30170-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="30170-135">[Windows PowerShell] 畫面的限制，因為至少部分傳回的資訊 （最值得注意的是比對的正規化規則的完整描述） 可能不會顯示螢幕上。</span><span class="sxs-lookup"><span data-stu-id="30170-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="30170-136">如果您只有感興趣的成功或失敗的測試，然後這可能不重要。</span><span class="sxs-lookup"><span data-stu-id="30170-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="30170-137">如果您偏好以查看傳回的資料的完整詳細資料，然後輸出內容輸送到 Format-list 指令程式執行測試時：</span><span class="sxs-lookup"><span data-stu-id="30170-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="30170-138">將更多的讀取者易記的格式顯示輸出：</span><span class="sxs-lookup"><span data-stu-id="30170-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="30170-139">TranslatedNumber: + 12065551219</span><span class="sxs-lookup"><span data-stu-id="30170-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="30170-140">MatchingRule: Description =;圖樣 = ^ (\\d{11}) $;翻譯 = + $1;</span><span class="sxs-lookup"><span data-stu-id="30170-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="30170-141">名稱 = 首碼所有; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="30170-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="30170-142">FirsMatchingRoute: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="30170-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="30170-143">MatchingUsage： 本機</span><span class="sxs-lookup"><span data-stu-id="30170-143">MatchingUsage : Local</span></span>

<span data-ttu-id="30170-144">如果測試失敗，測試 CsVoiceUser 會傳回空集合的屬性值：</span><span class="sxs-lookup"><span data-stu-id="30170-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="30170-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="30170-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="30170-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="30170-146">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="30170-147">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="30170-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="30170-148">有任意數目的為什麼測試 CsVoiceUser 指令程式可能會失敗的原因： 可能不會有可翻譯的提供的電話號碼正規化規則。</span><span class="sxs-lookup"><span data-stu-id="30170-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="30170-149">可能的語音路由的問題。</span><span class="sxs-lookup"><span data-stu-id="30170-149">There could be problems with the voice route.</span></span> <span data-ttu-id="30170-150">可能與撥號對應指派給使用者，有問題的組態問題。</span><span class="sxs-lookup"><span data-stu-id="30170-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="30170-151">因此，您可能想要加入 Verbose 參數，當您執行測試 CsVoiceUser 指令程式：</span><span class="sxs-lookup"><span data-stu-id="30170-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="30170-152">加入 Verbose 指令程式時，請測試 CsVoiceUser 會發給中採取的所有步驟的詳細的帳戶，進行其檢查時。</span><span class="sxs-lookup"><span data-stu-id="30170-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="30170-153">例如，您可能會看到類似以下的步驟執行：</span><span class="sxs-lookup"><span data-stu-id="30170-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="30170-154">VERBOSE： 尋找使用者身分識別 」 sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="30170-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="30170-155">VERBOSE： 載入撥號對應表: 「 RedmondDialPlan 」</span><span class="sxs-lookup"><span data-stu-id="30170-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="30170-156">此額外資訊可以提供提示想找出失敗的原因時，可採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="30170-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="30170-157">例如，如下所示的詳細資訊輸出告訴我們正在測試使用者已指派撥號對應表 redmonddialplan 指派。</span><span class="sxs-lookup"><span data-stu-id="30170-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="30170-158">如果測試失敗，一個邏輯的下一步是確認 RedmondDialPlan 可以翻譯提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="30170-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="30170-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="30170-159">See Also</span></span>


[<span data-ttu-id="30170-160">測試 CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="30170-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

