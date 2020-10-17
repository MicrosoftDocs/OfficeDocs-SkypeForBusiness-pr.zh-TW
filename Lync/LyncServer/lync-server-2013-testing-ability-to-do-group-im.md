---
title: Lync Server 2013：測試群組 IM 的能力
description: Lync Server 2013：測試群組 IM 的能力。
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
ms.openlocfilehash: f6988a0c1a7ba569f7b4da098ae741beab5e14fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560809"
---
# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a><span data-ttu-id="0b917-103">在 Lync Server 2013 中測試群組 IM 的能力</span><span class="sxs-lookup"><span data-stu-id="0b917-103">Testing ability to do group IM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b917-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="0b917-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b917-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="0b917-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0b917-106">每日</span><span class="sxs-lookup"><span data-stu-id="0b917-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b917-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="0b917-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0b917-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b917-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b917-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="0b917-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0b917-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0b917-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0b917-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsGroupIM Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0b917-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsGroupIM cmdlet.</span></span> <span data-ttu-id="0b917-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0b917-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0b917-113">描述</span><span class="sxs-lookup"><span data-stu-id="0b917-113">Description</span></span>

<span data-ttu-id="0b917-114">Test-CsGroupIM Cmdlet 會驗證組織中的使用者是否可以進行群組立即訊息會話。</span><span class="sxs-lookup"><span data-stu-id="0b917-114">The Test-CsGroupIM cmdlet verifies that users in your organization can conduct group instant messaging sessions.</span></span> <span data-ttu-id="0b917-115">當您執行 Test-CsGroupIM，指令 Cmdlet 會嘗試將一對測試使用者登入 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="0b917-115">When you run Test-CsGroupIM, the cmdlet attempts to sign in a pair of test users to Lync Server.</span></span> <span data-ttu-id="0b917-116">如果成功，Test-CsGroupIM 會使用第一個測試使用者建立新的會議，然後邀請第二個使用者加入該會議。</span><span class="sxs-lookup"><span data-stu-id="0b917-116">If successful, Test-CsGroupIM creates a new conference using the first test user, then invites the second user to join the conference.</span></span> <span data-ttu-id="0b917-117">交換訊息之後，兩個使用者都會中斷與系統的連線。</span><span class="sxs-lookup"><span data-stu-id="0b917-117">After an exchange of messages, both users are then disconnected from the system.</span></span> <span data-ttu-id="0b917-118">請注意，所有的動作都沒有任何使用者互動，也不會影響任何實際的使用者。</span><span class="sxs-lookup"><span data-stu-id="0b917-118">Note that all of this happens without any user interaction, and without affecting any actual users.</span></span> <span data-ttu-id="0b917-119">例如，假設「測試帳戶 sip:kenmyer@litwareinc.com」會對應至具有實際 Lync 伺服器帳戶的實際使用者。</span><span class="sxs-lookup"><span data-stu-id="0b917-119">For example, suppose that the test account sip:kenmyer@litwareinc.com corresponds to a real user who has a real Lync Server account.</span></span> <span data-ttu-id="0b917-120">在該情況下，測試將會在不干擾實際的 Ken Myer 的情況下進行。</span><span class="sxs-lookup"><span data-stu-id="0b917-120">In that case, the test will be conducted without any disruption to the real Ken Myer.</span></span> <span data-ttu-id="0b917-121">例如，即使在 Ken Myer 測試帳戶從系統登出時，Ken Myer 這個人仍然維持登入狀態。</span><span class="sxs-lookup"><span data-stu-id="0b917-121">For example, even when the Ken Myer test account logs off from the system, Ken Myer the person will remain logged on.</span></span> <span data-ttu-id="0b917-122">同樣地，real Ken Myer 不會收到加入會議的邀請。</span><span class="sxs-lookup"><span data-stu-id="0b917-122">Likewise, the real Ken Myer won't receive an invitation to join the conference.</span></span> <span data-ttu-id="0b917-123">該邀請將會傳送到測試帳戶，並由測試帳戶接受。</span><span class="sxs-lookup"><span data-stu-id="0b917-123">That invitation will be sent to, and accepted by, the test account.</span></span>

<span data-ttu-id="0b917-124">如需詳細資訊，請參閱 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="0b917-124">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0b917-125">執行測試</span><span class="sxs-lookup"><span data-stu-id="0b917-125">Running the test</span></span>

