---
title: Lync Server 2013：測試推播通知至智慧手機
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="f8af3-102">在 Lync Server 2013 中測試推播通知至智慧型電話</span><span class="sxs-lookup"><span data-stu-id="f8af3-102">Test push notifications to smart phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8af3-103">_**主題上次修改日期：** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="f8af3-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f8af3-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="f8af3-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="f8af3-105">次</span><span class="sxs-lookup"><span data-stu-id="f8af3-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f8af3-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="f8af3-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="f8af3-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f8af3-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f8af3-108">需要許可權</span><span class="sxs-lookup"><span data-stu-id="f8af3-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="f8af3-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="f8af3-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="f8af3-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxPushNotification Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="f8af3-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="f8af3-111">若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f8af3-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="f8af3-112">描述</span><span class="sxs-lookup"><span data-stu-id="f8af3-112">Description</span></span>

<span data-ttu-id="f8af3-113">推播通知服務（Apple 推播通知服務和 Microsoft 推播通知服務）可以傳送事件通知（例如新的立即訊息或新的語音信箱）至行動裝置（例如 Iphone 和 Windows phone），即使 Lync 用戶端在這些裝置上，目前已暫停或在背景中執行。</span><span class="sxs-lookup"><span data-stu-id="f8af3-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="f8af3-114">推播通知服務是在 Microsoft 伺服器上執行的雲端服務。</span><span class="sxs-lookup"><span data-stu-id="f8af3-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="f8af3-115">若要利用推播通知，您必須能夠連線到並透過推播通知 clearinghouse 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="f8af3-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="f8af3-116">CsMcxPushNotification Cmdlet 可讓系統管理員確認推播通知要求可以透過邊緣伺服器路由至推播通知 clearinghouse。</span><span class="sxs-lookup"><span data-stu-id="f8af3-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="f8af3-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="f8af3-117">Running the test</span></span>

<span data-ttu-id="f8af3-118">若要測試推播通知服務，請呼叫 CsMcxPushNotification Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8af3-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="f8af3-119">請確定您指定的是 Edge 伺服器的完整功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="f8af3-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="f8af3-120">如需詳細資訊，請參閱[Test CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f8af3-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="f8af3-121">判斷成功或失敗</span><span class="sxs-lookup"><span data-stu-id="f8af3-121">Determining success or failure</span></span>

<span data-ttu-id="f8af3-122">如果 Test CsMcxPushNotification 成功，則 Cmdlet 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="f8af3-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="f8af3-123">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="f8af3-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="f8af3-124">結果：成功</span><span class="sxs-lookup"><span data-stu-id="f8af3-124">Result : Success</span></span>

<span data-ttu-id="f8af3-125">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="f8af3-125">Latency : 00:00:00</span></span>

<span data-ttu-id="f8af3-126">出錯</span><span class="sxs-lookup"><span data-stu-id="f8af3-126">Error :</span></span>

<span data-ttu-id="f8af3-127">自檢</span><span class="sxs-lookup"><span data-stu-id="f8af3-127">Diagnosis :</span></span>

<span data-ttu-id="f8af3-128">如果測試 CsMcxPushNotification 無法連線到推播通知，則 Cmdlet 通常不會傳回失敗的測試結果。</span><span class="sxs-lookup"><span data-stu-id="f8af3-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="f8af3-129">相反，命令通常會完全失敗。</span><span class="sxs-lookup"><span data-stu-id="f8af3-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="f8af3-130">例如：</span><span class="sxs-lookup"><span data-stu-id="f8af3-130">For example:</span></span>

<span data-ttu-id="f8af3-131">CsMcxPushNotification：從網路收到504（伺服器超時）回應，且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="f8af3-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="f8af3-132">如需詳細資訊，請參閱例外狀況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f8af3-132">See the exception details for more information.</span></span>

<span data-ttu-id="f8af3-133">在第一行：1個字元：27</span><span class="sxs-lookup"><span data-stu-id="f8af3-133">At line:1 char:27</span></span>

