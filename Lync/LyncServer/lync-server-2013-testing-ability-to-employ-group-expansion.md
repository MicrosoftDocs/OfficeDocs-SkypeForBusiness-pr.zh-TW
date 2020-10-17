---
title: Lync Server 2013：測試使用群組擴充的能力
description: Lync Server 2013：測試使用群組擴充的能力。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6267bc2099fc420c5c57e1ef80f4bf4491334938
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560789"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="e812c-103">在 Lync Server 2013 中測試使用群組擴充的能力</span><span class="sxs-lookup"><span data-stu-id="e812c-103">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e812c-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e812c-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e812c-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e812c-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e812c-106">每日</span><span class="sxs-lookup"><span data-stu-id="e812c-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e812c-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="e812c-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e812c-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e812c-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e812c-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e812c-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e812c-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e812c-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e812c-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsGroupExpansion Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e812c-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="e812c-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e812c-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e812c-113">描述</span><span class="sxs-lookup"><span data-stu-id="e812c-113">Description</span></span>

<span data-ttu-id="e812c-114">Test-CsGroupExpansion Cmdlet 可讓您判斷群組擴充是否可在組織內運作。</span><span class="sxs-lookup"><span data-stu-id="e812c-114">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="e812c-115">啟用群組擴充功能時，使用者會將通訊群組設定為連絡人。</span><span class="sxs-lookup"><span data-stu-id="e812c-115">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="e812c-116">這表示，使用者可以將郵件定為群組，而不是該群組的個別成員，就能將相同的立即訊息傳送給所有群組成員。</span><span class="sxs-lookup"><span data-stu-id="e812c-116">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="e812c-117">群組擴充功能可讓您快速而輕鬆地查看所有群組成員及其目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="e812c-117">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="e812c-118">使用 Test-CsGroupExpansion Cmdlet，您可以使用群組的電子郵件地址來指定 Active Directory 通訊群組。</span><span class="sxs-lookup"><span data-stu-id="e812c-118">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="e812c-119">Test-CsGroupExpansion 然後使用群組擴充來取得群組成員資格，並將所檢索的清單與所提供之群組電子郵件地址的成員資格進行比較。</span><span class="sxs-lookup"><span data-stu-id="e812c-119">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="e812c-120">如果兩個清單相符，群組擴充就能正常運作。</span><span class="sxs-lookup"><span data-stu-id="e812c-120">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="e812c-121">請注意，您可以使用兩種方式測試群組擴充：測試服務本身，或測試相關聯的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="e812c-121">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="e812c-122">如需詳細資訊，請參閱 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e812c-122">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e812c-123">執行測試</span><span class="sxs-lookup"><span data-stu-id="e812c-123">Running the test</span></span>

<span data-ttu-id="e812c-124">您可以使用預先設定的測試帳戶執行 Test-CsGroupExpansion Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何已啟用 Lync Server 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e812c-124">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="e812c-125">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN 和有效通訊群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="e812c-125">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="e812c-126">例如：</span><span class="sxs-lookup"><span data-stu-id="e812c-126">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="e812c-127">若要使用實際使用者帳戶執行這種檢查，您必須先建立一個包含帳戶名稱和密碼的 Lync Server 身分憑證物件。</span><span class="sxs-lookup"><span data-stu-id="e812c-127">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="e812c-128">然後，您必須在系統呼叫 Test-CsGroupExpansion 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="e812c-128">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="e812c-129">如需詳細資訊，請參閱 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e812c-129">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e812c-130">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e812c-130">Determining success or failure</span></span>

<span data-ttu-id="e812c-131">如果指定的使用者可以使用群組擴充，您會收到類似下列的輸出，其 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="e812c-131">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e812c-132">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e812c-132">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e812c-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e812c-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e812c-134">結果：成功</span><span class="sxs-lookup"><span data-stu-id="e812c-134">Result : Success</span></span>

