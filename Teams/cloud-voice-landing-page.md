---
title: 規劃 Microsoft 團隊的語音方案
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 深入瞭解 Microsoft 團隊雲端語音功能，以及您將針對貴組織所做的部署決定。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 213950b808d781e8566e1ffae6f6075bb7b3371b
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686449"
---
# <a name="plan-your-teams-voice-solution"></a>規劃您的小組語音方案 

本文可協助您決定哪一種 Microsoft 語音解決方案適合您的組織。 決定之後，本文會提供內容的藍圖，讓您能夠實施您所選的方案。

> [!NOTE]
> 如需規劃團隊語音方案的相關指導方針，以將其從商務用 Skype Server 升級至團隊的整體方案，請參閱 [從商務用 skype 內部部署升級至團隊的 PSTN 考慮](upgrade-to-Teams-on-prem-pstn-considerations.md)。

您可能想要最簡單的解決方案 &mdash; 電話系統使用通話方案。 這是 Microsoft 的雲端解決方案，可提供私人分支 Exchange (PBX) 功能，以及呼叫公用交換電話網絡 (PSTN) ，如下列圖表所示。 在這個方案中，Microsoft 是您 PSTN 運營商。

![圖表1顯示含有通話方案的電話系統](media/voice-solutions-simple.png)

如果您對下列專案回答 [是]，就表示您可以使用 [電話撥入方案] 作為正確的方案：

- 您的地區提供通話方案。
- 您不需要保留目前的 PSTN 載波。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

不過，您的情況可能會更複雜一些。 例如，您可能在無法使用通話方案的位置中有辦事處。 或者，您可能需要一個支援複雜的多國部署的組合解決方案，且不同地理位置的需求不同。 Microsoft 支援解決方案組合： 

- 含有通話方案的電話系統
- 含直接佈線的電話系統與您自己的 PSTN 載波
- 結合直接佈線，搭配通話方案和電話系統使用電話系統的組合方案

## <a name="what-do-you-need-to-read"></a>您需要閱讀什麼？

**全是必要的。** 本文中的部分內容適用于所有組織。 例如，所有人都應該閱讀有關電話系統的資訊，並瞭解連線至公用交換電話網絡 (PSTN) 的選項。 


