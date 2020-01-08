---
title: Lync Server 2013：Mcus 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mcus table
ms:assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425742(v=OCS.15)
ms:contentKeyID: 48183674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf0a34d24bf60770f2b1e2664a89993f5917d854
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcus-table-in-lync-server-2013"></a>Lync Server 2013 中的 Mcus 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

Mcus 資料表是支援資料表。 每筆記錄儲存一個會議服務的相關資訊。 這些可能包括 IM 會議服務和電話會議服務（在前端伺服器上以進程的方式執行），以及網路會議服務和 A/V 會議服務。


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
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此會議服務器的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p><strong>McuTypeId</strong></p></td>
<td><p>inyint</p></td>
<td><p> 外</p></td>
<td><p>會議服務器類型，例如會議：聊天（適用于 Im）或會議：音訊影片。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

