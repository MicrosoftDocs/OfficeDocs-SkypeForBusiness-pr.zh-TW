---
title: Lync Server 2013： UserAgent view
description: Lync Server 2013： UserAgent view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent view
ms:assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721862(v=OCS.15)
ms:contentKeyID: 49733795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9fc5ef2ec01b50f3714dca3690d0844286baaef5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558859"
---
# <a name="useragent-view-in-lync-server-2013"></a>Lync Server 2013 中的 UserAgent 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

UserAgent View 儲存的使用者代理程式的相關資訊，包含在資料庫中有記錄的會話中。 此視圖已引進于 Microsoft Lync Server 2013。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UserAgentKey</p></td>
<td><p>int</p></td>
<td><p>用於識別此使用者代理程式的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p>UserAgent</p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p>UAType</p></td>
<td><p>Smallint</p></td>
<td><p>使用者代理程式的類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</p></td>
</tr>
<tr class="even">
<td><p>UACategory</p></td>
<td><p>Nvarchar (64) </p></td>
<td><p>使用者代理所屬的類別。 例如，Conferencing_Attendant_1 .0 的使用者代理程式屬於 UACategory CAA。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

