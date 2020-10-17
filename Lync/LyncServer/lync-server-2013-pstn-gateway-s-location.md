---
title: Lync Server 2013： PSTN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512440"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 閘道位置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

透過 PSTN 閘道路由傳送的來電和 PBXs 可能需要 Location-Based 路由限制，視這類系統的位置而定。 您可以在每個主幹基礎上啟用 Location-Based 路由的細微性。

當主幹上啟用時，Location-Based 路由會引進下列一組規則：

  - 以每個主幹為基礎啟用 Location-Based 路由時，在該主幹上定義的規則只會套用到透過該主幹路由傳送的來電。

  - 若要防止 PSTN 電話費旁路，其中的呼叫來自 PSTN 閘道所在的網路網站不同的網站，Location-Based 路由會引入網路網站與指定主幹的關聯。 這會定義允許通話路由傳送至指定主幹的網路網站。

您可以透過兩種方式，為 Location-Based 路由啟用主幹：

  - 骨幹關是針對 egresses 對 PSTN 進行呼叫的 PSTN 閘道所定義。 以這種類型的主幹路由傳送的來電，只會路由傳送到與主幹位於相同網路網站內的端點。

  - 主幹的定義是針對不會向 PSTN 和服務使用者提供靜態位置之舊版電話的轉送伺服器對等 (，例如 PBX 電話) 。 針對此特殊設定，所有由這種類型的主幹路由傳送的來電都會被視為與主幹產生來自相同的網路網站。 從 PBX 使用者撥打的 Location-Based 路由執行方式，會與與主幹位於相同網路網站的 Lync 使用者相同。 如果位於不同網路網站的兩個 PBX 系統是透過 Lync Server 連線，Location-Based 路由將允許從一個網路網站的一個 PBX 端點路由傳送到另一個網路網站中的另一個 PBX 端點。 Location-Based 路由將不會封鎖此案例。 除了這種情況，以及以相同位置的 Lync 使用者類似的方式，連接至具有此設定之轉送伺服器的端點，也可以撥打或接聽其他轉送伺服器對等的來電，而不是將通話路由傳送至 PSTN (亦即，不論轉送伺服器對等項的網路網站為何，都連接至不同 PBX 的端點) 。 涉及 PSTN 端點的所有撥入通話、撥出電話、來電轉接及來電，都要視位置為基礎，僅使用定義為本機至此類轉送伺服器對等的 PSTN 閘道。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中 Location-Based 路由的指導方針](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

