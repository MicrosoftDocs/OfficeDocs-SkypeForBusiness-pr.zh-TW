---
title: Lync Server 2013：tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalAffiliations
ms:assetid: 45fd8484-5837-44d2-85bb-45c83546607c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558642(v=OCS.15)
ms:contentKeyID: 48183993
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3976b98fddc96ad08f3de4413bf8f38ec3525496
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalAffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipalAffiliations 包含描述位置中的成員資格的主要隸屬關係，包括 Active directory 網域服務安全性群組（在 Active Directory 容器中，在網域中）。

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>principalID</p></td>
<td><p>int，not null</p></td>
<td><p>附屬原則的 ID。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，not null</p></td>
<td><p>代表隸屬關係的承擔者 ID。 每個主體（除系統使用者類型之外）都有自我隸屬關係。</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int，not null</p></td>
<td><p>Index. 自我隸屬關係的值是-1，而其他隸屬關係則會依序從每個&lt;PrincipalID、affiliationId&gt; bucket 中的1增加。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，not null</p></td>
<td><p>已進行最新更新的主體。 這通常是1，這表示 Active Directory 同步處理。</p></td>
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
<th>分欄</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID、index、affiliationID&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

