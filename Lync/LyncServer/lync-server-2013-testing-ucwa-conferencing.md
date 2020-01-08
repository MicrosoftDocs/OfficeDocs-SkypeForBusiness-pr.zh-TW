---
title: Lync Server 2013：測試 UCWA 會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b05b67f6f235cdcf3153149c9bd2373c30815d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a><span data-ttu-id="0f0a2-102">在 Lync Server 2013 中測試 UCWA 會議</span><span class="sxs-lookup"><span data-stu-id="0f0a2-102">Testing UCWA conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f0a2-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="0f0a2-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f0a2-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="0f0a2-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0f0a2-105">日常</span><span class="sxs-lookup"><span data-stu-id="0f0a2-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f0a2-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="0f0a2-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0f0a2-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f0a2-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f0a2-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="0f0a2-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0f0a2-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0f0a2-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsUcwaConference</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUcwaConference</strong> cmdlet.</span></span> <span data-ttu-id="0f0a2-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="0f0a2-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0f0a2-112">描述</span><span class="sxs-lookup"><span data-stu-id="0f0a2-112">Description</span></span>

<span data-ttu-id="0f0a2-113">**CsUcwaConference** Cmdlet 會確認一組測試使用者可以使用整合通訊 Web API （UCWA）排程、加入並進行線上會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-113">The **Test-CsUcwaConference** cmdlet verifies that a pair of test users can schedule, join, and then conduct an online conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="0f0a2-114">若要這樣做，此 Cmdlet 會使用 Lync Server web ticket 服務來驗證這兩個測試使用者，然後使用 Lync Server 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-114">To do this, the cmdlet uses the Lync Server web ticket service to authenticate the two test users and register them with Lync Server.</span></span> <span data-ttu-id="0f0a2-115">然後，該 Cmdlet 會使用召集人認證開始會議，並邀請參與者加入會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-115">The cmdlet then starts a conference using the organizer credentials and invites the participant to join the meeting.</span></span> <span data-ttu-id="0f0a2-116">加入會議之後，**測試 CsUcwaConference** Cmdlet 會驗證使用者是否可以執行 exchange 立即訊息和執行池等動作，然後中斷會議連線並登出兩個測試使用者。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-116">After the meeting is joined, the **Test-CsUcwaConference** cmdlet verifies that the users can do such things as exchange instant message and conduct pools, then disconnects the conference and unregisters the two test users.</span></span> <span data-ttu-id="0f0a2-117">當測試完成時，也會刪除排程的會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-117">The scheduled conference will also be deleted when the test is finished.</span></span>

<span data-ttu-id="0f0a2-118">**CsUcwaConference** Cmdlet 也可以用來判斷匿名使用者是否可以加入線上會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-118">The **Test-CsUcwaConference** cmdlet can also be used to determine whether anonymous users can join online conferences.</span></span>

<span data-ttu-id="0f0a2-119">請注意，除非已在該池中安裝 UCWA，否則不應針對 Microsoft Lync Server 2010 pool 執行**Test CsUcwaConference** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-119">Note that the **Test-CsUcwaConference** cmdlet should not be run against a Microsoft Lync Server 2010 pool unless UCWA was installed on that pool.</span></span> <span data-ttu-id="0f0a2-120">如果尚未安裝 UCWA，則**CsUcwaConference** Cmdlet 的呼叫將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-120">If UCWA has not been installed then the call to the **Test-CsUcwaConference** cmdlet will fail.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0f0a2-121">執行測試</span><span class="sxs-lookup"><span data-stu-id="0f0a2-121">Running the test</span></span>

