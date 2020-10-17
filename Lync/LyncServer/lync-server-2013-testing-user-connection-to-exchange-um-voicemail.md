---
title: Lync Server 2013：測試使用者與 Exchange UM 語音信箱的連線
description: Lync Server 2013：測試使用者與 Exchange UM 語音信箱的連線。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b887b5b0df02a5864e0a39f2b62893d20105a86a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552609"
---
# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="c3393-103">在 Lync Server 2013 中測試使用者與 Exchange UM 語音信箱的連線</span><span class="sxs-lookup"><span data-stu-id="c3393-103">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3393-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3393-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3393-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="c3393-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c3393-106">每日</span><span class="sxs-lookup"><span data-stu-id="c3393-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3393-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="c3393-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c3393-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3393-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3393-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="c3393-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c3393-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="c3393-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c3393-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsExUMVoiceMail</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="c3393-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="c3393-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c3393-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c3393-113">描述</span><span class="sxs-lookup"><span data-stu-id="c3393-113">Description</span></span>

<span data-ttu-id="c3393-114">**Test-CsExUMVoiceMail** Cmdlet 可讓系統管理員確認使用者是否可以存取和使用 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="c3393-114">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="c3393-115">若要這麼做，Cmdlet 會連線至整合通訊服務，並在指定的信箱中留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c3393-115">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="c3393-116">這可以是系統提供的語音信箱，也可以是自訂。您自行錄製的 WAV 檔案。</span><span class="sxs-lookup"><span data-stu-id="c3393-116">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c3393-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="c3393-117">Running the test</span></span>

<span data-ttu-id="c3393-118">下列範例會測試集區 atl-cs-001.litwareinc.com 的 Exchange 整合通訊語音信箱連線能力。</span><span class="sxs-lookup"><span data-stu-id="c3393-118">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c3393-119">只有針對集區 atl-cs-001.litwareinc.com 定義的測試使用者才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="c3393-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="c3393-120">如果有的話，此命令會判斷第一個測試使用者是否可以使用整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c3393-120">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="c3393-121">如果未設定集區的測試使用者，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c3393-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="c3393-122">下一個範例中所示的命令會測試使用者 litwareinc kenmyer 的 Exchange 整合通訊語音信箱連線能力 \\ 。</span><span class="sxs-lookup"><span data-stu-id="c3393-122">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="c3393-123">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 為使用者 litwareinc Kenmyer 建立 Windows PowerShell 命令列介面認證物件 \\ 。</span><span class="sxs-lookup"><span data-stu-id="c3393-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="c3393-124">請注意，您必須為此帳戶提供密碼，才能建立有效的認證物件，並確保 **Test-CsExUMVoiceMail** Cmdlet 可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="c3393-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="c3393-125">範例中的第二個命令會使用提供的認證物件 ($x) 和使用者 litwareinc kenmyer 的 SIP 位址， \\ 以判斷使用者是否可以連線至 Exchange 整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="c3393-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="c3393-126">下一個範例中所示的命令是範例1所示命令的變化。在此情況下，會包含 OutLoggerVariable 參數，以產生每個步驟所執行之每個步驟的詳細記錄 **Test-CsExUMVoiceMail** Cmdletand 每個步驟的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="c3393-126">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="c3393-127">若要這麼做，OutLoggerVariable 參數會加上參數值 ExumText;這會導致詳細記錄資訊儲存在名為 $ExumTest 的變數中。</span><span class="sxs-lookup"><span data-stu-id="c3393-127">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="c3393-128">在範例的最後一個命令中，會使用 ToXML ( # A1 方法將記錄資訊轉換成 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="c3393-128">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="c3393-129">然後，會 \\ 使用 Out-File Cmdlet，將 XML 資料寫入名為 C： LogsVoicemailTest.xml 的檔案 \\ 。</span><span class="sxs-lookup"><span data-stu-id="c3393-129">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c3393-130">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="c3393-130">Determining success or failure</span></span>

<span data-ttu-id="c3393-131">如果已正確設定 Exchange 整合，您會收到類似以下的輸出，其 Result 屬性標示為 [ **成功**]：</span><span class="sxs-lookup"><span data-stu-id="c3393-131">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="c3393-132">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3393-132">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c3393-133">結果：成功</span><span class="sxs-lookup"><span data-stu-id="c3393-133">Result : Success</span></span>

<span data-ttu-id="c3393-134">延遲：00：00：02.9911345</span><span class="sxs-lookup"><span data-stu-id="c3393-134">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="c3393-135">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="c3393-135">Error Message :</span></span>

<span data-ttu-id="c3393-136">診斷：</span><span class="sxs-lookup"><span data-stu-id="c3393-136">Diagnosis :</span></span>

<span data-ttu-id="c3393-137">如果指定的使用者無法連線至語音信箱，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="c3393-137">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="c3393-138">警告：無法讀取指定之完全限定的註冊器通訊埠號碼</span><span class="sxs-lookup"><span data-stu-id="c3393-138">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="c3393-139">功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="c3393-139">domain name (FQDN).</span></span> <span data-ttu-id="c3393-140">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="c3393-140">Using default Registrar port number.</span></span> <span data-ttu-id="c3393-141">例外：</span><span class="sxs-lookup"><span data-stu-id="c3393-141">Exception:</span></span>

<span data-ttu-id="c3393-142">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="c3393-142">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="c3393-143">在</span><span class="sxs-lookup"><span data-stu-id="c3393-143">at</span></span>

<span data-ttu-id="c3393-144">SipSyntheticTransaction TryRetri （SyntheticTransactions）</span><span class="sxs-lookup"><span data-stu-id="c3393-144">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="c3393-145">eveRegistrarPortFromTopology (Int32& registrarPortNumber) </span><span class="sxs-lookup"><span data-stu-id="c3393-145">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="c3393-146">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="c3393-146">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="c3393-147">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="c3393-147">Result : Failure</span></span>

<span data-ttu-id="c3393-148">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="c3393-148">Latency : 00:00:00</span></span>

<span data-ttu-id="c3393-149">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="c3393-149">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="c3393-150">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="c3393-150">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="c3393-151">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="c3393-151">established connection failed because connected host has</span></span>

<span data-ttu-id="c3393-152">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="c3393-152">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c3393-153">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="c3393-153">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="c3393-154">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="c3393-154">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="c3393-155">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="c3393-155">time, or established connection failed because connected host</span></span>

<span data-ttu-id="c3393-156">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="c3393-156">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="c3393-157">診斷：</span><span class="sxs-lookup"><span data-stu-id="c3393-157">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c3393-158">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="c3393-158">Reasons why the test might have failed</span></span>

<span data-ttu-id="c3393-159">以下是一些 **Test-CsExUMVoiceMail** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="c3393-159">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="c3393-160">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="c3393-160">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="c3393-161">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c3393-161">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="c3393-162">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="c3393-162">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="c3393-163">如果 Exchange 伺服器設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="c3393-163">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3393-164">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c3393-164">See Also</span></span>


[<span data-ttu-id="c3393-165">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="c3393-165">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

