---
title: Lync Server 2013：tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558616(v=OCS.15)
ms:contentKeyID: 48183513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0fc42a3151b5863885fdb3853ea529503e18a6b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastchatid-in-lync-server-2013"></a>Lync Server 2013 中的 tblLastChatId

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblLastChatId 包含每位使用者所產生（並在 tblChat 資料表中使用）的最後一個聊天 ID。

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
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>個</p></td>
<td><p>int，not null</p></td>
<td><p>[Node ID] （聊天室-僅限類型）。</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>Bigint，not null</p></td>
<td><p>上次使用的聊天 ID。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;lastChatID&gt;</p></td>
<td><p>主鍵（只有一個代表可充分處理）。</p></td>
</tr>
<tr class="even">
<td><p>個</p></td>
<td><p>在 tblNode 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的 tblChat](lync-server-2013-tblchat.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

