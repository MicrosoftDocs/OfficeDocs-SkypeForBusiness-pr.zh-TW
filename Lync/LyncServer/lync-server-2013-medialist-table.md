---
title: 'Lync Server 2013: MediaList 表格'
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
ms.openlocfilehash: 6fe16e903a1dfbc958336dca68903ca80770995d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a>Lync Server 2013 中的 mediaList 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2016年-07-12_

MediaList 表格是一種靜態表格，其中儲存了各種媒體類型清單。


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
<td><p><strong>MediaId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主要</p></td>
<td><p>值： 1-7</p></td>
</tr>
<tr class="even">
<td><p><strong>媒體業</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>靜態 MediaID 和媒體值的對應：</p>
<ul>
<li><p>1 – IM</p></li>
<li><p>2 – 檔案傳輸</p></li>
<li><p>3 – 遠端協助</p></li>
<li><p>4 – 應用程式共用</p></li>
<li><p>5 – 音訊</p></li>
<li><p>6 – 影片</p></li>
<li><p>7 – 應用程式邀請</p></li>
</ul></td>
</tr>
</tbody>
</table>


如果您嘗試判斷 LcsCDR.SessionDetailsView.MediaTypes 中的值的形式類型，您需要使用下列加入程式碼片段：

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

