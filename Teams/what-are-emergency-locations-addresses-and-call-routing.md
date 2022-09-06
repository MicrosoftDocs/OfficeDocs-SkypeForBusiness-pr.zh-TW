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
description: 瞭解緊急電話，包括緊急位址、緊急電話路由和動態緊急電話的相關資訊。
ms.openlocfilehash: 2118bfd3f380ac5e5e2773f1f4ccdc703332893a
ms.sourcegitcommit: 75dfc3cd9b59282d68e35e4d7185da572eb3795c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2022
ms.locfileid: "67606562"
---
# <a name="manage-emergency-calling"></a>管理緊急通話

本文說明管理緊急電話 &mdash; 時需要瞭解的概念，包括緊急位址、動態緊急位址和緊急電話路由的相關資訊。 本文使用下列術語：

- **緊急位址** - 城市位址 &mdash; ：貴組織商務地點的實體或街地位址。

  例如，位址 *12345 North Main Street， Redmond， WA 98052* 是用來將緊急電話路由至適當的調度部門，並協助尋找緊急來電者。

- **地點** - 通常是樓層、大樓、大樓、大樓或辦公室號碼。 Place 與緊急位址相關聯，以便在建築物內提供更精確的位置。 與緊急位址相關聯的地點數量不限。 例如，如果您的組織有多個建築物，您可能會想要包含每棟大樓和每棟大樓內每個樓層的地點資訊。

- **緊急位置** - 位置是具有選用位置的市用位址 &mdash; 。 如果您的企業有多個實體位置，您可能需要多個緊急位置。

  當您建立緊急位址時，會自動為此位址建立一個唯一的位置識別碼。 例如，如果您將地點新增至緊急位址 &mdash; ，如果您將樓層新增到建築物位址 &mdash; ，則會建立一個位置識別碼，以用於緊急位址和地點的組合。  在此範例中，會有兩個位置識別碼：一個用於城市位址;一個用於加入的市用位址和相關聯的地點。

  當您將緊急位置指派給使用者或網站時，就是這個與使用者或網站相關聯的唯一位置識別碼。

- **登入位址** - 指派給每個使用者的緊急位址。 登入位址有時稱為靜態緊急位址或記錄位址。  (目前，直接路由不支援登錄位址。 請儘快回來查看更新。) 

>[!Note]
>根據您使用的是 Microsoft 通話方案、運算子連線、電信業者連線行動 (公開預覽版) 或[PSTN 聯](pstn-connectivity.md)機的直接路由，您管理緊急電話的方式有一些差異。 本文將說明這些考慮事項。

## <a name="emergency-address-validation"></a>緊急位址驗證

若要將緊急位址指派給使用者或網路識別碼，您必須確定緊急位址已標示為「已驗證」。 位址驗證可確保該位址合法，且在指派位址之後無法修改。

如果您使用 Teams 系統管理中心的位址地圖搜尋功能來定義緊急位址，該位址會自動標示為已驗證。 因為如果位址的格式或表示方式變更，您無法修改經過驗證的緊急位址 &mdash; ，您必須建立具有更新格式的新位址。

## <a name="emergency-address-geo-codes"></a>緊急位址地理代碼

每個緊急位址可以有 (緯度和經度) 相關聯的地理代碼。 這些地理代碼在某些國家/地區會用來協助以動態位置路由緊急通話。

如果您使用 Teams 系統管理中心的位址地圖搜尋功能來定義緊急位址，地理位置代碼會自動與緊急位址相關聯。 如果您使用 PowerShell 定義位址，也可以將地理代碼與位址建立關聯。

Microsoft 建議您使用 Teams 系統管理中心的地圖搜尋功能來建立緊急位址，這可確保位址的格式設定、驗證，並具有適當的地理代碼。

>[!Important]
>若要將緊急位置指派給動態緊急通話的網路識別碼，緊急位址必須包含適當的地理位置代碼。

## <a name="considerations-for-calling-plans"></a>通話方案的考慮

