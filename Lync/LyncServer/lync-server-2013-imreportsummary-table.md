---
title: Lync Server 2013： IMReportSummary 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IMReportSummary table
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204753(v=OCS.15)
ms:contentKeyID: 48183673
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2254bafe059cc1a4bc6436580e9d604711f5fb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="imreportsummary-table-in-lync-server-2013"></a>Lync Server 2013 中的 IMReportSummary 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-20_

IMReportSummaryTable 會提供組織中的立即訊息會話的整體報告。 此表格是在 Microsoft Lync Server 2013 中推出。


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
<td><p><strong>開始</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>立即訊息會話開始的日期和時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char （1）</p></td>
<td><p>首選</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>Nvarchar （257）</p></td>
<td><p>首選</p></td>
<td><p>主持會話之池的完整功能變數名稱。</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>通話的優先順序（例如，緊急或非緊急）。 優先順序資訊會儲存在<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 的 CallPriorities 表格中</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>Bigint</p></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>Bigint</p></td>
<td></td>
<td><p>會話期間交換的立即訊息總數。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

