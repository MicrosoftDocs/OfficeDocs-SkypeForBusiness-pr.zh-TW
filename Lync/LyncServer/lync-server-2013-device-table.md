---
title: Lync Server 2013： Device 表格
description: Lync Server 2013： Device table。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device table
ms:assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398930(v=OCS.15)
ms:contentKeyID: 48185544
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46de64a49eace52d62cbd6384fcae680b5c511b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575639"
---
# <a name="device-table-in-lync-server-2013"></a>Lync Server 2013 中的裝置表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

Device 表是一種支援資料表，可儲存各種捕獲或呈現裝置的相關資訊。 資料表中的每一筆記錄都代表一個裝置。


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
<td><p><strong>DeviceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別此裝置的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceName</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>DeviceName + DeviceType 是唯一的</p></td>
<td><p>裝置名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceType</strong></p></td>
<td><p>位</p></td>
<td><p>DeviceName + DeviceType 是唯一的</p></td>
<td><p>裝置類型。 1是捕獲裝置，0代表呈現裝置。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

