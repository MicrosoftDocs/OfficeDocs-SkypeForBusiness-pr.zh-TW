---
title: 在商務用 Skype 中規劃位置基礎路由
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 規劃商務用 Skype Server 企業語音中的位置基礎路由，包括與同時震鈴和委派的互動，以及位置基礎路由支援的案例。
ms.openlocfilehash: 928a44ed9484f1766013404d23b61a2cc56841d2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741970"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>在商務用 Skype 中規劃位置基礎路由

規劃商務用 Skype Server 企業語音中的位置基礎路由，包括與同時震鈴和委派的互動，以及位置基礎路由支援的案例。

Location-Based 路由可讓您根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。 Location-Based 路由是通話管理功能，可控制商務用 Skype Server 傳送通話的方式。 它會根據商務用 Skype 來電者的地理位置，強制執行呼叫授權規則，以判斷通話是否可以路由傳送至 PBX 或 PSTN 端點。

Location-Based 路由引進一組新的規則，可修改國內和國際 PSTN 通話的路由，以避免收費旁路。 Location-Based 路由可讓您靈活地將這些規則的範圍設定為特定區域、特定閘道或特定使用者集。

下列案例說明 Location-Based 路由可強制執行的主要限制類型：

- Egress 呼叫-Location-Based 路由可強制撥出電話撥出電話至與來電者防止 pstn 長途電話旁路的 pstn 閘道，這樣可防止對來電者以外的 pstn 閘道撥出來電。

- 當傳入通話所在的 pstn 閘道與呼叫的商務用 Skype 使用者不在相同地區時，接來電 Location-Based 路由可防止傳入 PSTN 來電撥打商務用 Skype 端點。

- 未知地區-Location-Based 路由會限制位於未決定位置之使用者傳入和傳出 PSTN 來電 (亦即從網際網路連線或位於未知地區) 的遠端使用者。

- 國際地區-如果找不到使用者位置的閘道，Location-Based 路由會透過國際 PSTN 閘道來傳送撥出電話。

## <a name="guidance-for-where-to-apply-location-based-routing"></a>將 Location-Based 路由套用至何處的指導方針

根據情況而定，您可以在使用者的端點網路網站位置或 PSTN 閘道的網路網站位置上套用此 Location-Based 路由。 本主題提供如何套用 Location-Based 路由的指導方針。

### <a name="applying-location-based-routing-at-the-users-location"></a>在使用者的位置套用 Location-Based 路由

Location-Based 路由利用 E9-1-1、CAC 和媒體旁路所使用商務用 Skype Server 中所定義的相同網路地區、網站和子網，以避免 PSTN 免付費旁路。 使用者的位置取決於連線之使用者商務用 Skype 端點 (s) 的 IP 子網。 每個 IP 子網都會與網路網站產生關聯，該網站會匯總成系統管理員所定義的網路地區。 Location-Based 會根據使用者的網路網站強制進行路由傳送。

Location-Based 路由規則會依每個網路網站套用，這表示一組指定的規則會套用至位於相同網路網站中 Location-Based 路由的所有啟用端點。 管理員可以將 Location-Based 路由套用到需要該網站的網站。

您可以在每個網路網站上定義語音路由策略，以定義特定的 PSTN 閘道，以供位於網路網站中的所有使用者用來呼叫 PSTN 電話號碼。 這類語音路由原則會優先于使用者語音原則所定義的路由，當使用者位於啟用 Location-Based 路由的網路網站時，它會防止透過已啟用 Location-Based 路由的其他 PSTN 閘道路由呼叫。 當商務用 Skype 使用者撥打 PSTN 電話時，使用者的語音原則會決定使用者是否有權進行通話。 如果使用者的語音原則允許使用者撥打電話，Location-Based 路由決定來電應來自哪個 PSTN 閘道。 Location-Based 路由會根據使用者的位置來決定這種情況。

使用者位置可依下列方式分類：

- 使用者位於為 Location-Based 路由啟用的已知網路網站，而且他 (直接向內撥號) 號碼會在置於相同網路網站 (的 PSTN 閘道上終止例如，office) 。 撥出電話的路由會透過使用者所在之網站的語音路由原則進行。 對使用者的傳入 PSTN 呼叫會路由至位於與 PSTN 閘道位於相同網路網站的端點。

- 使用者位於與 PSTN 閘道所在之網路網站不同的已知網路網站。  (，亦即，使用者已前往另一部公司辦公室) 。 撥出電話的路由將使用使用者所在之網路網站的語音路由原則。 對使用者的內送 PSTN 通話不會路由到位於不同于 PSTN 閘道的端點，以避免 PSTN 收費繞過。

