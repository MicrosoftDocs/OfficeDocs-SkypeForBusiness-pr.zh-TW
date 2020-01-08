---
title: Lync Server 2013：測試使用者與 Exchange UM 語音信箱的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f09921d62eddb1f1b426e0e3b1fc4984a0987a8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="29de7-102">在 Lync Server 2013 中測試使用者與 Exchange UM 語音信箱的連線</span><span class="sxs-lookup"><span data-stu-id="29de7-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29de7-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="29de7-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29de7-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="29de7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="29de7-105">日常</span><span class="sxs-lookup"><span data-stu-id="29de7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29de7-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="29de7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="29de7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="29de7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29de7-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="29de7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="29de7-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="29de7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="29de7-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsExUMVoiceMail</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="29de7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="29de7-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="29de7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="29de7-112">描述</span><span class="sxs-lookup"><span data-stu-id="29de7-112">Description</span></span>

<span data-ttu-id="29de7-113">**CsExUMVoiceMail** Cmdlet 可讓系統管理員確認使用者可以存取及使用 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="29de7-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="29de7-114">若要這樣做，此 Cmdlet 會連線到整合郵件服務，並在指定的信箱中留下語音信箱。</span><span class="sxs-lookup"><span data-stu-id="29de7-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="29de7-115">這可以是系統提供的語音信箱，也可以是自訂的。WAV 檔案，您已經錄製了自己的檔案。</span><span class="sxs-lookup"><span data-stu-id="29de7-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="29de7-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="29de7-116">Running the test</span></span>

<span data-ttu-id="29de7-117">下列範例會針對 [pool atl-cs-001.litwareinc.com] 測試 Exchange 整合通訊語音信箱連線。</span><span class="sxs-lookup"><span data-stu-id="29de7-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="29de7-118">只有在針對 [池 atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="29de7-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="29de7-119">如果有的話，命令會判斷第一個測試使用者是否可以使用整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="29de7-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="29de7-120">如果沒有為該 pool 設定測試使用者，命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="29de7-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="29de7-121">下一個範例中所示的命令會針對使用者 litwareinc\\kenmyer，測試 Exchange 整合通訊語音信箱連線。</span><span class="sxs-lookup"><span data-stu-id="29de7-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="29de7-122">若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來為使用者 litwareinc\\kenmyer 建立 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="29de7-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="29de7-123">請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確保**Test CsExUMVoiceMail** Cmdlet 可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="29de7-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="29de7-124">這個範例中的第二個命令使用所提供的認證物件（$x）和使用者 litwareinc\\KENMYER 的 SIP 位址來判斷使用者是否可以連線到 Exchange 整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="29de7-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="29de7-125">下一個範例中所示的命令是範例1中顯示的命令變化，在這種情況下，會包含 OutLoggerVariable 參數，以產生由**Test CsExUMVoiceMail** Cmdletand 每個步驟成功或失敗所完成的每個步驟的詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="29de7-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="29de7-126">若要這樣做，OutLoggerVariable 參數會加在參數值 ExumText 的旁邊;這會使詳細的記錄資訊儲存在名為 $ExumTest 的變數中。</span><span class="sxs-lookup"><span data-stu-id="29de7-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="29de7-127">在這個範例的最後一個命令中，ToXML （）方法是用來將記錄資訊轉換成 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="29de7-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="29de7-128">然後，該 XML 資料會寫入一個名為 C：\\VoicemailTest 的檔案\\，並使用 Out file Cmdlet 來登入。</span><span class="sxs-lookup"><span data-stu-id="29de7-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="29de7-129">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="29de7-129">Determining success or failure</span></span>

<span data-ttu-id="29de7-130">如果 Exchange 整合設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功**：</span><span class="sxs-lookup"><span data-stu-id="29de7-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="29de7-131">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29de7-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29de7-132">結果：成功</span><span class="sxs-lookup"><span data-stu-id="29de7-132">Result : Success</span></span>

<span data-ttu-id="29de7-133">延隔時間：00：00：02.9911345</span><span class="sxs-lookup"><span data-stu-id="29de7-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="29de7-134">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="29de7-134">Error Message :</span></span>

<span data-ttu-id="29de7-135">自檢</span><span class="sxs-lookup"><span data-stu-id="29de7-135">Diagnosis :</span></span>

<span data-ttu-id="29de7-136">如果指定的使用者無法連線至語音信箱，結果將會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="29de7-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="29de7-137">警告：無法讀取指定之完全限定的註冊機構埠號碼</span><span class="sxs-lookup"><span data-stu-id="29de7-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="29de7-138">網功能變數名稱稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="29de7-138">domain name (FQDN).</span></span> <span data-ttu-id="29de7-139">使用預設的註冊器埠號碼。</span><span class="sxs-lookup"><span data-stu-id="29de7-139">Using default Registrar port number.</span></span> <span data-ttu-id="29de7-140">引發</span><span class="sxs-lookup"><span data-stu-id="29de7-140">Exception:</span></span>

<span data-ttu-id="29de7-141">InvalidOperationException：在拓撲中找不到相符的群集。</span><span class="sxs-lookup"><span data-stu-id="29de7-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="29de7-142">的</span><span class="sxs-lookup"><span data-stu-id="29de7-142">at</span></span>

<span data-ttu-id="29de7-143">TryRetri 的 SyntheticTransactions。 SipSyntheticTransaction</span><span class="sxs-lookup"><span data-stu-id="29de7-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="29de7-144">eveRegistrarPortFromTopology （Int32& registrarPortNumber）</span><span class="sxs-lookup"><span data-stu-id="29de7-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="29de7-145">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="29de7-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="29de7-146">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="29de7-146">Result : Failure</span></span>

<span data-ttu-id="29de7-147">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="29de7-147">Latency : 00:00:00</span></span>

<span data-ttu-id="29de7-148">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="29de7-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="29de7-149">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="29de7-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="29de7-150">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="29de7-150">established connection failed because connected host has</span></span>

<span data-ttu-id="29de7-151">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="29de7-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="29de7-152">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="29de7-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="29de7-153">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="29de7-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="29de7-154">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="29de7-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="29de7-155">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="29de7-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="29de7-156">自檢</span><span class="sxs-lookup"><span data-stu-id="29de7-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="29de7-157">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="29de7-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="29de7-158">以下是**測試 CsExUMVoiceMail**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="29de7-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="29de7-159">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="29de7-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="29de7-160">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="29de7-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="29de7-161">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="29de7-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="29de7-162">如果 Exchange 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="29de7-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29de7-163">請參閱</span><span class="sxs-lookup"><span data-stu-id="29de7-163">See Also</span></span>


[<span data-ttu-id="29de7-164">Test-CsExUMConnectivity</span><span class="sxs-lookup"><span data-stu-id="29de7-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

