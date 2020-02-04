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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a><span data-ttu-id="391ca-102">在 Lync Server 2013 中測試對等音訊/視頻通話</span><span class="sxs-lookup"><span data-stu-id="391ca-102">Testing peer to peer audio/video call in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="391ca-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="391ca-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="391ca-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="391ca-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="391ca-105">日常</span><span class="sxs-lookup"><span data-stu-id="391ca-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="391ca-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="391ca-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="391ca-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="391ca-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="391ca-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="391ca-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="391ca-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="391ca-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="391ca-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsP2PAV Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="391ca-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsP2PAV cmdlet.</span></span> <span data-ttu-id="391ca-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="391ca-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="391ca-112">說明</span><span class="sxs-lookup"><span data-stu-id="391ca-112">Description</span></span>

<span data-ttu-id="391ca-113">Test-CsP2PAV 是用來判斷一組測試使用者是否可以參與對等 A/V 交談。</span><span class="sxs-lookup"><span data-stu-id="391ca-113">Test-CsP2PAV is used to determine whether a pair of test users can participate in a peer-to-peer A/V conversation.</span></span> <span data-ttu-id="391ca-114">若要測試這種情況，請將兩位使用者登入 Lync Server，然後啟動 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="391ca-114">To test this scenario, the cmdlet starts off by logging on the two users to Lync Server.</span></span> <span data-ttu-id="391ca-115">假設兩次登錄成功，則第一個使用者接著邀請第二位使用者加入 A/V 通話。</span><span class="sxs-lookup"><span data-stu-id="391ca-115">Assuming that the two logons succeed, the first user then invites the second user to join an A/V call.</span></span> <span data-ttu-id="391ca-116">第二個使用者接受通話，兩個使用者之間的連線就會得到測試，然後通話就會結束，並從系統登出測試使用者。</span><span class="sxs-lookup"><span data-stu-id="391ca-116">The second user accepts the call, the connection between the two users is tested, and then the call is ended and the test users are logged off from the system.</span></span>

<span data-ttu-id="391ca-117">測試 CsP2PAV 並不會實際執行 A/V 通話。</span><span class="sxs-lookup"><span data-stu-id="391ca-117">Test-CsP2PAV does not actually conduct an A/V call.</span></span> <span data-ttu-id="391ca-118">不會在測試使用者之間交換多媒體資訊。</span><span class="sxs-lookup"><span data-stu-id="391ca-118">Multimedia information is not exchanged between the test users.</span></span> <span data-ttu-id="391ca-119">相反地，此 Cmdlet 只會驗證是否可以建立適當的連線，以及兩位使用者可以進行這類通話。</span><span class="sxs-lookup"><span data-stu-id="391ca-119">Instead, the cmdlet merely verifies that the appropriate connections can be made and that the two users can conduct such a call.</span></span>