下列各節說明如何管理 Microsoft 通話方案使用者的緊急通話。 若要瞭解 Microsoft 通話方案是否適合您的企業，請參閱 [PSTN 連線選項](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-calling-plans"></a>通話方案的緊急通話啟用

每個通話方案使用者都會自動啟用緊急電話，且必須有與其指派的電話號碼相關聯的已註冊緊急位址。

與電話號碼相關聯的位置取決於國家/地區：

- 例如，在美國和加拿大，將號碼指派給使用者時，必須有緊急位置。

- 對於其他國家， &mdash; 例如歐洲、中東及非洲 (EMEA) &mdash; 當您從 Microsoft 365 取得電話號碼，或從其他服務提供者或電信業者移轉電話號碼時，必須有緊急位置。

### <a name="dynamic-emergency-calling-for-calling-plans"></a>通話方案的動態緊急通話

通話方案的動態緊急通話功能可根據 Teams 用戶端的目前位置來設定和路由緊急通話。 自動路由到適當 [Public Safety Answer point] (PSAP) 或通知安全性服務台人員的能力，會因 Teams 使用者的使用方式而有所不同。

美國支援用於路由緊急電話的動態位置，如下所示。

- 如果美國通話方案使用者的 Teams 用戶端在美國內動態取得緊急位址，該位址會用於緊急路由，而不是登入位址，而且電話會自動路由至位址服務區域中的 PSAP。

- 如果美國通話方案使用者的 Teams 用戶端未在美國內動態取得緊急位址，則註冊的緊急位址會用來協助螢幕和路由通話。 不過，在將來電者連線到適當的 PSAP 之前，將會對通話進行螢幕畫面，以判斷是否需要更新位址。

加拿大支援傳送緊急電話的動態位置，與在美國中的位置相同，但有下列例外狀況：所有緊急通話都會在傳輸到 PSAP 之前，先顯示國家/地區。

如需詳細資訊，請參閱 [規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-calling-plans"></a>通話方案的緊急通話路由

當 Teams 通話方案使用者撥打緊急號碼時，電話路由至 PSAP 的方式取決於下列專案：

- 緊急位址是否由 Teams 用戶端動態決定。

- 緊急位址是否為與使用者電話號碼相關聯的已登入位址。

- 該國家/地區的緊急通話網路。

例如：

**在美國中：**

- 如果 Teams 用戶端位於租使用者定義的動態緊急位置，來自該用戶端的緊急通話會自動路由至提供該地理位置的 PSAP。

- 如果 Teams 用戶端不是位於租使用者定義的動態緊急位置，國家/地區話務中心會對來自該用戶端的緊急通話進行篩選，以判斷來電者的位置，然後再將電話轉接至服務于該地理位置的 PSAP。

- 如果緊急來電者無法將其緊急位置更新至篩選中心，電話將會轉接至提供來電者登入位址的 PSAP。

**在加拿大、愛爾蘭和英國**，緊急電話會先畫面化，以判斷使用者目前的位置，然後再將通話連線到適當的調度中心。

**在法國、德國和西班牙**，無論來電者的位置為何，緊急電話都會直接路由至提供與號碼相關聯之緊急位址的 PSAP。

**在荷蘭**，緊急電話會直接路由至 PSAP，以取得當地號碼的區碼，不論來電者的位置為何。

**在澳洲**，緊急位址是由電信業者合作夥伴設定和路由。

**在日本**，不支援緊急通話。

如需詳細資訊，請參閱：

- [通話方案](calling-plan-landing-page.md)
- [設定通話方案](set-up-calling-plans.md)
- [通話方案所用的不同電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [緊急通話條款及條件](emergency-calling-terms-and-conditions.md)

## <a name="considerations-for-operator-connect"></a>運算子連線的考慮

下列各節說明如何管理運算子連線使用者的緊急通話。 若要瞭解運算子連線是否是您企業的正確解決方案，請參閱 [PSTN 連線選項](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-operator-connect"></a>運算子連線的緊急通話啟用

每個運算子連線使用者都會自動啟用緊急通話。 緊急電話會以指定號碼自動路由至運算子連線電信業者。

租使用者系統管理員設定運算子連線使用者之登錄位址的能力，將取決於電信業者將這些功能上傳至客戶庫存時指派給該號碼的功能。 根據此設定，租使用者系統管理員可能不需要 &mdash; 也無法 &mdash; 設定、修改或刪除使用者的緊急位置。

### <a name="dynamic-emergency-calling-for-operator-connect"></a>運算子連線的動態緊急通話

運算子連線的動態緊急通話功能可根據 Teams 用戶端的目前位置來設定和路由緊急通話。 自動路由到適當 [Public Safety Answer point] (PSAP) 或通知安全性服務台人員的能力，會因 Teams 使用者的使用方式而有所不同。

美國支援用於路由緊急電話的動態位置，如下所示。

- 如果美國使用者的 Teams 用戶端在美國內動態取得緊急位址，該位址會用於緊急路由，而不是登入位址，而且電話會自動路由至位址服務區域中的 PSAP。

- 如果美國使用者的 Teams 用戶端未在美國內動態取得緊急位址，則註冊的緊急位址會用來協助螢幕和路由通話。 不過，在將來電者連線到適當的 PSAP 之前，將會對通話進行螢幕畫面，以判斷是否需要更新位址。

加拿大支援傳送緊急電話的動態位置，與美國中的位置相同，但有下列例外狀況：所有緊急電話都會在傳輸到 PSAP 之前，先顯示國家/地區。

如需詳細資訊，請參閱 [規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-operator-connect"></a>運算子連線的緊急通話路由

當 Teams 運算子連線使用者撥打緊急號碼時，電話路由至 PSAP 的方式取決於下列專案：

- 緊急位址是否由 Teams 用戶端動態決定。

- 緊急位址是否為與使用者電話號碼相關聯的已登入位址。

- 該國家/地區的緊急通話網路。

- 在美國和加拿大，動態路由是承運業者服務的一部分。 您不需要向其他服務提供者購買此服務。

- 如果 Teams 用戶端位於租使用者定義的動態緊急位置：
  - 在美國中，來自該用戶端的緊急通話會自動路由至服務于該地理位置的 PSAP。
  - 在加拿大，所有緊急電話都會由國家電話中心進行篩選，然後再將電話轉接到該地理位置的 PSAP。

- 如果 Teams 用戶端不是位於租使用者定義的動態緊急位置，國家/地區話務中心會對來自該用戶端的緊急通話進行篩選，以判斷來電者的位置，然後再將電話轉接至服務于該地理位置的 PSAP。

- 如果緊急來電者無法將其緊急位置更新至篩選中心，電話將會轉接至提供來電者登入位址的 PSAP。

## <a name="considerations-for-operator-connect-mobile"></a>考慮電信業者連線行動

下列各節說明如何管理電信業者連線行動使用者的緊急通話。 若要瞭解電信業者連線行動是否是您企業的正確解決方案，請參閱[PSTN 連線選項](pstn-connectivity.md)。

**電信業者連線行動是公開預覽版。**

### <a name="emergency-call-enablement-for-operator-connect-mobile"></a>啟用電信業者連線行動的緊急通話

每個電信業者連線行動使用者都會自動啟用緊急電話。 緊急電話會自動傳送至指定號碼的電信業者連線行動電信業者。

租使用者系統管理員為電信業者連線行動使用者設定登入位址的能力，取決於電信業者將這些功能上傳至客戶庫存時指派給該號碼的功能。 根據此設定，租使用者系統管理員可能不需要或無法設定、修改或刪除使用者的緊急位置。

透過啟用 SIM 卡的智慧型手機的原生撥號器撥打電話時，您的電信業者可能會使用地理座標或處理通話的儲存格塔來大約緊急位置尋求協助。

### <a name="dynamic-emergency-calling-for-operator-connect-mobile"></a>電信業者連線行動的動態緊急電話

運算子連線的動態緊急通話功能可根據 Teams 用戶端的目前位置來設定和路由緊急通話。 自動路由到適當 [Public Safety Answer point] (PSAP) 或通知安全性服務台人員的能力，會因 Teams 使用者的使用方式而有所不同。

美國支援用於路由緊急電話的動態位置，如下所示。

- 如果美國使用者的 Teams 用戶端在美國內動態取得緊急位址，該位址會用於緊急路由，而不是登入位址，而且電話會自動路由至位址服務區域中的 PSAP。

- 如果美國使用者的 Teams 用戶端未在美國內動態取得緊急位址，則註冊的緊急位址會用來協助螢幕和路由通話。 不過，在將來電者連線到適當的 PSAP 之前，將會對通話進行螢幕畫面，以判斷是否需要更新位址。

加拿大支援傳送緊急電話的動態位置，與美國中的位置相同，但有下列例外狀況：所有緊急電話都會在傳輸到 PSAP 之前，先顯示國家/地區。

如需詳細資訊，請參閱 [規劃及設定動態緊急通話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-operator-connect-mobile"></a>電信業者連線行動的緊急通話路由

當 Teams 電信業者連線行動使用者使用 Microsoft Teams 用戶端撥打緊急號碼時，通話路由至 PSAP 的方式取決於下列專案：

- 緊急位址是否由 Teams 用戶端動態決定。

- 緊急位址是否為與使用者電話號碼相關聯的已登入位址。

- 該國家/地區的緊急通話網路。

- 在美國和加拿大，動態路由是承運業者服務的一部分。 您不需要向其他服務提供者購買此服務。

- 如果 Teams 用戶端位於租使用者定義的動態緊急位置：
  - 在美國中，來自該用戶端的緊急通話會自動路由至服務于該地理位置的 PSAP。
  - 在加拿大，所有緊急電話都會由國家電話中心進行篩選，然後再將電話轉接到該地理位置的 PSAP。

- 如果 Teams 用戶端不是位於租使用者定義的動態緊急位置，國家/地區話務中心會對來自該用戶端的緊急通話進行篩選，以判斷來電者的位置，然後再將電話轉接至服務于該地理位置的 PSAP。

- 如果緊急來電者無法將其緊急位置更新至篩選中心，電話將會轉接至提供來電者登入位址的 PSAP。

您的電信業者會管理透過SIM-Enabled智慧型手機原生撥號器撥打的所有緊急電話，而且可能會使用多種技術來估計緊急位置，以取得地理座標或是哪些基座正在處理通話等協助。如需詳細資訊，請連絡您的電信業者。


## <a name="considerations-for-direct-routing"></a>直接路由的考慮

下列各節說明如何管理直接路由使用者的緊急通話。 若要瞭解直接路由是否是您企業的正確解決方案，請參閱 [PSTN 連線選項](pstn-connectivity.md)。

### <a name="emergency-call-enablement-for-direct-routing"></a>啟用直接路由的緊急通話

針對直接路由，您必須使用 [Teams 緊急通話路由原則](manage-emergency-call-routing-policies.md) 來定義使用者的緊急通話原則，以定義緊急號碼及其相關路由目的地。  (目前已註冊的緊急位置不支援直接路由使用者。) 

您可以將緊急通話路由原則指派給直接路由使用者帳戶、網路網站或兩者。 當 Teams 用戶端啟動或變更網路連線時，Teams 會執行下列用戶端所在網路網站的查閱：

- 如果緊急電話路由原則與網站相關聯，則會使用網站原則來設定緊急通話。

- 如果沒有與網站相關聯的緊急呼叫路由原則、如果用戶端已連線到未定義的網站，或是撥號號碼不符合與網站相關聯的緊急呼叫路由原則中定義的任何緊急號碼，則會使用與使用者帳戶相關聯的緊急呼叫路由原則來設定緊急電話。

- 如果 Teams 用戶端無法取得緊急通話路由原則，表示使用者無法進行緊急通話。

### <a name="dynamic-emergency-calling-for-direct-routing"></a>直接路由的動態緊急通話

直接路由的動態緊急通話提供功能，可根據 Teams 用戶端的目前位置來設定和路由緊急通話。 自動路由到適當 [Public Safety Answer point] (PSAP) 或通知安全性服務台人員的能力，會因 Teams 使用者的使用方式而有所不同。

針對直接路由使用者，只有下列美國才支援傳閱緊急電話的動態位置：

- 如果 美國直接路由使用者的 Teams 用戶端在美國內動態取得緊急位址，該位址會用於緊急路由，而且電話會自動路由至位址服務區域中的 PSAP。

- 如果美國直接路由使用者的 Teams 用戶端未在美國內動態取得緊急位址，則會在將來電連接到適當的 PSAP 之前，對通話進行篩選以判斷是否需要更新位址。

加拿大支援傳送緊急電話的動態位置，與在美國中的位置相同，但有下列例外狀況：所有緊急通話都會在傳輸到 PSAP 之前，先顯示國家/地區。

如需詳細資訊，請參閱 [設定動態緊急通話](configure-dynamic-emergency-calling.md)。

### <a name="emergency-call-routing-for-direct-routing"></a>直接路由的緊急通話路由

直接路由的緊急呼叫路由原則會參照線上 PSTN 使用量，必須具備適當的直接路由設定，才能正確地將緊急呼叫路由到適當的 PSTN 閘道 () 。 特別是，您必須確定緊急撥號字串有 OnlineVoiceRoute。 如需詳細資訊，請參閱 [設定直接路由](direct-routing-configure.md)。

> [!NOTE]
> Teams 用戶端不再在緊急號碼前面加上「+」登入;也就是 +911。 因此，Teams 緊急電話將不再于 911 號碼前面傳送「+」。 請確定您的語音路由模式反映此變更。

直接路由使用者動態路由緊急通話的能力會視指定國家/地區的緊急通話網路而有所不同。 有兩個解決方案可供使用：

- [緊急路由服務提供者僅 (美國) ](#emergency-routing-service-providers)
- [緊急位置識別號碼應用程式](#emergency-location-identification-number-applications)

#### <a name="emergency-routing-service-providers"></a>緊急路由服務提供者

在美國中，有許多經認證的緊急路由服務提供者 (ERSP) 可以根據來電者的位置自動路由緊急電話。

- 如果緊急路由服務提供者已整合到直接路由部署中，具有動態取得位置的緊急電話將會自動路由至服務該位置 (PSAP) 的 [Public Safety Answering Point]。

- 未動態取得位置的緊急通話會先進行篩選，以判斷使用者的目前位置，然後再根據更新的位置將通話連線到適當的調度中心。

如需詳細資訊，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

#### <a name="emergency-location-identification-number-applications"></a>緊急位置識別號碼應用程式

會話框線控制器 (SBC) 可以包含緊急位置識別編號 (ELIN) 應用程式。 如果 SBC ELIN 應用程式已整合到直接路由部署中，您必須在 ELIN 應用程式中設定緊急位址和相關聯的電話號碼，然後將 ELIN 記錄上傳到個別 PSTN 中的緊急通話資料庫。 使用 ELIN 識別碼的 Teams 緊急位置必須符合 ELIN 應用程式內的位置。

當有動態取得位置的緊急通話路由至適當的 SBC 時，ELIN 應用程式：

- 剖析來電者的緊急位置。
- 將位置與 ELIN 記錄相符。
- 以 ELIN 電話號碼取代緊急來電者的號碼。
- 將通話路由至服務該位置的 PSAP，然後由分派人員從上傳的 ELIN 記錄取得該位置。

當您撥回緊急號碼時，ELIN 應用程式會對原始緊急來電者執行反向的呼叫號碼替代。

如需詳細資訊，請參閱 [通過直接路由認證的會話框線控制器](direct-routing-border-controllers.md)。

## <a name="security-desk-notification"></a>安全性中心通知

Microsoft 通話方案、運算子連線和直接路由皆可使用安全性中心通知。

您可以使用 Teams 緊急通話原則 (TeamsEmergencyCalmerlingPolicy) 來設定應在緊急通話期間收到通知的人員，以及他們收到通知的方式：僅聊天、會議和靜音，或會議設為靜音，但可以取消靜音。 您也可以指定要撥號並加入緊急通話的使用者或群組的外部 PSTN 號碼。 請注意，PSTN 派對不允許取消靜音。

緊急通話原則可以授與 Teams 使用者帳戶、指派給網路網站或兩者。  當 Teams 用戶端啟動或變更網路連線時，Teams 會對用戶端所在的網路網站執行查閱：

- 如果緊急通話原則與網路網站相關聯，則會使用網站原則來設定安全性辦公桌通知。

- 如果沒有與網站相關聯的緊急通話原則，或是用戶端已連線到未定義的網站，則與使用者帳戶相關聯的緊急通話原則會用來設定安全性辦公桌通知。

- 如果 Teams 用戶端無法取得緊急通話原則，表示使用者未啟用安全性辦公桌通知。

在緊急通話期間，會在通話中加入一個安全性電話，而安全性中心使用者的體驗則是根據 Teams 緊急通話原則來控制。 每個安全性桌面成員都已開始進行群組聊天，而緊急來電者的位置會透過重要訊息通知分享。  如果會議選項已設定為原則的一部分，則每個安全性辦公桌使用者會在會議中另外被叫用。

### <a name="custom-emergency-disclaimer"></a>自訂緊急免責聲明

系統管理員能夠在租使用者中新增自訂橫幅，讓使用者啟用 E911。 使用者可以在確認其位址時關閉橫幅，當 Teams 重新開機時，橫幅會重新出現。 若要啟用這項功能，您需要在 Teams 緊急通話原則下設定緊急服務 **免責聲明** ，並輸入要向使用者顯示的字串訊息。 設定自訂原則時，此欄位為選用，且字串欄位限制為 250 個字元。

## <a name="related-topics"></a>相關主題

- [管理緊急電話原則](manage-emergency-calling-policies.md)
- [管理緊急通話路由原則 ](manage-emergency-call-routing-policies.md)
- [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)
- [指派或變更使用者的緊急位置](assign-change-emergency-location-user.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
