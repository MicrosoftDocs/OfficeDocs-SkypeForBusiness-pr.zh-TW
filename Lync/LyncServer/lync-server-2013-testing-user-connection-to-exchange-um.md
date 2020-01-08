---
title: Lync Server 2013：測試使用者與 Exchange UM 的連線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cc54577e94f7679e833f06a4a5de060aaf761a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="54655-102">在 Lync Server 2013 中測試使用者與 Exchange UM 的連線</span><span class="sxs-lookup"><span data-stu-id="54655-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54655-103">_**主題上次修改日期：** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="54655-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54655-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="54655-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="54655-105">日常</span><span class="sxs-lookup"><span data-stu-id="54655-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54655-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="54655-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="54655-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="54655-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54655-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="54655-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="54655-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="54655-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="54655-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行<strong>CsExUMConnectivity</strong> Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="54655-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="54655-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="54655-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="54655-112">描述</span><span class="sxs-lookup"><span data-stu-id="54655-112">Description</span></span>

<span data-ttu-id="54655-113">**CsExUMConnectivity** Cmdlet 會驗證指定的使用者是否可以連線到 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="54655-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="54655-114">請注意，這個 Cmdlet 只會驗證是否可以與服務建立連線。</span><span class="sxs-lookup"><span data-stu-id="54655-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="54655-115">它不會測試服務本身。</span><span class="sxs-lookup"><span data-stu-id="54655-115">It does not test the service itself.</span></span> <span data-ttu-id="54655-116">若要測試整合訊息服務（執行綜合交易 Cmdlet，以實際在使用者信箱中留下語音信箱），請使用 CsExUMVoiceMail Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54655-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="54655-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="54655-117">Running the test</span></span>

<span data-ttu-id="54655-118">下列範例會測試 [pool atl-cs-001.litwareinc.com] 的 Exchange 整合訊息連線。</span><span class="sxs-lookup"><span data-stu-id="54655-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="54655-119">只有在針對 [池 atl-cs-001.litwareinc.com] 定義測試使用者時，才能使用此命令。</span><span class="sxs-lookup"><span data-stu-id="54655-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="54655-120">如果有的話，命令會判斷第一個測試使用者是否可以連線至整合通訊。</span><span class="sxs-lookup"><span data-stu-id="54655-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="54655-121">如果沒有為該 pool 設定測試使用者，命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="54655-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="54655-122">下列範例中所示的命令會針對使用者 litwareinc\\Kenmyer 測試 Exchange 整合訊息連線。</span><span class="sxs-lookup"><span data-stu-id="54655-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="54655-123">若要這樣做，範例中的第一個命令會使用**取得認證**Cmdlet 來為使用者 litwareinc\\kenmyer 建立 Windows PowerShell 命令列介面認證物件。</span><span class="sxs-lookup"><span data-stu-id="54655-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="54655-124">請注意，您必須為此帳戶提供密碼才能建立有效的認證物件，並確保**Test CsExUMConnectivity** Cmdlet 可以執行其檢查。</span><span class="sxs-lookup"><span data-stu-id="54655-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="54655-125">這個範例中的第二個命令使用所提供的認證物件（$x）和使用者 litwareinc\\KENMYER 的 SIP 位址來判斷使用者是否可以連線到 Exchange 整合訊息。</span><span class="sxs-lookup"><span data-stu-id="54655-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="54655-126">下一個範例中所示的命令就是剛才所示的命令變化。</span><span class="sxs-lookup"><span data-stu-id="54655-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="54655-127">在這種情況下，會包含 OutLoggerVariable 參數，以產生由**Test CsExUMConnectivity** Cmdletand 每個步驟成功或失敗所完成的每個步驟的詳細記錄。</span><span class="sxs-lookup"><span data-stu-id="54655-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="54655-128">若要這樣做，OutLoggerVariable 參數會與參數值 ExumText 一起新增;這會使詳細的記錄資訊儲存在名為 $ExumTest 的變數中。</span><span class="sxs-lookup"><span data-stu-id="54655-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="54655-129">在這個範例的最後一個命令中，ToXML （）方法是用來將記錄資訊轉換成 XML 格式。</span><span class="sxs-lookup"><span data-stu-id="54655-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="54655-130">然後，該 XML 資料會寫入一個名為 C：\\ExumTest 的檔案\\，並使用 Out file Cmdlet 來登入。</span><span class="sxs-lookup"><span data-stu-id="54655-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="54655-131">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="54655-131">Determining success or failure</span></span>

<span data-ttu-id="54655-132">如果 Exchange 整合設定正確，您將會收到類似以下的輸出，結果屬性標示為**成功**：</span><span class="sxs-lookup"><span data-stu-id="54655-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="54655-133">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="54655-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="54655-134">結果：成功</span><span class="sxs-lookup"><span data-stu-id="54655-134">Result : Success</span></span>

<span data-ttu-id="54655-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="54655-135">Latency : 00:00:00</span></span>

<span data-ttu-id="54655-136">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="54655-136">Error Message :</span></span>

<span data-ttu-id="54655-137">自檢</span><span class="sxs-lookup"><span data-stu-id="54655-137">Diagnosis :</span></span>

<span data-ttu-id="54655-138">如果指定的使用者無法接收通知，結果就會顯示為**失敗**，而其他資訊將會記錄在錯誤與診斷屬性中：</span><span class="sxs-lookup"><span data-stu-id="54655-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="54655-139">目標 Fqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="54655-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="54655-140">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="54655-140">Result : Failure</span></span>

<span data-ttu-id="54655-141">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="54655-141">Latency : 00:00:00</span></span>

<span data-ttu-id="54655-142">錯誤訊息：10060，連線嘗試失敗，因為已連接的方</span><span class="sxs-lookup"><span data-stu-id="54655-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="54655-143">在一段時間後沒有正確回應，或</span><span class="sxs-lookup"><span data-stu-id="54655-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="54655-144">已建立的連線失敗，因為連接的主機有</span><span class="sxs-lookup"><span data-stu-id="54655-144">established connection failed because connected host has</span></span>

<span data-ttu-id="54655-145">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="54655-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="54655-146">內部例外狀況：連接嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="54655-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="54655-147">已連接的參與方在一段時間後沒有正確回應</span><span class="sxs-lookup"><span data-stu-id="54655-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="54655-148">時間或已建立的連線失敗，因為已連接主機</span><span class="sxs-lookup"><span data-stu-id="54655-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="54655-149">無法回應10.188.116.96：5061</span><span class="sxs-lookup"><span data-stu-id="54655-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="54655-150">自檢</span><span class="sxs-lookup"><span data-stu-id="54655-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="54655-151">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="54655-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="54655-152">以下是**測試 CsExUMConnectivity**可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="54655-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="54655-153">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="54655-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="54655-154">如果使用，必須正確設定選用的參數，否則測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="54655-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="54655-155">重新執行不含選用參數的命令，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="54655-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="54655-156">如果 Exchange 伺服器未正確設定或尚未部署，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="54655-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="54655-157">如果您的網路無法達到 Exchange 伺服器，此命令就會失敗。</span><span class="sxs-lookup"><span data-stu-id="54655-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="54655-158">請參閱</span><span class="sxs-lookup"><span data-stu-id="54655-158">See Also</span></span>


[<span data-ttu-id="54655-159">Test-CsExUMVoiceMail</span><span class="sxs-lookup"><span data-stu-id="54655-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

