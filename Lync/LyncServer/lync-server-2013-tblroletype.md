---
title: Lync Server 2013： tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc32fe1142094d750b947a789b1e8c473eac8937
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536300"
---
# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 中的 tblRoleType

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-25_

tblRoleType 表格是一種靜態查閱表格，其中含有角色類型與其相關的權限組。

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
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>rtypeID</p></td>
<td><p>int，非 null</p></td>
<td><p>角色類型識別碼。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>角色類型描述。以下是四個可用的角色：</p>
<ul>
<li><p>Member：聊天室成員</p></li>
<li><p>Manager：聊天室管理員</p></li>
<li><p>Voiced：視聽中心聊天室簡報者</p></li>
<li><p>Creator：可建立聊天室</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>bigint，非 null</p></td>
<td><p>角色的權限組。使用的位元如下：</p>
<ul>
<li><p>2: 若角色可管理節點則為 True。</p></li>
<li><p>4: 若角色可建立子節點則為 True。</p></li>
<li><p>7: 若角色可加入聊天室 (或類別的子聊天室) 則為 True。</p></li>
<li><p>8: 若角色可在聊天室 (或類別的子聊天室) 中交談則為 True。</p></li>
<li><p>10: 若角色可讀取聊天記錄則為 True (即使未加入聊天室時亦可)。</p></li>
<li><p>11: 若角色可看到聊天室則為 True (可進一步依據範圍和可見度等因素來調整)。</p></li>
<li><p>12: 若角色可在視聽中心聊天室中交談則為 True。</p></li>
<li><p>13: 若角色可在檢視節點時略過可見度規則則為 True。</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>索引鍵

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
<td><p>rtypeID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

