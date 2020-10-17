---
title: Lync Server 2013：通話轉移和來電轉接
description: Lync Server 2013：通話轉接及來電轉接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565249"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a>Lync Server 2013 中的來電轉接和來電轉接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

當涉及 PSTN 端點時，Location-Based 路由會分析 calle 端點的位置，以及將來電轉接或轉接至 (（例如，傳輸/轉送目標) ）的端點。 Location-Based 路由決定是否應該根據這兩個端點的位置來轉移或轉寄通話。

下表說明 Lync 使用者在使用 PSTN 端點的呼叫中的情形，以及 Lync 使用者將通話轉接至另一個 Lync 使用者的情形。 根據 transferee 端點的網路網站位置，Location-Based 路由會影響來電轉接或轉寄的路由。

### <a name="initiating-call-transfer-or-forward"></a>開始來電轉接或轉寄

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>使用者啟動通話轉接/轉寄</th>
<th>目標端點位於與使用者起始來電轉接或轉寄相同的網路網站</th>
<th>目標端點位於不同的網路網站中，以供使用者開始來電轉接或轉寄</th>
<th>目標端點位於未知的網路網站，或未啟用 Location-Based 路由的網路網站</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 使用者</p></td>
<td><p>允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
<td><p>不允許來電轉接或轉接</p></td>
</tr>
</tbody>
</table>

  

例如：使用 PSTN 端點通話中的 Lync 使用者，可將來電轉接至位於相同網路網站中的其他 Lync 使用者。 在此情況下，允許通話轉接。

下表說明 Lync 使用者與其他 Lync 使用者通話的情況，以及其中一位使用者將來電轉接至 PSTN 端點。 根據通話的轉接使用者位置，表格會詳細說明 Location-Based 路由會如何影響通話。

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a>來電轉接或轉接至 PSTN 端點

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>來電轉接/轉寄端點目標</th>
<th>相同網路網站中的 Lync 使用者</th>
<th>不同網路網站中的 Lync 使用者</th>
<th>未啟用 Location-Based 路由的未知網路網站或網站中的一或兩個 Lync 使用者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN 端點</p></td>
<td><p>轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接</p></td>
<td><p>轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接</p></td>
<td><p>轉接使用者的語音原則所允許的呼叫轉寄或轉接只能透過主幹未啟用 Location-Based 路由</p></td>
</tr>
</tbody>
</table>

  
例如：通話中的 Lync 使用者與另一個位於相同網路網站的 Lync 使用者，將來電轉接至 PSTN 端點，並且允許通話轉接。

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的 Location-Based 路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

