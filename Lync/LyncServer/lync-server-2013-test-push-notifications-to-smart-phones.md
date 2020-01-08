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
ms.openlocfilehash: 3a0d58c79fcd66229ffda43fa60ab99cedc308ab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>在 Lync Server 2013 中測試推播通知至智慧型電話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>次</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>需要許可權</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 CsMcxPushNotification Cmdlet 許可權的 RBAC 角色。 若要查看可以使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell 提示執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

推播通知服務（Apple 推播通知服務和 Microsoft 推播通知服務）可以傳送事件通知（例如新的立即訊息或新的語音信箱）至行動裝置（例如 Iphone 和 Windows phone），即使 Lync 用戶端在這些裝置上，目前已暫停或在背景中執行。 推播通知服務是在 Microsoft 伺服器上執行的雲端服務。 若要利用推播通知，您必須能夠連線到並透過推播通知 clearinghouse 進行驗證。 CsMcxPushNotification Cmdlet 可讓系統管理員確認推播通知要求可以透過邊緣伺服器路由至推播通知 clearinghouse。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要測試推播通知服務，請呼叫 CsMcxPushNotification Cmdlet。 請確定您指定的是 Edge 伺服器的完整功能變數名稱：

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

如需詳細資訊，請參閱[Test CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) Cmdlet 的說明主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>判斷成功或失敗

如果 Test CsMcxPushNotification 成功，則 Cmdlet 會傳回測試結果成功：

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

出錯

自檢

如果測試 CsMcxPushNotification 無法連線到推播通知，則 Cmdlet 通常不會傳回失敗的測試結果。 相反，命令通常會完全失敗。 例如：

CsMcxPushNotification：從網路收到504（伺服器超時）回應，且操作失敗。 如需詳細資訊，請參閱例外狀況詳細資料。

在第一行：1個字元：27

\+Test-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]，FailureResponseException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果推播通知服務無法正常顯示與邊緣伺服器通訊的問題，或與推播通知結算所進行通訊的問題。 如果您在執行 Test CsMcxPushNotification 時遇到問題，您應該執行的第一件事就是確認您的 Edge 伺服器正常運作。 其中一種方法是使用 Test CsAVEdgeConnectivity Cmdlet：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

這種檢查會驗證指定的使用者是否可以連線到 Edge 伺服器。

如果邊緣伺服器看起來正常運作，這通常表示您無法連線到推播通知 clearinghouse。 然後，這通常表示您尚未正確設定 clearinghouse URI，或是您沒有指向此 URL 的 DNS SRV 記錄。 您可以執行此命令，以確認 URI 已設定為正確的值（sip:push@push.lync.com）：

    Get-CsMcxConfiguration

如果 PushNotificationProxyUri 屬性是設定為 sip:push@push.lync.com 以外的任何專案，您可以使用 McxConfiguration Cmdlet 來修正該問題。 例如，這個命令會在整個組織中正確設定 URI：

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

如需詳細資訊，請參閱[CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) Cmdlet 的說明主題。

如果 URI 設定正確，下一個步驟應該是確認您有解析到 SIP 網域和 Edge 伺服器的 DNS SRV 記錄。 如需有關如何設定這些記錄的詳細資訊，請參閱行動性的協助主題 DNS 需求。 請注意，下列錯誤訊息通常表示 DNS 記錄的問題：

從網路收到504（伺服器超時）回應，且操作失敗。 如需詳細資訊，請參閱例外狀況詳細資料。

測試 CsMcxConfiguration 也可能會失敗，並出現以下錯誤訊息：

Test-CsMcxPushNotification：推播通知要求遭到拒絕。

在第一行：1個字元：27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo： OperationStopped：（:)\[Test-CsMcxPushNotification\]，SyntheticTransactionException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions. TestMcxPushNotificationCmdlet

如果您已啟用 URL 篩選並封鎖 HTTP：及 HTTPs：首碼，通常會發生 [推播通知要求] 訊息。 您可以使用類似下列的命令來判斷要封鎖哪些首碼：

``` 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

如果 [HTTP：] 或 [HTTPs：] 出現在結果中，您必須從 [封鎖的首碼] 清單中移除，推播通知才能正常運作。 您可以使用類似以下的命令來完成：

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

如需詳細資訊，請參閱[CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)Cmdlet 的說明主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

