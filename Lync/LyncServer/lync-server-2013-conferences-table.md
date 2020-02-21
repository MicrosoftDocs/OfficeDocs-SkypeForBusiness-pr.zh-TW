---
title: 'Lync Server 2013: Conferences 表格'
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
ms.openlocfilehash: d3dbaf1a721433cc04aa681dad56d753de8bc9a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferences-table-in-lync-server-2013"></a>Lync Server 2013 中的會議表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

此表格中的每一筆記錄包含一場電話會議的通話詳細資料。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>會議邀請的 CDR 代理程式所擷取的時間。 只能作為主索引鍵用來唯一地識別會議執行個體。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>識別工作階段的 ID 號碼。 搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。 *</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>會議 URI。 請參閱<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>唯一</p></td>
<td><p> </p></td>
<td><p>可用於週期性會議;每個週期性會議執行個體有相同的<strong>ConferenceUri</strong>，但會有不同的<strong>ConfInstance</strong>。</p></td>
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
<td><p>若要識別已擷取的會議集區的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-pools-table.md">在 Lync Server 2013 中的集區資料表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>OrganizerId</strong></p></td>
<td><p>臨界值</p></td>
<td><p>Foreign</p></td>
<td><p>若要識別此會議 URI 召集人的識別碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>位元遮罩，包含會議屬性。 可能的值為：</p>
<ul>
<li><p>0X01</p></li>
<li><p>綜合</p></li>
<li><p>交易</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>處理</strong></p></td>
<td><p>位元</p></td>
<td></td>
<td><p>監視服務所使用的內部欄位。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
</tbody>
</table>


\*對於大多數的工作階段，SessionIdSeq 會有 1 的值。 如果兩個工作階段時間來啟動完全相同，SessionIdSeq 的其中一個會是 1，並為其他將會是 2，依此類推。

</div>

<span> </span>

</div>

</div>

</div>

