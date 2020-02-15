---
title: Lync Server 2013： 測試 Exchange UM 語音信箱使用者連線
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
ms.openlocfilehash: ae68b9a5fb2e03fd08fbc7cd06507c54a383197f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a><span data-ttu-id="77da6-102">在 Lync Server 2013 中進行測試 Exchange UM 語音信箱的使用者連線</span><span class="sxs-lookup"><span data-stu-id="77da6-102">Testing user connection to Exchange UM voicemail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77da6-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="77da6-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77da6-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="77da6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="77da6-105">每日</span><span class="sxs-lookup"><span data-stu-id="77da6-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77da6-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="77da6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="77da6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="77da6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77da6-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="77da6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="77da6-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="77da6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="77da6-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csexumvoicemail</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="77da6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMVoiceMail</strong> cmdlet.</span></span> <span data-ttu-id="77da6-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="77da6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="77da6-112">描述</span><span class="sxs-lookup"><span data-stu-id="77da6-112">Description</span></span>

<span data-ttu-id="77da6-113">**Test-csexumvoicemail** cmdlet 可讓系統管理員確認使用者可以存取及使用 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="77da6-113">The **Test-CsExUMVoiceMail** cmdlet enables administrators to verify that a user can access and use the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="77da6-114">若要這麼做，指令程式連接至整合通訊服務，並留下語音信箱在指定的信箱。</span><span class="sxs-lookup"><span data-stu-id="77da6-114">To do this, the cmdlet connects to the unified messaging service and leaves a voice mail in the specified mailbox.</span></span> <span data-ttu-id="77da6-115">這可以是系統提供語音信箱，或自訂。您所錄製您自己的 WAV 檔案。</span><span class="sxs-lookup"><span data-stu-id="77da6-115">This can be a system-supplied voice mail, or it can be a custom .WAV file that you have recorded yourself.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="77da6-116">執行測試</span><span class="sxs-lookup"><span data-stu-id="77da6-116">Running the test</span></span>

<span data-ttu-id="77da6-117">下列範例會測試 Exchange 整合通訊語音郵件連線集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="77da6-117">The following example tests Exchange Unified Messaging voice mail connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="77da6-118">這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="77da6-118">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="77da6-119">如果他們有此命令會決定是否第一個測試使用者可以使用整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="77da6-119">If they have, then the command will determine whether the first test user can use Unified Messaging voice mail.</span></span> <span data-ttu-id="77da6-120">如果未設定之集區的測試使用者命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="77da6-120">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="77da6-121">下一個範例會測試 Exchange Unified Messaging 語音郵件連線使用者 litwareinc 所示的命令\\kenmyer。</span><span class="sxs-lookup"><span data-stu-id="77da6-121">The commands shown in the next example test Exchange Unified Messaging voice mail connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="77da6-122">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。</span><span class="sxs-lookup"><span data-stu-id="77da6-122">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="77da6-123">請注意，您必須提供建立有效的認證物件和，以確保**Test-csexumvoicemail** cmdlet 可以執行其檢查此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="77da6-123">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMVoiceMail** cmdlet can run its check.</span></span>

<span data-ttu-id="77da6-124">此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來決定是否或此使用者是否能夠連線至 Exchange 整合通訊語音信箱。</span><span class="sxs-lookup"><span data-stu-id="77da6-124">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging voice mail.</span></span>

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

<span data-ttu-id="77da6-125">在下一個範例中所示的命令是命令的範例 1; 所示的變化在此情況下，之後包含 OutLoggerVariable 參數會包含產生的成功或失敗的每個這些步驟即可**Test-csexumvoicemail** cmdletand 每個步驟的詳細資訊記錄。</span><span class="sxs-lookup"><span data-stu-id="77da6-125">The command shown in the next example is a variation of the command shown in Example 1; in this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMVoiceMail** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="77da6-126">若要這麼做，之後包含 OutLoggerVariable 參數會新增旁參數值 ExumText;會導致儲存在名為 $ExumTest 變數的詳細的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="77da6-126">To do this, the OutLoggerVariable parameter is added alongside the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="77da6-127">在範例中的最後一個命令，在 toxml （） 方法用於將轉換成 XML 格式的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="77da6-127">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="77da6-128">XML 資料然後寫入名為 c: 檔案\\記錄\\使用 VoicemailTest.xml Out-file cmdlet。</span><span class="sxs-lookup"><span data-stu-id="77da6-128">That XML data is then written to a file that is named C:\\Logs\\VoicemailTest.xml by using the Out-File cmdlet.</span></span>

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="77da6-129">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="77da6-129">Determining success or failure</span></span>

