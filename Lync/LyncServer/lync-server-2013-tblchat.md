---
title: 'Lync Server 2013: tblChat'
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
ms.openlocfilehash: c189e0a7d4c17b43d83a30f6dc9c282f5dbe3d24
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 中的 tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

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
<th>類型	</th>
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
<td><p>唯一序號 （每個節點識別碼） 定義聊天室的順序，由 tblLastChatId 表格產生的。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint，非 null</p></td>
<td><p>聊天訊息的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>使用者識別碼</p></td>
<td><p>int，非 null</p></td>
<td><p>海報的主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>位元，非 null</p></td>
<td><p>如果郵件是提醒訊息，則為 true。 如果它不是，則為 false。</p></td>
</tr>
<tr class="even">
<td><p>內容</p></td>
<td><p>nvarchar (max)，非 null</p></td>
<td><p>聊天室內容 （純文字版）。 內容通常是以純文字格式有下列例外：</p>
<ul>
<li><p>以 ma-filelink 表示的檔案： 連結。</p></li>
<li><p>連結以 HTML 元素表示 （雖然內容的類型不 html)。</p></li>
<li><p>故事編碼為"[STORY]...」 的格式類似。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>varchar(max)</p></td>
<td><p>聊天室內容 （RTF 版本）。 如果用戶端不會提供它可能是 Null。</p></td>
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
<td><p>&lt;channelID chatD&gt;</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

