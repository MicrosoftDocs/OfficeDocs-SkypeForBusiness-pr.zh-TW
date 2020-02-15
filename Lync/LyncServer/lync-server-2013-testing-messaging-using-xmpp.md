---
title: Lync Server 2013： 測試通訊使用 XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94841a3ec17878258b26fd945aa60123ac76a9c7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="423b6-102">測試通訊使用 Lync Server 2013 中的 XMPP</span><span class="sxs-lookup"><span data-stu-id="423b6-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="423b6-103">_**上次修改主題：** 2014年-11-03_</span><span class="sxs-lookup"><span data-stu-id="423b6-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="423b6-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="423b6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="423b6-105">每日</span><span class="sxs-lookup"><span data-stu-id="423b6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="423b6-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="423b6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="423b6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="423b6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="423b6-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="423b6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="423b6-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="423b6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="423b6-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csxmppim</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="423b6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="423b6-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="423b6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="423b6-112">描述</span><span class="sxs-lookup"><span data-stu-id="423b6-112">Description</span></span>

<span data-ttu-id="423b6-113">Extensible Messaging and Presence Protocol (XMPP) 是標準的通訊協定 (XML 格式)，可用於在網際網路上傳送訊息。</span><span class="sxs-lookup"><span data-stu-id="423b6-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="423b6-114">XMPP 原本命名為 Jabber，並且受到數個網際網路通訊及通訊應用程式，例如 Google Talk 和 Facebook 聊天室。</span><span class="sxs-lookup"><span data-stu-id="423b6-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="423b6-115">**Test-csxmppim** cmdlet 會確認使用者可以與 XMPP 網路上的使用者交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="423b6-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="423b6-116">請注意，這項測試順利完成，您必須具備有效的 SIP 位址的 XMPP 使用者，和的 SIP 位址必須與已設定為允許的 XMPP 協力廠商的網路上。</span><span class="sxs-lookup"><span data-stu-id="423b6-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="423b6-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="423b6-117">Running the test</span></span>

<span data-ttu-id="423b6-118">下列範例會驗證 XMPP 立即集區 atl-cs-001.litwareinc.com 的郵件功能。</span><span class="sxs-lookup"><span data-stu-id="423b6-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="423b6-119">這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="423b6-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="423b6-120">如果他們有此命令會決定是否第一個測試使用者可以傳送 XMPP 立即訊息給 SIP 位址 adelaney@contoso.com 的使用者。</span><span class="sxs-lookup"><span data-stu-id="423b6-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="423b6-121">如果沒有定義的測試使用者，然後將會失敗命令，因為它不會知道哪些使用者身分登入。</span><span class="sxs-lookup"><span data-stu-id="423b6-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="423b6-122">如果您還沒有定義的集區的測試使用者，就必須納入 UserSipAddress 參數，此命令應使用時，嘗試登入使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="423b6-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="423b6-123">下一個範例所示的命令會測試特定使用者的能力 (litwareinc\\pilar) 登入傳送到使用者 adelaney@contoso.com XMPP 立即訊息。</span><span class="sxs-lookup"><span data-stu-id="423b6-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="423b6-124">若要這麼做，在範例中的第一個命令會使用 Get-credential 指令程式來建立 Windows PowerShell 命令列介面認證物件，其中包含的名稱和密碼為 Pilar Ackerman 的使用者。</span><span class="sxs-lookup"><span data-stu-id="423b6-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="423b6-125">(因為登入名稱 litwareinc\\pilar 包含做為參數中，[Windows PowerShell 認證要求] 對話方塊只需要系統管理員輸入為 Pilar Ackerman 帳戶的密碼。)產生的認證物件然後儲存在名為 $cred1 變數。</span><span class="sxs-lookup"><span data-stu-id="423b6-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="423b6-126">此使用者是否可以登入集區 atl-cs-001.litwareinc.com 並傳送 XMPP 立即訊息，然後會檢查第二個命令。</span><span class="sxs-lookup"><span data-stu-id="423b6-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="423b6-127">若要執行這項工作， **Test-csxmppim** cmdlet 會呼叫，以及四個參數： TargetFqdn (之登錄器集區 FQDN);接收者 （郵件使用者的 SIP 地址所寄送至）;UserCredential （包含為 Pilar Ackerman 的使用者認證的 Windows PowerShell 物件）;和 UserSipAddress （會對應至提供的使用者認證的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="423b6-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="423b6-128">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="423b6-128">Determining success or failure</span></span>

<span data-ttu-id="423b6-129">如果正確設定 XMPP 立即訊息，您會收到類似，具有標示為 Result 屬性的輸出**成功：**</span><span class="sxs-lookup"><span data-stu-id="423b6-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="423b6-130">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="423b6-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="423b6-131">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="423b6-131">Result : Success</span></span>

<span data-ttu-id="423b6-132">延遲： 00:00:02.5361946</span><span class="sxs-lookup"><span data-stu-id="423b6-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="423b6-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="423b6-133">Error Message :</span></span>

<span data-ttu-id="423b6-134">診斷：</span><span class="sxs-lookup"><span data-stu-id="423b6-134">Diagnosis :</span></span>

<span data-ttu-id="423b6-135">如果指定的使用者無法使用 XMPP 立即訊息，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="423b6-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="423b6-136">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="423b6-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="423b6-137">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="423b6-137">domain name (FQDN).</span></span> <span data-ttu-id="423b6-138">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="423b6-138">Using default Registrar port number.</span></span> <span data-ttu-id="423b6-139">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="423b6-139">Exception:</span></span>

<span data-ttu-id="423b6-140">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="423b6-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="423b6-141">在</span><span class="sxs-lookup"><span data-stu-id="423b6-141">at</span></span>

<span data-ttu-id="423b6-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="423b6-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="423b6-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="423b6-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="423b6-144">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="423b6-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="423b6-145">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="423b6-145">Result : Failure</span></span>

<span data-ttu-id="423b6-146">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="423b6-146">Latency : 00:00:00</span></span>

<span data-ttu-id="423b6-147">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="423b6-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="423b6-148">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="423b6-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="423b6-149">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="423b6-149">established connection failed because connected host has</span></span>

<span data-ttu-id="423b6-150">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="423b6-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="423b6-151">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="423b6-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="423b6-152">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="423b6-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="423b6-153">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="423b6-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="423b6-154">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="423b6-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="423b6-155">診斷：</span><span class="sxs-lookup"><span data-stu-id="423b6-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="423b6-156">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="423b6-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="423b6-157">以下是一些常見的原因為何**Test-csxmppim**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="423b6-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="423b6-158">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="423b6-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="423b6-159">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="423b6-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="423b6-160">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="423b6-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="423b6-161">如果設定錯誤或尚未部署 XMPP 閘道設定，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="423b6-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="423b6-162">另請參閱</span><span class="sxs-lookup"><span data-stu-id="423b6-162">See Also</span></span>


[<span data-ttu-id="423b6-163">Set-csxmppgatewayconfiguration</span><span class="sxs-lookup"><span data-stu-id="423b6-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

