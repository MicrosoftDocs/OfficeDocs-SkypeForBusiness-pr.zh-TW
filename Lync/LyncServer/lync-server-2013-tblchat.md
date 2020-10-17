---
title: Lync Server 2013： tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f68c638b16ae0e7a253c063351784ce9f7d4d7c5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509470"
---
# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 中的 tblChat

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblChat 包含所有聊天訊息。

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
<th>類型</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>channelId</p></td>
<td><p>int，非 null</p></td>
<td><p>節點識別碼。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>bigint，非 null</p></td>
<td><p>定義聊天室順序) （由 tblLastChatId table 產生）的唯一順序編號 (每個節點識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint，非 null</p></td>
<td><p>聊天訊息的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，非 null</p></td>
<td><p>海報的主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>位元，非 null</p></td>
<td><p>True 是表示如果郵件是提醒訊息。 如果不是，則為 False。</p></td>
</tr>
<tr class="even">
<td><p>內容</p></td>
<td><p>Nvarchar (max) ，非 null</p></td>
<td><p> (純文字版本) 聊天內容。 內容通常會以純文字顯示，但有下列例外：</p>
<ul>
<li><p>檔案表示為 ma-filelink：連結。</p></li>
<li><p>連結會呈現為 HTML 元素 (，但無法將內容類型視為 HTML) 。</p></li>
<li><p>故事會編碼為 "[本文] ..."-like 格式。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Rtf</p></td>
<td><p>Varchar (max) </p></td>
<td><p> (RTF 版本) 聊天內容。 如果用戶端不提供此值，則可以為 Null。</p></td>
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
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

