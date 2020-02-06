---
title: 商務用 Skype Server 中的 SIP 中繼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 瞭解商務用 Skype Server 中的 SIP 中繼企業版語音
ms.openlocfilehash: 229774ef976a08031da7892dec0088d78b954b24
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802413"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>商務用 Skype Server 中的 SIP 中繼

瞭解商務用 Skype Server 中的 SIP 中繼企業版語音

會話初始通訊協定（SIP）是用來啟動及管理基本電話語音的語音 IP （VoIP）通訊會話，以及其他即時通訊服務，例如立即訊息、會議、目前狀態偵測及彩信. 本節提供有關實現 SIP trunks 的規劃資訊，這種類型的 SIP 連線延伸到您的本機網路邊界以外。

## <a name="what-is-sip-trunking"></a>什麼是 SIP 中繼？

SIP 幹線是一種 IP 連線，可在您的組織與防火牆以外的網際網路電話服務提供者（ITSP）之間建立 SIP 通訊連結。 通常，SIP 幹線是用來將貴組織的中心網站連線至 ITSP。 在某些情況下，您也可以選擇使用 SIP 中繼將分支網站連線至 ITSP。

部署 SIP 中繼可能是簡化貴組織的電訊，並準備最新的即時通訊功能的重要步驟。 SIP 中繼的主要優點之一是，您可以將貴組織的連線到中央網站的公用交換電話網絡（PSTN），而不是其前置任務、時間單位複用（TDM）中繼（通常是需要來自每個分支網站的個別幹線。

### <a name="cost-savings"></a>成本節約

與 SIP 中繼相關的成本節約可能相當重要：

- 遠距離通話通常會透過 SIP 幹線降低成本。

- 您可以削減易管理性成本，並減少部署的複雜性。

- 如果您將 SIP 主幹直接連線至 ITSP，成本較低，就可以消除基本比率介面（BRI）和主要比率介面（PRI）費用。 在 TDM 中繼中，服務提供者會以分鐘為通話付費。 SIP 中繼的成本可能是以頻寬使用量為基礎，您可以使用較小的增量來購買。 （實際成本取決於您所選擇之 ITSP 的服務模型。）

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 中繼與託管 PSTN 閘道或 IP PBX

因為 SIP trunks 直接連線至您的服務提供者，所以您可以消除 PSTN 閘道及其管理成本與複雜性。 使用 SIP 幹線，只需要減少維護與管理，即可帶來巨大的成本節約。

### <a name="expanded-voip-services"></a>擴充的 VoIP 服務

語音功能通常是部署 SIP 中繼的主要動機，但語音支援只是第一個步驟。 有了 SIP 中繼，您就可以延伸 VoIP 功能並啟用商務用 Skype Server，以提供一組更豐富的服務。 例如：

- 針對未執行商務用 Skype Server 的裝置，增強的目前狀態偵測功能可提供與行動電話的更佳整合，讓您可以查看使用者何時在行動電話上通話。

- E9-1-1 緊急通話可讓您接聽911通話的主管機構，判斷來電者與其電話號碼的位置。

> [!NOTE]
> 請與您的 ITSP 取得他們支援並可供您組織使用的服務清單。

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP Trunks 與直接 SIP 連線

[幹線] 一詞是從電路交換技術衍生而來。 它是指連接電話交換裝置的專用物理線路。 就像其前置任務一樣，時間分割複用（TDM） trunks，SIP trunks 是兩個獨立 SIP 網路之間的連線，即商務用 Skype Server enterprise 和 ITSP。 與電路交換 trunks 不同，SIP trunks 是可在任何支援的 SIP 中繼連線類型上建立的虛擬連線。

另一方面，直接 SIP 連線就是不跨越本機網路邊界的 SIP 連線（也就是，它們會連線到內部網路內的公用交換電話網絡（PSTN）閘道或私人分支 exchange （PBX）。 如需有關如何將直接 SIP 連線與商務用 Skype Server 搭配使用的詳細資訊，請參閱[商務用 Skype server 中的直接 sip](direct-sip.md)連線。

## <a name="how-do-i-implement-sip-trunking"></a>如何實現 SIP 中繼？

若要實現 SIP 中繼，您必須透過中繼伺服器路由連線，該伺服器充當商務用 Skype Server 用戶端與服務提供者之間通訊會話的 proxy，並視需要使用 transcodes 媒體。

每個中繼伺服器都有一個內部網路介面與一個外部網路介面。 內部介面會連接到前端伺服器。 外部介面通常稱為閘道介面，因為它通常是用來將中繼伺服器連線到公用交換式電話網絡（PSTN）閘道或 IP PBX。 若要實施 SIP 幹線，您可以將中繼伺服器的外部介面連接到 ITSP 的外部邊緣元件。 ITSP 的外部邊緣元件可以是 [會話邊界控制器（SBC）]、[路由器] 或 [閘道]。

