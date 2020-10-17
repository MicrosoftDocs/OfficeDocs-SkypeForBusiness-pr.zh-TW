---
title: Lync Server 2013：使用 XMPP 測試通訊
description: Lync Server 2013：使用 XMPP 測試通訊。
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
ms.openlocfilehash: 06faeae0a6104351f9102de31c76b2424a140deb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556299"
---
# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a><span data-ttu-id="a2158-103">在 Lync Server 2013 中使用 XMPP 測試郵件</span><span class="sxs-lookup"><span data-stu-id="a2158-103">Testing messaging using XMPP in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2158-104">_**主題上次修改日期：** 2014-11-03_</span><span class="sxs-lookup"><span data-stu-id="a2158-104">_**Topic Last Modified:** 2014-11-03_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2158-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="a2158-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a2158-106">每日</span><span class="sxs-lookup"><span data-stu-id="a2158-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2158-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="a2158-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a2158-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2158-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2158-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="a2158-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a2158-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a2158-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="a2158-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsXmppIM</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a2158-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsXmppIM</strong> cmdlet.</span></span> <span data-ttu-id="a2158-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a2158-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a2158-113">描述</span><span class="sxs-lookup"><span data-stu-id="a2158-113">Description</span></span>

<span data-ttu-id="a2158-114">Extensible Messaging and Presence Protocol (XMPP) 是標準的通訊協定 (XML 格式)，可用於在網際網路上傳送訊息。</span><span class="sxs-lookup"><span data-stu-id="a2158-114">The Extensible Messaging and Presence Protocol (XMPP) is a standard communications protocol (based on XML) used for sending messages across the Internet.</span></span> <span data-ttu-id="a2158-115">XMPP 最初命名為 Jabber) ，且由數個網際網路郵件和通訊應用程式（如 Google 交談及 Facebook 聊天）所支援。</span><span class="sxs-lookup"><span data-stu-id="a2158-115">XMPP was originally named Jabber, and is supported by several Internet messaging and communication applications, such as Google Talk and Facebook Chat.</span></span> <span data-ttu-id="a2158-116">**Test-CsXmppIM** Cmdlet 會驗證使用者是否可以與 XMPP 網路上的使用者交換立即訊息。</span><span class="sxs-lookup"><span data-stu-id="a2158-116">The **Test-CsXmppIM** cmdlet verifies that a user can exchange instant messages with a user on an XMPP network.</span></span> <span data-ttu-id="a2158-117">請注意，若要讓此測試成功，您必須具備 XMPP 使用者的有效 SIP 位址，而且該 SIP 位址必須位於設定為「允許的 XMPP」夥伴的網路上。</span><span class="sxs-lookup"><span data-stu-id="a2158-117">Note that, for this test to succeed, you must have a valid SIP address for the XMPP user, and that SIP address must be on a network that was configured as an allowed XMPP partner.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a2158-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="a2158-118">Running the test</span></span>

<span data-ttu-id="a2158-119">下列範例會驗證集區 atl-cs-001.litwareinc.com 的 XMPP 立即訊息功能。</span><span class="sxs-lookup"><span data-stu-id="a2158-119">The following example verifies the XMPP instant messaging capabilities for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a2158-120">只有針對集區 atl-cs-001.litwareinc.com 定義測試使用者時，此命令才會運作。</span><span class="sxs-lookup"><span data-stu-id="a2158-120">This command will work only if test users are defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="a2158-121">如果有的話，此命令會判斷第一個測試使用者是否可以傳送 XMPP 立即訊息給具有 SIP 位址 adelaney@contoso.com 的使用者。</span><span class="sxs-lookup"><span data-stu-id="a2158-121">If they have, then the command will determine whether the first test user can send an XMPP instant message to a user who has the SIP address adelaney@contoso.com.</span></span>

<span data-ttu-id="a2158-122">若未定義測試使用者，命令將會失敗，因為它不會知道哪個使用者登入。</span><span class="sxs-lookup"><span data-stu-id="a2158-122">If test users are not defined, then the command will fail because it won't know which user to log on as.</span></span> <span data-ttu-id="a2158-123">若尚未定義集區的測試使用者，則必須包括 UserSipAddress 參數，以及在嘗試登入時應使用命令的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="a2158-123">If you have not defined test users for a pool, then you must include the UserSipAddress parameter and the credentials of the user who the command should use when trying to log on.</span></span>

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

