---
title: 使用電話系統進行通話方案服務決策-Microsoft 團隊
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/13/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 選擇 [通話方案和授權], 設定緊急位置和功能 (例如語音信箱和本機號碼)、取得或轉接電話號碼。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ddc618a4b68c8a620568eba5ae2ed52d17096b30
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233079"
---
# <a name="make-my-service-decisions"></a>進行我的服務決策

若要規劃電話系統與通話方案的技術實現, 您必須提前進行一系列的服務決策, 以進一步準備貴組織, 以完善符合您所定義之業務需求的方案。

## <a name="calling-in-teams"></a>在團隊中通話

透過 Microsoft 團隊, 您的使用者可以撥打或接聽公用交換電話網絡 (PSTN) 的電話。 您的使用者可以使用自己的專用電話號碼, 從團隊用戶端應用程式撥打及接聽國內和國際電話, 以及包含語音信箱的高級功能。

> [!NOTE]
> 您可以在<https://aka.ms/O365Roadmap>最新的小組藍圖中, 找出可在您的部署範圍內使用呼叫方案功能來識別小組電話系統。

## <a name="phone-system-in-teams"></a>小組中的電話系統

若要讓團隊使用者能夠撥打電話並接收 PSTN 通話, 必須在 Office 365 中啟用電話系統的功能。

若要啟用與 PSTN 的連線, 您的組織可以使用 Microsoft 作為其電訊服務提供者。 最後, 您也可以選擇「攜帶您自己的」電訊服務提供者, 以啟用到 PSTN 的電話系統連線。

> [!IMPORTANT]
> 您也可以使用 [手機系統直連路由], 將您自己的電話服務提供者與您的小組部署搭配使用。 若要深入瞭解直接路由, 請參閱[直接路由指導](2-envision-make-my-service-decisions-direct-routing.md)方針。

## <a name="phone-system-with-calling-plans"></a>含有通話方案的電話系統

若要使用 Microsoft 作為您的電訊服務提供者, 您必須取得通話方案授權, 並將他們指派給您的電話系統使用者。

通話方案有兩種主要類型:

-   國內通話方案

-   國內和國際通話方案

每個通話方案類型都會將特定數量的通話分鐘數指派給每個獲指派授權的使用者。 通話分鐘分配已耗盡時, 使用者將無法進行撥出通話, 除了緊急通話之外, 直到下個月的帳單週期。 如果您想要讓使用者在通話分鐘數已用盡時仍能繼續撥出或撥出電話, 或讓擁有國內通話方案的使用者撥打國際電話, 您可以為您的組織設定通訊點數。

<!--ENDOFSECTION-->

## <a name="availability-of-calling-plans"></a>通話方案的可用性

在您針對團隊中的通話方案進行規劃前, 請先查看適用[于音訊會議與通話方案的國家/地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md), 以確認您區域中的通話方案服務可供使用。

> [!IMPORTANT]
> 鑒於法律限制, 對於要提供給跨國公司的呼叫方案而言, Office 365 訂閱的合約必須是以可供使用通話方案服務的國家或地區為基礎, 或是呼叫方案服務可以在哪裡地點.

> [!NOTE]
> 如果您的區域不提供通話方案, 您可以使用 [[電話系統直接路由](2-envision-make-my-service-decisions-direct-routing.md)], 讓您的使用者能夠使用具有 PSTN 功能的團隊。

確認貴組織可以取得 [通話方案] 服務之後, 請根據可用國家和地區的清單, 將您要實施通話方案服務的使用者位置或辦公室的清單進行編譯。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您要在其中執行呼叫方案服務的使用者位置或辦公室。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄要為通話方案服務啟用的使用者位置或辦公室。</li></ul>|

> [!TIP]
> 以下是含有通話方案網站啟用清單的電話系統範例。
> 
> | **辦事處**                     | **位置**   | **電話系統服務** |
> |--------------------------------|----------------|--------------------------|
> | 單一 Epping 道路                | 澳大利亞      | 舊版 PSTN 服務 |
> | 100 Cyberport 公路             | 香港特別行政區  | 電話系統直向路由 |
> | 一個 Marina Boulevard           | 新加坡      | 電話系統直向路由 |
> | 32倫敦 Bridge 大街        | 英國 | 含有通話方案的電話系統 |
> | 39 quai du Président Roosevelt | 法國         | 含有通話方案的電話系統 |

<!--ENDOFSECTION-->

## <a name="phone-numbers-and-emergency-locations"></a>電話號碼和緊急位置

