---
title: Lync Server 2013：會議表格
description: Lync Server 2013：會議表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferences table
ms:assetid: c3da6271-b3c6-4898-894f-10456ec794d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412964(v=OCS.15)
ms:contentKeyID: 48185340
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e0d8c61e795dc0c8f9843b871d7e4efd1bec571
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561599"
---
# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013 中的會議表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

此表格中的每一筆記錄都包含有關一部會議的呼叫詳細資料。


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
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>CDR 代理程式捕獲會議要求的時間。 僅用作主鍵，以唯一識別會議實例。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>識別工作階段的 ID 號碼。 與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議 URI。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>唯一</p></td>
<td><p> </p></td>
<td><p>適用于週期性會議;每個週期性會議實例都具有相同的 <strong>ConferenceUri</strong>，但會有不同的 <strong>ConfInstance</strong>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>會議開始時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>會議開始時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>識別碼，用來識別捕獲會議的集區。 如需詳細資訊，請參閱 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>臨界值</p></td>
<td><p>Foreign</p></td>
<td><p>識別此會議之召集人 URI 的識別碼號碼。 如需詳細資訊，請參閱 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>包含會議屬性的位元遮罩。 可能的值為：</p>
<ul>
<li><p>0X01</p></li>
<li><p>合成</p></li>
<li><p>交易</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>處理</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>監控服務所使用的內部欄位。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


\* 對於大部分的會話，SessionIdSeq 的值會是1。 如果兩個會話的開始時間完全相同，則 SessionIdSeq 為1，而另一個會是2，依此類推。

</div>

<span> </span>

</div>

</div>

</div>

