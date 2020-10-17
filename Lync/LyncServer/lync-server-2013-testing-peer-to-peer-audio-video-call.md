---
title: Lync Server 2013：測試對等音訊/視頻通話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8522a1f3a8aedd44a6d39faa0ba6f59ba773677
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504080"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="d970c-102">在 Lync Server 2013 中測試對等音訊/視頻通話</span><span class="sxs-lookup"><span data-stu-id="d970c-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d970c-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="d970c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d970c-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d970c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d970c-105">每日</span><span class="sxs-lookup"><span data-stu-id="d970c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d970c-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="d970c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d970c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d970c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d970c-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d970c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d970c-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d970c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d970c-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsP2PAV Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d970c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="d970c-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d970c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d970c-112">描述</span><span class="sxs-lookup"><span data-stu-id="d970c-112">Description</span></span>

<span data-ttu-id="d970c-113">Test-CsP2PAV 是用來判斷一組測試使用者是否可以參與對等 A/V 交談。</span><span class="sxs-lookup"><span data-stu-id="d970c-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="d970c-114">若要測試此案例，指令程式會從兩個使用者登入 Lync Server，以啟動 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d970c-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="d970c-115">假設這兩次登入都成功，則第一位使用者會邀請第二位使用者加入 A/V 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d970c-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="d970c-116">第二位使用者接受通話時，會測試兩位使用者之間的連線，然後結束通話，然後從系統中登出測試使用者。</span><span class="sxs-lookup"><span data-stu-id="d970c-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="d970c-117">Test-CsP2PAV 實際上不會進行 A/V 通話。</span><span class="sxs-lookup"><span data-stu-id="d970c-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="d970c-118">測試使用者間的多媒體資訊不會互換。</span><span class="sxs-lookup"><span data-stu-id="d970c-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="d970c-119">相反地，此 Cmdlet 只會驗證是否可以進行適當的連線，以及兩位使用者是否可以進行這類呼叫。</span><span class="sxs-lookup"><span data-stu-id="d970c-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="d970c-120">如需詳細資訊，請參閱 [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="d970c-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d970c-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="d970c-121">Running the test</span></span>

<span data-ttu-id="d970c-122">您可以使用一對預先設定的測試帳戶來執行 Test-CsP2PAV Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d970c-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="d970c-123">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d970c-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="d970c-124">例如：</span><span class="sxs-lookup"><span data-stu-id="d970c-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="d970c-125">若要使用實際使用者帳戶執行這項檢查，您必須為每個帳戶 (包含帳戶名稱和密碼) 的物件建立兩個 Lync Server 身分憑證物件。</span><span class="sxs-lookup"><span data-stu-id="d970c-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="d970c-126">當您呼叫 Test-CsP2PAV 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="d970c-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d970c-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d970c-127">Determining success or failure</span></span>

<span data-ttu-id="d970c-128">如果兩個測試使用者可以完成對等 A/V 呼叫，則會收到與結果屬性標示為「成功」類似的輸出 **：**</span><span class="sxs-lookup"><span data-stu-id="d970c-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="d970c-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d970c-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d970c-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="d970c-130">Result : Success</span></span>

<span data-ttu-id="d970c-131">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="d970c-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="d970c-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="d970c-132">Error :</span></span>

<span data-ttu-id="d970c-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="d970c-133">Diagnosis :</span></span>

<span data-ttu-id="d970c-134">如果測試使用者無法完成通話，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="d970c-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d970c-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d970c-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d970c-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="d970c-136">Result : Failure</span></span>

<span data-ttu-id="d970c-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="d970c-137">Latency : 00:00:00</span></span>

<span data-ttu-id="d970c-138">錯誤：480，暫時無法使用</span><span class="sxs-lookup"><span data-stu-id="d970c-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="d970c-139">診斷： ErrorCode = 15030，Source = atl-cs-001，Reason = Failed</span><span class="sxs-lookup"><span data-stu-id="d970c-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="d970c-140">路由傳送至 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="d970c-140">to route to Exchange Server</span></span>

<span data-ttu-id="d970c-141">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="d970c-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="d970c-142">例如，上一個輸出會指出測試失敗，因為無法與 Microsoft Exchange Server 取得聯繫。</span><span class="sxs-lookup"><span data-stu-id="d970c-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="d970c-143">這項錯誤訊息通常表示 Exchange 整合通訊的設定發生問題。</span><span class="sxs-lookup"><span data-stu-id="d970c-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="d970c-144">如果 Test-CsP2PAV 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="d970c-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="d970c-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose</span><span class="sxs-lookup"><span data-stu-id="d970c-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="d970c-146">包含 Verbose 參數時，Test-CsP2PAV 將會傳回其嘗試的每個動作的逐步帳戶，以檢查指定使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="d970c-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="d970c-147">例如，假設測試失敗併發生下列診斷：</span><span class="sxs-lookup"><span data-stu-id="d970c-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="d970c-148">ErrorCode = 6003，Source = atl-ws-01-cs-001，Reason = 不支援的對話方塊要求</span><span class="sxs-lookup"><span data-stu-id="d970c-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="d970c-149">如果您重新執行 Test-CsP2PAV 並包含 Verbose 參數，您會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="d970c-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="d970c-150">詳細：「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="d970c-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="d970c-151">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="d970c-151">Sending Registration request:</span></span>

<span data-ttu-id="d970c-152">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d970c-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="d970c-153">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d970c-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="d970c-154">註冊機構埠 = 5062。</span><span class="sxs-lookup"><span data-stu-id="d970c-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="d970c-155">已選取驗證類型 ' IWA '。</span><span class="sxs-lookup"><span data-stu-id="d970c-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="d970c-156">無法註冊端點的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="d970c-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="d970c-157">如需特定原因，請參閱 ErrorCode。 '</span><span class="sxs-lookup"><span data-stu-id="d970c-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="d970c-158">在工作流程 SyntheticTransactions 中發生 STP2PAVWorkflow 執行。</span><span class="sxs-lookup"><span data-stu-id="d970c-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="d970c-159">雖然它可能不會立即顯而易見，但如果您仔細檢查輸出，您會看到不正確的註冊埠 (埠 5062) 指定。</span><span class="sxs-lookup"><span data-stu-id="d970c-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="d970c-160">進而又導致測試失敗。</span><span class="sxs-lookup"><span data-stu-id="d970c-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d970c-161">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d970c-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="d970c-162">以下是一些 Test-CsP2PAV 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="d970c-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="d970c-163">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="d970c-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="d970c-164">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="d970c-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="d970c-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="d970c-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="d970c-166">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d970c-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="d970c-167">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="d970c-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="d970c-168">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="d970c-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