如需有關中繼伺服器的詳細資訊，請參閱[商務用 Skype server 中的中繼伺服器元件](mediation-server.md)。

### <a name="centralized-vs-distributed-sip-trunking"></a>集中化與分散式 SIP 中繼

集中式 SIP 中繼會透過您的中央網站路由所有 VoIP 流量，包括分支網站流量。 集中式部署模型簡單、經濟高效，且通常是在商務用 Skype Server 上實現 SIP trunks 的建議方法。

分散式 SIP 中繼是一種部署模型，您可以在其中在一或多個分支網站上執行本機 SIP trunks。 然後，VoIP 流量會直接從分支網站路由到服務提供者，而不需要透過中心網站。

只有在下列情況下，才需要分散式 SIP 中繼：

- 分支網站需要 survivable 手機連線（例如 WAN 向下）。 必須針對每個分支網站來分析此需求;某些分支可能需要冗余和容錯移轉，而其他則可能不需要。

- 在兩個中央網站之間必須具備復原能力。 您必須確定 SIP 主幹會在每個中央站台終止。 例如，如果您有都柏林及 Tukwila 的中央網站，且兩者都只使用一個網站的 SIP 主幹，則在幹線關閉時，其他網站的使用者就無法進行 PSTN 通話。

- 分支網站與中央網站位於不同的國家/地區。 出於相容性和法律原因，您至少需要針對每個國家/地區提供一個 SIP 幹線。 例如，在 [歐盟] 中，通訊不能離開國家/地區，也不會在本機終止並集中點。

根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹傳送所有使用者，或者您可以選擇透過 SIP 幹線在其分支網站上傳送部分使用者。 若要分析您的需求，請回答下列問題：

- 每個網站有多大（也就是有多少使用者可供企業語音）？

- 在每個網站上哪一條直向撥打電話（已有）號碼會取得最多電話？

部署集中式或分散式 SIP 中繼的決定需要成本效益分析。 在某些情況下，您可以選擇選用分散式部署模型（即使不需要）。 在完整的集中式部署中，所有分支網站流量都是透過 WAN 連結路由。 您可能會想要使用分散式 SIP 中繼，而不是針對 WAN 連結所需的頻寬付費。 例如，您可能會想要在分支網站上部署標準版伺服器，並在中央網站使用同盟，或者您可能想要部署 Survivable 分支裝置或 Survivable 分支伺服器與小型閘道。

> [!NOTE]
> 如需分散式 SIP 中繼的詳細資料，請參閱[商務用 Skype 伺服器中的分支網站 SIP 中繼](branch-site.md)。

### <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 中繼連線類型

商務用 Skype 伺服器支援下列 SIP 中繼連線類型：

- 多協定標籤切換（MPLS）是一種私人網路絡，可引導並將資料從一個網路節點傳送到下一個。 MPLS 網路中的頻寬是與其他訂閱者共用的，每個資料包都指派標籤來區分訂閱者的資料與另一個訂閱者的資料。 此連線類型不需要虛擬私人網路（VPN）。 可能的缺點是，過多的 IP 流量可能會干擾 VoIP 操作，除非 VoIP 流量是有優先權的。

- 沒有其他通訊的私人連線（例如租用的光纖連接或 T1 線路）通常是最可靠且安全的連線類型。 這個連線類型提供最高的呼叫儲存容量，但通常是最昂貴的容量。 VPN 不是必要的。 私人連線適合具有高呼叫量或嚴格的安全性和可用性需求的組織。

- 網際網路是成本最低的連線類型，但也是最不可靠的。 [網際網路連線] 是唯一需要 VPN 的商務用 Skype Server SIP 中繼連線類型。

#### <a name="selecting-a-connection-type"></a>選取連線類型

貴企業最合適的 SIP 中繼連線類型取決於您的需求和預算。

- 針對中型或大型企業而言，MPLS 網路通常會提供最大的價值。 它可以提供所需的頻寬，比專用的私人網路絡更便宜。

- 大型企業可能需要在歐盟中使用私有光纖、T1、T3 或更高的連線（E1、E3 或較高的介面）。

- 針對小型企業版或含有低通話量的分支網站，透過網際網路進行 SIP 中繼可能是最佳選擇。 建議您不要針對中型或大型網站使用此連線類型。

### <a name="bandwidth-requirements"></a>頻寬需求

