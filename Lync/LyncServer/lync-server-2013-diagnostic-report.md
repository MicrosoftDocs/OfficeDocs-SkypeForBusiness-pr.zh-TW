---
title: Lync Server 2013： 診斷報告
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
ms.openlocfilehash: 3e95d746d323e803bf7dbc37e8cdaebcdd1d655c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a>Lync Server 2013 中的診斷報告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-02-07_

診斷報告提供失敗工作階段的診斷與疑難排解的資訊。 此資訊包括診斷識別碼及工作階段失敗時，所報告的診斷標頭。 診斷識別碼是取得附加至 SIP 郵件，而診斷標頭提供隨附的說明診斷識別碼的唯一識別碼 （以毫秒診斷標頭的形式） 報告也可能包含重要已知的報告元件的疑難排解詳細資料。 例如：

  - 原因程式碼提供者產生失敗的 PSTN 閘道。 PSTN 網路上的撥出電話無法作用時，系統會自動產生 ISDN User Part (ISUP) 原因碼。 例如，PSTN 閘道可能傳送原因碼 34，代表沒有可用的電路或通訊管道可以完成通話。

  - 對等 FQDN、 連接埠與 Winsock 錯誤的連線失敗。

  - 正在進行查閱 DNS 解析失敗的名稱。 DNS 解析任何用戶端的連絡人名稱伺服器的時間，並要求的 IP 位址會對應至指定的裝置名稱。

<div>

## <a name="accessing-the-diagnostic-report"></a>存取診斷報告

可以按一下 [ [Lync Server 2013 中的端對端工作階段詳細資料報告](lync-server-2013-peer-to-peer-session-detail-report.md)] 或 [會議詳細資料報表上的 [診斷報告 （詳細資料）] 計量來存取診斷報告。

</div>

<div>

## <a name="filters"></a>篩選

無。 您無法篩選診斷報告。

</div>

<div>

## <a name="metrics"></a>計量

下表列出診斷報告針對每個工作階段所提供的資訊。

### <a name="diagnostic-report-metrics"></a>診斷報告計量

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名稱</th>
<th>可以排序這個項目嗎？</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>報告時間</strong></p></td>
<td><p>否</p></td>
<td><p>日期和時間報告的記錄。</p></td>
</tr>
<tr class="even">
<td><p><strong>回應碼</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 工作階段失敗時傳送的回應碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>要求類型</strong></p></td>
<td><p>否</p></td>
<td><p>SIP 失敗的要求類型。 例如，邀請、 BYE 或服務。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>否</p></td>
<td><p>錯誤的來源。</p></td>
</tr>
<tr class="odd">
<td><p><strong>來源使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>啟動工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td><p><strong>來源使用者代理程式</strong></p></td>
<td><p>否</p></td>
<td><p>起始工作階段之使用者端點所用的軟體。</p></td>
</tr>
<tr class="odd">
<td><p><strong>診斷識別碼</strong></p></td>
<td><p>否</p></td>
<td><p>唯一識別項 （以毫秒診斷標頭的形式） 附加在 SIP 訊息通常提供在疑難排解錯誤很有用的資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>內容類型</strong></p></td>
<td><p>否</p></td>
<td><p>失敗的媒體內容類型。 例如，常見的內容類型是應用程式/sdp。 工作階段描述通訊協定 (SDP) 是用於工作階段公告、 工作階段邀請和其他形式的多媒體工作階段初始標準網際網路通訊協定。</p></td>
</tr>
<tr class="odd">
<td><p><strong>應用程式</strong></p></td>
<td><p>否</p></td>
<td><p>應用程式發生錯誤的。</p></td>
</tr>
<tr class="even">
<td><p><strong>目標使用者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>獲邀加入工作階段之使用者的 SIP 位址。</p></td>
</tr>
<tr class="odd">
<td><p>會議加入時間 （毫秒）</p></td>
<td><p>否</p></td>
<td><p>量花使用者加入會議的時間 （以毫秒為單位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>診斷標頭</strong></p></td>
<td><p>否</p></td>
<td><p>診斷識別碼的描述。</p></td>
</tr>
</tbody>
</table>


[Ms-diagnostics 標頭] 頁面](https://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)上，可以找到診斷錯誤清單。

</div>

</div>

<span> </span>

</div>

</div>

</div>

