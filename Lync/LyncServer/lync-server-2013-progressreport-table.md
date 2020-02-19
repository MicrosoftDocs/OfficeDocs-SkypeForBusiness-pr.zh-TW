---
title: 'Lync Server 2013: ProgressReport 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50697242b7086dbd81b74d098d200b1162ac12a5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139064"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013 中的 ProgressReport 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

進度報告是以通話或工作階段完成時，用戶端上傳至資料庫的資料為基礎。 進度報告將寫入僅適用於通話和 Lync Server 2013 會決定可能會很有用進行診斷之用的工作階段。

ErrorTime、ErrorReportSeq 及 ProgressReportSeq 欄位不一定和錯誤有關，而是有關指出通話或訊息狀態的訊息。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>主索引鍵 /</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>包含此進度報告之進度錯誤報告的日期和時間。 請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>與 ErrorTime、ProgressReportSeq 搭配使用的識別碼，可識別唯一的進度報告。 請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要，外部</p></td>
<td><p>識別錯誤報告的識別碼。 ErrorReporSeq 與 ErrorTime 搭配使用，可識別唯一的錯誤報告。 請參閱如需詳細資訊的<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表格</a></p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別進度報告的識別碼。與 ErrorTime 及 ErrorReportSeq 搭配使用，可識別唯一的進度報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>進度報告的診斷 ID。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>（如果報告從伺服器元件傳送） 傳送錯誤報告的伺服器。 請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的伺服器表格</a>如需詳細資訊。Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>報告針對的 Lync Server 程序。如需詳細資訊，請參閱應用程式表格。</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>image</p></td>
<td></td>
<td><p>進度報告詳細資料，以二進位格式儲存，以節省空間。可使用此語法將資料轉換成文字格式：</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>會議所包含之不同元件的加入時間資訊的相互關聯唯一識別碼。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定元件加入會議的時間 (毫秒)。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

