---
title: Lync Server 2013： FocusJoinsAndLeaves 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500830"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a>Lync Server 2013 中的 FocusJoinsAndLeaves 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

此表格中的每一筆記錄都包含有關一位使用者的加入的 CDR 資訊，並留下一次會議的資訊。 每個會議都會在每次使用者加入和離開會議時，以一筆記錄呈現在此表格中。


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
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要，外部</p></td>
<td><p>會議執行個體的時間。 與 <strong>SessionIdSeq</strong> 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>用於辨識執行個體的 ID 號碼。 與 <strong>SessionIdTime</strong> 搭配使用，以唯一識別會議實例。 如需詳細資訊，請參閱 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 [會議] 表格。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要，外部</p></td>
<td><p>工作階段要求的時間。 其會與 <strong>SessionIdSeq</strong> 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要，外部</p></td>
<td><p>用來識別工作階段的識別碼。 會與 <strong>SessionIdTime</strong> 搭配使用，專門用於識別工作階段。 如需詳細資訊，請參閱 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的對話方塊表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>用於識別此使用者的唯一號碼， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 的 [使用者] 表格中</a>參照。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>如果使用者同時在多部電腦或裝置上登入，則會使用 <strong>UserInstance</strong> 來唯一地識別使用者/裝置組合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>使用者是否從內部登入。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserRole</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>此使用者在會議中的角色，例如簡報者或出席者。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此使用者加入會議的時間。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此使用者離開會議的時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>使用者的用戶端軟體版本，參考 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表格</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>唯一</p></td>
<td></td>
<td><p>會議中所使用之端點的全域唯一識別碼 (GUID) 。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

