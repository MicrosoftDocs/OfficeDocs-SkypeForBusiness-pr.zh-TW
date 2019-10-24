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
f1keywords: None
ms.custom:
- Optimization
description: 本文將協助說明商務用 Skype Online 與 ExpressRoute 的核心通話流程原則，並提供一些通話流程的詳細範例，讓您可以正確瞭解及規劃。
ms.openlocfilehash: 59198cf24445ba486b193436b4374fea6698f146
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/18/2019
ms.locfileid: "37642778"
---
# <a name="call-flow-using-expressroute"></a>使用 ExpressRoute 的通話流程

本文將協助說明商務用 Skype Online 與 ExpressRoute 的核心通話流程原則，並提供一些通話流程的詳細範例，讓您可以正確瞭解及規劃。

如果您是在 Office 365、商務用 Skype Server 混合版或商務用 Skype 雲端連接器版本中部署商務用 Skype Online，您將需要瞭解商務用 Skype 用戶端與伺服器與通話流程之間的通訊。您可以有效地規劃、部署、操作和疑難排解商務用 Skype Online 服務。

## <a name="call-flow-overview"></a>通話流程概覽

這份檔說明可以傳送這些通話流程資料的網段，並協助您瞭解哪些流量將在網路上保持不變，並與透過網際網路或 ExpressRoute 傳送的流量進行比較。 瞭解使用 ExpressRoute 的流量可協助您評估貴公司將使用 ExpressRoute 所收到的福利，並協助您瞭解 ExpressRoute 部署指示，以在您決定之後驗證並疑難排解您的部署使用 ExpressRoute。

此處所述的通話流程可能會受到控制之下各種不同因素的影響，包括防火牆規則、NAT 配置、proxy 和路由器設定。 本檔假設已套用建議的設定。 這些建議的設定如下所述：

