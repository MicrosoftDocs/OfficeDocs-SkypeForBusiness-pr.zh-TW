---
title: Lync Server 2013： Location-Based 路由的用戶端和伺服器支援
description: Lync Server 2013：用戶端和伺服器支援 Location-Based 路由。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549629"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的 Location-Based 路由的用戶端和伺服器支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-06-18_

Location-Based 路由是由 Lync Server 強制執行。 Lync Server 可以識別使用者從公司網路內部連線的網路網站。 因為遠端使用者位於公司網路外部，所以其位置被視為未知。

<div>

## <a name="lync-server-support"></a>Lync Server 支援

Location-Based 路由需要在指定的拓撲中的所有前端集區和 Standard Edition server 上部署 Lync Server 2013 CU1。 如果 Lync Server 2013 CU1 未安裝在拓撲中的某些 Lync 元件上，則無法完全強制執行 Location-Based 路由限制。

下表列出 Location-Based 路由支援的伺服器角色與版本組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>集區版本</th>
<th>轉送伺服器版本</th>
<th>支援</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 2013 月累計更新</p></td>
<td><p>Lync Server 2013 2013 月累計更新</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 月累計更新</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 2013 月累計更新</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 2013 月累計更新</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>任何</p></td>
<td><p>否</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync 用戶端支援

下表識別 Location-Based 路由支援的用戶端。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>用戶端類型</th>
<th>支援</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>是</p></td>
<td><p>包括 Lync 2013 月2013累計更新</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>否</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync 語音應答</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync for Windows 8</p></td>
<td><p>否</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>否</p></td>
<td><p>如果已啟用 Location-Based 路由的使用者使用，則必須停用 Lync Mobile 2013 用戶端的 VoIP。</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>是</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> 若要停用 Lync Mobile 2013 用戶端的 VoIP，請將行動原則指派給所有啟用位置路由之使用者的設定、IP Audio/Video、停用。 如需行動原則的詳細資訊，請參閱 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

