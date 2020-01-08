---
title: Lync Server 2013：Tenants 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7da863aa2b713f874aba00f5a4f481f45fb79b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a>Lync Server 2013 中的 Tenants 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

[承租人] 資料表是一個支援資料表，可儲存各種租使用者的清單。 資料表中的每一筆記錄代表一個租使用者。

<div>


> [!NOTE]  
> 在內部部署中，CDR 使用內傳內部租使用者識別碼來指示不同的驗證類型，例如公用 IM 連線、同盟與匿名。



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
<th>左欄</th>
<th>資料類型</th>
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>TenantId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此租使用者識別碼的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>TenantKey</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td></td>
<td><p>允許的值：</p>
<ul>
<li><p>00000000-0000-0000-0000-000000000000 –企業版</p></li>
<li><p>00000000-0000-0000-0000-000000000001-同盟</p></li>
<li><p>00000000-0000-0000-0000-000000000002-匿名</p></li>
<li><p>00000000-0000-0000-0000-000000000003 –公用 IM 連線</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

