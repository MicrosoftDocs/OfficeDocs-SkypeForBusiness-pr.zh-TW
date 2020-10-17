---
title: Lync Server 2013：同時震鈴
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 358a0dd6dab96b67b26c211c9f28dbc6c0842804
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519790"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a>Lync Server 2013 中同時震鈴

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

當呼叫方啟用同時震鈴時，Location-Based 路由會分析呼叫方的位置，以及所叫方的端點，以判斷是否應路由傳送。

下表說明以同時震鈴方式設定的使用者，同時震鈴目標是在相同網路網站、不同網路網站或未知網路網站中的使用者。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>的傳入 PSTN 通話</th>
<th>與被呼叫方位於相同的網路網站</th>
<th>位於不同于被呼叫者的網路網站</th>
<th>位於未知的網路網站，或未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>允許同時振鈴</p></td>
<td><p>不允許同時振鈴</p></td>
<td><p>不允許同時振鈴</p></td>
</tr>
</tbody>
</table>

  
下表說明 Lync 使用者 (的呼叫，例如 Lync 來電者) 在同一部網路網站、不同的網路網站，或從未知的網路網站。 被呼叫方具有 PSTN 端點 (，cellphone) 設定為同時環的目標。 在此案例中，Location-Based 路由會判斷是否應將通話路由傳送至同時振鈴目標 (（亦即，被叫方的 cellphone) ）。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>同時環目標</th>
<th>與被呼叫方位於相同的網路網站</th>
<th>位於不同于被呼叫者的網路網站</th>
<th>位於未知的網路網站，或未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>透過來電者的網站語音路由原則允許同時振鈴</p></td>
<td><p>透過來電者的網站語音路由原則允許同時振鈴</p></td>
<td><p>允許透過來電者語音原則進行同時振鈴，以主幹未啟用 Location-Based 路由</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 Location-Based 路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

