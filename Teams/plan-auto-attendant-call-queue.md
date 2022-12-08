---
title: 規劃 Teams 自動語音應答和通話佇列
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: ab9f05a2-22cb-4692-a585-27f82d1b37c7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.autoattendants.overview
- Phone System
- seo-marvel-apr2020
description: 瞭解自動語音應答和通話佇列，以及如何使用自動語音應答和通話佇列來協助來電者在功能表系統之間移動，以連絡組織中的人員或部門。
ms.openlocfilehash: 5b5076ecd8ea521071124f5400ac5c2831b4fbfe
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307618"
---
# <a name="plan-for-teams-auto-attendants-and-call-queues"></a>規劃 Teams 自動語音應答和通話佇列

自動語音應答可讓您根據來電者輸入來設定功能表選項來路由通話。 自動語音應答的功能表選項，例如「針對銷售人員，請按 1--若為服務按 2」，可讓組織提供一系列選項，引導來電者快速前往目的地，而不需要由人力運算子來處理來電。

通話佇列是來電者的等候區域。 如果來電者需要連絡特定專業的人員，例如銷售或服務，而不是特定人員，您可以使用通話佇列將來電者連線到可協助他們的代理群組。 來電者會被保留，直到被指派到佇列的專員可以接聽他們的來電。

自動語音應答和通話佇列搭配使用，可以輕鬆地將來電者路由至組織中適當的人員或部門。

## <a name="auto-attendants"></a>自動語音應答

自動語音應答的主要目的是根據來電者對所提供功能表選項的輸入，將來電者導向適當的人員或部門。 來電者可以導向至組織內的特定人員、撥打佇列等候與下一位可用的代理人通話，或是撥打語音信箱。 您可以針對上班時間、上班時間和假日指定不同的通話路由選項。

您可以使用文字轉換語音 (系統產生的提示來建立功能表提示) 或是上傳錄製的音訊檔案。 語音辨識會接受免持聽筒流覽的語音命令，但撥入的人員也可以使用電話鍵台來流覽功能表。

每個自動語音應答都有特定的語言和時區。 如果您以多種語言或全球多個地區進行業務，您可以視需要建立任意數量的不同自動語音應答，以容納來電者。

您可以針對每個自動語音應答設定運算子。 雖然您可以設定撥打至不同目的地的電信業者通話，但電信業者功能的設計是允許來電者與貴組織中能提供協助的特定人員通話。

您可以設定自動語音應答，允許來電者依名稱或分機號碼搜尋貴組織的目錄。 在自動語音應答中，您可以選擇要包含或排除的使用者群組，來指定誰可以進行目錄搜尋。  (這稱為 *dial scope*.) 

來電者可以透過直接電話號碼、設定或從另一個自動語音應答或通話佇列重新導向，來連線到自動語音應答。

## <a name="call-queues"></a>通話佇列

通話佇列與實體大樓內的等候室類似。 來電者等候通話被路由至佇列中的代理程式。 通話佇列通常用於銷售和服務功能。 不過，通話佇列可用於電話數目超過內部容量的任何情況，例如忙碌設施中的接聽員。

如果佇列中的來電者總數或等待時間超過您指定的限制，通話佇列會允許特定的呼叫路由。 通話可以路由至特定人員、語音信箱、其他通話佇列或自動語音應答。

通話佇列和自動語音應答一樣，都有語言設定。 如果您使用多種語言進行業務，則可以使用不同的通話佇列。 專員可以是多語言成員，可以是多個佇列的成員。

針對每一個通話佇列，您可以指定佇列中的代理程式是否可以選擇不接聽電話，以及是否應根據通話在 Teams 中的目前狀態指示路由給他們。

您可以將電話號碼指派給通話佇列，但是通話佇列不會針對上班時間和假日提供個別的通話路由。 除非您的通話佇列是 24/7 的人員，我們建議將電話號碼指派給自動語音應答，該自動語音應答會在上班時間內重新導向到通話佇列。

## <a name="prerequisites"></a>必要條件

若要設定自動語音應答和通話佇列，您需要下列資源：

- 每個自動語音應答以及每個通話佇列的 [資源帳戶](manage-resource-accounts.md) 。
- 每個資源帳戶的免費[Microsoft Teams 電話資源帳戶授權](teams-add-on-licensing/virtual-user.md)，可直接從 Teams 使用者或外部電話號碼撥號。
- 針對您要直接從外部電話號碼撥號的每個資源帳戶，至少一個[Microsoft服務號碼](getting-service-phone-numbers.md)、運算子[聯](operator-connect-plan.md)機[號碼、直接路由號碼](direct-routing-plan.md)或混合式號碼。
  - 服務號碼可能是付費或免付費號碼。

