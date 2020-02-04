---
title: Lync Server 2013：Locations 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a>Lync Server 2013 中的 Locations 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

每個記錄代表緊急呼叫中的一個位置參照，就像是 E9-1-1 通話。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話要求的時間。 與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>位置</strong></p></td>
<td><p>Nvarchar （max）</p></td>
<td></td>
<td><p>緊急通話的位置。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

