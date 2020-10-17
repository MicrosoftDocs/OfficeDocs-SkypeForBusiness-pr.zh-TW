---
title: Lync Server 2013：伺服器表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server table
ms:assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398801(v=OCS.15)
ms:contentKeyID: 48184890
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebfc08cd5a27527d5afebdae8b2fea8335f93dcb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510230"
---
# <a name="server-table-in-lync-server-2013"></a>Lync Server 2013 中的伺服器表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

伺服器資料表是支援的表格。 每筆記錄代表一部伺服器。


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
<td><p><strong>ServerKey</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別伺服器的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>FQDNOrIP</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>index</p></td>
<td><p>MAC 位址字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerType</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>1：轉送伺服器</p>
<p>2： A/V 會議 Server16394： A/V Edge service32769：閘道</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>Nvarchar (512) </p></td>
<td></td>
<td><p>伺服器所屬的集區。 僅適用于 A/V 會議伺服器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>僅限內部使用。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