<span data-ttu-id="77da6-130">如果已正確設定 Exchange 整合，您會收到類似，具有標示為 [**成功**結果屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="77da6-130">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="77da6-131">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="77da6-131">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="77da6-132">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="77da6-132">Result : Success</span></span>

<span data-ttu-id="77da6-133">延遲： 00:00:02.9911345</span><span class="sxs-lookup"><span data-stu-id="77da6-133">Latency : 00:00:02.9911345</span></span>

<span data-ttu-id="77da6-134">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="77da6-134">Error Message :</span></span>

<span data-ttu-id="77da6-135">診斷：</span><span class="sxs-lookup"><span data-stu-id="77da6-135">Diagnosis :</span></span>

<span data-ttu-id="77da6-136">如果指定的使用者無法連線到語音信箱，結果會顯示為**失敗**，以及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="77da6-136">If the specified user can't connect to voicemail, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="77da6-137">警告： 無法讀取登錄器的連接埠號碼指定完整</span><span class="sxs-lookup"><span data-stu-id="77da6-137">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="77da6-138">網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="77da6-138">domain name (FQDN).</span></span> <span data-ttu-id="77da6-139">使用預設登錄器連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="77da6-139">Using default Registrar port number.</span></span> <span data-ttu-id="77da6-140">例外狀況：</span><span class="sxs-lookup"><span data-stu-id="77da6-140">Exception:</span></span>

<span data-ttu-id="77da6-141">System.InvalidOperationException： 拓撲中找不到比對叢集。</span><span class="sxs-lookup"><span data-stu-id="77da6-141">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="77da6-142">在</span><span class="sxs-lookup"><span data-stu-id="77da6-142">at</span></span>

<span data-ttu-id="77da6-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span><span class="sxs-lookup"><span data-stu-id="77da6-143">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="77da6-144">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="77da6-144">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="77da6-145">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="77da6-145">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="77da6-146">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="77da6-146">Result : Failure</span></span>

<span data-ttu-id="77da6-147">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="77da6-147">Latency : 00:00:00</span></span>

<span data-ttu-id="77da6-148">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="77da6-148">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="77da6-149">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="77da6-149">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="77da6-150">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="77da6-150">established connection failed because connected host has</span></span>

<span data-ttu-id="77da6-151">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="77da6-151">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="77da6-152">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="77da6-152">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="77da6-153">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="77da6-153">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="77da6-154">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="77da6-154">time, or established connection failed because connected host</span></span>

<span data-ttu-id="77da6-155">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="77da6-155">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="77da6-156">診斷：</span><span class="sxs-lookup"><span data-stu-id="77da6-156">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="77da6-157">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="77da6-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="77da6-158">以下是一些常見的原因為何**Test-csexumvoicemail**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="77da6-158">Here are some common reasons why **Test-CsExUMVoiceMail** might fail:</span></span>

  - <span data-ttu-id="77da6-159">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="77da6-159">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="77da6-160">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="77da6-160">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="77da6-161">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="77da6-161">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="77da6-162">如果設定錯誤或尚未部署 Exchange 伺服器，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="77da6-162">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77da6-163">另請參閱</span><span class="sxs-lookup"><span data-stu-id="77da6-163">See Also</span></span>


[<span data-ttu-id="77da6-164">Test-csexumconnectivity</span><span class="sxs-lookup"><span data-stu-id="77da6-164">Test-CsExUMConnectivity</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

