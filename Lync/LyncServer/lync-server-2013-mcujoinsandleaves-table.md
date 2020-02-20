---
title: 'Lync Server 2013: McuJoinsAndLeaves 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 138fe5f989fb11986c3db6e134fa7f975a95c96e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013 中的 McuJoinsAndLeaves 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

此表格中的每一筆記錄包含一個組合的使用者加入或離開及會議伺服器的通話詳細資料。 例如，如果使用者加入會議，其中包含 web 會議與音訊/視訊的項目，會針對該使用者的 web 會議加入，建立一筆記錄，另一筆記錄會加以建立使用者的音訊/視訊會議加入。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>主索引鍵 /</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會議執行個體的時間。 <strong>SessionIdSeq</strong>搭配使用來唯一地識別會議執行個體。 請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用於辨識執行個體的 ID 號碼。 搭配<strong>SessionIdTime</strong>用來唯一地識別會議執行個體。 請參閱<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的會議表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用於識別此使用者的唯一號碼。 請參閱如需詳細資訊，<a href="lync-server-2013-users-table.md">使用者在 Lync Server 2013 中的表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Mcuuserinstance 會</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>如果使用者登入多部電腦或裝置一次，mcuuserinstance 會識別唯一的使用者/裝置組合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>位元</p></td>
<td><p> </p></td>
<td><p>是否使用者從 PSTN 加入與否。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用於識別此會議伺服器的唯一號碼。 請參閱<a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表格</a>如需詳細資訊。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Foreign</p></td>
<td><p>工作階段要求的時間。 其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用來識別工作階段的識別碼。 會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。 <a href="lync-server-2013-dialogs-table.md">Dialogs 表格 Lync Server 2013 中的</a>如需詳細資訊，請參閱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此使用者加入此會議伺服器的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此使用者離開此會議伺服器的時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>在會議中使用指定的用戶端軟體版本號碼的識別碼。 請參閱<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>如需詳細資訊。</p>
<p>Microsoft Lync Server 2013 中已採用此欄位。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

