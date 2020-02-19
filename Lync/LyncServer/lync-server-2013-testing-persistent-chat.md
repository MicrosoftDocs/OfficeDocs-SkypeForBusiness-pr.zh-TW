---
title: Lync Server 2013： 測試常設聊天室
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941f8830689c95fb782ac56594cd1d62785c1e1f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="d67c5-102">在 Lync Server 2013 中進行測試常設聊天室</span><span class="sxs-lookup"><span data-stu-id="d67c5-102">Testing persistent chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d67c5-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="d67c5-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d67c5-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="d67c5-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d67c5-105">每日</span><span class="sxs-lookup"><span data-stu-id="d67c5-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d67c5-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="d67c5-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d67c5-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d67c5-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d67c5-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="d67c5-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d67c5-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d67c5-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="d67c5-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-cspersistentchatmessage</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d67c5-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="d67c5-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="d67c5-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d67c5-112">描述</span><span class="sxs-lookup"><span data-stu-id="d67c5-112">Description</span></span>

<span data-ttu-id="d67c5-113">**Test-cspersistentchatmessage** cmdlet 會驗證測試使用者的一組可以交換郵件使用的常設聊天室服務。</span><span class="sxs-lookup"><span data-stu-id="d67c5-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="d67c5-114">若要這麼做，指令程式登入 Lync Server 2013 的兩個使用者、 使用者連到常設聊天室、 交換郵件的一組，然後結束聊天室並登出兩位使用者。</span><span class="sxs-lookup"><span data-stu-id="d67c5-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="d67c5-115">如果您沒有建立任何聊天室，或是如果兩個測試使用者帳戶未被指派的常設聊天室原則，可讓其存取常設聊天室服務，請注意，此 cmdlet 會呼叫將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d67c5-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d67c5-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="d67c5-116">Running the test</span></span>

<span data-ttu-id="d67c5-117">下列範例所示的命令會測試的一組使用者的能力 (litwareinc\\pilar 和 litwareinc\\kenmyer) 登入 Lync Server 2013，然後 exchange 郵件使用的常設聊天室服務。</span><span class="sxs-lookup"><span data-stu-id="d67c5-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="d67c5-118">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。</span><span class="sxs-lookup"><span data-stu-id="d67c5-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="d67c5-119">(因為登入名稱中，litwareinc\\pilar，包含做為參數，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="d67c5-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="d67c5-120">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="d67c5-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="d67c5-121">在手中的認證物件，第三個命令會決定這些兩個使用者是否可以登入 Lync Server 2013 和 exchange 使用常設聊天室的郵件。</span><span class="sxs-lookup"><span data-stu-id="d67c5-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="d67c5-122">若要執行這項工作， **Test-cspersistentchatmessage** cmdlet 會呼叫使用下列參數： TargetFqdn (之登錄器集區 FQDN);SenderSipAddress （第一個測試使用者的 SIP 位址）;與 SenderCredential （包含這個相同的使用者認證的 Windows PowerShell 物件）;ReceiverSipAddress （其他測試使用者的 SIP 位址）;並與 ReceiverCredential （包含在其他的測試使用者的認證的 Windows PowerShell 物件）。</span><span class="sxs-lookup"><span data-stu-id="d67c5-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d67c5-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="d67c5-123">Determining success or failure</span></span>

<span data-ttu-id="d67c5-124">如果指定的使用者具有有效的位置原則，您會收到類似，具有標示為 [**成功**結果屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="d67c5-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="d67c5-125">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d67c5-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d67c5-126">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="d67c5-126">Result : Success</span></span>

<span data-ttu-id="d67c5-127">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d67c5-127">Latency : 00:00:00</span></span>

<span data-ttu-id="d67c5-128">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="d67c5-128">Error Message :</span></span>

<span data-ttu-id="d67c5-129">診斷：</span><span class="sxs-lookup"><span data-stu-id="d67c5-129">Diagnosis :</span></span>

<span data-ttu-id="d67c5-130">如果指定的使用者不能交換使用的常設聊天室服務的訊息，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="d67c5-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="d67c5-131">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="d67c5-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="d67c5-132">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="d67c5-132">domain name (FQDN).</span></span> <span data-ttu-id="d67c5-133">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d67c5-133">Using default Registrar port number.</span></span> <span data-ttu-id="d67c5-134">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="d67c5-134">Exception:</span></span>

<span data-ttu-id="d67c5-135">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="d67c5-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="d67c5-136">在</span><span class="sxs-lookup"><span data-stu-id="d67c5-136">at</span></span>

<span data-ttu-id="d67c5-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="d67c5-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="d67c5-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="d67c5-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="d67c5-139">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d67c5-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d67c5-140">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="d67c5-140">Result : Failure</span></span>

<span data-ttu-id="d67c5-141">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="d67c5-141">Latency : 00:00:00</span></span>

<span data-ttu-id="d67c5-142">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="d67c5-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="d67c5-143">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="d67c5-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="d67c5-144">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="d67c5-144">established connection failed because connected host has</span></span>

<span data-ttu-id="d67c5-145">失敗回應\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="d67c5-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="d67c5-146">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="d67c5-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="d67c5-147">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="d67c5-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="d67c5-148">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="d67c5-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="d67c5-149">失敗回應</span><span class="sxs-lookup"><span data-stu-id="d67c5-149">has failed to respond</span></span>

<span data-ttu-id="d67c5-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]: 5061</span><span class="sxs-lookup"><span data-stu-id="d67c5-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="d67c5-151">診斷：</span><span class="sxs-lookup"><span data-stu-id="d67c5-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d67c5-152">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="d67c5-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="d67c5-153">以下是一些常見的原因為何**Test-cspersistentchatmessage**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="d67c5-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="d67c5-154">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="d67c5-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d67c5-155">需要的測試帳戶可能不存在或已正確建立。</span><span class="sxs-lookup"><span data-stu-id="d67c5-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="d67c5-156">可能有網路問題造成未預期的延遲的逾時測試。</span><span class="sxs-lookup"><span data-stu-id="d67c5-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d67c5-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d67c5-157">See Also</span></span>


[<span data-ttu-id="d67c5-158">授與 CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="d67c5-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="d67c5-159">New-cspersistentchatpolicy</span><span class="sxs-lookup"><span data-stu-id="d67c5-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="d67c5-160">Set-cspersistentchatpolicy</span><span class="sxs-lookup"><span data-stu-id="d67c5-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

