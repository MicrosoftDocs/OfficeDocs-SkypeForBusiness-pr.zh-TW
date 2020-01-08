---
title: Lync Server 2013：ErrorDef 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorDef table
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398503(v=OCS.15)
ms:contentKeyID: 48184403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef21484d564419a5ab5cce7373ceb0b0b71e4a29
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errordef-table-in-lync-server-2013"></a>Lync Server 2013 中的 ErrorDef 表格

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-05-25_

ErrorDef 表格會儲存可能發生的每個錯誤類型的相關資訊。 每一筆記錄都是一種錯誤類型。


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>首選</p></td>
<td><p>標識此類型錯誤的唯一識別碼編號。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>與此錯誤相關聯的標準 SIP 回應程式碼。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Microsoft 診斷 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>Int</p></td>
<td><p>外</p></td>
<td><p>通話的類型。 如需詳細資訊，請參閱<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中</a>的 [CallType] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>Varbinary （33）</p></td>
<td><p> </p></td>
<td><p>失敗的要求類型。</p>
<p>您可以使用下列語法，將此資料轉換成文字格式：</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>Varbinary （257）</p></td>
<td><p> </p></td>
<td><p>失敗之要求的內容類型。</p>
<p>您可以使用此 syntaxt，將此資料轉換成文字格式：</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

