---
title: Lync Server 2013：測試推播通知至智慧型電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0e8d6198fc022c03e69e68475d77f513d577ad4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519200"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a><span data-ttu-id="15e53-102">在 Lync Server 2013 中測試向智慧型電話的推播通知</span><span class="sxs-lookup"><span data-stu-id="15e53-102">Test push notifications to smart phones in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15e53-103">_**主題上次修改日期：** 2017-03-15_</span><span class="sxs-lookup"><span data-stu-id="15e53-103">_**Topic Last Modified:** 2017-03-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15e53-104">驗證排程</span><span class="sxs-lookup"><span data-stu-id="15e53-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="15e53-105">每月</span><span class="sxs-lookup"><span data-stu-id="15e53-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15e53-106">測試控管</span><span class="sxs-lookup"><span data-stu-id="15e53-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="15e53-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15e53-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15e53-108">必要的權限</span><span class="sxs-lookup"><span data-stu-id="15e53-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="15e53-109">使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="15e53-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="15e53-110">使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsMcxPushNotification Cmdlet 許可權的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="15e53-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="15e53-111">若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="15e53-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="15e53-112">描述</span><span class="sxs-lookup"><span data-stu-id="15e53-112">Description</span></span>

<span data-ttu-id="15e53-113">推播通知服務 (Apple Push Notification Service 和 Microsoft 推播通知服務) 可以將有關事件的通知傳送給行動裝置（例如 Iphone 和 Windows phone），即使這些裝置上的 Lync 用戶端目前已暫停或在後臺執行，也是如此。</span><span class="sxs-lookup"><span data-stu-id="15e53-113">The push notification service (Apple Push Notification Service and Microsoft Push Notification Service) can send notifications about events such as new instant messages or new voice mail to mobile devices such as iPhones and Windows Phones, even if the Lync client on those devices is currently suspended or running in the background.</span></span> <span data-ttu-id="15e53-114">推播通知服務是在 Microsoft 伺服器上執行的雲端式服務。</span><span class="sxs-lookup"><span data-stu-id="15e53-114">The push notification service is a cloud-based service that is running on Microsoft servers.</span></span> <span data-ttu-id="15e53-115">為了利用推播通知，您必須能夠連線至推播通知，並透過此驗證。</span><span class="sxs-lookup"><span data-stu-id="15e53-115">In order to take advantage of push notifications, you must be able to connect to, and be authenticated by, the push notification clearinghouse.</span></span> <span data-ttu-id="15e53-116">Test-CsMcxPushNotification Cmdlet 可讓系統管理員確認推播要求可以透過 Edge server 路由傳送至推播通知 clearinghouse。</span><span class="sxs-lookup"><span data-stu-id="15e53-116">The Test-CsMcxPushNotification cmdlet enables administrators to verify that push notification requests can be routed through your Edge server to the push notification clearinghouse.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="15e53-117">執行測試</span><span class="sxs-lookup"><span data-stu-id="15e53-117">Running the test</span></span>

<span data-ttu-id="15e53-118">若要測試推播通知服務，請致電 Test-CsMcxPushNotification Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="15e53-118">To test the push notification service, call the Test-CsMcxPushNotification cmdlet.</span></span> <span data-ttu-id="15e53-119">請務必指定 Edge server 的完整功能變數名稱：</span><span class="sxs-lookup"><span data-stu-id="15e53-119">Make sure that you specify the fully qualified domain name of your Edge server:</span></span>

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

