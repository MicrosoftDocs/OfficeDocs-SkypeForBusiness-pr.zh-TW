---
title: Lync Server 2013：媒體資料表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8b3aaff56e782307f3146fdcee7d4410340198
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a>Lync Server 2013 中的媒體資料表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

每個記錄代表點對點工作階段中所使用的一種媒體類型。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。

<div>


> [!NOTE]  
> 媒體資料表不應該用來計算會話的媒體持續時間。 此表格包含會話中媒體交換的信號詳細資料。 媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在 sessionee 接受會話之後才會啟動。 [EndTime] 通常代表這個會話的結束時間。



</div>


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主要、外部</p></td>
<td><p>會話要求的時間。 與<strong>SessionIdSeq</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主要、外部</p></td>
<td><p>識別會話的識別碼編號。 與<strong>SessionIdTime</strong>搭配使用，可唯一識別會話。 如需詳細資訊，請參閱<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中</a>的 [對話方塊] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaId</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>主要、外部</p></td>
<td><p>識別這個媒體類型的唯一號碼。 如需詳細資訊，請參閱<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中</a>的 [MediaList] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>開始</strong></p></td>
<td><p>datetime</p></td>
<td><p>首選</p></td>
<td><p>這是傳送媒體要求的時間，而不是真正的媒體啟動時間。 <strong>StartTime</strong>包含會話設定時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td></td>
<td><p>這是會話的結束時間。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

