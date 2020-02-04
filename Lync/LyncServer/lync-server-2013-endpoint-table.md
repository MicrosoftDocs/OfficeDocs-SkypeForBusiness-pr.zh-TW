---
title: Lync Server 2013：Endpoint 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Endpoint table
ms:assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398327(v=OCS.15)
ms:contentKeyID: 48184098
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11da225da1a8120f5de7ac21b3beb318326601f9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013 中的 Endpoint 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

端點資料表是一個支援資料表，可儲存已參與在資料庫中記錄會話之端點的相關資訊。 資料表中的每一筆記錄代表一個端點。


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
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此端點的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>名稱</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>唯一</p></td>
<td><p>端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OS</strong></p></td>
<td><p>Nvarchar</p></td>
<td><p> </p></td>
<td><p>端點的作業系統（OS）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>Nvarchar</p></td>
<td></td>
<td><p>端點的 CPU 名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>端點的 CPU 核心數。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUProcessorSpeed</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>端點的 CPU 處理器速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VirtualizationFlag</strong></p></td>
<td><p>Tinyint</p></td>
<td></td>
<td><p>表示系統是否正在虛擬化環境中執行的位標誌：</p>
<ul>
<li><p>0x0000 –無</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002-VMWare</p></li>
<li><p>0x0004 –虛擬電腦</p></li>
<li><p>0x0008 – Xen 電腦</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

