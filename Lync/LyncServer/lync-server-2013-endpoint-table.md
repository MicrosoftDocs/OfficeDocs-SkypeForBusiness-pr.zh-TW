---
title: Lync Server 2013：端點表格
description: Lync Server 2013： Endpoint table。
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
ms.openlocfilehash: 614872eee41b5d8e56da4b96cf5bbe3a4a1cf4d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575619"
---
# <a name="endpoint-table-in-lync-server-2013"></a>Lync Server 2013 中的端點表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

端點表是一種支援資料表，可儲存已參與資料庫中記錄之會話之端點的相關資訊。 資料表中的每一筆記錄都代表一個端點。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EndpointKey</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別此端點的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>名稱</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>Unique</p></td>
<td><p>端點名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>作業系統</strong></p></td>
<td><p>Nvarchar (128) </p></td>
<td><p> </p></td>
<td><p>端點 (作業系統) 。</p></td>
</tr>
<tr class="even">
<td><p><strong>CPUName</strong></p></td>
<td><p>Nvarchar (128) </p></td>
<td></td>
<td><p>端點的 CPU 名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUNumberOfCores</strong></p></td>
<td><p>Smallint</p></td>
<td></td>
<td><p>端點的 CPU 核心數目。</p></td>
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
<td><p>指出系統是否在虛擬化環境中執行的位旗標：</p>
<ul>
<li><p>0x0000 –無</p></li>
<li><p>0x0001 – HyperV</p></li>
<li><p>0x0002 – VMWare</p></li>
<li><p>0x0004 –虛擬 PC</p></li>
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

