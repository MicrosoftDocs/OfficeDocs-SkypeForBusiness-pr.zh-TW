---
title: Lync Server 2013：測試位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e034be609bfe773a15935d7f0875e0155b57df75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="716b1-102">在 Lync Server 2013 中測試位置原則</span><span class="sxs-lookup"><span data-stu-id="716b1-102">Testing location policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="716b1-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="716b1-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="716b1-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="716b1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="716b1-105">日常</span><span class="sxs-lookup"><span data-stu-id="716b1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="716b1-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="716b1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="716b1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="716b1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="716b1-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="716b1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="716b1-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="716b1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="716b1-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsLocationPolicy Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="716b1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="716b1-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="716b1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="716b1-112">描述</span><span class="sxs-lookup"><span data-stu-id="716b1-112">Description</span></span>

<span data-ttu-id="716b1-113">Test CsLocationPolicy Cmdlet 會驗證是否已將位置原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="716b1-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="716b1-114">位置原則是用來套用與 E9-1-1 功能及用戶端位置相關的設定。</span><span class="sxs-lookup"><span data-stu-id="716b1-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="716b1-115">位置原則會判斷使用者是否已啟用 E9-1-1，如果答案是「是」，則是緊急通話的行為。</span><span class="sxs-lookup"><span data-stu-id="716b1-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="716b1-116">例如，您可以使用位置原則來定義哪一個號碼是由緊急通話（911在美國）、企業安全性是否應該自動通知，以及應該如何傳送通話。</span><span class="sxs-lookup"><span data-stu-id="716b1-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="716b1-117">您可以在使用者或網路子網上測試位置原則。</span><span class="sxs-lookup"><span data-stu-id="716b1-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="716b1-118">如果您針對子網執行測試（透過指定子網參數的值），則 Cmdlet 會嘗試解析該子網上的位置原則。</span><span class="sxs-lookup"><span data-stu-id="716b1-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="716b1-119">如果未將位置原則指派給子網，則會檢索已設定使用者的位置原則。</span><span class="sxs-lookup"><span data-stu-id="716b1-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="716b1-120">如果成功地檢索到子網原則，則輸出會包含以 subnet-tagid 開頭的 LocationPolicyTagID 值。</span><span class="sxs-lookup"><span data-stu-id="716b1-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="716b1-121">如果找不到子網的位置原則，LocationPolicyTagID 將會以使用者 tagid 開始。</span><span class="sxs-lookup"><span data-stu-id="716b1-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="716b1-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="716b1-122">Running the test</span></span>

<span data-ttu-id="716b1-123">CsLocationPolicy Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="716b1-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="716b1-124">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="716b1-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="716b1-125">例如：</span><span class="sxs-lookup"><span data-stu-id="716b1-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="716b1-126">若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="716b1-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="716b1-127">當您呼叫 Test CsLocationPolicy 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="716b1-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="716b1-128">如需詳細資訊，請參閱[Test CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="716b1-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="716b1-129">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="716b1-129">Determining success or failure</span></span>

<span data-ttu-id="716b1-130">如果指定的使用者有有效的位置原則，您將會收到類似這樣的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="716b1-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="716b1-131">EnhancedEmergencyServicesEnabled： true</span><span class="sxs-lookup"><span data-stu-id="716b1-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="716b1-132">LocationPolicyTagID：使用者-tagid</span><span class="sxs-lookup"><span data-stu-id="716b1-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="716b1-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="716b1-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="716b1-134">結果：成功</span><span class="sxs-lookup"><span data-stu-id="716b1-134">Result : Success</span></span>

<span data-ttu-id="716b1-135">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="716b1-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="716b1-136">出錯</span><span class="sxs-lookup"><span data-stu-id="716b1-136">Error :</span></span>

<span data-ttu-id="716b1-137">自檢</span><span class="sxs-lookup"><span data-stu-id="716b1-137">Diagnosis :</span></span>

<span data-ttu-id="716b1-138">如果找不到指定使用者的有效位置原則，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="716b1-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="716b1-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="716b1-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="716b1-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="716b1-140">Result : Failure</span></span>

<span data-ttu-id="716b1-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="716b1-141">Latency : 00:00:00</span></span>

<span data-ttu-id="716b1-142">錯誤：404，找不到</span><span class="sxs-lookup"><span data-stu-id="716b1-142">Error : 404, Not Found</span></span>

<span data-ttu-id="716b1-143">診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="716b1-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="716b1-144">原因 = 無法針對 SIP 啟用目的 URI，或無法</span><span class="sxs-lookup"><span data-stu-id="716b1-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="716b1-145">有.</span><span class="sxs-lookup"><span data-stu-id="716b1-145">exist.</span></span>

<span data-ttu-id="716b1-146">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="716b1-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="716b1-147">先前的輸出指出測試失敗的原因是指定的使用者無效：帳戶不存在，或尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="716b1-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="716b1-148">您可以透過執行如下的命令，來確認帳戶的有效性，並判斷是否已啟用 nm 版 ocs-14-協力廠商的帳戶：</span><span class="sxs-lookup"><span data-stu-id="716b1-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="716b1-149">如果測試 CsLocationPolicy 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="716b1-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="716b1-150">包含詳細參數時，測試 CsLocationPolicy 會傳回在驗證位置原則時所嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="716b1-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="716b1-151">例如，此輸出表示 Lync Server 無法登入測試使用者，可能是因為提供了不正確密碼：</span><span class="sxs-lookup"><span data-stu-id="716b1-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="716b1-152">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="716b1-152">Sending Registration request :</span></span>

<span data-ttu-id="716b1-153">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="716b1-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="716b1-154">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="716b1-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="716b1-155">註冊機構埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="716b1-155">Registrar Port = 5061</span></span>

<span data-ttu-id="716b1-156">已選取 Auth 類型 ' IWA」。</span><span class="sxs-lookup"><span data-stu-id="716b1-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="716b1-157">針對 sip/atl-cs-001-litwareinc 的註冊。</span><span class="sxs-lookup"><span data-stu-id="716b1-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="716b1-158">"Register" 活動在 "0.0601795" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="716b1-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="716b1-159">[登錄已遭到拒絕] 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="716b1-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="716b1-160">檢查是否已使用正確的認證，且帳戶處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="716b1-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="716b1-161">在工作流程期間發生。</span><span class="sxs-lookup"><span data-stu-id="716b1-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="716b1-162">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="716b1-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="716b1-163">以下是測試 CsLocationPolicy 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="716b1-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="716b1-164">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="716b1-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="716b1-165">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="716b1-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="716b1-166">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="716b1-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="716b1-167">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="716b1-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="716b1-168">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="716b1-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

