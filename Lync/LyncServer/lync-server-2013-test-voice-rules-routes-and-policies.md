---
title: Lync Server 2013：測試語音規則、路由和原則
description: Lync Server 2013：測試語音規則、路由和原則。
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
ms.openlocfilehash: cf205ac2585298dfc5347d93e382e8bbda9f3ff4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557039"
---
# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="c6717-103">在 Lync Server 2013 中測試語音規則、路由和原則</span><span class="sxs-lookup"><span data-stu-id="c6717-103">Test voice rules, routes, and policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6717-104">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="c6717-104">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6717-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c6717-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c6717-106">每月</span><span class="sxs-lookup"><span data-stu-id="c6717-106">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6717-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="c6717-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c6717-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6717-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6717-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="c6717-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c6717-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c6717-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c6717-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsVoiceUser Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c6717-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="c6717-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c6717-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c6717-113">描述</span><span class="sxs-lookup"><span data-stu-id="c6717-113">Description</span></span>

<span data-ttu-id="c6717-114">當使用者撥打電話時，呼叫到達目的地所用的路由，取決於指派給該使用者的原則和撥號對應表。</span><span class="sxs-lookup"><span data-stu-id="c6717-114">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="c6717-115">指定使用者的 SIP 位址和電話號碼，Test-CsVoiceUser Cmdlet 會驗證問題使用者是否可以撥打該號碼。</span><span class="sxs-lookup"><span data-stu-id="c6717-115">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="c6717-116">測試成功時，Test-CsVoiceUser 會傳回下列專案：</span><span class="sxs-lookup"><span data-stu-id="c6717-116">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="c6717-117">根據使用者的撥號對應表，翻譯為 e.164 格式 (的數位) </span><span class="sxs-lookup"><span data-stu-id="c6717-117">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="c6717-118">提供該轉譯的正常化規則</span><span class="sxs-lookup"><span data-stu-id="c6717-118">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="c6717-119">語音路由使用 (根據路由優先順序) ;</span><span class="sxs-lookup"><span data-stu-id="c6717-119">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="c6717-120">將使用者語音原則連結到語音路由的電話使用方式。</span><span class="sxs-lookup"><span data-stu-id="c6717-120">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="c6717-121">Test-CsVoiceUser 可讓您判斷特定的電話號碼是否會如預期的方式進行路由和轉譯，以及協助疑難排解個別使用者所遇到的呼叫相關問題。</span><span class="sxs-lookup"><span data-stu-id="c6717-121">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c6717-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="c6717-122">Running the test</span></span>

<span data-ttu-id="c6717-123">在執行 Test-CsVoiceUser 指令指令時，您必須提供兩種資訊：所撥打的號碼 (DialedNumber) ，以及所測試之使用者帳戶的身分識別。</span><span class="sxs-lookup"><span data-stu-id="c6717-123">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="c6717-124">例如，下列命令會測試具有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者撥打電話號碼 + 1206555-1219 的能力：</span><span class="sxs-lookup"><span data-stu-id="c6717-124">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="c6717-125">電話號碼應該以您預期的撥號方式格式化。</span><span class="sxs-lookup"><span data-stu-id="c6717-125">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="c6717-126">例如，如果使用者在撥打長途電話之前未撥打1，則您應該使用此格式：</span><span class="sxs-lookup"><span data-stu-id="c6717-126">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="c6717-127">當然，在這種情況下，如果您沒有可以將號碼2065551219正確轉譯成 Lync Server 所使用的 e.164 電話格式的正規化規則，則測試會失敗。</span><span class="sxs-lookup"><span data-stu-id="c6717-127">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="c6717-128">如需詳細資訊，請參閱 help 主題 New-CsVoiceNormalizationRule Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c6717-128">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="c6717-129">如果您想要針對每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="c6717-129">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="c6717-130">如需詳細資訊，請參閱 Test-CsVoiceUser Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="c6717-130">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c6717-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c6717-131">Determining success or failure</span></span>