- 當使用者位於商務用 Skype Server 部署未知的網路網站時，撥出電話的路由會根據指派給使用者的語音原則，而不是系結至 Location-Based 路由限制的 PSTN 閘道。 傳入 PSTN 通話不會路由至位於未知網路網站的端點，以避免 PSTN 收費繞過。

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>在 PSTN 閘道的位置應用 Location-Based 路由

透過 PSTN 閘道路由傳送的來電和 PBXs 可能需要 Location-Based 路由限制，視這類系統的位置而定。 您可以在每個主幹基礎上啟用 Location-Based 路由的細微性。

當主幹上啟用時，Location-Based 路由會引進下列一組規則：

- 以每個主幹為基礎啟用 Location-Based 路由時，在該主幹上定義的規則只會套用到透過該主幹路由傳送的來電。

- 若要防止 PSTN 電話費旁路，其中的呼叫來自 PSTN 閘道所在的網路網站不同的網站，Location-Based 路由會引入網路網站與指定主幹的關聯。 這會定義允許通話路由傳送至指定主幹的網路網站。

您可以透過兩種方式，為 Location-Based 路由啟用主幹：

- 骨幹關是針對 egresses 對 PSTN 進行呼叫的 PSTN 閘道所定義。 以這種類型的主幹路由傳送的來電，只會路由傳送到與主幹位於相同網路網站內的端點。

- 主幹的定義是針對不會向 PSTN 和服務使用者提供靜態位置之舊版電話的轉送伺服器對等 (，例如 PBX 電話) 。 針對此特殊設定，所有由這種類型的主幹路由傳送的來電都會被視為與主幹產生來自相同的網路網站。 來自 PBX 使用者的呼叫，會與執行的 Location-Based 路由執行相同，就像是與主幹位於相同網路網站商務用 Skype 使用者一樣。 如果位於不同網路網站的兩個 PBX 系統是透過商務用 Skype Server 連線，則 Location-Based 路由將允許從一個網路網站的一個 pbx 端點路由傳送到另一個網路網站中的另一個 pbx 端點。 Location-Based 路由將不會封鎖此案例。 除了這種案例，與相同位置的商務用 Skype 使用者類似的情況下，連線至具有此設定之轉送伺服器對等的端點，也可以撥打或接聽其他轉送伺服器的來電，而不是將通話路由傳送至 PSTN (亦即，不論轉送伺服器對等所在的網站為何，連接至不同 PBX 的端點) 相關。 涉及 PSTN 端點的所有撥入通話、撥出電話、來電轉接及來電，都要視位置為基礎，僅使用定義為本機至此類轉送伺服器對等的 PSTN 閘道。

## <a name="scenarios-for-location-based-routing"></a>Location-Based 路由的案例

Location-Based 路由會在下列情況下路由呼叫時套用下列一般規則。

### <a name="outgoing-calls"></a>撥出電話

已啟用 Location-Based 路由之使用者的撥出電話路由會受到使用者端點之網路位置的影響。 下表說明 Location-Based 路由會如何影響撥出電話的路由，視來電者端點的位置而定。

**來電者向 PSTN 撥出電話**

|&nbsp;|已啟用 Location-Based 路由之網路網站中的使用者端點|位於未知網路網站或未啟用 Location-Based 路由的使用者端點|
|:-----|:-----|:-----|
|撥出電話的授權   |根據使用者的語音原則進行呼叫授權   |根據使用者的語音原則進行呼叫授權   |
|路由撥出通話   |根據網路網站的語音路由原則路由通話   |呼叫會根據使用者的語音原則進行路由傳送，且只有透過主幹未啟用 Location-Based 路由 (（如果有的話）)    |

### <a name="incoming-calls"></a>來電

對啟用 Location-Based 路由的使用者進行撥入電話的路由，取決於使用者端點的位置。 傳入通話的路由會以下列方式受到影響。 如果使用者對位於啟用網路功能的 Location-Based 路由的網站中的端點進行來電，而該端點位於與 PSTN 閘道相同的網路網站中，則會路由傳送通話。 如果使用者對位於啟用 Location-Based 路由的網路網站中的端點進行來電，而該端點位於與 PSTN 閘道不同的網路網站中，則不會路由呼叫。 當使用者沒有與撥入電話來源所在的 PSTN 閘道位於相同網路網站時，撥入電話會直接路由傳送至使用者的語音信箱，而且會將未接來電通知傳送給呼叫方。

