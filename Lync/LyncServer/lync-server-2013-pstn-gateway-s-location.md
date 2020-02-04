---
title: Lync Server 2013：PSTN 閘道位置
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
ms.openlocfilehash: b5d15589f37b18015f91e3717e19415d5ade6b6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724743"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a>Lync Server 2013 中 PSTN 閘道的位置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-09_

透過 PSTN 閘道和 Pbx 路由的通話，可能需要以位置為基礎的路由限制（視這類系統的位置而定）。 在每個幹線的細微性，都可以啟用以位置為基礎的路由。

在主幹上啟用時，以位置為基礎的路由會引入下列一組規則：

  - 針對每個幹線啟用位置路由時，在該主幹上定義的規則將只會套用到透過該主幹路由的通話。

  - 若要避免 PSTN tolls 繞過從網路網站產生的位置，而該網路網站是 PSTN 閘道所在的網路網站，則以位置為基礎的路由會引入網路網站與指定主幹的關聯性。 這會定義允許呼叫路由至指定主幹的網路網站。

您可以透過以下兩種方式，為基於位置的路由啟用 Trunks：

  - 幹線是針對 egresses 對 PSTN 的呼叫的 PSTN 閘道所定義。 由這種類型的幹線路由的撥入通話將只路由到與幹線位於相同網路網站內的端點。

  - 主幹是針對不在靜態位置（即 PBX 手機）中使用舊版手機的中繼伺服器對等進行的中繼伺服器對等定義。 針對這個特殊設定，由這種類型的幹線路由的所有撥出電話，都會被認為是來自同一個網路網站作為主幹。 從 PBX 使用者進行的呼叫將會有相同的以位置為基礎的路由強制執行，就像是與主幹一樣位於同一個網路網站中的 Lync 使用者。 如果在不同的網路網站中，有兩個 PBX 系統是透過 Lync Server 連線，則以位置為基礎的路由將允許從一個網路網站的一個 PBX 端點路由到其他網路網站中的另一個 PBX 端點。 這個案例不會受到以位置為基礎的路由封鎖。 除了這種情況及與相同位置中的 Lync 使用者類似的情況下，與此設定連線到中繼伺服器對等的端點，都能撥打或接聽其他中繼伺服器對等的呼叫，不會將呼叫路由至 PSTN （i）。e. 連接至不同 PBX 的端點），不論要與中繼伺服器對等關聯的網路網站為何。 所有的撥入通話、撥出通話、來電轉接與涉及 PSTN 端點的呼叫轉寄，都會受到基於位置的路由，只使用定義為本機到此類中繼伺服器對等的 PSTN 閘道。

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的位置基礎路由指引](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

