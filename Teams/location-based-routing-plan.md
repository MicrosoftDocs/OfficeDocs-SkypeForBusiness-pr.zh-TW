---
title: 規劃直接路由的依位置路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 瞭解如何規劃直接路由的位置路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f72360f4462a64e357d58489aa70203bf10c532
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326640"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>規劃直接路由的依位置路由

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

## <a name="overview-of-location-based-routing"></a>以位置為基礎的路由概覽

在某些國家和地區，略過公開交換式電話網絡（PSTN）供應商以減少長途通話成本是不合法的。 本文說明如何使用以位置為基礎的路由，根據其地理位置限制 Microsoft 團隊使用者的免付費略過。 本文只適用于電話系統直接路由。

您可以在這裡瞭解位置路由與指導方針，以協助您規劃。 當您準備好要套用並啟用以位置為基礎的路由時，請參閱：
- [部署以位置為基礎的路由的網路設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)

位置式路由是一項功能，可讓您根據原則與使用者在輸入或輸出 PSTN 通話時的地理位置來限制付費旁路。 

針對位置路由啟用團隊使用者時，下列專案適用：
- 若要進行出站 PSTN 通話，下列其中一項必須成立：
    - 使用者的端點位於已啟用位置路由的網路網站，並可透過針對位置式路由啟用的對應閘道來呼叫出口。 
    - 使用者的端點位於不支援位置路由的網路網站，並透過未啟用位置路由的閘道來呼叫出局。

    任何其他案例中都不允許出站通話。

- 若要接收入站 PSTN 呼叫，使用者的應答端點必須位於您的網路網站中，且呼叫 ingresses 是透過支援位置路由的閘道。 在任何其他情況下（例如，如果使用者是漫遊），不允許通話，而且會傳送到使用者的來電轉接設定（通常是語音信箱）。
- 若要將 PSTN 來電轉接給其他團隊使用者，目標使用者的端點必須位於與啟動傳輸的使用者相同的網路網站中。 任何其他案例中都不允許傳輸。 
- 若要將其他團隊使用者轉接至 PSTN，必須在與初始呼叫者相同的網路網站上，以與位置路由啟用路由的閘道來傳送通話。 任何其他案例中都不允許傳輸。

以位置為基礎的路由：使用商務用 Skype 伺服器所使用的相同網路區域、網站和子網定義。 當您針對某個位置限制付費旁路時，系統管理員會將該位置的每個 IP 子網和每個 PSTN 閘道與一個網路網站進行關聯。 使用者的位置是由使用者的小組端點在 PSTN 通話時所連接到的 IP 子網上所決定。 使用者可能會有多個小組用戶端位於不同的網站，在這種情況下，以位置為基礎的路由會根據其端點的位置，分別強制執行每個用戶端的路由。 

若要熟悉本文中使用的一些網路術語，請參閱[小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)。

## <a name="apply-location-based-routing"></a>套用以位置為基礎的路由

您必須將基於位置的路由套用至使用者、網路網站和 PSTN 閘道。  

### <a name="apply-location-based-routing-at-the-user-location"></a>在使用者位置套用以位置為基礎的路由

如前所述，以位置為基礎的路由只適用于設定直接傳送的使用者。 以位置為基礎的路由不適用於設定通話方案的使用者。 如果使用者位於 [免付費旁路限制] 底下，則必須啟用使用者的位置路由，這會控制他們可以撥打和接聽 PSTN 通話的條件，以及可使用的 PSTN 閘道。 在已啟用位置路由的使用者位於已啟用位置路由的網站上時，使用者必須透過連線到該網站的以位置為基礎的路由閘道進行呼叫。 

根據使用者的小組端點的 IP 位址來判斷使用者的目前位置，並據此套用規則，以位置為基礎的路由運作。 啟用位置路由的使用者位置可以使用下列方式加以分類： 
- **使用者位於與已指派其所在之 PSTN 閘道的同一個以位置為基礎的路由啟用的網站上。**<br>在這種情況下，使用者位於已啟用位置路由的已知網路網站中，而使用者的直接向內撥入（結束）號碼會在同一網路網站的 PSTN 閘道上終止。 例如，使用者是他們的辦公室。 
- **使用者位於其他以位置為基礎的路由啟用的網站，沒有與 PSTN 閘道關聯，而該網站是指派給他們的。**<br>在這種情況下，使用者位於已啟用位置路由的已知網路網站，而該網站未與使用者的已指派號碼的 PSTN 閘道相關聯。 例如，使用者移至另一個辦公室。  
- **使用者位於未啟用位置路由的內部網站上。** <br>在這種情況下，使用者位於未啟用位置路由的已知內部網路網站中。 
- **使用者位於未知的網站上。** 
    - 使用者位於未定義為網路網站的內部網路中。 
    - 使用者位於內部網路以外。 例如，使用者是在家中或咖啡店中的網際網路。 

