---
title: Lync Server 2013： 使用者的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2e0454b5f8fc891aa878623575ee3850050ba28
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 中的使用者的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

位置型路由的利用相同網路地區、 網站及子 E9-1-1 所使用的 Lync 伺服器中所定義，CAC 以及媒體旁路，將通話路由限制套用防範 PSTN 通話費略過。 使用者的位置取決於使用者的 Lync 從連線端點的 IP 子網路。 每個 IP 子網路是與網路網站，這會彙總成管理員所定義的網路地區相關聯。 位置型路由會強制執行根據使用者的網路網站。

位置型的路由規則會套用在每個網路網站為基礎，這表示一組指定的規則，將會套用至所有的端點啟用位置型路由位於相同的網路站台內。 系統管理員可以套用至需要的網路網站的位置型的路由。

語音路由原則可定義統計網路站台定義特定的 PSTN 閘道應該位於網路網站的所有使用者用來呼叫 PSTN 電話號碼。 這類語音路由原則會優先於使用者位於網路網站啟用位置型的路由，而它會防止透過已啟用其他 PSTN 閘道的通話路由傳送時，使用者的語音原則所定義的路由依位置路由。 Lync 使用者將置於 PSTN 通話，當使用者的語音原則會決定使用者是否可以被授權撥打電話。 如果使用者的語音原則允許使用者撥打電話，位置型路由會決定從應該 egress 通話的 PSTN 閘道。 位置型路由會判斷根據使用者的位置。

使用者的位置可以分類方式如下：

  - 使用者位於啟用位置型路由已知的網路網站，其 DID （直接向內撥號對應表） 號碼終止上放置在相同的網路網站 （亦即辦公室） 的 PSTN 閘道。 路由撥出通話將會透過使用者所在的網路網站的語音路由原則。 給使用者的傳入 PSTN 通話路由傳送至位於與 PSTN 閘道位於相同網路站台的端點。

  - 使用者位於已知的網路網站，位於不同的 PSTN 閘道的所在位置的網路網站。 （亦即使用者間傳送至其他公司辦公室）。 撥出電話路由傳送。 會使用使用者所在的網路網站的語音路由原則。 給使用者的傳入 PSTN 通話不會路由傳送至位於不同的站台比 PSTN 閘道，以避免 PSTN 通話費略過的端點。

  - 當使用者位於未知至 Lync Server 部署的網路網站時的撥出電話路由會根據指派給使用者未繫結至位置型路由限制的 PSTN 閘道的語音原則。 傳入 PSTN 通話不會路由傳送至位於不明的網路網站，以防止 PSTN 通話費略過的端點。

<div>

## <a name="see-also"></a>另請參閱


[依位置路由 Lync Server 2013 中的指引](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

