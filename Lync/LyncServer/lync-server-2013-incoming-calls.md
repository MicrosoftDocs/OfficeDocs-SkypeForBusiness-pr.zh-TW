---
title: Lync Server 2013：傳入通話
description: Lync Server 2013：傳入通話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547729"
---
# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 中的傳入通話

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

對啟用 Location-Based 路由的使用者進行撥入電話的路由，取決於使用者端點的位置。 傳入通話的路由會以下列方式受到影響。 如果使用者對位於啟用網路功能的 Location-Based 路由的網站中的端點進行來電，而該端點位於與 PSTN 閘道相同的網路網站中，則會路由傳送通話。 如果使用者對位於啟用 Location-Based 路由的網路網站中的端點進行來電，而該端點位於與 PSTN 閘道不同的網路網站中，則不會路由呼叫。 當使用者沒有與撥入電話來源所在的 PSTN 閘道位於相同網路網站時，撥入電話會直接路由傳送至使用者的語音信箱，而且會將未接來電通知傳送給呼叫方。

已啟用 Location-Based 路由之使用者的「來電轉接」設定會繼續強制執行，不過轉接的來電會受到使用者 Location-Based 路由限制的制約。

下表說明 Location-Based 路由會如何影響傳入通話的路由，視受話者端點的位置而定。 PSTN 閘道的網路網站會為 Location-Based 路由啟用，而且 Location-Based 路由只允許將 PSTN 呼叫路由傳送至相同網路網站內的端點。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>被呼叫者從 PSTN 接收輸入呼叫

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>被呼叫者的端點位於與 PSTN 閘道相同的網路網站中</th>
<th>受話者的端點與 PSTN 閘道不位於相同的網路網站</th>
<th>受話者的端點位於未知的網路網站中，或是未啟用 Location-Based 路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>傳入 PSTN 通話的路由</p></td>
<td><p>撥入電話會路由傳送至受話者的端點</p></td>
<td><p>傳入的呼叫未路由至受話者的端點</p></td>
<td><p>傳入的呼叫未路由至受話者的端點</p></td>
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