> [!NOTE]
> 資源帳戶因登入而停用，且必須維持不變。 這些帳戶無法使用聊天和目前狀態。

從通話佇列接聽來電的代理人必須企業語音啟用線上或內部部署使用者。 如需詳細資訊，請參閱 [指派、變更或移除使用者的電話號碼](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user) 和 [啟用使用者的直接路由](/microsoftteams/direct-routing-enable-users)。 此外，如果通話佇列是使用直接路由號碼，則需要開會或轉接電話的代理程式也需要：

- 如果通話佇列使用轉接模式，則會指派 [線上語音路由](manage-voice-routing-policies.md) 原則。
- 如果通話佇列使用會議模式，則會指派 [音訊會議授權](set-up-audio-conferencing-in-teams.md) 或 [線上語音路由](manage-voice-routing-policies.md) 原則。

如果您的專員使用 Microsoft Teams 應用程式進行通話佇列通話，則他們必須處於 TeamsOnly 模式。

在通話佇列中使用資源帳戶做為通話行識別碼用途時，資源帳戶必須具有 Teams 電話資源帳戶授權，以及下列其中一項指派：

- [通話方案](calling-plans-for-office-365.md)授權和指派的電話號碼。
- 指派 [的運算子連線](operator-connect-plan.md) 電話號碼。
- [線上語音路由原則](manage-voice-routing-policies.md)。
  - 使用直接路由時，電話號碼指派是選用的。

當自動語音應答或通話佇列將來電轉接至外部號碼時，如下所述的特定資源帳戶必須具有 Teams 電話資源帳戶授權，以及下列其中一項指派：

- [通話方案](calling-plans-for-office-365.md)授權和指派的電話號碼。
- 指派 [的運算子連線](operator-connect-plan.md) 電話號碼。
- [線上語音路由原則](manage-voice-routing-policies.md)。
  - 使用直接路由時，電話號碼指派是選用的。

授權的資源帳戶：

- 當自動語音應答轉接給其他自動語音應答或呼叫佇列以外部轉接來電時，授權第一個接收來電之自動語音應答的資源帳戶。
- 在所有其他通話案例中，授權自動語音應答的資源帳戶或執行外部轉接的通話佇列。

> [!NOTE]
> 如果指派給資源帳戶的通話方案已停用或遭到移除， [則通訊點](what-are-communications-credits.md)數若在租使用者 (中提供，但未指派給資源帳戶) ，則會被使用。 如果沒有通話方案或通訊點數，通話將會失敗。
>
> 自動語音應答的直接路由服務號碼和通話佇列僅支援Microsoft Teams 使用者和通話代理程式。
> 
> 不支援通話方案、運算子連線和直接路由主幹之間的傳輸。
> 
> 在混合式案例中，必須先在內部部署建立資源帳戶。 如需詳細資訊，請參閱 [規劃雲端通話佇列](/skypeforbusiness/hybrid/plan-call-queue)。

## <a name="business-decisions"></a>商務決策

在設定自動語音應答和通話佇列之前，您應該先做出一些決定，決定如何在企業中使用這些功能。 這些決定會決定您在設定自動語音應答和通話佇列時所選擇的設定。

記錄這些問題的解答，並提供資訊給執行設定的系統管理員。

- 您需要哪些語言？ 這些語言需要在哪裡 - 哪個部門或群組？
- 您想要允許來電者的語音輸入，還是只允許撥號輸入？
- 您是否需要針對下班時間或假日個別路由來電？ 什麼是時數和假日？
- 您是否要允許通話佇列中的代理程式選擇不接聽電話？
- 您希望通話佇列中的代理程式或電信業者在撥出時擁有特定的來電者識別碼嗎？
- 您想要啟用組織中的 [通話駐駐和擷取](call-park-and-retrieve.md) 功能，以協助連絡人或部門之間的撥號作業嗎？
- 針對語音提示，您是否要錄製自己的語音或使用系統產生的語音？
  - 系統產生的語音很容易更新。

## <a name="technical-decisions"></a>技術決策

當您使用自動語音應答和通話佇列將來電者連線到貴組織中的人員時，在您開始設定之前，有一些技術決策需要先做出。

您可以使用下列方式，將專員新增至通話佇列：

- 個別使用者
- 通訊群組清單
- 安全性群組，包括具備郵件功能的安全性群組
- Microsoft 365 群組或 Teams

如有需要，您可以針對每一個佇列使用這些選項的組合。 具有電子郵件地址的群組可用於語音信箱。 使用 Teams 提供許多優點，包括代理程式之間的共用檔案儲存空間和聊天、可接收語音信箱的常見信箱，以及可包含與企業營運應用程式或 Power Apps 整合的可延伸平臺。

