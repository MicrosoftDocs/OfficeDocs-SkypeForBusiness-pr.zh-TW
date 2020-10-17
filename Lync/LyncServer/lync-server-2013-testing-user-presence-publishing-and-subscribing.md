---
title: Lync Server 2013：測試使用者目前狀態發佈和訂閱
description: Lync Server 2013：測試使用者目前狀態發佈和訂閱。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90913f270fbd034ca4d2ea7cf3b93c255fc95c66
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541849"
---
# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a><span data-ttu-id="4a008-103">在 Lync Server 2013 中測試使用者的狀態發佈和訂閱</span><span class="sxs-lookup"><span data-stu-id="4a008-103">Testing user presence publishing and subscribing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a008-104">_**主題上次修改日期：** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="4a008-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a008-105">驗證排程</span><span class="sxs-lookup"><span data-stu-id="4a008-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="4a008-106">每日</span><span class="sxs-lookup"><span data-stu-id="4a008-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a008-107">測試控管</span><span class="sxs-lookup"><span data-stu-id="4a008-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="4a008-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a008-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a008-109">必要的權限</span><span class="sxs-lookup"><span data-stu-id="4a008-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="4a008-110">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="4a008-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="4a008-111">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsPresence Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4a008-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPresence cmdlet.</span></span> <span data-ttu-id="4a008-112">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4a008-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="4a008-113">描述</span><span class="sxs-lookup"><span data-stu-id="4a008-113">Description</span></span>

<span data-ttu-id="4a008-114">Test-CsPresence 是用來判斷一組測試使用者是否可以登入 Lync Server，然後再 exchange 顯示狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="4a008-114">Test-CsPresence is used to determine whether a pair of test users can log on to Lync Server and then exchange presence information.</span></span> <span data-ttu-id="4a008-115">為達此目的，此 Cmdlet 會先將兩個使用者登入系統。</span><span class="sxs-lookup"><span data-stu-id="4a008-115">To do this, the cmdlet first logs the two users on to the system.</span></span> <span data-ttu-id="4a008-116">如果兩者都登入成功，則第一個測試使用者會要求接收第二個使用者的目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="4a008-116">If both logons succeed, the first test user then asks to receive presence information from the second user.</span></span> <span data-ttu-id="4a008-117">第二個使用者會發行此資訊，而 Test-CsPresence 會驗證該資訊已成功傳輸給第一個使用者。</span><span class="sxs-lookup"><span data-stu-id="4a008-117">The second user publishes this information, and Test-CsPresence verifies that the information was successfully transmitted to the first user.</span></span> <span data-ttu-id="4a008-118">在 exchange 顯示狀態資訊之後，這兩個測試使用者便會從 Lync Server 登出。</span><span class="sxs-lookup"><span data-stu-id="4a008-118">After the exchange of presence information, the two test users are then logged off from Lync Server.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="4a008-119">執行測試</span><span class="sxs-lookup"><span data-stu-id="4a008-119">Running the test</span></span>

<span data-ttu-id="4a008-120">您可以使用一對預先設定的測試帳戶來執行 Test-CsPresence Cmdlet (請參閱設定測試帳戶以執行 Lync Server 測試) 或任何兩個已啟用 Lync Server 之使用者的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4a008-120">The Test-CsPresence cmdlet can be run using either a pair of preconfigured test accounts (see Setting Up Test Accounts for Running Lync Server Tests) or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="4a008-121">若要使用測試帳戶執行此檢查，您只需要指定所測試之 Lync Server 集區的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4a008-121">To run this check using test accounts, you just have to specify the FQDN of the Lync Server pool being tested.</span></span> <span data-ttu-id="4a008-122">例如：</span><span class="sxs-lookup"><span data-stu-id="4a008-122">For example:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="4a008-123">若要使用實際使用者帳戶執行這項檢查，您必須建立兩個 Windows PowerShell 認證物件 (包含每個帳戶之帳戶名稱和密碼) 的物件。</span><span class="sxs-lookup"><span data-stu-id="4a008-123">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="4a008-124">當您呼叫 Test-CsPresence 時，您必須包含這兩個帳戶的認證物件和 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="4a008-124">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsPresence:</span></span>

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

