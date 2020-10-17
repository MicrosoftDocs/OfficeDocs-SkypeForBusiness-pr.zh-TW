---
title: Lync Server 2013：使用者位置
description: Lync Server 2013：使用者的位置。
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
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561209"
---
# <a name="users-location-in-lync-server-2013"></a>Lync Server 2013 中的使用者位置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

Location-Based 路由利用 E9-1-1、CAC 和媒體旁路所用的 Lync Server 中所定義的相同網路地區、網站和子網，以避免 PSTN 免付費旁路。 使用者的位置取決於使用者 (s) 所連線的 Lync 端點的 IP 子網。 每個 IP 子網都會與網路網站產生關聯，該網站會匯總成系統管理員所定義的網路地區。 Location-Based 會根據使用者的網路網站強制進行路由傳送。

Location-Based 路由規則會依每個網路網站套用，這表示一組指定的規則會套用至位於相同網路網站中 Location-Based 路由的所有啟用端點。 管理員可以將 Location-Based 路由套用到需要該網站的網站。

您可以在每個網路網站上定義語音路由策略，以定義特定的 PSTN 閘道，以供位於網路網站中的所有使用者用來呼叫 PSTN 電話號碼。 這類語音路由原則會優先于使用者語音原則所定義的路由，當使用者位於啟用 Location-Based 路由的網路網站時，它會防止透過已啟用 Location-Based 路由的其他 PSTN 閘道路由呼叫。 當 Lync 使用者撥打 PSTN 電話時，使用者的語音原則會決定使用者是否有權進行通話。 如果使用者的語音原則允許使用者撥打電話，Location-Based 路由決定來電應來自哪個 PSTN 閘道。 Location-Based 路由會根據使用者的位置來決定這種情況。

使用者位置可依下列方式分類：

  - 使用者位於為 Location-Based 路由啟用的已知網路網站，而且他 (直接向內撥號) 號碼會在置於相同網路網站 (的 PSTN 閘道上終止例如，office) 。 撥出電話的路由會透過使用者所在之網站的語音路由原則進行。 對使用者的傳入 PSTN 呼叫會路由至位於與 PSTN 閘道位於相同網路網站的端點。

  - 使用者位於與 PSTN 閘道所在之網路網站不同的已知網路網站。  (，亦即，使用者已前往另一部公司辦公室) 。 撥出電話的路由將使用使用者所在之網路網站的語音路由原則。 對使用者的內送 PSTN 通話不會路由到位於不同于 PSTN 閘道的端點，以避免 PSTN 收費繞過。

  - 當使用者位於 Lync 伺服器部署無法識別的網站時，撥出電話的路由會根據指派給使用者的語音原則，而不是系結至 Location-Based 路由限制的 PSTN 閘道。 傳入 PSTN 通話不會路由至位於未知網路網站的端點，以避免 PSTN 收費繞過。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中 Location-Based 路由的指導方針](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

