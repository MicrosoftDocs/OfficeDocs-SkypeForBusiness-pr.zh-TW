---
title: 'Lync Server 2013: tblSkippedAffiliations'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblSkippedAffiliations
ms:assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558611(v=OCS.15)
ms:contentKeyID: 48183373
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d21dbda8b649588e691d285c62ff865e9f001308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblskippedaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblSkippedAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblSkippedAffiliations 包含無法讀取 （通常是由於 Active Directory 網域服務存取錯誤） 的關係。

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
<td><p>prinID</p></td>
<td><p>int，非 null</p></td>
<td><p>主體識別碼。</p></td>
</tr>
<tr class="even">
<td><p>affDescription</p></td>
<td><p>nvarchar (255)，非 null</p></td>
<td><p>識別關係的字串。</p>
<p>格式為： guid: {0} uri: {1} &gt;識別碼：{2}</p></td>
</tr>
<tr class="odd">
<td><p>updatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>上次更新此列之主體的識別碼。其一律為 1 (系統使用者) 因為 Active Directory 同步處理是這些項目的唯一來源。</p></td>
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
<th>資料欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinID affDescription&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>在 tblPrincipal.prinID 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

