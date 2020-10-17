---
title: Lync Server 2013：測試兩個使用者之間的 IM 功能
description: Lync Server 2013：測試兩個使用者之間的 IM 功能。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1409cfb58ed435a66dcf61db56660ca760e16422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560799"
---
# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a><span data-ttu-id="e02d9-103">在 Lync Server 2013 中測試兩個使用者之間的 IM 功能</span><span class="sxs-lookup"><span data-stu-id="e02d9-103">Testing ability to IM between two users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02d9-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="e02d9-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e02d9-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="e02d9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e02d9-106">每日</span><span class="sxs-lookup"><span data-stu-id="e02d9-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02d9-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="e02d9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e02d9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e02d9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02d9-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="e02d9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e02d9-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="e02d9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="e02d9-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e02d9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsIM cmdlet.</span></span> <span data-ttu-id="e02d9-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e02d9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e02d9-113">描述</span><span class="sxs-lookup"><span data-stu-id="e02d9-113">Description</span></span>

<span data-ttu-id="e02d9-114">Test-CsIM Cmdlet 會驗證一對測試使用者是否可以 exchange 立即訊息。</span><span class="sxs-lookup"><span data-stu-id="e02d9-114">The Test-CsIM cmdlet verifies that a pair of test users can exchange instant messages.</span></span> <span data-ttu-id="e02d9-115">呼叫時，Test-CsIM Cmdlet 會從嘗試將一組測試使用者登入 Lync Server 開始。</span><span class="sxs-lookup"><span data-stu-id="e02d9-115">When called, the Test-CsIM cmdlet starts off by trying to log on a pair of test users to Lync Server.</span></span> <span data-ttu-id="e02d9-116">假設兩次登入都成功，則 Cmdlet 會在兩個測試使用者之間啟動 IM 會話。</span><span class="sxs-lookup"><span data-stu-id="e02d9-116">Assuming the two logons are successful, the cmdlet then starts an IM session between the two test users.</span></span> <span data-ttu-id="e02d9-117"> (使用者1邀請使用者2到 IM 會話，而使用者2接受邀請。 ) 之後，請確認郵件可以在兩個使用者之間交換，Test-CsIM 然後結束 IM 會話，並將這兩位使用者從系統登出。</span><span class="sxs-lookup"><span data-stu-id="e02d9-117">(User 1 invites User 2 to an IM session, and User 2 accepts the invitation.) After verifying that messages can be exchanged between the two users, Test-CsIM then ends the IM session and logs both users off the system.</span></span>

<span data-ttu-id="e02d9-118">如需詳細資訊，請參閱 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e02d9-118">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e02d9-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="e02d9-119">Running the Test</span></span>

<span data-ttu-id="e02d9-120">您可以使用一對預先設定的測試帳戶來執行 Test-CsIM Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e02d9-120">The Test-CsIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="e02d9-121">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e02d9-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="e02d9-122">例如：</span><span class="sxs-lookup"><span data-stu-id="e02d9-122">For example:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="e02d9-123">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="e02d9-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="e02d9-124">當您呼叫 Test-CsIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="e02d9-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="e02d9-125">如需詳細資訊，請參閱 [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="e02d9-125">For more information, see the Help documentation for the [Test-CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e02d9-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="e02d9-126">Determining Success or Failure</span></span>

<span data-ttu-id="e02d9-127">如果這兩個使用者可以完成立即訊息會話，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="e02d9-127">If the two users can complete an instant messaging session, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="e02d9-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e02d9-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e02d9-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="e02d9-129">Result : Success</span></span>

<span data-ttu-id="e02d9-130">延遲：00：00：06.6630911</span><span class="sxs-lookup"><span data-stu-id="e02d9-130">Latency : 00:00:06.6630911</span></span>

<span data-ttu-id="e02d9-131">錯誤：</span><span class="sxs-lookup"><span data-stu-id="e02d9-131">Error :</span></span>

<span data-ttu-id="e02d9-132">診斷：</span><span class="sxs-lookup"><span data-stu-id="e02d9-132">Diagnosis :</span></span>

<span data-ttu-id="e02d9-133">如果測試使用者無法完成會話，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="e02d9-133">If the test users can't complete the session, the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="e02d9-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e02d9-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e02d9-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="e02d9-135">Result : Failure</span></span>

<span data-ttu-id="e02d9-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="e02d9-136">Latency : 00:00:00</span></span>

<span data-ttu-id="e02d9-137">錯誤：504，伺服器超時</span><span class="sxs-lookup"><span data-stu-id="e02d9-137">Error : 504, Server time-out</span></span>

<span data-ttu-id="e02d9-138">診斷： ErrorCode = 2，Source = atl-ws-01-cs，Reason = 請參閱</span><span class="sxs-lookup"><span data-stu-id="e02d9-138">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="e02d9-139">回應碼和 reason 片語。</span><span class="sxs-lookup"><span data-stu-id="e02d9-139">response code and reason phrase.</span></span>

