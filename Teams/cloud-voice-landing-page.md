---
title: 在 Microsoft Teams 中規劃語音解決方案
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
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: 深入瞭解 Microsoft Teams 雲端語音功能，以及您將為貴組織做出部署決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d77e0b1ec6277bfeffd85d6657d14fe810aae96
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102569"
---
# <a name="plan-your-teams-voice-solution"></a>規劃您的 Teams 語音解決方案 

本文可協助您決定適合貴組織的 Microsoft 語音解決方案。 在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。

> [!NOTE]
> 請參閱從商務用 Skype 內部部署升級至 Teams 的 [PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)考慮，以規劃 Teams 語音解決方案做為整體規劃的一部分。

您可能會想要最簡單的解決方案電話 &mdash; 系統與通話方案。 這是 Microsoft 的全雲端解決方案，提供私人分支 Exchange (PBX) 功能，以及撥打公用交換電話網絡 (PSTN) ，如下圖所示。 有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。

![圖表 1 顯示具有通話方案的電話系統](media/voice-solutions-simple.png)

如果您對下列專案回答是，則電話系統與通話方案是適合的解決方案：

- 地區提供通話方案。
- 您不需要保留目前的 PSTN 電信公司。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

不過，您的情況可能較為複雜。 例如，您可能在無法使用通話方案的位置有辦公室。 或者，您可能需要支援複雜、多國部署的組合解決方案，且不同的地理位置有不同的需求。 Microsoft 支援一組解決方案： 

- 具有通話方案的電話系統
- 具有您 PSTN 電信商的電話系統與直接路由
- 使用電話系統搭配通話方案與電話系統與直接路由的組合解決方案

## <a name="what-do-you-need-to-read"></a>您需要閱讀哪些資訊？

**全部為必填專案。** 本文中的部分章節與所有組織有關。 例如，每個人都應該閱讀電話系統，並瞭解在 PSTN (上連接公用電話) 。 


