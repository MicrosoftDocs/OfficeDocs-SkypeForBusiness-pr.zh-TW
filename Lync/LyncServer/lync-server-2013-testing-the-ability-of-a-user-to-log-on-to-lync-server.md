---
title: Lync Server 2013：測試使用者登入 Lync Server 的能力
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="49bb3-102">測試使用者登入 Lync Server 2013 的能力</span><span class="sxs-lookup"><span data-stu-id="49bb3-102">Testing the ability of a user to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49bb3-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="49bb3-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="49bb3-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="49bb3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="49bb3-105">日常</span><span class="sxs-lookup"><span data-stu-id="49bb3-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="49bb3-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="49bb3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="49bb3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="49bb3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="49bb3-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="49bb3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="49bb3-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="49bb3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="49bb3-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsRegistration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="49bb3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="49bb3-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="49bb3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="49bb3-112">說明</span><span class="sxs-lookup"><span data-stu-id="49bb3-112">Description</span></span>

<span data-ttu-id="49bb3-113">CsRegistration Cmdlet 可讓您確認貴組織中的使用者可以登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="49bb3-113">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="49bb3-114">當您執行 Test CsRegistration 時，此 Cmdlet 會嘗試將測試使用者登入 Lync Server，然後，如果成功，則會將測試使用者從系統中斷連線。</span><span class="sxs-lookup"><span data-stu-id="49bb3-114">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="49bb3-115">在任何情況下，都不會發生任何使用者互動，也不會影響任何實際的使用者。</span><span class="sxs-lookup"><span data-stu-id="49bb3-115">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="49bb3-116">例如，假設 [測試帳戶 sip:kenmyer@litwareinc.com] 對應給擁有真正的 Lync 伺服器帳戶的真實使用者。</span><span class="sxs-lookup"><span data-stu-id="49bb3-116">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="49bb3-117">在這種情況下，將會執行測試，而不會對真正的 Ken Myer 造成任何干擾。</span><span class="sxs-lookup"><span data-stu-id="49bb3-117">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="49bb3-118">當 Ken Myer 測試帳戶從系統登出時，該人員將會保持登入狀態的 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="49bb3-118">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="49bb3-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="49bb3-119">Running the test</span></span>

<span data-ttu-id="49bb3-120">CsRegistration Cmdlet 可以使用預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶）或任何已啟用 Lync Server 的使用者帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="49bb3-120">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="49bb3-121">若要使用測試帳戶執行這項檢查，您只需指定要測試的 Lync Server 註冊機構的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="49bb3-121">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="49bb3-122">例如：</span><span class="sxs-lookup"><span data-stu-id="49bb3-122">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="49bb3-123">若要使用實際的使用者帳戶執行此檢查，您必須先建立包含帳戶名稱和密碼的 Windows PowerShell 認證物件。</span><span class="sxs-lookup"><span data-stu-id="49bb3-123">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="49bb3-124">當您呼叫 Test CsRegistration 時，您必須包含該認證物件以及指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="49bb3-124">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="49bb3-125">如需詳細資訊，請參閱[Test CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="49bb3-125">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="49bb3-126">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="49bb3-126">Determining success or failure</span></span>

<span data-ttu-id="49bb3-127">如果指定的使用者可以登入（然後從 Lync Server 登出），您將會收到類似以下的輸出，並將 Result 屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="49bb3-127">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="49bb3-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49bb3-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49bb3-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="49bb3-129">Result : Success</span></span>

<span data-ttu-id="49bb3-130">延隔時間：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="49bb3-130">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="49bb3-131">出錯</span><span class="sxs-lookup"><span data-stu-id="49bb3-131">Error :</span></span>

<span data-ttu-id="49bb3-132">自檢</span><span class="sxs-lookup"><span data-stu-id="49bb3-132">Diagnosis :</span></span>

<span data-ttu-id="49bb3-133">如果指定的使用者無法登入或登出，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="49bb3-133">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="49bb3-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49bb3-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="49bb3-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="49bb3-135">Result : Failure</span></span>

<span data-ttu-id="49bb3-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="49bb3-136">Latency : 00:00:00</span></span>

<span data-ttu-id="49bb3-137">錯誤：404，找不到</span><span class="sxs-lookup"><span data-stu-id="49bb3-137">Error : 404, Not Found</span></span>

<span data-ttu-id="49bb3-138">診斷： ErrorCode = 1003，來源 = atl-cs-001. litwareinc，原因 = 使用者執行</span><span class="sxs-lookup"><span data-stu-id="49bb3-138">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="49bb3-139">不存在</span><span class="sxs-lookup"><span data-stu-id="49bb3-139">not exist</span></span>

<span data-ttu-id="49bb3-140">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="49bb3-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="49bb3-141">例如，由於找不到指定的使用者，所以先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="49bb3-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="49bb3-142">您可以執行此命令來判斷 SIP 位址是否有效（以及使用者是否已為 Lync Server 啟用指派該 SIP 位址的使用者）：</span><span class="sxs-lookup"><span data-stu-id="49bb3-142">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="49bb3-143">如果測試 CsRegistration 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="49bb3-143">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="49bb3-144">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsRegistration 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bb3-144">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="49bb3-145">例如：</span><span class="sxs-lookup"><span data-stu-id="49bb3-145">For example:</span></span>

<span data-ttu-id="49bb3-146">詳細：「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="49bb3-146">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="49bb3-147">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="49bb3-147">Sending Registration request:</span></span>

<span data-ttu-id="49bb3-148">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49bb3-148">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="49bb3-149">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="49bb3-149">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="49bb3-150">註冊機構埠 = 5061。</span><span class="sxs-lookup"><span data-stu-id="49bb3-150">Registrar Port = 5061.</span></span>

<span data-ttu-id="49bb3-151">已選取 [已信任] 驗證類型。</span><span class="sxs-lookup"><span data-stu-id="49bb3-151">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="49bb3-152">無法註冊端點的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="49bb3-152">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="49bb3-153">請參閱在工作流程 SyntheticTransactions STRegistrerWorkflow 執行期間發生的特定原因的 ErrorCode。</span><span class="sxs-lookup"><span data-stu-id="49bb3-153">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="49bb3-154">例外狀況堆疊： SipAsyncResult'1 （ThrowIfFailed （））</span><span class="sxs-lookup"><span data-stu-id="49bb3-154">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="49bb3-155">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="49bb3-155">Reasons why the test might have failed</span></span>

<span data-ttu-id="49bb3-156">以下是測試 CsRegistration 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="49bb3-156">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="49bb3-157">您指定的使用者帳戶不正確。</span><span class="sxs-lookup"><span data-stu-id="49bb3-157">You specified an incorrect user account.</span></span> <span data-ttu-id="49bb3-158">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="49bb3-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="49bb3-159">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="49bb3-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="49bb3-160">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="49bb3-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="49bb3-161">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="49bb3-161">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="49bb3-162">您指定的註冊機構池不正確。</span><span class="sxs-lookup"><span data-stu-id="49bb3-162">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="49bb3-163">您可以使用此命令傳回註冊機構池的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="49bb3-163">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="49bb3-164">註冊機構池目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="49bb3-164">The Registrar pool is currently not available.</span></span> <span data-ttu-id="49bb3-165">嘗試 ping 該池以查看它是否回應：</span><span class="sxs-lookup"><span data-stu-id="49bb3-165">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