已啟用 Location-Based 路由之使用者的「來電轉接」設定會繼續強制執行，不過轉接的來電會受到使用者 Location-Based 路由限制的制約。

下表說明 Location-Based 路由會如何影響傳入通話的路由，視受話者端點的位置而定。 PSTN 閘道的網路網站會為 Location-Based 路由啟用，而且 Location-Based 路由只允許將 PSTN 呼叫路由傳送至相同網路網站內的端點。

**被呼叫者從 PSTN 接收輸入呼叫**

|&nbsp;|被呼叫者的端點位於與 PSTN 閘道相同的網路網站中|受話者的端點與 PSTN 閘道不位於相同的網路網站|受話者的端點位於未知的網路網站中，或是未啟用 Location-Based 路由|
|:-----|:-----|:-----|:-----|
|傳入 PSTN 通話的路由   |撥入電話會路由傳送至受話者的端點   |傳入的呼叫未路由至受話者的端點   |傳入的呼叫未路由至受話者的端點   |

### <a name="call-transfers-and-call-forwarding"></a>通話轉移及來電轉接

當涉及 PSTN 端點時，Location-Based 路由會分析 calle 端點的位置，以及將來電轉接或轉接至 (（例如，傳輸/轉送目標) ）的端點。 Location-Based 路由決定是否應該根據這兩個端點的位置來轉移或轉寄通話。

下表說明使用 PSTN 端點的呼叫中商務用 Skype 使用者的案例，以及商務用 Skype 使用者將來電轉接至另一個商務用 Skype 使用者。 根據 transferee 端點的網路網站位置，Location-Based 路由會影響來電轉接或轉寄的路由。

**開始來電轉接或轉寄**

|使用者啟動通話轉接/轉寄|目標端點位於與使用者起始來電轉接或轉寄相同的網路網站|目標端點位於不同的網路網站中，以供使用者開始來電轉接或轉寄|目標端點位於未知的網路網站，或未啟用 Location-Based 路由的網路網站
|:-----|:-----|:-----|:-----|
|商務用 Skype 使用者   |允許來電轉接或轉接   |不允許來電轉接或轉接   |不允許來電轉接或轉接   |

例如：以 PSTN 端點通話的商務用 Skype 使用者會將來電轉接至相同網路網站中的另一個商務用 Skype 使用者。 在此情況下，允許通話轉接。

下表說明使用另一商務用 Skype 使用者的通話中商務用 Skype 使用者的案例，以及其中一位使用者將來電轉接至 PSTN 端點。 根據通話的轉接使用者位置，表格會詳細說明 Location-Based 路由會如何影響通話。

**來電轉接或轉接至 PSTN 端點**

|來電轉接/轉寄端點目標|在相同的網路網站中商務用 Skype 使用者|在不同網路網站中商務用 Skype 使用者|未啟用 Location-Based 路由的未知網路網站或網站中的一或兩個商務用 Skype 使用者|
|:-----|:-----|:-----|:-----|
|PSTN 端點   |轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接   |轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接   |轉接使用者的語音原則所允許的呼叫轉寄或轉接只能透過主幹未啟用 Location-Based 路由   |

例如：通話中的商務用 Skype 使用者與另一個商務用 Skype 使用者位於相同的網路網站，可將來電轉接至 PSTN 端點，並且允許通話轉接。

### <a name="simultaneous-ringing"></a>同時震鈴

當呼叫方啟用同時震鈴時，Location-Based 路由會分析呼叫方的位置，以及所叫方的端點，以判斷是否應路由傳送。

下表說明以同時震鈴方式設定的使用者，同時震鈴目標是在相同網路網站、不同網路網站或未知網路網站中的使用者。

****

|的傳入 PSTN 通話|與被呼叫方位於相同的網路網站|位於不同于被呼叫者的網路網站|位於未知的網路網站，或未啟用 Location-Based 路由|
|:-----|:-----|:-----|:-----|
|商務用 Skype 使用者   |允許同時振鈴   |不允許同時振鈴   |不允許同時振鈴   |

下表說明從商務用 Skype 使用者 (的呼叫，商務用 Skype 的來電者) 相同網路網站、不同的網路網站，或從未知的網路網站。 被呼叫方具有 PSTN 端點 (，cellphone) 設定為同時環的目標。 在此案例中，Location-Based 路由會判斷是否應將通話路由傳送至同時振鈴目標 (（亦即，被叫方的 cellphone) ）。

****

