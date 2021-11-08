---
title: 在 Microsoft Teams
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
description: 深入瞭解雲端Microsoft Teams功能，以及您將為貴組織做出部署決策。
appliesto:
- Microsoft Teams
ms.openlocfilehash: dba035c7bcbc6f94e8c4e7573f7dc6c4bc0e06c3
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824682"
---
# <a name="plan-your-teams-voice-solution"></a>規劃您的Teams語音解決方案 

本文可協助您決定適合貴組織的 Microsoft 語音解決方案。 在您決定之後，本文會提供內容藍圖，以便您執行您所選擇的解決方案。

您可能會想要使用通話方案 &mdash; 電話系統最簡單的解決方案。 這是 Microsoft 的全雲端解決方案，提供私人分支 Exchange (PBX) 功能，以及撥打公用交換電話網絡 (PSTN) ，如下圖所示。 有了這個解決方案，Microsoft 就是您的 PSTN 電信公司。

![圖表 1 顯示電話系統通話方案。](media/voice-solutions-simple.png)

如果您對下列專案回答是，電話系統通話方案是適合的解決方案：

- 通話方案可在您的地區使用。
- 您不需要保留目前的 PSTN 電信公司。
- 您想要使用 Microsoft 管理的 PSTN 存取權。

不過，您的情況可能較為複雜。 例如，您可能在無法使用通話方案的位置有辦公室。 或者，您可能需要支援複雜、多國部署的組合解決方案，且不同的地理位置有不同的需求。 Microsoft 支援一組解決方案： 

- 電話系統通話方案
- 電話系統具有運算子的 PSTN 電信連線
- 電話系統直接路由使用您自己的 PSTN 電信公司
- 搭配通話方案電話系統通話方案、電話系統運算子連線，以及/或電話系統直接路由的組合解決方案


## <a name="what-do-you-need-to-read"></a>您需要閱讀哪些資訊？

**全部為必填專案。** 本文中的部分章節與所有組織有關。 例如，每個人都應該閱讀電話系統並瞭解如何使用 PSTN (網) 。 


