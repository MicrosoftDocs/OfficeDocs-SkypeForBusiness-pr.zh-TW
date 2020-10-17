---
title: Lync Server 2013： tblPrincipalAffiliations
description: Lync Server 2013： tblPrincipalAffiliations。
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
ms.openlocfilehash: 01c373147a58300e64f22e60e989a777c59b2653
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547479"
---
# <a name="tblprincipalaffiliations-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalAffiliations

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipalAffiliations 包含主體隸屬關係，描述位置中的成員資格，包括 Active directory 網域服務安全性群組、Active Directory 容器中的網域。

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
<td><p>principalID</p></td>
<td><p>int，非 null</p></td>
<td><p>附屬主體的識別碼。</p></td>
</tr>
<tr class="even">
<td><p>affiliationID</p></td>
<td><p>int，非 null</p></td>
<td><p>代表隸屬關係之主體的識別碼。 除了系統使用者類型) 之外，每個主體 (都具有自我從屬。</p></td>
</tr>
<tr class="odd">
<td><p>index</p></td>
<td><p>int，非 null</p></td>
<td><p>指數。 「自我隸屬關係」的值是-1，另一個隸屬關係會依序從每個 &lt; principalID、affiliationId bucket 中的1增加 &gt; 。</p></td>
</tr>
<tr class="even">
<td><p>updatedBy</p></td>
<td><p>int，非 null</p></td>
<td><p>進行最新更新的主體。 這通常是1，表示 Active Directory 同步處理。</p></td>
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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;principalID、index、affiliationID&gt;</p></td>
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

