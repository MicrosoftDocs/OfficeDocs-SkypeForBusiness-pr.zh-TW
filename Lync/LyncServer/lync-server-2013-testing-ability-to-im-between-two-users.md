---
title: Lync Server 2013：測試在兩個使用者之間 IM 的功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ea824216c456e9f673a5383eab0b788933bf53d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="7c085-102">在 Lync Server 2013 的兩位使用者之間進行 IM 測試的功能</span><span class="sxs-lookup"><span data-stu-id="7c085-102">Testing ability to IM between two users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c085-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="7c085-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c085-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="7c085-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="7c085-105">日常</span><span class="sxs-lookup"><span data-stu-id="7c085-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c085-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="7c085-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="7c085-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7c085-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c085-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="7c085-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="7c085-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="7c085-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="7c085-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="7c085-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="7c085-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7c085-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="7c085-112">描述</span><span class="sxs-lookup"><span data-stu-id="7c085-112">Description</span></span>

<span data-ttu-id="7c085-113">CsIM Cmdlet 會驗證一對測試使用者可以交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="7c085-113">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="7c085-114">在呼叫時，CsIM Cmdlet 會嘗試將一組測試使用者登入 Lync Server 來啟動。</span><span class="sxs-lookup"><span data-stu-id="7c085-114">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="7c085-115">假設兩次登入成功，則 Cmdlet 會在兩個測試使用者之間啟動 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="7c085-115">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="7c085-116">（使用者1邀請使用者2加入 IM 會話，而使用者2則接受邀請。）在確認郵件可以在兩個使用者之間交換之後，測試 CsIM 接著結束 IM 會話，並將使用者從系統中記錄。</span><span class="sxs-lookup"><span data-stu-id="7c085-116">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="7c085-117">如需詳細資訊，請參閱[Test CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="7c085-117">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="7c085-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="7c085-118">Running the Test</span></span>

<span data-ttu-id="7c085-119">CsIM Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="7c085-119">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="7c085-120">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="7c085-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="7c085-121">例如：</span><span class="sxs-lookup"><span data-stu-id="7c085-121">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="7c085-122">若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="7c085-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="7c085-123">當您呼叫 Test CsIM 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="7c085-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="7c085-124">如需詳細資訊，請參閱[Test CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="7c085-124">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="7c085-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="7c085-125">Determining Success or Failure</span></span>

<span data-ttu-id="7c085-126">如果兩個使用者可以完成立即訊息會話，您將會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="7c085-126">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="7c085-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c085-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c085-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="7c085-128">Result : Success</span></span>

<span data-ttu-id="7c085-129">延隔時間：00：00：06.6630911</span><span class="sxs-lookup"><span data-stu-id="7c085-129">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="7c085-130">出錯</span><span class="sxs-lookup"><span data-stu-id="7c085-130">Error :</span></span>

<span data-ttu-id="7c085-131">自檢</span><span class="sxs-lookup"><span data-stu-id="7c085-131">Diagnosis :</span></span>

<span data-ttu-id="7c085-132">如果測試使用者無法完成會話，結果就會顯示為失敗，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="7c085-132">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="7c085-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c085-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c085-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="7c085-134">Result : Failure</span></span>

<span data-ttu-id="7c085-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="7c085-135">Latency : 00:00:00</span></span>

<span data-ttu-id="7c085-136">錯誤：504，伺服器超時</span><span class="sxs-lookup"><span data-stu-id="7c085-136">Error : 504, Server time-out</span></span>

<span data-ttu-id="7c085-137">診斷： ErrorCode = 2，Source = litwareinc = atl-ws-01，原因 = 請參閱</span><span class="sxs-lookup"><span data-stu-id="7c085-137">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="7c085-138">回應程式碼與原因片語。</span><span class="sxs-lookup"><span data-stu-id="7c085-138">response code and reason phrase.</span></span>

<span data-ttu-id="7c085-139">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="7c085-139">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="7c085-140">例如，由於找不到指定的使用者，所以先前的輸出指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="7c085-140">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="7c085-141">您可以執行此命令來判斷 SIP 位址是否有效（以及使用者是否已為 Lync Server 啟用指派該 SIP 位址的使用者）：</span><span class="sxs-lookup"><span data-stu-id="7c085-141">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="7c085-142">如果測試 CsIM 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="7c085-142">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="7c085-143">在包含詳細參數的情況下，當您檢查兩個測試使用者要在 IM 會話中參與的每個動作時，測試 CsIM 會傳回它嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="7c085-143">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="7c085-144">例如，以下是當使用者認證（在此例中為不正確的密碼）提供給 Test CsIM 時所發生的樣本輸出：</span><span class="sxs-lookup"><span data-stu-id="7c085-144">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="7c085-145">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="7c085-145">Sending Registration request :</span></span>

<span data-ttu-id="7c085-146">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c085-146">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="7c085-147">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="7c085-147">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="7c085-148">註冊機構埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="7c085-148">Registrar Port = 5061</span></span>

<span data-ttu-id="7c085-149">已選取 Auth 類型 ' IWA」。</span><span class="sxs-lookup"><span data-stu-id="7c085-149">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="7c085-150">針對 sip/atl-cs-001-litwareinc 的註冊。</span><span class="sxs-lookup"><span data-stu-id="7c085-150">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="7c085-151">"Register" 活動在 "0.0601795" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="7c085-151">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="7c085-152">[登錄已遭到拒絕] 例外狀況。</span><span class="sxs-lookup"><span data-stu-id="7c085-152">An exception 'The log on was denied.</span></span> <span data-ttu-id="7c085-153">檢查是否已使用正確的認證，且帳戶處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="7c085-153">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="7c085-154">在工作流程期間發生。</span><span class="sxs-lookup"><span data-stu-id="7c085-154">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="7c085-155">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="7c085-155">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="7c085-156">以下是測試 CsIM 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="7c085-156">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="7c085-157">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="7c085-157">You specified a user account that is not valid.</span></span> <span data-ttu-id="7c085-158">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="7c085-158">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="7c085-159">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="7c085-159">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="7c085-160">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="7c085-160">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="7c085-161">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="7c085-161">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="7c085-162">[立即訊息服務] 可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="7c085-162">The instant messaging service might not be available.</span></span> <span data-ttu-id="7c085-163">使用 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，無法使用 IM。</span><span class="sxs-lookup"><span data-stu-id="7c085-163">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="7c085-164">您可以執行類似下列的命令來驗證：</span><span class="sxs-lookup"><span data-stu-id="7c085-164">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="7c085-165">如果 BlockOnArchiveFailure 設定為 True，則應該判斷封存資料庫是否可用。</span><span class="sxs-lookup"><span data-stu-id="7c085-165">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="7c085-166">您可以使用下列命令，返回封存資料庫的位置：</span><span class="sxs-lookup"><span data-stu-id="7c085-166">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="7c085-167">存檔伺服器可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="7c085-167">The Archiving server might not be available.</span></span> <span data-ttu-id="7c085-168">您可以使用此命令來檢索封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="7c085-168">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="7c085-169">接著，您可以 ping 適當的伺服器，確認它可以使用。</span><span class="sxs-lookup"><span data-stu-id="7c085-169">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="7c085-170">例如：</span><span class="sxs-lookup"><span data-stu-id="7c085-170">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

