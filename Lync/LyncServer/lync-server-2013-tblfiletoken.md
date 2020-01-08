---
title: Lync Server 2013：tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978175"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a>Lync Server 2013 中的 tblFileToken

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblFileToken 包含臨時權杖以進行檔案傳輸。

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fileToken</p></td>
<td><p>Nvarchar （50），not null</p></td>
<td><p>唯一標記（GUID）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenUserID</p></td>
<td><p>int，not null</p></td>
<td><p>要轉移檔案之主體的 ID。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenChannelID</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>聊天室節點的 GUID。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenExpireDate</p></td>
<td><p>datetime、not null</p></td>
<td><p>到期時間。 （權杖會在30分鐘之後到期，除非已固定（請參閱此欄中的下列描述）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceFileUrl</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已傳送檔案的 URL （適用于合規性服務使用）。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceThumbnailUrl</p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>已傳送檔案的縮圖 URL （適用于合規性服務使用）。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenComplianceTime</p></td>
<td><p>datetime2</p></td>
<td><p>實際檔案傳輸作業（適用于合規性服務使用）的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenComplianceIsUpload</p></td>
<td><p>稍微</p></td>
<td><p>如果上傳則為 True;如果下載（適用于相容性服務使用），則為 False。</p></td>
</tr>
<tr class="odd">
<td><p>fileTokenCompliancePinned</p></td>
<td><p>bit、not null</p></td>
<td><p>如果權杖已釘選，則為 True。 它是用來在表格中保留權杖，直到合規性服務有機會從它取得相關欄位為止。</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>鍵

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>fileToken</p></td>
<td><p>主鍵。</p></td>
</tr>
<tr class="even">
<td><p>fileTokenChannelID</p></td>
<td><p>在 tblNode nodeGuid 資料表中使用 [查閱] 的外鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