<span data-ttu-id="391ca-120">如需詳細資訊，請參閱[Test CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="391ca-120">For more information, see the Help documentation for the [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="391ca-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="391ca-121">Running the test</span></span>

<span data-ttu-id="391ca-122">CsP2PAV Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="391ca-122">The Test-CsP2PAV cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="391ca-123">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="391ca-123">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="391ca-124">例如：</span><span class="sxs-lookup"><span data-stu-id="391ca-124">For example:</span></span>

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="391ca-125">若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Lync Server 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="391ca-125">To run this check using actual user accounts, you must create two Lync Server credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="391ca-126">當您呼叫 Test CsP2PAV 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="391ca-126">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsP2PAV:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="391ca-127">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="391ca-127">Determining success or failure</span></span>

<span data-ttu-id="391ca-128">如果兩個測試使用者可以完成對等 A/V 通話，您就會收到類似以下的輸出，並將 Result 屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="391ca-128">If the two test users can complete a peer-to-peer A/V call, then you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="391ca-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="391ca-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="391ca-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="391ca-130">Result : Success</span></span>

<span data-ttu-id="391ca-131">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="391ca-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="391ca-132">出錯</span><span class="sxs-lookup"><span data-stu-id="391ca-132">Error :</span></span>

<span data-ttu-id="391ca-133">自檢</span><span class="sxs-lookup"><span data-stu-id="391ca-133">Diagnosis :</span></span>

<span data-ttu-id="391ca-134">如果測試使用者無法完成通話，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="391ca-134">If the test users can't complete the call, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="391ca-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="391ca-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="391ca-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="391ca-136">Result : Failure</span></span>

<span data-ttu-id="391ca-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="391ca-137">Latency : 00:00:00</span></span>

<span data-ttu-id="391ca-138">錯誤：480，暫時無法使用</span><span class="sxs-lookup"><span data-stu-id="391ca-138">Error : 480, Temporarily Unavailable</span></span>

<span data-ttu-id="391ca-139">診斷： ErrorCode = 15030，Source = atl-cs-001. litwareinc，原因 = 失敗</span><span class="sxs-lookup"><span data-stu-id="391ca-139">Diagnosis : ErrorCode=15030,Source=atl-cs-001.litwareinc.com,Reason=Failed</span></span>

<span data-ttu-id="391ca-140">傳送到 Exchange Server</span><span class="sxs-lookup"><span data-stu-id="391ca-140">to route to Exchange Server</span></span>

<span data-ttu-id="391ca-141">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="391ca-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="391ca-142">例如，由於無法連絡 Microsoft Exchange Server，所以先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="391ca-142">For example, the previous output states that the test failed because the Microsoft Exchange Server couldn't be contacted.</span></span> <span data-ttu-id="391ca-143">此錯誤訊息通常表示 Exchange 整合訊息設定的問題。</span><span class="sxs-lookup"><span data-stu-id="391ca-143">This error message typically indicates a problem the configuration of Exchange Unified Messaging.</span></span>

<span data-ttu-id="391ca-144">如果測試 CsP2PAV 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="391ca-144">If Test-CsP2PAV fails then you might want to rerun the test, this time including the Verbose parameter:</span></span>

<span data-ttu-id="391ca-145">Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-詳細資訊</span><span class="sxs-lookup"><span data-stu-id="391ca-145">Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose</span></span>

<span data-ttu-id="391ca-146">在包含詳細參數時，測試 CsP2PAV 會傳回其在檢查指定使用者登入 Lync Server 的能力時所嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="391ca-146">When the Verbose parameter is included, Test-CsP2PAV will return a step-by-step account of each action it tried as it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="391ca-147">例如，假設您的測試由於下列診斷而失敗：</span><span class="sxs-lookup"><span data-stu-id="391ca-147">For example, suppose that your test failed with the following Diagnosis:</span></span>

<span data-ttu-id="391ca-148">ErrorCode = 6003，Source = atl-ws-01 = cs-001. litwareinc，Reason = 不支援的對話方塊要求</span><span class="sxs-lookup"><span data-stu-id="391ca-148">ErrorCode=6003,Source=atl-cs-001.litwareinc.com,Reason=Unsupported out of dialog request</span></span>

<span data-ttu-id="391ca-149">如果您重新執行 Test CsP2PAV 並包含 Verbose 參數，就會收到類似以下的輸出：</span><span class="sxs-lookup"><span data-stu-id="391ca-149">If you rerun Test-CsP2PAV and include the Verbose parameter, you'll get output similar to this:</span></span>

<span data-ttu-id="391ca-150">詳細：「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="391ca-150">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="391ca-151">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="391ca-151">Sending Registration request:</span></span>

<span data-ttu-id="391ca-152">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="391ca-152">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="391ca-153">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="391ca-153">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="391ca-154">註冊機構埠 = 5062。</span><span class="sxs-lookup"><span data-stu-id="391ca-154">Registrar Port = 5062.</span></span>

<span data-ttu-id="391ca-155">已選取 Auth 類型 ' IWA」。</span><span class="sxs-lookup"><span data-stu-id="391ca-155">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="391ca-156">無法註冊端點的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="391ca-156">An exception 'The endpoint was unable to register.</span></span> <span data-ttu-id="391ca-157">請參閱錯誤的特定原因。</span><span class="sxs-lookup"><span data-stu-id="391ca-157">See the ErrorCode for specific reason.'</span></span> <span data-ttu-id="391ca-158">在工作流程 SyntheticTransactions STP2PAVWorkflow 執行期間發生。</span><span class="sxs-lookup"><span data-stu-id="391ca-158">occurred during workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STP2PAVWorkflow execution.</span></span>

<span data-ttu-id="391ca-159">雖然這可能不會立即明顯，但如果您仔細檢查輸出，您會看到指定的註冊埠（埠5062）不正確。</span><span class="sxs-lookup"><span data-stu-id="391ca-159">Although it might not be immediately obvious, if you examine the output carefully you’ll see that an incorrect Registrar port (port 5062) was specified.</span></span> <span data-ttu-id="391ca-160">進而導致測試失敗。</span><span class="sxs-lookup"><span data-stu-id="391ca-160">In turn, that caused the test to fail.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="391ca-161">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="391ca-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="391ca-162">以下是測試 CsP2PAV 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="391ca-162">Here are some common reasons why Test-CsP2PAV might fail:</span></span>

  - <span data-ttu-id="391ca-163">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="391ca-163">You specified a user account that is not valid.</span></span> <span data-ttu-id="391ca-164">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="391ca-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
    <span data-ttu-id="391ca-165">Move-csuser "sip:kenmyer@litwareinc.com"</span><span class="sxs-lookup"><span data-stu-id="391ca-165">Get-CsUser "sip:kenmyer@litwareinc.com"</span></span>

  - <span data-ttu-id="391ca-166">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="391ca-166">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="391ca-167">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="391ca-167">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="391ca-168">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="391ca-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

