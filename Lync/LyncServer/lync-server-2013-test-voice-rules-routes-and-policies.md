---
title: Lync Server 2013：測試語音規則、路由及原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test voice rules, routes, and policies
ms:assetid: ebb9c3fa-6950-4311-87ca-e1ecd9280a43
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725213(v=OCS.15)
ms:contentKeyID: 63969661
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b3d0cec7e5bd127f5b69eba6956fc3c653cfa51
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-voice-rules-routes-and-policies-in-lync-server-2013"></a><span data-ttu-id="ad4b2-102">在 Lync Server 2013 中測試語音規則、路由與原則</span><span class="sxs-lookup"><span data-stu-id="ad4b2-102">Test voice rules, routes, and policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad4b2-103">_**主題上次修改日期：** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="ad4b2-103">_**Topic Last Modified:** 2014-05-20_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad4b2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="ad4b2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ad4b2-105">次</span><span class="sxs-lookup"><span data-stu-id="ad4b2-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad4b2-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="ad4b2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ad4b2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ad4b2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad4b2-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="ad4b2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ad4b2-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ad4b2-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsVoiceUser Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsVoiceUser cmdlet.</span></span> <span data-ttu-id="ad4b2-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsVoiceUser&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ad4b2-112">描述</span><span class="sxs-lookup"><span data-stu-id="ad4b2-112">Description</span></span>

<span data-ttu-id="ad4b2-113">當使用者撥打電話時，通話要達到目的地的路線，取決於指派給該使用者的原則和撥號方案。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-113">When a user makes a phone call, the route the call takes to reach its destination depends on both the policies and dial plans assigned to that user.</span></span> <span data-ttu-id="ad4b2-114">已知使用者的 SIP 位址和電話號碼，CsVoiceUser Cmdlet 會驗證問題的使用者是否可以完成電話號碼的通話。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-114">Given a user’s SIP address and a phone number, the Test-CsVoiceUser cmdlet verifies whether the user in question can complete a call to that number.</span></span> <span data-ttu-id="ad4b2-115">如果測試成功，測試 CsVoiceUser 會傳回下列內容：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-115">If the test succeeds, Test-CsVoiceUser returns the following:</span></span>

  - <span data-ttu-id="ad4b2-116">轉換為. 164 格式的數位（根據使用者的撥號計畫）</span><span class="sxs-lookup"><span data-stu-id="ad4b2-116">The number translated to E.164 format (based on the user’s dial plan)</span></span>

  - <span data-ttu-id="ad4b2-117">提供該翻譯的正常化規則</span><span class="sxs-lookup"><span data-stu-id="ad4b2-117">The normalization rule that supplied that translation</span></span>

  - <span data-ttu-id="ad4b2-118">使用的語音路由（根據路線優先順序）;</span><span class="sxs-lookup"><span data-stu-id="ad4b2-118">The voice route used (based on route priority);</span></span>

  - <span data-ttu-id="ad4b2-119">將使用者語音原則連結到語音路線的電話使用量。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-119">The phone usage that linked the user’s voice policy to the voice route.</span></span>

<span data-ttu-id="ad4b2-120">CsVoiceUser 可讓您判斷某個特定的電話號碼是否會依預期進行路由與翻譯，並協助您排查個別使用者所遇到的與呼叫相關的問題。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-120">Test-CsVoiceUser enables you to determine whether a specific phone number will route and translate as expected, and can help troubleshoot call-related problems that are experienced by individual users.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ad4b2-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="ad4b2-121">Running the test</span></span>

<span data-ttu-id="ad4b2-122">執行 CsVoiceUser Cmdlet 時，您必須提供兩種資訊：撥號號碼（DialedNumber），以及所測試的使用者帳戶身分識別。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-122">When running the Test-CsVoiceUser cmdlet you must supply two pieces of information: the number being dialed (DialedNumber) and the Identity of the user account being tested.</span></span> <span data-ttu-id="ad4b2-123">例如，這個命令會測試擁有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者對電話號碼 + 1206555-1219 撥打電話的能力：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-123">For example, this command tests the ability of the user who has the SIP address sip:kenmyer@litwareinc.com to make a call to the phone number +1206555-1219:</span></span>

`Test-CsVoiceUser -DialedNumber "12065551219" -SipUri "sip:kenmyer@litwareinc.com"`