<span data-ttu-id="4a008-125">如需詳細資訊，請參閱 [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) Cmdlet 的說明文件。</span><span class="sxs-lookup"><span data-stu-id="4a008-125">For more information, see the Help documentation for the [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="4a008-126">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="4a008-126">Determining success or failure</span></span>

<span data-ttu-id="4a008-127">如果指定的使用者可以交換顯示狀態資訊，則會收到類似以下的輸出，其 Result 屬性標示為 [ **成功]：**</span><span class="sxs-lookup"><span data-stu-id="4a008-127">If the specified users can exchange presence information, then you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="4a008-128">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4a008-128">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4a008-129">結果：成功</span><span class="sxs-lookup"><span data-stu-id="4a008-129">Result : Success</span></span>

<span data-ttu-id="4a008-130">延遲：00：00：06.3280315</span><span class="sxs-lookup"><span data-stu-id="4a008-130">Latency : 00:00:06.3280315</span></span>

<span data-ttu-id="4a008-131">錯誤：</span><span class="sxs-lookup"><span data-stu-id="4a008-131">Error :</span></span>

<span data-ttu-id="4a008-132">診斷：</span><span class="sxs-lookup"><span data-stu-id="4a008-132">Diagnosis :</span></span>

<span data-ttu-id="4a008-133">如果兩位使用者無法交換顯示狀態資訊，則結果會顯示為 [失敗]，而且會在 [錯誤] 和 [診斷] 屬性中記錄其他資訊：</span><span class="sxs-lookup"><span data-stu-id="4a008-133">If the two users can't exchange presence information, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="4a008-134">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="4a008-134">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="4a008-135">結果：失敗</span><span class="sxs-lookup"><span data-stu-id="4a008-135">Result : Failure</span></span>

<span data-ttu-id="4a008-136">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="4a008-136">Latency : 00:00:00</span></span>

<span data-ttu-id="4a008-137">錯誤：404，未找到</span><span class="sxs-lookup"><span data-stu-id="4a008-137">Error : 404, Not Found</span></span>

<span data-ttu-id="4a008-138">診斷： ErrorCode = 4005、Source = atl-cs-001.litwareinc.com、</span><span class="sxs-lookup"><span data-stu-id="4a008-138">Diagnosis : ErrorCode=4005,Source=atl-cs-001.litwareinc.com,</span></span>

<span data-ttu-id="4a008-139">原因 = 未啟用 SIP 的目的 URI 或不是</span><span class="sxs-lookup"><span data-stu-id="4a008-139">Reason=Destination URI either not enabled for SIP or does not</span></span>

<span data-ttu-id="4a008-140">存在。</span><span class="sxs-lookup"><span data-stu-id="4a008-140">exist.</span></span>

<span data-ttu-id="4a008-141">DiagnosticHeader。</span><span class="sxs-lookup"><span data-stu-id="4a008-141">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="4a008-142">例如，由於至少有兩個使用者帳戶的其中一個無效，所以先前的輸出會指出測試失敗：帳戶不存在，或尚未對 Lync Server 啟用。</span><span class="sxs-lookup"><span data-stu-id="4a008-142">For example, the previous output states that the test failed because at least one of the two user accounts is not valid: either the account does not exist or it has not been enabled for Lync Server.</span></span> <span data-ttu-id="4a008-143">您可以執行類似如下的命令，確認帳戶是否存在，並判斷是否已啟用 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="4a008-143">You can verify that the accounts exist, and determine whether they are enabled for Lync Server, by running a command similar to this:</span></span>

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

<span data-ttu-id="4a008-144">如果 Test-CsPresence 失敗，則您可能想要重新執行測試，這次包括 Verbose 參數：</span><span class="sxs-lookup"><span data-stu-id="4a008-144">If Test-CsPresence fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

<span data-ttu-id="4a008-145">包含 Verbose 參數時，Test-CsPresence 會傳回每個動作的逐步帳戶，檢查所嘗試的每一項動作時，檢查指定的使用者登入 Lync 伺服器的能力。</span><span class="sxs-lookup"><span data-stu-id="4a008-145">When the Verbose parameter is included, Test-CsPresence will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="4a008-146">例如：</span><span class="sxs-lookup"><span data-stu-id="4a008-146">For example:</span></span>

<span data-ttu-id="4a008-147">註冊要求命中不明</span><span class="sxs-lookup"><span data-stu-id="4a008-147">Registration Request hit against Unknown</span></span>

<span data-ttu-id="4a008-148">' Register ' activity 在 ' 0.0345791 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="4a008-148">'Register' activity completed in '0.0345791' secs.</span></span>

<span data-ttu-id="4a008-149">' SelfSubscribeActivity ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="4a008-149">'SelfSubscribeActivity' activity started.</span></span>

<span data-ttu-id="4a008-150">' SelfSubscribeActivity ' activity 在 ' 0.0041174 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="4a008-150">'SelfSubscribeActivity' activity completed in '0.0041174' secs.</span></span>

<span data-ttu-id="4a008-151">' SubscribePresence ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="4a008-151">'SubscribePresence' activity started.</span></span>

<span data-ttu-id="4a008-152">' SubscribePresence ' activity 在 ' 0.0038764 ' 秒內完成。</span><span class="sxs-lookup"><span data-stu-id="4a008-152">'SubscribePresence' activity completed in '0.0038764' secs.</span></span>

<span data-ttu-id="4a008-153">' PublishPresence ' 活動已開始。</span><span class="sxs-lookup"><span data-stu-id="4a008-153">'PublishPresence' activity started.</span></span>

<span data-ttu-id="4a008-154">在25秒內未收到例外狀況通知。 '</span><span class="sxs-lookup"><span data-stu-id="4a008-154">An exception 'Presence notification is not received within 25 secs.'</span></span> <span data-ttu-id="4a008-155">發生 ruing 工作流程 STPresenceWorkflow 執行 SyntheticTransactions。</span><span class="sxs-lookup"><span data-stu-id="4a008-155">occurred ruing Workflow Microsoft.Rtc.SyntheticTransactions.Workflows.STPresenceWorkflow execution.</span></span>

<span data-ttu-id="4a008-156">在25秒內未收到目前狀態通知這一事實可能表示網路問題阻礙交換資訊。</span><span class="sxs-lookup"><span data-stu-id="4a008-156">The fact that the presence notification was not received within 25 seconds might indicate that network issues are preventing information from being exchanged.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="4a008-157">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="4a008-157">Reasons why the test might have failed</span></span>

<span data-ttu-id="4a008-158">以下是一些 Test-CsPresence 可能失敗的常見原因：</span><span class="sxs-lookup"><span data-stu-id="4a008-158">Here are some common reasons why Test-CsPresence might fail:</span></span>

  - <span data-ttu-id="4a008-159">您指定了錯誤的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="4a008-159">You specified an incorrect user account.</span></span> <span data-ttu-id="4a008-160">您可以執行類似如下的命令，以確認使用者帳戶是否存在：</span><span class="sxs-lookup"><span data-stu-id="4a008-160">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="4a008-161">使用者帳戶有效，但目前未啟用 Lync Server 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="4a008-161">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="4a008-162">若要確認是否已為 Lync Server 啟用使用者帳戶，請執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="4a008-162">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="4a008-163">如果 Enabled 屬性設定為 False，表示目前未啟用 Lync Server 的使用者。</span><span class="sxs-lookup"><span data-stu-id="4a008-163">If the Enabled property is set to False that means that the user is currently not enabled for Lync Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

