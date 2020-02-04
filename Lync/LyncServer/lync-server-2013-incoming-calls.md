---
title: Lync Server 2013：來電
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
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a>Lync Server 2013 中的來電

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

將來電路由至啟用位置路由的使用者，視使用者端點的位置而定。 傳入通話的路由會受到下列方式的影響。 如果使用者有來電至位於以位置為基礎的路由的網路網站中的端點，且端點與 PSTN 閘道位於相同的網路網站中，通話就會路由。 如果使用者有來電至位於支援位置路由的網路網站中的端點，且端點所在的網路網站與 PSTN 閘道不同，則不會路由該通話。 當使用者沒有位於與來電所在的 PSTN 閘道相同網路網站中的端點時，撥入電話會直接路由至使用者的語音信箱，而未接來電通知將會傳送給呼叫方。

已啟用針對位置路由的使用者的來電轉接設定將會繼續生效，不過，轉寄的呼叫將會受到使用者的位置式路由限制。

下表說明根據被呼叫者終點的位置，以位置為基礎的路由會如何影響輸入通話的路由。 PSTN 閘道的網路網站是針對位置路由而啟用，且以位置為基礎的路由只允許將 PSTN 呼叫路由至同一網路網站中的端點。

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a>被呼叫者從 PSTN 接收入站通話

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
<th>被呼叫者的端點與 PSTN 閘道不在同一個網路網站中</th>
<th>被呼叫方的端點位於未知的網路網站，或未啟用以位置為基礎的路由</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>傳送進貨 PSTN 通話</p></td>
<td><p>來電是路由到被叫方的端點</p></td>
<td><p>來電未路由至被叫方的端點</p></td>
<td><p>來電未路由至被叫方的端點</p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的位置基礎路由案例](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

