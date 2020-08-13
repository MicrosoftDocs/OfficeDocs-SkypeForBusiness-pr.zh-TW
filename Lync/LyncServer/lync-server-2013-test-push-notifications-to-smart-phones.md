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
ms.openlocfilehash: 06684665819e14540628e5cd45309ef2c920b227
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>在 Lync Server 2013 中測試向智慧型電話的推播通知

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
<td><p>每月</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 Test-CsMcxPushNotification Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

推播通知服務 (Apple Push Notification Service 和 Microsoft 推播通知服務) 可以將有關事件的通知傳送給行動裝置（例如 Iphone 和 Windows phone），即使這些裝置上的 Lync 用戶端目前已暫停或在後臺執行，也是如此。 推播通知服務是在 Microsoft 伺服器上執行的雲端式服務。 為了利用推播通知，您必須能夠連線至推播通知，並透過此驗證。 Test-CsMcxPushNotification Cmdlet 可讓系統管理員確認推播要求可以透過 Edge server 路由傳送至推播通知 clearinghouse。

</div>

<div>

## <a name="running-the-test"></a>執行測試

若要測試推播通知服務，請致電 Test-CsMcxPushNotification Cmdlet。 請務必指定 Edge server 的完整功能變數名稱：

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

如需詳細資訊，請參閱[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) Cmdlet 的 [說明] 主題。

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Test-CsMcxPushNotification 成功，指令 Cmdlet 會傳回測試結果成功：

TargetFqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤：

診斷：

如果 Test-CsMcxPushNotification 無法連接到推播通知，則 Cmdlet 通常不會傳回失敗的測試結果。 相反的命令通常會完全失敗。 例如：

Test-CsMcxPushNotification：從網路接收到 504 (伺服器超時的回應) 回應，但操作失敗。 如需詳細資訊，請參閱例外狀況詳細資料。

線上：1個字元：27

\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] ，FailureResponseException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions、TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

如果推播通知服務失敗，通常表示與 Edge server 通訊問題，或與推播通知結算所進行通訊的問題。 如果您在執行 Test-CsMcxPushNotification 時遇到問題，您應該做的第一件事是驗證 Edge server 是否運作正常。 使用 Test-CsAVEdgeConnectivity Cmdlet 的方法之一：

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

這種檢查會驗證指定的使用者是否可以連接到 Edge server。

如果 Edge server 似乎運作正常，這通常表示您無法連線至推播通知 clearinghouse。 反過來，這通常表示您沒有正確地設定 clearinghouse URI，或您沒有指向此 URL 的 DNS SRV 記錄。 您可以執行下列命令，確認 URI 已設定為正確的值 (sip:push@push.lync.com) ：

    Get-CsMcxConfiguration

如果 PushNotificationProxyUri 屬性設定為 sip:push@push.lync.com 以外的任何專案，您可以使用 Microsoft.rtc.management.writeableconfig.settings.mcxconfiguration.mcxconfiguration Cmdlet 修正該問題。 例如，此命令會正確地設定整個組織的 URI：

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

如需詳細資訊，請參閱[Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) Cmdlet 的 [說明] 主題。

如果 URI 設定正確，下一個步驟應該是驗證您是否有解析為 SIP 網域和 Edge server 的 DNS SRV 記錄。 如需如何設定這些記錄的詳細資訊，請參閱協助主題行動的 DNS 需求。 請注意，下列錯誤訊息通常會指出 DNS 記錄的問題：

從網路接收到 504 (伺服器超時) 回應，但作業失敗。 如需詳細資訊，請參閱例外狀況詳細資料。

Set-csmcxconfiguration 也可能會失敗，並顯示此錯誤訊息：

Test-CsMcxPushNotification：推播通知要求遭到拒絕。

線上：1個字元：27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo： OperationStopped： (： ) \[ Test-CsMcxPushNotification \] ，SyntheticTransactionException

\+FullyQualifiedErrorId： WorkflowNotCompleted、SyntheticTransactions、TestMcxPushNotificationCmdlet

如果您已啟用 URL 篩選並封鎖 HTTP：及 HTTPs：首碼，則通常會發生「推入通知要求」訊息。 您可以使用類似下列的命令，判斷封鎖哪些首碼：

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

如果結果中出現 [HTTP：] 或 [HTTPs：]，您必須將它們從 [封鎖的首碼] 清單中移除，推播通知才能運作。 可以使用類似下列的命令來執行：

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

如需詳細資訊，請參閱[CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)Cmdlet 的 [說明] 主題。

</div>

</div>

<span> </span>

</div>

</div>

</div>

