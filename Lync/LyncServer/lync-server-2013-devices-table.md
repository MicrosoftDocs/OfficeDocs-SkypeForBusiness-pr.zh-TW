---
title: Lync Server 2013：Devices 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Devices table
ms:assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398351(v=OCS.15)
ms:contentKeyID: 48184169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f78e0b4ba3bb5271a2de43e423dfa4b3baf17cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="devices-table-in-lync-server-2013"></a>Lync Server 2013 中的 Devices 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

[裝置] 資料表是支援資料表。 每筆記錄儲存一個裝置（電話機）的相關資訊。


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
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別這個硬體版本的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>[Manufacturerid</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>此裝置的製造商。 如需詳細資訊，請參閱<a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中</a>的 [製造商] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HardwareVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>此裝置的硬體版本。 如需詳細資訊，請參閱<a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中</a>的 [HardwareVersions] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>MacAddress</strong></p></td>
<td><p>Bigint</p></td>
<td></td>
<td><p>MAC 位址</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

