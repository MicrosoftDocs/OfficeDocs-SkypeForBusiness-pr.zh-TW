---
title: Lync Server 2013： 撥出電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aa72bb1da56862765279f25f73070863d218067
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a>Lync Server 2013 中的撥出電話

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

路由撥出電話的使用者啟用位置型路由是受影響使用者的端點的網路位置。 下表說明如何以位置為主的路由會影響路由撥出通話根據發話者端點的位置。

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a>來電者將放至 PSTN 撥出電話

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>位於啟用位置型路由的網路網站的使用者端點</th>
<th>使用者端點位於不明的網路網站，或未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>撥出電話的授權</p></td>
<td><p>呼叫是根據授權的使用者的語音原則</p></td>
<td><p>呼叫是根據授權的使用者的語音原則</p></td>
</tr>
<tr class="even">
<td><p>撥出電話路由</p></td>
<td><p>通話路由傳送根據網路網站的語音路由原則</p></td>
<td><p>通話路由傳送，根據使用者的語音原則，以及只能透過主幹 （如果有的話） 未啟用位置型的路由</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另請參閱


[依位置路由 Lync Server 2013 中的案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