<span data-ttu-id="0b917-126">您可以使用一對預先設定的測試帳戶來執行 Test-CsGroupIM Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0b917-126">The Test-CsGroupIM cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="0b917-127">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="0b917-127">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="0b917-128">例如：</span><span class="sxs-lookup"><span data-stu-id="0b917-128">For example:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="0b917-129">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Lync Server 管理命令介面認證物件 (包含每個帳戶的帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="0b917-129">To run this check using actual user accounts, you must create two Lync Server Management Shell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="0b917-130">當您呼叫 Test-CsGroupIM 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="0b917-130">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsGroupIM:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

<span data-ttu-id="0b917-131">如需詳細資訊，請參閱 [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="0b917-131">For more information, see the Help documentation for the [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0b917-132">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="0b917-132">Determining Success or Failure</span></span>

<span data-ttu-id="0b917-133">如果兩位使用者可以完成群組立即訊息會話，則會收到與結果屬性標示為 [成功] 的輸出 **：**</span><span class="sxs-lookup"><span data-stu-id="0b917-133">If the two users can complete a group instant messaging session, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0b917-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b917-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b917-135">結果：成功</span><span class="sxs-lookup"><span data-stu-id="0b917-135">Result : Success</span></span>

<span data-ttu-id="0b917-136">延遲：00：00：06.3812203</span><span class="sxs-lookup"><span data-stu-id="0b917-136">Latency : 00:00:06.3812203</span></span>

<span data-ttu-id="0b917-137">錯誤：</span><span class="sxs-lookup"><span data-stu-id="0b917-137">Error :</span></span>

<span data-ttu-id="0b917-138">診斷：</span><span class="sxs-lookup"><span data-stu-id="0b917-138">Diagnosis :</span></span>

<span data-ttu-id="0b917-139">如果兩位使用者無法完成立即訊息會話，則結果會顯示為失敗，而且會在錯誤和診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="0b917-139">If the two users can't able to complete the instant messaging session, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0b917-140">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b917-140">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0b917-141">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="0b917-141">Result : Failure</span></span>

<span data-ttu-id="0b917-142">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="0b917-142">Latency : 00:00:00</span></span>

<span data-ttu-id="0b917-143">錯誤：404，未找到</span><span class="sxs-lookup"><span data-stu-id="0b917-143">Error : 404, Not Found</span></span>

<span data-ttu-id="0b917-144">診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="0b917-144">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="0b917-145">原因 = 未啟用 SIP 的目的 URI 或不是</span><span class="sxs-lookup"><span data-stu-id="0b917-145">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="0b917-146">存在。</span><span class="sxs-lookup"><span data-stu-id="0b917-146">exist.</span></span>

<span data-ttu-id="0b917-147">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="0b917-147">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="0b917-148">先前的輸出指出測試失敗的原因是至少一個測試帳戶無效，原因是該帳戶不存在，或是尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="0b917-148">The previous output states that the test failed because at least one of the test accounts was not valid, either because the account does not exist or because the user has not been enabled for Lync Server.</span></span> <span data-ttu-id="0b917-149">您可以透過執行類似如下的命令，確認帳戶是否存在，以及帳戶是否已啟用的帳戶已啟用。</span><span class="sxs-lookup"><span data-stu-id="0b917-149">You can verify the account exists, and whether or not the account has been enabled for nm-ocs-14-3rd by running a command similar to this:</span></span>

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="0b917-150">如果 Test-CsGroupIM 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="0b917-150">If Test-CsGroupIM fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="0b917-151">包含 Verbose 參數時，Test-CsGroupIM 會傳回每個動作所嘗試的每個動作的逐步帳戶，檢查指定使用者是否可以加入群組立即訊息會話。</span><span class="sxs-lookup"><span data-stu-id="0b917-151">When the Verbose parameter is included, Test-CsGroupIM will return a step-by-step account of each action it tried when it checked the ability of the specified users to participate in a group instant messaging sessions.</span></span> <span data-ttu-id="0b917-152">例如，如果測試失敗，而且您已告知一或多個使用者帳戶無效，您可以使用 Verbose 參數來重新執行測試，並判斷哪個使用者帳戶無效：</span><span class="sxs-lookup"><span data-stu-id="0b917-152">For example, if your test fails and you are told that one or more of the user accounts is not valid, you can rerun the test using the Verbose parameter and determine which user account is not valid:</span></span>

<span data-ttu-id="0b917-153">傳送註冊要求：</span><span class="sxs-lookup"><span data-stu-id="0b917-153">Sending Registration request:</span></span>

 <span data-ttu-id="0b917-154">目標 Fqdn = atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b917-154">Target Fqdn      = atl-cs-001.litwareinc.com</span></span>

 <span data-ttu-id="0b917-155">使用者 SIP 位址 = sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0b917-155">User SIP Address = sip:kenmyer@litwareinc.com</span></span>

 <span data-ttu-id="0b917-156">寄存器埠 = 5061</span><span class="sxs-lookup"><span data-stu-id="0b917-156">Register Port    = 5061</span></span>

<span data-ttu-id="0b917-157">已選取驗證類型 ' IWA '。</span><span class="sxs-lookup"><span data-stu-id="0b917-157">Auth type 'IWA' is selected.</span></span>

<span data-ttu-id="0b917-158">「登入已遭拒絕」例外狀況。</span><span class="sxs-lookup"><span data-stu-id="0b917-158">An exception 'The log on was denied.</span></span> <span data-ttu-id="0b917-159">請檢查是否已使用正確的認證，且帳戶為使用中。</span><span class="sxs-lookup"><span data-stu-id="0b917-159">Check that the correct credentials are being used and the account is active'</span></span>

<span data-ttu-id="0b917-160">如您所見，在此範例中，具有 SIP 位址 sip:kenmyer@litwareinc.com 的使用者無法登入。</span><span class="sxs-lookup"><span data-stu-id="0b917-160">As you can see, in this example the user who has the SIP address sip:kenmyer@litwareinc.com was not able to log on.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0b917-161">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="0b917-161">Reasons why the test might have failed</span></span>

<span data-ttu-id="0b917-162">以下是一些 Test-CsGroupIM 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="0b917-162">Here are some common reasons why Test-CsGroupIM might fail:</span></span>

  - <span data-ttu-id="0b917-163">您指定了錯誤的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="0b917-163">You specified an incorrect user account.</span></span> <span data-ttu-id="0b917-164">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="0b917-164">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="0b917-165">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0b917-165">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="0b917-166">若要確認已啟用 Lync Server 的使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="0b917-166">To verify that a user account was enabled for Lync Server, run a command similar to the following:</span></span>
    
    <span data-ttu-id="0b917-167">Get-CsUser "sip:kenmyer@litwareinc.com" |Select-Object 啟用</span><span class="sxs-lookup"><span data-stu-id="0b917-167">Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled</span></span>
    
    <span data-ttu-id="0b917-168">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="0b917-168">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="0b917-169">立即訊息服務可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="0b917-169">The instant messaging service might not be available.</span></span> <span data-ttu-id="0b917-170">透過 Lync Server，您可以設定系統，以便在無法存取封存資料庫時，立即訊息無法使用。</span><span class="sxs-lookup"><span data-stu-id="0b917-170">With Lync Server, you can configure the system so that instant messaging is not available if the archiving database cannot be accessed.</span></span> <span data-ttu-id="0b917-171">您可以執行類似下列的命令來確認：</span><span class="sxs-lookup"><span data-stu-id="0b917-171">You can verify that by running a command similar to the following:</span></span>
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    <span data-ttu-id="0b917-172">如果 BlockOnArchiveFailure 設定為 True，則應該決定封存資料庫是否可用。</span><span class="sxs-lookup"><span data-stu-id="0b917-172">If BlockOnArchiveFailure is set to True, then you should determine whether or not the archiving database is available.</span></span> <span data-ttu-id="0b917-173">您可以使用下列命令回到封存資料庫的位置：</span><span class="sxs-lookup"><span data-stu-id="0b917-173">You can return the locations of your archiving databases by using the following command:</span></span>
    
        Get-CsService -ArchivingDatabase

  - <span data-ttu-id="0b917-174">可能無法使用封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="0b917-174">The Archiving Server might not be available.</span></span> <span data-ttu-id="0b917-175">您可以使用下列命令來取得封存伺服器的 FQDN：</span><span class="sxs-lookup"><span data-stu-id="0b917-175">You can retrieve the FQDN of your Archiving Servers by using this command:</span></span>
    
        Get-CsService -ArchivingServer
    
    <span data-ttu-id="0b917-176">然後，您可以 ping 適當的伺服器以驗證其是否可供使用。</span><span class="sxs-lookup"><span data-stu-id="0b917-176">You can then ping the appropriate server to verify that it is available.</span></span> <span data-ttu-id="0b917-177">例如：</span><span class="sxs-lookup"><span data-stu-id="0b917-177">For example:</span></span>
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