<span data-ttu-id="0f0a2-122">範例1中所示的命令會確認一組測試使用者可以參與 UCWA 會議的 [pool atl-cs-001.litwareinc.com]。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-122">The command shown in Example 1 verifies that a pair of test users can participate in an UCWA conference on the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="0f0a2-123">請注意，如果您未預先定義一對 atl-cs-001.litwareinc.com 的健康情況監視設定測試使用者，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-123">Note that this command will fail if you have not predefined a pair of health monitoring configuration test users for atl-cs-001.litwareinc.com.</span></span>

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="0f0a2-124">範例2所示的命令會測試一對使用者（litwareinc\\pilar 和 litwareinc\\kenmyer）的功能，以參與 UCWA 會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-124">The commands shown in Example 2 test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to participate in an UCWA conference.</span></span> <span data-ttu-id="0f0a2-125">若要這樣做，範例中的第一個命令會使用取得認證 Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，該物件包含使用者 Pilar 方的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="0f0a2-126">（因為登入名稱（litwareinc\\pilar）是以參數的形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-126">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="0f0a2-127">第二個命令會執行相同的動作，這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-127">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="0f0a2-128">使用這兩個認證物件時，範例中的第三個命令會判斷兩個使用者是否可以參與 UCWA 會議。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-128">With the two credential objects in hand, the third command in the example determines whether the two users can participate in an UCWA conference.</span></span> <span data-ttu-id="0f0a2-129">若要執行這項工作，請使用下列參數來呼叫**CsUcwaConference** Cmdlet： TargetFqdn （註冊機構池的 FQDN）;OrganizerSipAddress （會議召集人的 SIP 位址）;OrganizerCredential （包含此相同使用者認證的 Windows PowerShell 物件）;ParticipantSipAddress （其他測試使用者的 SIP 位址）;與 ParticipantCredential （包含其他使用者認證的 Windows PowerShell 命令列介面物件）。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-129">To run this task, the **Test-CsUcwaConference** cmdlet is called, together with the following parameters: TargetFqdn (the FQDN of the Registrar pool); OrganizerSipAddress (the SIP address for the meeting organizer); OrganizerCredential (the Windows PowerShell object that contains the credentials for this same user); ParticipantSipAddress (the SIP address for the other test user); and ParticipantCredential (the Windows PowerShell command-line interface object that contains the credentials for the other user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0f0a2-130">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="0f0a2-130">Determining success or failure</span></span>

<span data-ttu-id="0f0a2-131">如果會議設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="0f0a2-131">If conferencing is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="0f0a2-132">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0f0a2-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0f0a2-133">目標 Uri： HTTPs://LyncTest-LyncTest. SelfHost。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-133">Target Uri : https:// LyncTest-SE.LyncTest.SelfHost.Corp.</span></span>

<span data-ttu-id="0f0a2-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span><span class="sxs-lookup"><span data-stu-id="0f0a2-134">Microsoft.com:443/CertProv/CertProvisiongService.svc</span></span>

<span data-ttu-id="0f0a2-135">結果：成功</span><span class="sxs-lookup"><span data-stu-id="0f0a2-135">Result : Success</span></span>

<span data-ttu-id="0f0a2-136">延隔時間：00：00：14.9862716</span><span class="sxs-lookup"><span data-stu-id="0f0a2-136">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="0f0a2-137">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="0f0a2-137">Error Message :</span></span>

<span data-ttu-id="0f0a2-138">自檢</span><span class="sxs-lookup"><span data-stu-id="0f0a2-138">Diagnosis :</span></span>

<span data-ttu-id="0f0a2-139">如果指定的使用者無法使用會議，則會將結果顯示為**失敗**，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="0f0a2-139">If the specified users can't use conferencing, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="0f0a2-140">警告：無法讀取指定之完全限定的註冊機構埠號碼</span><span class="sxs-lookup"><span data-stu-id="0f0a2-140">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="0f0a2-141">網功能變數名稱稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-141">domain name (FQDN).</span></span> <span data-ttu-id="0f0a2-142">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-142">Using default Registrar port number.</span></span> <span data-ttu-id="0f0a2-143">引發</span><span class="sxs-lookup"><span data-stu-id="0f0a2-143">Exception:</span></span>

<span data-ttu-id="0f0a2-144">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-144">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="0f0a2-145">的</span><span class="sxs-lookup"><span data-stu-id="0f0a2-145">at</span></span>

