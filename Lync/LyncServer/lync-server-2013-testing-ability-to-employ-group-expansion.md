---
title: Lync Server 2013：測試使用群組擴充的能力
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
ms.openlocfilehash: e8c12d687d6c23c7c7bdc2bf2d8046038154c871
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520740"
---
# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a><span data-ttu-id="1ca01-102">在 Lync Server 2013 中測試使用群組擴充的能力</span><span class="sxs-lookup"><span data-stu-id="1ca01-102">Testing ability to employ group expansion in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ca01-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1ca01-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ca01-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="1ca01-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1ca01-105">每日</span><span class="sxs-lookup"><span data-stu-id="1ca01-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ca01-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="1ca01-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1ca01-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ca01-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ca01-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="1ca01-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1ca01-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="1ca01-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1ca01-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsGroupExpansion Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="1ca01-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupExpansion cmdlet.</span></span> <span data-ttu-id="1ca01-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="1ca01-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1ca01-112">描述</span><span class="sxs-lookup"><span data-stu-id="1ca01-112">Description</span></span>

<span data-ttu-id="1ca01-113">Test-CsGroupExpansion Cmdlet 可讓您判斷群組擴充是否可在組織內運作。</span><span class="sxs-lookup"><span data-stu-id="1ca01-113">The Test-CsGroupExpansion cmdlet lets you determine whether group expansion is working within your organization.</span></span> <span data-ttu-id="1ca01-114">啟用群組擴充功能時，使用者會將通訊群組設定為連絡人。</span><span class="sxs-lookup"><span data-stu-id="1ca01-114">When group expansion is enabled, users configure distribution groups as a contact.</span></span> <span data-ttu-id="1ca01-115">這表示，使用者可以將郵件定為群組，而不是該群組的個別成員，就能將相同的立即訊息傳送給所有群組成員。</span><span class="sxs-lookup"><span data-stu-id="1ca01-115">That means that those users can then send the same instant message to all the group members by addressing the message to the group instead of to individual members of that group.</span></span> <span data-ttu-id="1ca01-116">群組擴充功能可讓您快速而輕鬆地查看所有群組成員及其目前的狀態。</span><span class="sxs-lookup"><span data-stu-id="1ca01-116">Group expansion enables you to quickly and easily view all the group members and their current status.</span></span>

<span data-ttu-id="1ca01-117">使用 Test-CsGroupExpansion Cmdlet，您可以使用群組的電子郵件地址來指定 Active Directory 通訊群組。</span><span class="sxs-lookup"><span data-stu-id="1ca01-117">With the Test-CsGroupExpansion cmdlet, you specify an Active Directory distribution group by using the group’s email address.</span></span> <span data-ttu-id="1ca01-118">Test-CsGroupExpansion 然後使用群組擴充來取得群組成員資格，並將所檢索的清單與所提供之群組電子郵件地址的成員資格進行比較。</span><span class="sxs-lookup"><span data-stu-id="1ca01-118">Test-CsGroupExpansion then uses group expansion to retrieve the group membership and compare the retrieved list to the membership of the group email address that you supplied.</span></span> <span data-ttu-id="1ca01-119">如果兩個清單相符，群組擴充就能正常運作。</span><span class="sxs-lookup"><span data-stu-id="1ca01-119">If the two lists match, then group expansion is working correctly.</span></span> <span data-ttu-id="1ca01-120">請注意，您可以使用兩種方式測試群組擴充：測試服務本身，或測試相關聯的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="1ca01-120">Note that you can test group expansion in two ways: by testing the service itself or by testing the associated web service.</span></span>

<span data-ttu-id="1ca01-121">如需詳細資訊，請參閱 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="1ca01-121">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1ca01-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="1ca01-122">Running the test</span></span>

<span data-ttu-id="1ca01-123">您可以使用預先設定的測試帳戶執行 Test-CsGroupExpansion Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何已啟用 Lync Server 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ca01-123">The Test-CsGroupExpansion cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who was enabled for Lync Server.</span></span> <span data-ttu-id="1ca01-124">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN 和有效通訊群組的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1ca01-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested and the email address for a valid distribution group.</span></span> <span data-ttu-id="1ca01-125">例如：</span><span class="sxs-lookup"><span data-stu-id="1ca01-125">For example:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

