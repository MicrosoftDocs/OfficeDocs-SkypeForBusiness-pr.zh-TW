---
title: 商務用 Skype Server 中的 SIP 主幹
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 深入瞭解商務用 Skype Server 企業語音中的 SIP 主幹
ms.openlocfilehash: 6278526a83e5af4b0020c9dbb822eabad7053426
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841015"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>商務用 Skype Server 中的 SIP 主幹

深入瞭解商務用 Skype Server 企業語音中的 SIP 主幹

工作階段初始通訊協定 (SIP) 可用來為基本電話服務與其他即時通訊服務 (如立即訊息、會議、顯示狀態偵測和多媒體等) 啟動及管理 VoIP 通訊工作階段。本節將提供實作「SIP 主幹」的規劃資訊，這是一種可延伸到您區域網路邊界以外的 SIP 連線。

## <a name="what-is-sip-trunking"></a>何謂 SIP 主幹？

SIP 主幹是一種 IP 連線，可在您的組織與網際網路電話語音服務提供者 (ITSP) 之間建立延伸到防火牆以外的 SIP 通訊連結。 通常，SIP 主幹是用來將組織的中央網站連線到 ITSP。 有時候，您也可能會選擇使用 SIP 主幹將分支網站連線至 ITSP。

部署 SIP 中繼可能是簡化組織之電信的重要步驟，並準備即時通訊的最新增強功能。 SIP 主幹的其中一個主要優點是，您可以將組織的連線整合至中央網站上的公用交換電話網路 (PSTN) ，而不是其前置任務、分複用 (TDM) 主幹，這通常需要每個分支網站的個別主幹。

### <a name="cost-savings"></a>節省成本

與 SIP 主幹相關聯的成本節約可能相當大：

- 長途通話通常會透過 SIP 主幹降低成本。

- 您可以削減管理成本，並降低部署的複雜度。

- 基本速率介面 (BRI) 和主要速率介面 (PRI) 費用，可在您將 SIP 主幹直接連接至您的 ITSP 時，降低成本。 在 TDM trunk 中，服務提供者會在一分鐘內收取通話的費用。 SIP 主幹的成本可能是根據頻寬使用量而定，您可以更小、更經濟的增量購買。  (實際成本取決於您所選擇之 ITSP 的服務模型。 ) 

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>與裝載 PSTN 閘道或 IP-PBX 的 SIP Trunk

由於 SIP 主幹直接連線至您的服務提供者，所以您可以省去您的 PSTN 閘道及其管理成本和複雜性。 使用 SIP 主幹可縮短維護和管理，從而導致大量成本節約。

### <a name="expanded-voip-services"></a>擴充的 VoIP 服務

語音功能常常是部署 SIP 主幹的主要動機，但語音支援只是第一步。 透過 SIP 主幹，您可以擴充 VoIP 功能，並讓商務用 Skype Server 提供一組更豐富的服務。 例如：

- 未執行商務用 Skype Server 裝置的增強顯示狀態偵測功能可提供與行動電話的更好整合，讓您能看到使用者何時接聽行動電話。

- E9-1-1 緊急電話可讓接聽911呼叫的授權者判斷來電者的電話號碼的位置。

> [!NOTE]
> 請與您的 ITSP 取得支援的服務清單，並可為您的組織啟用這些服務。

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 主幹與直接 SIP 連線的比較

「主幹」一詞衍生自電路交換技術。 它是指將電話交換設備相連的專門實體線路。 如同其前置任務、時間分割多工 (TDM) 主幹、SIP 主幹是兩個不同 SIP 網路之間的連線，商務用 Skype Server 企業和 ITSP。 與電路交換主幹不同之處在於，SIP 主幹是可以透過任何支援的 SIP 主幹連線類型建立的虛擬連線。

另一方面，直接 SIP 連線是未穿越區域網路邊界的 SIP 連線 (亦即，它們是連線至位於您內部網路中的公用交換電話網路 (PSTN) 閘道或專用交換機 (PBX))。 如需如何使用與商務用 Skype Server 的直接 sip 連線的詳細資訊，請參閱[商務用 Skype Server 中的直接 sip](direct-sip.md)連線。

## <a name="how-do-i-implement-sip-trunking"></a>如何執行 SIP 主幹？

若要執行 SIP 主幹，您必須透過轉送伺服器路由傳送，該伺服器可充當商務用 Skype Server 用戶端與服務提供者之間的通訊會話 proxy，以及必要時的 transcodes 媒體。

每個轉送伺服器都具有內部網路介面和外部網路介面。 內部介面連接至前端伺服器。 外部介面一般稱為閘道介面，因為傳統上它是用來將轉送伺服器連接到公用交換電話網路 (PSTN) 閘道或 IP-PBX。 若要執行 SIP 主幹，您可以將轉送伺服器的外部介面連接至 ITSP 的外部 edge 元件。 ITSP 的外部 Edge 元件可以是工作階段界限控制器 (SBC)、路由器或閘道。

