---
title: Lync Server 2013：MediaList 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b92c8a0a6957eed00cf4e25f60ce2e0ff24d1fd2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013 中的 MediaList 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016-07-12_

MediaList 資料表是一個靜態資料表，可儲存各種媒體類型的清單。


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
<td><p><strong>MediaId</strong></p></td>
<td><p>Tinyint</p></td>
<td><p>首選</p></td>
<td><p>值：1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>媒體</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td></td>
<td><p>MediaID 和媒體值的靜態對應：</p>
<ul>
<li><p>1-IM</p></li>
<li><p>2-檔案傳輸</p></li>
<li><p>3-遠端協助</p></li>
<li><p>4–應用程式共用</p></li>
<li><p>5–音訊</p></li>
<li><p>6–影片</p></li>
<li><p>7– App 邀請</p></li>
</ul></td>
</tr>
</tbody>
</table>


如果您要嘗試判斷 LcsCDR 中的值的模態類型，則需要使用下列聯結程式碼片段：

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

