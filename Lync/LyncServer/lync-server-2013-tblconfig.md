---
title: 'Lync Server 2013: tblConfig'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04138ad8e11a423fdbd3fc0cc2329ce00f9ffb39
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a>Lync Server 2013 中的 tblConfig

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblConfig 包含部分 Persistent Chat Server 不支援的組態，其中一個資料列。

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
<td><p>configLabel</p></td>
<td><p>nvarchar (255)，非 null</p></td>
<td><p>包含&quot;集區。&quot;</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>設定內容。</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID，非 null</p></td>
<td><p>資料庫執行個體的唯一識別碼。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>索引鍵

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
<td><p>configLabel</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

