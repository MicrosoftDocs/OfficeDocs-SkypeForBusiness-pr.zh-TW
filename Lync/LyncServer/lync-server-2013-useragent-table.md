---
title: 'Lync Server 2013: UserAgent 表格'
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
ms.openlocfilehash: 1b9abca1aaaff164759f195f8f60de335e279335
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="useragent-table-in-lync-server-2013"></a>Lync Server 2013 中的 UserAgent 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-05-25_

UserAgent 表格是一種支援資料表儲存的記錄資料庫中的工作階段的各種使用者代理程式清單。 在資料表中的每一筆記錄代表一個使用者代理程式


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
<th><strong>主索引鍵 /</strong></th>
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
<td><p>nvarchar(256)</p></td>
<td><p>Unique</p></td>
<td><p>使用者代理字串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1 是中繼伺服器。</p>
<p>2 是 A / V 會議伺服器。</p>
<p>4 是 Lync。</p>
<p>8 是 IP 電話。</p>
<p>16 是 Live Meeting 主控台。</p>
<p>32 是部署驗證工具 (DVT)。</p>
<p>64 是 Macintosh 電腦上的 Lync。</p>
<p>128 是 Office Communications Server 2007 R2 語音應答。</p>
<p>256 是會議宣告服務。</p>
<p>512 是會議自動語音應答。</p>
<p>1024 是回應群組應用程式。</p>
<p>2048 是外部語音控制。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

