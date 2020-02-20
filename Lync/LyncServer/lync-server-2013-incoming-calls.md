---
title: Lync Server 2013： 內送呼叫
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
ms.openlocfilehash: cb8be496e863058ddec27dd92b994d94b86a26e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 中的來電

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

路由傳送來電至使用者啟用位置型的路由，取決於使用者的端點的位置。 以下列方式，受影響的內送呼叫路由。 如果使用者有來電轉接至位於位置型的路由端點已啟用的網路網站，並端點位於相同網路網站與 PSTN 閘道，來電會路由傳送。 如果使用者有來電轉接至位於位置型的路由端點已啟用的網路網站，並端點位於不同的網路站台比 PSTN 閘道，不會路由傳送來電。 當使用者不具有位於相同的網路網站與 PSTN 閘道來電源自其中任何端點時，來電會被直接路由傳送至使用者的語音信箱和未接的來電通知會傳送給受話方。

來電轉接設定已啟用位置型路由的使用者仍可強制執行，不過，轉接電話會受到位置型路由限制的使用者。

下表說明如何以位置為主的路由會影響根據受話者端點的位置的撥入通話路由傳送。 PSTN 閘道的網路網站啟用位置型的路由，以及位置型路由只允許路由傳送至相同的網路站台內的端點的 PSTN 通話。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>受話者接收來自 PSTN 的輸入的呼叫

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
<th>位於相同網路網站與 PSTN 閘道的受話者端點</th>
<th>並非位於相同網路網站與 PSTN 閘道的受話者端點</th>
<th>受話者端點位於不明的網路網站，或未啟用位置型的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>路由傳送內送 PSTN 通話</p></td>
<td><p>來電會路由傳送至受話者端點</p></td>
<td><p>來電不會路由至受話者端點</p></td>
<td><p>來電不會路由至受話者端點</p></td>
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

