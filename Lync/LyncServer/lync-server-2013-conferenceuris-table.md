---
title: Lync Server 2013：ConferenceUris 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2b1ab44b564d649b6c8fb812077645c6dc13093
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferenceuris-table-in-lync-server-2013"></a>Lync Server 2013 中的 ConferenceUris 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

ConfereneUris 資料表是一個支援資料表，可儲存已參與在資料庫中的會議會話的各種會議 Uri 清單。 資料表中的每一筆記錄代表一個會議 URI。


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
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>時間戳記，內部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此會議 URI 的唯一號碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td></td>
<td><p>會議 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>求和</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ConferenceUri 的校驗和。 用來提高資料庫搜尋的速度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>URI 類型，例如會議： IM 會議的聊天或會議：音訊/視訊會議的音訊-視頻。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 資料表中</a>的 [UriTypes] 資料表。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

