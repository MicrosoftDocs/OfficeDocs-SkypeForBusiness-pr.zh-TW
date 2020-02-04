---
title: Lync Server 2013：如何實作 SIP 主幹？
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de621d7508b69dd3adc3babf487406825f3a93f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>如何在 Lync Server 2013 中實作 SIP 主幹？

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-03-18_

若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間通訊會話的 proxy，以及在必要時使用 transcodes 媒體。

每個中繼伺服器都有一個內部網路介面與一個外部網路介面。 內部介面會連接到前端伺服器。 外部介面通常稱為閘道介面，因為它通常是用來將中繼伺服器連線到公用交換式電話網絡（PSTN）閘道或 IP PBX。 若要實施 SIP 幹線，您可以將中繼伺服器的外部介面連接到 ITSP 的外部邊緣元件。

<div>


> [!NOTE]  
> ITSP 的外部邊緣元件可以是 [會話邊界控制器（SBC）]、[路由器] 或 [閘道]。



</div>

如需有關中繼伺服器的詳細資料，請參閱[Lync server 2013 中的 [轉送伺服器元件](lync-server-2013-mediation-server-component.md)]。

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中化與分散式 SIP 中繼

*集中式*SIP 中繼路由所有透過網際網路通訊協定（VoIP）流量的語音，包括分支網站流量，透過您的中央網站進行。 [集中式部署模型] 簡單、經濟高效，而且通常是使用 Lync Server 2013 實現 SIP trunks 的建議方法。

*分散式*SIP 中繼是一種部署模型，您可以在其中一個或多個分支網站上執行本機 SIP 主幹。 然後，VoIP 流量會直接從分支網站路由到服務提供者，而不需要透過中心網站。

只有在下列情況下，才需要分散式 SIP 中繼：

  - 分支網站需要 survivable 手機連線（例如 WAN 向下）。 必須針對每個分支網站來分析此需求;某些分支可能需要冗余和容錯移轉，而其他則可能不需要。

  - 在兩個中央網站之間必須具備復原能力。 您必須確定 SIP 主幹會在每個中央站台終止。 例如，如果您有都柏林及 Tukwila 的中央網站，且兩者都只使用一個網站的 SIP 主幹，則在幹線關閉時，其他網站的使用者就無法進行 PSTN 通話。

  - 分支網站與中央網站位於不同的國家/地區。 出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。 例如，在 [歐盟] 中，通訊不能離開國家/地區，也不會在本機終止並集中點。

根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹傳送所有使用者，或者您可以選擇透過 SIP 幹線在其分支網站上傳送部分使用者。 若要分析您的需求，請回答下列問題：

  - 每個網站有多大（也就是有多少使用者可供企業語音）？

  - 在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？

部署集中式或分散式 SIP 中繼的決定需要成本效益分析。 在某些情況下，您可以選擇選用分散式部署模型（即使不需要）。 在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。 您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。 例如，您可能會想要在分支網站上部署標準版伺服器，並在中央網站使用同盟，或者您可能想要部署 Survivable 分支裝置或 Survivable 分支伺服器與小型閘道。

<div>


> [!NOTE]  
> 如需分散式 SIP 中繼的詳細資料，請參閱<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP 中繼</A>。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 中繼連線類型

Lync Server 支援下列 SIP 中繼連線類型：

  - 多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。 MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。 此連線類型不需要虛擬私人網路（VPN）。 可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。

  - 沒有其他通訊的私人連線（例如租用的光纖連接或 T1 線路）通常是最可靠且安全的連線類型。 這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。 VPN 不是必要的。 私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。

  - 網際網路是成本最低的連線類型，但也是最不可靠的。 [網際網路連線] 是唯一需要 VPN 的 Lync Server SIP 中繼連線類型。

<div>

## <a name="selecting-a-connection-type"></a>選取連線類型

貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。

  - 針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。 它可以提供所需的頻寬，比專用的私人網路絡更便宜。

  - 大型企業可能需要在歐盟中使用私有光纖、T1、T3 或更高的連線（E1、E3 或較高的介面）。

  - 針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。 建議您不要針對中型或大型網站使用此連線類型。

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>頻寬需求

您的實現所需的頻寬量，取決於撥號容量（您必須能夠支援的併發呼叫數量）。 您必須考慮頻寬可用性，才能充分利用您已支付的峰值容量。 使用下列公式來計算 SIP 中繼峰值頻寬需求：

SIP 幹線峰值頻寬 = 最大同時呼叫 x （64 kbps + 標頭大小）

<div>


> [!NOTE]  
> [標頭大小] 的最大值為20個位元組。



</div>

</div>

<div>

## <a name="codec-support"></a>編解碼器支援

Lync Server 2013 只支援下列編解碼器：

  - G. 711 （主要在北美境外使用）

  - G. 711 μ-定律（適用于北美）

</div>

<div>

## <a name="internet-telephony-service-provider"></a>網際網路電話服務提供者

您實現 SIP 中繼連線的服務提供者的方式，從一個 ITSP 到另一個不同。 如需部署資訊，請聯絡您的服務提供者。 如需認證 SIP 中繼服務提供者清單，請參閱[Microsoft 整合通訊開啟互通性計畫網站](http://go.microsoft.com/fwlink/?linkid=287029)。

如需 Microsoft 認證 SIP 中繼提供者的詳細資料，請與您的 Microsoft 代表。

<div>


> [!IMPORTANT]  
> 您必須使用 Microsoft 認證服務提供者，以確保您的 ITSP 支援所有流經 SIP 幹線的功能（例如，設定及管理會話，以及支援所有延伸 VoIP 服務）。 Microsoft 技術支援不會延伸到使用 noncertified 提供者的設定。 如果您目前使用的網際網路服務提供者未經過 SIP 中繼認證，您可以選擇繼續使用該提供者作為 ISP，然後使用 Microsoft 針對 SIP 中繼認證的提供者。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