您的實現所需的頻寬量，取決於撥號容量（您必須能夠支援的併發呼叫數量）。 您必須考慮頻寬可用性，才能充分利用您已支付的峰值容量。 使用下列公式來計算 SIP 中繼峰值頻寬需求：

SIP 幹線峰值頻寬 = 最大同時呼叫 x （64 kbps + 標頭大小）

> [!NOTE]
> [標頭大小] 的最大值為20個位元組。

### <a name="codec-support"></a>編解碼器支援

商務用 Skype 伺服器只支援下列編解碼器：

- G. 711 （主要在北美境外使用）

- G. 711 μ-定律（適用于北美）

### <a name="internet-telephony-service-provider"></a>網際網路電話服務提供者

您實現 SIP 中繼連線的服務提供者的方式，從一個 ITSP 到另一個不同。 如需部署資訊，請聯絡您的服務提供者。 如需認證 SIP 中繼服務提供者清單，請參閱[Microsoft 整合通訊開啟互通性計畫網站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。

如需 Microsoft 認證 SIP 中繼提供者的詳細資料，請與您的 Microsoft 代表。

> [!IMPORTANT]
> 您必須使用 Microsoft 認證服務提供者，以確保您的 ITSP 支援所有流經 SIP 幹線的功能（例如，設定及管理會話，以及支援所有延伸 VoIP 服務）。 Microsoft 技術支援不會延伸到使用 noncertified 提供者的設定。 如果您目前使用的網際網路服務提供者未經過 SIP 中繼認證，您可以選擇繼續使用該提供者作為 ISP，然後使用 Microsoft 針對 SIP 中繼認證的提供者。

### <a name="topologies-and-components-for-sip-trunking"></a>SIP 中繼的拓撲與元件

下圖描述商務用 Skype 伺服器中的 SIP 中繼拓撲。

**SIP 中繼拓撲**

![SIP 主幹拓撲](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

如圖表中所示，IP 虛擬私人網路（VPN）是在商業網路與公用交換電話網絡（PSTN）服務提供者之間連線所使用。 這個私人網路絡的用途是提供 IP 連線、加強安全性，以及（選擇）取得服務品質（QoS）保證。 由於 VPN 的性質，您不需要針對媒體流量使用傳輸層安全性（TLS）來傳送 SIP 信號流量或安全即時傳輸通訊協定（SRTP）。 企業與服務提供者之間的連線是由針對 SIP 的純 TCP 連線和純時間傳輸通訊協定（RTP）（透過 UDP），透過 IP VPN 傳送媒體隧道。 確定 VPN 路由器之間的所有防火牆都已開啟埠，以允許 VPN 路由器進行通訊，以及 VPN 路由器外部邊緣的 IP 位址可公開路由。

> [!IMPORTANT]
> 請與您的服務提供者聯繫，判斷它是否提供高可用性支援，包括容錯移轉。 如果是這樣，您將需要判斷設定的程式。 例如，您是否只需要在每個中繼伺服器上設定一個 IP 位址和一個 SIP 幹線，或者您是否需要在每個中繼伺服器上設定多個 SIP trunks？ > 如果您有多個中心網站，也會詢問服務提供者是否有能力啟用與其他中心網站的連線。

> [!NOTE]
> 針對 SIP 中繼，我們強烈建議您部署獨立的中繼伺服器。 如需詳細資訊，請參閱在部署檔中[部署轉送伺服器和定義對等](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。

### <a name="securing-the-mediation-server-for-sip-trunking"></a>保護 SIP 中繼的中繼伺服器

為安全起見，您應該針對兩個 VPN 路由器之間的每個連線設定虛擬 LAN （VLAN）。 設定 VLAN 的實際處理常式會因路由器製造商而異。 如需詳細資訊，請與您的路由器廠商聯繫。

我們建議您遵循下列指導方針：

- 在中繼伺服器與周邊網路中的 VPN 路由器（也稱為 DMZ、網路隔離區域及遮罩子網）之間設定虛擬 LAN （VLAN）。

- 請勿允許將廣播或多播封包從路由器傳輸到 VLAN。

- 封鎖任何路由規則，可將流量從路由器路由到任何位置，而不是中繼伺服器。

如果您使用的是 VPN 伺服器，我們建議您遵循下列指導方針：

- 在 VPN 伺服器與中繼伺服器之間設定 VLAN。

- 請勿允許從 VPN 伺服器傳送廣播或多播資料包至 VLAN。

- 封鎖將 VPN 伺服器流量路由到任何位置的任何路由規則，而是中繼伺服器。

- 使用一般路由封裝（GRE）來加密 VPN 上的資料。

## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的分支網站 SIP 中繼](branch-site.md)

