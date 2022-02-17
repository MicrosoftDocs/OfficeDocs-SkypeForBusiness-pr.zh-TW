---
title: 規劃及管理緊急電話
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
- Calling Plans
- Direct Routing
- seo-marvel-mar2020
description: 瞭解緊急通話，包括關於緊急位址、緊急電話路由和動態緊急電話的資訊。
ms.openlocfilehash: db78ff3b8384cc923daa24f119852240fc1744d6
ms.sourcegitcommit: 2ddbaecb0bb7776dc5ab88727b1335e7e46d3704
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2022
ms.locfileid: "62881518"
---
# <a name="manage-emergency-calling"></a>管理緊急電話

本文將說明管理 &mdash; 緊急電話時必須瞭解的概念，包括緊急位址、動態緊急位址和緊急電話路由的資訊。 本文使用下列術語：

- **緊急位址** - 貴組織 &mdash; 營業地點的市民位址。

  例如，位址 *12345 North Main Street， Redmond， WA 98052* 是用來路由緊急電話給適當的調度機構，並協助尋找緊急來電者。

- **位置** - 通常是樓面、建築物、樓面或辦公室號碼。 Place 與緊急位址相關聯，以在建築物內提供更精確的位置。 您可以擁有無限個與緊急位址相關聯的位置。 例如，如果貴組織有多個建築物，您可能會想要包含每個建築物和每棟大樓內每一層的位置資訊。  

- **緊急位置** - 位置是具有選擇性 &mdash; 位置的市民位址。 如果您的公司有一多個實體位置，您可能需要多個緊急位置。 

  當您建立緊急位址時，會自動為此位址建立唯一的位置識別碼。 例如，如果您新增 &mdash; &mdash; 位置至緊急位址，如果您新增樓面至建築物位址，會針對緊急位址和地點的組合建立位置識別碼。  在此範例中，將會有兩個位置的 ID：一個為市民位址;一個為已加入的市民位址和相關位置。

  當您將緊急位置指派給使用者或網站時，這是與使用者或網站相關聯的這個唯一位置識別碼。

- **已登入位址** - 指派給每個使用者的緊急位址。 登入位址有時稱為靜態緊急位址或記錄位址。  (目前，直接路由不支援已註冊的位址。 請儘快回來查看更新。) 

>[!Note]
>視您使用的是 Microsoft 通話方案、接線連線或[PSTN](pstn-connectivity.md)連接直接路由，您管理緊急電話方式有一些差異。 本文將說明這些考慮事項。

## <a name="emergency-address-validation"></a>緊急位址驗證

若要將緊急位址指派給使用者或網路識別碼，您必須確保緊急位址標示為「已驗證」。 位址驗證可確保位址合法，且在指派位址後無法修改。 

如果您在系統管理中心使用位址地圖搜尋功能來定義緊急Teams，位址會自動標示為已驗證。 因為如果位址的格式 &mdash; 或表示方式變更，您無法修改經過驗證的緊急位址，您必須使用更新的格式建立新位址。


## <a name="emergency-address-geo-codes"></a>緊急位址地理代碼

每個緊急位址都可以有一個地理代碼 (與經度) 與它相關聯。 在一些國家/地區，這些地理代碼可用來協助以動態位置路由緊急電話。 

如果您在系統管理中心使用位址Teams搜尋功能來定義緊急位址，則地理代碼會自動與緊急位址相關聯。 如果您使用 PowerShell 定義位址，您也可以將地理位置代碼與位址建立關聯。 

Microsoft 建議您使用 Teams 系統管理中心的地圖搜尋功能來建立緊急位址，以確保位址已格式化、驗證，並擁有適當的地理位置代碼。 

>[!Important]
>若要將緊急位置指派給動態緊急電話的網路識別碼，緊急位址必須包含適當的地理位置代碼。


## <a name="considerations-for-calling-plans"></a>通話方案考慮

下列各節說明如何管理 Microsoft 通話方案使用者的緊急通話。 若要瞭解 Microsoft 通話方案是否適合您企業的解決方案，請參閱 [PSTN 連接選項](pstn-connectivity.md)。


### <a name="emergency-call-enablement-for-calling-plans"></a>通話方案緊急通話啟用功能

