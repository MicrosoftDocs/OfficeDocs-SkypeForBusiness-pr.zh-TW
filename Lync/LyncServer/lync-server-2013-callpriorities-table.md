---
title: Lync Server 2013： CallPriorities 表格
description: Lync Server 2013： CallPriorities 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallPriorities table
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398093(v=OCS.15)
ms:contentKeyID: 48183275
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3cd1639921c63630e157744dbc8af22c50fac7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565179"
---
# <a name="callpriorities-table-in-lync-server-2013"></a>Lync Server 2013 中的 CallPriorities 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

CallPriorities 表格是靜態表格，可儲存通話可能優先順序的清單 (如「緊急」、「急」或「一般」)。


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>優先順序</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td></td>
<td><p>允許的值：</p>
<ul>
<li><p>0 - 未知</p></li>
<li><p>1 - 非緊急</p></li>
<li><p>2 - 一般</p></li>
<li><p>3 - 急</p></li>
<li><p>4 - 緊急</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