<span data-ttu-id="e812c-135">延遲：00：00：01.1234976</span><span class="sxs-lookup"><span data-stu-id="e812c-135">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="e812c-136">錯誤：</span><span class="sxs-lookup"><span data-stu-id="e812c-136">Error :</span></span>

<span data-ttu-id="e812c-137">診斷：</span><span class="sxs-lookup"><span data-stu-id="e812c-137">Diagnosis :</span></span>

<span data-ttu-id="e812c-138">如果指定的使用者無法使用群組擴充，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e812c-138">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e812c-139">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="e812c-139">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="e812c-140">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e812c-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e812c-141">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="e812c-141">Result : Failure</span></span>

<span data-ttu-id="e812c-142">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="e812c-142">Latency : 00:00:00</span></span>

<span data-ttu-id="e812c-143">錯誤：</span><span class="sxs-lookup"><span data-stu-id="e812c-143">Error :</span></span>

<span data-ttu-id="e812c-144">診斷：</span><span class="sxs-lookup"><span data-stu-id="e812c-144">Diagnosis :</span></span>

<span data-ttu-id="e812c-145">Test-CsGroupExpansion：端點無法註冊。</span><span class="sxs-lookup"><span data-stu-id="e812c-145">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="e812c-146">如需特定原因，請參閱 ErrorCode。</span><span class="sxs-lookup"><span data-stu-id="e812c-146">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="e812c-147">先前的輸出表明測試失敗，因為指定的使用者無法使用 Lync Server 註冊。</span><span class="sxs-lookup"><span data-stu-id="e812c-147">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="e812c-148">如果測試帳戶不存在或尚未對 Lync Server 啟用，則通常會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e812c-148">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="e812c-149">您可以確認該帳戶是否存在，並執行類似如下的命令，以判斷該帳戶是否已啟用（如有）。</span><span class="sxs-lookup"><span data-stu-id="e812c-149">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="e812c-150">如果 Test-CsGroupExpansion 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="e812c-150">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="e812c-151">包含 Verbose 參數時 Test-CsGroupExpansion 會傳回每個動作的逐步帳戶，檢查所嘗試的特定使用者登入 Lync Server 的能力。</span><span class="sxs-lookup"><span data-stu-id="e812c-151">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="e812c-152">例如，下列輸出指出找不到指定的通訊群組：</span><span class="sxs-lookup"><span data-stu-id="e812c-152">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="e812c-153">嘗試取得 web 票證。</span><span class="sxs-lookup"><span data-stu-id="e812c-153">Trying to get web ticket.</span></span>

<span data-ttu-id="e812c-154">Web 服務 url： https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="e812c-154">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="e812c-155">使用 NTLM/Kerb 驗證。</span><span class="sxs-lookup"><span data-stu-id="e812c-155">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="e812c-156">GetWebTicketActivity 已完成。</span><span class="sxs-lookup"><span data-stu-id="e812c-156">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="e812c-157">' VerifyDistributionList ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="e812c-157">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="e812c-158">DLX Web 服務回應狀態為： NotFound。</span><span class="sxs-lookup"><span data-stu-id="e812c-158">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="e812c-159">' VerifyDistributionList ' activity 在 ' 0.2597923 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="e812c-159">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e812c-160">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e812c-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="e812c-161">以下是一些 Test-CsGroupExpansion 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="e812c-161">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="e812c-162">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="e812c-162">You specified an invalid user account.</span></span> <span data-ttu-id="e812c-163">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="e812c-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e812c-164">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e812c-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e812c-165">若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="e812c-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e812c-166">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="e812c-166">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="e812c-167">可能停用群組擴充。</span><span class="sxs-lookup"><span data-stu-id="e812c-167">Group expansion might be disabled.</span></span> <span data-ttu-id="e812c-168">可以關閉群組擴充。</span><span class="sxs-lookup"><span data-stu-id="e812c-168">It is possible to turn off group expansion.</span></span> <span data-ttu-id="e812c-169">如果停用群組擴充，Test-CsGroupExpansion Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="e812c-169">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="e812c-170">若要判斷是否已啟用群組擴充，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="e812c-170">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

