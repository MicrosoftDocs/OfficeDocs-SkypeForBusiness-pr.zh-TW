---
title: 'Lync Server 2013: Principalaffiliations'
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
ms.openlocfilehash: 0a57e4a3c7a5fdcc1825c140cb6e26f8cede8dc1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214439"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 Principalaffiliations

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

Principalaffiliations 包含主體關係，可描述位置，包括 Active Directory 網域服務的安全性群組，在 Active Directory 容器，在網域中的成員資格。

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
<td><p>principalID</p></td>
<td><p>int，非 null</p></td>
<td><p>相關主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，非 null</p></td>
<td><p>代表關係的主體識別碼。 每個主體 （除了系統使用者類型） 都有也自我 affiliation。</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int，非 null</p></td>
<td><p>索引。 自我關係的值為-1，而且其他關係的也會增加循序 1 中每個&lt;principalID，affiliationId&gt; bucket。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>最近一次更新的主體。 這通常是 1，這表示 Active Directory 同步處理。</p></td>
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
<th>Columns</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID、 索引、 affiliationID&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>principalID</p></td>
<td><p>在 tblPrincipal.prinID 表格中查閱外部索引鍵。</p></td>
</tr>
<tr class="odd">
<td><p>affiliationID</p></td>
<td><p>在 tblPrincipal.prinID 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