<span data-ttu-id="ad4b2-124">電話號碼應按照您預期的撥號方式來格式化。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-124">The phone number should be formatted in the way that you expect it to be dialed.</span></span> <span data-ttu-id="ad4b2-125">例如，如果使用者在撥打電話前沒有撥打1長途，您應該使用這個格式：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-125">For example, if users typically do not dial the 1 before placing a long distance call then you should use this format:</span></span>

`-DialedNumber "2065551219"`

<span data-ttu-id="ad4b2-126">當然，在這種情況下，如果您沒有可以正確將數位2065551219轉換成 Lync Server 所使用的 E. 164 電話格式的正常化規則，測試就會失敗。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-126">Of course, in that case, the test will fail if you do not have a normalization rule that can correctly translate the number 2065551219 into the E.164 telephone format that is used by Lync Server.</span></span> <span data-ttu-id="ad4b2-127">如需詳細資訊，請參閱 CsVoiceNormalizationRule Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-127">For more information, see the help topic New-CsVoiceNormalizationRule cmdlet.</span></span>

<span data-ttu-id="ad4b2-128">如果您想要針對您的每個使用者帳戶執行這個相同的測試，您可以使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-128">If you want to run this same test against each of your user accounts, you can use a command similar to the following:</span></span>

`Get-CsUser | ForEach-Object {$_.DisplayName; Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri $_.SipAddress} | Format-List`

<span data-ttu-id="ad4b2-129">如需詳細資訊，請參閱 Test CsVoiceUser Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-129">For more information, see the Help documentation for the Test-CsVoiceUser cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ad4b2-130">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="ad4b2-130">Determining success or failure</span></span>

<span data-ttu-id="ad4b2-131">如果測試成功完成（也就是，如果使用者可以撥打電話至指定號碼），輸出就會顯示已翻譯的電話號碼與相符的正常化規則及語音路線等資訊：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-131">If the test is completed successfully (that is, if the user can make a phone call to the specified number), the output will show information like the translated phone number and the matching normalization rule and voice route:</span></span>

<span data-ttu-id="ad4b2-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ad4b2-132">TranslatedNumber    MatchingRule    FirstMatchingRoute    MatchingUsage</span></span>

<span data-ttu-id="ad4b2-133">\----------------    ------------    ------------------    -------------</span><span class="sxs-lookup"><span data-stu-id="ad4b2-133"></span></span>

<span data-ttu-id="ad4b2-134">\+12065551219 Descripti .。。   LocalRoute Local</span><span class="sxs-lookup"><span data-stu-id="ad4b2-134">\+12065551219        Descripti...    LocalRoute            Local</span></span>

<span data-ttu-id="ad4b2-135">由於 Windows PowerShell 畫面的限制，至少有一些傳回的資訊（最重要的是相符正常化規則的完整描述）可能不會出現在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-135">Because of the limitations of the Windows PowerShell screen, at least some returned information (most notably the full description of the matching normalization rule) might not appear on-screen.</span></span> <span data-ttu-id="ad4b2-136">如果您只對測試的成功或失敗感興趣，那可能並不重要。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-136">If you are only interested in the success or failure of the test, then this might not matter.</span></span> <span data-ttu-id="ad4b2-137">如果您想要查看傳回資料的完整詳細資料，請在執行測試時，將輸出輸送至 Format 清單 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-137">If you would prefer to see the full details of the returned data then pipe the output to the Format-List cmdlet when running the test:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose | Format-List`

<span data-ttu-id="ad4b2-138">如此一來，就能以更容易讀取器的格式來顯示輸出：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-138">That will display the output in a more reader-friendly format:</span></span>

<span data-ttu-id="ad4b2-139">TranslatedNumber： + 12065551219</span><span class="sxs-lookup"><span data-stu-id="ad4b2-139">TranslatedNumber : +12065551219</span></span>

<span data-ttu-id="ad4b2-140">MatchingRule： Description =;Pattern = ^ （\\d{11}） $;譯文 = + $ 1;</span><span class="sxs-lookup"><span data-stu-id="ad4b2-140">MatchingRule : Description=;Pattern=^(\\d{11})$;Translation=+$1;</span></span>

<span data-ttu-id="ad4b2-141">Name = Prefix All; IsInternalExtension = False</span><span class="sxs-lookup"><span data-stu-id="ad4b2-141">Name=Prefix All;IsInternalExtension=False</span></span>