如需轉送伺服器的詳細資訊，請參閱[商務用 Skype Server 中的轉送伺服器元件](mediation-server.md)。

### <a name="centralized-vs-distributed-sip-trunking"></a>集中式與分散式 SIP 主幹的比較

集中式 SIP 中繼會透過您的中央網站路由傳送所有 VoIP 流量，包括分支網站流量。 集中式部署模型是簡單、經濟划算的，通常是使用商務用 Skype Server 執行 SIP 主幹的建議方法。

分散式 SIP 主幹是一種部署模型，您可以在其中執行一或多個分支網站上的本機 SIP 主幹。 VoIP 流量會從分支網站直接路由傳送至服務提供者，而不需要透過中央網站。

只有下列情況才必須使用分散式 SIP 主幹：

- 分支網站需要 survivable phone connectivity (例如，如果 WAN 停機) 。 應該針對每個分支網站來分析此需求;您的部分分支可能需要冗余和容錯移轉，但其他分支可能不需要。

- 兩部中央網站之間需要恢復功能。 您必須確定 SIP 主幹會在每個中央網站終止。 例如，如果您有都柏林和 Tukwila 中央網站，且兩者都只使用一個網站的 SIP 主幹，如果主幹中斷，其他網站的使用者將無法進行 PSTN 通話。

- 分支網站與中央網站位於不同的國家/地區。 基於相容性與法規考量，每個國家/地區至少要有一個 SIP 主幹。 以歐盟地區為例，若未在中心點上進行本機終止，通訊就只能侷限在國家/地區的範圍。

根據網站的地理位置和您在企業中預期的流量，您可能不想要透過中央 SIP 主幹路由傳送所有使用者，或者您可以選擇透過分支網站的 SIP 主幹路由傳送部分使用者。 若要分析自身需求，請回答下列問題：

- 每個網站有多大 (，也就是有多少使用者已啟用企業語音) ？

- 各網站上的哪些直接向內撥號 (DID) 號碼來電數最多？

在考量應部署集中式或分散式 SIP 主幹時，必須進行成本效益分析。 在某些情況下，即便並非必要，選擇分散式部署模型可能較有利。 在完整的集中式部署中，所有分支網站流量都透過 WAN 連結路由傳送。 與其為 WAN 連結所需的頻寬支付高額費用，您可能寧可使用分散式 SIP 主幹。 例如，您可能想要在具有同盟的中央網站的分支網站上部署 Standard Edition 的伺服器，或使用小型閘道部署 Survivable 分支裝置或 Survivable 分支伺服器。

> [!NOTE]
> 如需有關分散式 SIP 主幹的詳細資訊，請參閱[Branch site SIP trunk in 商務用 Skype Server](branch-site.md)。

### <a name="supported-sip-trunking-connection-types"></a>支援的 SIP 主幹連線類型

商務用 Skype Server 支援 SIP 主幹下列連線類型：

- Multiprotocol Label Switching (MPLS) 是可將資料從一個網路節點導向及承載到另一個網路節點的私人網路。 MPLS 網路中的頻寬是與其他訂閱者共用的，而每封資料包都會被指派標籤，以辨別來自另一位訂閱者的資料。 此連線類型不需要虛擬私人網路 (VPN)。 可能的缺點是，過多的 IP 流量可能會干擾 VoIP 作業，除非 VoIP 流量享有優先權。

- 不含其他流量的私人連線 (例如租用的光纖連線或 T1 線路) 通常會是最可靠而安全的連線類型。此連線類型可提供最高的通話承載能力，但通常也最昂貴。此連線類型不需要 VPN。私人連線適用於通話量大或安全性與可用性需求很高的組織。

- 網際網路是最經濟的連線類型，但可靠性也最低。 網際網路連線是唯一需要 VPN 的商務用 Skype Server SIP 主幹連線類型。

#### <a name="selecting-a-connection-type"></a>選取連線類型

您的企業最適合使用的 SIP 主幹連線類型，端視您的需求與預算而定。

- 對中型或較大的企業而言，MPLS 網路通常能提供最大的效益。它可以低於特殊私人網路的費率提供所需的頻寬。

- 大型企業可能需要私人光纖連線、T1、T3 或更高階的連線 (歐盟地區為 E1、E3 或更高階連線)。

- 對於具有低通話數量的小型企業或分支網站，透過網際網路的 SIP 主幹可能是最佳選擇。 不建議中型或較大的網站使用此連線類型。

### <a name="bandwidth-requirements"></a>頻寬需求

