---
title: 'Lync Server 2013: PSTN 閘道的位置'
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
ms.openlocfilehash: b3ff0e3ea426a8f3aa053b057b616148a42ad409
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 中的 PSTN 閘道的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-03-09_

透過 PSTN 閘道的通話路由傳送，且 Pbx 可能需要根據這類系統的位置的位置型路由限制。 在每個主幹為基礎的資料粒度，可以啟用位置型的路由。

位置型路由引進下列一組規則在主幹上啟用時：

  - 每個主幹根據啟用位置型路由時，規則會定義上的主幹將只會套用至來電路由傳送到該主幹。

  - 若要防止 PSTN tolls 略過其中呼叫源自網路網站不同的 PSTN 閘道的所在位置的網路網站，位置型路由會介紹指定主幹網路網站的關聯。 這是定義網路網站，可讓呼叫路由傳送至指定的主幹。

主幹可以啟用位置型的路由，以兩種方式：

  - 主幹被定義 PSTN 閘道 egresses 撥打至 PSTN。 這種類型的主幹路由傳送來電會路由傳送僅至位於相同網路站台為主幹的端點。

  - 主幹被定義中繼伺服器對等不會輸出通話的 PSTN 和服務的使用者與舊版電話靜態位置 （亦即 PBX 電話）。 此特定的組態，這種類型的主幹路由傳送所有來電會被都視為至源自於相同的網路站主幹。 PBX 使用者的來電將會有相同的位置型路由強制執行為 Lync 使用者都位於相同網路站台為主幹。 如果兩個位於不同的網路站台的 PBX 系統連線到 Lync Server，位置型路由會允許從一個網路站台中的一個 PBX 端點路由傳送至其他網路站台中的另一個 PBX 端點。 此案例不會遭到位置型的路由。 除了此案例中，為 Lync 使用者在相同位置以類似方式連線至與此組態的中繼伺服器對等的端點將能夠撥打或接聽電話到及傳送自其他中繼伺服器對等網路，請勿不將通話路由傳送至 PSTN (i。e.端點連接至不同的 PBX) 不論要將中繼伺服器對等網路相關聯的網站。 所有撥入的通話，撥出通話，通話轉接和通話的轉寄涉及 PSTN 端點會受到位置型路由傳送至使用這類中繼伺服器對等的本機定義的 PSTN 閘道。

<div>

## <a name="see-also"></a>另請參閱


[依位置路由 Lync Server 2013 中的指引](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