<span data-ttu-id="ad4b2-142">FirsMatchingRoute : LocalRoute</span><span class="sxs-lookup"><span data-stu-id="ad4b2-142">FirsMatchingRoute : LocalRoute</span></span>

<span data-ttu-id="ad4b2-143">MatchingUsage： Local</span><span class="sxs-lookup"><span data-stu-id="ad4b2-143">MatchingUsage : Local</span></span>

<span data-ttu-id="ad4b2-144">如果測試失敗，測試 CsVoiceUser 會傳回一組空的屬性值：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-144">If the test fails, Test-CsVoiceUser will return an empty set of property values:</span></span>

<span data-ttu-id="ad4b2-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span><span class="sxs-lookup"><span data-stu-id="ad4b2-145">TranslatedNumber MatchingRule FirstMatchingRoute MatchingUsage</span></span>

<span data-ttu-id="ad4b2-146">\---------------- ------------ ------------------ -------------</span><span class="sxs-lookup"><span data-stu-id="ad4b2-146"></span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ad4b2-147">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="ad4b2-147">Reasons why the test might have failed</span></span>

<span data-ttu-id="ad4b2-148">CsVoiceUser Cmdlet 可能失敗的任何幾個原因：可能沒有可翻譯提供的電話號碼的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-148">There are any number of reasons why the Test-CsVoiceUser cmdlet might fail: there might not be a normalization rule that can translate the provided phone number.</span></span> <span data-ttu-id="ad4b2-149">語音路線可能出現問題。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-149">There could be problems with the voice route.</span></span> <span data-ttu-id="ad4b2-150">指派給該使用者的撥號方案可能有設定問題。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-150">There could be a configuration issue with the dial plan assigned to the user in question.</span></span> <span data-ttu-id="ad4b2-151">因此，您可能會想要在執行 Test CsVoiceUser Cmdlet 時加入詳細參數：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-151">Because of that, you might want to include the Verbose parameter when you are running the Test-CsVoiceUser cmdlet:</span></span>

`Test-CsVoiceUser -DialedNumber "+12065551219" -SipUri "sip:kenmyer@litwareinc.com" -Verbose`

<span data-ttu-id="ad4b2-152">加入詳細的 Cmdlet 時，測試 CsVoiceUser 會針對執行檢查時所採取的步驟，發出詳細的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-152">When the Verbose cmdlet is included, Test-CsVoiceUser will issue a detailed account of all the steps in takes when conducting its checks.</span></span> <span data-ttu-id="ad4b2-153">例如，您可能會看到類似以下的步驟：</span><span class="sxs-lookup"><span data-stu-id="ad4b2-153">For example, you might see steps similar to these:</span></span> 

<span data-ttu-id="ad4b2-154">詳細：尋找具有 [sip:kenmyer@litwareinc.com] 身分識別的使用者</span><span class="sxs-lookup"><span data-stu-id="ad4b2-154">VERBOSE: Locating user with identity "sip:kenmyer@litwareinc.com"</span></span>

<span data-ttu-id="ad4b2-155">詳細：載入撥號方案： "RedmondDialPlan"</span><span class="sxs-lookup"><span data-stu-id="ad4b2-155">VERBOSE: Loading dial plan: "RedmondDialPlan"</span></span>

<span data-ttu-id="ad4b2-156">此額外資訊可能會提供提示，以找出錯誤原因的相關步驟。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-156">This additional information can provide hints as to the steps that you can take to pinpoint the cause of the failure.</span></span> <span data-ttu-id="ad4b2-157">例如，這裡顯示的詳細輸出告訴我們，經過測試的使用者已獲指派撥號方案 RedmondDialPlan。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-157">For example, the verbose output shown here tells us that the user being tested was assigned the dial plan RedmondDialPlan.</span></span> <span data-ttu-id="ad4b2-158">如果測試失敗，下一個邏輯後續步驟就是確認 RedmondDialPlan 可以翻譯提供的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ad4b2-158">If the test has failed, one logical next step would be to verify that RedmondDialPlan can translate the supplied phone number.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad4b2-159">請參閱</span><span class="sxs-lookup"><span data-stu-id="ad4b2-159">See Also</span></span>


[<span data-ttu-id="ad4b2-160">Test-CsVoiceUser</span><span class="sxs-lookup"><span data-stu-id="ad4b2-160">Test-CsVoiceUser</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsVoiceUser)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

