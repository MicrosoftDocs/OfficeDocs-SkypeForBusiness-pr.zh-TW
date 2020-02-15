---
title: Lync Server 2013： 測試 UCWA 會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5daad2d43cf5a7e61dd0e87fac79eb98b9c82e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038105"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="6f6d9-102">Lync Server 2013 中的測試 UCWA 會議</span><span class="sxs-lookup"><span data-stu-id="6f6d9-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f6d9-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="6f6d9-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f6d9-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="6f6d9-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6f6d9-105">每日</span><span class="sxs-lookup"><span data-stu-id="6f6d9-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f6d9-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="6f6d9-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6f6d9-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6f6d9-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f6d9-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="6f6d9-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6f6d9-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6f6d9-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csucwaconference</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="6f6d9-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6f6d9-112">描述</span><span class="sxs-lookup"><span data-stu-id="6f6d9-112">Description</span></span>

<span data-ttu-id="6f6d9-113">**Test-csucwaconference**會確認一組的測試使用者可以排程、 加入，然後進行線上會議使用 Unified Communications Web API (UCWA)。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="6f6d9-114">若要這麼做，指令程式將使用 Lync Server 的 web 票證服務來驗證兩位測試使用者，以及它們登錄與 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="6f6d9-115">接著，Cmdlet 會使用召集人認證來召開會議，然後邀請參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="6f6d9-116">加入會議之後， **test-csucwaconference**會確認使用者可以執行下列項目為交換立即訊息和管理辦法集區]，然後中斷會議及取消註冊的兩個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="6f6d9-117">測試完成時，也會一併刪除排定的會議。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="6f6d9-118">**Test-csucwaconference**也可用來判斷匿名使用者是否可以加入線上會議。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="6f6d9-119">請注意， **test-csucwaconference**應該不針對 Microsoft Lync Server 2010 集區執行，除非 UCWA 已安裝在該集區上。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="6f6d9-120">如果未安裝 UCWA **test-csucwaconference**呼叫將會失敗。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6f6d9-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="6f6d9-121">Running the test</span></span>

<span data-ttu-id="6f6d9-p104">範例 1 所示的命令可確認一對測試使用者能夠參與集區 atl-cs-001.litwareinc.com 上的 UCWA 會議。請注意，如果您未針對 atl-cs-001.litwareinc.com 預先定義一對狀況監控組態的測試使用者，這個命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-p104">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com. Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="6f6d9-124">範例 2 所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 參與 UCWA 會議。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="6f6d9-125">若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="6f6d9-126">(因為登入名稱中，litwareinc\\pilar，包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="6f6d9-127">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="6f6d9-128">使用這兩個認證物件手中，在範例中的第三個命令會決定是否為兩位使用者可以參與 UCWA 會議。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="6f6d9-129">若要執行這項工作， **test-csucwaconference**呼叫時，與下列參數： TargetFqdn (之登錄器集區 FQDN);OrganizerSipAddress （如會議召集人的 SIP 位址）;與 OrganizerCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ParticipantSipAddress （其他測試使用者的 SIP 位址）;和 ParticipantCredential （Windows PowerShell 命令列介面物件，其中包含其他使用者的認證）。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6f6d9-130">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="6f6d9-130">Determining success or failure</span></span>

<span data-ttu-id="6f6d9-131">如果已正確設定會議，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="6f6d9-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6f6d9-132">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6f6d9-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6f6d9-133">目標 Uri: https:// LyncTest-SE.LyncTest.SelfHost.Corp。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="6f6d9-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="6f6d9-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="6f6d9-135">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="6f6d9-135">Result : Success</span></span>

<span data-ttu-id="6f6d9-136">延遲： 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="6f6d9-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="6f6d9-137">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-137">Error Message :</span></span>

<span data-ttu-id="6f6d9-138">診斷：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-138">Diagnosis :</span></span>

<span data-ttu-id="6f6d9-139">如果指定的使用者無法使用會議，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6f6d9-140">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="6f6d9-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="6f6d9-141">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-141">domain name (FQDN).</span></span> <span data-ttu-id="6f6d9-142">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-142">Using default Registrar port number.</span></span> <span data-ttu-id="6f6d9-143">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-143">Exception:</span></span>

<span data-ttu-id="6f6d9-144">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="6f6d9-145">在</span><span class="sxs-lookup"><span data-stu-id="6f6d9-145">at</span></span>

<span data-ttu-id="6f6d9-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="6f6d9-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="6f6d9-147">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="6f6d9-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="6f6d9-148">Test-csucwaconference： 沒有指派的測試使用者</span><span class="sxs-lookup"><span data-stu-id="6f6d9-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="6f6d9-149">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="6f6d9-150">驗證測試使用者設定。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-150">Verify test user configuration.</span></span>

<span data-ttu-id="6f6d9-151">在線條： 1 char: 1</span><span class="sxs-lookup"><span data-stu-id="6f6d9-151">At line:1 char:1</span></span>

<span data-ttu-id="6f6d9-152">\+Test-csucwaconference TargetFqdn 「 LyncTest.SelfHost.Corp.Microsoft.com 」</span><span class="sxs-lookup"><span data-stu-id="6f6d9-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="6f6d9-153">\+CategoryInfo: ResourceUnavailable: （:）\[Test-csucwaconference\]</span><span class="sxs-lookup"><span data-stu-id="6f6d9-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="6f6d9-154">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="6f6d9-154">, InvalidOperationException</span></span>

<span data-ttu-id="6f6d9-155">\+FullyQualifiedErrorId: NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span><span class="sxs-lookup"><span data-stu-id="6f6d9-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="6f6d9-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="6f6d9-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6f6d9-157">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="6f6d9-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="6f6d9-158">以下是一些常見的原因為何**Test-csucwaconference**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="6f6d9-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="6f6d9-159">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="6f6d9-160">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="6f6d9-161">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="6f6d9-162">進行會議的功能取決於已指派給召開會議 （若是**Test-csucwaconference**指令程式，為 「 寄件者 」） 之使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="6f6d9-163">如果召集人不允許包含共同作業活動他/她的會議中 （例如，如果他/她的會議原則有 EnableDataCollaboration 屬性設為 False） 然後**Test-csucwaconference** cmdlet 會失敗。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="6f6d9-164">如果設定錯誤或尚未部署 Edge Server，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="6f6d9-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f6d9-165">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6f6d9-165">See Also</span></span>


[<span data-ttu-id="6f6d9-166">Test-csasconference</span><span class="sxs-lookup"><span data-stu-id="6f6d9-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="6f6d9-167">Test-csdataconference</span><span class="sxs-lookup"><span data-stu-id="6f6d9-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="6f6d9-168">Test-csavconference</span><span class="sxs-lookup"><span data-stu-id="6f6d9-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

