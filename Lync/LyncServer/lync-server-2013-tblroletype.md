---
title: Lync Server 2013：tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a>Lync Server 2013 中的 tblRoleType

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-25_

tblRoleType 是一個靜態查閱表格，其中包含角色類型及其關聯的許可權集。

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
<td><p>rtypeID</p></td>
<td><p>int，not null</p></td>
<td><p>角色類型 ID。</p></td>
</tr>
<tr class="even">
<td><p>rtypeDesc</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>角色類型描述。 共有四個可用的角色：</p>
<ul>
<li><p>成員：聊天室成員</p></li>
<li><p>管理員：聊天室管理員</p></li>
<li><p>濁音： auditorium 聊天室的簡報者</p></li>
<li><p>建立者：可以建立聊天室</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtypeAllowedPermSet</p></td>
<td><p>Bigint，not null</p></td>
<td><p>角色的許可權集。 已使用的位數如下：</p>
<ul>
<li><p>2：如果角色可以管理節點，則為 True。</p></li>
<li><p>4：如果角色可以建立子節點，則為 True。</p></li>
<li><p>7：如果角色可以加入聊天室（或類別的子聊天室），則為 True。</p></li>
<li><p>8：如果角色可以在聊天室（或在子類別的 [兒童聊天室] 聊天室）中聊天，則為 True。</p></li>
<li><p>10： True，如果角色可以讀取聊天記錄，即使未加入聊天室也一樣。</p></li>
<li><p>11：如果角色可以查看聊天室，則為 True。 （例如範圍和可見度等因素進一步改進。）</p></li>
<li><p>12：如果角色可以在 auditorium 聊天室中聊天，則為 True。</p></li>
<li><p>13：如果角色在查看節點時可以略過可見度規則，則為 True。</p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a>機碼

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
<td><p>rtypeID</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

