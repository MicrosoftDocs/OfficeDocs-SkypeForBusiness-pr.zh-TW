---
title: Lync Server 2013：UserSite 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: UserSite table
ms:assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398256(v=OCS.15)
ms:contentKeyID: 48183552
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dfb3e3d99775405ce4a09df706bec8eea59f6f9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="usersite-table-in-lync-server-2013"></a>Lync Server 2013 中的 UserSite 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2010-11-09_

UserSite 資料表是支援資料表。 每個記錄代表 [網路設定] 中定義的一個使用者網站。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>左欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserSiteKey</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別使用者網站的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSiteName</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p>唯一</p></td>
<td><p>使用者網站的名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegionKey</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>從<a href="lync-server-2013-region-table.md">Lync Server 2013 的地區資料表中</a>參考。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

