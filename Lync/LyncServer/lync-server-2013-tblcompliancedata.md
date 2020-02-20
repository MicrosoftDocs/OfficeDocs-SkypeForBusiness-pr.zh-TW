---
title: 'Lync Server 2013: tblComplianceData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558606(v=OCS.15)
ms:contentKeyID: 48183308
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc2858ede3d1d3ccd1cc9af44c564fcac3424f35
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013 中的 tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-12_

tblComplianceData 包含法規相符性介面卡尚未處理的規範事件。

### <a name="columns"></a>Columns

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>類型	</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>bigint，非 null</p></td>
<td><p>事件識別碼。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime，非 null</p></td>
<td><p>插入時間 (若是 cmplType=9，則可能是未來很久以後，因為此項目在此情況下只是預留位置)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int，非 null</p></td>
<td><p>規範事件的類型：</p>
<ul>
<li><p>1: 聊天</p></li>
<li><p>2: 對話</p></li>
<li><p>3: 檔案下載</p></li>
<li><p>4: 檔案上傳</p></li>
<li><p>9: 暫時性檔案傳輸</p></li>
<li><p>10: 聊天刪除 (及取代)</p></li>
<li><p>11: 聊天清除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint，非 null</p></td>
<td><p>事件的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar (255)，非 null</p></td>
<td><p>通道統一資源識別項 (URI)。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>聊天識別碼 (對應至 tblChat.chatId 表格)。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int，非 null</p></td>
<td><p>發佈者的主體識別碼 (對應至 tblPrincipal.prinID 表格)。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar (255)，非 null</p></td>
<td><p>使用者 URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>訊息 (編碼取決於 cmplType)。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>索引鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>主索引鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

