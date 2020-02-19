---
title: Lync Server 2013： 測試使用者連線至 Exchange UM
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
ms.openlocfilehash: b72552f56041103e381291bf13ab13283a3c47ee
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a><span data-ttu-id="48fdf-102">Lync Server 2013 中的測試使用者連線至 Exchange UM</span><span class="sxs-lookup"><span data-stu-id="48fdf-102">Testing user connection to Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48fdf-103">_**上次修改主題：** 2014年-11-01_</span><span class="sxs-lookup"><span data-stu-id="48fdf-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48fdf-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="48fdf-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="48fdf-105">每日</span><span class="sxs-lookup"><span data-stu-id="48fdf-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48fdf-106">測試工具</span><span class="sxs-lookup"><span data-stu-id="48fdf-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="48fdf-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48fdf-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48fdf-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="48fdf-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="48fdf-109">當執行在本機上使用 Lync Server 管理命令介面，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="48fdf-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="48fdf-110">當執行使用 Windows PowerShell 的遠端執行個體時，使用者必須被指派具有執行<strong>Test-csexumconnectivity</strong> cmdlet 的權限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="48fdf-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsExUMConnectivity</strong> cmdlet.</span></span> <span data-ttu-id="48fdf-111">若要查看可以使用此 cmdlet 的所有 RBAC 角色的清單，請在 Windows PowerShell 命令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="48fdf-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="48fdf-112">描述</span><span class="sxs-lookup"><span data-stu-id="48fdf-112">Description</span></span>

<span data-ttu-id="48fdf-113">**Test-csexumconnectivity** cmdlet 會驗證指定的使用者可以連線至 Microsoft Exchange Server 2013 整合通訊服務。</span><span class="sxs-lookup"><span data-stu-id="48fdf-113">The **Test-CsExUMConnectivity** cmdlet verifies that the specified user can connect to the Microsoft Exchange Server 2013 unified messaging service.</span></span> <span data-ttu-id="48fdf-114">請注意，此 cmdlet 只會驗證，可以連線至服務。</span><span class="sxs-lookup"><span data-stu-id="48fdf-114">Note that this cmdlet only verifies that a connection can be made to the service.</span></span> <span data-ttu-id="48fdf-115">它不會測試服務本身。</span><span class="sxs-lookup"><span data-stu-id="48fdf-115">It does not test the service itself.</span></span> <span data-ttu-id="48fdf-116">若要測試整合通訊服務 （藉由執行實際使用者的信箱中留下語音郵件訊息綜合交易 cmdlet） 使用 Test-csexumvoicemail cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48fdf-116">To test the unified messaging service (by running a synthetic transaction cmdlet that actually leaves a voice mail message in a user's mailbox) use the Test-CsExUMVoiceMail cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="48fdf-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="48fdf-117">Running the test</span></span>

<span data-ttu-id="48fdf-118">下列範例會測試 Exchange 整合通訊連線集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="48fdf-118">The following example tests Exchange Unified Messaging connectivity for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="48fdf-119">這個命令將會執行只有當測試使用者所定義的集區 atl-cs-001.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="48fdf-119">This command will work only if test users were defined for the pool atl-cs-001.litwareinc.com.</span></span> <span data-ttu-id="48fdf-120">如果他們有此命令會判斷第一個測試使用者是否可以連線至整合通訊。</span><span class="sxs-lookup"><span data-stu-id="48fdf-120">If they have, then the command will determine whether the first test user can connect to Unified Messaging.</span></span> <span data-ttu-id="48fdf-121">如果未設定之集區的測試使用者命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="48fdf-121">If test users were not configured for the pool then the command will fail.</span></span>

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

<span data-ttu-id="48fdf-122">下列範例會測試 Exchange Unified Messaging 連線使用者 litwareinc 所示的命令\\kenmyer。</span><span class="sxs-lookup"><span data-stu-id="48fdf-122">The commands shown in the following example test Exchange Unified Messaging connectivity for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="48fdf-123">若要這麼做，在範例中的第一個命令會使用**Get-credential**指令程式來建立使用者 litwareinc 所需的 Windows PowerShell 命令列介面認證物件\\kenmyer。</span><span class="sxs-lookup"><span data-stu-id="48fdf-123">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="48fdf-124">請注意，您必須提供建立有效的認證物件和，以確保**Test-csexumconnectivity** cmdlet 可以執行其檢查此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="48fdf-124">Note that you must supply the password for this account to create a valid credentials object and to ensure that the **Test-CsExUMConnectivity** cmdlet can run its check.</span></span>

