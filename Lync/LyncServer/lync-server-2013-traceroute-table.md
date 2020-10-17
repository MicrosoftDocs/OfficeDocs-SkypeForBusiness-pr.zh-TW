---
title: Lync Server 2013： TraceRoute 表格
description: Lync Server 2013： TraceRoute 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af33e572065fbab1eaaaef684997e7f95edaed9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549059"
---
# <a name="traceroute-table-in-lync-server-2013"></a>Lync Server 2013 中的 TraceRoute 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-02-21_

TraceRoute 表格包含來自呼叫的路由資訊。 此表格已引進 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要，外部</p></td>
<td><p>通話的開始日期與時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>唯一識別碼，用來區分可能在相同日期和同一時間開始的多個通話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要，外部</p></td>
<td><p>代表通話中使用的影片線條類型。 允許的值為：</p>
<ul>
<li><p>0–音訊</p></li>
<li><p>1–影片</p></li>
<li><p>2–全景影片</p></li>
<li><p>3–應用程式/桌面共用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>位</p></td>
<td><p>主要</p></td>
<td><p>撥出電話的端點。</p></td>
</tr>
<tr class="odd">
<td><p><strong>跳</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>網路躍點/</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>IP 位址的唯一識別碼。 IP 位址資訊會儲存在 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 IPAddress 表格</a>中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rtt</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>往返時間。 「往返時間」會測量語音資料包到達目的地所需的時間長度，然後傳回收到的通知。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

