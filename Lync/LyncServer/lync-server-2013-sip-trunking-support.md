---
title: Lync Server 2013 SIP 主幹支援
description: Lync Server 2013 SIP 主幹支援。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 427e573d88584ac8beb3bbcd54e68b13c4c42f0f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559059"
---
# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013 的 SIP 主幹支援

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

如果您打算將 Enterprise Voice 用於 SIP 主幹，您必須部署轉送伺服器，並確定其他基礎結構和元件符合部署模型適用的支援需求。 如需決定是否要執行 SIP trunk 的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 SIP](lync-server-2013-overview-of-sip-trunking.md) 主幹。

您可以使用適用于企業電話語音基礎結構的 Microsoft 整合通訊「開啟互通性」方案，尋找合格的公用交換電話網路 (PSTN) 閘道、IP PBXs 和 SIP trunk 服務，包括合格的 IP 電話語音服務提供者。 如需詳細資訊，請參閱 Microsoft 整合通訊開啟互通性計畫網站，網址為 [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309) 。

<div>

## <a name="mediation-server-support"></a>轉送伺服器支援

若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器充當 Lync Server 2013 用戶端與服務提供者之間的通訊會話 proxy。 轉送伺服器會對來自用戶端和伺服器的媒體流量進行解碼，並在將其傳送至服務提供者之前對其重新進行編碼。 重新編碼是必要的，因為 SIP 主幹不支援某些使用的編解碼器，例如即時音訊 (RTA) 或互動式連線建立 (冰) 的通訊協定協商，以進行防火牆遍歷。

每個轉送伺服器都可以有兩個網路介面卡，其提供內部和外部網路介面。 外部介面一般稱為閘道介面，因為傳統上它是用來連接到 PSTN 閘道或 IP-PBX。 若要執行 SIP 主幹，請將外部介面連接至服務提供者 (SBC) 的會話邊界控制器。

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>集中式與分散式 SIP 主幹的比較

*集中式* SIP 主幹會透過網際網路通訊協定 (VoIP) 流量（包括分支網站流量），透過您的資料中心來路由傳送所有語音。 集中式部署模型是簡單、經濟划算的，通常是以 Lync Server 2013 實施 SIP 主幹的慣用方法。

根據企業內的使用模式，您可能不想要透過集中式 SIP 主幹路由傳送所有使用者。 若要分析自身需求，請回答下列問題：

  - 每個網站有多大？ 有多少使用者？

  - 在每個網站上，哪個直接向內撥號 () 號碼會取得最多的電話？

*分散式* SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。 VoIP 流量會從分支網站直接路由傳送至其服務提供者，而不需要透過您的資料中心。

只有下列情況才必須使用分散式 SIP 主幹：

  - 分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。 如果分支需要重複和容錯移轉，服務提供者將會收費，且設定會花更長的時間。 這應該會針對每個分支網站進行分析。 您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。

  - 分支網站和資料中心位於不同的國家/地區。 基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。

決定是否要部署集中式或分散式 SIP 中繼時，需要成本效益分析。 在某些情況下，選用分散式部署模式也是有益的，即使不是必要也一樣。 在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。 與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。

<div>


> [!NOTE]  
> 如需有關如何使用分散式 SIP 主幹的原因和方式的詳細資訊，請參閱規劃檔中的 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP trunk In Lync Server 2013</A> 。



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 主幹連線類型

Lync Server 2013 支援 SIP 主幹的下列連線類型：

  - Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。 MPLS 網路的頻寬會與其他訂戶共用，並且會為每個資料封包指派一個標籤，用以區別不同訂戶的資料。 此連線類型不需要 VPN。 可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。

  - 沒有其他流量的專用連線通常是最可靠且安全的連線類型 (例如，租用的光纜光纜或 T1 線路) 。 此連線類型可提供最高的通話容量，但通常是最昂貴的容量。 此連線類型不需要 VPN。 私人連線適用於通話量大或安全性與可用性需求很高的組織。

  - 公用 Internet 是最低成本的連線類型，但也是最不可靠的，且具有最低通話能力的連線類型。 您的網際網路電話語音服務提供者 (ITSP) 可以協助保護這種 SIP 主幹連線類型（如果它支援傳輸層安全性 (TLS) 及安全 Real-Time 傳輸通訊協定 (SRTP) ，以加密信號和媒體流量）。 如果您無法透過網際網路設定 SIP 主幹連線以使用 TLS 和 SRTP，強烈建議您使用 VPN 隧道提供更安全的連線。 請與您的 ITSP 聯繫，以判斷其是否提供與 SRTP 的 TLS 支援。

<div>

## <a name="selecting-a-connection-type"></a>選取連線類型

您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。

  - 針對中型或大型企業，MPLS 網路通常會提供最大的價值。 它可以低於特殊私人網路的費率提供所需的頻寬。

  - 大型企業可能需要私人光纖或 T1 連接。

  - 對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。 不過，對於中型或大型網站，不建議使用此連線類型。

</div>

</div>

<div>

## <a name="codec-support"></a>轉碼器支援

服務提供者 proxy 必須支援下列編解碼器：

  - G.711 a-law (主要使用於北美以外的地區)

  - G.711 µ-law (使用於北美地區)

</div>

</div>

<span> </span>

</div>

</div>

</div>

