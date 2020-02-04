---
title: Lync Server 2013：tblADUpdates
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
ms.openlocfilehash: cb4b5b73fb74c2337eeaa6b065396253a2cb0be4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731513"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladupdates-in-lync-server-2013"></a>Lync Server 2013 中的 tblADUpdates

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。

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
<td><p>prinGuid</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>已變更之物件的主要 GUID。</p></td>
</tr>
<tr class="even">
<td><p>prinADPath</p></td>
<td><p>Nvarchar （384），not null</p></td>
<td><p>物件的判別名。</p></td>
</tr>
<tr class="odd">
<td><p>prinAttributesChanged</p></td>
<td><p>bit、not null</p></td>
<td><p>如果物件至少有一個屬性已變更，則為 True。</p></td>
</tr>
<tr class="even">
<td><p>prinMembersChanged</p></td>
<td><p>bit、not null</p></td>
<td><p>如果成員資格變更，則為 True。</p></td>
</tr>
<tr class="odd">
<td><p>prinAffiliationsChanged</p></td>
<td><p>bit、not null</p></td>
<td><p>不使用。</p></td>
</tr>
<tr class="even">
<td><p>prinDeleted</p></td>
<td><p>bit、not null</p></td>
<td><p>如果已刪除物件，則為 True。</p></td>
</tr>
<tr class="odd">
<td><p>lastUpdated</p></td>
<td><p>datetime、not null</p></td>
<td><p>插入列的時間戳記。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

