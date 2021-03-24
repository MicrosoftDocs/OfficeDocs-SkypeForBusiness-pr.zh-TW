---
title: 使用 ExpressRoute 的通話流程
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: 本文協助說明商務用 Skype Online 和 ExpressRoute 的核心通話流程原則，並為您提供一些通話流程的詳細範例，讓您正確瞭解和規劃通話流程。
ms.openlocfilehash: 968b0a991e89d8c9cfd9ef3e26e2e30806c069b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100729"
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的通話流程

本文協助說明商務用 Skype Online 和 ExpressRoute 的核心通話流程原則，並為您提供通話流程的一些詳細範例，讓您正確瞭解及規劃通話流程。

如果您是將商務用 Skype Online 部署為 Microsoft 365 或 Office 365、商務用 Skype Server 混合式或商務用 Skype 雲端連接器版的一部分，您必須瞭解商務用 Skype 用戶端與伺服器與通話流程之間的通訊，以便有效規劃、部署、操作及疑難排解商務用 Skype Online 服務。

## <a name="call-flow-overview"></a>通話流程概觀

本檔說明可傳輸這些通話流量資料的網路區段，並説明您瞭解與透過網際網路或 ExpressRoute 傳輸的流量相比，哪些流量會維持在您的網路上。 瞭解哪些流量使用 ExpressRoute，可協助評估貴公司使用 ExpressRoute 所獲得的好處，並説明您瞭解 ExpressRoute 部署指南，在您決定使用 ExpressRoute 後驗證和疑難排解您的部署。

此處所述的通話流程可能會受到您控制的各種因素影響，包括防火牆規則、NAT 組配置、代理和路由器組。 本檔假設已採用建議設定。 以下建議設定如下所述：

