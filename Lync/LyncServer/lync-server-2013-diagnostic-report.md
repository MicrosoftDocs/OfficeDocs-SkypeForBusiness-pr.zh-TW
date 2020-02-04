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
ms.openlocfilehash: 14a2fa69e0e2397b970850a91042f0241060f839
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的診斷報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-07_

診斷報告提供失敗會話的診斷與疑難排解資訊。 此資訊包括在會話失敗時所報告的診斷 ID 和診斷標頭。 診斷 ID 是附加至 SIP 訊息的唯一識別碼（以 ms 診斷標頭形式），而診斷標頭則提供診斷識別碼的隨附描述。 報告可能也包含報告元件已知的有用疑難排解詳細資料。 例如：

  - PSTN 閘道產生失敗時所提供的原因代碼。 PSTN 網路上的撥出電話失敗時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，指出沒有電路或通道可以完成通話。

  - 針對連接失敗的對等 FQDN、埠和 Winsock 錯誤。

  - 尋找 DNS 解析失敗的名稱。 只要用戶端與名稱伺服器聯絡，並要求對應至指定裝置名稱的 IP 位址，就會發生 DNS 解析。

<div>

## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

您可以透過在 Lync Server 2013 或會議詳細資料包表中，按一下[點對點工作階段詳細資料包告](lync-server-2013-peer-to-peer-session-detail-report.md)上的診斷報告（詳細資料）度量來存取診斷報告。

</div>

<div>

## <a name="filters"></a>濾鏡

無。 您無法篩選診斷報告。

</div>

<div>

## <a name="metrics"></a>指標

下表列出每個會話的診斷報告所提供的資訊。

### <a name="diagnostic-report-metrics"></a>診斷報告度量單位

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>您可以針對此專案進行排序嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>記錄報告的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應代碼</strong></p></td>
<td><p>否</p></td>
<td><p>在會話失敗時傳送 SIP 回應代碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求類型</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的 SIP 要求類型。 例如，[邀請]、[再見] 或 [服務]。</p></td>
</tr>
<tr class="even">
<td><p><strong>從源</strong></p></td>
<td><p>否</p></td>
<td><p>錯誤來源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>從使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>從使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>啟動會話之使用者的端點所使用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的媒體內容類型。 例如，常見的內容類型是 Application/sdp。 會話描述通訊協定（SDP）是一種標準的網際網路通訊協定，用於會話宣告、會話邀請以及其他多媒體會話啟動的形式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>應用程式</strong></p></td>
<td><p>否</p></td>
<td><p>錯誤中涉及的應用程式。</p></td>
</tr>
<tr class="even">
<td><p><strong>使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>受邀者加入會話之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p>會議加入時間（毫秒）</p></td>
<td><p>否</p></td>
<td><p>使用者加入會議所需的時間量（以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷標頭</strong></p></td>
<td><p>否</p></td>
<td><p>診斷識別碼描述。</p></td>
</tr>
</tbody>
</table>


您可以在[Ms Diagnostics 頁首頁面](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)找到診斷錯誤清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

