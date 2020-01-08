---
title: Lync Server 2013： ClientVersions view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d219b8666afc0684b0d61f02f06618ea6ef60f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a>Lync Server 2013 中的 [ClientVersions] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-01_

ClientVersions view 會儲存已參與在資料庫中記錄會話的各種用戶端類型和版本資訊。 該視圖中的每一筆記錄代表一個用戶端版本。 此視圖已在 Microsoft Lync Server 2013 中推出。

<div>


> [!NOTE]  
> 某些欄可能有多個記錄。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>左欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>標識此用戶端類型與版本的唯一號碼。</p></td>
</tr>
<tr class="even">
<td><p><strong>版本</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>代表使用者代理程式。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>用戶端類型。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>Nvarchar （64）</p></td>
<td><p>用戶端所屬的類別。 例如，用戶端 Conferencing_Attendant_1 .0 屬於 ClientCategory CAA。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

