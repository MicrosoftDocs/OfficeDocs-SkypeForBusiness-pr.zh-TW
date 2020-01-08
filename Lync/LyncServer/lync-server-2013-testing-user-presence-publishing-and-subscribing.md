---
title: Lync Server 2013：測試使用者目前狀態發佈及訂閱
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17c7052550067868ff201c809a51e1d119c5f8a1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982442"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="2f178-102">在 Lync Server 2013 中測試使用者目前狀態發佈及訂閱</span><span class="sxs-lookup"><span data-stu-id="2f178-102">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2f178-103">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="2f178-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2f178-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="2f178-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="2f178-105">日常</span><span class="sxs-lookup"><span data-stu-id="2f178-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2f178-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="2f178-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="2f178-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f178-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2f178-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="2f178-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="2f178-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f178-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="2f178-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsPresence Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="2f178-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="2f178-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2f178-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="2f178-112">描述</span><span class="sxs-lookup"><span data-stu-id="2f178-112">Description</span></span>

<span data-ttu-id="2f178-113">Test-CsPresence 是用來判斷一組測試使用者是否可以登入 Lync Server，以及 exchange 目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="2f178-113">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="2f178-114">若要這樣做，此 Cmdlet 會先將兩位使用者記錄在系統上。</span><span class="sxs-lookup"><span data-stu-id="2f178-114">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="2f178-115">如果兩個登錄都成功，第一個測試使用者就會要求接收來自第二個使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="2f178-115">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="2f178-116">第二個使用者發佈此資訊，而測試 CsPresence 驗證資訊已順利傳送給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="2f178-116">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="2f178-117">在交換目前狀態資訊之後，兩個測試使用者就會從 Lync Server 登入。</span><span class="sxs-lookup"><span data-stu-id="2f178-117">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="2f178-118">執行測試</span><span class="sxs-lookup"><span data-stu-id="2f178-118">Running the test</span></span>

