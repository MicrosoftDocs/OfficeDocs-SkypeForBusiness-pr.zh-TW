---
title: Lync Server 2013：測試持續性聊天
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
ms.openlocfilehash: 7c1980d66649ff465ad251d5b95a9642e5bcd43c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504070"
---
# <a name="testing-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="fb9d6-102">在 Lync Server 2013 中測試持續性聊天</span><span class="sxs-lookup"><span data-stu-id="fb9d6-102">Testing persistent chat in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb9d6-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="fb9d6-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb9d6-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="fb9d6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fb9d6-105">每日</span><span class="sxs-lookup"><span data-stu-id="fb9d6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb9d6-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="fb9d6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fb9d6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fb9d6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb9d6-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="fb9d6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fb9d6-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fb9d6-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsPersistentChatMessage</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsPersistentChatMessage</strong> cmdlet.</span></span> <span data-ttu-id="fb9d6-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fb9d6-112">描述</span><span class="sxs-lookup"><span data-stu-id="fb9d6-112">Description</span></span>

<span data-ttu-id="fb9d6-113">**Test-CsPersistentChatMessage** Cmdlet 會驗證一對測試使用者是否可以使用 Persistent Chat service 來交換郵件。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-113">The **Test-CsPersistentChatMessage** cmdlet verifies that a pair of test users can exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="fb9d6-114">為做到這一點，指令指令會將兩位使用者記錄到 Lync Server 2013，將使用者連線到 persistent 聊天室，交換一對郵件，然後結束聊天室，並登出兩位使用者。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-114">To do this, the cmdlet logs the two users on to Lync Server 2013, connects the users to a persistent Chat room, exchanges a pair of messages, then exits the chat room and logs off the two users.</span></span> <span data-ttu-id="fb9d6-115">請注意，如果您未建立任何聊天室或沒有為這兩個測試使用者帳戶指派可存取 Persistent Chat service 的持續性聊天原則，則呼叫此 Cmdlet 將會失敗。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-115">Note that calls to this cmdlet will fail if you have not created any chat rooms or if the two test user accounts are not assigned a Persistent Chat policy that gives them access to the Persistent Chat service.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fb9d6-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="fb9d6-116">Running the test</span></span>