每個通話方案使用者會自動啟用緊急電話，而且必須擁有與其指派的電話號碼相關聯的已註冊緊急位址。 

當位置與電話號碼相關聯時，取決於國家/地區：

- 例如，在美國和加拿大，當號碼指派給使用者時，需要緊急位置。

- 對於歐洲 &mdash; 、中東和非洲 (EMEA) 等其他國家/地區) &mdash; 當您從 Microsoft 365 取得電話號碼，或從另一個服務提供者或電信公司移轉電話號碼時，需要緊急位置。


### <a name="dynamic-emergency-calling-for-calling-plans"></a>通話方案的動態緊急電話

針對通話方案的動態緊急電話提供根據用戶端目前位置設定及路由緊急Teams功能。 自動路由至適當的公用安全應答點 (PSAP) 或通知安全性服務台人員的能力會視使用者使用Teams而異。  

美國支援路由緊急電話的動態位置，如下所示。 

- 如果美國Teams方案使用者的 Teams 用戶端動態取得美國國內的緊急位址，該位址會用於緊急路由，而非登入位址，且該通話會自動路由至位址服務區域中的 PSAP。

- 如果Teams美國通話方案使用者的用戶端無法在美國境內動態取得緊急位址，則已註冊的緊急位址會用來協助螢幕和路由通話。 不過，在將來電者連接到適當的 PSAP 之前，會先篩選電話，判斷是否必須更新位址。

加拿大支援撥打緊急電話的動態位置，但下列例外情況除外：所有緊急電話都會在轉接至 PSAP 之前，先進行國內的篩選。

