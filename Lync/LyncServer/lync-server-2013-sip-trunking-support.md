---
title: Lync Server 2013 SIP 主幹連線支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹連線支援

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

如果您打算使用企業語音搭配 SIP 中繼，您必須部署一個轉送伺服器並確定其他基礎結構和元件符合您部署模型適當的支援需求。 如需決定是否要實現 SIP 中繼的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的 SIP 中繼概覽](lync-server-2013-overview-of-sip-trunking.md)。

您可以使用 Microsoft 整合通訊開啟企業電話結構的互通性計畫，找出合格的公用交換電話網絡（PSTN）閘道、IP-Pbx 和 SIP 中繼服務，包括合格的 IP 電話服務提供者。 如需詳細資訊，請參閱 Microsoft 整合通訊開啟交互操作[http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)性計畫網站。

<div>

## <a name="mediation-server-support"></a>中繼伺服器支援

若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間通訊會話的 proxy。 中繼伺服器會從用戶端和伺服器解碼媒體流量，並在傳送給服務提供者之前重新進行編碼。 您需要重新編碼，因為 SIP trunks 不支援某些使用的編解碼器，例如即時音訊（RTA）或適用于防火牆遍歷的互動式連接建立（ICE）通訊協定協商。

每個中繼伺服器都可以有兩個網路介面卡，提供內部和外部網路介面。 外部介面通常稱為閘道介面，因為傳統的介面是用來連接 PSTN 閘道或 IP PBX。 若要實現 SIP 幹線，您可以將外部介面連接至服務提供者的會話邊界控制器（SBC）。

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中化與分散式 SIP 中繼

*集中式*SIP 中繼路由所有透過網際網路通訊協定（VoIP）流量的語音，包括分支網站流量，以及透過您的資料中心。 [集中式部署模型] 簡單、經濟高效，而且通常是使用 Lync Server 2013 實現 SIP trunks 的最佳做法。

您可能不想透過集中式 SIP 主幹來傳送所有使用者，這要視企業中的使用模式而定。 若要分析您的需求，請回答下列問題：

  - 每個網站有多大？ 有多少使用者？

  - 在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？

*分散式*SIP 中繼是一種部署模型，您可以在其中一個或多個分支網站上執行本機 SIP 主幹。 然後，VoIP 流量會直接從分支網站路由到其服務提供者，而不需要經過您的資料中心。

只有在下列情況下，才需要分散式 SIP 中繼：

  - 分支網站需要 survivable 手機連線（例如 WAN 向下）。 如果分支需要冗余及容錯移轉，服務提供者將會收取較高的費用，且設定需要較長的時間。 這應該針對每個分支網站進行分析。 某些分支可能需要冗余和容錯移轉，而其他則可能不需要。

  - 分支網站與資料中心位於不同的國家/地區。 出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。

決定是否要部署集中式或分散式 SIP 中繼需要成本效益分析。 在某些情況下，選用分散式部署模式可能會有好處，即使不需要。 在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。 您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。

<div>


> [!NOTE]  
> 如需有關為何以及如何使用分散式 SIP 中繼的詳細資料，請參閱規劃檔中的<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支網站 SIP 中繼</A>。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 中繼連線類型

Lync Server 2013 支援下列 SIP 中繼連線類型：

  - 多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。 MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。 此連線類型不需要 VPN。 可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。

  - 沒有其他流量的私人連線通常是最可靠且安全的連線類型（例如，租光纖連接或 T1 線路）。 這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。 VPN 不是必要的。 私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。

  - 公用網際網路是成本最低的連線類型，但也是最不可靠的，以及具有最低通話能力的容量。 如果您的網際網路電話服務提供者（ITSP）支援傳輸層安全性（TLS）及安全即時傳輸通訊協定（SRTP）來加密信號與媒體流量，就能協助保護此 SIP 主幹連線類型。 如果您無法透過網際網路設定 SIP 中繼連線來使用 TLS 與 SRTP，我們強烈建議您使用 VPN 隧道來提供更安全的連線。 請與您的 ITSP，以判斷它是否提供與 SRTP 的 TLS 支援。

<div>

## <a name="selecting-a-connection-type"></a>選取連線類型

貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。

  - 針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。 它可以提供所需的頻寬，比專用的私人網路絡更便宜。

  - 大型企業可能需要專用光纖或 T1 連線。

  - 針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。 不過，對於中等大小或較大的網站，建議不要使用此連線類型。

</div>

</div>

<div>

## <a name="codec-support"></a>編解碼器支援

服務提供者 proxy 必須支援下列編解碼器：

  - G. 711 （主要在北美境外使用）

  - G. 711 μ-定律（適用于北美）

</div>

</div>

<span> </span>

</div>

</div>

</div>

