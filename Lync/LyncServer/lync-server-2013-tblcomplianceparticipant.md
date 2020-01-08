---
title: Lync Server 2013：tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e98b257552f728d0976df6331673f1f55d0dbdeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>Lync Server 2013 中的 tblComplianceParticipant

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblComplianceParticipant 包含每個通道及每個伺服器的目前參與者。

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
<td><p>channelUri</p></td>
<td><p>Nvarchar （255），not null</p></td>
<td><p>通道統一資源識別項（URI）。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，not null</p></td>
<td><p>參與者的主體識別碼（對應至 tblPrincipal prinID 資料表）。</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>Bigint，not null</p></td>
<td><p>加入事件的時間戳記。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>Bigint</p></td>
<td><p>如果參與者仍在加入，則為 Null。 如果 not null，則通道的時間戳記會保留事件。</p>
<p>這些專案會在所有翻譯員處理事件時最終移除。</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>Nvarchar （255），not null</p></td>
<td><p>使用者 URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>伺服器身分識別（例如在 serverID 資料表中則為 tblServerIdentity）。</p></td>
</tr>
<tr class="odd">
<td><p>識別碼</p></td>
<td><p>Bigint</p></td>
<td><p>伺服器會話。 這是在每次聊天服務啟動時產生的亂數字。 它是用來區分會話，目的是識別孤立參與者。</p></td>
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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;channelUri、userId、joinedAt&gt;</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

