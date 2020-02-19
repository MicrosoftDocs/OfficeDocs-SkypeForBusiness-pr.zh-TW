---
title: 'Lync Server 2013: M:N 主幹'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e18bff7fa6031101f73ba4b5ce11f5a0d3c015
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a>Lync Server 2013 中的 M:N 主幹

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-01_

Lync Server 2013 從舊版的通話路由用途定義中的主幹支援較大的彈性。 主幹是邏輯和之間的關聯的中繼伺服器接聽連接埠號碼與閘道的聆聽連接埠號碼。 這意味著幾件事： 中繼伺服器可以有多個主幹至相同的閘道。中繼伺服器可以有多個主幹不同閘道;相反地閘道可以有多個主幹至不同的中繼伺服器。

仍需要閘道 」 新增至使用拓撲產生器 Lync 拓撲時要建立根主幹。 指定的中繼伺服器可以處理的閘道器數目取決於伺服器的處理容量離峰忙線中。 如果您在部署中繼伺服器中所述的[Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)支援文件，然後多少作用中的非旁路呼叫獨立中繼伺服器可以處理的估計值超過 Lync Server 2013 的基本硬體需求的硬體是大約 1000年通話。 當部署這些規格，中繼伺服器預期會在執行轉碼，但仍將通話路由傳送多個閘道即使閘道不支援的硬體會議媒體旁路。

時定義電話路由，請指定該路由，相關聯的主幹，但未指定此中繼伺服器相關聯的路由。 相反地，您可以使用拓撲產生器主幹建立關聯的中繼伺服器。 換句話說，路由會判斷哪一個主幹，用於通話，並接著，與該主幹相關聯之中繼伺服器會傳送該通話的訊號。

中繼伺服器可部署為集區;此集區可以組合與前端集區，或其可部署為獨立集區。 當中繼伺服器已組合與前端集區時，集區的大小可以是大小的最多 12 （登錄器集區限制）。 數位簽章這些新功能增加的可靠性與部署彈性的中繼伺服器，但他們需要下列的對等實體中相關聯的功能：

  - **PSTN 閘道。** Lync Server 2013 合格的閘道必須實作 DNS 負載平衡，以便做為一個集區的中繼伺服器，進而負載達到負載平衡呼叫負載平衡器集區之間之合格公用交換的電話網路 (PSTN) 閘道。

  - **工作階段邊界控制器。** SIP 主幹，對等實體為網際網路電話語音服務提供者的工作階段邊界控制器 (SBC)。 在 SBC 的中繼伺服器集區的方向，SBC 可以接收來自集區中任何中繼伺服器的連線。 在集區的方向從 SBC，流量可以傳送至集區中任何中繼伺服器。 達成這的一種方法是透過 DNS 負載平衡，如果服務提供者和 SBC 支援。 另一種方法是讓服務提供者的集區] 中的所有中繼伺服器的 IP 位址和服務提供者會佈建這些中其 SBC 為個別的 SIP 主幹的每一部中繼伺服器。 服務提供者會接著處理負載平衡的本身伺服器。 並非所有服務提供者或 Sbc 可能都支援這些功能。 此外，服務提供者可能額外收費的這項功能。 一般而言，每個 SIP 主幹，以將 SBC 會帶來月費。

  - **IP PBX。** 在 IP PBX SIP 終止的中繼伺服器集區的方向，IP PBX 可以接收來自集區中任何中繼伺服器的連線。 在集區的方向從 IP PBX，流量可以傳送至集區中任何中繼伺服器。 因為大部分的 Ip-pbx 不支援 DNS 負載平衡，我們建議從 IP-PBX 定義個別的直接 SIP 連線，為集區中每個中繼伺服器。 IP PBX 會再處理自己負載平衡流量分散至透過 [主幹] 群組。 假設是主幹群組在 IP PBX 有一致的路由規則集合。 是否特定 IP PBX 支援此主幹群組概念，以及如何它與 IP PBX 的自己備援交集和叢集架構需要判斷之前您可以決定的中繼伺服器叢集與 IP PBX 可以正確進行互動。

中繼伺服器集區必須有與它互動的對等閘道的統一檢視。 這表示集區中的所有成員存取對等閘道的相同定義從設定存放區，並同樣也可能會與其互動的撥出電話。 因此，沒有任何方法可以分割區，以便有些中繼伺服器與僅限撥出電話的特定閘道對等通訊。 如果這類分割為必要，必須使用獨立中繼伺服器集區。 這是案例，例如，如果在 PSTN 閘道、 SIP 主幹或 IP Pbx 互動稍早在本主題中詳述的集區相關聯的功能不存在。

特定的 PSTN 閘道、 IP PBX 或 SIP 主幹對等網路可以路由傳送至多個中繼伺服器或主幹。 特定中繼伺服器集區可以控制的閘道器數目取決於使用媒體旁路的通話數目。 如果大量通話使用媒體旁路，中繼伺服器集區中可以處理許多的多個呼叫，因為是必要的唯一信號層處理。

</div>

<span> </span>

</div>

</div>

</div>