<span data-ttu-id="2f178-119">CsPresence Cmdlet 可以使用一組預先配置的測試帳戶（請參閱設定執行 Lync Server 測試的測試帳戶），或是任何已啟用 Lync Server 的任何兩個使用者的帳戶執行。</span><span class="sxs-lookup"><span data-stu-id="2f178-119">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="2f178-120">若要使用測試帳戶執行此檢查，您只需指定要測試的 Lync 伺服器池的 FQDN 即可。</span><span class="sxs-lookup"><span data-stu-id="2f178-120">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="2f178-121">例如：</span><span class="sxs-lookup"><span data-stu-id="2f178-121">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="2f178-122">若要使用實際的使用者帳戶執行這項檢查，您必須為每個帳戶建立兩個 Windows PowerShell 認證物件（包含帳戶名稱和密碼的物件）。</span><span class="sxs-lookup"><span data-stu-id="2f178-122">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="2f178-123">當您呼叫 Test CsPresence 時，您必須包含這些認證物件和兩個帳戶的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="2f178-123">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="2f178-124">如需詳細資訊，請參閱[Test CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="2f178-124">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2f178-125">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="2f178-125">Determining success or failure</span></span>

<span data-ttu-id="2f178-126">如果指定的使用者可以交換目前狀態資訊，您將會收到與此類似的輸出，結果屬性標示為**成功：**</span><span class="sxs-lookup"><span data-stu-id="2f178-126">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="2f178-127">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f178-127">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2f178-128">結果：成功</span><span class="sxs-lookup"><span data-stu-id="2f178-128">Result : Success</span></span>

<span data-ttu-id="2f178-129">延隔時間：00：00：06.3280315</span><span class="sxs-lookup"><span data-stu-id="2f178-129">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="2f178-130">出錯</span><span class="sxs-lookup"><span data-stu-id="2f178-130">Error :</span></span>

<span data-ttu-id="2f178-131">自檢</span><span class="sxs-lookup"><span data-stu-id="2f178-131">Diagnosis :</span></span>

<span data-ttu-id="2f178-132">如果兩個使用者無法交換目前狀態資訊，則會將結果顯示為失敗，而且會在錯誤與診斷屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="2f178-132">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="2f178-133">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="2f178-133">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="2f178-134">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="2f178-134">Result : Failure</span></span>

<span data-ttu-id="2f178-135">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="2f178-135">Latency : 00:00:00</span></span>

<span data-ttu-id="2f178-136">錯誤：404，找不到</span><span class="sxs-lookup"><span data-stu-id="2f178-136">Error : 404, Not Found</span></span>

<span data-ttu-id="2f178-137">診斷： ErrorCode = 4005，Source = atl-cs-001.litwareinc.com，</span><span class="sxs-lookup"><span data-stu-id="2f178-137">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="2f178-138">原因 = 無法針對 SIP 啟用目的 URI，或無法</span><span class="sxs-lookup"><span data-stu-id="2f178-138">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="2f178-139">有.</span><span class="sxs-lookup"><span data-stu-id="2f178-139">exist.</span></span>

<span data-ttu-id="2f178-140">DiagnosticHeader 中的 [Rtc]</span><span class="sxs-lookup"><span data-stu-id="2f178-140">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="2f178-141">例如，先前的輸出指出，因為兩個使用者帳戶中至少有一個帳戶無效，所以測試失敗：帳戶不存在，或尚未啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="2f178-141">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="2f178-142">您可以執行如下所示的命令，確認帳戶存在，並判斷是否已啟用 Lync Server：</span><span class="sxs-lookup"><span data-stu-id="2f178-142">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="2f178-143">如果測試 CsPresence 失敗，您可能會想要重新執行測試，這次包括詳細參數：</span><span class="sxs-lookup"><span data-stu-id="2f178-143">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="2f178-144">包含詳細參數時，當您檢查指定的使用者是否已登入 Lync Server 的功能時，測試 CsPresence 會傳回其嘗試的每個動作的逐步帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f178-144">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="2f178-145">例如：</span><span class="sxs-lookup"><span data-stu-id="2f178-145">For example:</span></span>

<span data-ttu-id="2f178-146">針對未知的註冊要求</span><span class="sxs-lookup"><span data-stu-id="2f178-146">Registration Request hit against Unknown</span></span>

<span data-ttu-id="2f178-147">"Register" 活動在 "0.0345791" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="2f178-147">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="2f178-148">「SelfSubscribeActivity」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="2f178-148">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="2f178-149">"SelfSubscribeActivity" 活動在 "0.0041174" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="2f178-149">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="2f178-150">「SubscribePresence」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="2f178-150">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="2f178-151">"SubscribePresence" 活動在 "0.0038764" 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="2f178-151">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="2f178-152">「PublishPresence」活動已開始。</span><span class="sxs-lookup"><span data-stu-id="2f178-152">'PublishPresence' activity started.</span></span>

<span data-ttu-id="2f178-153">在25秒內未收到例外狀況通知。</span><span class="sxs-lookup"><span data-stu-id="2f178-153">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="2f178-154">ruing 工作流程 SyntheticTransactions. STPresenceWorkflow 執行。</span><span class="sxs-lookup"><span data-stu-id="2f178-154">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="2f178-155">在25秒內沒有收到目前狀態通知的事實，可能表示網路問題無法與資訊交換。</span><span class="sxs-lookup"><span data-stu-id="2f178-155">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2f178-156">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="2f178-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="2f178-157">以下是測試 CsPresence 可能失敗的一些常見原因：</span><span class="sxs-lookup"><span data-stu-id="2f178-157">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="2f178-158">您指定的使用者帳戶不正確。</span><span class="sxs-lookup"><span data-stu-id="2f178-158">You specified an incorrect user account.</span></span> <span data-ttu-id="2f178-159">您可以執行如下的命令來確認使用者帳戶已存在：</span><span class="sxs-lookup"><span data-stu-id="2f178-159">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="2f178-160">使用者帳戶有效，但目前尚未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f178-160">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="2f178-161">若要確認已啟用 Lync Server 的使用者帳戶，請執行如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="2f178-161">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="2f178-162">如果 Enabled 屬性設為 False，表示目前尚未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="2f178-162">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

