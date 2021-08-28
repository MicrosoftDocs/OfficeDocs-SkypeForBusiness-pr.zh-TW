---
title: 規劃雲端自動語音應答
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: 使用含商務用 Skype Server 2019 的雲端自動語音應答的概覽
ms.openlocfilehash: 5d28618efc2b02240cdfe3e4c05945f9a6e4b575
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58610170"
---
# <a name="plan-cloud-auto-attendants"></a>規劃雲端自動語音應答

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

在) 2019 或 Exchange Server 中，與 Exchange 整合通訊 (Exchange Server 2013 或 Exchange Server 2016 Exchange Online 的自動語音應答已不再提供使用。 如果您的商務用 Skype Server 2019 的實現與上述任一 Exchange 版本整合，您必須使用與電話系統相關聯的線上雲端語音功能。 如需將位於 Exchange Server 2013 和2016的 Exchange UM 服務移至雲端，請參閱[規劃商務用 Skype Server 和 Exchange Server 遷移](plan-um-migration.md)。

這本身就表示，如果您想要使用整合通訊功能（如自動語音應答），則會有商務用 Skype Server 2019 的混合式實現。 如需詳細資訊，請參閱[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

自動語音應答是一項雲端服務，可接受客戶來電和播放問候語、提供功能表選項，並與使用語音或撥號盤的來電者互動，以將來電路由傳送至正確目的地。 每個自動語音應答都會被指派一個 *資源帳戶* (請參閱設定) 商務用 Skype Server 2019 系統上的 [資源帳戶](configure-onprem-ra.md)，以直接連結到 Microsoft Teams 系統管理中心中的自動語音應答。 請參閱 [什麼是雲端自動](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md) 語音應答？如需有關自動語音應答的詳細資訊，以及自動語音應答的選項及功能有哪些。

> [!NOTE]
> 您可以將多個 Microsoft 服務號碼、直接路由編號或混合號碼指派給自動語音應答。

對雲端自動語音應答的來電可以採用下列其中一種路徑，如下所示：

![自動語音應答的圖表](../../SfBServer2019/media/AA-plan-concept.png)

1. Via 商務用 Skype Server 2019
2. 透過 [會話邊界控制器](/MicrosoftTeams/direct-routing-border-controllers.md) 和 [直接路由](/MicrosoftTeams/direct-routing-plan.md)
3. 透過在 Microsoft 365 或 Office 365 中的線上號碼。

另請參閱：

- [設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)
- [自動接聽和路由傳送來電](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。  您的需求取決於您的案例：

- 如果您已在使用 Exchange UM 線上或內部部署，且您升級為商務用 Skype 2019，您將需要捕獲自動語音應答的結構，並使用雲端自動語音應答在雲端中重新建立。 如需詳細資訊，請參閱[將 Exchange UM 自動語音應答或通話佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

- 若為雲端自動語音應答的新設定，請遵循  [設定資源帳戶](configure-onprem-ra.md)中所述的步驟。

除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft Cloud 自動語音應答服務：

- 混合連接。 如果您已部署商務用 Skype Server，而您想要為您的內部部署使用者啟用雲端自動語音應答，則必須確定您的內部部署與線上環境之間已設定混合式連線能力。 這有時稱為分割網域設定。

   如需詳細資訊，請參閱[Plan 商務用 Skype Server 和 Microsoft 365 之間的混合](plan-hybrid-connectivity.md)式連線，或 Office 365 和[設定商務用 Skype Server 及 Microsoft 365 或 Office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 如果您要將電話號碼指派給您的自動語音應答，則需要[Office 365 企業版 E5](../../SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing.md)授權。
- 為每個自動語音應答建立線上 [資源帳戶](/MicrosoftTeams/manage-resource-accounts.md) 或內部部署 [資源帳戶](configure-onprem-ra.md) ，並指派電話號碼和授權。 

## <a name="migration-and-interoperability"></a>遷移和互通性

如果您打算部署商務用 Skype Server 2019 和/或 Exchange Server 2019，您必須仔細規劃遷移，以確保自動語音應答的持續支援。 請記住下列事項：

- Exchange Server 2019 不再提供 Exchange UM 功能
- Exchange整合通訊處於退休模式
- 商務用 Skype Server 2019 不再與 Exchange Online UM 整合

雲端自動語音應答可使用商務用 Skype Server 2019、2015及2013進行設定。

Microsoft 建議下列遷移路徑：

- 若要升級為商務用 Skype Server 2019，您可以在 Exchange Server 2013 或2016中使用 Exchange UM，但如果您使用 Exchange Server 2019，則必須升級至雲端自動語音應答。

- 如果您要升級為 Exchange Server 2019，而您使用舊版的 Exchange Server UM 來商務用 Skype Server 語音訊息，則 Microsoft 建議您在信箱升級之前升級為商務用 Skype Server 2019。  否則，語音訊息功能將會遺失。

如需規劃遷移的詳細資訊，請參閱[商務用 Skype Server 和 Exchange Server 遷移的計畫](plan-um-migration.md)。

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>遷移先前執行的 Exchange UM 自動語音應答系統

目前，我們不支援在 Exchange 2013 或2016中所建立的 UM 自動語音應答系統上自動遷移至雲端。 若要手動重新建立自動語音應答系統，您必須：

1. 使用 Exchange 系統管理 PowerShell 命令來檢查舊自動語音應答系統的結構，包括任何嵌套的自動語音應答和通話佇列。  
2. 建立與每個 UM 自動語音應答節點相關聯的文字到語音腳本或錄製的訊息複本。
3. 針對每個自動語音應答節點建立內部部署端點，包括將測試電話號碼和授權指派給物件。 請注意，您現在可以指定線上服務（如電話系統）所使用的內部部署電話號碼授權。
4. 使用 Microsoft Teams 和電話系統來執行新的雲端自動語音應答服務。 請參閱 [設定資源帳戶](configure-onprem-ra.md) 以取得執行詳細資料。 當您這麼做時，請上傳文字到語音的腳本或與每個 UM 自動語音應答節點相關聯的錄製郵件。
5. 測試雲端自動語音應答的功能。
6. 將指派給舊 Exchange UM 自動語音應答的電話號碼重新指派給新建立的主雲端自動語音應答。

如需這些步驟的詳細資訊，請參閱[將 Exchange UM 自動語音應答或通話佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

當您具有符合您需求的實體結構，以及可有效指導客戶有效的腳本時，請繼續 [設定資源帳戶](configure-onprem-ra.md)。

> [!CAUTION]
> 如[KB4480742](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)所述，不鼓勵將伺服器2015中建立的 UM 自動語音應答 Exchange 移至執行伺服器2019的伺服器。 在此情況下，您必須將其保留在 coexistance 模式中執行的商務用 Skype Server 2015 集區。

## <a name="see-also"></a>另請參閱

[規劃商務用 Skype 和 Exchange Server 的先決條件的移轉](plan-um-migration.md)

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面錄製自訂提示](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)

ExchangeUM：[自動接聽和路由傳送來電](/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](plan-hybrid-connectivity.md)

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](configure-hybrid-connectivity.md)

[KB4480742：將連絡人物件移至商務用 Skype Server 2019 後，對訂閱者存取或自動語音應答的呼叫會失敗，並會出現「快速忙碌」和「500伺服器內部」錯誤](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)