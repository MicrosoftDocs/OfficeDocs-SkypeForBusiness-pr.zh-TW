---
title: Lync Server 2013：測試群組 IM 的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8552d5caadf26d70265f5538f10c6152eb67dcc8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="07231-102">在 Lync Server 2013 中進行群組 IM 的測試能力</span><span class="sxs-lookup"><span data-stu-id="07231-102">Testing ability to do group IM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07231-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="07231-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="07231-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="07231-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="07231-105">日常</span><span class="sxs-lookup"><span data-stu-id="07231-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="07231-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="07231-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="07231-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07231-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="07231-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="07231-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="07231-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="07231-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="07231-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsGroupIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="07231-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="07231-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="07231-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="07231-112">說明</span><span class="sxs-lookup"><span data-stu-id="07231-112">Description</span></span>

<span data-ttu-id="07231-113">CsGroupIM Cmdlet 會確認貴組織中的使用者可以執行群組立即訊息會話。</span><span class="sxs-lookup"><span data-stu-id="07231-113">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="07231-114">當您執行 Test CsGroupIM 時，此 Cmdlet 會嘗試將一組測試使用者登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="07231-114">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="07231-115">如果成功，測試 CsGroupIM 會使用第一個測試使用者建立新的會議，然後邀請第二位使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="07231-115">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="07231-116">在交換郵件之後，這兩個使用者就會中斷與系統的連線。</span><span class="sxs-lookup"><span data-stu-id="07231-116">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="07231-117">請注意，所有這一切都不會發生任何使用者互動，也不會影響任何實際的使用者。</span><span class="sxs-lookup"><span data-stu-id="07231-117">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="07231-118">例如，假設 [測試帳戶 sip:kenmyer@litwareinc.com] 對應給擁有真正的 Lync 伺服器帳戶的真實使用者。</span><span class="sxs-lookup"><span data-stu-id="07231-118">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="07231-119">在這種情況下，將會執行測試，而不會對真正的 Ken Myer 造成任何干擾。</span><span class="sxs-lookup"><span data-stu-id="07231-119">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="07231-120">例如，即使 Ken Myer 測試帳戶登入系統，該人員仍會保持登入狀態。</span><span class="sxs-lookup"><span data-stu-id="07231-120">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="07231-121">同樣地，實際的 Ken Myer 不會收到加入會議的邀請。</span><span class="sxs-lookup"><span data-stu-id="07231-121">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="07231-122">該邀請將由測試帳戶傳送給及接受。</span><span class="sxs-lookup"><span data-stu-id="07231-122">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="07231-123">如需詳細資訊，請參閱[Test CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="07231-123">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="07231-124">執行測試</span><span class="sxs-lookup"><span data-stu-id="07231-124">Running the test</span></span>

<span data-ttu-id="07231-125">CsGroupIM Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="07231-125">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="07231-126">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="07231-126">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="07231-127">例如：</span><span class="sxs-lookup"><span data-stu-id="07231-127">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="07231-128">若要使用實際的使用者帳戶執行此檢查，您必須為每個帳戶建立兩個 Lync Server 管理命令介面身分憑證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="07231-128">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="07231-129">當您呼叫 Test CsGroupIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="07231-129">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="07231-130">如需詳細資訊，請參閱[Test CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="07231-130">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="07231-131">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="07231-131">Determining Success or Failure</span></span>

<span data-ttu-id="07231-132">如果兩個使用者可以完成群組立即訊息會話，您會收到類似以下的輸出，並將 Result 屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="07231-132">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="07231-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07231-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="07231-134">結果：成功</span><span class="sxs-lookup"><span data-stu-id="07231-134">Result : Success</span></span>

<span data-ttu-id="07231-135">延隔時間：00：00：06.3812203</span><span class="sxs-lookup"><span data-stu-id="07231-135">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="07231-136">出錯</span><span class="sxs-lookup"><span data-stu-id="07231-136">Error :</span></span>

<span data-ttu-id="07231-137">自檢</span><span class="sxs-lookup"><span data-stu-id="07231-137">Diagnosis :</span></span>

<span data-ttu-id="07231-138">如果兩個使用者無法完成立即訊息會話，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="07231-138">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="07231-139">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07231-139">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="07231-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="07231-140">Result : Failure</span></span>

<span data-ttu-id="07231-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="07231-141">Latency : 00:00:00</span></span>

<span data-ttu-id="07231-142">錯誤：404，找不到</span><span class="sxs-lookup"><span data-stu-id="07231-142">Error : 404, Not Found</span></span>

<span data-ttu-id="07231-143">診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="07231-143">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="07231-144">原因 = 無法針對 SIP 啟用目的 URI，或無法</span><span class="sxs-lookup"><span data-stu-id="07231-144">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="07231-145">有.</span><span class="sxs-lookup"><span data-stu-id="07231-145">exist.</span></span>

<span data-ttu-id="07231-146">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="07231-146">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="07231-147">由於帳戶不存在或使用者尚未啟用 Lync Server，所以先前的輸出指出測試失敗的原因，因為至少有一個測試帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="07231-147">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="07231-148">您可以透過執行如下命令，確認帳戶存在，以及帳戶是否已啟用 nm-ocs-14-3：</span><span class="sxs-lookup"><span data-stu-id="07231-148">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="07231-149">如果測試 CsGroupIM 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="07231-149">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="07231-150">在包含詳細參數的情況下，CsGroupIM 會在檢查指定使用者在群組立即訊息會話中的每個動作時，傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="07231-150">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="07231-151">例如，如果您的測試失敗，而且您收到一或多個使用者帳戶無效，您可以使用詳細參數重新執行測試，並判斷哪個使用者帳戶無效：</span><span class="sxs-lookup"><span data-stu-id="07231-151">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="07231-152">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="07231-152">Sending Registration request:</span></span>

 <span data-ttu-id="07231-153">目標 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07231-153">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="07231-154">使用者 SIP 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="07231-154">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="07231-155">寄存器埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="07231-155">Register Port    = 5061</span></span>

<span data-ttu-id="07231-156">已選取 Auth 類型 ' IWA」。</span><span class="sxs-lookup"><span data-stu-id="07231-156">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="07231-157">[登錄已遭到拒絕] 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="07231-157">An exception 'The log on was denied.</span></span> <span data-ttu-id="07231-158">檢查是否已使用正確的認證，且帳戶處於作用中」</span><span class="sxs-lookup"><span data-stu-id="07231-158">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="07231-159">您可以看到，在這個範例中，擁有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者無法登入。</span><span class="sxs-lookup"><span data-stu-id="07231-159">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="07231-160">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="07231-160">Reasons why the test might have failed</span></span>

<span data-ttu-id="07231-161">以下是測試 CsGroupIM 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="07231-161">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="07231-162">您指定的使用者帳戶不正確。</span><span class="sxs-lookup"><span data-stu-id="07231-162">You specified an incorrect user account.</span></span> <span data-ttu-id="07231-163">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="07231-163">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="07231-164">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="07231-164">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="07231-165">若要確認使用者帳戶已啟用 Lync Server，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="07231-165">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="07231-166">Move-csuser "sip:kenmyer@litwareinc.com" |選取-已啟用物件</span><span class="sxs-lookup"><span data-stu-id="07231-166">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="07231-167">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="07231-167">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="07231-168">[立即訊息服務] 可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="07231-168">The instant messaging service might not be available.</span></span> <span data-ttu-id="07231-169">使用 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，立即訊息無法使用。</span><span class="sxs-lookup"><span data-stu-id="07231-169">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="07231-170">您可以執行類似下列的命令來驗證：</span><span class="sxs-lookup"><span data-stu-id="07231-170">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="07231-171">如果 BlockOnArchiveFailure 設定為 True，則應該判斷封存資料庫是否可用。</span><span class="sxs-lookup"><span data-stu-id="07231-171">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="07231-172">您可以使用下列命令，返回封存資料庫的位置：</span><span class="sxs-lookup"><span data-stu-id="07231-172">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="07231-173">存檔伺服器可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="07231-173">The Archiving Server might not be available.</span></span> <span data-ttu-id="07231-174">您可以使用此命令來檢索封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="07231-174">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="07231-175">接著，您可以 ping 適當的伺服器，確認它可以使用。</span><span class="sxs-lookup"><span data-stu-id="07231-175">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="07231-176">例如：</span><span class="sxs-lookup"><span data-stu-id="07231-176">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

