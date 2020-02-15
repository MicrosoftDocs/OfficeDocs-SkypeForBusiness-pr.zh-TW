---
title: 'Lync Server 2013: tblEnumValue'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblEnumValue
ms:assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615025(v=OCS.15)
ms:contentKeyID: 48185040
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d182a3689ae38d4117b45d6590bb2ccd08c0a8b7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblenumvalue-in-lync-server-2013"></a>Lync Server 2013 中的 tblEnumValue

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-28_

tblEnumValue 是一種硬式編碼表格，包含節點表格中所用的屬性的可見度和行為值。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>類型	</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>smallint，非 null</p></td>
<td><p>值的 ID。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>smallint，非 null</p></td>
<td><p>屬性的識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>attributeValue</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>值的名稱。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>索引鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>valueID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>attributeID</p></td>
<td><p>在 tblEnumAttribute.attributeID 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


### <a name="table-values"></a>表格值

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>valueID</th>
<th>attributeID</th>
<th>attributeValue</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>1 </p></td>
<td><p>私用</p></td>
</tr>
<tr class="even">
<td><p>3 </p></td>
<td><p>1 </p></td>
<td><p>範圍</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>2 </p></td>
<td><p>一般</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>2 </p></td>
<td><p>視聽中心</p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>1 </p></td>
<td><p>開啟</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 tblNode](lync-server-2013-tblnode.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

