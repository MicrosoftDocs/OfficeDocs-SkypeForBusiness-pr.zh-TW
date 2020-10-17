---
title: Lync Server 2013：測試 Exchange 至 Lync 通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e0d3354a71079f20d552aa3175083540744a5b1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536016"
---
# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Exchange 至 Lync 通知

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>驗證排程</p></td>
<td><p>每日</p></td>
</tr>
<tr class="even">
<td><p>測試控管</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>必要的權限</p></td>
<td><p>使用 Lync Server 管理命令介面在本機執行時，使用者必須是 RTCUniversalServerAdmins 安全性群組的成員。</p>
<p>使用 Windows PowerShell 的遠端實例執行時，必須為使用者指派具有執行 <strong>Test-CsExStorageNotification</strong> Cmdlet 許可權的 RBAC 角色。 若要查看可使用此 Cmdlet 的所有 RBAC 角色清單，請從 Windows PowerShell prompt 中執行下列命令：</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>描述

**Test-CsExStorageNotification**指令程式可用來驗證 Microsoft Exchange Server 2013 notification 服務是否可在任何時候對使用者的連絡人清單進行更新時通知 Lync Server 2013。 此 Cmdlet 只有在您使用整合連絡人存放區時才有效。

</div>

<div>

## <a name="running-the-test"></a>執行測試

範例1所示的命令會測試，以查看 Lync Server Storage Service 是否可以連線至使用者 sip:kenmyer@litwareinc.com 的 Microsoft Exchange Server 信箱通知服務。 在此範例中，NetNamedPipe 是用來做為 WCF 系結。

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>決定成功或失敗

如果 Exchange 整合設定正確，您會收到類似以下的輸出，並將 Result 屬性標示為 [ **成功**]：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：成功

延遲：00:00:00

錯誤訊息：

診斷：

如果指定的使用者無法接收通知，結果將會顯示為 [失敗]，而且會在 [錯誤及診斷] 屬性中記錄其他資訊：

目標 Fqdn： atl-cs-001.litwareinc.com

結果：失敗

延遲：00:00:00

錯誤訊息：10060，連接嘗試失敗，因為連接的方

在一段時間後沒有正確回應，或

已建立連線失敗，因為連接的主機已

無法回應10.188.116.96：5061

內部例外狀況：連接嘗試失敗，因為

在一段時間後，連接的通訊錄未正確回應

時間或已建立的連線失敗，因為連接的主機

無法回應10.188.116.96：5061

診斷：

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>測試可能失敗的原因

以下是一些 **Test-CsExStorageNotification** 可能失敗的常見原因：

  - 提供的參數值不正確。 如果使用，必須正確設定選用參數，否則測試將會失敗。 請重新執行不含選用參數的命令，然後查看是否成功。

  - 如果 Microsoft Exchange 伺服器設定不當或尚未部署，此命令將會失敗。

</div>

<div>

## <a name="see-also"></a>另請參閱


[Test-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

