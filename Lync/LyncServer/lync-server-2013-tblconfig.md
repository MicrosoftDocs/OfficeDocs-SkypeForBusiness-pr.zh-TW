---
title: Lync Server 2013：tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblConfig
ms:assetid: 7445e7db-c574-46fa-b964-8640d77047a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558663(v=OCS.15)
ms:contentKeyID: 48184515
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b0e383791eafbe017e5163156ba53cdad581cb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblconfig-in-lync-server-2013"></a>Lync Server 2013 中的 tblConfig

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-12_

tblConfig 包含部分持續聊天伺服器不支援的設定（在單一列中）。

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
<td><p>configLabel</p></td>
<td><p>Nvarchar （255），not null</p></td>
<td><p>包含&quot;pool。&quot;</p></td>
</tr>
<tr class="even">
<td><p>configContent</p></td>
<td><p>Nvarchar （max）</p></td>
<td><p>配置內容。</p></td>
</tr>
<tr class="odd">
<td><p>configPoolID</p></td>
<td><p>GUID，不是 null</p></td>
<td><p>資料庫實例的唯一識別碼。</p></td>
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
<td><p>configLabel</p></td>
<td><p>主鍵。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