- [設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 URL 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 概觀](/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

未遵循上述檔所找到的設定步驟的設定和設定，其通話流程可能會與本文所述不同。 此外，您可能會發現自己有一些組組問題，例如非對稱和非優化的網路路由，或是非最佳傳輸通訊協定。 每當涉及 ExpressRoute 時，非對稱路由都是一項重要的考慮，因為 ExpressRoute 會引入 Office 365 的第二個路徑，這為在一個方向使用網際網路的路由和在另一個方向使用 ExpressRoute 的另一個路由建立可能性。 這可能會導致流量在經過狀態防火牆時，以返回方向遭到封鎖。

## <a name="network-segments-and-traffic-types"></a>網路區段和流量類型

### <a name="network-segments"></a>網路區段

在說明通話流程之前，我們需要定義一些條款，説明您瞭解商務用 Skype Online 中使用的網路區段和媒體類型。

下列通話流程圖會顯示四個不同的網路區段，每個區段是由不同組織管理 (您的內部網路、您的網路服務提供者及其網際網路對等合作夥伴，以及具有不同績效特性的 Microsoft) 。 若要瞭解網路績效目標指導方針，請參閱商務用 Skype Online 中的 [媒體質量和網路連線能力](media-quality-and-network-connectivity-performance.md)。

您可以在下方看到我們將要討論的每個網路區段。

![通話流程網路區段。](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **您的網路** 這是您控制和管理之整體網路的一部分網路區段。 這包括辦公室內的所有連接，無論是有線或無線，辦公室大樓之間，到內部部署資料中心，以及您與網際網路提供者或 ExpressRoute 合作夥伴的連線。

一般來說，您的網路邊緣有一或多個具有防火牆和/或 Proxy 伺服器的 DMZ，這些防火牆和/或 Proxy 伺服器會強制執行貴組織的安全性原則，而且只允許您設定和設定的某些網路流量。 由於您管理此網路，因此您可以直接控制網路績效，強烈建議您完成網路評定，以驗證網路網站內部以及從網路到商務用 Skype Online 之間的績效。 若要瞭解績效需求，請參閱商務用 Skype Online 中的 [媒體質量和網路連線能力](media-quality-and-network-connectivity-performance.md)。

 **網際網路** 這是網路區段，屬於您整體網路的一部分，供從網路外部連線至商務用 Skype Online 的使用者使用，且用於未配置 ExpressRoute 時的所有連線。 網際網路及其所有連線並非由您或 Microsoft 管理，因此無法判斷效果和路由路徑，這對整體通話流程和品質的影響最大。

 **ExpressRoute** 這是您整體網路的一部分網路區段，可為您提供 Microsoft 網路的專用私人連接。 這是將您的網路連線到 Microsoft 網路 (Microsoft 365 或 Office 365 資料中心) 的建議選項，適用于所有與網路速度和績效相關的工作負載，例如商務用 Skype Online 即時通訊。 ExpressRoute 在您的網路之間建立，而 Microsoft 網路則使用 [ExpressRoute](/azure/expressroute/expressroute-locations) 連接提供者來提供私人和受管理的網路，其執行時間為 99.9%，且支援服務品質 (QoS) ，可改善網路擠塞期間即時媒體的績效。

 **Microsoft 網路** 這是支援 Microsoft 365 和 Office 365 服務之整體網路的一部分網路區段。 這包括 Microsoft 365 或 Office 365 Online 伺服器之間的所有通訊。 這可能包括經過 Microsoft 網路骨幹網的流量，以及是在地理區域之間傳送的流量。

### <a name="types-of-traffic"></a>流量類型

商務用 Skype Online 的網路流量分為兩大類別，在通話流程中顯示為個別路徑：

 **即時媒體** 是封裝在 RTP (即時傳輸通訊協定) 資料，支援音訊、視視、應用程式共用和檔案傳輸工作負載。 一般而言，媒體流量對延遲高度敏感，因此您希望此流量採用最直接的路徑，並使用 UDP 做為傳輸層通訊協定，因為使用 TCP 會引入較高的延遲。

 **訊號** 是用戶端與伺服器之間的通訊連結，或是用來控制活動的其他用戶端 (例如，在呼叫啟動或傳送) 時。 雖然部分用戶端使用 HTTP 型 REST 介面，但大多數訊號流量會使用 SIP 通訊協定。 為了簡單明瞭，我們考慮使用各種訊號，在這類流量中可能會經過 HTTP 和 HTTPS 或 TLS 連接。 請注意，此流量對於延遲的敏感性要低得多，但如果端點之間的延遲超過數秒，可能會導致服務中斷或通話超時。

此流量的目的地位於所有 Microsoft [365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 或 Office 365 服務的 Office 365 URL 和 IP 位址範圍中。 針對每個 URL，它會指出該部分流量是否可能穿過 Microsoft 365 的 ExpressRoute 或 Office 365。 若圖表顯示啟用 ExpressRoute 時，網際網路仍然用於某些流量，請參閱 [Azure ExpressRoute for Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)。 必須瞭解，即使列在 ExpressRoute 上可路由的 URL 也可以從網際網路路由。 這表示在某些情況下，決定是否要使用網際網路或 ExpressRoute 取決於用戶端的位置，以及 Proxy 伺服器和防火牆的組配置。 此外，還必須瞭解，由於並非所有與 Microsoft 365 或 Office 365 相關聯的 URL 都能使用 ExpressRoute，即使您向 ExpressRoute 合作夥伴購買 ExpressRoute，也還是需要網際網路連接。

只能從網際網路送出的流量包括常見的網際網路相依性，例如憑證吊銷清單 (CRLs) 、DNS 查詢和名稱解析、共用 Microsoft 365 或 Office 365 服務的 URL ，例如 Microsoft 365 系統管理中心，以及商務用 Skype Online 的一些非即時通訊功能，例如遙測和與 Skype 消費者互通性的聯盟，以及串流用於 Skype 會議廣播的媒體。 若要協助您做出決策，請參閱使用 [ExpressRoute for Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) 進行路由，以在規劃網路路由時提供更多考慮。

## <a name="principles-for-call-flows-with-skype-for-business"></a>商務用 Skype 通話流程的原則

在我們瞭解特定通話流程案例詳細資料之前，有六項一般原則可協助您瞭解商務用 Skype 的通話流程。

1. 商務用 Skype 會議會託管在會議召集人位於同一地區。 如果召集人是 Online 使用者，則此為雲端;如果會議召集人是內部部署使用者，則位於內部部署資料中心。

2. 從用戶端到託管會議的媒體流量一直會送到會議託管的伺服器。 這可能是您管理之資料中心內的內部部署伺服器，或雲端中的 Online 伺服器。 不過，Edge 伺服器一直用於線上會議的媒體流程。

3. 對等通話的媒體流量會採取可用的最直接路由。 偏好的路由會直接傳送至遠端對等 (用戶端) ，但如果因為防火牆封鎖流量或類似情況而無法使用該路由，則一或多個 Edge 伺服器會轉傳流量。

4. 訊號流量一直會傳輸至使用者所住的伺服器，無論是線上或內部部署。 如果前端伺服器無法直接連接，將會使用 Edge 伺服器。

5. 由於用戶端防火牆組 (，加入由 Online 主持的會議的使用者一 (一或兩個 Edge 伺服器) 。

6. 如果從包含內部部署之同一個網路進行連接，加入內部部署會議的使用者通常不會使用 Edge 伺服器，而且從網路外部連接時，會使用一或兩個 Edge 伺服器。

若要深入瞭解所選媒體路徑的詳細資訊，請參閱 [ICE - Edge Media Connectivity](https://aka.ms/AVEdge)。 雖然這段影片是 Lync Server 2013，但原則和通訊協定仍然適用于商務用 Skype。

## <a name="skype-for-business-call-flows-with-expressroute"></a>商務用 Skype 通話流程與 ExpressRoute

現在，您瞭解四個不同的網路區段，以及商務用 Skype 通話流程的一些一般原則，您可以使用這項資訊來説明您瞭解哪些商務用 Skype 流量會穿過 ExpressRoute 網路區段。

一般而言，如果一個端點位於您的網路，另一個端點位於 Microsoft 365 或 Office 365 資料中心，網路流量會穿過 ExpressRoute 連接。 這包括用戶端與伺服器之間的訊號流量、電話會議期間使用的媒體流量，或使用 Online Edge 伺服器的對等通話。

如果兩個端點都能直接在網際網路上通訊，或位於您的網路內，流量不會穿過 ExpressRoute 連接。 這包括對等通話的媒體、從網際網路到內部部署的流量，或網際網路與 Microsoft 365 或 Office 365 Edge Servers 之間的任何流量。 例如，使用者從旅館加入 Online 會議。

## <a name="basic-skype-for-business-call-flow"></a>基本商務用 Skype 通話流程

為了協助您適用上述商務用 Skype 通話流程的一般主體，本文的下一節包含數個圖表供參考。 這不是所有可能的通話流程完整清單，但可協助您適用上述詳細原則。 此外，已選取圖表中的情境來涵蓋常見的部署類型，包括線上、混合式、雲端連接器，以及一種特殊案例 Skype 會議廣播。

> [!NOTE]
> 商務用 Skype 所使用的流量子集無法通過 ExpressRoute 路由，而且一定會採用網際網路路徑。 請參閱 [Office 365 URL](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) 和 IP 位址範圍，以判斷受影響的 URL。

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>從客戶網路內撥打 Microsoft 365 或 Office 365 使用者的對等通話
<a name="bk_Figure2"> </a>

針對對等通話，媒體流量會一直採用最直接的路由至目的地。 不過，訊號流量會進入 Microsoft 365 或 Office 365 資料中心，而線上使用者則位於該資料中心。 由於這兩個使用者位於同一個 WAN 上，而且沒有任何內容會阻止用戶端直接通訊，因此媒體會直接在它們之間流動。 針對這兩個使用者發出流量的訊號，會經過每個組織資料中心的 ExpressRoute 連接。 若要在此案例顯示通話流程，請參閱此說明。

 **對等通話流程**

![使用對等通話進行通話流程。](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>您網路上加入由 Online 主持的會議的線上使用者
<a name="bk_Figure3"> </a>

在對等範例中，媒體流量會一直採用最直接的路由至目的地。 不過，對於線上會議，目的地會位於雲端。 這表示從您的網路加入會議的所有使用者的媒體流量會穿過 ExpressRoute 連接，而訊號流量會傳輸至雲端。 下圖顯示媒體和訊號都會針對您網路內的使用者，執行 ExpressRoute 連接，並針對從網路外部連接到網際網路的使用者 ，例如從咖啡店或旅館直接穿過網際網路。

請記住，會議的位置是由會議召集人所定義，而不是由參與者定義。 這表示如果會議是由內部部署客戶排程，媒體流量不會在 ExpressRoute 上流向雲端，而是會將網際網路路由至會議召集人的內部部署資料中心。

Online 會議的媒體目的地為 Microsoft 365 或 Office 365 雲端內的資料中心，但資料中心可能位於與加入會議的使用者不同的地理區域。 這有兩種方式之一：

- 如果會議召集人來自與出席者或參與者不同的公司，且召集人的組織位於不同的地理位置或國家/地區。

- 如果使用者從與公司組織所在的國家/地區不同的國家/地區加入，可能是因為公司是跨國公司，或是使用者出差。

在此案例使用 ExpressRoute 的好消息是，使用 ExpressRoute 進位附加元件後，無論會議組織資料中心的召集人的地理區域如何，ExpressRoute 路徑後的資料都會自動通過 Microsoft 的骨幹。

 **線上使用者與線上會議通話流程**

![線上主持電話會議的通話流程。](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>在混合式部署中加入由內部部署使用者主持的會議
<a name="bk_Figure3"> </a>

請記住，支援主持會議的會議服務器是由會議召集人的住家位置所決定。 在此情境中，在混合式部署中加入內部部署使用者排程會議的所有使用者的媒體會流向內部部署資料中心。 線上家用使用者訊號會透過他們的組織在雲端建立，而媒體會嘗試直接連線。 在此情境中，由於這兩個使用者都是從您的網路內連線，因此可以直接進行媒體連線，因此 ExpressRoute 只會用於向線上家用使用者發出流量的訊號。 如果線上家用使用者從網際網路連線，媒體可能會穿過 ExpressRoute ，如果 Online Edge 伺服器是用來連線。

 **由混合式使用者通話流程主持的會議**

![onprem 託管的通話流程。](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>具有 Microsoft 365 或 Office 365 託管會議的內部部署 Edge 伺服器
<a name="bk_Figure5"> </a>

當混合式使用者加入 Online 主持的會議時，我們知道訊號和媒體會目的地為 Microsoft 365 或 Office 365 雲端，而且由於使用者從網際網路加入，因此通常會採用直接網際網路路徑。 不過，在某些情況下 ，例如由於防火牆限制，無法直接使用網際網路路徑。 在這種情況下，內部部署 Edge 伺服器可以轉傳媒體流量，這會導致媒體流量回到您的內部部署網路，然後再將 ExpressRoute 回路路由至雲端。

 **使用內部部署 Edge 伺服器加入線上電話會議的內部部署使用者**

![透過邊緣伺服器進行電話會議的通話流程。](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用商務用 Skype 雲端連接器版進行 PSTN 通話
<a name="bk_Figure6"> </a>

使用 [商務用 Skype Online 雲端連接器版本](https://aka.ms/CloudConnectorInstaller) 使用內部部署資源 ，例如 SIP 主幹或 PSTN 閘道，或使用最小的硬體裝置與商務用 Skype 整合，提供 PSTN 連線。 使用雲端連接器版本，使用者會以線上為首頁，並當使用者與通話方案沒有關系時，做為一般線上使用者。 PSTN 案例的訊號會穿過 ExpressRoute 連接在用戶端與雲端之間移動 ，而媒體流量會保留在 WAN 內。 在此案例中，訊號會以 Microsoft 365 或 Office 365 雲端轉場，並終止于雲端連接器。

 **透過 Microsoft 365 或 Office 365 和雲端連接器的電話系統撥打 PSTN 電話**

![使用雲端 PBX 雲端連接器進行 PSTN 通話的通話流程。](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>從客戶網路加入使用者的 Skype 會議廣播
<a name="bk_Figure6"> </a>

Skype 會議廣播是一種特殊使用案例，由兩部分會議組成，每個部分都有不同的網路傳輸設定檔。 第一部分，以及從網路績效的觀點而言最重要的是內部會議。 這是會議即時部分，包含一或多個用戶端端點，可連接到雲端中的會議服務器。 使用會議此部分傳送的資料與上述範例完全一樣，使用者會加入 Online 會議。

Skype 會議廣播的獨特之處，是使用廣播串流服務將會議發佈給大量會議出席者。 此廣播串流服務無法通過 ExpressRoute 路由，而是使用網際網路，提供內容傳遞網路與 CDN (選擇性) 支援。 瞭解廣播串流是單向媒體流程很有説明，因為出席者會聆聽但不要說話，而且支援緩衝，因此對於延遲、封包遺失和抖動等網路性能問題的敏感性要低得多。 系統針對這些問題優化廣播流量，而是針對頻寬使用進行優化，因為可能有許多出席者收到串流媒體。

 **與來自客戶網路的使用者進行 Skype 會議廣播**

![Skype 會議廣播的通話流程。](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>按部署類型顯示通話流程模式

使用上述常見通話流程範例，以及瞭解控制流量模式的一般原則，下表提供大量部署和使用案例組合的流量模式摘要。 這些表格不會收集所有可能的通話流程組合，但應可協助您進一步瞭解通話流程的一般原則。

資料會傳送，並列為組織的本地資料;不會離開客戶網路、網際網路或 ExpressRoute。 下列模式是根據最常見的網路設定 ，例如防火牆、聯盟和網際網路，並假設參與多方或聯盟流程的所有組織都有 ExpressRoute。 實際上，使用不同的設定可能會導致流量模式與下列不同。

### <a name="call-flows-for-skype-for-business-online"></a>商務用 Skype Online 的通話流程

商務用 Skype Online 使用案例會涉及家用 Online 的使用者，而且可能會從內部網路或網際網路進行通話。 內部部署伺服器不是這些案例的一部分，因此所有會議或 PSTN 相關媒體都會流向雲端，而 Online 使用者 Edge 伺服器也會位於雲端。

 **商務用 Skype Online 的通話流程摘要**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用狀況** <br/> |**端點** <br/> |**訊號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**注釋** <br/> |
|對等通話  <br/> |兩個用戶端，這兩個用戶端都位於您的網路上。  <br/> |ExpressRoute  <br/> |當地  <br/> |[從客戶網路內撥打 Microsoft 365 或 Office 365 使用者的對等通話](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|對等通話  <br/> |兩個用戶端，一個位於 (內部) ，另一個位於網際網路上的用戶端 (外部) 。  <br/> |內部使用者：ExpressRoute  <br/> 外部使用者：網際網路  <br/> |內部使用者：ExpressRoute  <br/> 外部使用者：Microsoft 365 或 Office 365 Edge 伺服器的網際網路。  <br/> |[來自客戶網路內的 Microsoft 365 或 Office 365 使用者的對等通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |假設防火牆會阻止需要 Online Edge 伺服器的用戶端之間的直接連線。 從內部使用者到 Online Edge 伺服器的流量會遵循與電話會議會議服務器類似的路徑。  <br/> |
|對聯盟組織中使用者的對等通話  <br/> |您網路上有兩個用戶端 (內部) ，而位於聯盟組織網路上的線上使用者 () 。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[您網路上加入由 Online 主持的會議的線上使用者](call-flow-using-expressroute.md#bk_Figure3) <br/> |假設防火牆會阻止用戶端之間的直接連線，需要 Online Edge 伺服器。 從內部使用者到 Online Edge 伺服器的流量會遵循與電話會議會議服務器類似的路徑。  <br/> |
|在客戶網路中按使用者加入電話會議  <br/> |雲端網路和會議服務器的用戶端。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[您網路上加入由 Online 主持的會議的線上使用者](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|在網際網路中按使用者加入電話會議  <br/> |用戶端位於雲端的網際網路和會議服務器上。  <br/> |互聯網  <br/> |互聯網  <br/> |[您網路上加入由 Online 主持的會議的線上使用者](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入由另一家公司的 on-prem Server 主持的會議  <br/> |協力廠商資料中心網路和會議服務器的用戶端。  <br/> |互聯網  <br/> |互聯網  <br/> |不適用  <br/> |由於主持會議的會議服務器位於其他客戶的內部部署網路上，因此沒有任何資料會透過 Microsoft 雲端傳遞。  <br/> |
|PSTN 通話  <br/> |客戶網路和雲端電話系統伺服器的用戶端  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[您網路上加入由 Online 主持的會議的線上使用者](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 通話  <br/> |雲端網際網路和電話系統伺服器的用戶端  <br/> |互聯網  <br/> |互聯網  <br/> |不適用  <br/> |媒體和訊號會流向 Microsoft 365 或 Office 365 資料中心。 由於用戶端端點位於網際網路上，因此所有資料都會在整個網際網路上流向 Microsoft 資料中心 (即使需要 Online Edge 伺服器才能連線) 。  <br/> |

> [!NOTE]
> ExpressRoute 會用於從位於公司網路的使用者到線上 Edge Server 的媒體路徑上，但如果使用另一個客戶內部部署的邊緣伺服器，則不會使用 ExpressRoute。

### <a name="call-flows-for-skype-for-business-hybrid"></a>商務用 Skype 混合式通話流程

混合式通話流程適用于您擁有至少包含內部部署部分使用者的商務用 Skype 部署。 本節中的通話流程包括內部部署會議，以及至少有一個內部部署家用使用者的對等或 PSTN 通話。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用狀況** <br/> |**端點** <br/> |**訊號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**注釋** <br/> |
|對等通話  <br/> |客戶網路和內部部署兩個用戶端  <br/> |當地  <br/> |當地  <br/> |[從客戶網路內撥打 Microsoft 365 或 Office 365 使用者的對等通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |由於使用者是內部部署，因此訊號會從內部部署資料中心而非雲端，在內部部署中流動。  <br/> |
|對等通話  <br/> |兩個用戶端，都從客戶網路進行連接。 其中一個位於線上，另一個則位於內部部署。  <br/> |線上使用者：ExpressRoute  <br/> 內部部署使用者：local  <br/> |當地  <br/> |[來自客戶網路內的 Microsoft 365 或 Office 365 使用者的對等通話](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有 Online 家用使用者會傳送訊號流量至雲端。  <br/> |
|對聯盟組織中使用者的對等通話  <br/> |兩個用戶端是客戶網路中內部部署使用者 (內部) ，而線上使用者則位於 (聯盟) 。  <br/> |內部使用者：local  <br/> 聯合使用者：ExpressRoute  <br/> |網際網路或 ExpressRoute (視使用線上或內部部署邊緣伺服器)   <br/> |您網路上[線上使用者](call-flow-using-expressroute.md#bk_Figure3)加入由 Online 主持的會議，以及 Microsoft [365 或 Office 365](call-flow-using-expressroute.md#bk_Figure5)託管會議的一部分內部部署 Edge 伺服器， (媒體流量) 。 <br/> |假設防火牆會阻止用戶端之間的直接連線，需要 Online Edge 伺服器。 ICE 協商會提供線上 (連線) 內部部署使用者 (內部部署 Edge 伺服器所提供的線上) 連線。  <br/> |
|在由 Online 使用者或使用者安排 (中，以使用者加入電話會議)   <br/> |雲端網路和會議服務器的內部部署使用者。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[您網路上加入由 Online 主持的會議的線上使用者](call-flow-using-expressroute.md#bk_Figure3) <br/> |電話會議的伺服器資源是由會議召集人定義。 在這種情況下，它是由 Online 使用者排程，因此資源會位在雲端。  <br/> |
|PSTN 通話  <br/> |您網路和內部部署商務用 Skype 資料中心的內部部署使用者。  <br/> |當地  <br/> |當地  <br/> |[使用商務用 Skype 雲端連接器版進行 PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> |與使用雲端連接器版本的情況類似，但該使用者是內部部署，因此訊號會保留在您的網路內。  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>使用雲端連接器的商務用 Skype 通話流程

連線至雲端連接器版本的使用者全部是線上家用版。 這表示會議會線上，而訊號會遵循與 Online 使用者相同的模式。 針對 PSTN 通話外的其他案例，商務用 Skype Online 的通話流程會與上述完全相同。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用狀況** <br/> |**端點** <br/> |**訊號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**注釋** <br/> |
|PSTN 通話  <br/> |使用雲端連接器版本在您的網路上的線上使用者。  <br/> |當地  <br/> |當地  <br/> |[使用商務用 Skype 雲端連接器版進行 PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 通話  <br/> |使用雲端連接器版網際網路的線上使用者。  <br/> |互聯網  <br/> |互聯網  <br/> |使用 [商務用 Skype 雲端連接器版與 Microsoft 365 或 Office 365](call-flow-using-expressroute.md#bk_Figure5) 託管會議與 PSTN 通話的內部部署 [Edge 伺服器組合](call-flow-using-expressroute.md#bk_Figure6)。  <br/> |網際網路使用者將透過雲端連接器中包含的 Edge 伺服器進行連接，而雲端連接器會連接到 PSTN 網路。  <br/> |

## <a name="related-topics"></a>相關主題

[ExpressRoute 檔](/azure/expressroute/)