<span data-ttu-id="48fdf-125">此範例中的第二個命令使用提供的認證物件 ($x) 和的 SIP 位址的使用者 litwareinc\\kenmyer 來決定是否或這個使用者可以連線至 Exchange 整合通訊。</span><span class="sxs-lookup"><span data-stu-id="48fdf-125">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether or this user can connect to Exchange Unified Messaging.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="48fdf-126">在下一個範例中所示的命令是命令的如上所示的變化。</span><span class="sxs-lookup"><span data-stu-id="48fdf-126">The command shown in the next example is a variation of the command just shown.</span></span> <span data-ttu-id="48fdf-127">在此情況下，之後包含 OutLoggerVariable 參數會包含產生的成功或失敗的每個這些步驟即可**Test-csexumconnectivity** cmdletand 每個步驟的詳細資訊記錄。</span><span class="sxs-lookup"><span data-stu-id="48fdf-127">In this case, the OutLoggerVariable parameter is included to generate a detailed log of every step done by the **Test-CsExUMConnectivity** cmdletand the success or failure of each of those steps.</span></span> <span data-ttu-id="48fdf-128">若要這麼做，之後包含 OutLoggerVariable 參數會新增搭配參數值 ExumText;會導致儲存在名為 $ExumTest 變數的詳細的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="48fdf-128">To do this, the OutLoggerVariable parameter is added together with the parameter value ExumText; that causes detailed logging information to be stored in a variable named $ExumTest.</span></span> <span data-ttu-id="48fdf-129">在範例中的最後一個命令，在 toxml （） 方法用於將轉換成 XML 格式的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="48fdf-129">In the final command in the example, the ToXML() method is used to convert the log information to XML format.</span></span> <span data-ttu-id="48fdf-130">XML 資料然後寫入名為 c: 檔案\\記錄\\使用 ExumTest.xml Out-file cmdlet。</span><span class="sxs-lookup"><span data-stu-id="48fdf-130">That XML data is then written to a file that is named C:\\Logs\\ExumTest.xml by using the Out-File cmdlet.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="48fdf-131">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="48fdf-131">Determining success or failure</span></span>

<span data-ttu-id="48fdf-132">如果已正確設定 Exchange 整合，您會收到類似，具有標示為 [**成功**結果屬性的輸出：</span><span class="sxs-lookup"><span data-stu-id="48fdf-132">If Exchange integration is correctly configured, you'll receive output similar to this, with the Result property marked as **Success**:</span></span>

<span data-ttu-id="48fdf-133">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="48fdf-133">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="48fdf-134">結果： 成功</span><span class="sxs-lookup"><span data-stu-id="48fdf-134">Result : Success</span></span>

<span data-ttu-id="48fdf-135">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="48fdf-135">Latency : 00:00:00</span></span>

<span data-ttu-id="48fdf-136">錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="48fdf-136">Error Message :</span></span>

<span data-ttu-id="48fdf-137">診斷：</span><span class="sxs-lookup"><span data-stu-id="48fdf-137">Diagnosis :</span></span>

<span data-ttu-id="48fdf-138">如果指定的使用者無法收到通知，結果會顯示為**失敗**，及其他資訊會記錄在 [錯誤] 和 [診斷屬性：</span><span class="sxs-lookup"><span data-stu-id="48fdf-138">If the specified user can't receive notifications, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="48fdf-139">目標 Fqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="48fdf-139">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="48fdf-140">結果： 失敗</span><span class="sxs-lookup"><span data-stu-id="48fdf-140">Result : Failure</span></span>

<span data-ttu-id="48fdf-141">延遲： 00:00:00</span><span class="sxs-lookup"><span data-stu-id="48fdf-141">Latency : 00:00:00</span></span>

<span data-ttu-id="48fdf-142">錯誤訊息： 10060 的連線嘗試失敗，因為連線對象</span><span class="sxs-lookup"><span data-stu-id="48fdf-142">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="48fdf-143">正常後沒有回應一段時間，或</span><span class="sxs-lookup"><span data-stu-id="48fdf-143">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="48fdf-144">已建立的連線失敗，因為已連線的主機</span><span class="sxs-lookup"><span data-stu-id="48fdf-144">established connection failed because connected host has</span></span>

<span data-ttu-id="48fdf-145">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="48fdf-145">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="48fdf-146">內部的例外狀況： 的連線嘗試失敗，因為</span><span class="sxs-lookup"><span data-stu-id="48fdf-146">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="48fdf-147">連線對象正確後沒有回應一段</span><span class="sxs-lookup"><span data-stu-id="48fdf-147">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="48fdf-148">時間，或已建立的連線失敗，因為連線的主機</span><span class="sxs-lookup"><span data-stu-id="48fdf-148">time, or established connection failed because connected host</span></span>

<span data-ttu-id="48fdf-149">失敗回應 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="48fdf-149">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="48fdf-150">診斷：</span><span class="sxs-lookup"><span data-stu-id="48fdf-150">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="48fdf-151">測試可能有為何失敗的原因</span><span class="sxs-lookup"><span data-stu-id="48fdf-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="48fdf-152">以下是一些常見的原因為何**Test-csexumconnectivity**可能會失敗：</span><span class="sxs-lookup"><span data-stu-id="48fdf-152">Here are some common reasons why **Test-CsExUMConnectivity** might fail:</span></span>

  - <span data-ttu-id="48fdf-153">提供不正確的參數值。</span><span class="sxs-lookup"><span data-stu-id="48fdf-153">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="48fdf-154">如果使用，必須正確設定選用的參數或測試將會失敗。</span><span class="sxs-lookup"><span data-stu-id="48fdf-154">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="48fdf-155">重新執行此命令不含選擇性參數，並查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="48fdf-155">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="48fdf-156">如果設定錯誤或尚未部署 Exchange 伺服器，此命令將會失敗。</span><span class="sxs-lookup"><span data-stu-id="48fdf-156">This command will fail if the Exchange Server is misconfigured or not yet deployed.</span></span>

  - <span data-ttu-id="48fdf-157">如果 Exchange 伺服器不是連線到您網路上，此命令會失敗。</span><span class="sxs-lookup"><span data-stu-id="48fdf-157">This command will fail if the Exchange Server is not reachable over your network.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48fdf-158">另請參閱</span><span class="sxs-lookup"><span data-stu-id="48fdf-158">See Also</span></span>


[<span data-ttu-id="48fdf-159">Test-csexumvoicemail</span><span class="sxs-lookup"><span data-stu-id="48fdf-159">Test-CsExUMVoiceMail</span></span>](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

