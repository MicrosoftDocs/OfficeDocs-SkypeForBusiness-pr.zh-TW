---
title: Lync Server 2013： tblADUpdates
description: Lync Server 2013： tblADUpdates。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADUpdates
ms:assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615033(v=OCS.15)
ms:contentKeyID: 48185227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ab4418a10eac283d0f39d09b1c1fe15a32b2e68
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573679"
---
# <a name="tbladupdates-in-lync-server-2013"></a>Lync Server 2013 中的 tblADUpdates

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。

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
<td><p>prinGuid</p></td>
<td><p>GUID，非 null</p></td>
<td><p>已變更之物件的主體 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>Nvarchar (384) ，非 null</p></td>
<td><p>物件的辨別名稱。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果物件的至少一個屬性已變更。</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果成員資格變更。</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>位元，非 null</p></td>
<td><p>不會使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果物件已刪除。</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime，非 null</p></td>
<td><p>插入列時的時間戳記。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

