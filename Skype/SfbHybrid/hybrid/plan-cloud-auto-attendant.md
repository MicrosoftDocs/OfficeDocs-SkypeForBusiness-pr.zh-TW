---
title: 規劃雲端自動語音應答
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動助手的概覽
ms.openlocfilehash: 1a5f1aad4cd983f1f3839f47c54404d168ecf7f0
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2019
ms.locfileid: "36185536"
---
# <a name="plan-cloud-auto-attendants"></a>規劃雲端自動語音應答

Exchange Server 2019 或 exchange Online 中已不再提供與 Exchange 整合通訊 (Exchange Server 2013 或 Exchange Server 2016) 搭配使用的自動回應。 如果您的商務用 Skype Server 2019 實現與其中一個 Exchange 版本整合, 您將需要使用與電話系統相關聯的線上雲端語音功能。 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)的相關資訊, 瞭解如何將 exchange UM 服務託管于 exchange Server 2013 和2016移至雲端。

這本身就代表, 如果您想要使用 [自動語音傳送] 等統一訊息功能, 就會有混合式的商務用 Skype Server 2019。 如需詳細資訊, 請參閱[設定商務用 Skype Server 與 Office 365 之間的混合式連接](configure-hybrid-connectivity.md)。

自動語音應答是一種雲端服務, 可接受客戶呼叫及播放問候語、透過功能表選項提供, 以及使用語音或撥號鍵台與來電者進行互動, 以將來電路由到正確的目的地。 每個自動語音應答都會獲指派**資源帳戶**(請參閱[設定](configure-onprem-ra.md)您的商務用 Skype Server 2019 系統), 該系統會直接連結到 Microsoft 團隊系統管理中心的自動語音應答。 請參閱[什麼是雲端自動](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants.md)語音應答？如需自動語音應答的詳細資訊, 以及自動語音應答的選項和功能。

> [!NOTE]
> 您可以將多個 Microsoft 服務號碼或混合式編號指派給自動語音應答。

對雲端自動語音應答的撥入呼叫可以採用數種路徑, 如下所示:

![自動語音應答的圖表](../../SfBServer2019/media/AA-plan-concept.png)

1. 透過商務用 Skype Server 2019
2. 透過[會話邊界控制器](/MicrosoftTeams/direct-routing-border-controllers.md)和[直接路由](/MicrosoftTeams/direct-routing-plan.md)
3. 透過 Office 365 中的數位線上進行。

另請參閱:

- [設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)
- [自動接聽來電並傳送來電](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。  您的需求取決於您的案例:

- 如果您已經在使用 Exchange UM 線上或內部部署, 且您升級至商務用 Skype 2019, 您將需要使用雲端自動語音應答來捕獲自動語音應答的結構, 並在雲端重新建立。 如需詳細資訊, 請參閱[將 EXCHANGE UM 自動語音應答或呼叫佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

- 如需雲端自動語音應答的新設定, 請依照[設定資源帳戶](configure-onprem-ra.md)中所述的步驟進行。

除了上述需求之外, 必須將以下需求設定為連線至 Microsoft 雲端自動語音應答服務:

- 混合式連線性。 如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端自動回應, 您必須確保您在內部部署與線上環境之間已設定混合式連接。 這有時稱為分割網域配置。

   如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 如果您要將電話號碼指派給自動語音應答, 您必須具備[Office 365 企業版 E5](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/office-365-enterprise-e5-with-audio-conferencing)授權。
- 針對每個自動語音應答建立內部部署[資源帳戶](/MicrosoftTeams/manage-resource-accounts.md), 並指派電話號碼和授權。 

## <a name="migration-and-interoperability"></a>遷移和互通性

如果您打算部署商務用 Skype Server 2019 和/或 Exchange Server 2019, 您必須小心地規劃您的遷移, 以確保自動語音應答的支援。 請記住下列事項:

- Exchange Server 2019 不再提供 Exchange UM 功能
- Exchange 整合訊息線上處於停用模式
- 商務用 Skype Server 2019 不再與 Exchange Online UM 整合

雲端自動語音應答可以使用商務用 Skype Server 2019、2015和2013進行設定。

Microsoft 建議下列遷移路徑:

- 如果您要升級到商務用 Skype Server 2019, 您可以在 Exchange Server 2013 或2016中使用 Exchange UM, 但如果您使用的是 Exchange Server 2019, 則必須升級至雲端自動語音應答。

- 如果您要升級到 Exchange Server 2019, 且您使用舊版 Exchange Server UM 進行商務用 Skype Server 語音訊息, Microsoft 建議您先升級到商務用 Skype Server 2019, 然後再升級信箱。  否則, 語音訊息功能將會遺失。

如需規劃遷移的詳細資訊, 請參閱[規劃商務用 Skype Server 與 Exchange server 遷移](plan-um-migration.md)。

### <a name="migrating-a-previously-implemented-exchange-um-auto-attendant-system"></a>遷移先前實施的 Exchange UM 自動語音應答系統

我們目前不支援自動遷移至在 Exchange 2013 或2016中建立的 UM 自動語音應答系統雲端。 若要手動重新建立自動語音應答系統, 您必須:

1. 使用 Exchange admin powershell 命令來查看舊自動語音應答系統的結構, 包括任何嵌套的自動語音應答及呼叫佇列。  
2. 建立與每個 UM 自動語音應答節點相關聯的文字轉換語音腳本或錄製郵件的複本。
3. 針對每個自動語音應答節點建立內部部署端點, 包括將測試電話號碼和授權指派給物件。 請注意, 您現在可以指派線上服務 (例如電話系統) 所使用的內部部署電話號碼授權。
4. 使用商務用 Skype Online 和電話系統來執行新的雲端自動語音應答服務。 請參閱[設定資源帳戶](configure-onprem-ra.md)以取得詳細資料。 如此一來, 請上傳與每個 UM 自動語音應答節點相關聯的文字轉換語音腳本或錄製的訊息。
5. 測試雲端自動語音應答的功能。
6. 將指派給舊版 Exchange UM 自動語音應答的電話號碼重新指派給新建立的主雲端自動語音應答。

如需這些步驟的詳細資訊, 請參閱[將 EXCHANGE UM 自動語音應答或呼叫佇列移至電話系統](configure-onprem-ra.md#moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system)。

## <a name="additional-planning-resources"></a>其他規劃資源

標題為「小型企業」的教學課程[範例-設定自動](/microsoftteams/tutorial-org-aa)語音應答: 完成收集使用者需求之資訊的程式、規劃自動語音應答及使用者的結構 (以及可能通話佇列)、撰寫功能表提示, 以及在線上系統管理中心實施方案。 查看教學課程, 並使用這裡的練習來建立您的方案。

當您有符合您需求的實體結構, 以及能有效引導客戶的腳本時, 請繼續[設定資源帳戶](configure-onprem-ra.md)。

> [!CAUTION]
> 如[KB4480742](https://support.microsoft.com/en-us/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)所述, 不鼓勵將在伺服器2015中建立的 Exchange UM 自動語音應答移至執行伺服器2019的伺服器。 針對時間, 您必須將它們放在在 coexistance 模式下執行的商務用 Skype Server 2015 池。

## <a name="see-also"></a>請參閱

[規劃商務用 Skype Server 與 Exchange Server 遷移](plan-um-migration.md)

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面啟用自訂提示錄製](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)

Exchange UM:[自動接聽並傳送來電](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/automatically-answer-and-route-calls/automatically-answer-and-route-calls)

[規劃商務用 Skype Server 與 Office 365 之間的混合式連接](plan-hybrid-connectivity.md)

[在商務用 Skype Server 和 Office 365 之間設定混合式連接](configure-hybrid-connectivity.md)

[KB4480742: 將連絡人物件移至商務用 Skype Server 2019 後, 無法呼叫訂閱者存取或自動語音應答失敗並出現「500伺服器內部」錯誤](https://support.microsoft.com/help/4480742/call-failures-and-500-server-internal-error-after-migration-to-2019)
