---
title: Lync Server 2013：診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6eb6de7f2ba23d52a7b508869dbb25c9c5e3802
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514490"
---
# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的診斷報告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

診斷報告可提供失敗會話的診斷與疑難排解資訊。 此資訊包含會話失敗時所報告的診斷識別碼和診斷標頭。 診斷 ID 是與 SIP 郵件相連的 ms diagnostics 標頭) 形式的唯一識別碼 (，而診斷標頭則提供診斷識別碼的附帶描述。 報告可能也包含報告元件所知道的有用疑難排解詳細資料。 例如：

  - 產生失敗之 PSTN 閘道所提供的原因碼。 PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。

  - 連接失敗的對等 FQDN、埠和 Winsock 錯誤。

  - 要尋找以進行 DNS 解析失敗的名稱。 DNS 解析會在用戶端接觸名稱伺服器時進行，並要求對應至指定裝置名稱的 IP 位址。

<div>

## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

您可以在 Lync Server 2013 或會議詳細資料包告的 [ [Peer-to-Peer 會話詳細資料](lync-server-2013-peer-to-peer-session-detail-report.md) ] 報告中，按一下 [診斷報告] (詳細資料) 指標，即可存取診斷報告。

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選診斷報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個會話的診斷報告中提供的資訊。

### <a name="diagnostic-report-metrics"></a>診斷報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>姓名</th>
<th>可以排序這個項目嗎？</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>報告的記錄日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>會話失敗時傳送的 SIP 回應碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求類型</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 SIP 要求類型。 例如，邀請、再見或服務。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>否</p></td>
<td><p>錯誤來源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話之使用者端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 郵件（通常會在疑難排解錯誤中提供有用資訊) ）的表單中的唯一識別碼 (。</p></td>
</tr>
<tr class="even">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的媒體內容類型。 例如，常見的內容類型為 Application/sdp。 Session Description Protocol (SDP) 是標準的網際網路通訊協定，用來進行會話宣告、會話邀請及其他形式的多媒體會話初始。</p></td>
</tr>
<tr class="odd">
<td><p><strong>應用程式</strong></p></td>
<td><p>否</p></td>
<td><p>錯誤所涉及的應用程式。</p></td>
</tr>
<tr class="even">
<td><p><strong>至使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>獲邀加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p>會議加入時間 (毫秒) </p></td>
<td><p>否</p></td>
<td><p>使用者加入會議所需的時間（以毫秒為單位）)  (量。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷標頭</strong></p></td>
<td><p>否</p></td>
<td><p>診斷識別碼描述。</p></td>
</tr>
</tbody>
</table>


您可以在 [Ms Diagnostics 頁首頁面](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上找到診斷錯誤的清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