<span data-ttu-id="a2158-124">下一個範例中所示的命令會測試特定使用者 (litwareinc pilar 的功能 \\ 。) 登入以傳送 XMPP 立即訊息給使用者 adelaney@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="a2158-124">The commands shown in the next example test the ability of a specific user (litwareinc\\pilar) to log on to send an XMPP instant message to the user adelaney@contoso.com.</span></span> <span data-ttu-id="a2158-125">為做到這一點，範例中的第一個命令會使用 Get-Credential Cmdlet 來建立 Windows PowerShell 命令列介面身分介面，該物件包含使用者 Pilar Ackerman 的名稱和密碼。</span><span class="sxs-lookup"><span data-stu-id="a2158-125">To do this, the first command in the example uses the Get-Credential cmdlet to create a Windows PowerShell command-line interface credential object that contains the name and password of the user Pilar Ackerman.</span></span> <span data-ttu-id="a2158-126"> (因為登入名稱 litwareinc \\ pilar 已包含為參數，所以 Windows PowerShell 認證要求] 對話方塊只要求系統管理員輸入 Pilar Ackerman 帳戶的密碼。 ) 所產生的身分憑證物件會儲存在名為 $cred 1 的變數中。</span><span class="sxs-lookup"><span data-stu-id="a2158-126">(Because the logon name litwareinc\\pilar was included as a parameter, the Windows PowerShell Credential Request dialog box only requires the administrator to enter the password for the Pilar Ackerman account.) The resulting credential object is then stored in a variable named $cred1.</span></span>

<span data-ttu-id="a2158-127">然後，第二個命令會檢查此使用者是否可以登入集區 atl-cs-001.litwareinc.com 並傳送 XMPP 立即訊息。</span><span class="sxs-lookup"><span data-stu-id="a2158-127">The second command then checks whether this user can log on to the pool atl-cs-001.litwareinc.com and send the XMPP instant message.</span></span> <span data-ttu-id="a2158-128">若要執行此工作， **CsXmppIm** 指令程式會與四個參數一起呼叫： TargetFqdn (註冊區集區的 FQDN) ;收件者 (要傳送郵件給) 的使用者 SIP 位址。UserCredential (包含 Pilar Ackerman 使用者認證) 的 Windows PowerShell 物件。和 UserSipAddress (與所提供使用者認證) 相對應的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="a2158-128">To run this task, the **Test-CsXmppIm** cmdlet is called, together with four parameters: TargetFqdn (the FQDN of the Registrar pool); Receiver (the SIP address of the user the message is being addressed to); UserCredential (the Windows PowerShell object that contains Pilar Ackerman’s user credentials); and UserSipAddress (the SIP address that corresponds to the supplied user credentials).</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a2158-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="a2158-129">Determining success or failure</span></span>

<span data-ttu-id="a2158-130">如果 XMPP 立即訊息設定正確，您會收到類似以下的輸出，並將 Result 屬性標示為 **成功：**</span><span class="sxs-lookup"><span data-stu-id="a2158-130">If XMPP instant messaging is correctly configured, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="a2158-131">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2158-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2158-132">結果：成功</span><span class="sxs-lookup"><span data-stu-id="a2158-132">Result : Success</span></span>

<span data-ttu-id="a2158-133">延遲：00：00：02.5361946</span><span class="sxs-lookup"><span data-stu-id="a2158-133">Latency : 00:00:02.5361946</span></span>

<span data-ttu-id="a2158-134">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="a2158-134">Error Message :</span></span>

<span data-ttu-id="a2158-135">診斷：</span><span class="sxs-lookup"><span data-stu-id="a2158-135">Diagnosis :</span></span>

<span data-ttu-id="a2158-136">如果指定的使用者無法使用 XMPP 立即訊息，結果將會顯示為 [ **失敗**]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="a2158-136">If the specified users can't use XMPP instant messaging, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="a2158-137">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="a2158-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="a2158-138">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="a2158-138">domain name (FQDN).</span></span> <span data-ttu-id="a2158-139">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="a2158-139">Using default Registrar port number.</span></span> <span data-ttu-id="a2158-140">例外：</span><span class="sxs-lookup"><span data-stu-id="a2158-140">Exception:</span></span>

<span data-ttu-id="a2158-141">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="a2158-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="a2158-142">在</span><span class="sxs-lookup"><span data-stu-id="a2158-142">at</span></span>

<span data-ttu-id="a2158-143">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="a2158-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="a2158-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="a2158-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="a2158-145">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2158-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2158-146">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="a2158-146">Result : Failure</span></span>

<span data-ttu-id="a2158-147">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="a2158-147">Latency : 00:00:00</span></span>

<span data-ttu-id="a2158-148">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="a2158-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="a2158-149">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="a2158-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="a2158-150">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="a2158-150">established connection failed because connected host has</span></span>

<span data-ttu-id="a2158-151">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="a2158-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a2158-152">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="a2158-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="a2158-153">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="a2158-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="a2158-154">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="a2158-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="a2158-155">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="a2158-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="a2158-156">診斷：</span><span class="sxs-lookup"><span data-stu-id="a2158-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a2158-157">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="a2158-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="a2158-158">以下是一些 **Test-CsXmppIM** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="a2158-158">Here are some common reasons why **Test-CsXmppIM** might fail:</span></span>

  - <span data-ttu-id="a2158-159">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="a2158-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a2158-160">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a2158-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a2158-161">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="a2158-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a2158-162">如果 XMPP 閘道設定設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a2158-162">This command will fail if XMPP gateway configuration is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2158-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2158-163">See Also</span></span>


[<span data-ttu-id="a2158-164">Set-CsXmppGatewayConfiguration</span><span class="sxs-lookup"><span data-stu-id="a2158-164">Set-CsXmppGatewayConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

