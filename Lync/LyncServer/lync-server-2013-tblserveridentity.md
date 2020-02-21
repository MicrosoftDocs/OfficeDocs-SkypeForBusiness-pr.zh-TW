---
title: 'Lync Server 2013: tblServerIdentity'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblServerIdentity
ms:assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558648(v=OCS.15)
ms:contentKeyID: 48184125
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2d6de094f9786cc5d6bb3b25635cc54a290851e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblserveridentity-in-lync-server-2013"></a>tblServerIdentity 在 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblServerIdentity 包含 Persistent Chat Server 集區中的作用中的聊天伺服器。

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
<td><p>serverID</p></td>
<td><p>int，非 null</p></td>
<td><p>伺服器識別碼。 從中央管理存放區，會對應至執行個體識別碼。</p></td>
</tr>
<tr class="even">
<td><p>serverAddress</p></td>
<td><p>nvarchar (256)，非 null</p></td>
<td><p>使用 Windows Communication Foundation 位址的伺服器位址。</p></td>
</tr>
<tr class="odd">
<td><p>serverLastPingTime</p></td>
<td><p>datetime</p></td>
<td><p>通道伺服器更新此列以證明其為執行中的最新時間。</p></td>
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
<td><p>serverID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