<span data-ttu-id="e02d9-140">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="e02d9-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="e02d9-141">例如，由於找不到指定的使用者，所以先前的輸出會指出測試失敗。</span><span class="sxs-lookup"><span data-stu-id="e02d9-141">For example, the previous output states that the test failed because the specified user couldn't be found.</span></span> <span data-ttu-id="e02d9-142">您可以執行下列命令，判斷 SIP 位址是否有效 (，以及指派該 SIP 位址是否已啟用 Lync Server) 的使用者：</span><span class="sxs-lookup"><span data-stu-id="e02d9-142">You can determine whether a SIP address is valid (and whether the user assigned that SIP address was enabled for Lync Server) by running this command:</span></span>

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

<span data-ttu-id="e02d9-143">如果 Test-CsIM 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="e02d9-143">If Test-CsIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="e02d9-144">包含 Verbose 參數時，Test-CsIM 會傳回每個動作所嘗試的每個動作的逐步帳戶，檢查這兩個測試使用者在 IM 會話中所採取的功能。</span><span class="sxs-lookup"><span data-stu-id="e02d9-144">When the Verbose parameter is included, Test-CsIM will return a step-by-step account of each action it tried when it checked the ability of the two test users to take part in an IM session.</span></span> <span data-ttu-id="e02d9-145">例如，在這種情況下，會發生錯誤的使用者 (認證集合時，會發生範例輸出，Test-CsIM 中) 提供錯誤的密碼：</span><span class="sxs-lookup"><span data-stu-id="e02d9-145">For example, here’s sample output that occurs when an incorrect set of user credentials (in this case, an incorrect password) is supplied to Test-CsIM:</span></span>

<span data-ttu-id="e02d9-146">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="e02d9-146">Sending Registration request :</span></span>

<span data-ttu-id="e02d9-147">目標 Fqdn = atl-cs-011.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e02d9-147">Target Fqdn = atl-cs-011.litwareinc.com</span></span>

<span data-ttu-id="e02d9-148">使用者 Sip 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e02d9-148">User Sip Address = sip:kenmyer@litwareinc.com</span></span>

<span data-ttu-id="e02d9-149">註冊機構埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="e02d9-149">Registrar Port = 5061</span></span>

<span data-ttu-id="e02d9-150">已選取驗證類型 ' IWA '。</span><span class="sxs-lookup"><span data-stu-id="e02d9-150">Auth Type 'IWA' is selected.</span></span>

<span data-ttu-id="e02d9-151">對 sip/atl-cs-001-001 的註冊點擊 litwareinc</span><span class="sxs-lookup"><span data-stu-id="e02d9-151">Registration hit against sip/atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e02d9-152">' Register ' activity 在 ' 0.0601795 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="e02d9-152">'Register' activity completed in '0.0601795' secs.</span></span>

<span data-ttu-id="e02d9-153">「登入已遭拒絕」例外狀況。</span><span class="sxs-lookup"><span data-stu-id="e02d9-153">An exception 'The log on was denied.</span></span> <span data-ttu-id="e02d9-154">請檢查是否已使用正確的認證，以及帳戶是否有效。 '</span><span class="sxs-lookup"><span data-stu-id="e02d9-154">Check that the correct credentials are being used and the account is active.'</span></span> <span data-ttu-id="e02d9-155">在工作流程中發生。</span><span class="sxs-lookup"><span data-stu-id="e02d9-155">occurred during the Workflow.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e02d9-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="e02d9-156">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="e02d9-157">以下是一些 Test-CsIM 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="e02d9-157">Here are some common reasons why Test-CsIM might fail:</span></span>

  - <span data-ttu-id="e02d9-158">您指定的使用者帳戶無效。</span><span class="sxs-lookup"><span data-stu-id="e02d9-158">You specified a user account that is not valid.</span></span> <span data-ttu-id="e02d9-159">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="e02d9-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="e02d9-160">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e02d9-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="e02d9-161">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="e02d9-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="e02d9-162">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="e02d9-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="e02d9-163">立即訊息服務可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="e02d9-163">The instant messaging service might not be available.</span></span> <span data-ttu-id="e02d9-164">透過 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，無法使用 IM。</span><span class="sxs-lookup"><span data-stu-id="e02d9-164">With Lync Server, you can configure the system so that IM is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="e02d9-165">您可以執行類似下列的命令來確認：</span><span class="sxs-lookup"><span data-stu-id="e02d9-165">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="e02d9-166">如果 BlockOnArchiveFailure 設定為 True，則應該決定封存資料庫是否可用。</span><span class="sxs-lookup"><span data-stu-id="e02d9-166">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="e02d9-167">您可以使用下列命令回到封存資料庫的位置：</span><span class="sxs-lookup"><span data-stu-id="e02d9-167">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="e02d9-168">可能無法使用封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="e02d9-168">The Archiving server might not be available.</span></span> <span data-ttu-id="e02d9-169">您可以使用下列命令來取得封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="e02d9-169">You can retrieve the FQDN of your Archiving servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="e02d9-170">然後，您可以 ping 適當的伺服器以驗證其是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="e02d9-170">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="e02d9-171">例如：</span><span class="sxs-lookup"><span data-stu-id="e02d9-171">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

