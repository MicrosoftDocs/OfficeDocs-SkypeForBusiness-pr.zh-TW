---
title: Lync Server 2013：tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalMemberDifference
ms:assetid: 0b94f555-6888-4fe0-a048-4660a2513276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558612(v=OCS.15)
ms:contentKeyID: 48183379
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5db403431c182e3f5bb8e7a3fabaa04cd2a94d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipalmemberdifference-in-lync-server-2013"></a>Lync Server 2013 中的 tblPrincipalMemberDifference

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblPrincipalMemberDifference 包含尚未由後續 Active Directory 網域服務同步處理步驟處理的群組成員資格變更（新增和移除的成員）。

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
<td><p>prinGuid</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>已變更之群組的主要 GUID。</p></td>
</tr>
<tr class="even">
<td><p>memberADPath</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>成員的判別名。</p></td>
</tr>
<tr class="odd">
<td><p>memberRemoved</p></td>
<td><p>bit、not null</p></td>
<td><p>如果成員已新增，則為 False。 如果成員已移除，則為 True。</p></td>
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
<td><p>&lt;prinGuid, memberADPath&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

