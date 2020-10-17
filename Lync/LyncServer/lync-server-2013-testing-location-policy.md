---
title: Lync Server 2013：測試位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5cd477b02aa261b762f728ca15d296f49dfbac1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535990"
---
# <a name="testing-location-policy-in-lync-server-2013"></a><span data-ttu-id="dd06b-102">Lync Server 2013 中的測試位置原則</span><span class="sxs-lookup"><span data-stu-id="dd06b-102">Testing location policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd06b-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="dd06b-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd06b-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="dd06b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="dd06b-105">每日</span><span class="sxs-lookup"><span data-stu-id="dd06b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd06b-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="dd06b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="dd06b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd06b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd06b-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="dd06b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="dd06b-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="dd06b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="dd06b-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsLocationPolicy Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="dd06b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsLocationPolicy cmdlet.</span></span> <span data-ttu-id="dd06b-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="dd06b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="dd06b-112">描述</span><span class="sxs-lookup"><span data-stu-id="dd06b-112">Description</span></span>

<span data-ttu-id="dd06b-113">Test-CsLocationPolicy Cmdlet 會驗證是否已將位置原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="dd06b-113">The Test-CsLocationPolicy cmdlet verifies that a location policy is assigned to a user.</span></span> <span data-ttu-id="dd06b-114">位置原則用來套用與 E9-1-1 功能和用戶端位置相關的設定。</span><span class="sxs-lookup"><span data-stu-id="dd06b-114">The location policy is used to apply settings that relate to E9-1-1 functionality and client location.</span></span> <span data-ttu-id="dd06b-115">位置原則會決定使用者是否已啟用 E9-1-1，如果答案是「是」，表示緊急通話的行為為何。</span><span class="sxs-lookup"><span data-stu-id="dd06b-115">The location policy determines whether a user is enabled for E9-1-1, and, if the answer is "yes,", what the behavior is of an emergency call.</span></span> <span data-ttu-id="dd06b-116">例如，您可以使用位置原則來定義哪些號碼會在美國) 中 (911，是否應自動通知公司的安全性，以及如何路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="dd06b-116">For example, you can use the location policy to define what number makes up an emergency call (911 in the United States), whether corporate security should be automatically notified, and how the call should be routed.</span></span>

<span data-ttu-id="dd06b-117">您可以針對使用者或網路子網路測試位置原則。</span><span class="sxs-lookup"><span data-stu-id="dd06b-117">You can test location policies on users or on network subnets.</span></span> <span data-ttu-id="dd06b-118">如果您針對子網路執行測試 (透過指定 Subnet 參數的值)，Cmdlet 就會嘗試解析該子網路的位置原則。</span><span class="sxs-lookup"><span data-stu-id="dd06b-118">If you run the test against a subnet (by specifying a value for the Subnet parameter), the cmdlet will attempt to resolve the location policy for that subnet.</span></span> <span data-ttu-id="dd06b-119">如果該子網路未指派位置原則，則會擷取已設定之使用者的位置原則。</span><span class="sxs-lookup"><span data-stu-id="dd06b-119">If no location policy is assigned to the subnet, the location policy for the configured user will be retrieved.</span></span> <span data-ttu-id="dd06b-120">如果成功地取回子網原則，輸出會包含以 subnet-tagid 開頭的 LocationPolicyTagID 值。</span><span class="sxs-lookup"><span data-stu-id="dd06b-120">If the subnet policy is retrieved successfully, the output will include a LocationPolicyTagID value that begins with subnet-tagid.</span></span> <span data-ttu-id="dd06b-121">如果找不到子網路的位置原則，則 LocationPolicyTagID 的開頭為 user-tagid。</span><span class="sxs-lookup"><span data-stu-id="dd06b-121">If a location policy for the subnet was not found, the LocationPolicyTagID will begin with user-tagid.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="dd06b-122">執行測試</span><span class="sxs-lookup"><span data-stu-id="dd06b-122">Running the test</span></span>

<span data-ttu-id="dd06b-123">您可以使用預先設定的測試帳戶執行 Test-CsLocationPolicy Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd06b-123">The Test-CsLocationPolicy cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="dd06b-124">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync 伺服器集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="dd06b-124">To run this check using a test account, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="dd06b-125">例如：</span><span class="sxs-lookup"><span data-stu-id="dd06b-125">For example:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="dd06b-126">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="dd06b-126">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="dd06b-127">接著，當您呼叫 Test-CsLocationPolicy 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="dd06b-127">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsLocationPolicy:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="dd06b-128">如需詳細資訊，請參閱 [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="dd06b-128">For more information, see the Help documentation for the [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="dd06b-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="dd06b-129">Determining success or failure</span></span>

<span data-ttu-id="dd06b-130">如果指定的使用者有有效的位置原則，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="dd06b-130">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="dd06b-131">EnhancedEmergencyServicesEnabled： true</span><span class="sxs-lookup"><span data-stu-id="dd06b-131">EnhancedEmergencyServicesEnabled : true</span></span>

<span data-ttu-id="dd06b-132">LocationPolicyTagID： user-tagid</span><span class="sxs-lookup"><span data-stu-id="dd06b-132">LocationPolicyTagID : user-tagid</span></span>

<span data-ttu-id="dd06b-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd06b-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd06b-134">結果：成功</span><span class="sxs-lookup"><span data-stu-id="dd06b-134">Result : Success</span></span>

<span data-ttu-id="dd06b-135">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="dd06b-135">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="dd06b-136">錯誤：</span><span class="sxs-lookup"><span data-stu-id="dd06b-136">Error :</span></span>

<span data-ttu-id="dd06b-137">診斷：</span><span class="sxs-lookup"><span data-stu-id="dd06b-137">Diagnosis :</span></span>

<span data-ttu-id="dd06b-138">如果找不到指定使用者的有效位置原則，則會顯示 [結果]，並在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="dd06b-138">If a valid location policy cannot be found for the specified user, then Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="dd06b-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd06b-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd06b-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="dd06b-140">Result : Failure</span></span>

<span data-ttu-id="dd06b-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="dd06b-141">Latency : 00:00:00</span></span>

<span data-ttu-id="dd06b-142">錯誤：404，未找到</span><span class="sxs-lookup"><span data-stu-id="dd06b-142">Error : 404, Not Found</span></span>

<span data-ttu-id="dd06b-143">診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="dd06b-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="dd06b-144">原因 = 未啟用 SIP 的目的 URI 或不是</span><span class="sxs-lookup"><span data-stu-id="dd06b-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="dd06b-145">存在。</span><span class="sxs-lookup"><span data-stu-id="dd06b-145">exist.</span></span>

<span data-ttu-id="dd06b-146">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="dd06b-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="dd06b-147">先前的輸出指出測試失敗的原因是指定的使用者無效：帳戶不存在，或尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd06b-147">The previous output states that the test failed because the specified user is not valid: either the account does not exist or the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="dd06b-148">您可以驗證帳戶是否有效，以及執行類似如下的命令，以判斷該帳戶是否已啟用（包含）。</span><span class="sxs-lookup"><span data-stu-id="dd06b-148">You can verify the validity of an account, and determine whether or not that account has been enabled for nm-ocs-14-3rd, by running a command similar to this:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

<span data-ttu-id="dd06b-149">如果 Test-CsLocationPolicy 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="dd06b-149">If Test-CsLocationPolicy fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="dd06b-150">包含 Verbose 參數時，Test-CsLocationPolicy 會傳回在驗證位置原則時所嘗試之每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd06b-150">When the Verbose parameter is included, Test-CsLocationPolicy will return a step-by-step account of each action it tried when verifying the location policy.</span></span> <span data-ttu-id="dd06b-151">例如，此輸出表示 Lync Server 無法登入測試使用者，可能是因為提供的密碼無效：</span><span class="sxs-lookup"><span data-stu-id="dd06b-151">For example, this output indicates that Lync Server couldn't log on the test user, probably because an invalid password was supplied:</span></span>

<span data-ttu-id="dd06b-152">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="dd06b-152">Sending Registration request :</span></span>

<span data-ttu-id="dd06b-153">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd06b-153">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="dd06b-154">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="dd06b-154">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="dd06b-155">註冊機構埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="dd06b-155">Registrar Port = 5061</span></span>

<span data-ttu-id="dd06b-156">已選取驗證類型 ' IWA '。</span><span class="sxs-lookup"><span data-stu-id="dd06b-156">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="dd06b-157">對 sip/atl-cs-001-001 的註冊點擊 litwareinc</span><span class="sxs-lookup"><span data-stu-id="dd06b-157">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="dd06b-158">' Register ' activity 在 ' 0.0601795 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="dd06b-158">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="dd06b-159">「登入已遭拒絕」例外狀況。</span><span class="sxs-lookup"><span data-stu-id="dd06b-159">An exception 'The log on was denied.</span></span> <span data-ttu-id="dd06b-160">請檢查是否已使用正確的認證，以及帳戶是否有效。 '</span><span class="sxs-lookup"><span data-stu-id="dd06b-160">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="dd06b-161">在工作流程中發生。</span><span class="sxs-lookup"><span data-stu-id="dd06b-161">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="dd06b-162">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="dd06b-162">Reasons why the test might have failed</span></span>

<span data-ttu-id="dd06b-163">以下是一些 Test-CsLocationPolicy 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="dd06b-163">Here are some common reasons why Test-CsLocationPolicy might fail:</span></span>

  - <span data-ttu-id="dd06b-164">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="dd06b-164">You specified a user account that is not valid.</span></span> <span data-ttu-id="dd06b-165">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="dd06b-165">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="dd06b-166">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd06b-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="dd06b-167">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="dd06b-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="dd06b-168">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="dd06b-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

