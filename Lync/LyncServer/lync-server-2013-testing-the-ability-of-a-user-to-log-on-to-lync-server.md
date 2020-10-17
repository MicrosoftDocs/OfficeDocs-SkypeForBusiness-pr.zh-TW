---
title: Lync Server 2013：測試使用者登入 Lync Server 的能力
description: Lync Server 2013：測試使用者登入 Lync Server 的能力。
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
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556209"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a><span data-ttu-id="533fb-103">測試使用者登入 Lync Server 2013 的能力</span><span class="sxs-lookup"><span data-stu-id="533fb-103">Testing the ability of a user to log on to Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="533fb-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="533fb-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="533fb-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="533fb-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="533fb-106">每日</span><span class="sxs-lookup"><span data-stu-id="533fb-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="533fb-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="533fb-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="533fb-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="533fb-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="533fb-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="533fb-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="533fb-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="533fb-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="533fb-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsRegistration Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="533fb-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsRegistration cmdlet.</span></span> <span data-ttu-id="533fb-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="533fb-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="533fb-113">描述</span><span class="sxs-lookup"><span data-stu-id="533fb-113">Description</span></span>

<span data-ttu-id="533fb-114">Test-CsRegistration Cmdlet 可讓您確認組織中的使用者是否可以登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="533fb-114">The Test-CsRegistration cmdlet enables you to verify that users in your organization can log on to Lync Server.</span></span> <span data-ttu-id="533fb-115">當您執行 Test-CsRegistration 時，指令程式會嘗試將測試使用者登入 Lync Server，如果成功，則會將測試使用者從系統上中斷連接。</span><span class="sxs-lookup"><span data-stu-id="533fb-115">When you run Test-CsRegistration, the cmdlet attempts to sign in a test user to Lync Server and then, if it is successful, disconnects that test user from the system.</span></span> <span data-ttu-id="533fb-116">發生以上所有狀況時，都不會有任何使用者介入，也不會影響任何實際的使用者。</span><span class="sxs-lookup"><span data-stu-id="533fb-116">All of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="533fb-117">例如，假設「測試帳戶 sip:kenmyer@litwareinc.com」會對應至具有實際 Lync 伺服器帳戶的實際使用者。</span><span class="sxs-lookup"><span data-stu-id="533fb-117">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="533fb-118">在該情況下，測試將會在不干擾實際的 Ken Myer 的情況下進行。</span><span class="sxs-lookup"><span data-stu-id="533fb-118">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="533fb-119">當 Ken Myer 測試帳戶從系統登出時，他將繼續登入的 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="533fb-119">When the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="533fb-120">執行測試</span><span class="sxs-lookup"><span data-stu-id="533fb-120">Running the test</span></span>