<span data-ttu-id="fb9d6-117">下列範例所示的命令會測試一組使用者 (litwareinc \\ pilar and litwareinc \\ kenmyer) 登入 Lync Server 2013，然後使用 Persistent Chat service 進行 exchange 郵件的功能。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-117">The commands shown in the following example test the ability of a pair of users (litwareinc\\pilar and litwareinc\\kenmyer) to log on to Lync Server 2013 and then exchange messages using the Persistent Chat service.</span></span> <span data-ttu-id="fb9d6-118">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Pilar Ackerman 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-118">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="fb9d6-119"> (由於登入名稱 litwareinc \\ pilar 已包含為參數，所以 [Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 產生的認證物件會儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-119">(Because the logon name, litwareinc\\pilar, was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credentials object is then stored in a variable named $cred1.</span></span> <span data-ttu-id="fb9d6-120">第二個命令會執行相同的程序，但這次會傳回 Ken Myer 帳戶的認證物件。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-120">The second command does the same thing, this time returning a credential object for the Ken Myer account.</span></span>

<span data-ttu-id="fb9d6-121">使用 credential 物件，第三個命令會判斷是否這兩位使用者可以使用持續聊天登入 Lync Server 2013 和 exchange 郵件。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-121">With the credential objects in hand, the third command determines whether these two users can log on to Lync Server 2013 and exchange messages using Persistent Chat.</span></span> <span data-ttu-id="fb9d6-122">若要執行這項工作， **Test-CsPersistentChatMessage** Cmdlet 會使用下列參數呼叫： TargetFqdn (註冊機構集區的 FQDN) ;SenderSipAddress (第一個測試使用者的 SIP 位址) ;SenderCredential (包含此相同使用者之認證的 Windows PowerShell 物件) ;ReceiverSipAddress (其他測試使用者) 的 SIP 位址;和 ReceiverCredential (包含其他測試使用者) 之認證的 Windows PowerShell 物件。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-122">To perform this task, the **Test-CsPersistentChatMessage** cmdlet is called using the following parameters: TargetFqdn (the FQDN of the Registrar pool); SenderSipAddress (the SIP address for the first test user); SenderCredential (the Windows PowerShell object that contains the credentials for this same user); ReceiverSipAddress (the SIP address for the other test user); and ReceiverCredential (the Windows PowerShell object that contains the credentials for the other test user).</span></span>

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fb9d6-123">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="fb9d6-123">Determining success or failure</span></span>

<span data-ttu-id="fb9d6-124">如果指定的使用者有有效的位置原則，則會收到類似下列的輸出，並將 Result 屬性標示為 [ **成功**]：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-124">If the specified user has a valid location policy, then you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="fb9d6-125">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb9d6-125">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb9d6-126">結果：成功</span><span class="sxs-lookup"><span data-stu-id="fb9d6-126">Result : Success</span></span>

<span data-ttu-id="fb9d6-127">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="fb9d6-127">Latency : 00:00:00</span></span>

<span data-ttu-id="fb9d6-128">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-128">Error Message :</span></span>

<span data-ttu-id="fb9d6-129">診斷：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-129">Diagnosis :</span></span>

<span data-ttu-id="fb9d6-130">如果指定的使用者無法使用 Persistent Chat service 來交換郵件，則結果會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-130">If the specified users can't exchange messages using the Persistent Chat service, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="fb9d6-131">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="fb9d6-131">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="fb9d6-132">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-132">domain name (FQDN).</span></span> <span data-ttu-id="fb9d6-133">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-133">Using default Registrar port number.</span></span> <span data-ttu-id="fb9d6-134">例外：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-134">Exception:</span></span>

<span data-ttu-id="fb9d6-135">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-135">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="fb9d6-136">在</span><span class="sxs-lookup"><span data-stu-id="fb9d6-136">at</span></span>

<span data-ttu-id="fb9d6-137">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="fb9d6-137">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="fb9d6-138">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="fb9d6-138">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="fb9d6-139">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="fb9d6-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="fb9d6-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="fb9d6-140">Result : Failure</span></span>

<span data-ttu-id="fb9d6-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="fb9d6-141">Latency : 00:00:00</span></span>

<span data-ttu-id="fb9d6-142">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="fb9d6-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="fb9d6-143">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="fb9d6-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="fb9d6-144">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="fb9d6-144">established connection failed because connected host has</span></span>

<span data-ttu-id="fb9d6-145">無法回應 \[ 2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="fb9d6-145">failed to respond \[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="fb9d6-146">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="fb9d6-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="fb9d6-147">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="fb9d6-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="fb9d6-148">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="fb9d6-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="fb9d6-149">回應失敗</span><span class="sxs-lookup"><span data-stu-id="fb9d6-149">has failed to respond</span></span>

<span data-ttu-id="fb9d6-150">\[2001：4898： e8： f39e：5c9a： ad83：81b3： 9944 \] ：5061</span><span class="sxs-lookup"><span data-stu-id="fb9d6-150">\[2001:4898:e8:f39e:5c9a:ad83:81b3:9944\]:5061</span></span>

<span data-ttu-id="fb9d6-151">診斷：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fb9d6-152">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="fb9d6-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="fb9d6-153">以下是一些 **Test-CsPersistentChatMessage** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="fb9d6-153">Here are some common reasons why **Test-CsPersistentChatMessage** might fail:</span></span>

  - <span data-ttu-id="fb9d6-154">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="fb9d6-155">必要的測試帳戶可能不存在，或已正確建立。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-155">The required test accounts may not exist or have been correctly created.</span></span>

  - <span data-ttu-id="fb9d6-156">可能發生網路問題，造成測試超時，造成未預期的延遲。</span><span class="sxs-lookup"><span data-stu-id="fb9d6-156">There may have been a network issue causing an unexpected delay which timed out the test.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fb9d6-157">另請參閱</span><span class="sxs-lookup"><span data-stu-id="fb9d6-157">See Also</span></span>


[<span data-ttu-id="fb9d6-158">Grant-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="fb9d6-158">Grant-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[<span data-ttu-id="fb9d6-159">New-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="fb9d6-159">New-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[<span data-ttu-id="fb9d6-160">Set-CsPersistentChatPolicy</span><span class="sxs-lookup"><span data-stu-id="fb9d6-160">Set-CsPersistentChatPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