<span data-ttu-id="15e53-120">如需詳細資訊，請參閱 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="15e53-120">For more information, see the help topic for the [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="15e53-121">決定成功或失敗</span><span class="sxs-lookup"><span data-stu-id="15e53-121">Determining success or failure</span></span>

<span data-ttu-id="15e53-122">如果 Test-CsMcxPushNotification 成功，指令 Cmdlet 會傳回測試結果成功：</span><span class="sxs-lookup"><span data-stu-id="15e53-122">If Test-CsMcxPushNotification succeeds the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="15e53-123">TargetFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="15e53-123">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="15e53-124">結果：成功</span><span class="sxs-lookup"><span data-stu-id="15e53-124">Result : Success</span></span>

<span data-ttu-id="15e53-125">延遲：00:00:00</span><span class="sxs-lookup"><span data-stu-id="15e53-125">Latency : 00:00:00</span></span>

<span data-ttu-id="15e53-126">錯誤：</span><span class="sxs-lookup"><span data-stu-id="15e53-126">Error :</span></span>

<span data-ttu-id="15e53-127">診斷：</span><span class="sxs-lookup"><span data-stu-id="15e53-127">Diagnosis :</span></span>

<span data-ttu-id="15e53-128">如果 Test-CsMcxPushNotification 無法連接到推播通知，則 Cmdlet 通常不會傳回失敗的測試結果。</span><span class="sxs-lookup"><span data-stu-id="15e53-128">If Test-CsMcxPushNotification is unable to connect to the push notification clearinghouse the cmdlet will typically not return a test result of Failure.</span></span> <span data-ttu-id="15e53-129">相反的命令通常會完全失敗。</span><span class="sxs-lookup"><span data-stu-id="15e53-129">Instead the command will usually fail completely.</span></span> <span data-ttu-id="15e53-130">例如：</span><span class="sxs-lookup"><span data-stu-id="15e53-130">For example:</span></span>

<span data-ttu-id="15e53-131">Test-CsMcxPushNotification：從網路接收到 504 (伺服器超時的回應) 回應，但操作失敗。</span><span class="sxs-lookup"><span data-stu-id="15e53-131">Test-CsMcxPushNotification : A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="15e53-132">如需詳細資訊，請參閱例外狀況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="15e53-132">See the exception details for more information.</span></span>

<span data-ttu-id="15e53-133">線上：1個字元：27</span><span class="sxs-lookup"><span data-stu-id="15e53-133">At line:1 char:27</span></span>

<span data-ttu-id="15e53-134">\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com</span><span class="sxs-lookup"><span data-stu-id="15e53-134">\+ Test-CsMcxPushNotification \<\<\<\< -AccessEdgeFqdn lyncedge.mydomain.com</span></span>

<span data-ttu-id="15e53-135">\+ CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] ，FailureResponseException</span><span class="sxs-lookup"><span data-stu-id="15e53-135">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], FailureResponseException</span></span>

<span data-ttu-id="15e53-136">\+ FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions、TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="15e53-136">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="15e53-137">測試可能失敗的原因</span><span class="sxs-lookup"><span data-stu-id="15e53-137">Reasons why the test might have failed</span></span>

<span data-ttu-id="15e53-138">如果推播通知服務失敗，通常表示與 Edge server 通訊問題，或與推播通知結算所進行通訊的問題。</span><span class="sxs-lookup"><span data-stu-id="15e53-138">If the push notification service fails that usually indicates either problems communicating with your Edge server, or problems communicating with the Push Notification Clearing House.</span></span> <span data-ttu-id="15e53-139">如果您在執行 Test-CsMcxPushNotification 時遇到問題，您應該做的第一件事是驗證 Edge server 是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="15e53-139">If you encounter problems when you run Test-CsMcxPushNotification, the first thing that you should do is verify that your Edge server is working correctly.</span></span> <span data-ttu-id="15e53-140">使用 Test-CsAVEdgeConnectivity Cmdlet 的方法之一：</span><span class="sxs-lookup"><span data-stu-id="15e53-140">One way to do that is to use the Test-CsAVEdgeConnectivity cmdlet:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="15e53-141">這種檢查會驗證指定的使用者是否可以連接到 Edge server。</span><span class="sxs-lookup"><span data-stu-id="15e53-141">This check verifies that a specified user can connect to the Edge server.</span></span>

<span data-ttu-id="15e53-142">如果 Edge server 似乎運作正常，這通常表示您無法連線至推播通知 clearinghouse。</span><span class="sxs-lookup"><span data-stu-id="15e53-142">If the Edge server seems to be working correctly, that often means that you are unable to connect to the push notification clearinghouse.</span></span> <span data-ttu-id="15e53-143">反過來，這通常表示您沒有正確地設定 clearinghouse URI，或您沒有指向此 URL 的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="15e53-143">In turn, that typically means that you either have not configured the clearinghouse URI correctly or that you do not have a DNS SRV record that points to this URL.</span></span> <span data-ttu-id="15e53-144">您可以執行下列命令，確認 URI 已設定為正確的值 (sip:push@push.lync.com) ：</span><span class="sxs-lookup"><span data-stu-id="15e53-144">You can verify that the URI is set to the correct value (sip:push@push.lync.com) by running this command:</span></span>

    Get-CsMcxConfiguration

<span data-ttu-id="15e53-145">如果 PushNotificationProxyUri 屬性設定為 sip:push@push.lync.com 以外的任何專案，您可以使用 Set-McxConfiguration Cmdlet 修正該問題。</span><span class="sxs-lookup"><span data-stu-id="15e53-145">If the PushNotificationProxyUri property is set to anything other than sip:push@push.lync.com then you can correct that problem by using the Set-McxConfiguration cmdlet.</span></span> <span data-ttu-id="15e53-146">例如，此命令會正確地設定整個組織的 URI：</span><span class="sxs-lookup"><span data-stu-id="15e53-146">For example, this command correctly sets the URI throughout your organization:</span></span>

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

