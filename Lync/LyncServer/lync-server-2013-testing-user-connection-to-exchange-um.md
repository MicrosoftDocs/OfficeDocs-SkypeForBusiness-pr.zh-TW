---
title: Lync Server 2013：測試使用者與 Exchange UM 的連線
description: Lync Server 2013：測試使用者與 Exchange UM 的連線。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea6f7d446fe3fd98db67bab4ffee9cc976202689
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556062"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="252b9-103">在 Lync Server 2013 中測試使用者與 Exchange UM 的連線</span><span class="sxs-lookup"><span data-stu-id="252b9-103">Testing user connection to Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="252b9-104">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="252b9-104">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="252b9-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="252b9-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="252b9-106">每日</span><span class="sxs-lookup"><span data-stu-id="252b9-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="252b9-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="252b9-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="252b9-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="252b9-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="252b9-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="252b9-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="252b9-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="252b9-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="252b9-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsExUMConnectivity</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="252b9-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="252b9-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="252b9-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="252b9-113">描述</span><span class="sxs-lookup"><span data-stu-id="252b9-113">Description</span></span>

<span data-ttu-id="252b9-114">**Test-CsExUMConnectivity** Cmdlet 會驗證指定的使用者是否可以連線至 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="252b9-114">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="252b9-115">請注意，此 Cmdlet 只會驗證是否可對服務進行連線。</span><span class="sxs-lookup"><span data-stu-id="252b9-115">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="252b9-116">它不會測試服務本身。</span><span class="sxs-lookup"><span data-stu-id="252b9-116">It does not test the service itself.</span></span> <span data-ttu-id="252b9-117">若要測試整合通訊服務 (執行綜合交易指令程式，該 Cmdlet 會在使用者的信箱中實際留下語音信箱訊息) 使用 Test-CsExUMVoiceMail 指令程式。</span><span class="sxs-lookup"><span data-stu-id="252b9-117">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="252b9-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="252b9-118">Running the test</span></span>

<span data-ttu-id="252b9-119">下列範例會測試集區 atl-cs-001.litwareinc.com 的 Exchange 整合通訊連線能力。</span><span class="sxs-lookup"><span data-stu-id="252b9-119">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="252b9-120">只有針對集區 atl-cs-001.litwareinc.com 定義的測試使用者才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="252b9-120">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="252b9-121">如果有的話，此命令會判斷第一個測試使用者是否可以連線至整合通訊。</span><span class="sxs-lookup"><span data-stu-id="252b9-121">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="252b9-122">如果未設定集區的測試使用者，命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="252b9-122">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="252b9-123">下列範例中所示的命令會測試使用者 litwareinc kenmyer 的 Exchange 整合通訊連線能力 \\ 。</span><span class="sxs-lookup"><span data-stu-id="252b9-123">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="252b9-124">為做到這一點，範例中的第一個命令會使用 **Get-Credential** Cmdlet 為使用者 litwareinc Kenmyer 建立 Windows PowerShell 命令列介面認證物件 \\ 。</span><span class="sxs-lookup"><span data-stu-id="252b9-124">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="252b9-125">請注意，您必須為此帳戶提供密碼，才能建立有效的認證物件，並確保 **Test-CsExUMConnectivity** Cmdlet 可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="252b9-125">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="252b9-126">範例中的第二個命令會使用提供的認證物件 ($x) 和使用者 litwareinc kenmyer 的 SIP 位址， \\ 以判斷使用者是否可以連線至 Exchange 整合通訊。</span><span class="sxs-lookup"><span data-stu-id="252b9-126">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="252b9-127">下一個範例中所示的命令是剛才所顯示之命令的變化。</span><span class="sxs-lookup"><span data-stu-id="252b9-127">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="252b9-128">在此情況下，會包含 OutLoggerVariable 參數，以產生每個步驟所執行之每個步驟的詳細記錄 **Test-CsExUMConnectivity** Cmdletand 每個步驟的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="252b9-128">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="252b9-129">若要這麼做，OutLoggerVariable 參數會加上參數值 ExumText。這會導致詳細記錄資訊儲存在名為 $ExumTest 的變數中。</span><span class="sxs-lookup"><span data-stu-id="252b9-129">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="252b9-130">在範例的最後一個命令中，會使用 ToXML ( # A1 方法將記錄資訊轉換成 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="252b9-130">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="252b9-131">然後，會 \\ 使用 Out-File Cmdlet，將 XML 資料寫入名為 C： LogsExumTest.xml 的檔案 \\ 。</span><span class="sxs-lookup"><span data-stu-id="252b9-131">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="252b9-132">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="252b9-132">Determining success or failure</span></span>

<span data-ttu-id="252b9-133">如果已正確設定 Exchange 整合，您會收到類似以下的輸出，其 Result 屬性標示為 [ **成功**]：</span><span class="sxs-lookup"><span data-stu-id="252b9-133">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="252b9-134">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="252b9-134">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="252b9-135">結果：成功</span><span class="sxs-lookup"><span data-stu-id="252b9-135">Result : Success</span></span>

<span data-ttu-id="252b9-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="252b9-136">Latency : 00:00:00</span></span>

<span data-ttu-id="252b9-137">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="252b9-137">Error Message :</span></span>

<span data-ttu-id="252b9-138">診斷：</span><span class="sxs-lookup"><span data-stu-id="252b9-138">Diagnosis :</span></span>

<span data-ttu-id="252b9-139">如果指定的使用者無法接收通知，結果將會顯示為 [ **失敗**]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="252b9-139">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="252b9-140">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="252b9-140">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="252b9-141">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="252b9-141">Result : Failure</span></span>

<span data-ttu-id="252b9-142">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="252b9-142">Latency : 00:00:00</span></span>

<span data-ttu-id="252b9-143">錯誤訊息：10060，連接嘗試失敗，因為連接的方</span><span class="sxs-lookup"><span data-stu-id="252b9-143">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="252b9-144">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="252b9-144">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="252b9-145">已建立連線失敗，因為連接的主機已</span><span class="sxs-lookup"><span data-stu-id="252b9-145">established connection failed because connected host has</span></span>

<span data-ttu-id="252b9-146">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="252b9-146">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="252b9-147">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="252b9-147">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="252b9-148">在一段時間後，連接的通訊錄未正確回應</span><span class="sxs-lookup"><span data-stu-id="252b9-148">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="252b9-149">時間或已建立的連線失敗，因為連接的主機</span><span class="sxs-lookup"><span data-stu-id="252b9-149">time, or established connection failed because connected host</span></span>

<span data-ttu-id="252b9-150">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="252b9-150">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="252b9-151">診斷：</span><span class="sxs-lookup"><span data-stu-id="252b9-151">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="252b9-152">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="252b9-152">Reasons why the test might have failed</span></span>

<span data-ttu-id="252b9-153">以下是一些 **Test-CsExUMConnectivity** 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="252b9-153">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="252b9-154">提供的參數值不正確。</span><span class="sxs-lookup"><span data-stu-id="252b9-154">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="252b9-155">如果使用，必須正確設定選用參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="252b9-155">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="252b9-156">請重新執行不含選用參數的命令，然後查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="252b9-156">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="252b9-157">如果 Exchange 伺服器設定不當或尚未部署，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="252b9-157">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="252b9-158">如果無法透過網路存取 Exchange Server，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="252b9-158">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="252b9-159">另請參閱</span><span class="sxs-lookup"><span data-stu-id="252b9-159">See Also</span></span>


[<span data-ttu-id="252b9-160">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="252b9-160">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