<span data-ttu-id="1ca01-126">若要使用實際使用者帳戶執行這種檢查，您必須先建立一個包含帳戶名稱和密碼的 Lync Server 身分憑證物件。</span><span class="sxs-lookup"><span data-stu-id="1ca01-126">To run this check using an actual user account, you must first create a Lync Server credentials object that contains the account name and password.</span></span> <span data-ttu-id="1ca01-127">然後，您必須在系統呼叫 Test-CsGroupExpansion 時，包含該身分憑證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="1ca01-127">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsGroupExpansion:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="1ca01-128">如需詳細資訊，請參閱 [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="1ca01-128">For more information, see the Help documentation for the [Test-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1ca01-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="1ca01-129">Determining success or failure</span></span>

<span data-ttu-id="1ca01-130">如果指定的使用者可以使用群組擴充，您會收到類似下列的輸出，其 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="1ca01-130">If the specified user can use group expansion, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1ca01-131">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="1ca01-131">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="1ca01-132">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1ca01-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1ca01-133">結果：成功</span><span class="sxs-lookup"><span data-stu-id="1ca01-133">Result : Success</span></span>

<span data-ttu-id="1ca01-134">延遲：00：00：01.1234976</span><span class="sxs-lookup"><span data-stu-id="1ca01-134">Latency : 00:00:01.1234976</span></span>

<span data-ttu-id="1ca01-135">錯誤：</span><span class="sxs-lookup"><span data-stu-id="1ca01-135">Error :</span></span>

<span data-ttu-id="1ca01-136">診斷：</span><span class="sxs-lookup"><span data-stu-id="1ca01-136">Diagnosis :</span></span>

<span data-ttu-id="1ca01-137">如果指定的使用者無法使用群組擴充，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="1ca01-137">If the specified user can't use group expansion, then the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1ca01-138">TargetUri： https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span><span class="sxs-lookup"><span data-stu-id="1ca01-138">TargetUri : https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc</span></span>

<span data-ttu-id="1ca01-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1ca01-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1ca01-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="1ca01-140">Result : Failure</span></span>

<span data-ttu-id="1ca01-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="1ca01-141">Latency : 00:00:00</span></span>

<span data-ttu-id="1ca01-142">錯誤：</span><span class="sxs-lookup"><span data-stu-id="1ca01-142">Error :</span></span>

<span data-ttu-id="1ca01-143">診斷：</span><span class="sxs-lookup"><span data-stu-id="1ca01-143">Diagnosis :</span></span>

<span data-ttu-id="1ca01-144">Test-CsGroupExpansion：端點無法註冊。</span><span class="sxs-lookup"><span data-stu-id="1ca01-144">Test-CsGroupExpansion : The endpoint was unable to register.</span></span> <span data-ttu-id="1ca01-145">如需特定原因，請參閱 ErrorCode。</span><span class="sxs-lookup"><span data-stu-id="1ca01-145">See the ErrorCode for specific reason.</span></span>

<span data-ttu-id="1ca01-146">先前的輸出表明測試失敗，因為指定的使用者無法使用 Lync Server 註冊。</span><span class="sxs-lookup"><span data-stu-id="1ca01-146">The previous output states that the test failed because the specified user was unable to register with Lync Server.</span></span> <span data-ttu-id="1ca01-147">如果測試帳戶不存在或尚未對 Lync Server 啟用，則通常會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="1ca01-147">This will typically occur if the test account does not exist or has not enabled for Lync Server.</span></span> <span data-ttu-id="1ca01-148">您可以確認該帳戶是否存在，並執行類似如下的命令，以判斷該帳戶是否已啟用（如有）。</span><span class="sxs-lookup"><span data-stu-id="1ca01-148">You can verify that the account exists, and determine whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to the following:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="1ca01-149">如果 Test-CsGroupExpansion 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="1ca01-149">If Test-CsGroupExpansion fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

<span data-ttu-id="1ca01-150">包含 Verbose 參數時 Test-CsGroupExpansion 會傳回每個動作的逐步帳戶，檢查所嘗試的特定使用者登入 Lync Server 的能力。</span><span class="sxs-lookup"><span data-stu-id="1ca01-150">When the Verbose parameter is included Test-CsGroupExpansion will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="1ca01-151">例如，下列輸出指出找不到指定的通訊群組：</span><span class="sxs-lookup"><span data-stu-id="1ca01-151">For example, this output indicates that the specified distribution group couldn't be found:</span></span>

<span data-ttu-id="1ca01-152">嘗試取得 web 票證。</span><span class="sxs-lookup"><span data-stu-id="1ca01-152">Trying to get web ticket.</span></span>

<span data-ttu-id="1ca01-153">Web 服務 url： https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span><span class="sxs-lookup"><span data-stu-id="1ca01-153">Web Service url : https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc</span></span>

<span data-ttu-id="1ca01-154">使用 NTLM/Kerb 驗證。</span><span class="sxs-lookup"><span data-stu-id="1ca01-154">Using NTLM/Kerb auth.</span></span>

<span data-ttu-id="1ca01-155">GetWebTicketActivity 已完成。</span><span class="sxs-lookup"><span data-stu-id="1ca01-155">GetWebTicketActivity completed.</span></span>

<span data-ttu-id="1ca01-156">' VerifyDistributionList ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="1ca01-156">'VerifyDistributionList' activity started.</span></span>

<span data-ttu-id="1ca01-157">DLX Web 服務回應狀態為： NotFound。</span><span class="sxs-lookup"><span data-stu-id="1ca01-157">DLX Web Service Response Status is: NotFound.</span></span>

<span data-ttu-id="1ca01-158">' VerifyDistributionList ' activity 在 ' 0.2597923 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="1ca01-158">'VerifyDistributionList' activity completed in '0.2597923' secs.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1ca01-159">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="1ca01-159">Reasons why the test might have failed</span></span>

<span data-ttu-id="1ca01-160">以下是一些 Test-CsGroupExpansion 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="1ca01-160">Here are some common reasons why Test-CsGroupExpansion might fail:</span></span>

  - <span data-ttu-id="1ca01-161">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="1ca01-161">You specified an invalid user account.</span></span> <span data-ttu-id="1ca01-162">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="1ca01-162">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1ca01-163">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ca01-163">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="1ca01-164">若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="1ca01-164">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="1ca01-165">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="1ca01-165">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="1ca01-166">可能停用群組擴充。</span><span class="sxs-lookup"><span data-stu-id="1ca01-166">Group expansion might be disabled.</span></span> <span data-ttu-id="1ca01-167">可以關閉群組擴充。</span><span class="sxs-lookup"><span data-stu-id="1ca01-167">It is possible to turn off group expansion.</span></span> <span data-ttu-id="1ca01-168">如果停用群組擴充，Test-CsGroupExpansion Cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="1ca01-168">If group expansion was disabled then the Test-CsGroupExpansion cmdlet will fail.</span></span> <span data-ttu-id="1ca01-169">若要判斷是否已啟用群組擴充，請使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="1ca01-169">To determine whether group expansion is enabled, use a command similar to this:</span></span>
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