詳細資訊請參閱規劃 [及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-calling-plans"></a>通話方案緊急通話路由

當Teams方案使用者撥打緊急號碼時，呼叫路由至 PSAP 的方式取決於下列各項：

- 緊急位址是否由用戶端動態Teams決定。

- 緊急位址是否與使用者電話號碼相關聯的登入位址。

- 該國家/地區緊急電話網絡。

例如：

**在美國：**

- 如果Teams用戶端位於租使用者定義的動態緊急位置，該用戶端的緊急電話會自動路由至該地理位置的 PSAP。

- 如果 Teams 用戶端未位於租使用者定義的動態緊急位置，則來自該客戶的緊急電話會由國家電話中心進行篩選，以決定來電者的位置，然後再將來電轉接至該地理位置的 PSAP。

- 如果緊急來電者無法將其緊急位置更新至篩選中心，來電會轉接至 PSAP，提供來電者的登入位址。

**在加拿大、愛爾蘭** 及英國，緊急電話會先進行篩選，以判斷使用者的目前位置，然後再將電話連接到適當的調度中心。

**在法國、德國** 和西班牙，無論來電者的位置如何，緊急電話都會直接路由至 PSAP，服務與號碼相關聯的緊急位址。

**在荷蘭，** 無論來電者的位置如何，緊急電話都會直接路由至當地區碼的 PSAP。

**在澳大利亞，** 緊急位址是由電信合作夥伴進行配置和路由。

**日本不支援** 緊急電話。


詳細資訊，請參閱：

- [通話方案](calling-plan-landing-page.md)
- [設定通話方案](set-up-calling-plans.md)
- [用於通話方案的各種電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>運算子的考慮連線

下列各節說明如何管理運算子和使用者的連線通話。 若要瞭解 [運算子連線是否適合您企業的解決方案，請參閱[PSTN 連接選項](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-operator-connect"></a>運算子的緊急通話啟用連線

系統會自動連線每位接線員和使用者撥打緊急電話。 緊急電話會自動路由至電信連線號碼的電信公司。

租使用者系統管理員為運算子 連線 使用者設定登入位址的能力，取決於電信公司將號碼上傳到客戶庫存時指派給該號碼的功能。 根據這項設定，租使用者系統管理員可能 &mdash; &mdash; 必須或無法設定、修改或刪除使用者的緊急位置。 

### <a name="dynamic-emergency-calling-for-operator-connect"></a>運算子電話機的動態緊急連線

針對 Operator 連線動態緊急電話提供根據用戶端目前位置來設定及路由緊急Teams通話。 自動路由至適當的公用安全應答點 (PSAP) 或通知安全性服務台人員的能力會視使用者使用Teams而異。 

美國支援路由緊急電話的動態位置，如下所示。 

- 如果Teams使用者的 Teams 用戶端在美國境內動態取得緊急位址，該位址會用於緊急路由，而非已註冊的位址，通話會自動路由至位址服務區域中的 PSAP。

- 如果Teams使用者的用戶端無法在美國境內動態取得緊急位址，則已註冊的緊急位址會用來協助螢幕和路由通話。 不過，在將來電者連接到適當的 PSAP 之前，會先篩選電話，判斷是否必須更新位址。

加拿大支援撥打緊急電話的動態位置，但下列例外情況除外：所有緊急電話都會在轉接至 PSAP 之前，先進行國內的篩選。

詳細資訊請參閱規劃 [及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-operator-connect"></a>接線員電話機的緊急連線

當Teams接線連線撥打緊急號碼時，呼叫路由至 PSAP 的方式取決於下列各項：

- 緊急位址是否由用戶端動態Teams決定。

- 緊急位址是否與使用者電話號碼相關聯的登入位址。

- 該國家/地區緊急電話網絡。

- 在美國和加拿大，動態路由是電信公司服務的一部分。 您不需要向另一個服務提供者取得這項服務。

- 如果Teams用戶端位於租使用者定義的動態緊急位置：

   - 在美國，來自該用戶端的緊急電話會自動路由至該地理位置的 PSAP。
   - 在加拿大，所有緊急電話都會先由國家電話中心進行篩選，再轉接至該地理位置的 PSAP。

- 如果 Teams 用戶端未位於租使用者定義的動態緊急位置，則來自該客戶的緊急電話會由國家電話中心進行篩選，以決定來電者的位置，然後再將來電轉接至該地理位置的 PSAP。

- 如果緊急來電者無法將其緊急位置更新至篩選中心，來電會轉接至 PSAP，提供來電者的登入位址。


## <a name="considerations-for-direct-routing"></a>直接路由的考慮

下列各節說明如何管理直接路由使用者的緊急通話。 若要瞭解直接路由是否適合您企業的解決方案，請參閱 [PSTN 連接選項](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-direct-routing"></a>直接路由的緊急通話啟用功能

針對直接路由，您必須使用緊急呼叫路由Teams定義緊急號碼及其相關聯的路由目的地[，](manage-emergency-call-routing-policies.md)以定義使用者的緊急通話政策。  (目前，直接路由使用者不支援已註冊的緊急位置。) 

您可以將緊急通話路由策略指派給直接路由使用者帳戶、網路網站或兩者。 當Teams用戶端啟動或變更網路Teams，系統會執行用戶端所在的網路網站的檢查，如下所示：

- 如果緊急呼叫路由策略與網站相關聯，則網站策略會用來設定緊急通話。

- 如果沒有與網站相關聯的緊急呼叫路由策略，如果用戶端是在未定義的網站上連接，或撥打的號碼不符合與網站相關聯的緊急通話路由策略中定義的任何緊急號碼，則與使用者帳戶相關聯的緊急通話路由策略會用來設定緊急通話。 

- 如果Teams用戶端無法取得緊急呼叫路由策略，則使用者不會啟用緊急通話。


### <a name="dynamic-emergency-calling-for-direct-routing"></a>直接路由的動態緊急電話

直接路由的動態緊急電話提供根據用戶端目前位置來設定及路由緊急Teams通話。 自動路由至適當的公用安全應答點 (PSAP) 或通知安全性服務台人員的能力會視使用者使用Teams國/地區而異。

對於直接路由使用者，只有美國支援路由緊急電話的動態位置，如下所示：

-   如果Teams直接路由使用者的用戶端動態取得美國的緊急位址，該位址會用於緊急路由，而且該通話會自動路由至位址服務區域中的 PSAP。

-   如果Teams直接路由使用者的用戶端未在美國境內動態取得緊急位址，將會先篩選電話，判斷在將來電者連接到適當的 PSAP 之前，是否必須更新位址。

加拿大支援撥打緊急電話的動態位置，但下列例外情況除外：所有緊急電話都會在轉接至 PSAP 之前，先進行國內的篩選。

詳細資訊，請參閱 [設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-direct-routing"></a>直接路由的緊急通話路由

直接路由的緊急呼叫路由策略會參照線上 PSTN 使用方式，此使用方式必須擁有適當的直接路由配置，以將緊急通話正確路由至適當的 PSTN (閘道) 。 特別是，您必須確保緊急撥號字串有 OnlineVoiceRoute。 詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。 

> [!NOTE]
> Teams用戶端不再將 「+」 符號預先放在緊急號碼前面;也就是說，+911。 因此，Teams緊急電話不會再在 911 號碼之前傳送「+」。 請確定語音路由模式反映此變更。

直接路由使用者動態路由緊急電話的能力會因特定國家/地區內的緊急通話網路而異。 有兩種可用的解決方案：

- [緊急路由服務提供者僅 (美國) ](#emergency-routing-service-providers)
- [緊急位置識別碼應用程式](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>緊急路由服務提供者

在美國，有許多經過認證的緊急路由服務提供者 (ERSP) 根據來電者的位置自動路由緊急電話。

- 如果緊急路由服務提供者已整合至直接路由部署，具有動態取得位置的緊急電話會自動路由至服務該位置的公用安全應答點 (PSAP) 點。

-  沒有動態取得位置的緊急電話會先經過篩選，以決定使用者的目前位置，然後再根據更新的位置將通話連接到適當的調度中心。

詳細資訊，請參閱會話 [邊界控制器通過直接路由認證](direct-routing-border-controllers.md)。


#### <a name="emergency-location-identification-number-applications"></a>緊急位置識別碼應用程式

會話邊界控制器 (SBC) ELIN 應用程式包含緊急 (識別) 號碼。 如果 SBC ELIN 應用程式已整合至直接路由部署，您必須在 ELIN 應用程式中設定緊急位址和相關電話號碼，然後將 ELIN 記錄上傳到各自 PSTN 中的緊急通話資料庫。 Teams ELIN 識別碼的緊急位置必須與 ELIN 應用程式中的位置相符。

當具有動態取得位置的緊急電話路由至適當的 SBC 時，ELIN 應用程式：

- 剖析來電者的緊急位置。
- 將位置與 ELIN 記錄比對。
- 以 ELIN 電話號碼取代緊急來電者的電話號碼。
- 將通話路由至服務該位置的 PSAP，然後調度員從上傳的 ELIN 記錄取得位置。

當呼叫回緊急號碼時，ELIN 應用程式會執行與原始緊急來電者相反的呼叫號碼取代。 

詳細資訊，請參閱會話 [邊界控制器通過直接路由認證](direct-routing-border-controllers.md)。


## <a name="security-desk-notification"></a>安全電話台通知

Microsoft 通話方案、接線連線和直接路由連線提供安全電話機通知。

您可以使用 Teams 緊急通話策略 (TeamsEmergencyCallingPolicy) 來設定在緊急通話期間應通知哪些人，以及通知方式：僅聊天、在會議中和靜音，或會議在和靜音中，但能夠取消靜音。 您也可以指定使用者或群組的外部 PSTN 號碼，以撥打並加入緊急通話。 請注意，PSTN 方不允許取消靜音。

緊急通話政策可以授予Teams使用者帳戶、指派給網路網站或兩者。  當用戶端Teams或變更網路連接時，Teams會執行用戶端所在的網路網站的檢查：

- 如果緊急通話策略與網路網站相關聯，則網站策略會用來設定安全電話機通知。

- 如果沒有與網站相關聯的緊急通話政策，或用戶端是在未定義的網站上連接，則與使用者帳戶相關聯的緊急通話策略會用來設定安全性電話機通知。  

- 如果Teams用戶端無法取得緊急通話政策，則使用者不會啟用安全電話台通知。

緊急通話期間，安全電話台會召開電話會議，而安全電話台使用者的體驗則根據緊急Teams控制。 每個安全電話台成員會開始進行群組聊天，而緊急來電者的位置會透過重要訊息通知共用。  如果會議選項已配置為策略的一部分，則每個安全電話台使用者會另外稱為會議的一部分。

    
## <a name="related-topics"></a>相關主題

- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急通話路由策略 ](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