使用 Office 365 中的呼叫方案, 貴組織中的每位使用者都必須有一個獨特的直接撥出撥號 (已執行) 電話號碼, 以及對應的驗證緊急位址。 審查[管理雲端語音電話號碼](2-envision-make-my-service-decisions-phone-system.md#manage-cloud-voice-telephone-numbers), 為您的通話方案實施方案規劃電話號碼。

為通話方案設定電話號碼時, 您必須先將緊急位址指派給每個電話號碼, 然後才能指派號碼給使用者。 這是支援緊急通話所需的。 必須驗證緊急位址, 以確保緊急回應服務要使用的正確格式。

> [!IMPORTANT]
> 緊急服務通話在通話方案服務中的運作方式與傳統的電話語音不同。 您必須瞭解這些差異, 並將它們傳達給所有使用者, 這一點非常重要。 如需詳細資訊, 請參閱[緊急通話條款與條件](emergency-calling-terms-and-conditions.md)。

除了提供已驗證的緊急位址之外, 您還可以定義緊急位置, 並將它們與已驗證的緊急位址進行關聯, 以便在位址中提供更精確的位置。 緊急位置通常是使用者所處的建築物編號、樓層、建築物磚或辦公室號碼。

若要深入瞭解有關通話方案相關緊急位置的詳細資訊, 請參閱下列文章:

-   [什麼是緊急位置、位址及呼叫路由？](what-are-emergency-locations-addresses-and-call-routing.md)

-   [緊急通話條款與條件](emergency-calling-terms-and-conditions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>針對通話方案實現的範圍, 決定要針對使用者位置或辦公室收集緊急位置資訊的間隔。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>在通話方案實施的範圍內, 記錄每個使用者位置或 office 的詳細緊急位址及緊急位置。</li></ul>|

> [!TIP]
> 您可以使用下列範本來記錄電話號碼和緊急位置詳細資料的詳細資料。
> 
> |使用者名 |緊急位置與位址 |電話號碼 |
> |-----|-------------------------------|-------------|
> |Emily Braun |1034/32 倫敦 Bridge 大街、倫敦、SE1、英國 |+ 44 23 4567 8901 |
> |Lidia Holloway |1065/32 倫敦 Bridge 大街、倫敦、SE1、英國 |+ 44 23 4567 89112 |
> |港 Lahr |1023/32 倫敦 Bridge 大街、倫敦、SE1、英國 |+ 44 23 4567 8921 |
> |Marcel Beauchamp |07E15D/39 quai du Président Roosevelt, 92130 Issy-果-Moulineaux, 法國 | TBA |
> |Rachelle Cormier |07N15D/39 quai du Président Roosevelt, 92130 Issy-果-Moulineaux, 法國 | TBA |
> |Isabell Potvin |07F05E/39 quai du Président Roosevelt, 92130 Issy-果-Moulineaux, 法國 | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>語音信箱

雲端語音信箱 (由 Azure 語音信箱服務提供支援) 只支援將語音信箱存款至 Exchange 信箱, 且不支援協力廠商電子郵件系統。

根據預設, 雲端語音信箱可搭配 Exchange Online 使用;但它具有最低支援的 Exchange 內部部署版本和部署模型, 可讓您在內部部署 Exchange 部署中傳送語音信箱訊息給使用者信箱。

雲端語音信箱包括語音信箱, 預設會針對貴組織中的所有使用者啟用該功能。 您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。 如果您的組織決定要讓語音信箱保持啟用, 您也必須考慮語音信箱是否需要啟用猥褻遮罩。 如需詳細資訊, 請參閱[設定貴組織的語音信箱原則](set-up-phone-system-voicemail.md)。

>[!NOTE]
> 已實現回退機制, 讓雲端語音信箱可以使用 SMTP 重新傳送郵件, 這表示在協力廠商電子郵件系統上擁有信箱的使用者會收到其語音信箱訊息。 此機制不包括保證的服務正常運作時間或其他語音信箱功能, 例如變更語音信箱問候語。

如需手機系統實現中語音信箱的詳細資訊, 請參閱[使用通話方案的電話系統](calling-plan-landing-page.md)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定是否要在通話方案實現中啟用雲端語音信箱。</li><li>如果使用 Exchange 內部部署且您的現有部署不符合支援雲端語音信箱的需求, 請從可用的選項 ([升級及設定] 中選擇 [雲端語音信箱支援]、[遷移至 Exchange Online] 或 [利用回退])。先前所述的機制)。</li><li>決定是否要在整個組織或特定使用者中啟用或停用語音信箱或語音信箱。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>如果適用, 請將 Exchange 決策點記錄在支援雲端語音信箱。</li><li>如果您要啟用/停用語音信箱、語音信箱, 以及語音信箱只針對特定使用者提供猥褻遮罩, 請記錄該使用者清單。</li></ul>|

> [!TIP]
> 使用通話方案實現的電話系統的雲端語音信箱詳細資料, 可以記錄如下。
> 
> |使用者名 |Exchange 信箱 |啟用語音信箱嗎？ |語音信箱 |語音信箱的褻瀆遮罩 |
> |------------------|------------------|-------------------|----------|----------|
> |Emily Braun      |Online      |是的 |後 |後 |
> |Lidia Holloway   |Online      |是的 |後 |禁止 |
> |港 Lahr       |內部部署 |是的 |後 |後 |
> |Marcel Beauchamp |內部部署 |是的 |禁止 |N/A |
> |Rachelle Cormier |Online      |是的 |禁止 |N/A |
> |Isabell Potvin   |內部部署 |是的 |禁止 |N/A |

<!--ENDOFSECTION-->

## <a name="calling-identity"></a>通話身分識別

根據預設, 所有出站通話都會將指派的電話號碼做為呼叫身分識別 (來電者識別碼)。 通話的收件者可以快速識別來電者, 決定是否要接受或拒絕通話。 在某些情況下, 您可以使用 office 的主要電話號碼來遮罩本機號碼, 以保護呼叫者身分識別, 這通常是由自動語音應答設定所提供的服務號碼 (作為來電者識別碼), 或封鎖本機號碼[全部簡報]。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您的通話方案實現是否需要呼叫者識別碼操作。</li><li>如果適用的話, 決定要實施的呼叫者識別碼操作類型 (含服務號碼或 anonymize 的遮罩)。</li><li>如果適用的話, 請決定需要呼叫者識別碼處理的使用者, 以及要指派給每個使用者的呼叫者識別碼操作類型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將指派給使用者的呼叫者識別碼操作以及要指派的呼叫者 ID 操作類型記錄在檔中。</li></ul>|

> [!TIP]
> 下列是呼叫者 ID 遮罩詳細資料檔案的範例。
> 
> |使用者名  |啟用輸出來電者識別碼遮罩  |本機號碼遮罩類型  |允許使用者覆寫  | 啟用輸入來電者識別碼遮罩  |
> |---------|---------|---------|---------|---------|
> |Emily Braun|不|N/A|是的|不|
> |Lidia Holloway|是的|服務號碼 (OrgAA, + 44 20 7946 0000)|不|是的|
> |港 Lahr|不|N/A|是的|不|
> |Marcel Beauchamp|是的|服務號碼 (OrgAA、TBA)|不|是的|
> |Rachelle Cormier|是的|Anonymize|是的|不|
> |Isabell Potvin|是的|服務號碼 (OrgAA、TBA)|不|是的|

<!--ENDOFSECTION-->

## <a name="licensing-for-cloud-voice-capabilities"></a>雲端語音功能授權

音訊會議和電話系統是 Office 365 中的功能。 對於擁有 Office 365 E3 或 E1 訂閱者案的現有客戶, 他們可以以附加元件服務的方式另行授權;它們已包含在 Office 365 E5 訂閱者案中。

通話方案是 Office 365 中的電話系統功能附加元件, 因此您必須已啟用電話系統授權, 才能使用通話方案。

若要支援其他音訊會議和通話方案使用案例 (國際會議撥出、通話方案分鐘分配的外部呼叫已耗盡等等), 您可以為您的組織設定通訊點數。

## <a name="licensing-for-calling-plans"></a>撥號方案的授權

如果您的組織想要將 Microsoft 視為電訊服務提供者, 您必須取得適用于使用者業務需求的通話方案附加元件。 一般來說, 組織中的每個人都不需要撥打國際電話, 因此您可以為大多數使用者提供國內通話方案授權。

通話方案授權有兩種類型:

-   國內通話方案

-   國際與國內通話方案

> [!NOTE]
> 針對特定使用者所認為的 "國內" 是由使用者指派的 Office 365 使用位置所決定。

每個通話方案類型都提供使用者每月可使用的通話分鐘數, 以進行國內通話或國際通話。 國內通話方案與國際與國內通話方案相比成本較低。

針對個別使用者的業務需求訂閱及指派最合適的通話方案類型, 可協助貴組織控制其通話方案實施的成本。

針對每個 Office 365 租使用者, 加總的通話分鐘數會依國家或地區, 以及每個通話方案類型。 當您達到租使用者的每月通話分鐘數上限時, 通話方案服務 (除了緊急通話之外) 將會在月份剩餘部分暫停。 通話方案服務將會在下一個行事曆月的第一天自動繼續。

您可以設定貴組織的通訊點數, 讓使用者在撥出通話分鐘數之後撥出電話, 而不需等到下個月帳單週期。 此外, 通訊點數為指派國內通話方案的使用者提供撥打國際通話的能力, 然後使用「每分鐘付款」的模型來支付。

若要深入瞭解手機系統和通話方案, 請參閱下列文章:

-   [電話系統](https://products.office.com/en-us/skype-for-business/phone-system)

-   [通話方案](https://products.office.com/en-us/skype-for-business/calling-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>如果您的組織沒有必要的電話系統授權, 請決定是否要取得電話系統授權, 方法是逐步執行您現有的 Office 365 訂閱, 或購買 [電話系統] 附加元件服務。</li><li>決定哪些使用者需要國內通話方案授權, 且需要國內和國際電話方案授權。</li><li>針對您的通話方案實現, 決定您是否需要通訊點數。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄 [分部]、[部門]、[office] 或 [使用者群組] 您將指派電話系統授權給國內通話方案或國內與國際通話方案。</li></ul>|

> [!TIP]
> 您可以使用下列範例, 使用通話方案使用者來記錄電話系統的授權指派。
> 
> |使用者名 |辦事處 |Office 365 授權 |通話方案 |
> |----|----|----|----|
> |Emily Braun |32倫敦 Bridge 大街 |Office 365 E5 |國際與國內通話方案 |
> |Lidia Holloway |32倫敦 Bridge 大街 |Office 365 E5 |國內通話方案 |
> |港 Lahr |32倫敦 Bridge 大街 |Office 365 E5 |國內通話方案 |
> |Marcel Beauchamp |39 quai du Président Roosevelt |Office 365 E3, 電話系統附加元件 |國內通話方案 |
> |Rachelle Cormier |39 quai du Président Roosevelt |Office 365 E5 |國際與國內通話方案 |
> |Isabell Potvin |39 quai du Président Roosevelt |Office 365 E3, 電話系統附加元件 |國內通話方案 |

<!--ENDOFSECTION-->

## <a name="communications-credits"></a>通訊點數

您的使用者可以使用通訊點數從音訊會議會議撥出, 將其他人從世界各地 (在會議召集人的原產國之外) 新增給其他人。 您可以設定貴組織的通訊點數, 讓使用者在用盡通話分鐘數之後撥出來電, 而不需等到下個月的帳單週期。 此外, 通訊點數為指派給國內通話方案的使用者提供撥打國際通話的能力, 然後使用「每分鐘付款」的模型收取費用。

在實施通訊點數時, 第一個要考慮的事項是, 決定要購買的資金量。 如果您的組織選擇使用自動加值, 您將透過測量實際使用量來決定最佳金額。 監視您在一段時間內的通訊點數使用量, 並根據需要調整您的再充電金額。

針對您的通話方案實現, 您可以控制每個使用者的通訊點數的使用方式, 這可協助您確保您已將這些點數指派給您的業務需求。

若要深入瞭解通訊點數, 請參閱[通訊信用是什麼？](what-are-communications-credits.md)。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>針對您的音訊會議或通話方案實現, 決定您是否需要通訊點數。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄您要為其啟用通訊點數的 [分部]、[部門]、[office] 或 [使用者] 群組。</li><li>為您的音訊會議或通話方案實施記錄您的通訊點數規劃。</li></ul>|

> [!TIP]
> 您可以使用下列範例來記錄通話方案使用者的通訊點數指派清單。
> 
> |使用者名 |辦事處 |通話方案 |通訊點數 |
> |----|----|----|----|
> |Emily Braun |32倫敦 Bridge 大街 |國際與國內通話方案 |後 |
> |Lidia Holloway |32倫敦 Bridge 大街 |國內通話方案 |禁止 |
> |港 Lahr |32倫敦 Bridge 大街 |國內通話方案 |後 |
> |Marcel Beauchamp |39 quai du Président Roosevelt |國內通話方案 |禁止 |
> |Rachelle Cormier |39 quai du Président Roosevelt |國際與國內通話方案 |後 |
> |Isabell Potvin |39 quai du Président Roosevelt |國內通話方案 |禁止 |

<br>

> [!TIP]
> 您的通訊點數規劃號碼可能會有記錄, 如下列範例所示。
>
> |         |         |
> |---------|---------|
> |初始金額|$1000|
> |觸發金額|$400|
> |自動重新充電金額|TBA|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理雲端語音電話號碼

如果您是透過攜帶您自己的電訊服務提供者來實施電話系統, 電話號碼管理就會維持不變。

針對音訊會議和通話方案的實現, 您可以選擇取得新的電話號碼或轉移 (埠) 現有的電話號碼。

若要讓使用者以您習慣的方式撥打電話號碼 (例如忽略當地電話的區功能變數代碼、忽略國內通話的國家/地區碼), 或是在組織中執行會議撥出或呼叫其他使用者時使用短數位撥號嗎？您可以設定自訂的撥號方案並指派給使用者。

## <a name="acquire-new-telephone-numbers"></a>取得新的電話號碼

在 Microsoft 雲端語音解決方案中, 有兩種電話號碼類型:

-   訂閱者 (使用者) 編號, 可指派給您組織中的使用者。

-   服務號碼, 提供付費和免付費服務號碼 (其併發通話容量高於訂閱者號碼), 而且可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。

如需電話號碼類型的詳細資訊, 請參閱[通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)。

您可以取得的電話號碼總數, 取決於電話號碼類型, 以及您已購買並指派給使用者的授權數量。

如需您可以取得的電話號碼總計數的詳細資訊, 請參閱[您可以取得多少電話號碼？](how-many-phone-numbers-can-you-get.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定將從 Microsoft 取得新電話號碼的使用者位置或辦公室。</li><li>決定要從 Microsoft 取得的電話號碼類型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將從 Microsoft 取得新電話號碼的使用者位置或辦公室記錄在檔中。</li><li>檔要從 Microsoft 取得的電話號碼類型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>轉移現有的電話號碼

如果您的組織想要將現有的電話號碼轉移 (或埠) 至 Microsoft, 您可以透過將埠訂單要求提交給 Microsoft 來執行此動作。

您可以一次轉移所有現有的電話號碼 (完整埠), 並在部分市場中, 您可以轉移現有電話號碼的子集 (部分埠)。 部分埠在您只想要將使用者逐步移至使用通話方案的電話系統時可能會很有用。

單一端口順序只能將電話號碼轉移到單一電話號碼類型。 如果您需要將部分電話號碼作為訂閱者號碼或作為服務號碼的傳輸, 我們建議您先完成到 Microsoft 的轉移, 然後在 Microsoft 的控制中立即執行轉換。

或者, 您也可以一次提交多個埠要求、一個埠要求 (如果支援部分埠)。 不過, 這個替代方法會將您的合約延長到您現有的電訊服務提供者。

電話號碼移植是一個複雜的主題, 需要進行完整的規劃、協調及充分管理您的專案關係人預期。 若要深入瞭解, 請參閱下列文章:

-   [將電話號碼傳送到 Office 365](transfer-phone-numbers-to-office-365.md)

-   [傳送電話號碼常見問題](transferring-phone-numbers-common-questions.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定現有電話號碼會傳送至 Microsoft 的使用者位置或辦公室。</li><li>決定要傳送給 Microsoft 的電話號碼類型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將現有電話號碼傳送至 Microsoft 的使用者位置或辦公室記錄在檔中。</li><li>檔要傳送給 Microsoft 的電話號碼類型。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>撥號方案

Office 365 的 [電話系統] 功能中的撥號方案是一組正常化規則, 可將撥打的電話號碼轉換成替代格式 (通常是164個格式), 用於呼叫授權及呼叫路由。 音訊會議服務會利用電話系統所用的相同功能, 在會議撥出案例中轉譯撥打的電話號碼 (例如, 透過 PSTN 邀請參與者並撥回 [呼叫我] 功能)。

在 Office 365 的 [電話系統] 功能中, 有兩種類型的撥號方案:

-   [**服務撥號方案]:** 這是根據使用者的 Office 365 使用位置所套用的預設撥號計畫, 且無法加以修改。

-   **租使用者撥號方案:** 這是租使用者中可自訂的撥號方案, 會進一步分為兩種類型:

    -   **租使用者-全域撥號方案:** 套用至租使用者中所有使用者的撥號計畫。

    -   **租使用者撥號方案:** 僅適用于特定使用者的撥號方案。

指派給使用者的有效撥號方案是服務撥號方案 (根據使用者的 Office 365 使用位置) 與租使用者撥號方案 (可以是租使用者的全域撥號方案或租使用者撥號方案) 的組合。

![表格顯示三種服務與租使用者撥號方案組合。](media/audio_conferencing_image8.png "表格顯示三種服務與租使用者撥號方案組合。")

> [!IMPORTANT]
> 每個租使用者撥號方案中最多可以有25個正常化規則;因此, 請務必避免複製已提供給服務撥號方案中的正常化規則。

如需撥號方案的詳細資訊, 請參閱[什麼是撥號方案？](what-are-dial-plans.md)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您的組織是否需要自訂的撥號方案 (業務需求、採納需求等)。</li><li>如果適用, 請決定租使用者撥號方案 (租使用者或租使用者) 的範圍, 以支援您自訂撥號方案的需求。</li><li>如果適用, 請決定您要建立以支援雲端語音實現範圍內的使用者位置或分支機搆的租使用者撥號方案。</li><li>如果適用, 決定要為每位使用者指派自訂撥號方案和租使用者撥號計畫。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄自訂的撥號方案, 以及要設定為雲端語音實現中的相關正常化規則。</li><li>記錄指派自訂撥號方案的使用者, 以及要指派給每個使用者的租使用者撥號計畫。</li></ul>|

> [!TIP]
> 如果適用于您的專案, 您可以使用下列範本來記錄租使用者撥號方案設定。
> 
> |租使用者撥號方案名稱<br>_說明_  |正常化規則名稱<br>_說明_  |模式<br>翻譯<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_一 Epping 公路 Ryde, NSW, AU 撥號方案_|**AU-NSW-NorthRyde-OER-內部**<br>_一個 Epping 公路 office、北 Ryde、NSW、澳大利亞的內部號碼 (x7000-x7999)_|^ (7 \ d{3}) $<br>+ 6125550 $ 1<br>滿足|
> ||**AU-NSW-本機**<br>_NSW、澳大利亞的當地數位正常化_|^ ([2-9] \d{7}) $<br>+ 612 $ 1<br>虛假|
> ||**AU-TollFree**<br>_澳大利亞免付費電話號碼標準化_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $ 1<br>虛假|
> ||**AU-服務**<br>_澳大利亞服務號碼標準化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>虛假|
> |**SG-新加坡-OMB**<br>_OMB 新加坡, SG 撥號方案_|**SG-OMB-內部**<br>_OMB office、新加坡的內部號碼 (x8000-"x8999")_|^ (8 \ d{3}) $<br>+ 656888 $ 1<br>滿足|
> ||**SG-TollFree**<br>_適用于新加坡的免費電話號碼標準化_|^ (1？ 800 \ d{7}) \d * $<br>+ 65 $ 1<br>虛假|
> ||**SG 服務**<br>_適用于新加坡的服務號碼標準化_|^ (1 \ d{3,4}\|9 d{2}) $<br>$1<br>虛假|
> |**FR-巴黎-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-果-Moulineaux, 法國撥號方案_|**FR-39qdPR-內部**<br>_在 39 quai du Président Roosevelt office、Issy-果-Moulineaux、法國的內部號碼 (x7000-"x7999")_|^ (7 \ d{3}) $<br>+ 3319999 $ 1<br>滿足|
> ||**FR-TollFree**<br>_法國免付費電話號碼標準化_|^ 0？(80 \ d{7}) \d * $<br>+ 33 $ 1<br>虛假|
> ||**FR-服務**<br>_法國的服務編號正常化_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>虛假|

<br>

> [!TIP]
> 您可以利用下面的範例範本來記錄撥號計畫作業, 以支援您的專案:
>
> |使用者名  |辦事處  |撥號方案類型  |撥號方案名稱  |
> |---------|---------|---------|---------|
> |Adele Vance|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |立民 Wilber|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |Ben Walters|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |Christie Cline|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |Debra Berger|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |先生|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |Emily Braun|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |Lidia Holloway|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |港 Lahr|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>檔服務決策 

使用本文前幾節中的資訊來記錄您的服務決策。 一般來說, 本檔將包含下列主要章節:

-   含通話方案網站啟用清單的電話系統

-   使用通話方案使用者的電話系統授權指派

-   通訊點數規劃編號

-   電話號碼購置、電話號碼, 以及緊急位置詳細資料

-   語音信箱配置詳細資料

-   本機號碼遮罩配置詳細資料

-   租使用者撥號方案

-   撥號方案指派

<!--ENDOFSECTION-->