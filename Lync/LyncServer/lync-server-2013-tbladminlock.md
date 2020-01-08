---
title: Lync Server 2013：tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdfbc28f440fe9bbcc186e685cd5efdb5f23498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a>Lync Server 2013 中的 tblAdminLock

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-25_

tblAdminLock 包含執行某些系統管理員命令所需的管理員鎖。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lockExpiresTime</p></td>
<td><p>datetime、not null</p></td>
<td><p>[鎖定到期日] 和 [時間]。 擁有者可以定期延伸此值。</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int，not null</p></td>
<td><p>擁有鎖定的伺服器 ID。</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int，not null</p></td>
<td><p>擁有鎖定之主體的 ID。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

