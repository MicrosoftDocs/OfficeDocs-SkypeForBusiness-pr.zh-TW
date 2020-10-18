---
title: Lync Server 2013： ProgressReport view
description: Lync Server 2013： ProgressReport view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b95086012f254499644e778e43cafdf70ffc8f9c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579789"
---
# <a name="progressreport-view-in-lync-server-2013"></a>Lync Server 2013 中的 ProgressReport 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

ProgressReport view 儲存已完成會話的相關資訊。 進度報告只會寫入 Lync Server 2013 決定可用於診斷目的的呼叫和會話。 此視圖已引進于 Microsoft Lync Server 2013。

<div>


> [!NOTE]  
> ErrorTime、ErrorReportSeq 及 ProgressReportSeq 欄位不一定和錯誤有關，而是有關指出通話或訊息狀態的訊息。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>發生錯誤的時間。 與 ErrorReportSeq 搭配使用，以唯一識別錯誤。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用以識別錯誤的 ID 號碼。 與 ErrorTime 搭配使用，以唯一識別錯誤。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>識別進度報表的識別碼。 用來區分相同錯誤報表的進度報告。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>錯誤報表的診斷識別碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起源錯誤的伺服器名稱 (如果報告是從伺服器元件傳送) 中。</p></td>
</tr>
<tr class="even">
<td><p><strong>應用程式</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起源錯誤的應用程式名稱 (如果報告是從伺服器元件傳送) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>唯一</p></td>
<td><p>與會議相關聯之不同元件的加入時間資訊的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定元件加入會議所需的時間 (（毫秒）) 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>Varchar (max) </p></td>
<td><p>其他錯誤資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