| 全部需要 | 說明 |
| :------------|:-------|
| [**電話系統**](#phone-system) | Microsoft 365 雲端與 Microsoft 團隊一起啟用呼叫控制和私人分支 Exchange (PBX) 功能的 Microsoft 技術。 |
| [**公用交換電話網絡 (PSTN) 連接選項**](#public-switched-telephone-network-connectivity-options) | 您可以選擇使用 Microsoft 作為電話運營商，或使用直接路由將您自己的電話運營商連線至 Microsoft 團隊。 與電話系統搭配使用 PSTN 連線選項，讓您的使用者能夠撥打世界各地的電話。|

**視您的需求而定。** 本文中的部分章節是根據您現有的部署與需求而相關。 例如，只有在地理位置不允許使用 [免付費旁路] 的直接路由客戶才需要 Location-Based 傳送。

考慮您可能需要下列哪些其他設定：

![圖2顯示其他語音元件，例如 Microsoft 的電話號碼、撥號方案和通話路由等。](media/voice-consider-additional-components.png)

| 視您的需求而定 | 說明 |
| :------------|:-------|
| [**Microsoft 的電話號碼**](#phone-numbers-from-microsoft) | 如何從 Microsoft 取得及管理電話號碼，以及如何將現有號碼轉移至 Microsoft。 如果您需要取得 Microsoft 通話方案的電話號碼、轉移現有號碼、取得服務號碼等，請閱讀這種情況。 |
| [**撥號方案和呼叫路由**](#dial-plans-and-call-routing) | 如何設定和管理可將撥打的電話號碼轉換成替代格式的撥號方案 (通常是) 的撥號驗證及呼叫路由的 E. 164 格式。 如果您需要瞭解什麼是撥號方案，以及是否需要指定貴組織的撥號方案，請閱讀此資訊。|
| [**緊急通話**](#emergency-calling) | 如何管理和設定緊急呼叫， &mdash; 視 PSTN 連接選項而定。 如果您使用的是 Microsoft 通話方案或直接傳送，且需要瞭解如何管理組織的緊急通話，請閱讀本節。 |
| [**直接路由的以位置為基礎的路由**](#location-based-routing-for-direct-routing) |如何使用 Location-Based 路由 (LBR) 根據其地理位置來限制 Microsoft 團隊使用者的付費略過。 如果您的組織在不允許使用 [免付費旁路] 的位置使用直接路由，請閱讀本節內容。
| [**雲端語音功能的網路拓撲**](#network-topology-for-voice-features) | 如果您的組織是部署 Location-Based 路由 (LBR) 進行直接路由或動態緊急通話，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。 如果您要實現直接路由的 LBR，或者如果您是使用通話方案或直接路由來執行動態緊急通話，請閱讀本節。 |
| [**遷移現有的語音解決方案**](#migrate-your-existing-voice-solution-to-teams) | 將您的語音解決方案遷移至小組時，需要考慮的事項。  如果您是從現有的語音解決方案遷移至小組，請閱讀本節內容。 



> [!Important]
> 本文主要針對 Microsoft 團隊提供的語音方案。 雖然 [Microsoft 電話) 解決方案](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) 中的商務用 Skype online 方案仍提供 (，但請務必瞭解2021年7月31日的商務用 skype online 將會停用。  在該日期之後，商務用 Skype Online 服務將無法再存取。 此外， &mdash; 不論是透過商務用 Skype 伺服器或雲端連接器版本及商務用 Skype Online，您的內部部署環境之間的 PSTN &mdash; 連線都將不再受支援。 本文將說明團隊語音方案，以及如何使用直接路由將內部部署電話網絡（如有必要）連線至團隊。


## <a name="phone-system"></a>電話系統

[電話系統] 是 Microsoft 的技術，可讓您在 Microsoft 365 或 Office 365 雲端中使用 microsoft 團隊來啟用呼叫控制和私人分支 Exchange (PBX) 功能。

[電話系統] 可與團隊或商務用 Skype 用戶端和認證的裝置搭配使用。 [電話系統] 可讓您以從 Microsoft 365 或 Office 365 直接提供的一組功能取代現有的 PBX 系統。 

貴組織中的使用者之間的呼叫是在手機系統內內部處理，而不會移至公用的交換電話網絡 (PSTN) 。 這適用于您組織中位於不同地理區域的使用者之間的通話，並移除這些內部通話的長途成本。

本文將介紹下列電話系統金鑰功能與功能，以及您必須考慮的部署決定：

- [自動語音應答和通話佇列](#auto-attendants-and-call-queues)
- [雲端語音信箱](#cloud-voicemail)
- [通話身分識別](#calling-identity)

![圖表3顯示手機系統包含自動語音應答及呼叫查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

如需所有電話系統功能的相關資訊，以及如何設定電話系統，請參閱下列文章：

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)
- [在組織中設定電話系統](setting-up-your-phone-system.md)<br>
  說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費電話號碼的通訊點數。 

如需管理支援的裝置的相關資訊，請參閱在 Microsoft 團隊和[小組 Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[中管理您的裝置](devices/device-management.md)。


### <a name="auto-attendants-and-call-queues"></a>自動語音應答及呼叫佇列

自動語音應答可讓您根據本機號碼來設定功能表選項，以路由通話。 通話佇列是呼叫者的等待區域。 [自動語音應答] 和 [呼叫佇列] 可搭配使用，輕鬆地將呼叫者路由至組織中的適當人員或部門。

如需自動語音應答和通話佇列的相關資訊，請參閱下列文章：

- [規劃小組自動語音應答及呼叫佇列](plan-auto-attendant-call-queue.md)
- [設定自動語音應答](create-a-phone-system-auto-attendant.md)
- [建立通話佇列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自動語音應答及呼叫佇列](voice-case-study-call-queues.md)<br>
  說明虛構的多國企業（Contoso）如何針對其語音方案實施自動語音應答及呼叫佇列。

### <a name="cloud-voicemail"></a>雲端語音信箱

雲端語音信箱（由 Azure 語音信箱服務提供技術支援）只支援在 Exchange 信箱中存款語音信箱。 它不支援協力廠商電子郵件系統。 

雲端語音信箱包括語音信箱，預設會針對貴組織中的所有使用者啟用該功能。 您的公司需求可能需要您針對特定使用者或整個組織中的所有人停用語音信箱。

針對僅限線上使用者，在指派電話系統授權之後，系統會自動為使用者設定及設定雲端語音信箱。 針對有 Exchange 信箱的電話系統使用者，您需要執行額外的設定步驟。 

如需有關雲端語音信箱及其設定的詳細資訊，請參閱下列文章：

- [設定雲端語音信箱](set-up-phone-system-voicemail.md)
- [在組織中設定語音信箱原則](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>通話身分識別

根據預設，所有的呼出通話會使用指派的電話號碼來呼叫身分識別 (來電者識別碼) 。 通話的收件者可以快速識別來電者，決定是否要接受或拒絕通話。 如需設定本機號碼或變更或封鎖本機號碼的相關資訊，請參閱 [設定使用者的本機號碼](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用交換電話網路連接選項

電話系統為您的組織提供完整的 PBX 功能。 不過，若要讓使用者撥打貴組織外的通話，您必須將電話系統連線至公用的交換電話網絡 (PSTN) 。 若要將電話系統連線至 PSTN，您可以選擇下列其中一個選項：

- [**含有通話方案的電話系統**](#phone-system-with-calling-plan)。 以 Microsoft 作為 PSTN 運營商的一體式雲端解決方案。

- 使用直接路由將內部部署環境連接至團隊的 [**電話系統（含您自己的 PSTN 載波）**](#phone-system-with-own-pstn-carrier-with-direct-routing) 。

您也可以選擇組合選項，讓您設計複雜環境的解決方案，或管理多重步驟的遷移 (稍後) 的其他遷移。

### <a name="phone-system-with-calling-plan"></a>含有通話方案的電話系統 

如本文先前所述，使用通話方案的電話系統是適用于團隊使用者的 Microsoft 的雲端語音方案。 這是最簡單的選項，可將 Microsoft 手機系統連線到公開交換的電話網絡 (PSTN) ，以讓世界各地的電話與行動裝置市話。 透過此選項，Microsoft 可為您的組織提供私人分支 Exchange (PBX) 功能，並充當 PSTN 運營商，如下列圖表所示：

![圖表4顯示含自動語音應答、通話佇列、本機號碼等等，以及 Microsoft 作為 PSTN 載波的電話系統](media/voice-solution-microsoft-complete.png)

如果您對下列專案回答 [是]，就表示您可以使用 [電話撥入方案] 作為正確的方案：

- 您的地區提供通話方案。
- 您不需要保留目前的 PSTN 載波。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

使用此選項： 

- 您可以在 Microsoft 手機系統隨附新增國內或國際通話方案（可讓世界各地的電話撥打電話） (，視授權) 的服務等級而定。

- 您不需要部署或維護內部部署的部署， &mdash; 因為通話方案不會在 Microsoft 365 或 Office 365 上運作。

- 注意：如有必要，您可以選擇將受支援的會話邊界控制器 (SBC) ，透過直接路由取得與 SBC 所支援的協力廠商 Pbx、類比裝置及其他協力廠商電話裝置的互通性。

此選項需要不間斷地連線至 Microsoft 365 或 Office 365。

如需通話方案的詳細資訊，請參閱下列文章：

- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [如何購買通話方案](calling-plans-for-office-365.md)
- [通話方案的適用國家與地區](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [設定通話方案](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>含直接佈線的有自己 PSTN 載波的電話系統

此選項使用直接路由將 Microsoft Phone 系統連線到電話網絡，如下列圖表所示： 

![圖表5顯示含直接路由的電話系統](media/voice-solution-with-direct-routing.png)

如果您對下列問題回答 [是]，則使用直接路由的電話系統就是適合您的解決方案：

- 您想要將團隊與電話系統搭配使用。
- 您必須保留目前的 PSTN 載波。
- 您想要混合路由，有些呼叫是透過通話方案進行，有些是透過您的運營商進行。
- 您必須與協力廠商的 Pbx 和/或裝置進行交互操作，例如，我們的系統開銷呼叫器、類比裝置等。

使用此選項：

- 您可以將自己的支援 SBC 連接到 Microsoft Phone System，而不需要額外的內部部署軟體。

- 您幾乎可以在 Microsoft Phone 系統中使用任何電話運營商。

- 您可以選擇設定和管理此選項，或由您的運營商或合作夥伴 (詢問您的承運人或合作夥伴是否提供此選項) 。

- 您可以設定您的電話裝置 &mdash; （例如協力廠商 PBX 和模擬裝置 &mdash; 與 Microsoft Phone 系統）之間的互通性。


此選項需要下列各項：

- 無法中斷連接至 Microsoft 365 或 Office 365。

- 部署及維護支援的 SBC。

- 含協力廠商承運人的合同。
   (除非部署為選項，才能為使用通話方案的電話系統上的使用者提供與協力廠商 PBX、類比裝置或其他電話裝置的連線。 ) 

如需直接路由的詳細資訊，請參閱下列文章：

- [電話系統直接路由](direct-routing-landing-page.md)
- [規劃直接路由](direct-routing-plan.md)
- [設定直接路由](direct-routing-configure.md)
- [管理與直接路由搭配使用的語音路由策略](manage-voice-routing-policies.md)
- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Microsoft 的電話號碼

Microsoft 提供兩種電話號碼類型： *訂閱者* (使用者) 號碼，您可以將其指派給組織中的使用者，也可以指派 *服務* 號碼，提供付費和免付費服務號碼。 服務號碼的併發通話容量高於訂閱者號碼，而且可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。

您將需要決定：

- 哪些使用者位置需要來自 Microsoft 的新電話號碼？
-  (訂閱者或服務) 需要哪種電話號碼？ 
- 我要如何將現有的電話號碼移植至團隊？

如需在組織中管理電話號碼的詳細資訊，包括取得新號碼或轉接現有號碼，請參閱下列文章：

- [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [通話方案所用的不同類型的電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [為您的使用者取得電話號碼](getting-phone-numbers-for-your-users.md)
- [將電話號碼轉移至 Microsoft 團隊](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>撥號方案和呼叫路由

撥號方案是一組正常化規則，將撥打的電話號碼轉換成替換格式， (通常是) 的 E. 164 個格式，用於呼叫授權及呼叫路由。

您必須決定下列事項： 

- 我的組織需要自訂的撥號對應表？
- 哪些使用者需要自訂的撥號方案？
- 應該將哪個租使用者撥號方案指派給每個使用者？

如需詳細資訊，請參閱下列文章： 

- [什麼是撥號對應表？](what-are-dial-plans.md)
- [規劃租使用者撥號方案](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [建立和管理撥號對應表](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>緊急電話

您設定緊急呼叫的方式會根據 PSTN 連線選項而有所不同： Microsoft 通話方案或直接傳送。 Microsoft 通話方案和電話系統直連路由的動態緊急通話可提供設定及路由緊急通話的功能，並根據團隊用戶端的目前位置來通知安全人員。 如需緊急呼叫概念與術語的詳細資訊，以及如何設定動態緊急通話，請參閱下列文章：

- [管理緊急通話](what-are-emergency-locations-addresses-and-call-routing.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
- [Contoso 案例研究：緊急通話](voice-case-study-emergency-calling.md)<br>
  說明虛構的多國企業（Contoso）如何針對其組織實現緊急通話。

## <a name="location-based-routing-for-direct-routing"></a>直接路由 Location-Based 路由

在某些國家和地區，不一定要略過公開交換的電話網絡 (PSTN) 提供者來減少長途通話成本。 [Location-Based 傳送直接路由功能] 可讓您根據地理位置限制 Microsoft 團隊使用者的付費略過。 如需如何規劃及設定 Location-Based 路由 (LBR) 的詳細資訊，請參閱下列文章：

- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [設定依位置路由的網路設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [Contoso 案例研究： Location-Based 路由](voice-case-study-location-based-routing.md)<br>
  說明虛構的多國企業（Contoso）如何針對其組織實施 Location-Based 路由。

## <a name="network-topology-for-voice-features"></a>語音功能的網路拓撲

如果您要部署動態緊急通話或 Location-Based 路由以進行直接路由，您必須設定網路設定，以便與 Microsoft 團隊中的這些功能搭配使用。 若要瞭解如何設定網路區域、網路網站、網路子網和信任的 IP 位址的網路設定，請參閱下列文章：

- [Microsoft 團隊中雲端語音功能的網路設定-概念與術語](cloud-voice-network-settings.md)
- [在 Microsoft 團隊中管理雲端語音功能的網路拓撲](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>將現有的語音解決方案遷移至團隊

針對升級至團隊的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。 只有在使用者處於 TeamsOnly 模式時，才會支援將電話系統與團隊一起使用。 如果您需要升級至團隊的基本資訊，請從這裡開始：

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [關於升級架構](upgrade-framework.md)
- [從商務用 Skype 升級至團隊-適用于 IT 系統管理員](upgrade-to-teams-on-prem-overview.md)

當您遷移您的語音解決方案時，當您移至 TeamsOnly 模式時，可能會有四個通話案例：

- [**商務用 Skype Online 中的使用者，包含 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升級時，此使用者將會繼續進行 Microsoft 通話計畫。

- **[商務用 skype Online 中的使用者，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) 可透過商務用 skype 內部部署或雲端連接器版本使用內部部署語音功能**。 使用者在小組中的升級需要與使用者遷移以直接傳送路由，以確保 TeamsOnly 使用者有 PSTN 功能。

- **[在商務用 Skype 內部部署中使用企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，他們將會移至線上並保留內部部署 PSTN 連線**。 將此使用者遷移至團隊需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將使用者的遷移轉移至直接傳送路線。 

- **[在商務用 Skype 內部部署中使用企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，他們將會移至線上並使用 Microsoft 通話方案**。  將此使用者遷移至小組需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並將該使用者電話號碼的埠與) 的埠進行協調，) 從可用的地區指派新的訂閱者號碼。

如需如何針對這些案例實施語音遷移的詳細資訊 &mdash; ，包括您需要設定混合式連線的相關資訊，以及如何使用內部部署語音功能將使用者遷移至直接佈線， &mdash; 請參閱下列文章：

- [升級至小組所需的 PSTN 考慮-適用于 IT 系統管理員](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 語音遷移案例研究](voice-case-study-overview.md)<br>
  案例研究說明虛構的多國公司（Contoso）如何針對其組織實施小組語音方案。 它包含下列文章：

  - [團隊升級方案](voice-case-study-migration-plan.md)
  - [電話系統和 PSTN 連線選項](voice-case-study-phone-system.md)
  - [以位置為基礎的路由實施](voice-case-study-location-based-routing.md)
  - [緊急通話](voice-case-study-emergency-calling.md)
  - [自動語音應答和通話佇列](voice-case-study-call-queues.md)
  - [音訊會議](voice-case-study-audio-conferencing.md)












