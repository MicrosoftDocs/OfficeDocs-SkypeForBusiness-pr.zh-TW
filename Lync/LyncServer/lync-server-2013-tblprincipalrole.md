---
title: Lync Server 2013：tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615039(v=OCS.15)
ms:contentKeyID: 48185597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 560f454531060a8458c8c920a1e4c5921867f3e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalrole-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalRole

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipalRole 包含指派給節點的明確角色。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prinRoleNodeID</p></td>
<td><p>int，not null</p></td>
<td><p>角色所套用的節點識別碼。</p></td>
</tr>
<tr class="even">
<td><p>prinRolePrinID</p></td>
<td><p>int，not null</p></td>
<td><p>Principal ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int，not null</p></td>
<td><p>角色類型識別碼（從 tblRoleType）。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
<td><p>int，not null</p></td>
<td><p>上次更新此專案的主體 ID。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prinRoleNodeID, prinRolePrinID, prinRoleTypeID&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>在 tblNode 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePrinID</p></td>
<td><p>在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>在 tblRoleType rtypeID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

