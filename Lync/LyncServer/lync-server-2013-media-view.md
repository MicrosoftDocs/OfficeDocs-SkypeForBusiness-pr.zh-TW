---
title: Lync Server 2013：媒體視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1ec4b80cc790068029a286a54d26a59a35fc125
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a>Lync Server 2013 中的媒體視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

媒體視圖儲存點對點工作階段中所使用之一個媒體類型的相關資訊。 如果使用一個以上的媒體類型，則資料表中的多筆記錄會代表一個會話。 此視圖已在 Microsoft Lync Server 2013 中推出。

<div>


> [!NOTE]  
> 媒體視圖不應該用來計算會話的媒體持續時間。 此視圖包含會話中媒體交換的信號詳細資料。 媒體交換是由邀請要求所完成，而 StartTime 則會指出邀請的傳送時間。邀請時間不一定代表媒體開始時間，因為媒體只有在接受會話之後才會啟動。



</div>

媒體視圖在[Lync Server 2013](lync-server-2013-sessiondetails-view.md)的 [SessionDetails] 視圖中，除了下面所列的所有欄之外，還有其中一個資料行。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>媒體</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>媒體類型。 如需詳細資訊，請參閱<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中</a>的 [MediaList] 資料表。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>媒體要求的傳送時間。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>會話的結束時間。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