<span data-ttu-id="15e53-147">如需詳細資訊，請參閱 [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="15e53-147">For more information, see the help topic for the [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet.</span></span>

<span data-ttu-id="15e53-148">如果 URI 設定正確，下一個步驟應該是驗證您是否有解析為 SIP 網域和 Edge server 的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="15e53-148">If the URI is configured correctly, your next step should be to verify that you have a DNS SRV record that resolves to your SIP domain and your Edge server.</span></span> <span data-ttu-id="15e53-149">如需如何設定這些記錄的詳細資訊，請參閱協助主題行動的 DNS 需求。</span><span class="sxs-lookup"><span data-stu-id="15e53-149">For more information about how to configure these records, see the help topic DNS Requirements for Mobility.</span></span> <span data-ttu-id="15e53-150">請注意，下列錯誤訊息通常會指出 DNS 記錄的問題：</span><span class="sxs-lookup"><span data-stu-id="15e53-150">Note that the following error message usually indicates a problem with DNS records:</span></span>

<span data-ttu-id="15e53-151">從網路接收到 504 (伺服器超時) 回應，但作業失敗。</span><span class="sxs-lookup"><span data-stu-id="15e53-151">A 504 (Server time-out) response was received from the network and the operation failed.</span></span> <span data-ttu-id="15e53-152">如需詳細資訊，請參閱例外狀況詳細資料。</span><span class="sxs-lookup"><span data-stu-id="15e53-152">See the exception details for more information.</span></span>

<span data-ttu-id="15e53-153">您也可以使用此錯誤訊息 Test-CsMcxConfiguration 會失敗：</span><span class="sxs-lookup"><span data-stu-id="15e53-153">It’s also possible that Test-CsMcxConfiguration will fail with this error message:</span></span>

<span data-ttu-id="15e53-154">Test-CsMcxPushNotification：推播通知要求遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="15e53-154">Test-CsMcxPushNotification : Push Notification request was rejected.</span></span>

<span data-ttu-id="15e53-155">線上：1個字元：27</span><span class="sxs-lookup"><span data-stu-id="15e53-155">At line:1 char:27</span></span>

<span data-ttu-id="15e53-156">\+ Test-CsMcxPushNotification \<\<\<\<</span><span class="sxs-lookup"><span data-stu-id="15e53-156">\+ Test-CsMcxPushNotification \<\<\<\<</span></span>

<span data-ttu-id="15e53-157">\+ CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] ，SyntheticTransactionException</span><span class="sxs-lookup"><span data-stu-id="15e53-157">\+ CategoryInfo : OperationStopped: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException</span></span>

<span data-ttu-id="15e53-158">\+ FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions、TestMcxPushNotificationCmdlet</span><span class="sxs-lookup"><span data-stu-id="15e53-158">\+ FullyQualifiedErrorId : WorkflowNotCompleted,Microsoft.Rtc.Management.SyntheticTransactions.TestMcxPushNotificationCmdlet</span></span>

<span data-ttu-id="15e53-159">如果您已啟用 URL 篩選並封鎖 HTTP：及 HTTPs：首碼，則通常會發生「推入通知要求」訊息。</span><span class="sxs-lookup"><span data-stu-id="15e53-159">The “Push notification request was rejected” message typically occurs if you have enabled URL filtering and are blocking the http: and https: prefixes.</span></span> <span data-ttu-id="15e53-160">您可以使用類似下列的命令，判斷封鎖哪些首碼：</span><span class="sxs-lookup"><span data-stu-id="15e53-160">You can determine which prefixes are being blocked by using a command similar to the following:</span></span>

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

<span data-ttu-id="15e53-161">如果結果中出現 [HTTP：] 或 [HTTPs：]，您必須將它們從 [封鎖的首碼] 清單中移除，推播通知才能運作。</span><span class="sxs-lookup"><span data-stu-id="15e53-161">If http: or https: appear in the results, you must remove them from the blocked prefix list for push notifications to work.</span></span> <span data-ttu-id="15e53-162">可以使用類似下列的命令來執行：</span><span class="sxs-lookup"><span data-stu-id="15e53-162">That can be done by using commands similar to these:</span></span>

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

<span data-ttu-id="15e53-163">如需詳細資訊，請參閱 [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)Cmdlet 的 [說明] 主題。</span><span class="sxs-lookup"><span data-stu-id="15e53-163">For more information, see the help topic for the [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

