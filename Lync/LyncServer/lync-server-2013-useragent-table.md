---
title: Lync Server 2013： UserAgent 表格
description: Lync Server 2013： UserAgent 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserAgent table
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398939(v=OCS.15)
ms:contentKeyID: 48185582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b701d8384313d0267dd566e0c32242f6cc077472
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558889"
---
# <a name="useragent-table-in-lync-server-2013"></a>Lync Server 2013 中的 UserAgent 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

UserAgent 表格是一種支援表格，可儲存已參與資料庫中記錄之會話的各種使用者代理程式清單。 資料表中的每一筆記錄都代表一個使用者代理程式


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>欄</strong></th>
<th><strong>資料類型</strong></th>
<th><strong>索引鍵/索引</strong></th>
<th><strong>詳細資料</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>主要</p></td>
<td><p>用於識別此使用者代理程式的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>Unique</p></td>
<td><p>使用者代理程式字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>Smallint</p></td>
<td><p> </p></td>
<td><p>1是轉送伺服器。</p>
<p>2是 A/V 的會議服務器。</p>
<p>4是 Lync。</p>
<p>8是 IP 電話。</p>
<p>16是 Live Meeting 主控台。</p>
<p>32是部署驗證工具 (DVT) 。</p>
<p>64是 Macintosh 電腦上的 Lync。</p>
<p>128是 Office 通訊伺服器 2007 R2 語音應答。</p>
<p>256為會議宣告服務。</p>
<p>512為會議自動語音應答。</p>
<p>1024是回應群組應用程式。</p>
<p>2048超出語音控制。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

