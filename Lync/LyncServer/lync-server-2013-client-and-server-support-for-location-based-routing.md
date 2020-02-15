---
title: Lync Server 2013： 用戶端與伺服器支援的位置型的路由
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
ms.openlocfilehash: efdb03adbdf1392e27c3107eef4aaf97f3708e66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Lync Server 2013 中的位置型路由的用戶端與伺服器支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-06-18_

位置型路由會強制執行 Lync server。 Lync Server 可以識別使用者會將連線從公司網路內的網路網站。 遠端使用者位於公司網路之外，因為它們的位置會被視為未知。

<div>

## <a name="lync-server-support"></a>Lync Server 支援

位置型的路由需要上所有的前端集區和 Standard Edition 伺服器之給定拓撲中的已部署了 Lync Server 2013 CU1。 如果在拓撲中特定 Lync 元件上未安裝 Lync Server 2013 CU1、 位置型路由限制無法完全強制執行。

下表列出位置型路由可支援的伺服器角色和版本組合。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>集區版本</th>
<th>中繼伺服器版本</th>
<th>支援</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 年 2 月 2013年累計更新</p></td>
<td><p>Lync Server 2013 年 2 月 2013年累計更新</p></td>
<td><p>是</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 年 2 月 2013年累計更新</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>否</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 年 2 月 2013年累計更新</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>否</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 年 2 月 2013年累計更新</p></td>
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

下表列出位置型路由支援的用戶端。


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
<td><p>包括 Lync 2013 年 2 月 2013年累計更新</p></td>
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
<td><p>Lync Attendant</p></td>
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
<td><p>VoIP 必須停用 Lync Mobile 2013 用戶端如果啟用位置型路由與使用者使用。</p></td>
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
> 若要停用 VoIP Lync Mobile 2013 用戶端，請指派行動性原則的設定，IP 音訊/視訊，停用所有使用者啟用位置型路由與。 如需行動性原則的詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-csmobilitypolicy</A>。



</div>

</div>

<div>

## <a name="see-also"></a>另請參閱


[規劃 Lync Server 2013 中依位置路由](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