### <a name="apply-location-based-routing-at-the-network-site"></a>在網路網站上套用以位置為基礎的路由 
網路網站必須針對位置路由啟用，以協助您決定在漫遊時，哪些閘道要路由以位置為基礎的路由功能使用者。 如果已啟用以位置路由的使用者漫遊到已啟用位置式路由的網站，則只有在該網站上啟用位置路由的 PSTN 閘道才能用於撥出通話。 如果已啟用位置路由的使用者漫遊至未啟用位置式路由的網站，則任何未啟用位置路由的閘道都可以用來進行撥出通話。  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>在 PSTN 閘道套用以位置為基礎的路由 

閘道會與網站建立關聯，以判斷啟用位置路由的使用者在撥打或接聽 PSTN 通話時，可以找到哪個位置。 閘道必須針對位置路由啟用，以確保其符合 [付費旁路] 限制，且無法供沒有啟用位置路由的使用者使用。 同一個閘道可能會與多個網站建立關聯，而且您可以將它設定為啟用位置路由，或不啟用以位置路由（視網站而定）。

## <a name="scenarios-for-location-based-routing"></a>位置基礎路由案例

本節說明使用以位置為基礎的路由來限制免付費旁路的不同案例，並比較針對沒有啟用位置式路由的使用者進行位置式路由的使用者的呼叫路由方式。