您的實作所需的頻寬量，取決於您的話務量 (您必須能夠支援的並行通話數量)。您必須將頻寬可用性納入考量，以充分使用您花錢購買的最大容量。您可以使用下列公式計算 SIP 主幹的最大頻寬需求：

SIP 主幹最大頻寬 = 同時通話數上限 x (64 kbps + 標頭大小)

> [!NOTE]
> 標頭大小上限為 20 個位元組。

### <a name="codec-support"></a>轉碼器支援

商務用 Skype Server 只支援下列編解碼器：

- G.711 a-law (主要使用於北美以外的地區)

- G.711 µ-law (使用於北美地區)

### <a name="internet-telephony-service-provider"></a>網際網路電話語音服務提供者

SIP 主幹連線之服務提供者端的實作方式，會根據 ITSP 而不同。 如需部署資訊，請連絡服務提供者。 如需認證 SIP 主幹服務提供者的清單，請參閱 [Microsoft 整合通訊開啟互通性計畫網站](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)。

如需 Microsoft 認證 SIP 主幹提供者的詳細資訊，請連絡 Microsoft 代表。

> [!IMPORTANT]
> 您必須使用 Microsoft 認證服務提供者，以確定 ITSP 支援所有周遊 SIP 主幹的功能 (例如，設定和管理工作階段，以及支援所有延伸的 VoIP 服務)。Microsoft 技術支援未延伸至使用非認證提供者的設定。如果您目前使用未獲得 SIP 主幹認證的網際網路服務提供者，則可以選擇繼續使用該提供者做為 ISP，並使用 Microsoft 認證的提供者進行 SIP 主幹作業。

### <a name="topologies-and-components-for-sip-trunking"></a>SIP 主幹的拓撲與元件

下圖描述商務用 Skype Server 中的 SIP 主幹拓撲。

**SIP 主幹拓撲**

![SIP Trunk 拓撲。](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

如圖所示，在商業網路和公用交換電話網路 (PSTN) 服務提供者之間的連線中，會使用 IP 虛擬私人網路 (VPN) 。 此私人網路的目的在於提供 IP 連線功能、增強安全性，以及 (選擇性) 取得服務品質 (QoS) 保證。 由於 VPN 的性質，您不需要使用傳輸層安全性 (TLS) 以進行 SIP 信號流量或安全即時傳輸通訊協定 (SRTP) 的媒體流量。 企業和服務提供者之間的連線是由 SIP 和即時即時傳輸通訊協定的純 TCP 連線所組成 (RTP)  (透過 UDP) 透過 IP VPN 傳送媒體隧道。 確定所有 VPN 路由器間的防火牆皆已開啟埠，以允許 VPN 路由器通訊，而且 VPN 路由器外部邊緣的 IP 位址可公開路由傳送。

> [!IMPORTANT]
> 請與您的服務提供者聯繫，以判斷其是否提供高可用性支援（包括容錯移轉）。 如果是的話，您將需要決定設定的程式。 例如，您只需要在每個轉送伺服器上設定一個 IP 位址和一個 SIP 主幹，還是需要在每個轉送伺服器上設定多個 SIP 主幹？ > 如果您有多部中央網站，也請詢問服務提供者是否有能力啟用與其他中央網站之間的連線。

> [!NOTE]
> 若為 SIP 主幹，強烈建議您部署獨立的轉送伺服器。 如需詳細資訊，請參閱部署檔中的 [部署轉送伺服器及定義對等](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) 專案。

### <a name="securing-the-mediation-server-for-sip-trunking"></a>保護 SIP 中繼的轉送伺服器

基於安全性的考慮，您應該為兩個 VPN 路由器間的每個連線設定虛擬 LAN (VLAN) 。 安裝 VLAN 的實際程式會因不同的路由器製造商而異。 如需詳細資訊，請與您的路由器廠商聯繫。

建議您遵循這些方針：

- 在周邊網路中的轉送伺服器和 VPN 路由器之間設定虛擬 LAN (VLAN)  (也稱為 DMZ、隔離區域和遮罩式子網) 。

- 不允許從路由器將廣播或多播封包傳輸至 VLAN。

- 封鎖將流量從路由器路由傳送至任何地方（轉送伺服器）的路由規則。

如果您使用 VPN 伺服器，我們建議您遵循下列指導方針：

- 在 VPN 伺服器與轉送伺服器之間設定 VLAN。

- 不允許從 VPN 伺服器將廣播或多播封包傳輸至 VLAN。

- 封鎖將 VPN 伺服器流量路由傳送至任何無所不在（轉送伺服器）的路由規則。

- 使用一般路由封裝 (GRE) ，加密 VPN 上的資料。

## <a name="see-also"></a>另請參閱

[分支網站 SIP 主幹 in 商務用 Skype Server](branch-site.md)