| 全部為必填專案 | 說明 |
| :------------|:-------|
| [**電話系統**](#phone-system) | Microsoft 在 Microsoft 365 雲端與 Microsoft Teams 中啟用通話控制和私人分支 Exchange (PBX) 功能的技術。 |
| [**公用交換電話網絡 (PSTN) 連接選項**](#public-switched-telephone-network-connectivity-options) | 選擇使用 Microsoft 做為電話電信業者，或使用直接路由將您自己的電話電信業者連接到 Microsoft Teams。 PSTN 連接選項與電話系統結合，可讓使用者撥打全球電話。|

**視您的需求而不同。** 本文中的部分章節會根據您的現有部署和需求而相關。 例如，Location-Based不允許免付費路的地理位置中的直接路由客戶，才需要直接路由。

請考慮您可能需要的這些額外配置：

![圖表 2 顯示其他語音元件，例如 Microsoft 的電話號碼、撥號方案及通話路由等。](media/voice-consider-additional-components.png)

| 視您的需求而不同 | 說明 |
| :------------|:-------|
| [**Microsoft 的電話號碼**](#phone-numbers-from-microsoft) | 如何取得和管理 Microsoft 的電話號碼，以及如何將現有的號碼移轉至 Microsoft。 如果您需要取得 Microsoft 通話方案的電話號碼、轉接現有號碼、取得服務號碼等，請閱讀本文。 |
| [**撥號方案與通話路由**](#dial-plans-and-call-routing) | 如何設定及管理撥號方案，將撥號電話號碼轉換成替代格式 (通常是 E.164 格式) 電話授權和呼叫路由。 如果您需要瞭解什麼是撥號方案，以及您是否需要為貴組織指定撥號方案，請閱讀本文。|
| [**緊急電話**](#emergency-calling) | 如何管理及設定緊急電話 &mdash; ，取決於您的 PSTN 連接選項。 如果您使用的是 Microsoft 通話方案或直接路由，並需要瞭解如何管理組織的緊急電話，請閱讀本節。 |
| [**直接路由的基於位置的路由**](#location-based-routing-for-direct-routing) |如何使用 Location-Based路由 (LBR) 根據 Microsoft Teams 使用者的地理位置來限制免付費。 如果貴組織在不允許免付費路的位置使用直接路由，請閱讀本節。
| [**雲端語音功能的網路拓撲**](#network-topology-for-voice-features) | 如果貴組織正在部署 Location-Based路由 (LBR) 直接路由或動態緊急電話，您必須設定網路設定，以用於 Microsoft Teams 中的這些功能。 如果您正針對直接路由執行 LBR，或是使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。 |
| [**遷移現有的語音解決方案**](#migrate-your-existing-voice-solution-to-teams) | 將語音解決方案移遷移到 Teams 時，您需要思考的問題。  如果您是從現有的語音解決方案移向 Teams，請閱讀本節。 



> [!Important]
> 本文著重于 Microsoft Teams 的語音解決方案。 雖然商務用 Skype Online 解決方案 (如 [Microsoft](/SkypeForBusiness/hybrid/msft-telephony-solutions) 電話解決方案) 所述，但必須瞭解商務用 Skype Online 將于 2021 年 7 月 31 日停用。  之後，商務用 Skype Online 服務將無法再使用。 此外，將不再支援內部部署環境之間的 PSTN 連線，無論是透過商務用 Skype Server 或雲端連接器版本，還是商務用 &mdash; &mdash; Skype Online。 本文將介紹 Teams 語音解決方案，以及如何在必要時使用直接路由將您的內部部署電話網路連接到 Teams。


## <a name="phone-system"></a>電話系統

電話系統是 Microsoft 使用 Microsoft Teams 在 Microsoft 365 或 Office 365 雲端中啟用通話控制和私人分支 exchange (PBX) 功能的技術。

電話系統可與 Teams 或商務用 Skype 用戶端及認證裝置一起運作。 電話系統可讓您以一組直接從 Microsoft 365 或 Office 365 提供的功能取代現有的 PBX 系統。 

貴組織使用者之間的通話在電話系統內部處理，而且永遠不會在 PSTN (電話) 。 這適用于貴組織中位於不同地理區域的使用者之間的通話，這可移除這些內部通話的長途費用。

本文將介紹下列電話系統的重要功能，以及您需要考慮的部署決策：

- [自動語音應答和通話佇列](#auto-attendants-and-call-queues)
- [雲端語音信箱](#cloud-voicemail)
- [通話身分識別](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別](media/phone-system-contains.png)

有關所有電話系統功能以及如何設定電話系統的資訊，請參閱下列文章：

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)
- [設定貴組織的 [電話系統]](setting-up-your-phone-system.md)<br>
  說明如何購買和指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊額度。 

有關管理支援裝置的資訊，請參閱在 [Microsoft Teams](devices/device-management.md) 和 Teams Marketplace 中管理 [您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。


### <a name="auto-attendants-and-call-queues"></a>自動電話機和通話佇列

自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。 通話佇列正在等待來電者的區域。 自動語音回應和通話佇列一起使用，可以輕鬆地將來電者路由至貴組織中適當的人員或部門。

有關自動電話機和通話佇列的資訊，請參閱下列文章：

- [規劃 Teams 自動電話機和通話佇列](plan-auto-attendant-call-queue.md)
- [設定自動話務員](create-a-phone-system-auto-attendant.md)
- [建立通話佇列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自動電話機和通話佇列](voice-case-study-call-queues.md)<br>
  說明一家虛構的多國公司 Contoso 如何實作自動語音語音和通話佇列，以尋求語音解決方案。

### <a name="cloud-voicemail"></a>雲端語音信箱

雲端語音信箱由 Azure 語音信箱服務提供，僅支援語音信箱存款至 Exchange 信箱。 它不支援協力廠商電子郵件系統。 

雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。 您的業務需求可能會要求您針對特定使用者或整個組織的每一個人停用語音信箱翻譯。

僅針對線上使用者，在指派使用者電話系統授權後，系統會自動為使用者設定和設定雲端語音信箱。 對於擁有 Exchange 信箱的電話系統使用者，您必須執行額外的組組步驟。 

有關雲端語音信箱及其組組的資訊，請參閱下列文章：

- [設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)
- [在組織中設定語音信箱政策](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>通話身分識別

根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。 來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。 有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱為使用者設定 [本機號碼](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用交換電話網路連接選項

電話系統為貴組織提供完整的 PBX 功能。 不過，若要讓使用者在組織外撥打電話，您必須將電話系統連接到公用交換電話網絡 (PSTN) 。 若要將電話系統連接到 PSTN，您可以選擇下列其中一個選項：

- [**電話系統與通話方案**](#phone-system-with-calling-plan)。 以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。

- [**使用自己的 PSTN 電信**](#phone-system-with-own-pstn-carrier-with-direct-routing) 公司電話系統，使用直接路由將您的內部部署環境連接到 Teams。

您也可以選擇選項群組合，以設計複雜環境的解決方案，或管理多步驟移 (移) 。

### <a name="phone-system-with-calling-plan"></a>具有通話方案的電話系統 

如本文先前所述，電話系統與通話方案是 Microsoft 針對 Teams 使用者的全雲端語音解決方案。 這是將 Microsoft Phone System 連接到公用交換電話網絡 (PSTN) 以啟用撥打全球有線電話和行動電話最簡單的選項。 有了這個選項，Microsoft (PBX) 私人分支 Exchange 功能，並做為您的 PSTN 電信公司，如下圖所示：

![圖表 4 顯示具有自動語音機、通話佇列、本機號碼等功能的電話系統，以及 Microsoft 作為 PSTN 電信業者](media/voice-solution-microsoft-complete.png)

如果您對下列專案回答是，則電話系統與通話方案是適合的解決方案：

- 地區提供通話方案。
- 您不需要保留目前的 PSTN 電信公司。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

使用此選項： 

- 您取得 Microsoft Phone 系統時，新增了國內或國際通話方案， (視全球授權服務等級) 。

- 由於通話方案在 &mdash; Microsoft 365 或 Office 365 外運作，因此不需要部署或維護內部部署。

- 注意：如有需要，您可以選擇透過直接路由連接支援的會話邊界控制器 (SBC) ，以與 SBC 支援的協力廠商 PBX、類比裝置和其他協力廠商電話設備進行互通性。

此選項需要不間斷地連接到 Microsoft 365 或 Office 365。

有關通話方案的資訊，請參閱下列文章：

- [哪一個通話方案適合您？](calling-plan-landing-page.md)
- [如何購買通話方案](calling-plans-for-office-365.md)
- [通話方案的適用國家與地區](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [設定通話方案](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>具有具有直接路由的 PSTN 電信公司的電話系統

此選項使用直接路由將 Microsoft Phone System 連接到您的電話網絡，如下圖所示： 

![圖表 5 顯示具有直接路由的電話系統](media/voice-solution-with-direct-routing.png)

如果您對下列問題回答是，則使用直接路由的電話系統是適合的解決方案：

- 您想要使用 Teams 與電話系統。
- 您需要保留目前的 PSTN 電信公司。
- 您想要混合路由，有些通話會透過通話方案進行，有些則透過您的電信公司進行。
- 您需要與協力廠商 PBX 和/或設備進行交互操作，例如架空傳呼機、類比裝置等。

使用此選項：

- 您將自己支援的 SBC 連接到 Microsoft Phone System，而不需要其他內部部署軟體。

- 您幾乎可以在 Microsoft Phone System 中使用幾乎任何電話電信業者。

- 您可以選擇設定及管理這個選項，也可以由您的電信公司或合作夥伴設定及管理 (詢問您的電信公司或合作夥伴是否提供此選項) 。

- 您可以設定電話設備之間的互通性，例如協力廠商 PBX 和類比裝置與 &mdash; Microsoft &mdash; Phone System。


此選項需要下列專案：

- 不間斷地連接到 Microsoft 365 或 Office 365。

- 部署及維護支援的 SBC。

- 與協力廠商電信公司簽訂合約。
   (除非已部署為選項，為使用通話方案的電話系統使用者提供協力廠商 PBX、類比裝置或其他電話設備) 

有關直接路由的資訊，請參閱下列文章：

- [電話系統直接路由](direct-routing-landing-page.md)
- [規劃直接路由](direct-routing-plan.md)
- [設定直接路由](direct-routing-configure.md)
- [管理語音路由策略，以用於直接路由](manage-voice-routing-policies.md)
- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [通過直接路由認證的工作階段邊界控制器清單](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Microsoft 的電話號碼

Microsoft 有兩種可用的電話號碼：訂閱者 *(* 使用者) 號碼，可指派給貴組織的使用者;以及服務號碼，以付費和免付費服務號碼提供。 服務號碼的並行通話容量高於訂閱者號碼，並可以指派給音訊會議、自動語音服務或通話佇列等服務。

您必須決定：

- 哪些使用者位置需要 Microsoft 的新電話號碼？
- 我需要哪一 (或服務) 電話號碼？ 
- 如何將現有的電話號碼移植到 Teams？

有關管理貴組織電話號碼 ，包括取得新號碼或移轉離職號碼等詳細資訊，請參閱下列文章：

- [管理貴組織的電話號碼](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [用於通話方案的各種電話號碼](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [為您的使用者取得電話號碼](getting-phone-numbers-for-your-users.md)
- [將電話號碼轉接至 Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>撥號方案與通話路由

撥號方案是一組將撥號電話號碼轉換成替代格式的標準化規則 (通常是 E.164 格式) 電話授權和呼叫路由。

您必須決定下列事項： 

- 我的組織需要自訂的撥號對應表？
- 哪些使用者需要自訂撥號方案？
- 應該為每個使用者指派哪一個租使用者撥號方案？

詳細資訊，請參閱下列文章： 

- [什麼是撥號對應表？](what-are-dial-plans.md)
- [規劃租使用者撥號方案](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [建立和管理撥號對應表](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>緊急電話

您設定緊急電話方式會根據您的 PSTN 連接選項而不同：Microsoft 通話方案或直接路由。 Microsoft 通話方案與電話系統直接路由的動態緊急電話提供設定及路由緊急電話的能力，並依據 Teams 用戶端的目前位置通知安全人員。 若要進一步瞭解緊急電話概念和術語，以及如何設定動態緊急電話，請參閱下列文章：

- [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md)
- [規劃和設定動態緊急電話](configure-dynamic-emergency-calling.md)
- [Contoso 案例研究：緊急電話](voice-case-study-emergency-calling.md)<br>
  說明一家虛構的多國公司 Contoso 如何為組織實作緊急電話。

## <a name="location-based-routing-for-direct-routing"></a>Location-Based直接路由的路由

在一些國家和地區，若要降低長途電話費用， (PSTN) 通電話網絡不合法。 Location-Based直接路由路由可讓您根據 Microsoft Teams 使用者的地理位置限制免付費路。 若要進一步瞭解如何規劃及設定 LBR Location-Based路由 (，請參閱) 文章：

- [規劃直接路由的依位置路由](location-based-routing-plan.md)
- [設定依位置路由的網路設定](location-based-routing-configure-network-settings.md)
- [啟用直接路由的依位置路由](location-based-routing-enable.md)
- [Contoso 案例研究：Location-Based路由](voice-case-study-location-based-routing.md)<br>
  說明一家虛構的多國公司 Contoso 如何為Location-Based路由實作。

## <a name="network-topology-for-voice-features"></a>語音功能的網路拓撲

如果您要部署動態緊急電話或直接路由Location-Based路由，您必須設定網路設定，以在 Microsoft Teams 中與這些功能一起使用。 若要瞭解如何設定網路區域、網路網站、網路子網和受信任的 IP 位址的網路設定，請參閱下列文章：

- [Microsoft Teams 中雲端語音功能的網路設定 - 概念和術語](cloud-voice-network-settings.md)
- [在 Microsoft Teams 中管理雲端語音功能的網路拓撲](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>將現有的語音解決方案遷移到 Teams

對於升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。 只有在使用者進入 TeamsOnly 模式時，才支援在 Teams 中使用電話系統。 如果您需要升級至 Teams 的基本資訊，請從這裡開始：

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [關於升級架構](upgrade-framework.md)
- [IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)

移移語音解決方案時，移至 TeamsOnly 模式時，有四種可能的通話案例：

- [**商務用 Skype Online 中的使用者，具有 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，該使用者會繼續擁有 Microsoft 通話方案。

- **[商務用 Skype Online](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 中的使用者，透過商務用 Skype 內部部署或雲端連接器版本提供內部部署語音功能。 使用者升級至 Teams 時，必須協調使用者的移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。

- **[商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** 內部部署與企業語音的使用者，將會移往線上並保持內部部署 PSTN 連線。 將此使用者移轉至 Teams，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 

- **[在商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 內部部署中使用企業語音的使用者，該使用者將會移往線上，並且使用 Microsoft 通話方案。  將該使用者移轉至 Teams 時，需要將使用者的內部部署商務用 Skype 帳戶移至雲端，並配合 A) 將該使用者電話號碼的埠移至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。

若要進一步瞭解如何針對這些案例執行語音移移，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移向直接路由的資訊，請參閱 &mdash; &mdash; 下列文章：

- [升級至 Teams 時 ，適用于 IT 系統管理員的 PSTN 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 語音移移案例研究](voice-case-study-overview.md)<br>
  案例研究說明虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案。 它包含下列文章：

  - [Teams 升級計畫](voice-case-study-migration-plan.md)
  - [電話系統與 PSTN 連接選項](voice-case-study-phone-system.md)
  - [位置式路由實現](voice-case-study-location-based-routing.md)
  - [緊急電話](voice-case-study-emergency-calling.md)
  - [自動語音應答和通話佇列](voice-case-study-call-queues.md)
  - [音訊會議](voice-case-study-audio-conferencing.md)