- [團隊使用者將出站呼叫放入 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)
- [團隊使用者從 PSTN 接收入站通話](#teams-user-receives-an-inbound-call-from-the-pstn)
- [團隊使用者將來電轉移或轉寄給其他團隊使用者](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [小組使用者將來電轉接或轉寄給 PSTN 端點](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [同時響鈴](#simultaneous-ringing)
- [委派](#delegation)

下圖顯示在每個案例中，以位置為基礎的路由所啟用的限制。 針對位置式路由所啟用的使用者、網路網站和閘道，在其周圍有一個框線。 使用圖表做為指南，協助您瞭解在各個案例中，以位置為基礎的路由運作方式。  

![圖表顯示以位置為基礎的路由案例](media/lbr-direct-routing.png "圖表顯示以位置為基礎的路由案例")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>團隊使用者將出站呼叫放入 PSTN

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用位置路由

未啟用位置路由的使用者可以使用任何不是透過其指派的語音路由策略來進行位置路由的網站上的閘道，來撥出通話。 不過，如果已啟用閘道進行位置式路由，即使指派給其語音路由策略，使用者還是無法透過閘道撥出通話。 如果使用者漫遊到已啟用位置式路由的網站，他們只能透過其正常路由閘道進行呼叫，而不會啟用位置路由。
 
#### <a name="user-enabled-for-location-based-routing"></a>已啟用使用者的位置路由
相比之下，為啟用位置路由的使用者傳送撥出通話的路由會受到使用者端點的網路位置影響。 下表顯示視 User1 位置而定的位置路由如何影響對多個 User1 撥出通話的路由。 

|User1 端點位置  |針對 User1 的出站通話進行路由  |
|---------|---------|
|已指派使用者所用的相同網站，已針對位置路由（Site1）啟用網站      |根據使用者的語音路由策略，在 Site1 上使用以位置路由（GW1）為基礎的閘道路由的通話         |
|已指派使用者的位置以外的其他網站，已針對位置路由（Site2）啟用網站    |根據使用者的語音路由策略，在漫遊 Site2 中，透過支援位置路由（GW2）的呼叫進行路由        |
|指派使用者的位置以外的網站，網站未啟用位置路由（Site3）  |在未啟用以位置路由（GW3）為基礎的位置路由的閘道，且根據使用者的語音路由策略，進行通話       |
|未知的內部網路（Location4）    |  不允許 PSTN 通話       |
|未知外部網路（Location5）    | 不允許 PSTN 通話        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>團隊使用者從 PSTN 接收入站通話

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用位置路由

未啟用位置路由的使用者，可能會收到來自閘道的撥入通話，而該閘道並未啟用來自其指派的 ingresses 的位置路由。 如果使用者漫遊至未啟用位置式路由的網站，他們仍可透過其正常 PSTN 閘道接收來電。
  
#### <a name="user-enabled-for-location-based-routing"></a>已啟用使用者的位置路由

比較而言，對於以位置為基礎的路由啟用的使用者，只會在它們位於相同的網站時，將其已指派給它的 PSTN 閘道接收來電。 下表顯示當 User1 移至不同網路位置時，User1 如何接收撥入通話。 如果通話不是傳送給使用者的端點，則會移至使用者的來電轉接設定（如果設定已設定）。 通常，這是語音信箱。  

|User1 端點位置  |將入站呼叫路由至 User1  |
|---------|---------|
|使用者所指派的位置相同的網站，針對位置路由（Site1）啟用網站   | 在 Site1 中傳送給 User1's 端點的通話        |
|已指派使用者的位置以外的其他網站，已針對位置路由（Site2）啟用網站    | 通話未路由至 Site2 中的端點        |
|指派使用者的位置以外的網站，網站未啟用位置路由（Site3）    | 通話未路由至 Site3 中的端點        |
|未知的內部網路（Location4）   | 通話未路由至 Location4 中的端點        |
|未知外部網路（Location5）     | 通話未路由至 Location5 中的端點        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>團隊使用者將來電轉移或轉寄給其他團隊使用者

在涉及 PSTN 端點時，以位置為基礎的路由會分析是否有一或兩個使用者啟用位置路由，並判斷是否應該根據兩個端點的位置來轉移或轉寄通話。 
 
來電轉接要求初始使用者在來電轉接時接聽電話，而不需要先接聽來電。 這表示即使 User1 不在位置，也可以轉寄呼叫來接收撥入通話（請參閱[小組使用者從 PSTN 區段接收入站通話](#teams-user-receives-an-inbound-call-from-the-pstn)），而且如果 user1 無法接收撥入通話，就無法傳送通話。 

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用位置路由

未啟用位置路由的使用者可以將 PSTN 來電轉接或轉寄到其他未啟用位置路由的使用者。 使用者通常不能將 PSTN 來電轉接或轉寄給啟用位置式路由的使用者，因為以位置為基礎的路由使用者通常只能在以位置為基礎的路由的 PSTN 呼叫閘道上共同使用。 例外狀況是當啟用位置路由的使用者漫遊至尚未啟用位置路由的網站時。 在這種情況下，允許轉接的通話。  

同樣地，沒有啟用位置路由的使用者，只能從另一個尚未啟用位置路由的使用者接收轉接或轉寄的 PSTN 通話。 

#### <a name="user-enabled-for-location-based-routing"></a>已啟用使用者的位置路由

一般來說，只有在目標使用者已啟用位置路由且位於相同的網站時，才能從啟用位置路由的閘道轉移和轉寄進貨 PSTN 呼叫。 否則，不允許轉移和轉接通話。 

下表顯示是否允許來電轉接與來電轉接，視目標使用者的位置而定。 在此表格中，位於 Site1 中的 [User1]，會啟動轉接或轉寄給其他團隊使用者，這些使用者也是已啟用位置式路由及位於不同位置的使用者。  

|目標使用者端點位置|User1 啟動來電轉接 |User1 啟動來電轉接|
|---------|---------|---------|
|與發起者相同的網路網站（例如）|允許|允許|
|不同的網路網站，已針對位置路由（User3）啟用網站|不允許|不允許|
|不同的網路網站，沒有為以位置為基礎的路由（User4）啟用網站|不允許|不允許|
|未知的內部網路（User5）| 不允許|不允許|
|未知外部網路（User6）| 不允許|不允許|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>小組使用者將來電轉接或轉寄給 PSTN 端點

#### <a name="user-not-enabled-for-location-based-routing"></a>使用者未啟用位置路由

- 允許將 PSTN 來電轉接並轉寄到另一個 PSTN 號碼。 
- 將入站 VOIP 來電轉接及轉寄到 PSTN，必須遵守來電者的免付費回避限制。 
    - 如果呼叫者未啟用位置路由，可以將它們傳輸到任何未啟用位置路由的 PSTN 閘道。
    - 如果呼叫者已啟用位置路由，則只能將其轉移到位於相同網路網站的以位置為基礎的路由啟用的閘道。 

#### <a name="user-enabled-for-location-based-routing"></a>已啟用使用者的位置路由

- 將 PSTN 來電轉接及轉寄轉移到另一個 PSTN 號碼的同時，必須在同一個以位置為基礎且已撥入來電的閘道路由。 
- 將入站 VOIP 來電轉接及轉寄到 PSTN 時，必須同時服從呼叫者，並呼叫使用者的免付費旁路限制。 
    - 如果呼叫者未啟用位置路由，可以將它們傳輸到任何未啟用位置路由的 PSTN 閘道。
    - 如果呼叫者是針對位置路由啟用，則只能將它們轉移至位於相同網路網站的以位置為基礎的路由啟用的閘道。
 
下表顯示如何將 VOIP 呼叫從使用者 Site1 傳送到不同位置的使用者，這些位置是轉接或轉寄 PSTN 端點的電話。  

|使用者啟動來電轉接或轉寄  |轉接至 PSTN  |轉接至 PSTN  |
|---------|---------|---------|
|相同的網路網站，已針對位置路由（選擇2）啟用網站   |您只能透過 User2's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 傳送來電轉接         |根據 User2's 語音路由策略，在 Site1 中，呼叫轉寄只能透過以位置為基礎的路由 Gateway1 進行路由         |
|不同的網路網站，已針對位置路由（User3）啟用網站    |您只能透過 User3's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 傳送來電轉接         |根據 User3's 語音路由策略，在 Site1 上使用以位置為基礎的路由 Gateway1 傳送呼叫轉寄功能         |
|不同的網路網站，沒有為以位置為基礎的路由（User4）啟用網站    |您只能透過 User4's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 傳送來電轉接         |根據 User4's 語音路由策略，在 Site1 上使用以位置為基礎的路由 Gateway1 傳送呼叫轉寄功能         |
|未知的內部網路（User5）     |您只能透過 User5's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 傳送來電轉接         |根據 User5's 語音路由策略，在 Site1 上使用以位置為基礎的路由 Gateway1 傳送呼叫轉寄功能         |
|未知外部網路（User6）   |您只能透過 User6's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 傳送來電轉接        |根據 User6's 語音路由策略，在 Site1 上使用以位置為基礎的路由 Gateway1 傳送呼叫轉寄功能         |

### <a name="simultaneous-ringing"></a>同時響鈴

當啟用位置路由的使用者收到通話且同時來電時，以位置為基礎的路由會分析呼叫方的位置，以及呼叫方的端點，判斷是否應該路由通話。 同時響鈴遵循與來電轉接與轉寄相同的位置規則。 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>同時撥打另一個小組使用者

下表顯示針對 User1 的進貨 PSTN 呼叫，以位置為基礎的路由是否允許不同的使用者同時撥打給不同的使用者。

|目標使用者端點位置|同時撥打  |
|---------|---------|
|與發起者相同的網路網站（例如）   |允許         |
|針對位置路由（User3）啟用不同的漫遊網路網站   |不允許         |
|漫遊網路網站未啟用位置路由（User4）   |不允許        |
|未知的內部網路（User5）    | 不允許        |
|未知外部網路（User6）    |不允許        |
|目標使用者是 PSTN 號碼    |只能透過 User1's 語音路由策略，在 Site1 上啟用以位置為基礎的路由 Gateway1 進行呼叫路由      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>同時撥打 PSTN 端點

下表顯示從 Site1 到不同位置的輸入 VOIP 呼叫的位置路由行為，並將同時撥打的使用者數設定為 PSTN 號碼。 

|呼叫使用者端點位置  |同時振鈴目標是 PSTN 端點 |
|---------|---------|
|相同的網路網站，已針對位置路由（選擇2）啟用網站    |只能透過 User2's 語音路由策略，在 Site1 上以位置為基礎的路由 Gateway1 傳送通話       |
|針對位置路由（User3）啟用不同的網路網站    |呼叫只能透過以位置為基礎的路由 Gateway1 在 Site1 上根據 User3's 語音路由策略來路由        |
|未針對位置路由（User4）啟用不同的網路網站    |呼叫只能透過以位置為基礎的路由 Gateway1 在 Site1 上根據 User4's 語音路由策略來路由         |
|未知的內部網路（User5）    |呼叫只能透過以位置為基礎的路由 Gateway1 在 Site1 上根據 User5's 語音路由策略來路由         |
|未知外部網路（User6）   |呼叫只能透過以位置為基礎的路由 Gateway1 在 Site1 上根據 User6's 語音路由策略來路由         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>透過語音 app 撥入通話（自動語音應答或通話佇列）

允許來自以位置為基礎的路由的入站 PSTN 呼叫連線至自動語音應答或通話佇列。 針對位置式路由啟用的使用者，只要位於輸入 PSTN 呼叫產生的同一個網站，就只能接收來自這些應用程式的入站來電轉接。 
 
語音 app 傳輸允許來電轉接及同時撥打給使用者和 PSTN。 完成對目標的呼叫，受限於前面所列的以位置為基礎的路由規則。  
 
也允許轉接至語音信箱。  

### <a name="delegation"></a>委派

團隊使用者可以選擇代表自己撥打或接聽電話的代理人。 小組中的委派功能受到依位置的路由影響，如下所示： 
- 如果您代表 delegator 從某個位置路由的代理啟用委派撥出電話，就會套用相同的規則。 呼叫路由是以代理人的呼叫授權原則、語音路由原則和位置為基礎。 如需詳細資訊，請參閱[小組使用者將出站呼叫放入 PSTN](#teams-user-places-an-outbound-call-to-the-pstn)。 
- 對 delegator 的入站 PSTN 呼叫而言，用於來電轉接或同時撥打給其他使用者的相同位置路由規則也適用于代理人。 如需詳細資訊，請參閱[小組使用者轉移或轉寄呼叫給其他團隊使用者](#teams-user-transfers-or-forwards-call-to-another-teams-user)、[團隊使用者將來電轉接或轉寄給 PSTN 端點](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)，以及[同時撥打](#simultaneous-ringing)。 如果代理人將 PSTN 端點設定為同時環目標，則會使用委派的語音路由策略，將呼叫路由至 PSTN。 
- 若是委派，建議您將 delegator 及相關聯的代理人放在同一個網路網站中。 

## <a name="other-planning-considerations"></a>其他規劃考慮

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>從內部部署位置路由部署所做的變更

已不再使用網路網站語音路由原則。 相反地，我們會使用使用者的語音路由原則。 這表示，若要讓使用者能夠漫遊到其他網站，語音路由策略必須包含漫遊網站的閘道。 

### <a name="technical-considerations-for-location-based-routing"></a>位置基礎路由的技術考量

支援 IPv4 與 IPv6 子網，但在檢查相符時，會優先考慮 IPv6。

### <a name="client-support-for-location-based-routing"></a>以位置為基礎的路由的用戶端支援

支援下列團隊用戶端：
- 團隊桌面用戶端（Windows 和 Mac）
- 團隊行動用戶端（iOS 和 Android）
- 團隊 IP 電話

不支援小組網頁用戶端與商務用 Skype 用戶端。

### <a name="capabilities-not-supported-by-location-based-routing"></a>未受位置基礎路由支援的功能

以位置為基礎的路由不適用於下列類型的互動。 當團隊端點與下列案例中的 PSTN 端點互動時，不會強制執行位置路由： 
- 透過通話駐留撥打電話給寄存或檢索 PSTN 電話 
- 內部部署商務用 Skype 使用者或商務用 Skype Online 使用者會呼叫團隊使用者  

### <a name="location-based-routing-for-conferencing"></a>以位置為基礎的會議路由

在 PSTN 通話中啟用位置路由的使用者，不允許以其他使用者或 PSTN 號碼開始會議。 允許連線到自動語音應答或通話佇列。 如果使用者有會議授權，使用者必須啟動一則與相關使用者的會議，並透過會議橋打電話給 PSTN，以開始電話會議。  

### <a name="media-bypass-requirement-for-location-based-routing"></a>針對位置路由的媒體旁路需求

如果您是在印度部署以位置為基礎的路由，也就是設定媒體旁路的需求。 若要深入瞭解，請參閱使用直接路由與[本機媒體優化來](direct-routing-media-optimization.md)[規劃媒體旁路](direct-routing-plan-media-bypass.md)。

## <a name="next-steps"></a>後續步驟

移至[設定位置路由的網路設定](location-based-routing-configure-network-settings.md)。

## <a name="related-topics"></a>相關主題

- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [小組中雲端語音功能的網路設定](cloud-voice-network-settings.md)
