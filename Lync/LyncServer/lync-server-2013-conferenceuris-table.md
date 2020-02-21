---
title: 'Lync Server 2013: ConferenceUris 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4310c90bdf3381bf9a5b357d6b45c9252ab7136b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceUris 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-05-25_

ConfereneUris 表格是一種支援資料表儲存各種會議記錄資料庫中的會議工作階段的 Uri 的清單。 在資料表中的每一筆記錄代表一個會議 URI。


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要</p></td>
<td><p>時間戳記，供內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別此會議 URI 的唯一號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td></td>
<td><p>會議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>總和檢查碼</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ConferenceUri 總和檢查碼。 用來增加資料庫搜尋的速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>Foreign</p></td>
<td><p>URI 類型，例如 IM 會議，或 conf:audio conf:chat-視訊的音訊/視訊會議。 請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a>表如需詳細資訊。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

