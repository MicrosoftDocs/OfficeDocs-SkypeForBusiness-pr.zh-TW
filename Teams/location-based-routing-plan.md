---
title: 規劃直接路由的依位置路由
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 瞭解如何規劃直接路由Location-Based路由。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 887fd7bf955f5caa76a0dde3b42b96b912f23355
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829607"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>規劃直接路由的依位置路由

## <a name="overview-of-location-based-routing"></a>路由Location-Based概觀

在一些國家和地區，忽略公用交換電話網絡 (PSTN) 降低長途電話費用是違法的行為。 本文將說明如何使用 Location-Based路由，根據使用者的地理位置Microsoft Teams付費旁路。 本文僅適用于直接電話系統路由。

在這裡，您將取得路由Location-Based概觀，以及可協助您規劃的指南。 當您準備好要申請並啟用路由Location-Based，請參閱：

- [部署路由Location-Based設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)

> [!NOTE]
> Location-Based高或 DoD 部署中Microsoft 365 政府社群雲端 (GCC) 路由。

Location-Based路由是一項功能，可讓您根據原則以及使用者的地理位置，在輸入或外發 PSTN 通話時限制免付費。 Location-Based路由的目的是提供一種機制，以防止免付費路。 它不應該用來做為根據使用者位置動態路由 PSTN 通話的機制，否則可能會導致非預期的結果。

當使用者Teams路由時Location-Based，則適用下列條件：

- 若要撥打外發 PSTN 通話，下列其中一項必須為 True：
    - 使用者的端點位於已啟用 Location-Based 路由和呼叫輸出的網路網站中，此網路網站會透過已啟用 Location-Based 路由的對應閘道Location-Based出口。 
    - 使用者的端點位於未針對 Location-Based 路由啟用的網路網站中，並且透過未啟用 Location-Based 路由的閘道出口。

    在任何其他情況下都不允許外線通話。