- [設定商務用 Skype Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [Office 365 Url 與 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [ExpressRoute 概述](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/)

未遵循上述檔中的設定步驟的設定和設定，可能會有不同的呼叫流程與我們在這裡所記錄的相同。 此外，您可能會發現配置問題，例如非對稱與不滿意的網路路由或非最佳傳輸通訊協定。 在涉及 ExpressRoute 時，非對稱路由是一個重要的考慮，因為 ExpressRoute 會將第二個路徑提供給 Office 365，這可讓使用網際網路的路由成為一個方向，而另一個路由則使用在其他方向上的 ExpressRoute。 這可能會導致流量在傳回狀態的防火牆流經時封鎖在傳回方向。

## <a name="network-segments-and-traffic-types"></a>網段與流量類型

### <a name="network-segments"></a>網段

在我們可以說明通話流程之前，我們需要定義一些字詞，協助您瞭解網路區段以及在商務用 Skype Online 中使用的媒體類型。

下列的通話流程圖顯示四個不同的網路區段，每個網段都由不同的組織（您的內部網路、您的網路服務提供者，以及其網際網路對等合作夥伴以及 Microsoft）所管理效能特性。 如需網路效能目標的指導方針，請參閱[商務用 Skype Online 中的媒體質量和網路連線效能](media-quality-and-network-connectivity-performance.md)。

在下方，您可以看到我們將討論的每個網路區段。

![通話流程網路區段。](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **您的網路**這個網段是您控制及管理的整個網路的一部分。 這包括您的辦公室內的所有連線（無論是有線或無線）、office 建築物之間、內部部署資料中心，以及您連線至網際網路供應商或 ExpressRoute 合作夥伴。

一般來說，您的網路邊緣有一個或多個使用防火牆和/或 proxy 伺服器的 DMZ，這些伺服器會強制執行您組織的安全性原則，且只允許您已設定並設定的特定網路流量。 因為您要管理這個網路，所以您可以直接控制您的網路效能，而且強烈建議您完成網路評量，以驗證您網路中的網站與商務用 Skype 的網路中的效能。Online. 若要查看效能需求，請參閱[商務用 Skype Online 中的媒體質量和網路連線效能](media-quality-and-network-connectivity-performance.md)。

 **網際網路**這是整個網路的一部分，該網路區段將由從您的網路外部連線到商務用 Skype Online 的使用者使用，且在未設定 ExpressRoute 時用於所有連線。 網際網路及其所有連線都不由您或 Microsoft 管理，所以無法決定效能與路由路徑，這將會對整個通話流程和品質產生最大的影響。

 **ExpressRoute**這個網段是整個網路的一部分，可為您提供專用、私人的 Microsoft 網路連線連線。 這是將您的網路連線至 Microsoft 網路（Office 365 資料中心）的選項，適合與網路速度和效能（例如商務用 Skype Online 即時通訊）相關的所有工作負載。 在您的網路與 Microsoft 網路之間進行 ExpressRoute 連線使用[expressroute 連線提供者](https://azure.microsoft.com/documentation/articles/expressroute-locations/)來提供私人和受管理的網路（含99.9% 的正常運作時間），並支援可改善效能的服務品質（QoS）在網路擁塞期間進行即時媒體。

 **Microsoft 網路**這個網段是支援 Office 365 服務之整個網路的一部分。 這包含 Office 365 線上伺服器之間的所有通訊。 這可能包括流經 Microsoft 網路骨幹的流量，並在地理區域之間傳送。

### <a name="types-of-traffic"></a>流量類型

商務用 Skype Online 的網路流量分為兩大類別，在通話流程中顯示為個別路徑：

 **即時媒體**是在 RTP （即時傳輸通訊協定）中封裝的資料，支援音訊、影片、應用程式共用和檔案傳輸工作負載。 一般來說，媒體流量會有很高的延遲，因此您可能會想要使用 UDP 來充分利用最直接路徑，並將 UDP 當作傳輸層通訊協定，因為使用 TCP 會帶來較高的延遲。

 [發**信號**] 是用戶端與伺服器之間的通訊連結，或用來控制活動的其他用戶端（例如，啟動通話時），以及傳送 im。 大多數的信號流量都使用 SIP 通訊協定，不過有些用戶端使用 HTTP 式的 REST 介面。 若要簡單，我們正在考慮在這種類型的流量中，透過 HTTP 和 HTTPS 或 TLS 連線來傳播的各種信號。 請務必瞭解，這項流量對延遲而言不太敏感，但如果端點之間的延遲時間超過數秒，可能會導致服務中斷或呼叫超時。

此流量的目的地在所有 Office 365 服務的[office 365 url 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)中找到。 針對每個 URL，它會指出這部分流量是否可能會遍歷 ExpressRoute for Office 365。 如果圖表顯示已啟用 ExpressRoute 時，仍在部分流量中使用網際網路，請參閱適用于[Office 365 的 Azure ExpressRoute](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)。 請務必瞭解，即使是在 ExpressRoute 上列出的可透過 ExpressRoute 路由的 Url，也可透過網際網路路由。 這表示在某些情況下，會根據用戶端的位置與 proxy 伺服器和防火牆的設定，決定是否要使用網際網路或 ExpressRoute。 此外，請務必瞭解，因為並非所有與 Office 365 相關聯的 Url 都能使用 ExpressRoute，即使您是從 ExpressRoute 合作夥伴購買 ExpressRoute，仍需要網際網路連線。

只能透過網際網路傳送的流量包括常見的網際網路相依性，例如憑證撤銷清單（Crl）、DNS 查閱和名稱解析、共用 Office 365 服務的 Url，例如 Microsoft 365 系統管理中心的 Url，以及一些商務用 Skype Online 的非即時通訊功能，例如遙測與與 Skype 消費者進行互通性的同盟，以及針對 Skype 會議廣播進行流式處理的媒體。 若要協助您做出決策，請參閱[與 ExpressRoute For Office 365 的路由](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408)，以取得規劃網路路由時的更多考慮。

## <a name="principles-for-call-flows-with-skype-for-business"></a>使用商務用 Skype 進行通話流程的原則

在取得特定通話流程案例的詳細資料之前，有六個一般原則可協助您瞭解商務用 Skype 的通話流程。

1. 商務用 Skype 會議位於會議召集人所駐留的同一個區域中。 如果召集人是線上使用者，或在內部部署資料中心（如果會議召集人是內部部署的使用者），這是在 Office 365 雲端。

2. 從用戶端傳送到託管會議的媒體流量，永遠會移至託管會議所在的伺服器。 這可能是您在 Office 365 雲端中管理或線上伺服器的資料中心內的內部部署伺服器。 不過，在線上會議的媒體流程中，通常會使用 Edge 伺服器。

3. 對等通話的媒體流量會充分利用可用的直接路線。 首選路由是直接指向遠端對等（用戶端），但如果防火牆封鎖流量或類似這樣的內容，則一或多個邊緣伺服器會中繼流量。

4. 信號流量永遠會移至使用者駐留的伺服器（線上或內部部署）。 如果前端伺服器無法直接連線，則會使用邊緣伺服器。

5. 加入線上舉行會議的使用者將永遠使用邊緣伺服器（如果是用戶端防火牆設定，則會有兩個需要）。

6. 如果您是從您的網路外部連線到相同的網路，且在連線時，會使用一或兩個邊緣伺服器來連接託管內部部署的使用者，通常不會使用邊緣伺服器。

若要深入瞭解所選媒體路徑的詳細資訊，請參閱[ICE 邊緣媒體](https://aka.ms/AVEdge)連線。 雖然此影片涉及 Lync Server 2013，但原則與通訊協定仍適用于商務用 Skype。

## <a name="skype-for-business-call-flows-with-expressroute"></a>使用 ExpressRoute 進行商務用 Skype 通話流程

現在您已經瞭解四種不同的網段，以及商務用 Skype 通話流程的一些一般指導原則，您可以使用該資訊來協助您瞭解哪些商務用 Skype 通訊會透過 ExpressRoute網路區段。

一般來說，如果您的網路中有一個端點，而且另一個端點位於 Office 365 datacenter 中，網路流量將會遍歷 ExpressRoute 連線。 這會包括用戶端與伺服器之間的信號流量、通話期間使用的媒體流量，或使用線上邊緣伺服器的對等通話。

如果兩個端點都能透過網際網路直接通訊或位於您的網路內，通信量將無法穿越 ExpressRoute 連線。 這將包含對等通話的媒體、從網際網路傳送到內部部署的流量，或網際網路與 Office 365 Edge 伺服器之間的任何流量。 例如，使用者從旅館加入線上會議。

## <a name="basic-skype-for-business-call-flow"></a>基本商務用 Skype 通話流程

為了協助您套用上述商務用 Skype 通話流程的一般原則，本文的下一節包含幾個參考圖表。 這不是所有可能的通話流程的完整清單，但旨在協助您套用上述詳細原則。 此外，圖表中的案例已選取以涵蓋常見的部署類型，包括線上、混合式、雲端連接器，以及在一個特殊的情況下，Skype 會議廣播。

> [!NOTE]
> 商務用 Skype 所使用的流量子集無法透過 ExpressRoute 路由，且永遠會採用網際網路路徑。 請參閱[Office 365 url 和 IP 位址範圍](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)，以判斷可能受影響的 url。

### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>客戶網路中的 Office 365 使用者對等呼叫
<a name="bk_Figure2"> </a>

對於對等呼叫，媒體流量永遠會最直接傳送到目的地。 不過，信號流量會傳送給線上使用者所在的 Office 365 資料中心。 因為兩個使用者都在同一個 WAN 上，而且不能防止用戶端直接通訊，所以媒體會直接在它們之間流動。 針對每個組織的資料中心的 ExpressRoute 連線，這兩個使用者都可透過信號傳送傳輸。 若要在這種情況下顯示通話流程，請參閱此。

 **對等通話流程**

![與對等通話的通話流程。](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>網路上的線上使用者加入線上託管的會議
<a name="bk_Figure3"> </a>

在對等範例中，媒體流量永遠會最直接傳送到目的地。 不過，對於線上會議，目的地位於 Office 365 雲端。 這表示從您的網路中加入會議的所有使用者的媒體流量都會遍歷 ExpressRoute 連線，而信號流量則會傳播至 Office 365 雲端。 下圖顯示的是媒體和寄件者會針對您網路中的使用者進行 ExpressRoute 連線，並直接從您的網路外部連線至網際網路的使用者（例如從咖啡[購物] 或 [旅館]。

請記住，會議的地點是由會議召集人所定義，而不是由參與者所定義。 這表示如果會議是由內部部署客戶排程，媒體流量將無法透過 ExpressRoute 流向 Office 365 雲端，但會改為將網際網路傳遞到會議召集人的內部部署資料中心。

適用于線上會議的目的地將是 Office 365 雲端內的資料中心，但資料中心與加入會議的使用者可能位於不同的地理區域。 這可能會以下列兩種方式之一發生：

- 如果會議召集人是來自于出席者或參與者以外的其他公司，且召集人組織是位於不同的地理位置或國家/地區。

- 如果使用者是從公司組織所在位置以外的其他國家/地區進行加入，可能是因為公司是跨國公司，或使用者正在旅行中。

在這種情況下，使用 ExpressRoute 的好消息是 expressroute premium 附加元件、ExpressRoute 路徑後面的資料，不論會議召集人的地理區域為何，都將會自動傳遞到 Microsoft 的主幹中組織的資料中心。

 **含線上會議通話流程的線上使用者**

![線上託管會議通話的通話流程。](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>加入混合式部署中由內部部署使用者主持的會議
<a name="bk_Figure3"> </a>

請記住，支援託管會議的會議服務器是由會議召集人的駐留位置決定。 在這種情況下，所有在混合式部署中加入由內部部署使用者排程之會議的使用者的媒體，都會流向內部部署資料中心。 線上總部使用者的通知會透過其組織在 Office 365 雲端中建立，而媒體則會嘗試直接連線。 在這種情況下，因為兩個使用者都是從您的網路內部連線，所以可以直接進行媒體連線，因此 ExpressRoute 只適用于線上穴使用者的通知流量。 如果線上穴使用者從網際網路連線，則如果使用線上邊緣伺服器進行連線，媒體就可以遍歷 ExpressRoute。

 **由混合式使用者通話流程託管的會議**

![呼叫流程託管 onprem。](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>擁有 Office 365 託管會議的內部部署邊緣伺服器
<a name="bk_Figure5"> </a>

當混合式使用者加入線上託管會議時，我們知道寄件者和媒體將是 Office 365 雲端的目的地，而且因為使用者是從網際網路加入，所以通常會採取直接的網際網路路徑。 不過，在某些情況下（例如由於防火牆限制），無法使用直接網際網路路徑。 在這種情況下，內部部署邊緣伺服器可以中繼媒體流量，這會導致媒體流量回到您的內部部署網路，然後再將 ExpressRoute 電路轉送到 Office 365 雲端。

 **內部部署使用者使用內部部署邊緣伺服器加入線上會議通話**

![電話會議的通話流程是透過邊緣伺服器進行。](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>使用商務用 Skype 雲端連接器版本進行 PSTN 通話
<a name="bk_Figure6"> </a>

使用[商務用 Skype Online 雲端連接器版本](https://aka.ms/CloudConnectorInstaller)可提供使用內部部署資源（例如 SIP 幹線或 PSTN 閘道），或使用最低硬體裝置與商務用 Skype 整合的 pstn 連通性。 使用雲端連接器 Edition，使用者可以在線上進行中，並在不涉及通話方案時充當一般的線上使用者。 PSTN 案例的信號傳送會在用戶端和在 ExpressRoute 連線的情況下（如果有的話），而且媒體流量會維持在 WAN 中。 在此案例中，發信號會在 Office 365 雲端發出，並在雲端連接器結束。

 **透過 Office 365 和雲端連接器中的電話系統進行 PSTN 通話**

![使用雲端 PBX 雲端連接器進行 PSTN 通話的通話流程。](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>從客戶網路加入的使用者的 Skype 會議廣播
<a name="bk_Figure6"> </a>

Skype 會議廣播是一個特殊的使用案例，由包含兩個部分的會議組成，每個部分都有不同的網路傳輸設定檔。 從網路效能角度來查看最重要的第一個部分，就是內部會議。 這是會議的即時部分，其中包含一或多個連線至 Office 365 雲端會議服務器的用戶端端點。 使用這部分會議所傳送的資料，與上述範例完全一樣，就是使用 Office 365 使用者加入與線上會議。

什麼是讓 Skype 會議廣播與眾不同，就是使用廣播串流服務將會議發佈到大量的會議出席者。 這個廣播串流服務無法透過 ExpressRoute 路由，而是使用可供選用的內容傳遞網路（CDN）服務支援的網際網路。 認識到廣播資料流程是單向媒體流程是很有説明的，因為出席者聆聽但不說話並支援緩衝，因此對網路效能問題（例如延遲、資料包遺失和抖動）不太敏感。 因為可能會有非常大量的出席者接收流式媒體，所以它已針對頻寬利用率進行優化，而不是針對這些問題優化廣播流量。

 **從客戶網路向使用者廣播 Skype 會議**

![Skype 會議廣播的通話流程。](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>依部署類型呼叫流程模式

透過上述常見的呼叫流程範例，以及瞭解控制交通模式的一般原則，以下表格提供大量部署與使用案例組合的流量模式摘要。 這些表格不會捕獲通話流程的所有可能組合，但應協助您進一步瞭解通話流程的一般原則。

資料會傳送，並列為組織的本機。它不會離開客戶網路、網際網路或 ExpressRoute。 下列所列的模式是以最常見的網路設定為基礎（例如防火牆、同盟和網際網路），並假設所有參與多方或同盟資料流程的組織都有 ExpressRoute。 在實際操作中，不同的設定可能會產生與下列不同的流量模式。

### <a name="call-flows-for-skype-for-business-online"></a>商務用 Skype Online 的通話流程

商務用 Skype Online 使用案例涉及連線的使用者，也可以從您的內部網路或網際網路撥打電話。 內部部署伺服器不屬於這些案例，所以所有與會議或 PSTN 相關的媒體都會流向 Office 365 雲端，而線上使用者邊緣伺服器也會位於雲端。

 **商務用 Skype Online 的通話流程摘要**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用案例** <br/> |**端點** <br/> |**信號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**筆記** <br/> |
|對等通話  <br/> |兩個用戶端，都在您的網路上。  <br/> |ExpressRoute  <br/> |局部  <br/> |[客戶網路中的 Office 365 使用者對等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|對等通話  <br/> |您網路上的兩個用戶端（內部），以及網際網路上的另一個用戶端（外部）。  <br/> |內部使用者： ExpressRoute  <br/> 外部使用者：網際網路  <br/> |內部使用者： ExpressRoute  <br/> 外部使用者：網際網路至 Office 365 Edge 伺服器。  <br/> |[客戶網路中的 Office 365 使用者對等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |假設防火牆封鎖用戶端之間的直接連線，這需要線上邊緣伺服器。 內部使用者與線上邊緣伺服器的流量遵循與會議服務器通話的類似路徑。  <br/> |
|聯盟組織中的使用者對等呼叫  <br/> |您網路上的兩個用戶端（內部），以及聯盟組織網路（同盟）上的線上使用者。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[網路上的線上使用者加入線上託管的會議](call-flow-using-expressroute.md#bk_Figure3) <br/> |假設防火牆封鎖用戶端之間的直接連接，需要線上邊緣伺服器。 內部使用者與線上邊緣伺服器的流量與會議服務器進行電話會議的類似路徑。  <br/> |
|在客戶網路中由使用者加入會議通話  <br/> |在 Office 365 雲端，您的網路和會議服務器上的用戶端。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[網路上的線上使用者加入線上託管的會議](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|在網際網路中由使用者加入會議通話  <br/> |用戶端位於 Office 365 雲端的網際網路和會議服務器上。  <br/> |互聯  <br/> |互聯  <br/> |[網路上的線上使用者加入線上託管的會議](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|加入其他公司的內部部署伺服器託管的會議  <br/> |在協力廠商資料中心的網路和會議服務器上的用戶端。  <br/> |互聯  <br/> |互聯  <br/> |不適用  <br/> |由於主持會議的會議服務器位於不同客戶的內部部署網路上，因此不會透過 Microsoft 雲端傳遞任何資料。  <br/> |
|PSTN 通話  <br/> |客戶網路中的用戶端與 Office 365 雲端的電話系統伺服器  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[網路上的線上使用者加入線上託管的會議](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|PSTN 通話  <br/> |Office 365 雲端中的網際網路和手機系統伺服器上的用戶端  <br/> |互聯  <br/> |互聯  <br/> |不適用  <br/> |媒體和通知會流向 Office 365 資料中心。 因為用戶端端點是在網際網路上，所以所有資料都會透過網際網路流過 Microsoft datacenter （即使連線需要線上邊緣伺服器）。  <br/> |

> [!NOTE]
> ExpressRoute 將用於從公司網路上的使用者的媒體路徑，到線上邊緣伺服器，但如果使用另一個客戶內部部署的邊緣伺服器，則不會使用它。

### <a name="call-flows-for-skype-for-business-hybrid"></a>商務用 Skype 混合式通話流程

如果您的商務用 Skype 部署包含至少託管內部部署的使用者，就會套用混合式通話流程。 此區段中的呼叫流程包含的是內部部署會議，以及至少有一個內部部署宿主使用者的對等或 PSTN 通話。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用案例** <br/> |**端點** <br/> |**信號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**筆記** <br/> |
|對等通話  <br/> |客戶網路上的兩個用戶端，以及駐留內部部署  <br/> |局部  <br/> |局部  <br/> |[客戶網路中的 Office 365 使用者對等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |因為使用者是託管于內部部署，所以會將資料流程從本機傳送到內部部署資料中心，而不是 Office 365 雲端。  <br/> |
|對等通話  <br/> |兩個用戶端，兩者都是從客戶網路連接。 一個是在線上，另一個則是託管內部部署。  <br/> |線上使用者： ExpressRoute  <br/> 內部部署使用者：本機  <br/> |局部  <br/> |[客戶網路中的 Office 365 使用者對等呼叫](call-flow-using-expressroute.md#bk_Figure2) <br/> |只有線上駐留的使用者才會傳送傳送信號流量給 Office 365 雲端。  <br/> |
|聯盟組織中的使用者對等呼叫  <br/> |在客戶網路（內部）和聯盟公司網路（同盟）的線上使用者中，有兩個用戶端在內部部署使用者。  <br/> |內部使用者：本機  <br/> 聯盟使用者： ExpressRoute  <br/> |網際網路或 ExpressRoute （取決於使用的是線上或內部部署邊緣伺服器）  <br/> |[您網路上的線上使用者加入在線上託管的會議](call-flow-using-expressroute.md#bk_Figure3)，以及[包含 Office 365 託管會議的內部部署邊緣伺服器](call-flow-using-expressroute.md#bk_Figure5)（適用于媒體流量）。 <br/> |假設防火牆封鎖用戶端之間的直接連接，需要線上邊緣伺服器。 ICE 協商將提供線上（由線上使用者）和內部部署邊緣伺服器（由內部部署使用者）進行連線。  <br/> |
|在客戶網路中，由使用者加入電話會議（由線上使用者排程的會議）  <br/> |在 Office 365 雲端，您的網路和會議服務器上的內部部署使用者。  <br/> |ExpressRoute  <br/> |ExpressRoute  <br/> |[網路上的線上使用者加入線上託管的會議](call-flow-using-expressroute.md#bk_Figure3) <br/> |電話會議的伺服器資源是由會議召集人所定義。 在這種情況下，它是由線上使用者排程，所以資源位於 Office 365 雲端。  <br/> |
|PSTN 通話  <br/> |您網路上的內部部署使用者以及商務用 Skype 資料中心。  <br/> |局部  <br/> |局部  <br/> |[使用商務用 Skype 雲端連接器版本進行 PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> |使用雲端連接器版本的類似案例，除了該使用者是託管于內部部署的電腦之外，所以信號仍在您的網路中。  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>使用雲端連接器進行商務用 Skype 的通話流程

將會連線到雲端連接器版本的使用者全都駐留在線上。 這表示會議將是線上的，而且寄件者必須遵循與線上使用者相同的模式。 針對 PSTN 呼叫以外的情況，通話流程將會完全如上述商務用 Skype Online 所述。

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**使用案例** <br/> |**端點** <br/> |**信號路徑** <br/> |**媒體路徑** <br/> |**範例流程** <br/> |**筆記** <br/> |
|PSTN 通話  <br/> |使用雲端連接器 Edition 在您的網路上的線上使用者。  <br/> |局部  <br/> |局部  <br/> |[使用商務用 Skype 雲端連接器版本進行 PSTN 通話](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|PSTN 通話  <br/> |使用雲端連接器 Edition 使用網際網路的線上使用者。  <br/> |互聯  <br/> |互聯  <br/> |[使用商務用 Skype 雲端連接器版本](call-flow-using-expressroute.md#bk_Figure6) [，將內部部署邊緣伺服器與 Office 365 託管會議](call-flow-using-expressroute.md#bk_Figure5)和 PSTN 通話結合。  <br/> |網際網路使用者將透過雲端連接器中包含的邊緣伺服器進行連線，而雲端連接器會連線至 PSTN 網路。  <br/> |

## <a name="related-topics"></a>相關主題

[ExpressRoute 檔](https://go.microsoft.com/fwlink/?LinkId=690285)


