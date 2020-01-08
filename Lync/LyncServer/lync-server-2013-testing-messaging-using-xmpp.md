---
title: Lync Server 2013：使用 XMPP 測試訊息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acd03cdf2a5215c980b788dbaffafc5936fe5b5e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="51e4b-102">使用 Lync Server 2013 中的 XMPP 測試訊息</span><span class="sxs-lookup"><span data-stu-id="51e4b-102">Testing messaging using XMPP in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51e4b-103">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="51e4b-103">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51e4b-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="51e4b-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="51e4b-105">日常</span><span class="sxs-lookup"><span data-stu-id="51e4b-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51e4b-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="51e4b-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="51e4b-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="51e4b-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51e4b-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="51e4b-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="51e4b-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="51e4b-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="51e4b-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsXmppIM</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="51e4b-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="51e4b-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="51e4b-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="51e4b-112">描述</span><span class="sxs-lookup"><span data-stu-id="51e4b-112">Description</span></span>

<span data-ttu-id="51e4b-113">[可擴展訊息與目前狀態通訊協定（XMPP）] 是標準通訊通訊協定（根據 XML），用於透過網際網路傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="51e4b-113">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="51e4b-114">XMPP 最初已命名為 Jabber，且受到數個網際網路訊息與通訊應用程式（例如 Google 交談和 Facebook 聊天）支援。</span><span class="sxs-lookup"><span data-stu-id="51e4b-114">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="51e4b-115">**CsXmppIM** Cmdlet 會確認使用者可以與 XMPP 網路上的使用者交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="51e4b-115">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="51e4b-116">請注意，若要讓此測試成功，您必須具備 XMPP 使用者的有效 SIP 位址，且該 SIP 位址必須位於已設定為允許 XMPP 合作夥伴的網路上。</span><span class="sxs-lookup"><span data-stu-id="51e4b-116">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="51e4b-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="51e4b-117">Running the test</span></span>

<span data-ttu-id="51e4b-118">下列範例會驗證 pool atl-cs-001.litwareinc.com 的 XMPP 立即訊息功能。</span><span class="sxs-lookup"><span data-stu-id="51e4b-118">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="51e4b-119">只有針對 [pool atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="51e4b-119">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="51e4b-120">如果有的話，命令會判斷第一個測試使用者是否可以傳送 XMPP 立即訊息給擁有 SIP 位址 adelaney@contoso.com 的使用者。</span><span class="sxs-lookup"><span data-stu-id="51e4b-120">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="51e4b-121">如果沒有定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。</span><span class="sxs-lookup"><span data-stu-id="51e4b-121">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="51e4b-122">如果您沒有為某個池定義測試使用者，則您必須加入 UserSipAddress 參數以及在嘗試登入時應該使用該命令的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="51e4b-122">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="51e4b-123">下一個範例中所示的命令會測試特定使用者（litwareinc\\pilar）登入的能力，以傳送 XMPP 立即訊息給使用者 adelaney@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="51e4b-123">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="51e4b-124">若要這樣做，範例中的第一個命令會使用取得認證 Cmdlet 來建立 Windows PowerShell 命令列介面身分憑證物件，該物件包含使用者 Pilar 方的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="51e4b-124">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="51e4b-125">（因為登入名稱 litwareinc\\pilar 是以參數形式提供，所以 [Windows PowerShell 認證要求] 對話方塊只需要管理員輸入 pilar 方帳戶的密碼。）接著會將產生的認證物件儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="51e4b-125">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="51e4b-126">然後，第二個命令會檢查此使用者是否可以登入 [pool atl-cs-001.litwareinc.com]，並傳送 XMPP 的立即訊息。</span><span class="sxs-lookup"><span data-stu-id="51e4b-126">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="51e4b-127">若要執行這項工作，請使用四個參數： TargetFqdn （註冊機構池的 FQDN）來呼叫**CsXmppIm** Cmdlet;收件者（傳送訊息的使用者的 SIP 位址）;UserCredential （包含 Pilar 方使用者認證的 Windows PowerShell 物件）;與 UserSipAddress （與提供的使用者認證相對應的 SIP 位址）。</span><span class="sxs-lookup"><span data-stu-id="51e4b-127">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="51e4b-128">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="51e4b-128">Determining success or failure</span></span>

<span data-ttu-id="51e4b-129">如果 XMPP 立即訊息設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="51e4b-129">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="51e4b-130">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="51e4b-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="51e4b-131">結果：成功</span><span class="sxs-lookup"><span data-stu-id="51e4b-131">Result : Success</span></span>

<span data-ttu-id="51e4b-132">延隔時間：00：00：02.5361946</span><span class="sxs-lookup"><span data-stu-id="51e4b-132">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="51e4b-133">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="51e4b-133">Error Message :</span></span>

<span data-ttu-id="51e4b-134">自檢</span><span class="sxs-lookup"><span data-stu-id="51e4b-134">Diagnosis :</span></span>

<span data-ttu-id="51e4b-135">如果指定的使用者無法使用 XMPP 立即訊息，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="51e4b-135">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="51e4b-136">警告：無法讀取指定之完全限定的註冊機構埠號碼</span><span class="sxs-lookup"><span data-stu-id="51e4b-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="51e4b-137">網功能變數名稱稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="51e4b-137">domain name (FQDN).</span></span> <span data-ttu-id="51e4b-138">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="51e4b-138">Using default Registrar port number.</span></span> <span data-ttu-id="51e4b-139">引發</span><span class="sxs-lookup"><span data-stu-id="51e4b-139">Exception:</span></span>

<span data-ttu-id="51e4b-140">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="51e4b-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="51e4b-141">的</span><span class="sxs-lookup"><span data-stu-id="51e4b-141">at</span></span>

<span data-ttu-id="51e4b-142">TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction</span><span class="sxs-lookup"><span data-stu-id="51e4b-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="51e4b-143">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="51e4b-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="51e4b-144">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="51e4b-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="51e4b-145">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="51e4b-145">Result : Failure</span></span>

<span data-ttu-id="51e4b-146">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="51e4b-146">Latency : 00:00:00</span></span>

<span data-ttu-id="51e4b-147">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="51e4b-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="51e4b-148">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="51e4b-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="51e4b-149">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="51e4b-149">established connection failed because connected host has</span></span>

<span data-ttu-id="51e4b-150">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="51e4b-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="51e4b-151">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="51e4b-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="51e4b-152">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="51e4b-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="51e4b-153">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="51e4b-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="51e4b-154">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="51e4b-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="51e4b-155">自檢</span><span class="sxs-lookup"><span data-stu-id="51e4b-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="51e4b-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="51e4b-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="51e4b-157">以下是**測試 CsXmppIM**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="51e4b-157">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="51e4b-158">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="51e4b-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="51e4b-159">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="51e4b-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="51e4b-160">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="51e4b-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="51e4b-161">如果 XMPP 閘道設定配置錯誤或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="51e4b-161">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51e4b-162">請參閱</span><span class="sxs-lookup"><span data-stu-id="51e4b-162">See Also</span></span>


[<span data-ttu-id="51e4b-163">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="51e4b-163">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

