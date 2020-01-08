---
title: Lync Server 2013：ProgressReport 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013 中的 ProgressReport 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

進度報告是以用戶端在通話或會話完成後上傳到資料庫的資料為基礎。 進度報告只會寫入 Lync Server 2013 決定可能對診斷用途有用的通話和會話。

ErrorTime、ErrorReportSeq 和 ProgressReportSeq 欄位不一定會參照錯誤，而是指出通話或訊息狀態的訊息。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>包含此進度報告之進度錯誤報表的日期和時間。 如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>與 ErrorTime、ProgressReportSeq 搭配使用的識別碼編號，可唯一識別進度報告。 如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>識別錯誤報表的識別碼編號。 ErrorReporSeq 與 ErrorTime 搭配使用，可唯一識別錯誤報表。 如需詳細資訊，請參閱<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中</a>的 [ErrorReport] 資料表</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別進度報表的識別碼編號。 與 ErrorTime 和 ErrorReportSeq 搭配使用，可唯一識別進度報告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>進度報告的診斷識別碼。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>源</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>傳送錯誤報表的伺服器（如果報告是從伺服器元件傳送）。 如需詳細資訊，請參閱<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 [伺服器] 資料表。此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>報告所用的 Lync Server 進程。 如需詳細資訊，請參閱應用程式表格。</p></td>
</tr>
<tr class="even">
<td><p><strong>具體</strong></p></td>
<td><p>影像</p></td>
<td></td>
<td><p>以二進位格式儲存的進度報告詳細資料，以節省空間。此資料可以使用下列語法轉換成文字格式：</p>
<p>cast （以 Varbinary （max）格式轉換為 Varchar （max））</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td></td>
<td><p>與會議中所涉及之不同元件的加入時間資訊關聯的唯一識別碼。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定元件加入會議所需的時間（以毫秒為單位）。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

