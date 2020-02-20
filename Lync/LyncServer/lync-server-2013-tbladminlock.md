---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf1c04cb24f8fee668cd21f24fc7c9c1c5341d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a>Lync Server 2013 中的 tblAdminLock

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-06-25_

tblAdminLock 表格包含執行某些系統管理員命令所需的系統管理員鎖定。

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime，非 null</p></td>
<td><p>鎖定到期的日期和時間。擁有者可定期延長這個值。</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int，非 null</p></td>
<td><p>掌握鎖定之伺服器的識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int，非 null</p></td>
<td><p>掌握鎖定之主體的識別碼。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

