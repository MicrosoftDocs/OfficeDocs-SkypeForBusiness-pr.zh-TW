---
title: Lync Server 2013： CallType 表格
description: Lync Server 2013： CallType 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CallType table
ms:assetid: a1d7187c-f851-4967-88ea-73922911ee7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412752(v=OCS.15)
ms:contentKeyID: 48185019
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7af9c40396b993893f5157b89bedff0d80d87eb0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565169"
---
# <a name="calltype-table-in-lync-server-2013"></a>Lync Server 2013 中的 CallType 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

CallType 表格是儲存可能通話類型清單的靜態表格。


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
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>CallType</strong></p></td>
<td><p>Nvarchar</p></td>
<td></td>
<td><p>允許的值：</p>
<ul>
<li><p>0 -- 不明</p></li>
<li><p>1–立即訊息</p></li>
<li><p>2--應用程式共用</p></li>
<li><p>3--音訊</p></li>
<li><p>4–音訊和影片</p></li>
<li><p>5–檔案傳輸</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