<span data-ttu-id="c6717-132">如果成功完成測試 (也就是說，如果使用者可以撥打電話給指定的號碼) ，輸出會顯示如已翻譯的電話號碼和對應正規化規則和語音路由等資訊：</span><span class="sxs-lookup"><span data-stu-id="c6717-132">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="c6717-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c6717-133">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="c6717-134">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="c6717-134">\----------------    ------------    ------------------    -------------</span></span>

<span data-ttu-id="c6717-135">\+12065551219 Descripti .。。   LocalRoute Local</span><span class="sxs-lookup"><span data-stu-id="c6717-135">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="c6717-136">由於 Windows PowerShell 畫面的限制，至少某些傳回的資訊 (比對的相符正規化規則) 的完整描述可能不會出現在畫面上。</span><span class="sxs-lookup"><span data-stu-id="c6717-136">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="c6717-137">如果您只對成功或失敗的測試感興趣，則可能不重要。</span><span class="sxs-lookup"><span data-stu-id="c6717-137">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="c6717-138">如果您想要在執行測試時，看到傳回資料的完整詳細資料，然後將輸出輸送至 Format-List Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c6717-138">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="c6717-139">這樣會以更易於讀取器的格式顯示輸出：</span><span class="sxs-lookup"><span data-stu-id="c6717-139">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="c6717-140">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="c6717-140">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="c6717-141">MatchingRule： Description =;Pattern = ^ (\\ d {11}) $;轉譯 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="c6717-141">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="c6717-142">Name = Prefix All; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="c6717-142">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="c6717-143">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="c6717-143">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="c6717-144">MatchingUsage：本機</span><span class="sxs-lookup"><span data-stu-id="c6717-144">MatchingUsage : Local</span></span>

<span data-ttu-id="c6717-145">測試失敗時，Test-CsVoiceUser 會傳回一組空的屬性值：</span><span class="sxs-lookup"><span data-stu-id="c6717-145">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="c6717-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="c6717-146">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="c6717-147">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="c6717-147">\---------------- ------------ ------------------ -------------</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c6717-148">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c6717-148">Reasons why the test might have failed</span></span>

<span data-ttu-id="c6717-149">Test-CsVoiceUser Cmdlet 可能失敗的原因有多種：可能不會有可轉譯所提供電話號碼的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="c6717-149">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="c6717-150">語音路由可能會發生問題。</span><span class="sxs-lookup"><span data-stu-id="c6717-150">There could be problems with the voice route.</span></span> <span data-ttu-id="c6717-151">指派給問題使用者的撥號對應表可能發生設定問題。</span><span class="sxs-lookup"><span data-stu-id="c6717-151">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="c6717-152">因此，當您執行 Test-CsVoiceUser Cmdlet 時，您可能會想要加入 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="c6717-152">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="c6717-153">加入詳細的指令 Cmdlet 時，Test-CsVoiceUser 會發佈執行其檢查時所採取之所有步驟的詳細帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6717-153">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="c6717-154">例如，您可能會看到類似下列的步驟：</span><span class="sxs-lookup"><span data-stu-id="c6717-154">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="c6717-155">詳細：尋找身分識別為 "sip:kenmyer@litwareinc.com" 的使用者</span><span class="sxs-lookup"><span data-stu-id="c6717-155">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="c6717-156">詳細：載入撥號對應表： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="c6717-156">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="c6717-157">這項額外資訊可提供您可以採取的步驟，以找出失敗的原因。</span><span class="sxs-lookup"><span data-stu-id="c6717-157">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="c6717-158">例如，此處顯示的詳細資訊輸出會告訴我們所測試的使用者已獲指派撥號對應表 RedmondDialPlan。</span><span class="sxs-lookup"><span data-stu-id="c6717-158">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="c6717-159">如果測試失敗，下一個邏輯的步驟就是驗證 RedmondDialPlan 是否可以轉譯所提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="c6717-159">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6717-160">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c6717-160">See Also</span></span>


[<span data-ttu-id="c6717-161">測試-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="c6717-161">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