<span data-ttu-id="0f0a2-146">TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction</span><span class="sxs-lookup"><span data-stu-id="0f0a2-146">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="0f0a2-147">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="0f0a2-147">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="0f0a2-148">Test-CsUcwaConference：沒有指派測試使用者</span><span class="sxs-lookup"><span data-stu-id="0f0a2-148">Test-CsUcwaConference : There is no test user assigned for</span></span>

<span data-ttu-id="0f0a2-149">\[LyncTest.SelfHost.Corp.Microsoft.com\]。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-149">\[LyncTest.SelfHost.Corp.Microsoft.com\].</span></span> <span data-ttu-id="0f0a2-150">驗證測試使用者配置。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-150">Verify test user configuration.</span></span>

<span data-ttu-id="0f0a2-151">在第一行：1個字元：1</span><span class="sxs-lookup"><span data-stu-id="0f0a2-151">At line:1 char:1</span></span>

<span data-ttu-id="0f0a2-152">\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span><span class="sxs-lookup"><span data-stu-id="0f0a2-152">\+ Test-CsUcwaConference -TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"</span></span>

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

<span data-ttu-id="0f0a2-153">\+CategoryInfo： ResourceUnavailable：（:)\[Test-CsUcwaConference\]</span><span class="sxs-lookup"><span data-stu-id="0f0a2-153">\+ CategoryInfo : ResourceUnavailable: (:) \[Test-CsUcwaConference\]</span></span>

<span data-ttu-id="0f0a2-154">, InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="0f0a2-154">, InvalidOperationException</span></span>

<span data-ttu-id="0f0a2-155">\+FullyQualifiedErrorId： NotFoundTestUsers，，</span><span class="sxs-lookup"><span data-stu-id="0f0a2-155">\+ FullyQualifiedErrorId : NotFoundTestUsers,Microsoft.Rtc.Management.Synth</span></span>

<span data-ttu-id="0f0a2-156">eticTransactions.TestUcwaConferenceCmdlet</span><span class="sxs-lookup"><span data-stu-id="0f0a2-156">eticTransactions.TestUcwaConferenceCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0f0a2-157">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="0f0a2-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="0f0a2-158">以下是**測試 CsUcwaConference**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="0f0a2-158">Here are some common reasons why **Test-CsUcwaConference** might fail:</span></span>

  - <span data-ttu-id="0f0a2-159">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="0f0a2-160">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="0f0a2-161">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="0f0a2-162">執行會議的功能，取決於已指派給組織會議之使用者的會議原則（在**CsUcwaConference** Cmdlet 中為「寄件者」）。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-162">The ability to conduct a conference depends on the conferencing policy that has been assigned to the user who organized the conference (in the case of the **Test-CsUcwaConference** cmdlet, that is the "sender").</span></span> <span data-ttu-id="0f0a2-163">如果召集人不能在會議中加入共同作業（例如，如果他/她的會議原則將 EnableDataCollaboration 屬性設為 False），則**CsUcwaConference** Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-163">If the organizer is not allowed to include collaborative activities in his or her meeting (for example, if his or her conferencing policy has the EnableDataCollaboration property set to False) then the **Test-CsUcwaConference** cmdlet will fail.</span></span>

  - <span data-ttu-id="0f0a2-164">如果 Edge 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f0a2-164">This command will fail if the Edge Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0f0a2-165">請參閱</span><span class="sxs-lookup"><span data-stu-id="0f0a2-165">See Also</span></span>


[<span data-ttu-id="0f0a2-166">Test-CsASConference</span><span class="sxs-lookup"><span data-stu-id="0f0a2-166">Test-CsASConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[<span data-ttu-id="0f0a2-167">Test-CsDataConference</span><span class="sxs-lookup"><span data-stu-id="0f0a2-167">Test-CsDataConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[<span data-ttu-id="0f0a2-168">Test-CsAVConference</span><span class="sxs-lookup"><span data-stu-id="0f0a2-168">Test-CsAVConference</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

