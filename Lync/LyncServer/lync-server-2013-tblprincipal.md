---
title: Lync Server 2013：tblPrincipal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c24f963b34ef6184675e724496d7d45ca1d40d27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipal 包含所有的承擔者，包括使用者、資料夾和群組。

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
<td><p>prinID</p></td>
<td><p>int，not null</p></td>
<td><p>Principal ID。</p></td>
</tr>
<tr class="even">
<td><p>prinGuid</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>主要 GUID。 這會被廣泛用做為備用主鍵，因為它的意義是要與 Active Directory 網域服務空間相交。 （快取的主體的 GUID 等於對應的 Active Directory 物件 GUID。）</p></td>
</tr>
<tr class="odd">
<td><p>prinUri</p></td>
<td><p>Nvarchar （256），not null</p></td>
<td><p>主體 URI。 SIP 配置適用于使用者，而 ma grp 則用於幾乎所有其他專案。</p></td>
</tr>
<tr class="even">
<td><p>prinName</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>通用名稱。 僅供使用者類型使用。</p></td>
</tr>
<tr class="odd">
<td><p>prinDisplayName</p></td>
<td><p>NVarchar （256）</p></td>
<td><p>顯示名稱。 僅供使用者類型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinCompanyName</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>[公司名稱]。 僅供使用者類型使用。</p></td>
</tr>
<tr class="odd">
<td><p>prinEmail</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>電子郵件。 僅供使用者類型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>Nvarchar （384）</p></td>
<td><p>Principal 是其快取版本之 Active Directory 物件的功能變數名稱。 對於非 Active Directory 物件（例如系統使用者）的類型，可以是 Null。</p></td>
</tr>
<tr class="odd">
<td><p>prinADUserPrincipalName</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>使用者的使用者主體名稱（UPN）。 只能由一般的使用者類型使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDisabled</p></td>
<td><p>Smallint，not null</p></td>
<td><ul>
<li><p>0：主體處於作用中狀態。</p></li>
<li><p>1：主體已停用，因為使用者的 SIP 功能已停用。</p></li>
<li><p>2：由於相關聯的 AD 物件已遭刪除，主體會被刪除。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>prinTypeID</p></td>
<td><p>Smallint，not null</p></td>
<td><p>主體類型（從 tblPrincipalType 資料表）。</p></td>
</tr>
<tr class="even">
<td><p>prinPoolID</p></td>
<td><p>Int</p></td>
<td><p>主體的 Lync pool 分派。</p></td>
</tr>
<tr class="odd">
<td><p>prinPolicyID</p></td>
<td><p>Int</p></td>
<td><p>使用者的持續聊天伺服器原則值（如果有標籤類型原則的話）。</p></td>
</tr>
<tr class="even">
<td><p>prinAddedBy</p></td>
<td><p>int</p></td>
<td><p>建立者的主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>prinAddedOn</p></td>
<td><p>Bigint，not null</p></td>
<td><p>建立時間的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>prinUpdatedBy</p></td>
<td><p>int</p></td>
<td><p>上次更新此原則的主要使用者識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>prinUpdatedOn</p></td>
<td><p>Bigint，not null</p></td>
<td><p>上次更新的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>prinVerifiedOn</p></td>
<td><p>datetime、not null</p></td>
<td><p>主體上次 Active Directory 同步處理的日期和時間。</p></td>
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
<td><p>prinID</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>prinTypeID</p></td>
<td><p>在 tblPrincipalType ptypeID 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