|同時環目標|與被呼叫方位於相同的網路網站|位於不同于被呼叫者的網路網站|位於未知的網路網站，或未啟用 Location-Based 路由|
|:-----|:-----|:-----|:-----|
|PSTN 端點   |透過來電者的網站語音路由原則允許同時振鈴   |透過來電者的網站語音路由原則允許同時振鈴   |允許透過來電者語音原則進行同時振鈴，以主幹未啟用 Location-Based 路由   |

### <a name="skype-for-business-cumulative-update-4"></a>商務用 Skype累計更新4

使用累計更新4時，您將會看到下列專案：

- Location-Based 會透過語音原則（包括商務用 Skype 行動用戶端）繼續啟用路由。

- 商務用 Skype 行動用戶端的通話行為會根據是否已啟用 Location-Based 路由和通訊用戶端而定。 這是設計為靜態的，但在某些情況下，您可能會將商務用 Skype 行動用戶端關聯至本機 PSTN 閘道，並允許某些行為（例如升級）。

- 不論您的作業系統為何，您的商務用 Skype 行動用戶端都應該具有相同的功能。

下表會逐步引導您完成一些後續累計更新4案例：

|Location-Based 路由使用者|其他聚會|動作|結果|
|:-----|:-----|:-----|:-----|
|商務用 Skype移動   |PSTN   |商務用 Skype行動裝置接收進來的 PSTN 通話。   |通話透過「透過運作」 (CvW) 傳送，而非 VoIP。   |
|商務用 Skype移動   |PSTN   |商務用 Skype行動裝置撥打外送 PSTN 電話。   |通話是透過 CvW 路由傳送，而不是 VoIP。   |
|商務用 Skype移動   |PSTN   |商務用 SkypeMobile 位於 PSTN 通話中。 商務用 Skype行動裝置接著將通話升級至其他使用者或連絡人。   |如果使用者或連絡人是從本機前往 PSTN 閘道腿，則通話會透過 VoIP 路由傳送。  <br/> 如果使用者或連絡人是從 PSTN 閘道腿遠端，則通話會透過 CvW 路由傳送。  <br/> 如果無法透過 PSTN 到達目標使用者，則呼叫會失敗。  <br/> 如果目標連絡人是會議自動語音應答 (CAA) ，則會封鎖通話。   |
|商務用 Skype移動   |商務用 Skype 用戶端或同盟使用者   |商務用 Skype 行動對另一部商務用 Skype 用戶端或同盟使用者發起語音通話。   |呼叫是透過 VoIP 完成。   |
|商務用 Skype移動   |商務用 Skype 用戶端或同盟使用者   | 商務用 Skype 用戶端或同盟使用者對商務用 Skype 行動 Location-Based 路由使用者發起語音電話。  |呼叫是透過 VoIP 完成。   |
|商務用 Skype移動   |商務用 Skype 用戶端或同盟使用者   |商務用 Skype 用戶端或同盟使用者在 VoIP 呼叫商務用 Skype 行動使用者。 任何一方會升級至其他商務用 Skype 或同盟使用者。   |呼叫是透過 VoIP 完成。   |
|商務用 Skype移動   |同盟使用者   |同盟使用者對商務用 Skype 行動裝置 Location-Based 路由使用者的語音電話;商務用 Skype 行動裝置會升級至 PSTN 使用者。   |封鎖通話。   |
|商務用 Skype移動   |同盟使用者   |同盟使用者在商務用 Skype 行動 Location-Based 路由使用者的 VoIP 呼叫上;每一方都升級至 CAA 連絡人。   |會封鎖已呈報的通話，並顯示適當的錯誤訊息。   |
|商務用 Skype移動   |同盟使用者   |同盟使用者 VoIP 呼叫商務用 Skype 行動 Location-Based 路由使用者，且同盟使用者升級至 PSTN 使用者。   |根據同盟使用者的 Location-Based 路由，將允許或禁止呈報。 商務用 Skype Mobile Location-Based 路由使用者的應用程式不會採取任何動作。   |

### <a name="delegation"></a>委派

商務用 Skype 的委派功能會受到以下列方式 Location-Based 路由的影響：

- 啟用 Location-Based 路由的代理人代表管理員撥打電話時，代理人的語音原則會用來授權通話，並使用代理人的網站語音路由原則路由傳送通話

- 針對主管的內送 PSTN 電話，可依照通話轉接及轉接及同時響鈴的主題所述，套用適用于來電轉接或同時振鈴的相同規則。

