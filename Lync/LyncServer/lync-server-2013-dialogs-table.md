---
title: Lync Server 2013：Dialogs 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a25ae1d298f1cf5908c4669a78485491fadd617d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a>Lync Server 2013 中的 Dialogs 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

對話方塊表格是一個支援資料表，可儲存點對點工作階段之 DialogIDs 的相關資訊。


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
<td><p>首選</p></td>
<td><p>會話要求的時間;與 SessionIDSeq 搭配使用，可唯一識別會話。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>識別會話的識別碼編號。 與 SessionIDTime 搭配使用，可唯一識別會話。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ExternalID 的校驗和。 此欄位可用來提高資料庫搜尋的速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>Varbinary （775）</p></td>
<td><p> </p></td>
<td><p>SIP 對話方塊識別碼，儲存為二進位。 二進位檔案的格式為：</p>
<p>對話方塊; 從標籤; 到標籤</p>
<p>您可以使用下列語法，將此資料轉換成文字格式：</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

