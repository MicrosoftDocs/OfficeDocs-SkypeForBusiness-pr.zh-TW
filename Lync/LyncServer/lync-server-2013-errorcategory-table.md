---
title: 'Lync Server 2013: ErrorCategory 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorCategory table
ms:assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204675(v=OCS.15)
ms:contentKeyID: 48183425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3052aa95aa6cd846717aa98c5778531aeee6f7e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorcategory-table-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorCategory 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-08-20 個_

ErrorCategory 表包含每個 Microsoft Lync Server 2013 診斷分類的易記名稱。 根據預設，Lync Server 2013 會使用下列分類：

  - 0 -- 成功

  - 1--預期的失敗

  - 2 – 未預期的失敗

Microsoft Lync Server 2013 中已採用此表格。


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
<td><p><strong>類別識別碼</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主要</p></td>
<td><p>分類的唯一識別碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>指派給分類的值和易記名稱。允許的值為：</p>
<ul>
<li><p>0 -- 成功</p></li>
<li><p>1--預期的失敗</p></li>
<li><p>2 – 未預期的失敗</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

