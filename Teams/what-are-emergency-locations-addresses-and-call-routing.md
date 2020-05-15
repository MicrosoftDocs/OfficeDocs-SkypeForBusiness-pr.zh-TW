---
title: 規劃及管理緊急通話
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 瞭解緊急通話，包括緊急位址、緊急通話路由及動態緊急通話的相關資訊。
ms.openlocfilehash: 8c2de31aa81ac36338560c9b75d5c7ef27e460f8
ms.sourcegitcommit: 000515147632c6278bcda4505a1038014dda8e2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232544"
---
# <a name="manage-emergency-calling"></a>管理緊急通話

本文將說明管理緊急通話所需注意的概念，包括緊急位址、動態緊急位址及緊急呼叫路由的相關資訊。 本文使用下列術語：

- **緊急位址**-一個市政位址，即貴組織的公司位置的實體或街道位址。

  例如，位址 12345 [*北部] 街道、[雷德蒙]、[98052 華盛頓] （WA））* 是用來將緊急呼叫路由至適當的派單頒發機構，並協助您尋找緊急來電者。

- **地點**-通常是底價、樓、翼或辦公室號碼。 [地點] 與緊急位址相關聯，可在建築物中提供更精確的位置。 您可以有與緊急位址相關聯的不限制數量的位置。 例如，如果您的組織有多個建築物，您可能會想要在每個建築物中包含每個建築物和每個樓層的位置資訊。  

- **緊急位置**-位置是市政位址，有一個選用的位置。 如果您的公司有一個以上的物理位置，可能需要一個以上的緊急位置。 

  當您建立緊急位址時，系統會自動為此位址建立唯一的位置識別碼。  如果您在 [急診位址] 中新增位置，例如，如果您在建築物位址加上樓面，就會為 [緊急位址] 和 [地點] 的組合建立位置 ID。  在這個範例中，會有兩個位置 Id：一個用於市政位址;一個用於已連接的市政位址和相關聯的位置。

  當您將緊急位置指派給使用者或網站時，它就是與使用者或網站相關聯的唯一位置識別碼。

- **已**登錄的位址-指派給每個通話方案使用者的緊急位址;它有時稱為靜態緊急位址或記錄的位址。  （已註冊的位址不適用於直接路由使用者）。

您可以使用 [團隊系統管理中心]，為通話方案使用者建立緊急位址。  

>[!Note]
>您管理緊急呼叫的方式有一些差異，取決於您使用的是電話系統通話方案，還是您的 PSTN 連線的電話系統直向路由。 本文將說明這些考慮。

## <a name="emergency-address-validation"></a>緊急位址驗證

若要將緊急位址指派給使用者或網路識別碼，您必須確保緊急位址標示為「已驗證」。  位址驗證可確保位址合法，且在指派後無法進行修改。 

如果您使用 [團隊系統管理中心] 的 [位址圖] 搜尋功能來定義緊急位址，位址就會自動標示為 [已驗證]。 您無法修改已驗證的緊急位址。 因此，如果位址的格式或代表變更，您必須使用已更新的格式建立新的位址。


## <a name="emergency-address-geo-codes"></a>緊急位址 geo 代碼

每個緊急位址都可以有與其相關聯的地理程式碼（緯度和經度）。 在某些國家/地區使用這些地理程式碼，以協助以動態位置路由緊急通話。 

如果您使用 [團隊系統管理中心] 的 [位址圖] 搜尋功能來定義緊急位址，則地理程式碼會自動與緊急位址建立關聯。 如果您使用 PowerShell 定義位址，您也可以將地區代碼與位址建立關聯。 不過，Microsoft 建議您使用 [團隊系統管理中心] 中的 [地圖搜尋] 功能，為通話方案建立緊急位址，這將確保位址已格式化、驗證且具有適當的地區代碼。  

>[!Important]
>若要將緊急位置指派給網路識別碼以進行動態緊急通話，緊急位址必須包含適當的地理程式碼。


## <a name="considerations-for-calling-plans"></a>通話方案的考慮

