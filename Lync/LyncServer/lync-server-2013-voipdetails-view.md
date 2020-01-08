---
title: Lync Server 2013： VoIPDetails view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoIPDetails view
ms:assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687973(v=OCS.15)
ms:contentKeyID: 49733561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9553be13dcd73f89ba8d6ab051602d378bf353da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-view-in-lync-server-2013"></a>Lync Server 2013 中的 [VoIPDetails] 視圖

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

[VoIPDetails] 視圖儲存點對點工作階段的相關資訊，其中至少有一個使用者是 VoIP 使用者。 此視圖已在 Microsoft Lync Server 2013 中推出。

<div>


> [!NOTE]  
> [VoIPDetails] 視圖會包含 [ <A href="lync-server-2013-sessiondetails-view.md">Lync Server 2013</A> ] 的 [SessionDetails] 視圖中的所有資料行，以及下列所列的欄。



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
<td><p><strong>FromPhone</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>啟動會話之使用者的電話 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToPhone</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>加入會話之使用者的電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByUri</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>中斷會話的使用者 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByUriType</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>中斷會話的使用者 URI 類型。 如需詳細資訊，請參閱<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中</a>的 [UriTypes] 資料表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedByTenant</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>中斷會話的使用者租使用者。</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedByPhone</strong></p></td>
<td><p>Nvarchar （450）</p></td>
<td><p>中斷會話的使用者的電話 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話的使用者所使用的中繼伺服器。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServer</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>加入會話的使用者所使用的中繼伺服器。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGateway</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>啟動會話的使用者所使用的閘道。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGateway</strong></p></td>
<td><p>Nvarchar （256）</p></td>
<td><p>加入會話的使用者所使用的閘道。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