- 若要接收傳入 PSTN 通話，使用者的接聽端點必須位於呼叫透過啟用 [路由Location-Based的同一個網路網站。 在任何其他情況下 ，例如使用者漫遊時，不允許通話，而且會路由至使用者的呼叫轉 (語音信箱) 。
- 若要將 PSTN Teams另一位使用者，目標使用者的端點必須位於啟動傳輸的使用者所在的同一個網路網站中。 其他任何案例都不允許傳輸。 
- 若要將另Teams使用者轉接到 PSTN，呼叫必須透過與初始來電者位於相同網路網站的 Location-Based 路由啟用閘道進行轉接。 其他任何案例都不允許傳輸。

Location-Based路由使用相同的網路區域、網站和子網定義，商務用 Skype Server使用。 當位置限制免付費時，系統管理員會將該位置的每個 IP 子網和每個 PSTN 閘道關聯至網路網站。 使用者的位置是由 IP 子網決定，Teams PSTN 通話時，使用者與端點已連結。 使用者可能會有多個位於Teams用戶端，在這種情況下，Location-Based路由會依據其端點位置個別強制執行每個用戶端的路由。 

若要熟悉本文中使用的部分網路術語，請參閱本文中的雲端語音功能網路[Teams。](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>將 Location-Based路由

您必須將路由Location-Based使用者、網路網站和 PSTN 閘道。  

### <a name="apply-location-based-routing-at-the-user-location"></a>在Location-Based位置使用路由

如先前所述，Location-Based路由僅適用于設定為直接路由的使用者。 Location-Based路由不適用於已設定通話方案的使用者。 如果使用者受到免付費限制Location-Based，則必須啟用 [路由傳送方式>，此限制會控制他們可以撥打和接聽 PSTN 通話的條件，以及可以使用的 PSTN 閘道。 啟用 Location-Based 路由的使用者位於已啟用 Location-Based 路由的網站時，使用者必須透過已連接到網站的 Location-Based 路由啟用閘道撥打電話。 

Location-Based路由會依據使用者端點的 IP 位址決定使用者的目前位置，Teams並適用規則。 啟用路由的使用者位置Location-Based下列方式分類： 
- **使用者位於指派其 DID 的 PSTN Location-Based啟用路由的網站。**<br>在此情境中，使用者位於已啟用 Location-Based 路由的已知網路網站中，而使用者的 [直接向內撥號 (DID) 號碼會終止于同一個網路網站的 PSTN 閘道上。 例如，使用者位於他們的辦公室。 
- **使用者位於另一個啟用路由的網站Location-Based與指派其 DID 的 PSTN 閘道沒有關聯。**<br>在此情境中，使用者位於已啟用 Location-Based 路由的已知網路網站中，而且該網站不會與指派使用者的 DID 號碼的 PSTN 閘道相關聯。 例如，使用者會前往另一個辦公室。  
- **使用者所在的內部網站並未啟用路由Location-Based路由。** <br>在此情境中，使用者位於未針對路由啟用的已知內部網路Location-Based網站。 
- **使用者位於未知的網站。** 
    - 使用者位於未定義為網路網站的內部網路內。 
    - 使用者位於內部網路外部。 例如，使用者在家中或咖啡店的網際網路上。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在Location-Based上使用路由 
必須啟用網路網站，Location-Based路由，協助決定在漫遊時要路由Location-Based路由啟用的使用者。 如果已啟用 Location-Based 路由的使用者漫遊至已啟用 Location-Based 路由的網站，則只有已啟用該網站 Location-Based 路由的 PSTN 閘道可用於外發通話。 如果已啟用 Location-Based 路由的使用者漫遊至未啟用 Location-Based 路由的網站，則任何未針對 Location-Based 路由啟用的閘道都可以用於外發通話。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN Location-Based上申請路由 

閘道會與網站相關聯，以決定啟用 [路由Location-Based使用者撥打或接收 PSTN 通話時的位置。 必須針對 Location-Based啟用閘道，以確保它受免付費限制限制，且無法由未啟用 Location-Based 的使用者使用。 同一個閘道可能與多個網站相關聯，而且可以將它配置為啟用 Location-Based 路由，或視網站Location-Based路由啟用。

## <a name="scenarios-for-location-based-routing"></a>位置基礎路由案例

本節說明使用 Location-Based 路由限制付費旁路的不同案例，並比較未啟用 Location-Based 路由的使用者與已啟用 Location-Based 路由的使用者的通話路由方式。

- [Teams將外線通話撥打到 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams收到 PSTN 的來電](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams轉接或轉接呼叫給另一位Teams使用者](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams轉接或轉接呼叫至 PSTN 端點](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時響鈴](#simultaneous-ringing)
- [委派](#delegation)

下圖顯示每個案例的 Location-Based路由啟用的限制。 已啟用路由的使用者、網路網站和閘道Location-Based其周圍有一個邊界。 使用圖表做為指南，説明您瞭解路由Location-Based路由如何運作。  

![顯示路由Location-Based圖表。](media/lbr-direct-routing.png "顯示路由Location-Based圖表")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams將外線通話撥打到 PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用 Location-Based路由

未啟用 Location-Based 路由的使用者，可以在未透過指派的語音路由策略進行 Location-Based 路由的任何網站上，使用任何閘道撥打外接電話。 不過，如果閘道已啟用 Location-Based路由，即使已指派給語音路由策略，使用者也無法透過閘道撥打外接電話。 如果使用者漫遊至已啟用 Location-Based 路由的網站，則他們只能透過未針對 Location-Based 路由啟用的一般路由閘道Location-Based通話。
 
#### <a name="user-enabled-for-location-based-routing"></a>使用者已啟用 Location-Based路由
相較之下，已啟用路由Location-Based使用者的外發通話路由會受到使用者端點的網路位置影響。 下表顯示路由Location-Based路由如何影響 User1 的外發通話路由，視使用者 1 的位置而不同。 

|User1 端點位置  |User1 的外發通話路由  |
|---------|---------|
|已指派使用者的 DID 的同一個網站，Location-Based網站 1 (網站)       |根據使用者的語音路由Location-Based， (GW1) 閘道路由的通話         |
|與指派使用者 DID 的網站不同，網站已啟用 Location-Based路由 (網站)     |根據使用者的語音路由策略，Location-Based路由 (GW2) 漫遊網站 GW2 的閘道路由通話        |
|與指派使用者 DID 的網站不同，網站未啟用 Location-Based網站 (網站)   |根據使用者的語音路由策略，未針對 Location-Based 路由 (GW3) 啟用 Location-Based 路由的閘道路由通話       |
|位置 4 (未知的內部)     |  不允許 PSTN 通話       |
|位置 5 (未知的外部)     | 不允許 PSTN 通話        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams從 PSTN 接收來電

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用 Location-Based路由

未針對 Location-Based 路由啟用的使用者，可以從未為其指派 DID 號碼輸入的 Location-Based 路由啟用的閘道接收輸入通話。 如果使用者漫遊到未啟用 [路由Location-Based的網站，他們仍然可以透過一般 PSTN 閘道接聽來電。
  
#### <a name="user-enabled-for-location-based-routing"></a>使用者已啟用 Location-Based路由

相較之下，啟用 Location-Based路由的使用者只能從 PSTN 閘道接收其 DID 位於同一個網站時指派的來電。 下表顯示當使用者 1 移至不同的網路位置時，使用者1 如何接收來電。 如果通話未路由至使用者的端點，則呼叫會傳送到使用者的呼叫轉轉設定 ，如果設定已設定。 一般來說，這是語音信箱。  

|User1 端點位置  |將輸入通話路由至 User1  |
|---------|---------|
|與指派使用者 DID 的網站相同，網站會啟用 Location-Based網站 1 (路由)    | 在 Site1 中路由至 User1 端點的通話        |
|與指派使用者 DID 的網站不同，網站已啟用 Location-Based路由 (網站)     | 未路由至 Site2 中的端點的通話        |
|與指派使用者 DID 的網站不同，網站未啟用 Location-Based網站 (網站)     | 未路由至 Site3 端點的通話        |
|位置 4 (未知的內部)    | 未路由至位置 4 端點的通話        |
|位置 5 (未知的外部)      | 未路由至位置 5 中的端點的通話        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams轉接或轉接呼叫給另一位Teams使用者

當涉及 PSTN 端點時，Location-Based路由會分析一或兩個使用者是否已啟用 Location-Based 路由，並決定是否應該根據兩個端點的位置轉移或轉送通話。 
 
來電轉接要求啟動使用者接聽來電，而來電轉接則不需要接聽初始通話。 這表示即使 User1 不在接收輸入通話的位置 (也可以轉接通話 (請參閱 Teams 使用者從[PSTN](#teams-user-receives-an-inbound-call-from-the-pstn)區段) 接收輸入通話的資料表，如果使用者無法接收輸入通話，就無法轉接通話。 

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用 Location-Based路由

未啟用 [路由Location-Based可以將 PSTN 通話轉接或轉接給未啟用 [路由Location-Based使用者。 使用者通常無法將 PSTN 通話轉接或轉接給已啟用 Location-Based 路由的使用者，因為啟用 Location-Based 路由的使用者一般只能在 Location-Based 路由啟用的閘道進行 PSTN 通話。 例外是啟用路由Location-Based使用者漫遊到未啟用路由Location-Based網站。 在此情境中，允許轉接的通話。  

同樣地，未啟用 [路由Location-Based使用者只能收到另一個未啟用 [路由Location-Based轉接或轉Location-Based PSTN 通話。 

#### <a name="user-enabled-for-location-based-routing"></a>使用者已啟用 Location-Based路由

一般而言，只有在目標使用者已啟用 Location-Based 路由且位於同一個網站時，才能從已啟用 Location-Based 路由的閘道轉移和轉送傳入 PSTN 通話。 否則，不允許轉接和轉接通話。 

下表顯示是否允許來電轉接和來電轉接，視目標使用者的位置而不同。 在此資料表中，位於 Site1 中的 User1 會啟動傳輸或轉Teams移轉給其他已啟用 Location-Based 路由，以及位於不同位置的使用者。  

|目標使用者端點位置|User1 會啟動來電轉接 |User1 會啟動呼叫前轉|
|---------|---------|---------|
|與 User2 (啟動) |允許|允許|
|不同的網路網站，使用者 3 Location-Based路由 (網站) |不允許|不允許|
|不同的網路網站，未針對使用者 4 Location-Based路由 (啟用) |不允許|不允許|
|User5 (內部網路) | 不允許|不允許|
|User6 (未知) | 不允許|不允許|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams轉接或轉接呼叫至 PSTN 端點

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用 Location-Based路由

- 允許將 PSTN 通話轉接至另一個 PSTN 號碼。 
- 將傳入 VOIP 通話轉接及轉接到 PSTN 時，必須遵守來電者的付費旁路限制。 
    - 如果來電者未針對 Location-Based啟用，可以將來電者轉接到任何未啟用 [路由Location-Based閘道。
    - 如果來電者已啟用路由Location-Based，他們只能轉移到位於相同網路Location-Based路由啟用閘道。 

#### <a name="user-enabled-for-location-based-routing"></a>使用者已啟用 Location-Based路由

- 將 PSTN 通話的內送轉接和轉Location-Based PSTN 號碼必須路由到與來電抵達的啟用路由的閘道相同。 
- 將傳入 VOIP 通話轉接及轉接到 PSTN 時，必須同時遵守來電者與稱為使用者的付費旁路限制。 
    - 如果來電者未針對 Location-Based啟用，可以將來電者轉接到任何未啟用 [路由Location-Based閘道。
    - 如果來電者已啟用路由Location-Based，則只能將來電者移轉到位於相同網路Location-Based路由啟用閘道。
 
下表顯示 [Location-Based路由如何影響將 VoIP 通話從網站 1 的 User1 路由傳送給在不同位置將來電轉接或轉接到 PSTN 端點的使用者。  

|使用者啟動來電轉接或轉接  |移轉至 PSTN  |轉往 PSTN  |
|---------|---------|---------|
|相同的網路網站，使用者 2 Location-Based路由 (網站)    |根據 User2 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由來電轉接         |根據 User2 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由呼叫         |
|不同的網路網站，使用者 3 Location-Based路由 (網站)     |根據 User3 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由來電轉接         |根據 User3 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由呼叫。         |
|不同的網路網站，未針對使用者 4 Location-Based路由 (啟用)     |根據 User4 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由來電轉接         |根據 User4 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由呼叫。         |
|User5 (內部網路)      |根據 User5 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由來電轉接         |根據 User5 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由呼叫。         |
|User6 (未知)    |根據 User6 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由來電轉接        |根據 User6 的語音路由Location-Based，只能透過網站 1 的啟用路由的閘道1 路由呼叫。         |

### <a name="simultaneous-ringing"></a>同時響鈴

當已啟用 Location-Based 路由的使用者收到來電並啟用同時響鈴時，Location-Based 路由會分析通話方的位置和被叫方端點，以決定是否應該路由通話。 同時撥打會遵循與Location-Based和轉接相同的規則。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>另一位使用者同時Teams鈴

下表顯示 [Location-Based路由是否允許同時撥打給使用者 1 的輸入 PSTN 通話給不同的使用者。

|目標使用者端點位置|同時響鈴  |
|---------|---------|
|與 User2 (啟動)    |允許         |
|針對使用者 3 的路由Location-Based啟用 (網路)    |不允許         |
|未針對使用者 4 Location-Based路由 (啟用漫遊)    |不允許        |
|User5 (內部網路)     | 不允許        |
|User6 (未知)     |不允許        |
|目標使用者是 PSTN 號碼    |根據 User1 的語音路由Location-Based，只能在 Site1 透過啟用路由的閘道1 路由通話      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同時響鈴到 PSTN 端點

下表顯示Location-Based使用者 1 的傳入 VOIP 通話路由行為，以及同時撥打設定為 PSTN 號碼的不同位置的使用者。 

|稱為使用者端點位置  |同時響鈴目標為 PSTN 端點 |
|---------|---------|
|相同的網路網站，使用者 2 Location-Based路由 (網站)     |根據 User2 的語音路由Location-Based，只能透過網站 1 的路由閘道1 路由通話       |
|針對使用者 3 Location-Based路由 (啟用)     |根據 User3 的語音路由Location-Based，只能透過網站 1 的路由閘道1 路由通話        |
|不同的網路網站未針對使用者 4 Location-Based路由 (啟用)     |根據 User4 的語音路由Location-Based，只能透過網站 1 的路由閘道1 路由通話         |
|User5 (內部網路)     |根據 User5 的語音路由Location-Based，只能透過網站 1 的路由閘道1 路由通話         |
|User6 (外部網路)    |根據 User6 的語音路由Location-Based，只能透過網站 1 的路由閘道1 路由通話         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>透過語音應用程式撥打 (自動語音留言或通話佇列) 

允許從已啟用路由Location-Based閘道的傳入 PSTN 通話，以連接到自動電話機或通話佇列。 啟用 [Location-Based路由的使用者，只有在這些應用程式位於傳入 PSTN 通話來源所在的同一個網站時，才能接收來自這些應用程式的來電轉移。 
 
語音應用程式傳輸允許來電轉接和同時撥打給使用者和 PSTN。 完成目標通話時，受先前列出的Location-Based規則所規範。  
 
也允許轉往語音信箱。  

### <a name="delegation"></a>委派

使用者Teams使用者可以選擇可以代表他們撥打和接聽電話的代理人。 郵件中的委派功能Teams受 Location-Based路由影響，如下所示： 
- 對於來自具有路由Location-Based代理人的外發通話，則適用相同的規則。 通話路由是根據代理人的通話授權策略、語音路由策略和位置。 若要詳細資訊，請參閱Teams[將外線通話撥打到 PSTN。](#teams-user-places-an-outbound-call-to-the-pstn) 
- 針對傳入 PSTN 呼叫委派者，Location-Based呼叫轉譯或同時撥打給其他使用者的相同路由規則也適用于代理人。 詳細資訊，請參閱Teams轉接或轉接呼叫給另一位[Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)使用者、Teams使用者轉接或轉接呼叫至[PSTN 端點](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)，以及同時[撥打。](#simultaneous-ringing) 當代理人將 PSTN 端點設定為同時響鈴目標時，代理人的語音路由策略會用來將通話路由至 PSTN。 
- 對於委派，建議您將委派者和相關代理人位於同一個網路網站。 

## <a name="other-planning-considerations"></a>其他規劃考慮

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>內部部署和路由Location-Based變更

不再使用網路網站語音路由策略。 相反地，我們使用使用者的語音路由策略。 這表示，若要允許使用者漫遊到其他網站，語音路由策略必須包含漫遊網站的閘道。 

### <a name="technical-considerations-for-location-based-routing"></a>位置基礎路由的技術考量

支援 IPv4 和 IPv6 子網，不過，在檢查相符專案時，IPv6 會優先使用。

### <a name="client-support-for-location-based-routing"></a>用戶端支援 Location-Based路由

支援Teams用戶端：
- Teams桌面用戶端 (Windows Mac) 
- Teams iOS 和 Android (行動用戶端) 
- TeamsIP 電話

不支援Teams用戶端商務用 Skype用戶端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>未受位置基礎路由支援的功能

Location-Based路由不適用於下列互動類型。 Location-Based下列情況下，當端點與 PSTN 端點Teams時，不會強制執行路由： 
- 透過 [呼叫停駐點撥打或取回 PSTN 通話 
- 內部部署使用者商務用 Skype或線上商務用 Skype使用者Teams使用者  

### <a name="location-based-routing-for-conferencing"></a>Location-Based會議路由

Location-Based PSTN 通話中啟用路由功能的使用者無法與其他使用者或 PSTN 號碼開始會議。 允許連接到自動電話機或通話佇列。 如果使用者有會議授權，使用者必須啟動與相關使用者的會議，並透過會議橋接器撥打 PSTN 以開始電話會議。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>路由的媒體Location-Based要求

如果您要在印度部署 Location-Based路由，則還必須設定媒體旁路。 若要深入瞭解，請參閱[使用](direct-routing-plan-media-bypass.md)直接路由和直接路由的當地媒體[優化規劃媒體旁路。](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>在 VoIP (直接語音) 

VoIP (IP) 不得與印度的任何電話設備一起部署。

## <a name="next-steps"></a>後續步驟

請前往 [設定網路設定Location-Based路由](location-based-routing-configure-network-settings.md)。

## <a name="related-topics"></a>相關主題

- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [雲端語音功能的網路設定Teams](cloud-voice-network-settings.md)
