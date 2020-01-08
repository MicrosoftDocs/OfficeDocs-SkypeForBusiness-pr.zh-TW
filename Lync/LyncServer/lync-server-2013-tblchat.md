---
title: Lync Server 2013：tblChat
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 620dcb49580f8d19a8f262c22b1005e3cefeac4e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>Lync Server 2013 中的 tblChat

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblChat 包含所有聊天訊息。

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
<td><p>channelId</p></td>
<td><p>int，not null</p></td>
<td><p>節點識別碼。</p></td>
</tr>
<tr class="even">
<td><p>chatId</p></td>
<td><p>Bigint，not null</p></td>
<td><p>定義 tblLastChatId 表格產生的聊天室順序的唯一順序編號（每個節點識別碼）。</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>Bigint，not null</p></td>
<td><p>聊天訊息的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，not null</p></td>
<td><p>海報的主體識別碼。</p></td>
</tr>
<tr class="odd">
<td><p>isAlert</p></td>
<td><p>bit、not null</p></td>
<td><p>如果訊息是提醒訊息，則為 True。 如果不是，則為 False。</p></td>
</tr>
<tr class="even">
<td><p>內容</p></td>
<td><p>Nvarchar （max），not null</p></td>
<td><p>聊天內容（純文字版本）。 內容通常是純文字，但有下列例外狀況：</p>
<ul>
<li><p>檔案表示為 ma-filelink：連結。</p></li>
<li><p>連結是以 HTML 元素表示（雖然無法將內容類型視為 HTML）。</p></li>
<li><p>案例的編碼方式是「[情景] ...」格式。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>rtf</p></td>
<td><p>Varchar （max）</p></td>
<td><p>聊天內容（RTF 版本）。 如果用戶端無法提供，可能會是 Null。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>機碼

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelID, chatD&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