若要瞭解您所在地區是否有可用的通話方案，請參閱[通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。


### <a name="emergency-call-enablement"></a>緊急通話啟用

每個通話方案使用者都會自動啟用緊急通話，而且必須擁有與其指派的電話號碼相關聯的註冊緊急位址。 

當位置必須與電話號碼相關聯時，視國家/地區而定：

- 例如，在美國和加拿大，在指派數位給使用者時，需要緊急位置。

- 在其他國家/地區（例如歐洲、中東及非洲（EMEA）），當您從 Office 365 取得電話號碼或從另一個服務提供者或承運商轉接時，就需要緊急位置。

### <a name="dynamic-emergency-calling"></a>動態緊急通話

Microsoft 通話方案的動態緊急通話可提供根據團隊用戶端目前位置來設定和路由緊急通話的功能。 自動路由至適當的公用安全回應點（PSAP）或通知安全服務台人員的功能，會視小組使用者使用的國家/地區而有所不同。  

針對呼叫方案使用者，只支援在美國進行路由緊急通話的動態位置，如下所示。 （如需有關動態緊急通話與直接路由的詳細資訊，請參閱[直接路由的注意事項](#considerations-for-direct-routing)。

- 如果美國通話方案使用者的團隊用戶端動態取得美國境內的緊急位址，該位址會用於緊急路由，而不是已註冊的位址，而且通話會自動路由到位址的服務區域中的 PSAP。

- 如果美國通話方案使用者的團隊用戶端無法在美國動態取得緊急位址，則會使用註冊的緊急位址來協助螢幕並傳送通話。 不過，在將呼叫者連線至適當的 PSAP 之前，會進行通話，以判斷是否需要更新的位址。

在美國，您必須設定作為指派給網路識別碼之緊急位置一部分的市政位址，並包含相關聯的地理程式碼。 如需詳細資訊，請參閱[規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。


### <a name="emergency-call-routing"></a>緊急通話路由

當小組通話方案使用者撥打電話號碼時，通話如何路由至 PSAP，取決於下列情況：

- 緊急位址是否由團隊用戶端動態決定。

- 緊急位址是否是與使用者的電話號碼相關聯的登入位址。

- 該國家/地區的緊急通話網路。

  **在美國：**

  - 如果團隊用戶端位於租使用者定義的動態緊急位置，來自該用戶端的緊急呼叫會自動路由至該地理位置的 PSAP 服務。 

  - 如果團隊用戶端不在租使用者的動態緊急位置，來自該用戶端的緊急呼叫是由國內話務中心加以遮罩，在將來電轉接到該地理位置的 PSAP 之前，決定呼叫者的位置。

  - 如果緊急來電者無法將其緊急位置更新至 [篩選中心]，該呼叫將會傳送給呼叫者登入位址的 PSAP。

  **在加拿大、愛爾蘭及英國**，緊急通話是在將呼叫連接至適當的派遣中心之前，先進行確認，以判斷使用者目前的位置。 

  **在華北、德國和西班牙**，緊急通話會直接路由到 PSAP 中與電話號碼相關聯之緊急位址的服務，而不管來電者的位置為何。

  **在荷蘭**，無論來電者為何位置，緊急通話都會直接路由到該號碼當地區號的 PSAP。

  **在澳大利亞**，緊急位址是由電信公司合作夥伴設定和路由。

  **在日本**，不支援緊急通話。


如需詳細資訊，請參閱：

- [通話方案](calling-plan-landing-page.md)

- [通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)

- [緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-direct-routing"></a>直接路由的考慮

如果您的地區無法使用通話方案，或者您想要保留現有的承運人，請考慮[直接傳送](direct-routing-landing-page.md)。 如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)及[管理緊急呼叫路由策略](manage-emergency-call-routing-policies.md)。

### <a name="emergency-call-enablement-and-configuration"></a>緊急通話啟用與設定

您必須使用 TeamsEmergencyCallRoutingPolicy 來定義直接路由使用者的緊急通話原則，以定義緊急號碼及其相關聯的路由目的地。 （請注意，直接路由使用者不支援註冊的緊急位置。）

您可以將 TeamsEmergencyCallRoutingPolicy 指派給團隊直接傳送使用者帳戶、網路網站或兩者。 當團隊用戶端啟動或變更網路連線時，小組會在用戶端所在的網路網站上執行查閱，如下所示：

- 如果 TeamsEmergencyCallRoutingPolicy 與網站相關聯，則會使用網站原則設定緊急通話。

- 如果沒有與網站相關聯的 TeamsEmergencyCallRoutingPolicy，或用戶端是在未定義的網站上連線，則會使用與使用者帳戶相關聯的 TeamsEmergencyCallRoutingPolicy 來設定緊急通話。 

- 如果團隊用戶端無法取得 TeamsEmergencyCallRoutingPolicy，則不會啟用緊急通話的使用者。

### <a name="dynamic-emergency-calling"></a>動態緊急通話

直接路由使用者的團隊用戶端可以取得動態緊急位址，這可以根據來電者的位置來動態路由通話。 如需詳細資訊，請參閱[設定動態緊急通話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing"></a>緊急通話路由

TeamsEmergencyCallRoutingPolicy 參照的是線上 PSTN 使用量，必須具備適當的直接路由設定，才能將緊急通話正確地路由至適當的 PSTN 閘道。 特別是，您必須確保緊急撥號字串有 OnlineVoiceRoute。 如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。 

（注意：團隊用戶端會在緊急電話號碼前面加上「+」登入，就像商務用 Skype 用戶端所做的一樣，也就是 + 911。 在未來幾個月內將會修改這項行為，如此一來，進行緊急通話的小組就不會再傳送數位前面的 "+";也就是說，911。）

針對直接路由使用者動態路由緊急呼叫的能力，視特定國家/地區內的緊急呼叫網路而定。 提供兩種解決方案：

- 緊急路由服務提供者（僅限美國） 
- 緊急位置身分識別號碼（ELIN）閘道應用程式

#### <a name="emergency-routing-service-providers"></a>緊急路由服務提供者

在美國，有許多認證的緊急路由服務提供者（ERSPs）可以根據來電者的位置自動路由緊急通話。

- 如果緊急路由服務提供者已整合至直接路由部署，則使用動態取得位置的緊急呼叫會自動路由到該位置的公用安全應答點（PSAP）。

-  在沒有動態取得位置的緊急通話是先進行篩選，以便在根據更新的位置將呼叫連線至適當的派遣中心之前，決定使用者的目前位置。

如需詳細資訊，請參閱針對[直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-elin-applications"></a>緊急位置識別號碼（ELIN）應用程式

會話邊界控制器（SBCs）可以包含緊急位置身分識別號碼（ELIN）應用程式。 如果 SBC ELIN 應用程式已整合至直接路由部署，您必須在 ELIN 應用程式中設定緊急位址和相關的電話號碼，然後將 ELIN 記錄上傳到各自 PSTN 中的緊急呼叫資料庫。  使用 ELIN 識別碼的小組緊急位置，必須符合 ELIN 應用程式中的專案。

當有動態取得位置的緊急通話路由至適當的 SBC 時，ELIN 應用程式：

- 分析來電者的緊急位置。
- 將位置與 ELIN 記錄相符。
- 以 ELIN 電話號碼取代緊急來電者的號碼。
- 將呼叫路由至該位置的 PSAP，然後重新分派者從上傳的 ELIN 記錄中取得位置。

當來電回緊急電話號碼時，ELIN 應用程式將會對原始緊急來電者執行反向呼叫數位替換。 

如需詳細資訊，請參閱針對[直接路由認證的會話邊界控制器](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>Security 辦公桌通知

Microsoft 通話方案和電話系統直接路由都提供了 Security 辦公桌通知。

您可以使用 TeamsEmergencyCallingPolicy 來設定要在緊急通話期間收到通知的人員，以及通知的方式： [僅限聊天]、[conferenced] 和 [已靜音]，或 [conferenced] 中的 [取消靜音] 功能。  您也可以指定使用者或群組的外部 PSTN 號碼來撥打並加入緊急通話。 

您可以將 TeamsEmergencyCallingPolicy 授與兩個小組使用者帳戶、指派給網路網站或兩者。  當團隊用戶端啟動或變更網路連線時，小組會針對用戶端所在的網路網站執行查閱：

- 如果 TeamsEmergencyCallingPolicy 與網路網站相關聯，則會使用網站原則來設定 security 辦公桌通知。

- 如果沒有與網站相關聯的 TeamsEmergencyCallingPolicy，或用戶端是在未定義的網站上連線，則會使用與使用者帳戶相關聯的 TeamsEmergencyCallingPolicy 來設定 security 辦公桌通知。  

- 如果團隊用戶端無法取得 TeamsEmergencyCallingPolicy，則不會為使用者啟用 security 辦公桌通知。

在緊急通話期間，安全服務台是 conferenced 到通話中，而安全服務台使用者則是根據 TeamsEmergencyCallingPolicy 進行控制。 群組聊天是從每個安全服務台成員開始，緊急呼叫者的位置會透過重要的訊息通知來共用。  如果會議選項是設定為原則的一部分，則每個安全服務台使用者也會在會議中另行稱為。

    
## <a name="related-topics"></a>相關主題

- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急呼叫路由策略](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