<span data-ttu-id="f8af3-134">\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="f8af3-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="f8af3-135">\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]，FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="f8af3-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="f8af3-136">\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="f8af3-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="f8af3-137">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="f8af3-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="f8af3-138">如果推播通知服務無法正常顯示與邊緣伺服器通訊的問題，或與推播通知結算所進行通訊的問題。</span><span class="sxs-lookup"><span data-stu-id="f8af3-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="f8af3-139">如果您在執行 Test CsMcxPushNotification 時遇到問題，您應該執行的第一件事就是確認您的 Edge 伺服器正常運作。</span><span class="sxs-lookup"><span data-stu-id="f8af3-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="f8af3-140">其中一種方法是使用 Test CsAVEdgeConnectivity Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f8af3-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="f8af3-141">這種檢查會驗證指定的使用者是否可以連線到 Edge 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f8af3-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="f8af3-142">如果邊緣伺服器看起來正常運作，這通常表示您無法連線到推播通知 clearinghouse。</span><span class="sxs-lookup"><span data-stu-id="f8af3-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="f8af3-143">然後，這通常表示您尚未正確設定 clearinghouse URI，或是您沒有指向此 URL 的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="f8af3-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="f8af3-144">您可以執行此命令，以確認 URI 已設定為正確的值（sip:push@push.lync.com）：</span><span class="sxs-lookup"><span data-stu-id="f8af3-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="f8af3-145">如果 PushNotificationProxyUri 屬性是設定為 sip:push@push.lync.com 以外的任何專案，您可以使用 McxConfiguration Cmdlet 來修正該問題。</span><span class="sxs-lookup"><span data-stu-id="f8af3-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="f8af3-146">例如，這個命令會在整個組織中正確設定 URI：</span><span class="sxs-lookup"><span data-stu-id="f8af3-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="f8af3-147">如需詳細資訊，請參閱[CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f8af3-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="f8af3-148">如果 URI 設定正確，下一個步驟應該是確認您有解析到 SIP 網域和 Edge 伺服器的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="f8af3-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="f8af3-149">如需有關如何設定這些記錄的詳細資訊，請參閱行動性的協助主題 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="f8af3-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="f8af3-150">請注意，下列錯誤訊息通常表示 DNS 記錄的問題：</span><span class="sxs-lookup"><span data-stu-id="f8af3-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="f8af3-151">從網路收到504（伺服器超時）回應，且操作失敗。</span><span class="sxs-lookup"><span data-stu-id="f8af3-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="f8af3-152">如需詳細資訊，請參閱例外狀況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f8af3-152">See the exception details for more information.</span></span>

<span data-ttu-id="f8af3-153">測試 CsMcxConfiguration 也可能會失敗，並出現以下錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="f8af3-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="f8af3-154">Test-CsMcxPushNotification：推播通知要求遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="f8af3-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="f8af3-155">在第一行：1個字元：27</span><span class="sxs-lookup"><span data-stu-id="f8af3-155">At line:1 char:27</span></span>

<span data-ttu-id="f8af3-156">\+Test-CsMcxPushNotification\<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="f8af3-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="f8af3-157">\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]，SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="f8af3-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="f8af3-158">\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions. TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="f8af3-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="f8af3-159">如果您已啟用 URL 篩選並封鎖 HTTP：及 HTTPs：首碼，通常會發生 [推播通知要求] 訊息。</span><span class="sxs-lookup"><span data-stu-id="f8af3-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="f8af3-160">您可以使用類似下列的命令來判斷要封鎖哪些首碼：</span><span class="sxs-lookup"><span data-stu-id="f8af3-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="f8af3-161">如果 [HTTP：] 或 [HTTPs：] 出現在結果中，您必須從 [封鎖的首碼] 清單中移除，推播通知才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="f8af3-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="f8af3-162">您可以使用類似以下的命令來完成：</span><span class="sxs-lookup"><span data-stu-id="f8af3-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="f8af3-163">如需詳細資訊，請參閱[CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="f8af3-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

