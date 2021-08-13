---
title: Microsoft Teams 通話流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 瞭解Teams如何使用Office 365拓撲中的流程，以及用於對等媒體通訊的唯一小組流程。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ebe6de7773ca77964619f5d90d1c189ea8d731c8d7c242c2a04a619a33c55414
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319856"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft Teams 通話流程

> [!TIP]
> 請觀看此會話，瞭解Teams如何運用您的網路，以及如何規劃最佳的網路連接[：Teams規劃](https://aka.ms/teams-networking)。

## <a name="overview"></a>概觀

本文將說明如何在各種拓撲Teams Microsoft 365或Office 365呼叫流程。 此外，本文說明Teams對等媒體通訊的唯一流程。 檔說明這些流程、其用途，以及其來源和網路上終止。 為了本文的目的，請假設下列各項：

- Flow內部部署用戶端會使用 X 與雲端Microsoft 365或Office 365服務通訊。 它來自客戶網路，並終止為 Microsoft 365 或 Office 365。

- Flow內部部署用戶端會使用 Y 與網際網路上具有相依性Microsoft 365 Office 365通訊。 它來自客戶網路，並終止為網際網路上的端點。

本文涵蓋下列資訊：

- **背景**。 提供背景資訊，例如流程可能經過的網路、流量類型、從客戶網路到 Microsoft 365 或 Office 365 服務端點的連接指引、協力廠商元件的互通性，以及 Teams 用來選取媒體流程的原則。

- **各種拓撲中的通話流程**。 說明各種拓撲中通話流的使用方式。 針對每個拓撲，該節會列舉所有支援流程，並說明這些流程在數個使用案例中的使用方式。 針對每個使用案例，它會使用流程圖說明流程的順序和選取範圍。

- **Teams快速路由優化 。** 說明如何在部署 Express Route 進行優化時使用這些流程，以簡單拓撲說明。

## <a name="background"></a>背景

### <a name="network-segments"></a>網路區段

**客戶網路**。 這是您控制和管理的網路區段。 這包括客戶辦公室內的所有客戶連結，無論是有線或無線網路、辦公室大樓之間的連接、內部部署資料中心的連線，以及您與網際網路提供者、Express Route 或任何其他私人對等互連的關聯。

一般來說，客戶網路具有數個網路周邊與防火牆和/或 Proxy 伺服器，會強制執行貴組織的安全性原則，而且只允許您設定和設定的某些網路流量。 由於您管理此網路，因此您可以直接控制網路績效，因此我們建議您完成網路評定，以驗證網路網站內部以及網路到 Microsoft 365 或 Office 365 網路之間的績效。

**網際網路**。 這是網路區段，屬於您整體網路的一部分，由從客戶網路外部Microsoft 365或Office 365使用者使用。 一些來自客戶網路的流量也會使用Microsoft 365 Office 365。

**已流覽或來賓私人網路絡**。 這是客戶網路外部的網路區段，而非公用網際網路中的網路區段，您的使用者及其來賓可能會流覽 (，例如家用私人網路絡或企業私人網路絡，不會部署 Teams，而您的使用者及其客戶與 Teams 服務互動的位置可能位於) 。

> [!NOTE]
> 與Microsoft 365或Office 365的連接也適用于這些網路。

**Microsoft 365 或 Office 365。** 這是支援服務或Microsoft 365 Office 365區段。 它在全球發佈，在大多數位置，邊緣會靠近客戶網路。 函數包括傳輸轉場、會議服務器和媒體處理器。

**Express Route (選) 。** 這是您整體網路的一部分，網路區段會提供您與網路或Microsoft 365專用Office 365連接。

### <a name="types-of-traffic"></a>流量類型

**即時媒體**。 封裝在即時傳輸通訊通訊協定 (RTP) 支援音訊、視視和螢幕共用工作負載的資料。 一般而言，媒體流量對延遲高度敏感，因此您希望此流量採用最直接的路徑，並使用 UDP 與 TCP 做為傳輸層通訊協定，這是從品質角度分析互動式即時媒體的最佳傳輸方式。  (請注意，媒體可以使用 TCP/IP，也可以在 HTTP 通訊協定內進行加密，但因為品質影響不佳，不建議使用 ) RTP 流程，因為 SRTP 只會加密有效負載。

**訊號**。 用戶端與伺服器之間的通訊連結，或其他用來控制活動的用戶端 (例如，在呼叫啟動) 傳送立即訊息。 大多數訊號流量會使用 HTTPS 型 REST 介面，但在某些情況下 (例如 Microsoft 365 或 Office 365 與會話邊界控制器之間的) 使用 SIP 通訊協定。 請注意，此流量對於延遲的敏感性要低得多，但如果端點之間的延遲超過數秒，可能會導致服務中斷或通話超時。

### <a name="connectivity-to-microsoft-365-or-office-365"></a>與 Microsoft 365 或 Office 365

Teams[需要網際網路的網際網路連接](/office365/enterprise/assessing-network-connectivity)。 Teams URL 和 IP 位址範圍列于 Office 365 [URL 和 IP 位址範圍中](/office365/enterprise/urls-and-ip-address-ranges)。  (請注意，您必須開啟 TCP 埠 80 和 443 以及 UDP 埠 3478 到 3481 的連線。) 此外，Teams 與 商務用 Skype Online 有相依性，也必須連線至網際網路。

Teams使用標準 IETF 互動式連接建立和 ICE (流程) 連接。

### <a name="interoperability-restrictions"></a>互通性限制

**協力廠商媒體轉場**。 一Teams媒體流程 (，也就是說，其中一個媒體端點Teams) 只可Teams或商務用 Skype原生媒體轉場。 不支援協力廠商媒體轉場的互通性。  (請注意，與 PSTN 邊界上的協力廠商 SBC 必須終止 RTP/RTCP 資料流程，使用 SRTP 保護，不得轉傳至下一個躍點。) 

**協力廠商 SIP Proxy 伺服器**。 第Teams SBC 和/或閘道的 SIP 訊號對話方塊可能會Teams或商務用 Skype SIP 代理。 不支援協力廠商 SIP Proxy 的互通性。

**協力廠商 B2BUA (或 SBC) 。** 第Teams SBC 會終止來自 PSTN 的媒體流程。 不過，不支援協力廠商 SBC 在 Teams 網路 (中與協力廠商 SBC 之間的互通性Teams或 商務用 Skype端點) 。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>不建議使用 Microsoft Teams

**VPN 網路**。 不建議媒體流量 (流程 2') 。 VPN 用戶端應該使用分割Teams路由媒體流量，就像任何外部非 VPN 使用者一樣，如啟用 Lync 媒體以避開 VPN 管道[所指定](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)。

> [!NOTE]
> 雖然標題表示 Lync，但也適用于Teams Lync。

**封包圖形器**。 不建議在媒體流量中使用任何類型的封包Teams、封包檢查或封包圖形器裝置，而且可能會大幅降低品質。

### <a name="principles"></a>原則

有四個一般原則可協助您瞭解通話流程Microsoft Teams：

- 會議Microsoft Teams由第一Microsoft 365 Office 365參與者加入之同一地區的人員主持。  (請注意，如果某些拓撲中此規則有例外，將在本檔中說明這些例外，並以適當的通話流程說明。) 

- Teams或Microsoft 365媒體端點Office 365媒體處理需求使用，而不是根據通話類型使用。  (例如，點對點通話可能會使用雲端中的媒體端點來處理媒體的抄寫或錄製，而有兩個參與者的會議可能不會在雲端使用任何媒體端點。) 不過，大部分會議都會使用媒體端點進行混合和路由，而該目的會配置在會議舉辦地點。 從用戶端傳送至媒體端點的媒體流量可能會直接路由，或因客戶網路防火牆限制Microsoft 365或 Office 365使用傳輸轉送。

- 對等通話的媒體流量會採用可用的最直接路由，假設通話未強制使用雲端中的媒體端點 (請參閱先前的) 。 偏好的路由會直接傳送至遠端對等 (用戶端) ，但如果該路由不可用，則一或多個傳輸轉場會轉傳流量。 建議媒體流量不得轉譯伺服器，例如封包圖形器、VPN 伺服器等，因為這會影響媒體質量。

- 訊號流量一直會進入最接近使用者的伺服器。

若要深入瞭解所選媒體路徑的詳細資訊，請參閱瞭解 Microsoft Teams [- BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo)中的媒體流程。

## <a name="call-flows-in-various-topologies"></a>各種拓撲中的通話流程

### <a name="teams-topology"></a>Teams拓撲

此拓撲是由使用雲端Teams服務的客戶所使用，而不需要任何內部部署，例如 商務用 Skype Server 或 電話系統路由。 此外，無需 Azure Express 路由Microsoft 365或Office 365的介面即可在網際網路上完成。

[![Microsoft Teams線上通話流程圖 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*圖 1 - Teams拓撲*

請注意：

- 上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。 在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。
- Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。

您可以在本文稍後找到下列選擇性拓撲的更多相關資訊：

- 商務用 Skype混合拓撲中說明內部部署 **Teams部署**。
- 電話系統PSTN (的直接路由) 在 [直接路由Teams **拓撲中描述**。
- Express Route 在 Teams **快速路由優化中描述**。

**Flow描述**：

- **Flow 2** – 代表客戶網路上使用者啟動到網際網路的流量，作為使用者體驗Teams一部分。 這些流程的範例為 DNS 和對等媒體。
- **Flow 2'** – 代表遠端行動Teams使用者啟動流程，使用 VPN 到客戶網路。
- **Flow 3** – 代表由遠端行動Teams使用者啟動Microsoft 365或Office 365/Teams流程。
- **Flow 4** – 代表客戶網路上使用者啟動以Microsoft 365或Office 365/Teams流程。
- **Flow 5** – 代表客戶網路內使用者與另Teams使用者Teams或商務用 Skype之間的對等媒體流程。
- **Flow 6** – 代表遠端行動使用者Teams與另一個遠端行動Teams或商務用 Skype使用者之間的對等媒體流程。

#### <a name="use-case-one-to-one"></a>使用案例：一對一

一對一通話使用一般模型，來電者會取得一組包含 IP 位址/埠的候選者，包括用戶端的 ip 位址、轉傳和反射式 (公用 IP 位址，如轉傳) 候選者所看見。 來電者會傳送這些候選者給被叫方;被叫方也會取得一組類似的候選者，並將他們傳送給來電者。 STUN 連接檢查訊息會用來尋找哪些來電者/稱為方媒體路徑可以工作，並選取最佳工作路徑。 媒體 (，即使用 SRTP 保護的 RTP/RTCP 封包) 然後使用選取的候選組來送出。 傳輸轉場是部署在 Microsoft 365 Office 365。

如果本地 IP 位址/埠候選者或反射式候選者具有連線性，則媒體會選取用戶端 (或使用 NAT) 之間的直接路徑。 如果用戶端都位於客戶網路上，則應該選取直接路徑。 這需要客戶網路內的直接 UDP 連接。 如果用戶端都是移動雲端使用者，則根據 NAT/防火牆，媒體可能會使用直接連接。

如果客戶網路上有一個用戶端是內部用戶端，而一個用戶端是外部 (例如行動雲端使用者) ，則本地或反身候選者之間的直接連接不太可能正常。 在這種情況下，一個選項是使用用戶端 (的其中一個傳輸轉場候選項目，例如，內部用戶端從 Microsoft 365 或 Office 365 傳輸轉場取得轉場候選者;外部用戶端必須能夠將 STUN/RTP/RTCP 封包傳送至傳輸轉) 。 另一個選項是內部用戶端傳送給行動雲端用戶端所取得之轉送候選者。 請注意，雖然強烈建議使用媒體的 UDP 連接，但支援 TCP。

**高層級步驟**：

1. Teams使用者 A 會使用流程 2 (DNS) URL 功能變數名稱。
1. Teams使用者 A 使用流程 4 在傳輸轉Teams上配置媒體轉場埠。
1. Teams使用者 A 會使用流程 4 傳送「邀請」給 ICE 求職者Microsoft 365或Office 365。
1. Microsoft 365或Office 365使用流程 4 傳送通知Teams使用者 B。
1. Teams使用者 B 使用流程 4 在傳輸轉Teams上配置媒體轉場埠。
1. Teams使用者 B 使用流程 4 傳送「answer」給 ICE 候選者，然後使用 Teams 4 轉Flow回使用者 A。
1. Teams使用者 A Teams使用者 B 會調用 ICE 連接測試，且已選取最佳的可用媒體路徑 (請參閱下方圖表，瞭解各種使用案例) 。
1. Teams使用者使用流程 4 Microsoft 365或Office 365傳送遙測。

**在客戶網路中：**

[![Microsoft Teams線上通話流程圖 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*圖 2 - 在客戶網路中*

在步驟 7 中，已選取對等媒體流程 5。

媒體是雙向的。 流程 5 的方向表示一端會從連接的角度啟動通訊，與本檔中所有流程一致。 在這種情況下，使用哪個方向並不重要，因為兩個端點都位於客戶網路內。

**客戶網路傳送至外部使用者 (傳輸轉Teams轉) ：**

[![Microsoft Teams線上通話流程圖 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*圖 3 - 由傳輸轉 (轉Teams轉傳至外部使用者)*

在步驟 7 中，會選取流程 4，從客戶網路到 Microsoft 365 或 Office 365，以及流程 3，從遠端行動Teams使用者到 Microsoft 365 或 Office 365。 這些流程會由 Teams 傳輸轉Microsoft 365或Office 365。

媒體是雙向的，其中方向會指出哪一端從連接角度啟動通訊。 在此案例中，這些流程會使用不同的傳輸通訊協定和位址，用於訊號與媒體。

**直接使用媒體 (外部使用者) ：**

[![Microsoft Teams線上通話流程圖 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*圖 4 - 客戶網路與外部使用者 (媒體)*

在步驟 7 中，已選取流程 2，從客戶網路 (用戶端的對等) 網際網路。

- 使用遠端行動使用者直接 (不透過Microsoft 365或Office 365) 媒體是選擇性的。 換句話說，客戶可能會封鎖此路徑，以透過傳輸轉場或Microsoft 365 Office 365。

- 媒體是雙向的。 流程 2 對遠端行動使用者的方向表示一端從連接角度啟動通訊。

**VPN 使用者傳送至內部使用者 (傳輸轉Teams轉)**

[![Microsoft Teams線上通話流程圖 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*圖 5 - VPN 使用者到內部使用者 (傳輸轉Teams轉)*

VPN 與客戶網路之間的訊號是使用 flow 2'。 客戶網路與客戶或Microsoft 365之間的Office 365使用流程 4。 不過，媒體會忽略 VPN，並且使用流程 3 和 4 路由至 Teams 或 Microsoft 365 媒體轉Office 365。

**VPN 使用者至內部使用者 (媒體)**

[![Microsoft Teams線上通話流程圖 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*圖 6 - VPN 使用者至內部使用者 (媒體)*

VPN 與客戶網路之間的訊號是使用 flow 2'。 客戶網路與客戶或Microsoft 365之間的Office 365使用流程 4。 不過，媒體會忽略 VPN，並且使用流程 2 從客戶網路路由至網際網路。

媒體是雙向的。 流程 2 對遠端行動使用者的方向表示一端從連接角度啟動通訊。

**VPN 使用者到外部使用者 (媒體)**

[![Microsoft Teams通話流程圖 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*圖 7 - VPN 使用者對外部使用者 (媒體)*

VPN 使用者與客戶網路之間的訊號是使用 flow 2' ，並且使用流程 4 來Microsoft 365或Office 365。 不過，媒體會忽略 VPN，而且會使用流程 6 路由。

媒體是雙向的。 流程 6 對遠端行動使用者的方向表示一端從連接角度啟動通訊。

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>使用案例：Teams或主幹Microsoft 365 PSTN Office 365 PSTN

Microsoft 365 Office 365具有電話系統，可讓您從公用交換電話網絡或 PSTN (接聽) 。 如果 PSTN 主幹是使用 電話系統方案進行連接，則此使用案例沒有特殊的連接需求。  (如果您想要將您自己的內部部署 PSTN 主幹連接到 Microsoft 365 或 Office 365，您可以使用 電話系統路由.) 

[![Microsoft Teams線上通話流程圖 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*圖 8 - Teams透過主幹Office 365 PSTN*

#### <a name="use-case-teams-meeting"></a>使用案例：Teams會議

會議服務器中的音訊/視 (/螢幕) 是Microsoft 365 Office 365。 其公用 IP 位址必須從客戶網路取得，而且必須從 Nomadic Cloud 用戶端取得。 每個用戶端/端點必須能夠連接到會議服務器。

內部用戶端會以與一對一通話相同的方式取得本地、反身及轉傳候選者。 用戶端會以邀請將這些候選者傳送至會議服務器。 會議服務器不會使用轉接，因為它有可公開到達的 IP 位址，因此會以其本地 IP 位址候選者回應。 用戶端和會議服務器會以與一對一通話相同的方式檢查連接。

請注意：

- Teams無法加入商務用 Skype，商務用 Skype無法加入Teams會議。

- PSTN 使用者視會議的召集人 PSTN 通話和/或會議布備而選擇「撥入」或「撥出」。

- 來賓使用者或客戶使用者可以從來賓私人網路絡加入，此網路受到 FW/NAT 的嚴格規則保護。

[![Microsoft Teams線上通話流程圖 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*圖 9 - Teams會議*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>使用案例：與內部部署商務用 Skype聯合

**在傳送或Teams傳輸轉Microsoft 365轉Office 365**

[![Microsoft Teams線上通話流程圖 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*圖 10 - 在 Teams 傳輸轉場轉Office 365*

請注意：

- 根據定義，聯合是兩個租使用者之間的通訊。 在此案例中，租使用者 A 使用 Teams，會與租使用者 B 進行聯盟，商務用 Skype內部部署。 如果租使用者 B 也使用 Microsoft 365 或 Office 365，則 商務用 Skype 用戶端會使用流程 3 與 Microsoft 365 或 Office 365。

- 從聯合用戶端商務用 Skype到內部部署商務用 Skype Server的訊號與媒體超出本檔的範圍。 不過，此處說明清楚。

- 閘道會Teams商務用 Skype之間的訊號。

- 在此案例中，媒體會使用流程 4，Teams傳輸轉傳至客戶網路和遠端商務用 Skype用戶端。

**在聯盟租使用者中商務用 Skype媒體轉場的媒體**

[![Microsoft Teams線上通話流程圖 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*圖 11 - 在商務用 Skype租使用者中由媒體轉商務用 Skype轉轉的媒體*

請注意：

- 從聯合用戶端到商務用 Skype用戶端的訊號商務用 Skype Server媒體超出本檔的範圍。 不過，此處說明清楚。

- 閘道會Teams商務用 Skype之間的訊號。

- 在此案例中，媒體會使用流程 2 商務用 Skype內部部署媒體轉遞傳送至客戶網路。  (請注意，從 Teams 使用者到聯盟客戶網路中遠端媒體轉場的流量一開始會由媒體轉場封鎖，直到相反方向的流量開始流動。 不過，雙向流程會開啟雙向的) 

**直接 (對等)**

[![Microsoft Teams線上通話流程圖 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*圖 12 - 直接 (對等)*

### <a name="teams-hybrid-topology"></a>Teams混合式拓撲

此拓撲包含Teams部署商務用 Skype拓撲。

[![Microsoft Teams線上通話流程圖 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*圖 13 - Teams拓撲*

- 上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。 在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。

- Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。

其他流程 (拓撲Teams上方) ：

- **Flow 5A** – 代表客戶網路中 Teams 使用者之間的對等媒體流程，以及客戶網路邊緣的 商務用 Skype 內部部署媒體轉場。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>使用案例：Teams商務用 Skype一對一

**客戶網路中混合式**

[![Microsoft Teams線上通話流程圖 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*圖 14 - 客戶網路內部的混合式*

閘道會Teams商務用 Skype之間的訊號。 不過，媒體會使用流程 5 在客戶網路中直接對等路由。

**混合式客戶網路與外部商務用 Skype使用者 - 由Microsoft 365或Office 365**

[![Microsoft Teams線上通話流程圖 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*圖 15 - 混合式客戶網路與外部商務用 Skype使用者 - 由 Office 365*

請注意：

- 從用戶端到內部商務用 Skype的訊號商務用 Skype Server媒體超出本檔的範圍。 不過，此處說明清楚。

- 閘道會Teams商務用 Skype之間的訊號。

- 媒體會透過傳輸轉Teams透過流程 4 傳送至客戶網路。

**與外部使用者商務用 Skype混合式客戶網路 - 由內部部署 Edge 轉用**

[![Microsoft Teams線上通話流程圖 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*圖 16 - 混合式客戶網路與外部商務用 Skype使用者 - 由內部部署 Edge 轉傳*

請注意：

- 從用戶端商務用 Skype到內部部署商務用 Skype Server的訊號與媒體超出本檔的範圍。 不過，此處說明清楚。

- 閘道會橋接器連接訊號。

- 媒體是由內部商務用 Skype內部部署商務用 Skype內媒體轉Teams，以使用媒體流程 5A 傳送至客戶網路內的使用者。

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams直接路由電話系統拓撲

此拓撲包含Teams路由電話系統拓撲。

直接路由可讓您將支援的內部部署客戶擁有的會話邊界控制器 (SBC) 硬體裝置配對至 Microsoft 365 或 Office 365，然後將電話主幹連接到該裝置，以使用協力廠商公用交換電話網絡 (PSTN) 服務提供者。

若要支援此案例，客戶必須從 Microsoft 的其中一個認證合作夥伴部署經過認證的 SBC 以直接路由。 SBC 必須按照廠商的建議進行配置，並且可路由至 Microsoft 365 或 Office 365 UDP 流量。 媒體可能會直接從 Teams 和/或 商務用 Skype 用戶端流向 SBC (，而忽略 Teams 閘道) 或Teams閘道。 當主幹已配置為跳過 Teams 閘道時，與 SBC 的連線性是以 ICE 為基礎，其中 SBC 支援 ICE-Lite，而 Teams/商務用 Skype 媒體端點則支援 ICE Full Form。

[![Microsoft Teams線上通話流程圖 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*圖 17 - Teams路由電話系統拓撲

請注意：

- 上圖中箭的方向會反映影響企業周邊連接之通訊的起始方向。 在媒體用 UDP 的情況下，第一個封包 () 可能會以相反方向流動，但這些封包可能會封鎖，直到其他方向的封包流程。

- Teams與 商務用 Skype並排部署，因此用戶端會顯示為「Teams/SFB 使用者」。

其他流程 (線上拓撲Teams上) ：

- **Flow 4'** - 代表從 Microsoft 365 或 Office 365 到客戶網路的流量，用於在雲端中的 Teams 媒體伺服器與內部部署 SBC 建立連接。
- **Flow 5B** – 代表客戶網路內Teams直接路由 SBC 以旁路模式傳送 SBC 之間的媒體流程。
- **Flow 5C** – 代表 PSTN hairpin 通話旁路模式中，將 SBC 直接路由至另一個直接路由 SBC 之間的媒體流程。

**具有直接路由的內部使用者 (傳輸轉Teams轉)**

[![Microsoft Teams線上通話流程圖 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*圖 18 - 內部使用者使用直接路由 (傳輸轉Teams轉)*

請注意：

- SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號和媒體使用流程 4 和/或流程 4'。

- 使用流程 4 從客戶網路內的用戶端Microsoft 365或Office 365媒體。

**使用直接路由或 (的遠端使用者會透過媒體伺服器或 MP (路由) )**

[![Microsoft Teams線上通話流程圖 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*圖 19 - 使用直接路由或 (的遠端使用者會透過媒體伺服器或 MP (路由) )*

請注意：

- SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號和媒體使用流程 4 和/或流程 4'。

- 從網際網路用戶端將訊號和媒體Microsoft 365或Office 365使用流程 3。

**內部使用者直接路由 (媒體旁)**

[![Microsoft Teams線上通話流程圖 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*圖 20 - 內部使用者直接路由 (媒體旁)*

請注意：

- SBC 必須有一個公用 IP 位址，可路由自 Microsoft 365 或 Office 365。

- 從 SBC Microsoft 365或 Office 365，反之亦然，請使用流程 4 和/或流程 4'。

- 使用流程 4，從客戶網路內的用戶端Microsoft 365或Office 365用戶端。

- 客戶網路內從用戶端到客戶網路內 SBC 的媒體使用流程 5B。

**使用直接路由的遠端使用者 (傳輸轉Teams轉)**

[![Microsoft Teams線上通話流程圖 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*圖 21 - 使用直接路由的遠端使用者 (傳輸轉Teams轉)*

請注意：

- SBC 必須有一個公用 IP 位址，可路由至 Microsoft 365 或 Office 365 網際網路。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。

- 從用戶端在網際網路上接收Microsoft 365或Office 365使用 flow 3。

- 從網際網路用戶端到客戶網路中 SBC 的媒體會使用流程 3 和 4，由傳輸轉Teams轉場。

**遠端使用者直接路由 (直接路由)**

[![Microsoft Teams線上通話流程圖 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*圖 22 - 遠端使用者直接路由 (直接路由)*

請注意：

- SBC 必須有一個公用 IP 位址，可路由至 Microsoft 365 或 Office 365 網際網路。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。

- 從用戶端在網際網路上接收Microsoft 365或Office 365使用 flow 3。

- 從網際網路用戶端到客戶網路中 SBC 的媒體使用 flow 2。

**直接路由 (媒體) - PSTN 髮夾 (因為來電轉接/轉接)**

[![Microsoft Teams線上通話流程圖 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*圖 23 - (媒體旁) - PSTN 髮夾 (來電轉接/轉接)*

請注意：

- SBC 必須有一個公用 IP 位址，從 Microsoft 365 或 Office 365。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。

- 呼叫從 PSTN 到 PSTN 後，用戶端會結束訊號和媒體循環。

- 從客戶網路內的 SBC 實例 A 到客戶網路內的 SBC 實例 B 的媒體 (其中，A 和 B 可以使用流程 5C) 同一個實例。

**直接路由 (媒體Microsoft 365或Office 365) - 跨兩個租使用者撥打 PSTN 發釘電話**

[![Microsoft Teams線上通話流程圖 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*圖 24 - 透過 (或 Microsoft 365 直接路由Office 365) - 跨兩個租使用者撥打 PSTN 發釘通話*

請注意：

- SBC 必須有一個公用 IP 位址，從 Microsoft 365 或 Office 365。

- 從 SBC 到 Microsoft 365 或 Office 365 訊號使用流程 4 和/或流程 4'。

- 呼叫從 PSTN 到 PSTN 後，用戶端會結束訊號和媒體循環。

- 客戶網路 X 到 SBC 實例 B 內的 SBC 實例 A 媒體必須透過 Microsoft 365 或 Office 365 Media Server 轉傳，且不得使用旁路模式。

## <a name="teams-with-express-route-optimization"></a>Teams快速路由優化

[![Microsoft Teams線上通話流程圖 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*圖 25 - Teams快速路由優化*

如果 Express Route 是對齊並部署，Teams流程可能會從流程 4 重新路由到流程 1，以及從流程 4' 到流程 1'。 不過，Teams應用程式會與其他使用流程 4 和 4'的網際網路Microsoft 365或Office 365流量有硬性相依性;因此，這些流程不得封鎖。

請注意，商務用 Skype混合式 Edge 流量會路由至網際網路，而非 Express Route 來與外部使用者通訊，並與其他租使用者進行聯盟。

若要避免非對稱流程，重新路由必須同時朝兩個方向進行。 換句話說，客戶網路內的位址可以透過網際網路或 Express Route 路由路由，根據優化，但不能透過這兩者路由路由。


**客戶網路傳送至外部使用者 (傳輸轉Teams轉) ：**

[![Microsoft Teams線上通話流程圖 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*圖 26 - 由傳輸轉 (轉Teams轉傳至外部使用者)*

**高層級步驟：**

1. Teams客戶網路內的使用者會使用 flow2 解析 DNS (功能變數名稱) URL 功能變數名稱。
1. Teams客戶網路內的使用者會使用流程 1 在 Teams 傳輸轉場上配置媒體轉場埠。
1. Teams客戶網路內的使用者會使用流程 1 傳送「邀請」給 ICE 求職者，Microsoft 365或Office 365。
1. Microsoft 365或Office 365使用流程 3 將通知傳送Teams外部使用者。
1. Teams使用者使用流程 3 在傳輸轉Teams上配置媒體轉場埠。
1. Teams使用流程 3 傳送「answer」給 ICE 候選者，而流程 3 會使用第 1 個Teams傳送回Flow A。
1. Teams使用者 A 和 Teams使用者 B 會調用 ICE 連接測試，並選取流程 1 和 3，這兩個流程會由傳輸轉Teams轉。
1. Teams使用者使用流程 1 和 Microsoft 365 3 Office 365傳送遙測至或傳送資料。

> [!NOTE]
> Flow 4 必須啟用，Teams要求流程 4 的其他微服務上的應用程式相依性。
