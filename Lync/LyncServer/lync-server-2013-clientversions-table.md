---
title: Lync Server 2013： ClientVersions 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions table
ms:assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398356(v=OCS.15)
ms:contentKeyID: 48184176
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8987bc1078dfdfaec8cccdb6625ceb9846ef6a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499170"
---
# <a name="clientversions-table-in-lync-server-2013"></a>Lync Server 2013 中的 ClientVersions 表格

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。


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
<th>索引鍵/索引</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>VersionId</strong></p></td>
<td><p><strong>int</strong></p></td>
<td><p>主要</p></td>
<td><p>用於識別此用戶端類型及版本的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>版本</strong></p></td>
<td><p><strong>Nvarchar (256) </strong></p></td>
<td></td>
<td><p>版本名稱。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>指出工作階段所使用的用戶端類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表格</a> 。</p>
<p>此欄位是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

