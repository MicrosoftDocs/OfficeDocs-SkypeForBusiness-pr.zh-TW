---
title: 撥打手機系統直通路線服務決策-Microsoft 團隊
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 07/09/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 瞭解直接路由、授權及需要進行的決定。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a2371c72f24b19b9e3c4fe836a59cbc800ad1c4
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/28/2019
ms.locfileid: "36181971"
---
# <a name="make-my-service-decisions"></a>進行我的服務決策

若要規劃手機系統 Direct 路由的技術實施 (「直接路由」), 您必須提前進行一系列的服務決策, 以進一步準備貴組織, 以符合您所定義的商業需求。

## <a name="calling-in-teams"></a>在團隊中通話

透過 Microsoft 團隊, 您的使用者可以撥打或接聽公用交換電話網絡 (PSTN) 的電話。 您的使用者可以使用自己的專用電話號碼, 從小組用戶端應用程式撥打及接聽國內和國際電話 (包括語音信箱)。

## <a name="direct-routing"></a>直接路由

若要讓團隊使用者能夠撥打電話並接收 PSTN 通話, 必須在 Office 365 中啟用電話系統的功能。

若要啟用 PSTN 連線, 您可以使用直接路由, 讓貴組織中的人員能夠透過 PSTN 撥打及接聽組織外部的電話撥打電話。

透過直接佈線, 由協力廠商提供的 PSTN 連線功能可讓您繼續使用 PSTN 服務提供者所提供的現有 PSTN trunks。 此功能可讓您在含有通話方案 ("通話方案") 的電話系統中, 或在已有的 PSTN 服務提供者合約需要維護或與特定內部部署系統進行互通性的部署中進行部署必填。

<!--ENDOFSECTION-->

## <a name="availability-of-direct-routing"></a>直接路由的可用性

