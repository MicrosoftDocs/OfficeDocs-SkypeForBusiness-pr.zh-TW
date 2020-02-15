---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9d5122b375b4906320f254179ce101652ad6db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42047996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblPrincipal 包含所有主體，包括使用者、資料夾及群組。

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
<td><p>prinGuid</p></td>
<td><p>GUID，非 null</p></td>
<td><p>主體 GUID。 這是廣泛用來作為替代的主索引鍵因為其意義透過跨越到 Active Directory 網域服務空間。 （如快取的主體 GUID 是等於相對應的 Active Directory 物件的 GUID）。</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>主體 URI。SIP 配置可用於使用者，而 ma-grp 幾乎可用於其他所有項目。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>一般名稱。僅可用於使用者類型。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>Nvarchar (256)</p></td>
<td><p>顯示名稱。僅可用於使用者類型。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>公司名稱。僅可用於使用者類型。</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>電子郵件。僅可用於使用者類型。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>nvarchar (384)</p></td>
<td><p>Active Directory 物件 (主體為快取版本) 的網域名稱。非 Active Directory 物件的類型可以是 Null (例如系統使用者)。</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>使用者的使用者主體名稱 (UPN)。僅可用於一般使用者類型。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>smallint，非 null</p></td>
<td><ul>
<li><p>0：主體為作用中狀態。</p></li>
<li><p>1：主體已停用，因為使用者的 SIP 功能已停用。</p></li>
<li><p>2：主體已刪除，因為相關聯的 AD 物件已刪除。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>smallint，非 null</p></td>
<td><p>主體類型 (參照 tblPrincipalType 表格)。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>臨界值</p></td>
<td><p>主體的 Lync 集區指派。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>臨界值</p></td>
<td><p>對於使用者來說，如果出現標記類型原則的常設聊天室伺服器原則值。</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>建立者的主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>建立時間的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>最近一次進行更新之主體的識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>bigint，非 null</p></td>
<td><p>最近一次更新的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime，非 null</p></td>
<td><p>最近一次主體之 Active Directory Sync 重新整理的日期與時間。</p></td>
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
<td><p>prinID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>在 tblPrincipalType.ptypeID 表格中查閱外部索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

