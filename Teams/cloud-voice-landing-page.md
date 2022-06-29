---
title: 在 Microsoft Teams 中規劃您的語音解決方案
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
description: 深入瞭解 Microsoft Teams 雲端語音功能，以及您為組織做出的部署決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b1f4b0756e640d9b93e235b2724ce7841b4f44f
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240822"
---
# <a name="plan-your-teams-voice-solution"></a>規劃您的 Teams 語音解決方案

本文可協助您決定哪個 Microsoft 語音解決方案適合您的組織。 在您決定之後，本文會提供可讓您實作所選解決方案的內容藍圖。

您可能會想要電話系統與通話方案最簡單的解決方案 &mdash; 。 此選項是 Microsoft 的全雲解決方案，提供 Private Branch Exchange (PBX) 功能，以及呼叫公用交換電話網路 (PSTN) ，如下圖所示。 透過此解決方案，Microsoft 是您的 PSTN 電信業者。

![圖表 1 顯示電話系統與通話方案。](media/voice-solutions-simple.png)

如果您對下列事項回答「是」，則「電話系統與通話方案」是適合您的解決方案：

- 您所在的地區可使用通話方案。
- 您不需要保留目前的 PSTN 電信業者。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

不過，您的情況可能較為複雜。 例如，您可能會在無法使用通話方案的位置設立辦公室。 或者，您可能需要支援複雜、多國部署的組合解決方案，針對不同的地理位置提供不同的需求。 Microsoft 支援一系列解決方案：

- 電話系統與通話方案
- 與您自己的 PSTN 電信業者搭配運算子連線的電話系統
- 電話系統與您自己的 PSTN 電信業者搭配直接路由
- 搭配通話方案使用電話系統、電話系統搭配運算子連線，以及/或電話系統搭配直接路由的組合解決方案

如需所有語音解決方案選項的視覺摘要，請參閱語音解決方案海報。

