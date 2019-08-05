---
title: Microsoft 團隊通話流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: 說明團隊如何在各種不同拓撲中使用 Office 365 流程。
ms.openlocfilehash: ecdeb6dc4e1e7219dc8c01c710877437661e0ceb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/23/2019
ms.locfileid: "36181518"
---
# <a name="microsoft-teams-call-flows"></a>Microsoft 團隊通話流程

> [!Tip]
> 請觀看下列會話, 瞭解團隊如何利用您的網路, 以及如何規劃最佳的網路連線:[團隊網路規劃](https://aka.ms/teams-networking)

## <a name="overview"></a>概觀
本文將說明團隊如何在各種不同拓撲中使用 Office 365 通話流程。 此外, 它還描述用於對等媒體通訊的獨特團隊流程。 檔會說明這些流程、其用途, 以及其在網路上的來源和終止。 針對本文的用途, 請假設下列事項:

- 內部部署的 Office 365 用戶端會使用流程 X 與雲端中的 Office 365 服務進行通訊。 它是從客戶網路產生, 並終止為 Office 365 中的端點。

- 內部部署 Office 365 用戶端使用流程 Y 來與 Office 365 所依賴的網際網路上的服務進行通訊。 它源于客戶網路, 並終止為網際網路上的端點。

本文包含下列各節:

- **背景**-提供背景資訊, 例如 Office 365 流程可能流經的網路、流量類型、從客戶網路到 Office 365 服務端點的連線指示、與協力廠商元件的互通性, 以及團隊用來選取媒體流程的原則。

- **不同拓撲中的通話流程**-說明各種拓撲中通話流程的使用方式。 針對每個拓朴, 此區段會列舉所有受支援的資料流程, 並說明如何透過幾種使用案例使用這些流程。 針對每個使用案例, 它會透過流程圖來描述資料流程的順序與選取。 

- **具有快速路由優化的小組**-說明在部署快速路由以進行優化時, 這些流程的使用方式, 以簡單拓撲說明。

## <a name="background"></a>背景
### <a name="network-segments"></a>網段
**客戶網路**: 這是您控制和管理的網路區段。 這包括客戶辦公室內的所有客戶連線 (無論是有線或無線)、office 建築物之間、內部部署資料中心, 以及您連線至網際網路供應商、快速路由或任何其他私人對等。 

通常, 客戶網路有數個網路週邊, 且有多個防火牆和/或 proxy 伺服器, 會強制執行您組織的安全性原則, 而且只允許您已設定和設定的特定網路流量。 因為您要管理此網路, 所以您可以直接控制網路的效能, 而且強烈建議您完成網路評量, 以驗證您網路中的網站與 Office 365 網路中的網站的效能。 

**網際網路**: 這是整個網路的一部分, 該網路區段將由從客戶網路外部連線至 Office 365 的使用者所使用。 從客戶網路到 Office 365 的某些流量也會使用它。 

已**訪問/來賓私人網路**: 這是客戶網路外部的網路區段, 但不在公用網際網路中, 您的使用者和/或其客人可能會造訪。 例如, 「家用私人網路」或「企業私人網路」, 它不會部署小組, 您的使用者和/或其客戶與團隊服務可以駐留在其中。

>**注意**: 與 Office 365 的連線也適用于這些網路。

**Office 365**: 這是支援 Office 365 服務的網路區段。 它在全球各地分佈, 且最接近客戶網路在大部分位置的邊緣。 本檔中提到的函數包括傳輸中繼、會議服務器和媒體處理器。 

**快速路線 (選用)**: 這是整個網路的一部分, 可為您提供 Office 365 網路的專用專用連線。

### <a name="types-of-traffic"></a>流量類型

**即時媒體**: 在 RTP (即時傳輸通訊協定) 中封裝的資料, 支援音訊、影片和螢幕共用工作負載。 一般來說, 媒體流量會有很高的延遲, 因此您可能會希望此流量盡可能地採用最直接路徑, 並將 UDP 與 TCP 做為傳輸層通訊協定, 這是從品質觀點開始互動即時媒體的最佳傳輸. (注意: 作為最後一個手段, 媒體可以在 HTTP 通訊協定中使用 TCP/IP, 也可在 HTTP 通訊協定內進行隧道作業, 但由於不良品質的影響, 不建議您這麼做。)RTP 流程是透過 SRTP 加以保護, 其中只有負載是經過加密的。

[**通知**]: 用戶端與伺服器之間的通訊連結, 或用來控制活動的其他用戶端 (例如, 啟動通話時), 並傳送立即訊息。 大多數的信號流量都使用 HTTPS 式的 REST 介面, 但在某些情況下 (例如, Office 365 與會話邊界控制器之間的連線), 它會使用 SIP 通訊協定。 請務必瞭解, 這項流量對延遲而言不太敏感, 但如果端點之間的延遲時間超過數秒, 可能會導致服務中斷或呼叫超時。 

### <a name="connectivity-to-office-365"></a>Office 365 的連線能力

小組需要[連線至網際網路](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。 團隊端點 Url 和 IP 位址範圍會列在[Office 365 url 和 ip 位址範圍](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中。 (注意: 請開啟與 TCP 埠80和443的連線, 並需要 UDP 埠3478到3481。)此外, 小組也會對商務用 Skype Online 產生相依性的相依性, 這也必須連線到網際網路。

團隊媒體流程連線是透過標準的 IETF ICE (互動式連接建立) 程式來實現。

### <a name="interoperability-restrictions"></a>互通性限制
**協力廠商媒體繼電器**: 團隊媒體流程 (也就是, 其中一個媒體端點是團隊) 可能只會遍歷團隊或商務用 Skype 原生媒體轉送器。 不支援與協力廠商媒體轉接的互通性。 (注意: PSTN 上的協力廠商 SBC 必須結束 RTP/RTCP 串流, 並透過 SRTP 加以保護, 而不會將其轉接至下一個躍點)。

**協力廠商 SIP proxy 伺服器**: 具有協力廠商 SBC 和/或閘道的 [使用 SIP 通知 SIP] 對話方塊, 可能會遍歷小組或商務用 Skype 原生 SIP proxy。 不支援與協力廠商 SIP proxy 的互通性。

**協力廠商 B2BUA (也就是 SBC)**: 來自/到 PSTN 的團隊媒體流程是由協力廠商 SBC 終止。 不過, 不支援在小組網路中與協力廠商 SBC (也就是協力廠商 SBC 調節兩個小組/商務用 Skype 端點) 的互通性。

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Microsoft 團隊不建議的技術

**VPN 網路**: 不建議媒體流量 (即, 流程2」)。 VPN 用戶端應該使用分割式 VPN, 並路由媒體流量, 就像在中指定的https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/任何外部非 VPN 使用者。

>**注意**: 雖然標題是 Lync, 但也適用于團隊。

[**資料包 shapers**]: 不建議任何類型的資料包 snippers、資料包檢查或資料包整形服務裝置, 可能會顯著降低品質。 

### <a name="principles"></a>理念
有四個一般原則可協助您瞭解 Microsoft 團隊的通話流程:
 
1.  Microsoft 團隊會議是由 Office 365 託管于第一個參與者加入的同一個區域中。 (注意: 如果這項規則在某些拓撲中會有例外狀況, 則會在這份檔中說明, 並以適當的通話流程來說明。)

2.  Office 365 中的團隊媒體端點是根據媒體處理需求使用, 而不是以通話類型為基礎。 (例如, 點對點通話可能會使用雲端中的媒體端點來處理操作媒體及/或錄製, 而有兩個參與者的會議可能不會使用雲端中的任何媒體端點)。不過, 大部分的會議將會使用媒體端點來進行混合和路由用途, 並在託管會議的位置進行分派。 從用戶端傳送至媒體端點的媒體流量可能會直接路由, 或在 Office 365 中使用傳輸中繼 (如果由於客戶網路防火牆限制而需要)。 

3.  對等通話的媒體流量會佔用最直接的路線, 假設該通話不會要求雲端中的媒體端點 (請參閱上述 #2)。 首選路由會直接連到遠端對等 (用戶端), 但如果該路由無法使用, 則一或多個傳輸中繼將會中繼流量。 建議媒體流量不應該橫向伺服器 (例如資料包 shapers、VPN 伺服器等), 因為這會影響媒體質量。

4.  信號流量永遠會移至最接近使用者的伺服器。 

若要深入瞭解所選媒體路徑的詳細資訊, 請參閱https://www.youtube.com/watch?v=1tmHMIlAQdo。

## <a name="call-flows-in-various-topologies"></a>不同拓撲中的通話流程
### <a name="teams-topology"></a>團隊拓朴
此拓朴是由客戶使用來自雲端的團隊服務, 而不需要任何內部部署 (例如商務用 Skype Server 或電話系統直式路由)。 此外, Office 365 的介面是透過沒有 Azure Express 路由的網際網路完成。 

[![Microsoft 團隊線上通話流程圖01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*圖 1-團隊拓朴*

請注意:

- 上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。 在 UDP 的 [媒體] 中, 第一個資料包可能會以相反的方向流向, 但在其他方向的資料包都可能會遭到封鎖, 直到其他方向的資料包流動為止。
- 團隊會與商務用 Skype Online 一起進行並排部署, 因此用戶端會顯示為「團隊/SFB 使用者」。

您可以在以下文章中找到有關下列選用拓撲的詳細資訊:

- 商務用 Skype 內部部署在**團隊混合式拓撲**中有說明。
- [電話系統 Direct 路由 (適用于 PSTN 連線)] 會在**具有直接路由拓撲的小組**中描述。
- 在**具有快速路線優化的小組**中, 會說明快速路線。

**流程描述**:
- [**流程 2** ]: 代表使用者在使用者的小組體驗中, 由客戶網路上的使用者在網際網路上所啟動的流程。 這些流程的範例是 DNS 和對等媒體。
- [**流程 2 "** –代表由遠端行動小組使用者所啟動的流程, 其中包含 VPN 至客戶網路。 
- **流程 3** –代表由遠端行動小組使用者發起給 Office 365/團隊端點的流程。 
- [**流程 4** ]-代表使用者在客戶網路上由 Office 365/小組端點啟動的流程。
- **流程 5** –代表團隊使用者與客戶網路中的其他小組或商務用 Skype 使用者之間的對等媒體流程。
- **流程 6** –代表遠端行動小組使用者與其他遠端行動小組或網際網路上的商務用 Skype 使用者之間的對等媒體流程。

#### <a name="use-case-one-to-one"></a>使用案例: 一對一
一對一通話使用常見的模型, 在此模式中, 呼叫者會透過 IP 位址/埠來取得一組候選人, 包括本機、中繼及反身 (用戶端的公用 IP 位址 (由中繼) 候選人來查看)。 來電者會將這些候選人傳送給被叫方;呼叫的參與方也會獲得類似的候選人集合, 並將其傳送給來電者。 STUN 連線檢查訊息是用來找出哪些來電者/叫方媒體路徑正常運作, 且選取了最佳的工作路徑。 然後使用選取的候選對, 傳送媒體 (也就是透過 SRTP 保護的 RTP/RTCP 資料包)。 傳輸中繼是作為 Office 365 的一部分來部署。

如果本機 IP 位址/埠候選或反身候選人都有連通性, 則會選取用戶端 (或透過 NAT) 之間的直接路徑來供媒體使用。 如果用戶端都在客戶網路上, 則應選取直接路徑。 這需要在客戶網路中直接進行 UDP 連線。 如果用戶端都是 nomadic 雲端使用者, 則視 NAT/防火牆而定, 媒體可能會使用直接連通性。

如果客戶網路上有一個用戶端, 且有一個用戶端是外部用戶端 (例如, 行動雲端使用者), 則無法直接連線到本機或反身候選作業。 在此情況下, 選項是使用其中一個用戶端的傳輸中繼站候選人 (例如, 內部用戶端從 Office 365 中的傳輸中繼取得中繼候選人); 外部用戶端必須能夠傳送 STUN/RTP/RTCP 資料包至傳輸轉接)。 另一個選項是內部用戶端傳送至行動雲端用戶端取得的中繼候選人。 請注意, 雖然強烈建議媒體的 UDP 連線, 但支援 TCP。

**高層次步驟**:
1. 團隊使用者 A 透過 flow2 解析 URL 網功能變數名稱稱 (DNS)
2. 小組使用者 A 透過流程4在團隊傳輸中繼上分配媒體轉送埠
3. 團隊使用者 A 透過流程4至 Office 365, 透過 ICE 候選人傳送「邀請」
4. Office 365 透過流程4將通知傳送給團隊使用者 B
5. 團隊使用者 B 透過流程4在團隊傳輸中繼上分配媒體轉送埠
6. 團隊使用者 B 透過流程4傳送由 ICE 候選人提供的「回答」, 並透過流程4轉寄回小組使用者 A
7. 小組使用者 A 與團隊使用者 B 呼叫 ICE 連線測試, 並選取最佳可用媒體路徑 (請參閱下圖以查看各種使用方式)
8. 團隊使用者透過流程4傳送遙測至 Office 365

**在客戶網路中:**

[![Microsoft 團隊線上通話流程圖02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*圖 2-客戶網路內*
 
在步驟7中, 選取了對等媒體流程5。
 
媒體是雙向的。 [流程 5] 的方向代表 [一側] 會從連線的角度啟動通訊, 且與本檔中的所有流程一致。 在這種情況下, 因為兩個端點都在客戶網路內, 所以使用哪個方向是不重要的。

**外部使用者的客戶網路 (依小組傳輸轉接的媒體轉送):**

[![Microsoft 團隊線上通話流程圖03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*圖 3-外部使用者的客戶網路 (依小組傳輸轉接的媒體轉送)*
 
在步驟7、流程4中, 從客戶網路到 Office 365, 以及流程 3 (從遠端行動小組使用者到 Office 365) 已選取。 這些流程是透過 Office 365 內的小組傳輸中繼進行中繼。

媒體是雙向的, 其中的方向表示哪個端從連線性角度啟動通訊。 在這種情況下, 這些流程是透過不同的傳輸通訊協定和位址, 用於傳送信號和媒體。

**外部使用者的客戶網路 (直接媒體):**

[![Microsoft 團隊線上通話流程圖04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*圖 4-外部使用者的客戶網路 (直接媒體)*
 
在步驟7中, 選取了 [從客戶網路到網際網路 (用戶端對等)] 的 [流程 2]。
- 使用遠端行動使用者 (也就是不透過 Office 365 中繼) 的直接媒體是選擇性的。 換句話說, 客戶可能會封鎖此路徑, 透過 Office 365 中的傳輸中繼來強制執行媒體路徑。

- 媒體是雙向的。 [流程 2] 到 [遠端行動使用者] 的方向表示一個端從連線的觀點啟動通訊。 

**VPN 使用者至內部使用者 (依小組傳輸轉接的媒體轉送)**

[![Microsoft 團隊線上通話流程圖05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*圖 5-VPN 使用者至內部使用者 (依小組傳輸轉接的媒體轉送)*
 
從 VPN 到客戶網路之間的信號, 是透過流程2」。 客戶網路與 Office 365 之間的信號是透過流程4。 不過, 媒體會繞過 VPN, 而且是透過 Office 365 中的 [流程 3] 和 [4] 到 [小組媒體轉送] 進行路由。

**VPN 使用者至內部使用者 (直接媒體)**

[![Microsoft 團隊線上通話流程圖06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*圖 6-VPN 使用者至內部使用者 (直接媒體)*

從 VPN 到客戶網路之間的信號, 是透過流程2」。 客戶網路與 Office 365 之間的信號是透過流程4。 不過, 媒體會繞過 VPN, 且是透過流程2從客戶網路傳送到網際網路。

媒體是雙向的。 流向遠端行動使用者的流程2的方向, 表示一側會從連接的觀點啟動通訊。

**VPN 使用者至外部使用者 (直接媒體)**

[![Microsoft 團隊通話流程圖表07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*圖 7-VPN 使用者與外部使用者 (直接媒體)*

VPN 使用者與客戶網路之間的信號, 是透過流程2」, 並透過流程4傳送到 Office 365。 不過, 媒體會繞過 VPN, 且是透過流程6路由。

媒體是雙向的。 [流量 6] 到 [遠端行動使用者] 的方向代表, 一個端會從連接的角度啟動通訊。

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>使用案例: 透過 Office 365 幹線的團隊至 PSTN
Office 365 有一個手機系統, 可讓您撥打及接聽公用交換電話網絡 (PSTN) 撥打電話。 如果 PSTN 幹線是透過電話系統通話方案連線, 則此使用案例沒有特殊的連接需求。 (如果您想要將自己的內部部署 PSTN 幹線連接至 Office 365, 您可以使用 [電話系統直式路由]。)

[![Microsoft 團隊線上通話流程圖表08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*圖 8-透過 Office 365 幹線的團隊至 PSTN*

#### <a name="use-case-teams-meeting"></a>使用案例: 團隊會議

音訊/視頻/螢幕共用 (VBSS) 會議服務器是 Office 365 的一部分。 它的公用 IP 位址必須可從客戶網路取得, 而且必須是從 Nomadic 雲端用戶端取得的。 每個用戶端/端點都需要能夠連接到會議服務器。

內部用戶端會以與一對一通話描述的相同方式來取得本機、身式和中繼候選人。 用戶端會將這些候選人傳送給邀請中的會議服務器。 會議服務器不會使用中繼, 因為它有可公開取得的 IP 位址, 因此它會以其當地 IP 位址候選的方式回復。 用戶端與會議服務器會以與一對一通話描述的相同方式檢查連線性。 

請注意:

- 團隊用戶端無法加入商務用 Skype 會議, 且商務用 Skype 用戶端無法加入團隊會議。

- PSTN 使用者可以選擇 [撥入] 或 [撥出], 視會議的召集人 PSTN 通話和/或會議提供而定。 

- 來賓使用者或客戶使用者可以從來賓私人網路絡加入, 而這是透過 FW/NAT 與嚴格規則來保護。

[![Microsoft 團隊線上通話流程圖09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*圖 9-團隊會議*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>使用案例: 與商務用 Skype 內部部署的同盟

**媒體會依團隊在 Office 365 中傳輸的方式進行中繼**

[![Microsoft 團隊線上通話流程圖10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*圖 10-在 Office 365 中, 依團隊傳輸中繼的方式傳送媒體*

請注意:

- 同盟是依定義, 在兩個租使用者之間的通訊。 在此案例中, 使用團隊的租使用者 federates 使用商務用 Skype 內部部署。 如果承租人 B 也是使用 Office 365, 則商務用 Skype 用戶端將使用流程3與 Office 365 連線。

- 從同盟商務用 Skype 用戶端到內部部署商務用 skype 伺服器的信號和媒體不在本檔的範圍內。 不過, 這裡有清楚的說明。

- 在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。

- 在這種情況下, 媒體會透過 Office 365 中的小組傳輸中繼來轉接至客戶網路, 以及透過流程4進行遠端 Skype 用戶端。

**受同盟租使用者的商務用 Skype 媒體轉送所進行的媒體轉送**

[![Microsoft 團隊線上通話流程圖11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*圖 11-受同盟租使用者的商務用 Skype 媒體轉送所進行的媒體轉送*

請注意:

- 從同盟商務用 Skype 用戶端到內部部署商務用 skype 伺服器的信號和媒體不在本檔的範圍內。 不過, 這裡有清楚的說明。

- 在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。

- 在此案例中, 媒體是透過商務用 Skype 在內部部署媒體轉送轉接至客戶網路 (透過流程 2)。 (請注意, 媒體轉送會先將來自團隊使用者的流量傳送給聯盟客戶網路中的遠端媒體轉送, 直到相反方向的流量開始流動為止。 不過, 雙向流程會以兩個方向開啟連線。

**Direct (對等)**

[![Microsoft 團隊線上通話流程圖12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*圖 12-Direct (對等)*

### <a name="teams-hybrid-topology"></a>小組混合式拓朴
此拓朴包括擁有商務用 Skype 內部部署的小組。

[![Microsoft 團隊線上通話流程圖13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*圖 13-小組混合式拓撲*
 
- 上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。 在 UDP 的 [媒體] 中, 第一個資料包可能會以相反的方向流向, 但在其他方向的資料包都可能會遭到封鎖, 直到其他方向的資料包流動為止。

- 團隊會與商務用 Skype Online 一起進行並排部署, 因此用戶端會顯示為「團隊/SFB 使用者」。

其他流程 (在小組拓撲之上):
- [**流程 5a** ] –代表客戶網路中的小組使用者與客戶網路邊緣的商務用 Skype 內部網路媒體中繼之間的對等媒體流程。

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>使用案例: 團隊到商務用 Skype 一對一
**在客戶網路中混合式**

[![Microsoft 團隊線上通話流程圖14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*圖 14-在客戶網路中混合式*
 
在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。 不過, 媒體是透過流程5在客戶網路內以直接對等方式傳送。

**含外部商務用 Skype 使用者的混合式客戶網路 (由 Office 365 中繼)**

[![Microsoft 團隊線上通話流程圖15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*圖 15-使用外部商務用 Skype 使用者的混合式客戶網路-由 Office 365 中繼*

請注意:

- 從商務用 Skype 用戶端到內部部署商務用 Skype 伺服器的信號和媒體不在本檔的範圍內。 不過, 這裡有清楚的說明。

- 在團隊與商務用 Skype 之間的通知是由 Office 365 中的閘道橋接。

- 媒體是透過整個流程4傳送到客戶網路, 在 Office 365 中, 透過團隊傳輸繼電器進行中繼。

**含外部商務用 Skype 使用者的混合式客戶網路–由內部部署邊緣進行中繼**

[![Microsoft 團隊線上通話流程圖16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*圖 16-含外部商務用 Skype 使用者的混合式客戶網路-透過內部部署邊緣進行中繼*
 
請注意:

- 從商務用 Skype 用戶端到內部部署商務用 Skype 伺服器的信號及媒體不在本檔的範圍內。 不過, 這裡有清楚的說明。

- 在 Office 365 中, 發網關會將信號橋接。

- 在商務用 Skype 內部部署邊緣, 透過媒體流程5A 在客戶網路內, 透過商務用 Skype 媒體轉送來中繼媒體。

### <a name="teams-with-phone-system-direct-routing-topology"></a>使用電話系統直通路由拓朴的小組
此拓朴包括具有手機系統直接路由的小組。 

[直接路由] 可讓您使用協力廠商公用的電話網絡 (PSTN) 服務提供者, 方法是將支援的內部部署客戶擁有的會話邊界控制器 (SBC) 硬體裝置與 Office 365 進行配對, 然後將電話幹線連接到該裝置。 

為了支援此案例, 客戶必須部署一個認證的 SBC, 以便直接從 Microsoft 認證合作夥伴中傳送。 SBC 必須根據供應商的建議進行設定, 並可透過 Office 365 路由以進行直接的 UDP 流量。 媒體可能直接從團隊和/或商務用 Skype 用戶端傳送至 SBC (繞過團隊閘道) 或遍歷團隊閘道。 當主幹設定為略過團隊閘道時, 與 sbc 的連線是依據 ICE, 而 SBC 支援 ICE, 而商務用 Skype 媒體端點支援全冰。 

[![Microsoft 團隊線上通話流程圖17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* 圖 17-使用電話系統直通路由拓撲的團隊

請注意:

- 上方圖表上的箭號方向反映了對企業週邊的連線所產生的溝通的起始方向。 在 UDP 的 [媒體] 中, 第一個資料包可能會以相反的方向流向, 但在其他方向的資料包都可能會遭到封鎖, 直到其他方向的資料包流動為止。

- 團隊會與商務用 Skype Online 一起進行並排部署, 因此用戶端會顯示為「團隊/SFB 使用者」。

其他流程 (在團隊線上拓朴之上):
- [**流程 4** ]-代表從 Office 365 到客戶網路的流程, 用來在雲端的小組媒體伺服器與 SBC 內部部署之間建立連線。
- **流程 5b** –代表客戶網路中的小組使用者之間的媒體流程, 並以旁路模式直接傳送 SBC。
- **流程 5c** -代表在 PSTN hairpin 通話旁路模式中, 直接路由 sbc 與另一個直接路由 sbc 之間的媒體流程。

**具有直接路由的內部使用者 (依團隊在 Office 365 中傳輸中繼的方式進行媒體轉送)**

[![Microsoft 團隊線上通話流程圖18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*圖 18-在 Office 365 中使用直接路由的內部使用者 (依小組傳輸的媒體轉接)*

請注意:
 
- SBC 必須有可從 Office 365 路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號和媒體, 反之亦然, 請使用流程4和/或流程4。

- 從客戶網路中用戶端到 Office 365 的傳送信號及媒體使用流程4。


**含直接路由的遠端使用者 (透過 Office 365 中的媒體伺服器 (MP) 路由媒體)**

[![Microsoft 團隊線上通話流程圖19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*圖 19-有直接路由的遠端使用者 (媒體是透過 Office 365 中的媒體伺服器 (MP) 路由)*
 
請注意:

- SBC 必須有可從 Office 365 路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號和媒體, 反之亦然, 請使用流程4和/或流程4。

- 從網際網路上的用戶端傳送信號和媒體至 Office 365 使用流程3。

**內部使用者直接路由 (媒體旁路)**

[![Microsoft 團隊線上通話流程圖20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*圖 20-內部使用者直接路由 (媒體旁路)*
 
請注意:

- SBC 必須有可從 Office 365 路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號, 反之亦然, 使用流程4和/或流程4。

- 從客戶網路中的用戶端傳送給 Office 365 使用流程4。

- 從客戶網路中的用戶端傳送到客戶網路中的 SBC 的媒體使用流程5B。

**具有直接路由的遠端使用者 (由 Office 365 中的小組傳輸繼電器的媒體旁路中繼)**

[![Microsoft 團隊線上通話流程圖21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*圖 21: 使用直接路由的遠端使用者 (在 Office 365 中, 由小組傳輸中繼的媒體旁路中繼)*

請注意:

- SBC 必須有可從 Office 365 和網際網路路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號, 反之亦然, 使用流程4和/或流程4。

- 從網際網路上的用戶端傳送到 Office 365 的信號是使用流程3。

- 從網際網路上的用戶端到客戶網路中的 SBC 使用流程3和 4, 由 Office 365 中的小組傳輸繼電器來中繼。 

**遠端使用者直接路由 (媒體旁路直接)**

[![Microsoft 團隊線上通話流程圖22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*圖 22-遠端使用者直接路由 (媒體旁路直接)*
 
請注意:

- SBC 必須有可透過 Office 365 和網際網路路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號, 反之亦然, 使用流程4和/或流程4。

- 從網際網路上的用戶端傳送到 Office 365 的信號是使用流程3。

- 從網際網路上的用戶端媒體到客戶網路中的 SBC 使用流程2。

**直接路由 (媒體旁路)-PSTN hairpin 通話 (由於呼叫轉寄/轉接)**

[![Microsoft 團隊線上通話流程圖23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*圖 23-直接路由 (媒體旁路)-PSTN hairpin 通話 (由於呼叫轉寄/轉接)*
 
請注意:

- SBC 必須有可從 Office 365 路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號, 反之亦然, 使用流程4和/或流程4。

- 從 PSTN 到 PSTN hairpinned 通話之後, 用戶端就不在信號和媒體循環。

- 從客戶網路內部的 SBC 實例 A 到客戶網路內的 sbc 實例 B (其中 A 和 B 可以是相同實例) 的媒體則使用流程5C。

**直接路由 (透過 Office 365 的媒體)-跨兩個租使用者的 PSTN hairpin 通話**

[![Microsoft 團隊線上通話流程圖24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*圖 24-直接路由 (透過 Office 365 的媒體)-跨兩個租使用者的 PSTN hairpin 通話*
 
請注意:

- SBC 必須有可從 Office 365 路由的公用 IP 位址。

- 從 SBC 到 Office 365 的信號, 反之亦然, 使用流程4和/或流程4。

- 從 PSTN 到 PSTN hairpinned 通話之後, 用戶端就不在信號和媒體循環。

- 從位於客戶網路 X 至 SBC 實例 B 之 SBC 實例 A 的媒體, 必須透過 Office 365 媒體伺服器中繼, 且無法使用旁路模式。

## <a name="teams-with-express-route-optimization"></a>具有快速路線優化的小組

[![Microsoft 團隊線上通話流程圖25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*圖 25-具有快速路線優化的小組*
 
在直通路線已左右對齊和部署的情況下, 小組流程可能會從流程4重新路由至流程 1, 並從流程4」重新路由至 [流程 1]。 不過, 小組應用程式會透過資料流程4和 4, 在網際網路上對其他 Office 365 流程產生硬性依賴性;因此, 不一定會封鎖這些流程。 

請注意, 商務用 Skype 混合式邊緣流量會路由到網際網路, 而不是表示與外部使用者通訊, 並與其他租使用者聯盟的路線。 

若要避免非對稱資料流程, 必須在兩個方向之間進行重新路由。 換句話說, 在客戶網路中的位址是透過 [網際網路] 或 [快速路由] 進行路由, 而不是透過優化, 而是在這兩者中都可以。

例如：

**外部使用者的客戶網路 (依小組傳輸轉接的媒體轉送):**

[![Microsoft 團隊線上通話流程圖26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*圖 26-外部使用者的客戶網路 (依小組傳輸轉接的媒體轉送)*
 
**高層次步驟:**
1. 客戶網路中的小組使用者可透過 flow2 解析 URL 功能變數名稱 (DNS)
2. 客戶網路中的小組使用者會透過流程1在小組傳輸中繼上分配媒體轉送埠
3. 在客戶網路中的小組使用者透過流程1到 Office 365 傳送「邀請」給 ICE 候選人
4. OFFICE 365 透過流程3將通知傳送給外部團隊使用者
5. 團隊外部使用者透過流程3在團隊傳輸中繼上分配媒體轉送埠
6. 團隊外部使用者透過流程3傳送「回答」與 ICE 候選人, 然後透過流程3轉寄傳回給小組使用者 A
7. 小組使用者 A 與團隊使用者 B 呼叫 ICE 連線測試, 並選取 [流程 1] 和 [3], 這些是由 Office 365 中的小組傳輸繼電器來中繼
8. 團隊使用者透過流程1和 3, 將遙測傳送至 Office 365

>**注意**: 必須啟用流程 4, 才能支援在要求流程4的其他微服務上使用小組應用程式的相依性。
