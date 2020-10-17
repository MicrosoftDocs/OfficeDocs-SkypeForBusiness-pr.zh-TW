---
title: Lync Server 2013：承租人表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 091a1db8f19e44277d71371aa14c14635e6fba6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521750"
---
# <a name="tenants-table-in-lync-server-2013"></a>Lync Server 2013 中的承租人表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

承租人資料表是一種支援資料表，可儲存各種承租人的清單。 表格中的每筆記錄代表一位承租人。

<div>


> [!NOTE]  
> 在內部部署中，CDR 使用內建承租人租使用者識別碼來表示不同的驗證類型，例如公用 IM 連線、同盟和匿名。



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別此租使用者識別碼的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td></td>
<td><p>允許的值：</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 –企業版</p></li>
<li><p>00000000-0000-0000-0000-000000000001 –同盟</p></li>
<li><p>00000000-0000-0000-0000-000000000002 –匿名</p></li>
<li><p>00000000-0000-0000-0000-000000000003 –公用 IM 連線能力</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