建議您在開始設定之前，選擇將通話代理程式新增至佇列的策略。

如果您有現有的自動語音應答和通話佇列基礎結構，而且要移轉到 Teams，您將需要一個方案，將現有的電話號碼移轉到新的自動語音應答和通話佇列。 您可能需要建立 [移轉訂單](phone-number-calling-plans/port-order-overview.md) ，才能從其他提供者移動您的號碼。 我們建議您暫時取得一或多個新的電話號碼，並測試自動語音應答和通話佇列流量，然後再將它們切換到您目前服務中的號碼。

**會議模式** 是通話佇列中的一個選項，可大幅減少將 Teams VOIP 通話和 PSTN 通話連線至專員所需的時間。 若要讓會議模式正常運作，通話佇列中的代理程式必須使用下列其中一個用戶端：

- 最新版本的 Microsoft Teams 桌面用戶端、Android 應用程式或 iOS 應用程式。
- Microsoft手機系統版本 1449/1.0.94.2020051601 或更新版本。
  
將專員的 Teams 帳戶設定為僅限 Teams 模式。 不符合需求的代理程式不包含在通話路由清單中。

如果您的代理程式都使用相容的用戶端，建議您為通話佇列啟用會議模式。

**呼叫路由流程** 方案可協助判斷撥入貴組織之人員最有效率的路由。 若要瞭解如何規劃您的來電路由流程，請參閱 [規劃您的通話路由流程](plan-your-call-routing-flow.md)。

## <a name="getting-started"></a>快速入門

完成本文中的規劃工作後，請依照下列步驟設定自動語音應答和通話佇列：

1. 從組織外部直接撥號，取得您想要存取的自動語音應答和通話佇列所需的服務號碼。 這可能包括 [從其他提供者移轉號碼](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ，或 [要求新的服務號碼](getting-service-phone-numbers.md)。

2. 針對您計畫建立的每個資源帳戶取得 [Teams Phone 資源帳戶授權](teams-add-on-licensing/virtual-user.md) 。 這些授權是免費的，因此我們建議您在日後決定變更資源帳戶時，多多取得一些授權。

3. 為您要建立的每個自動語音應答和通話佇列建立[資源帳戶](manage-resource-accounts.md)。 將 Teams 電話資源帳戶授權指派給每個可直接撥打的資源帳戶，並選擇性地指派服務號碼。

4. [建立您想要在](set-up-holidays-in-teams.md) 自動語音應答中分別傳送通話的假日。

5. 或者，如果您想要使用此功能來協助轉接電話，也可以 [設定通話駐車和取](call-park-and-retrieve.md) 回。

6. 建立您要用來包含通話佇列之通話代理程式的群組。

7. 如果您打算允許透過分機撥號，請確定您已將使用者的分機號碼新增至 Azure Active Directory (Azure AD) 設定檔。

完成上述步驟後，就可以建立自動語音應答和通話佇列。 因為自動語音應答和通話佇列可以將通話重新導向至彼此，請參閱您建立的工作流程圖表，判斷應該先建立哪個自動語音應答或通話佇列。 在上述圖表中的範例中，您會在建立 Contoso 主自動語音應答之前建立銷售和支援通話佇列，因為主自動語音應答需要將來電者導向銷售和支援通話佇列。

如需如何建立自動語音應答和通話佇列的相關資訊，請參閱下列文章：

- [設定自動語音應答](create-a-phone-system-auto-attendant.md)
- [建立通話佇列](create-a-phone-system-call-queue.md)

> [!IMPORTANT]
> 使用者的 Azure AD GUID 權杖會在使用者設定為：時，儲存為自動語音應答或通話佇列設定的一部分：
>
>  - 自動語音應答或通話佇列 **授權使用者**。
>  - 自動語音應答 **運算子**。
>  - **組織轉移點中的人員**。
>  - 通話佇列的個別成員。
> 
> 自動語音應答和通話佇列設定未與 Azure AD 生命週期事件同步處理。  Teams 系統管理員必須手動更新自動語音應答和通話佇列設定，以便在設定中包含的使用者離開組織時移除此個人資料。
>
> 這不適用於透過通訊群組清單或頻道設定的通話佇列代理成員資格。 也不適用於透過自動語音應答的 [ **以名稱撥號** ] 或 [ **以號碼撥號** 方式撥號] 功能聯繫的使用者。

如果您需要更廣泛的功能，例如與工作流程、Bot 和簡訊整合，請考慮[Azure 通訊服務](/azure/communication-services/overview)。

## <a name="related-topics"></a>相關主題

[規劃直接路由](direct-routing-plan.md)

[音訊會議與通話方案的適用國家/地區](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
