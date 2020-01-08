---
title: Lync Server 2013：Phones 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920454a5db71c1e6f3cd2ea2ae1134d149b4f297
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981683"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a>Lync Server 2013 中的 Phones 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-08-20_

[電話] 資料表是支援表格。 資料表中的每一筆記錄都儲存 VoIP 通話中有記錄在資料庫中的一個電話號碼的相關資訊。


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
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此手機的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p> </p></td>
<td><p>電話號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td></td>
<td><p>時間戳記（僅供內部使用）。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中推出。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