- 當代理人將 PSTN 端點設定為同時振鈴目標時，如果是對管理員的來電，就會使用與傳入主幹相關聯之網站的語音路由原則，將通話路由傳送至代理人的 PSTN 端點。

- 為了進行委派，建議管理員和其相關聯的代理人通常位於相同的網路網站。

## <a name="other-planning-considerations"></a>其他規劃考慮

規劃 Location-Based 路由時，您應該考慮對下列案例的影響。

### <a name="disaster-recovery"></a>嚴重損壞修復

在從主要集區容錯移轉至備份組區，以及將一般作業還原至主要集區時，Location-Based 路由會在發生災難和復原程式期間的任何時間保持強制執行。

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

設定 Location-Based 路由會影響部署 Survivable 分支裝置相關聯之閘道的規劃。 與您的 SBA 關聯的閘道，必須位於與 Survivable Branch 裝置相同的網路網站中;否則，位於 Survivable Branch 裝置的使用者將不會在設定 Location-Based 路由的情況下，撥打撥出電話。 當您的 Survivable 分支裝置與中央網站之間的 WAN 連線已停機時，Location-Based 路由限制仍會執行。

## <a name="client-and-server-support-for-location-based-routing"></a>Location-Based 路由的用戶端和伺服器支援

Location-Based 路由會由商務用 Skype Server 強制執行。 商務用 Skype Server 可以識別使用者從公司網路內部連線的網站。 因為遠端使用者位於公司網路外部，所以其位置被視為未知。

### <a name="server-support"></a>伺服器支援

Location-Based 路由需要在指定拓撲中的所有前端集區和 Standard Edition 伺服器上部署商務用 Skype Server 或 Lync Server 2013 CU1。 若未安裝這些版本的伺服器，則無法完全強制執行位置基礎路由限制。

下表列出 Location-Based 路由支援的伺服器角色與版本組合。

****

|集區版本|轉送伺服器版本|支援|
|:-----|:-----|:-----|
|商務用 Skype Server 或 Lync Server 2013 月2013累計更新   |商務用 Skype Server 或 Lync Server 2013 月2013累計更新   |是   |
|商務用 Skype Server 或 Lync Server 2013 月2013累計更新   |Lync Server 2013   |否   |
|商務用 Skype Server 或 Lync Server 2013 月2013累計更新   |Lync Server 2010   |否   |
|商務用 Skype Server 或 Lync Server 2013 月2013累計更新   |Office Communications Server 2007 R2   |否   |
|Lync Server 2013   |任何   |否   |
|Lync Server 2010   |任何   |否   |
|Office Communications Server 2007 R2   |任何   |否   |

### <a name="client-support"></a>用戶端支援

下表識別 Location-Based 路由支援的用戶端。

****

|用戶端類型|支援|詳細資料|
|:-----|:-----|:-----|
|商務用 Skype   |是   ||
|Lync 2013   |是   ||
|Lync 2010   |是   ||
|Office Communicator 2007 R2   |否   ||
|Lync Phone Edition   |是   ||
|Lync 語音應答   |是   ||
|Windows 8 的 Lync   |否   ||
|Lync Mobile 2013   |否   |如果已啟用 Location-Based 路由的使用者使用，則必須停用 Lync Mobile 2013 用戶端的 VoIP。   |
|Lync Mobile 2010   |是   ||

> [!NOTE]
> 若要停用商務用 Skype 用戶端的 VoIP，請為所有啟用 Location-Based 路由的使用者指派設定、IP Audio/Video、停用行動原則。 如需行動原則的詳細資訊，請參閱 [New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy)。

## <a name="capabilities-not-supported-by-location-based-routing"></a>Location-Based 路由不支援的功能

Location-Based 路由不適用於下列類型的互動。 當商務用 Skype 端點與使用這些功能的 PSTN 端點互動時，不會強制執行 Location-Based 路由。

- PSTN 電話撥入式會議

- 透過回應群組的呼入和呼出 PSTN 通話

- 透過通話駐留通話駐留或檢索 PSTN 通話

- 對宣告服務的打入 PSTN 通話

- 透過群組呼叫收取的打入的 PSTN 通話

若要對下列清單中的互動類型執行 Location-Based 路由規則，您必須為會議啟用 Location-Based 路由：

- 來自會議的 PSTN 撥出

- 從對等音訊交談上報至涉及 PSTN 端點的會議

- 涉及 PSTN 端點的諮詢轉移

若要啟用 Location-Based 的會議路由，請參閱 [會議的位置基礎路由](/previous-versions/office/lync-server-2013/lync-server-2013-location-based-routing-for-conferencing)。