您可以在 Office 365 的任何國家/地區取得直接傳送。 請參閱[國際可用性](https://products.office.com/business/international-availability), 取得這些國家/地區的清單。

確認貴組織可以取得電話系統功能之後, 請根據可用國家和地區的清單, 將您要實施電話系統的使用者位置或分支機搆的清單進行編譯。 此外, 還要找出您要為每個位置啟用通話方案或直接路由的使用者。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>找出您要在其中實施電話系統的使用者位置或辦公室。<li>針對您所擁有的每個位置, 找出您要為其啟用通話方案或直接傳送的使用者。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將啟用電話系統的使用者位置或辦公室記錄在檔中。<li>針對您要啟用呼叫方案或針對您所擁有的每個位置的直接傳送來記錄使用者清單</ul>|

> [!TIP]
> 以下是直接路由網站啟用清單的範例。
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

[電話系統] 需要貴組織中的每位使用者都有唯一的直向內撥號 (已撥) 電話號碼。 透過直接路由, 電話號碼和緊急服務是由您的 PSTN 服務提供者所提供。

> [!NOTE]
> 透過直接路由, 您的使用者可以繼續使用 PSTN 服務提供者所提供的電話號碼。
> 
> [!TIP]
> 您可以使用下列範本來記錄電話號碼的詳細資料。
> 
> |使用者名 |電話號碼 |
> |-----|-------------|
> |Emily Braun | + 44 23 4567 8901 |
> |Lidia Holloway | + 44 23 4567 89112 |
> |港 Lahr | + 44 23 4567 8921 |
> |Marcel Beauchamp | TBA |
> |Rachelle Cormier | TBA |
> |Isabell Potvin | TBA |

<!--ENDOFSECTION-->

## <a name="voicemail"></a>語音信箱

雲端語音信箱 (由 Azure 語音信箱服務提供支援) 只支援將語音信箱存款至 Exchange 信箱, 且不支援協力廠商電子郵件系統。

雲端語音信箱包括語音信箱, 預設會針對貴組織中的所有使用者啟用該功能。 您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。 如果您的組織決定將語音信箱保持在啟用狀態, 您也必須考慮是否要啟用語音信箱要求語言。 如需詳細資訊, 請參閱[設定貴組織的語音信箱原則](set-up-phone-system-voicemail.md)。

如需手機系統實現中語音信箱的詳細資訊, 請參閱[設定雲端語音信箱](set-up-phone-system-voicemail.md)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定是否要在直接路由實現中啟用雲端語音信箱。<li>決定是否要在整個組織或特定使用者中啟用或停用語音信箱或語音信箱。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>如果適用, 請將決策點記錄在支援雲端語音信箱。<li>如果您要啟用或停用語音信箱、語音信箱, 以及語音信箱只針對特定使用者提供猥褻遮罩, 請記錄該使用者清單。</ul>|

> [!TIP]
> [雲端語音信箱] 的詳細資料會記錄在下表中。
> 
> | **使用者名**         | **Exchange 信箱** | **啟用語音信箱嗎？** | **語音信箱** | **語音信箱的褻瀆遮罩** |
> |------------------|----------------------|-----------------------|-----------------------------|-----------------------------------------------|
> | Emily Braun      | Online               | 是的                   | 後                     | 後                                       |
> | Lidia Holloway   | Online               | 是的                   | 後                     | 禁止                                      |
> | 港 Lahr       | 內部部署          | 是的                   | 後                     | 後                                       |
> | Marcel Beauchamp | 內部部署          | 是的                   | 禁止                    | N/A                                           |
> | Rachelle Cormier | Online               | 是的                   | 禁止                    | N/A                                           |
> | Isabell Potvin   | 內部部署          | 是的                   | 禁止                    | N/A                                           |
> 
> [!NOTE]
> 若要使用團隊和語音信箱, 您的使用者必須擁有 Exchange 信箱。 如需更多詳細資料, 請參閱[Exchange 與 Microsoft 團隊的互動方式](exchange-teams-interact.md)。

<!--ENDOFSECTION-->

## <a name="licensing-for-direct-routing"></a>直接路由的授權

如果您的組織想要使用直接路由, 您必須取得所需的授權。 直接傳送的使用者必須具備下列 Office 365 中指派的授權:

-   Microsoft Phone 系統

-   Microsoft 團隊

-   音訊會議

若要將外部參與者加入排程的會議, 請撥打電話給他們, 或提供撥入號碼。 在撥出外部參與者之後, 音訊會議服務會使用線上呼叫功能來撥打通話。 [音訊會議授權] 是選擇性的, 而且只對將加入音訊會議的小組會議所需的使用者才是必要的。


> [!NOTE]
> 若要提供免付費的會議橋接電話號碼, 並支援會議撥出到國際電話號碼, 您應該為您的組織設定[通訊點數](what-are-communications-credits.md)。

音訊會議和電話系統可以為擁有 Office 365 E3 或 E1 訂閱者案之現有客戶的附加元件服務另行授權;它們已包含在 Office 365 E5 訂閱者案中。

> [!TIP]
> 您也可以在將呼叫安排傳送給協力廠商 Pbx 時, 針對啟用呼叫方案的使用者使用直接路由。 如需詳細資訊, 請參閱[直接路由的授權與其他需求](direct-routing-plan.md#licensing-and-other-requirements)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>如果您的組織沒有必要的電話系統授權, 請決定是否要取得電話系統授權, 方法是逐步執行您現有的 Office 365 訂閱, 或購買 [電話系統] 附加元件服務。<li>針對直接路由實現, 決定您是否需要通訊點數。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄 [分部]、[部門]、[office] 或 [使用者群組] 您將指派電話系統授權。<li>如果音訊會議有免付費電話號碼, 請記錄 [分部]、[部門]、[office] 或 [使用者群組], 您將會啟用通訊點數。</ul>|

<!--ENDOFSECTION-->

## <a name="office-365-considerations"></a>Office 365 考慮

任何將啟用直接路由的使用者, 都必須駐留在 Office 365 中。 針對使用內部部署商務用 Skype Server 或 Lync Server 的混合式部署, 您必須先將使用者移至商務用 Skype Online, 然後才能將其設定為搭配團隊直接傳送。

必須針對團隊啟用直接路由實施範圍中的所有使用者。

您必須在一或多個網域中啟用您的 Office 365 租使用者\*, 因為 onmicrosoft.com 網域無法與直接路由搭配使用。 如需網域和 Office 365 租使用者的詳細資訊, 請參閱[網域常見問題](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定是否任何使用者都需要遷移到商務用 Skype Online, 以支援直接傳送。<li>找出需要為團隊啟用的使用者。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄需要移至商務用 Skype Online 且可供團隊使用的使用者清單。</ul>|

<!--ENDOFSECTION-->

## <a name="sbc-considerations"></a>SBC 考慮

您需要使用經過驗證且支援的會話邊界控制器 (SBCs), 而這兩者必須要與直接路由服務配對, 為您的使用者提供 PSTN 連線能力。 如需已驗證的 SBCs 清單, 請參閱[支援的會話框線控制器](direct-routing-plan.md#supported-session-border-controllers-sbcs)。

視您的環境、位置數量及語音路由需求而定, 您可能需要部署多個 SBCs, 才能支援您的使用者基底。

### <a name="sbc-domain-names"></a>SBC 網功能變數名稱稱

您與直接路由配對的每個 SBC 都必須有唯一的 DNS 名稱。 SBC DNS 名稱必須來自于 Office 365 租使用者註冊的其中一個功能變數名稱。 如果您的租使用者已獲指派多個功能變數名稱, 您可以在規劃 SBCs 的 DNS 名稱時, 使用下列任何功能變數名稱。

> [!IMPORTANT]
> 不允許對 SBC DNS 名稱使用 *. onmicrosoft.com。

### <a name="certificates"></a>證書

使用直接路由部署的每個 SBC, 都需要從支援的認證頒發機構清單中取得的憑證。 憑證必須在 subject、subject 替換名稱或公用名稱欄位中包含 SBC DNS 名稱。

> [!NOTE]
> 也支援使用 SBCs 的萬用字元憑證。

如需詳細資訊以及支援的認證機構清單, 請參閱[適用于 SBC 的公用信任憑證](direct-routing-plan.md#public-trusted-certificate-for-the-sbc)。


### <a name="sbc-ip-addresses-and-ports"></a>SBC IP 位址與埠

每個 SBC 都必須使用可從 Office 365 資料中心存取的公用 IP 位址進行設定。 您也可以設定網路位址轉譯 (NAT), 將您的 SBCs 發佈至 Office 365 資料中心。

SBCs 需要雙向連線才能與雲端服務通訊以取得信號和媒體。 [發信號] 是由名為 [ *SIP Proxy*] 的元件處理, 媒體由*媒體處理器*來處理。

您必須在每個 SBC 上針對 SIP 信號和媒體定義特定的埠號碼, 並將您的防火牆設定為允許對這些埠及其相關 IP 位址進行雙向通訊。

如需詳細資訊, 請參閱[SIP 信號: fqdn 和防火牆埠](direct-routing-plan.md#sip-signaling-fqdns-and-firewall-ports)及[媒體流量: 埠範圍](direct-routing-plan.md#media-traffic-port-ranges)。


> [!NOTE]
> 我們強烈建議根據 SBC 模型, 為每個 SBC 設定最大併發會話限制。 這個限制會在 SBC 執行或接近其容量時觸發通知。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您要將半形部署到哪個位置。<li>針對您打算部署的每個 SBC, 決定一個 DNS 名稱。<li>根據 SBC 功能變數名稱決定, 決定您要使用萬用字元憑證來支援部署中的所有半形, 或每個 SBC 專用的憑證。<li>決定您要從哪個公用憑證授權單位取得您的 SBCs 證書。<li>針對您要部署的每個 SBC 定義公用 IP 位址/埠組, 並決定您是否要將公用 IP 位址指派給 SBCs 或使用 NAT。<li>找出每個 SBC 支援或可以處理的併發會話數目上限。<li>使用 [媒體旁路] 來決定要設定哪一個 SBCs。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>使用下列範例資料表, 將針對 SBCs 所做的每個決策進行檔記錄。</ul>|


> [!TIP]
> 使用下列範本來記錄直接路由部署的 SBC 詳細資料。
> 
> | **SBC DNS 名稱 (FQDN)** | **SBC 與模型** | **憑證** | **位置**  | **IP 位址** | **SIP 信號埠** | **NAT-T?** | **最大併發會話數** | **已啟用媒體旁路功能嗎？** |
> |-------------------------|------------------------|-----------------|---------------|----------------|------------------------|----------|-----------------------------|---------------------------|
> | SBC-Europe.contoso.com | TBD | \*. contoso.com | 阿姆斯特丹 | TBD | TBD | 是的 | TBD | 不 |
> | SBC-Asia.contoso.com | TBD | \*. contoso.com | 香港特別行政區 | TBD | TBD | 不 | TBD | 是的 |
> | SBC-Africa.contoso.com | TBD | \*. contoso.com | Johannesburg | TBD | TBD | 是的 | TBD | 是的 |

<!--ENDOFSECTION-->

## <a name="voice-routing"></a>語音路由

您需要設定 Microsoft Phone 系統, 以將呼叫路由到特定的 SBCs, 以進行直接路由。 您可以根據下列專案設定語音路由:

-   名為 [數位模式]。

-   呼叫數位模式 + 撥打電話的使用者。


[通話路由] 是由下列元素所組成:

-   語音路由策略– PSTN 用途的容器;可以指派給使用者或多位使用者

-   PSTN 用途–語音路由和 PSTN 用途的容器;可以在不同的語音路由策略中共用

-   語音路由-數位模式和一組線上 PSTN 閘道, 用於撥打電話號碼符合模式的呼叫

-   線上 PSTN 閘道-位於 SBC 的指標, 也會儲存透過 SBC 發出通話時所套用的設定, 例如轉寄 P 斷言身分識別 (PAI) 或首選編解碼器;可以新增到語音路由

您可以使用直接路由來設定語音路由, 以便與通話方案共存。 這項設定可讓通話方案使用直接路由, 將某些呼叫路由到特定的 SBCs。

> [!TIP]
> SBCs 可以指定為 [ ** 作用中] 和 [*備份*]。 這表示當被設定為適用于此數值模式的 SBC (或數位模式 + 特定使用者) 無法使用時, 會將呼叫路由至 backup SBC。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您要建立的語音路由策略、PSTN 使用及語音路由, 以便在直接路由實現的範圍內支援使用者位置或辦公室。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>為您的組織記錄語音路由策略、PSTN 用途及語音路線。<li>將指派給您所定義之每個語音路由策略的使用者記錄。</ul>|

> [!TIP]
> 使用下列範本來記錄直接路由部署的語音原則。
> 
> | **PSTN 使用量** | **語音路線** | **數位模式** | **優先順序** | **SBC** | **說明** |
> |----------------|-----------------|----------------------------|--------------|-----------------------------------|-----------------------------------------------------------------------------------------|
> | 僅限美國 | "雷德蒙 1" | \^\\+ 1 (425\|206) (\\d{7})\$ | sr-1 | sbc1.contoso.com sbc2.contoso.com | 呼叫號碼 + 1 425 XXX XX xx 美元或 + 1 206 XXX XX xx 的活動路由 |
> | 僅限美國 | "雷德蒙 2" | \^\\+ 1 (425\|206) (\\d{7})\$ | pplx-2 | sbc3.contoso.com sbc4.contoso.com | 呼叫號碼的備份路由 + 1 425 XXX XX XX or + 1 206 XXX XX xx |
> | 僅限美國 | "Other + 1" | \^\\+ 1 (\\d{10})\$ | 3 | sbc5.contoso.com sbc6.contoso.com | 呼叫號碼的路由 + 1 XXX XXX XXX xx (除 + 1 425 XXX XX 或 + 1 206 XXX XX xx 以外) |
> | 國際 | 國際 | \\d + | 4 | sbc2.contoso.com sbc5.contoso.com | 任何數位模式的路線 |
> 
> [!IMPORTANT]
> 語音路由策略中的 PSTN 用法會依順序套用, 如果在第一次使用中發現相符, 就不會評估其他用法。

<!--ENDOFSECTION-->

## <a name="calling-and-interop-policies"></a>通話和交互操作原則

只有 Microsoft 團隊支援直接傳送。 若要透過直接佈線來撥打或接聽 PSTN 電話, 您必須設定必要的原則, 以確保在團隊中接收來電。

> [!NOTE]
> 啟用直接路由的使用者無法使用商務用 Skype 來放置或接收直接路由呼叫, 因此必須部署團隊用戶端。

您可以使用下列兩種方法的其中一種, 設定您的使用者將團隊設為其首選用戶端通話:

-   針對僅限團隊模式設定使用者

-   指派 TeamsCallingPolicy 和 TeamsInteropPolicy, 將團隊設定為首選的呼叫用戶端。

如需詳細資訊, 請參閱[將 Microsoft 團隊設定為使用者的首選呼叫用戶端](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users)。


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您要使用哪種方法將團隊設定為 [呼叫的首選用戶端]。</ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將使用者設定為使用互通性和呼叫原則進行設定。</ul>|

> [!IMPORTANT]
> 當使用者設定為 [僅限團隊] 模式時, 此使用者就無法再登入商務用 Skype。

若要讓您的使用者在團隊用戶端中看到 [通話] 索引標籤, 您必須在租使用者的組織層級啟用私人通話。 如需如何啟用私人通話的詳細資訊, 請參閱[啟用 Microsoft 團隊通話](direct-routing-configure.md)。


<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>檔服務決策

使用本文前幾節中的資訊來記錄您的服務決策。 一般來說, 本檔將包含下列主要章節:

-   含通話方案網站啟用清單的電話系統

-   語音信箱配置詳細資料

-   電話系統直接路由使用者的授權指派

-   SBC 配置詳細資料

-   語音路由策略與路由詳細資料

-   互通性與通話原則詳細資料

<!--ENDOFSECTION-->