| 全部為必填專案 | 描述 |
| :------------|:-------|
| [**電話系統**](#phone-system) | Microsoft 的呼叫控制與私人分支與 PBX Exchange (技術) 雲端Microsoft 365功能Microsoft Teams。 |
| [**公用交換電話網絡 (PSTN) 選項**](#public-switched-telephone-network-connectivity-options) | 選擇使用 Microsoft 做為電話電信業者，或使用電信業者電話Microsoft Teams或直接路由連線電信業者。 PSTN 電話系統結合，可讓使用者撥打全球電話。|

**視您的需求而不同。** 本文和相關文章中的一些章節會根據您的現有部署和需求而相關。 例如，Location-Based不允許免付費路的地理位置中的直接路由客戶，才需要直接路由。

請考慮您可能需要的這些額外配置：

![圖表 2 顯示其他語音元件，例如電話的號碼、撥號方案及通話路由等等。](media/voice-consider-additional-components.png)

| 視您的需求而不同 | 描述 |
| :------------|:-------|
| [**電話號碼管理**](pstn-connectivity.md#phone-number-management) | 如何取得和管理電話號碼會根據您的 PSTN 連接選項而不同。 如果您需要取得電話號碼、傳輸現有號碼、取得服務號碼等，請閱讀本節。 |
| [**通話路由和撥號方案**](pstn-connectivity.md#call-routing-and-dial-plans) | 如何設定及管理將撥號電話號碼轉換成替代格式的撥號方案 (通常是 E.164 格式) 電話授權和呼叫路由。 如果您需要瞭解什麼是撥號方案，以及您是否需要為貴組織指定撥號方案，請閱讀本節。|
| [**緊急電話**](pstn-connectivity.md#emergency-calling) | 如何管理及設定緊急電話會根據您的 PSTN 連接選項而不同。 如果您需要瞭解如何管理組織的緊急電話，請閱讀本節。 |
| [**直接路由的基於位置的路由**](pstn-connectivity.md#location-based-routing-for-direct-routing) |如何使用 Location-Based路由 (LBR) 根據使用者的地理位置Microsoft Teams付費旁路。 如果貴組織在不允許免付費路的位置使用直接路由，請閱讀本節。
| [**雲端語音功能的網路拓撲**](pstn-connectivity.md#network-topology-for-voice-features) | 如果貴組織正在部署 Location-Based路由 (LBR) 直接路由或動態緊急電話，您必須設定網路設定，以與 Microsoft Teams 中的這些功能一Microsoft Teams。 如果您正針對直接路由執行 LBR，或是使用通話方案或直接路由來實施動態緊急電話，請閱讀本節。 |
| [**遷移現有的語音解決方案**](#migrate-your-existing-voice-solution-to-teams) | 當您將語音解決方案移向 Teams。  如果您要從現有的語音解決方案移向新的語音解決方案，請閱讀Teams。 

> [!Important]
> 本文著重于語音解決方案與Microsoft Teams。 雖然目前商務用 Skype線上版解決方案，但必須瞭解 商務用 Skype Online 將于 2021 年 7 月 31 日停用。  在此日期之後，商務用 Skype線上服務將無法再使用。 此外，不再支援內部部署環境之間的 PSTN 連線商務用 Skype Server雲端連接器版本和 商務用 Skype Online 之間的 &mdash; &mdash; PSTN 連線。 本文將介紹Teams語音解決方案，以及如何在必要時使用直接路由或運算子Teams連接內部部署電話網絡連線。


## <a name="phone-system"></a>電話系統

電話系統 Microsoft 的技術，可啟用通話控制與私人分支 Exchange (PBX) 雲端Microsoft 365功能Microsoft Teams。

電話系統用戶端Teams或商務用 Skype認證裝置。 電話系統可讓您將現有的 PBX 系統取代為一組直接從 Microsoft 365。 

貴組織使用者之間的通話在內部處理電話系統，而且永遠不會前往 PSTN (電話) 。 這適用于貴組織中位於不同地理區域的使用者之間的通話，這可移除這些內部通話的長途費用。

本文將介紹下列電話系統功能，以及您需要考慮的部署決策：

- [自動語音應答和通話佇列](#auto-attendants-and-call-queues)
- [雲端語音信箱](#cloud-voicemail)
- [通話身分識別](#calling-identity)

![圖表 3 顯示電話系統包含自動語音留言和通話查詢、雲端語音信箱和通話身分識別。](media/phone-system-contains.png)

若要瞭解所有電話系統功能，以及如何設定電話系統，請參閱下列文章：

- [以下是可透過電話系統獲得的功能](here-s-what-you-get-with-phone-system.md)
- [設定貴組織的 [電話系統]](setting-up-your-phone-system.md)<br>
  說明如何購買及指派電話系統授權、管理電話號碼，以及設定免付費號碼的通訊額度。 

有關管理支援裝置的資訊，請參閱在[](devices/device-management.md)Microsoft Teams 和[Teams 管理您的裝置](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)。


### <a name="auto-attendants-and-call-queues"></a>自動電話機和通話佇列

自動語音機允許您設定功能表選項，以根據來電者輸入路由通話。 通話佇列正在等待來電者的區域。 自動語音回應和通話佇列一起使用，可以輕鬆地將來電者路由至貴組織中適當的人員或部門。

有關自動電話機和通話佇列的資訊，請參閱下列文章：

- [規劃自動Teams和通話佇列](plan-auto-attendant-call-queue.md)
- [設定自動機務員](create-a-phone-system-auto-attendant.md)
- [建立通話佇列](create-a-phone-system-call-queue.md) 
- [Contoso 案例研究：自動電話機和通話佇列](voice-case-study-call-queues.md)<br>
  說明一家虛構的多國公司 Contoso 如何針對語音解決方案實作自動語音語音和通話佇列。

### <a name="cloud-voicemail"></a>雲端語音信箱

雲端語音信箱 Azure 語音信箱服務提供的支援，僅支援語音信箱Exchange信箱。 它不支援協力廠商電子郵件系統。 

雲端語音信箱包括語音信箱抄錄，根據預設，它對組織中的所有使用者啟用。 您的業務需求可能會要求您停用特定使用者或整個組織所有人的語音信箱翻譯功能。

只有線上使用者雲端語音信箱，系統會在使用者獲得授權後，自動設定電話系統設定。 對於電話系統信箱的使用者Exchange，您必須執行額外的組組步驟。 

有關雲端語音信箱及其組組的資訊，請參閱下列文章：

- [設定 [雲端語音信箱]](set-up-phone-system-voicemail.md)
- [在組織中設定語音信箱政策](manage-voicemail-policies.md)


### <a name="calling-identity"></a>通話身分識別

根據預設，所有外發通話會使用指派的電話號碼做為通話身分識別 (來電) 。 來電接收者可以快速識別來電者，並决定是否接聽或拒絕接聽來電。 有關設定本機號碼或變更或封鎖本機號碼的資訊，請參閱為使用者設定 [本機號碼](set-the-caller-id-for-a-user.md)。 

## <a name="public-switched-telephone-network-connectivity-options"></a>公用交換電話網路連接選項

電話系統為貴組織提供完整的 PBX 功能。 不過，若要讓使用者在組織外撥打電話，您必須將電話電話系統到公用交換電話網絡 (PSTN) 。 若要電話系統 PSTN，您可以選擇下列其中一個選項：

- [**電話系統通話方案 。**](pstn-connectivity.md#phone-system-with-calling-plan) 以 Microsoft 做為 PSTN 電信公司的全雲端解決方案。

- [**電話系統與您自己的 PSTN 電信公司使用運算子連線。**](operator-connect-plan.md) 使用運算子連線，如果您現有的接線員是 Microsoft Operator 連線 計畫的參與者，他們可以管理將 PSTN 通話Teams。 有關運算子和運算子的權益和需求連線，請參閱[規劃運算子連線。](operator-connect-plan.md)

- [**電話系統使用**](pstn-connectivity.md#phone-system-with-direct-routing)直接路由將您的內部部署環境連接到您的 PSTN 電信Teams。

您也可以選擇選項群組合，以設計複雜環境的解決方案，或管理多步驟移 (移) 。

無論您電話系統 PSTN 連接選項，大部分的功能都是相同的。 不過，功能有一些差異，會影響您設定特定 電話系統功能 ，例如通話路由和緊急電話。 有關 PSTN 連接選項和這些組組考慮的詳細資訊，請參閱 [PSTN 連接選項](pstn-connectivity.md)。


## <a name="migrate-your-existing-voice-solution-to-teams"></a>將現有的語音解決方案遷移到Teams

> [!NOTE]
> 有關將 Teams 語音解決方案規劃為從 商務用 Skype Server 升級至 Teams 的整體計畫之一的指引，請參閱從 商務用 Skype 內部部署升級到 Teams 的[PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)考慮。

對於升級至 Teams 的組織，最終的目標是將所有使用者移至 TeamsOnly 模式。 只有在電話系統 TeamsOnly Teams，才支援在 Teams 中使用應用程式。 如果您需要升級至 Teams 的基本資訊，請從這裡開始：

- [開始升級您的 Microsoft Teams](upgrade-start-here.md)
- [關於升級架構](upgrade-framework.md)
- [適用于 IT 系統管理員的升級策略](upgrade-to-teams-on-prem-implement.md)

移移語音解決方案時，移至 TeamsOnly 模式時，有四種可能的通話案例：

- [**使用 Microsoft 通話商務用 Skype Online 中的使用者**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)。 升級後，該使用者會繼續擁有 Microsoft 通話方案。

- **[透過內部商務用 Skype](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** 或雲端連接器版使用內部部署語音商務用 Skype Online 中的使用者。 使用者的升級至Teams使用者移向直接路由，以確保 TeamsOnly 使用者具有 PSTN 功能。

- 使用 商務用 Skype 內部部署的使用者企業語音 ，該使用者將會移往線上並保持 **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)內部部署 PSTN 連線**。 將該使用者移轉Teams需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，並協調使用者移轉至直接路由。 

- 使用 商務用 Skype 內部部署 **[的使用者企業語音，](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** 該使用者將會移往線上，並且使用 Microsoft 通話方案。  將該使用者移轉至 Teams 時，需要將使用者的內部部署 商務用 Skype 帳戶移至雲端，然後使用 A) 將該使用者電話號碼的埠移轉至 Microsoft 通話方案，或 B) 從可用區域指派新的訂閱者號碼。

若要進一步瞭解如何針對這些案例執行語音移移，包括何時需要設定混合式連接，以及如何將具有內部部署語音功能的使用者移向直接路由的資訊，請參閱 &mdash; &mdash; 下列文章：

- [升級至適用于 IT 系統管理員的 PSTN Teams PSTN 考慮](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Contoso 語音移移案例研究](voice-case-study-overview.md)<br>
  案例研究說明一家虛構的多國公司 Contoso 如何為組織Teams語音解決方案。 它包含下列文章：

  - [Teams升級方案](voice-case-study-migration-plan.md)
  - [電話系統 PSTN 連接選項](voice-case-study-phone-system.md)
  - [位置式路由實現](voice-case-study-location-based-routing.md)
  - [緊急電話](voice-case-study-emergency-calling.md)
  - [自動語音應答和通話佇列](voice-case-study-call-queues.md)
  - [音訊會議](voice-case-study-audio-conferencing.md)