<span data-ttu-id="533fb-121">您可以使用預先設定的測試帳戶執行 Test-CsRegistration Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="533fb-121">The Test-CsRegistration cmdlet can be run using either a preconfigured test account (see Setting Up Test Accounts for Running Lync Server Tests) or the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="533fb-122">若要使用測試帳戶執行這項檢查，您只需要指定所測試之 Lync Server 註冊集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="533fb-122">To run this check using a test account, you just have to specify the FQDN of the Lync Server Registrar pool being tested.</span></span> <span data-ttu-id="533fb-123">例如：</span><span class="sxs-lookup"><span data-stu-id="533fb-123">For example:</span></span>

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="533fb-124">若要使用實際使用者帳戶執行這種檢查，您必須先建立 Windows PowerShell 身分憑證物件，其中包含帳戶名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="533fb-124">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="533fb-125">接著，當您呼叫 Test-CsRegistration 時，必須包含該認證物件和指派給該帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="533fb-125">You must then include that credentials object and the SIP address assigned to the account when you call Test-CsRegistration:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="533fb-126">如需詳細資訊，請參閱 [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="533fb-126">For more information, see the Help documentation for the [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="533fb-127">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="533fb-127">Determining success or failure</span></span>

<span data-ttu-id="533fb-128">如果指定的使用者可以登入 (，然後從) Lync Server 登出，您會收到與結果屬性標示為「成功」類似的輸出 **：**</span><span class="sxs-lookup"><span data-stu-id="533fb-128">If the specified user can log on to (and then log off from) Lync Server, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="533fb-129">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="533fb-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="533fb-130">結果：成功</span><span class="sxs-lookup"><span data-stu-id="533fb-130">Result : Success</span></span>

<span data-ttu-id="533fb-131">延遲：00：00：06.8630376</span><span class="sxs-lookup"><span data-stu-id="533fb-131">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="533fb-132">錯誤：</span><span class="sxs-lookup"><span data-stu-id="533fb-132">Error :</span></span>

<span data-ttu-id="533fb-133">診斷：</span><span class="sxs-lookup"><span data-stu-id="533fb-133">Diagnosis :</span></span>

<span data-ttu-id="533fb-134">如果指定的使用者無法登入或登出，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="533fb-134">If the specified user can't log in or log out, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="533fb-135">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="533fb-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="533fb-136">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="533fb-136">Result : Failure</span></span>

<span data-ttu-id="533fb-137">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="533fb-137">Latency : 00:00:00</span></span>

<span data-ttu-id="533fb-138">錯誤：404，未找到</span><span class="sxs-lookup"><span data-stu-id="533fb-138">Error : 404, Not Found</span></span>

<span data-ttu-id="533fb-139">診斷： ErrorCode = 1003，source = atl-ws-01，Reason，Reason = User 執行的動作</span><span class="sxs-lookup"><span data-stu-id="533fb-139">Diagnosis : ErrorCode=1003,source=atl-cs-001.litwareinc.com,Reason=User does</span></span>

<span data-ttu-id="533fb-140">不存在</span><span class="sxs-lookup"><span data-stu-id="533fb-140">not exist</span></span>

<span data-ttu-id="533fb-141">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="533fb-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="533fb-142">例如，由於找不到指定的使用者，所以先前的輸出會指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="533fb-142">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="533fb-143">您可以執行下列命令，判斷 SIP 位址是否有效 (和使用者指派該 SIP 位址是否已啟用 Lync Server) ：</span><span class="sxs-lookup"><span data-stu-id="533fb-143">You can determine whether or not a SIP address is valid (and whether the user assigned that SIP address is enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "sip:kenmyer@litwareinc.com"

<span data-ttu-id="533fb-144">如果 Test-CsRegistration 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="533fb-144">If Test-CsRegistration fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="533fb-145">包含 Verbose 參數時，Test-CsRegistration 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="533fb-145">When the Verbose parameter is included, Test-CsRegistration will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="533fb-146">例如：</span><span class="sxs-lookup"><span data-stu-id="533fb-146">For example:</span></span>

<span data-ttu-id="533fb-147">詳細：「註冊」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="533fb-147">VERBOSE: 'Register' activity started.</span></span>

<span data-ttu-id="533fb-148">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="533fb-148">Sending Registration request:</span></span>

<span data-ttu-id="533fb-149">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="533fb-149">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="533fb-150">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="533fb-150">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="533fb-151">註冊機構埠 = 5061。</span><span class="sxs-lookup"><span data-stu-id="533fb-151">Registrar Port = 5061.</span></span>

<span data-ttu-id="533fb-152">已選取 Auth Type ' Trusted」。</span><span class="sxs-lookup"><span data-stu-id="533fb-152">Auth Type 'Trusted' is selected.</span></span>

<span data-ttu-id="533fb-153">無法註冊端點的例外狀況。</span><span class="sxs-lookup"><span data-stu-id="533fb-153">An exception 'The endpoint is unable to register.</span></span> <span data-ttu-id="533fb-154">請參閱在工作流程 SyntheticTransactions 期間發生的特定原因的 ErrorCode STRegistrerWorkflow 執行。</span><span class="sxs-lookup"><span data-stu-id="533fb-154">See the ErrorCode for specific reason' occurred during Workflow Microsoft.Rtc.SyntheticTransactions.Workflow.STRegistrerWorkflow execution.</span></span>

<span data-ttu-id="533fb-155">例外狀況堆疊：在 SipAsyncResult'1 中，ThrowIfFailed ( # A1</span><span class="sxs-lookup"><span data-stu-id="533fb-155">Exception Call Stack: at Microsoft.Rtc.Signaling.SipAsyncResult'1.ThrowIfFailed()</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="533fb-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="533fb-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="533fb-157">以下是一些 Test-CsRegistration 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="533fb-157">Here are some common reasons why Test-CsRegistration might fail:</span></span>

  - <span data-ttu-id="533fb-158">您指定了錯誤的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="533fb-158">You specified an incorrect user account.</span></span> <span data-ttu-id="533fb-159">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="533fb-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="533fb-160">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="533fb-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="533fb-161">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="533fb-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="533fb-162">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="533fb-162">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="533fb-163">您指定了不正確的註冊集區。</span><span class="sxs-lookup"><span data-stu-id="533fb-163">You specified an incorrect Registrar pool.</span></span> <span data-ttu-id="533fb-164">您可以使用下列命令傳回註冊機集區的 Fqdn：</span><span class="sxs-lookup"><span data-stu-id="533fb-164">You can return the FQDNs of your Registrar pools by using this command:</span></span>
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - <span data-ttu-id="533fb-165">註冊機構集區目前無法使用。</span><span class="sxs-lookup"><span data-stu-id="533fb-165">The Registrar pool is currently not available.</span></span> <span data-ttu-id="533fb-166">請嘗試 ping 集區，以查看它是否回應：</span><span class="sxs-lookup"><span data-stu-id="533fb-166">Try pinging the pool to see whether it responds:</span></span>
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

