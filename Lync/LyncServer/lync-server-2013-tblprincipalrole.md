---
title: 'Lync Server 2013: tblPrincipalRole'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4da9525e81856989c5d5046e43b2277ca6a8b2a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalRole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblPrincipalRole 包含指派給節點的明確角色。

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
<td><p>prinRoleNodeID</p></td>
<td><p>int，非 null</p></td>
<td><p>套用角色的節點識別碼。</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int，非 null</p></td>
<td><p>主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int，非 null</p></td>
<td><p>角色類型識別碼 （來自於 tblRoleType)。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>上次更新此項目之主體的識別碼。</p></td>
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
<td><p>&lt;prinRoleNodeID，prinRolePrinID prinRoleTypeID&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>在 tblNode.nodeID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>在 tblPrincipal.prinID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>在 tblRoleType.rtypeID 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

