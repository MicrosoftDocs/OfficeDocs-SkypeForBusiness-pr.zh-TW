---
title: Lync Server 2013：tblComplianceData
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
ms.openlocfilehash: 48516f307a084d30fde06a03548119e0ada34d6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancedata-in-lync-server-2013"></a>Lync Server 2013 中的 tblComplianceData

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblComplianceData 包含尚未由合規性配接器處理的合規性事件。

### <a name="columns"></a>分欄

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>類型</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>Bigint，not null</p></td>
<td><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>Smalldatetime，not null</p></td>
<td><p>插入的時間（對於 cmplType = 9，未來可能是目前的時間），因為該專案只是該案例中的預留位置。</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int，not null</p></td>
<td><p>合規性事件的類型：</p>
<ul>
<li><p>1：聊天</p></li>
<li><p>2： Backchat</p></li>
<li><p>3：檔案下載</p></li>
<li><p>4：檔案上傳</p></li>
<li><p>9：暫存檔案傳輸</p></li>
<li><p>10：聊天刪除（使用 [取代]）</p></li>
<li><p>11：聊天清除</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>Bigint，not null</p></td>
<td><p>事件的時間戳記。</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>Nvarchar （255），not null</p></td>
<td><p>通道統一資源識別項（URI）。</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>Bigint</p></td>
<td><p>聊天識別碼（對應至 tblChat chatId 表）。</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int，not null</p></td>
<td><p>海報的主體識別碼（對應至 tblPrincipal prinID）。</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>Nvarchar （255），not null</p></td>
<td><p>使用者 URI。</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>Nvarchar （max）</p></td>
<td><p>訊息（編碼依據 cmplType）。</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>機碼

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