[![Microsoft Voice Solutions 海報。](media/microsoft-voice-solutions-thumb.png)](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br> [PDF](https://download.microsoft.com/download/4/3/5/435cd4e9-ca56-4fd1-acb6-d1fda7952320/microsoft-voice-solutions.pdf) <br>[Visio](https://download.microsoft.com/download/7/5/c/75c13012-e20c-48bd-a6dd-ea49d1a3420d/microsoft-voice-solutions.vsdx) 
<br>

>[!NOTE]
>如果您是中小型企業 (300 人或以下) ，Microsoft 現在會將電話系統與國內通話方案搭售。 如需詳細資訊，請參閱 [適用于中小型企業的電話系統指導方針](/microsoftteams/business-voice/whats-business-voice) ，以協助您規劃、設定和管理語音解決方案。

## <a name="what-do-you-need-to-read"></a>您需要閱讀什麼？

**這是所有人的必要專案。** 本文中的部分章節與所有組織有關。 例如，每個人都應該閱讀電話系統，並瞭解連線到公用交換電話網路 (PSTN) 選項。


| 適用于所有 | 描述 |
| :------------|:-------|
| [**電話系統**](#phone-system) | Microsoft 在 Microsoft 365 雲端使用 Microsoft Teams 啟用通話控制和專用 Exchange (PBX) 功能的技術。 |
| [**公用交換電話網路 (PSTN) 連線選項**](#public-switched-telephone-network-connectivity-options) | 選擇 Microsoft 做為您的電話語音電信業者，或使用運算子連線或直接路由，將您自己的電話語音電信業者連線到 Microsoft Teams。 結合電話系統，PSTN 連線選項可讓您的使用者撥打世界各地的電話。|

**視您的需求而定。** 根據您現有的部署和需求，本文章和相關文章中的部分章節是相關的。 例如，只有在地理位置不允許略過付費的直接路由客戶，才需要Location-Based路由。

請考慮下列其中一種您可能需要的其他設定：

![圖表 2 會顯示其他語音元件，例如來自 Microsoft 的電話號碼、撥號對應表和通話路由等。](media/voice-consider-additional-components.png)

| 視您的需求而定 | 描述 |
| :------------|:-------|
| [**電話號碼管理**](pstn-connectivity.md#phone-number-management) | 取得及管理電話號碼會根據您的 PSTN 連線選項而有所不同。 如果您需要取得電話號碼、移轉現有號碼、取得服務號碼等，請閱讀本節。 |
| [**通話路由和撥號對應表**](pstn-connectivity.md#call-routing-and-dial-plans) | 如何設定和管理撥號對應的撥號對應表，將撥號電話號碼轉換為替代格式 (通常是 E.164 格式) ，以供通話授權和通話路由使用。 如果您需要瞭解什麼是撥號對應表，以及是否需要為組織指定撥號對應表，請閱讀本節。|
| [**緊急通話**](pstn-connectivity.md#emergency-calling) | 管理及設定緊急通話方式會根據您的 PSTN 連線選項而有所不同。 如果您需要瞭解如何管理組織的緊急電話，請閱讀本節。 |
| [**直接路由的位置型路由**](pstn-connectivity.md#location-based-routing-for-direct-routing) |如何使用Location-Based路由 (LBR) 根據使用者的地理位置限制 Microsoft Teams 使用者的付費略過。 如果貴組織在不允許略過付費的位置使用直接路由，請閱讀本節。
| [**雲端語音功能的網路拓撲**](pstn-connectivity.md#network-topology-for-voice-features) | 如果貴組織正在部署Location-Based路由 (LBR) 以進行直接路由或動態緊急通話，您必須在 Microsoft Teams 中為這些功能設定網路設定。 如果您正在實作 LBR 直接路由，或是您正在實作使用通話方案或直接路由的動態緊急通話，請閱讀本節。 |
| [**移轉您現有的語音解決方案**](#migrate-your-existing-voice-solution-to-teams) | 將語音解決方案移轉到 Teams 時，您需要考慮的考慮。  如果您要從現有的語音解決方案移轉到 Teams，請閱讀本節。 

> [!Important]
> 本文著重于 Microsoft Teams 的語音解決方案。 由於 商務用 Skype Online 于 2021 年 7 月 31 日淘汰，不論是透過 商務用 Skype Server 或雲端連接器版本 &mdash; 與 商務用 Skype Online，您的內部部署環境 &mdash; 之間的 PSTN 連線都不再受到支援。 本文將介紹 Teams 語音解決方案，以及您如何視需要使用運算子連線或直接路由將內部部署電話語音網路連線至 Teams。


## <a name="phone-system"></a>電話系統

電話系統是 Microsoft 在 Microsoft 365 雲端使用 Microsoft Teams 啟用通話控制和專用 Exchange (PBX) 功能的技術。

電話系統可與 Teams 用戶端和認證裝置搭配使用。 電話系統可讓您以直接從 Microsoft 365 提供的一組功能取代現有的 PBX 系統。 

貴組織中的使用者之間的通話，不論地理區域為何，都會在電話系統內部處理。 這些內部通話永遠不會移至公用交換電話網路 (PSTN) ，因此貴公司可避免長途電話費。

本文將介紹下列電話系統主要功能，以及您需要考慮的部署決策：

- [自動語音應答和通話佇列](#auto-attendants-and-call-queues)
- [雲端語音信箱](#cloud-voicemail)
- [通話身分識別](#calling-identity)

![圖表 3 顯示電話系統包含自動語音應答和通話查詢、雲端語音信箱和通話身分識別。](media/phone-system-contains.png)

如需所有電話系統功能，以及如何設定電話系統的資訊，請參閱下列文章：

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)
- [設定貴組織的 [電話系統]](setting-up-your-phone-system.md)<br>
  說明如何購買和指派電話系統授權、管理電話號碼，以及設定免付費電話號碼的通訊點數。 

如需管理支援的裝置的相關資訊，請參閱在 Microsoft Teams 和[Teams 市集中](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)[管理您的裝置](devices/device-management.md)。


### <a name="auto-attendants-and-call-queues"></a>自動語音應答和通話佇列

自動語音應答可讓您根據來電者輸入來設定功能表選項來路由通話。 通話佇列是來電者的等候區域。 自動語音應答和通話佇列搭配使用，可以輕鬆地將來電者路由至組織中適當的人員或部門。

如需自動語音應答和通話佇列的相關資訊，請參閱下列文章：

- [規劃 Teams 自動語音應答和通話佇列](plan-auto-attendant-call-queue.md)
- [設定自動語音應答](create-a-phone-system-auto-attendant.md)
- [建立通話佇列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自動語音應答和通話佇列](voice-case-study-call-queues.md)<br>
  說明虛擬的多國公司 Contoso 如何實作語音解決方案的自動語音應答和通話佇列。

### <a name="cloud-voicemail"></a>雲端語音信箱

雲端語音信箱由 Azure 語音信箱服務提供，僅支援 Exchange 信箱的語音信箱存款。 不支援協力廠商電子郵件系統。 

雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。 您的業務需求可能會要求您停用特定使用者或整個組織每個人的語音信箱轉譯功能。

雲端語音信箱會自動設定並布建給 Teams 使用者。  

如需雲端語音信箱及其設定的詳細資訊，請參閱下列文章：

- [設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)
- [在貴組織中設定語音信箱原則](manage-voicemail-policies.md)


### <a name="calling-identity"></a>通話身分識別

根據預設，所有撥出電話都會使用指派的電話號碼作為通話身分識別 (來電者識別碼) 。 來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。 如需設定來電者識別碼或變更或封鎖來電者識別碼的相關資訊，請參閱 [設定使用者的來電號碼](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用交換電話網路連線選項

電話系統為您的組織提供完整的 PBX 功能。 不過，若要讓使用者在組織外部撥打電話，您需要將電話系統連線到公用交換電話網路 (PSTN) 。 若要將電話系統連線到 PSTN，您可以選擇下列其中一個選項：

- [**電話系統與通話方案**](pstn-connectivity.md#phone-system-with-calling-plan)。 將 Microsoft 做為 PSTN 電信業者的所有雲端解決方案。

- 使用運算子 [**連線與您自己的 PSTN 電信業者的電話系統**](operator-connect-plan.md)。 使用運算子連線時，如果您現有的運算子是參與 Microsoft 運算子連線計畫，他們可以管理將 PSTN 通話帶到 Teams 的服務。 如需運算子連線的優點和需求資訊，請參閱 [規劃運算子連線](operator-connect-plan.md)。

- 使用直接路由將內部部署環境連線至 Teams，與 [**您自己的 PSTN 電信業者使用電話**](pstn-connectivity.md#phone-system-with-direct-routing)系統。

您可以選擇選項群組合，讓您設計複雜環境的解決方案，或管理多步驟移轉。 您稍後會閱讀更多有關移轉的資訊。

無論您選擇的 PSTN 連線選項為何，大部分的電話系統功能都相同。 不過，功能有一些差異會影響您設定特定電話系統功能的方式，例如通話路由和緊急通話。 如需 PSTN 連線選項和設定考慮的詳細資訊，請參閱 [PSTN 連線選項](pstn-connectivity.md)。


## <a name="migrate-your-existing-voice-solution-to-teams"></a>將您現有的語音解決方案移轉到 Teams

> [!NOTE]
> 如需在整體規劃中規劃 Teams 語音解決方案，以從 商務用 Skype Server 升級至 Teams 的指導方針，請參閱[從內部部署升級至 Teams 商務用 Skype 的 PSTN 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)。

對於升級至 Teams 的組織而言，最終目標是將所有使用者移至 TeamsOnly 模式。 只有當使用者處於 TeamsOnly 模式時，才支援使用電話系統。 如果您需要升級至 Teams 的基本資訊，請從這裡開始：

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [關於升級架構](upgrade-framework.md)
- [適用于 IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)

移轉語音解決方案時，移動至 TeamsOnly 模式時，有四種可能的通話案例：

- [**商務用 Skype Online 中的使用者，且有 Microsoft 通話方案**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升級時，此使用者將繼續擁有 Microsoft 通話方案。

- **[商務用 Skype Online 中的使用者，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)可透過內部部署或雲端連接器版本商務用 Skype內部部署語音功能**。 使用者升級至 Teams 時，必須與將使用者移轉到直接路由協調，以確保 TeamsOnly 使用者具備 PSTN 功能。

- 商務用 Skype內部部署 **[中具有企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)，將會移至線上並保持內部部署 PSTN 連線** 能力。 將此使用者移轉到 Teams 時，必須將使用者的內部部署商務用 Skype帳戶移至雲端，並配合使用者移轉到直接路由來協調移轉。 

- 商務用 Skype內部部署 **[且擁有企業語音的使用者](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)，將會移至線上並使用 Microsoft 通話方案**。  將此使用者移轉到 Teams 時，必須將使用者的內部部署商務用 Skype帳戶移至雲端，並使用 A) 該使用者電話號碼的埠移轉至 Microsoft 通話方案，或是 B) 從可用地區指派新的訂閱者號碼。

如需如何針對這些案例實作語音移轉的詳細資訊，請參閱下列文章：

- [升級至 Teams 時的 PSTN 考慮 — 適用于 IT 系統管理員](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 語音移轉案例研究](voice-case-study-overview.md)<br>
  案例研究說明虛構的多國公司 Contoso 如何為組織實作 Teams 語音解決方案。 其中包含下列文章：

  - [Teams 升級計畫](voice-case-study-migration-plan.md)
  - [電話系統和 PSTN 連線選項](voice-case-study-phone-system.md)
  - [以位置為基礎的路由實作](voice-case-study-location-based-routing.md)
  - [緊急通話](voice-case-study-emergency-calling.md)
  - [自動語音應答和通話佇列](voice-case-study-call-queues.md)
  - [音訊會議](voice-case-study-audio-conferencing.md)
