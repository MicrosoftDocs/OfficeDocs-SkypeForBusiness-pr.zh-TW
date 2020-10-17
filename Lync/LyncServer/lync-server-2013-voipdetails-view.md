---
title: Lync Server 2013： VoIPDetails view
description: Lync Server 2013： VoIPDetails view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ecd34be0c8568eef29d773f088e8503a8065743
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566199"
---
# <a name="voipdetails-view-in-lync-server-2013"></a>Lync Server 2013 中的 VoIPDetails 視圖

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

VoIPDetails 檢視會儲存對等工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已引進于 Microsoft Lync Server 2013。

<div>


> [!NOTE]  
> VoIPDetails view 包含在 <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 視圖</A> 中的所有欄，此外還會列出下列欄。



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>欄</th>
<th>資料類型</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>FromPhone</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>起始工作階段之使用者的電話 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>參加工作階段之使用者的電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>中斷連線工作階段之使用者的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>中斷連線工作階段之使用者的 URI 類型。 如需詳細資訊，請參閱 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表格</a> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>中斷連線工作階段之使用者的租用戶。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>Nvarchar (450) </p></td>
<td><p>中斷連線工作階段之使用者的電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起始工作階段之使用者所使用的中繼伺服器。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>參加工作階段之使用者所使用的中繼伺服器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>起始工作階段之使用者所使用的閘道。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>Nvarchar (256) </p></td>
<td><p>參加工作階段之使用者所使用的閘道。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

