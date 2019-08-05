---
title: 規劃雲端通話佇列
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動語音應答的概覽。
ms.openlocfilehash: bcb1f14ed9dfc3471b146a318a97700c362f115c
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2019
ms.locfileid: "36185542"
---
# <a name="plan-cloud-call-queues"></a>規劃雲端通話佇列

雲端通話佇列是一項服務, 可接受客戶來電、播放問候語訊息, 然後在等待佇列中進行這些呼叫, 然後搜尋預先設定的代理程式清單來應答這些來電。 您可以在已啟用郵件功能的通訊群組清單或安全性群組中定義一組代理程式。 貴組織可以有一個或多個通話佇列。 通話佇列通常與自動語音應答搭配使用。

此外, 雲端通話佇列可以提供:

- 在呼叫者等待保留時的音樂
- 通話佇列的自訂設定大小上限、超時及呼叫處理選項

每個通話佇列都會獲指派**資源帳戶**(請參閱在商務用 Skype Server 2019 系統上[設定資源](configure-onprem-ra.md)帳戶), 該系統會直接連結到 Microsoft 團隊系統管理中心的呼叫佇列。 如需通話佇列的用途, 以及呼叫佇列的選項和功能, 請參閱[建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue)。

> [!NOTE]
> 您可以將多個電話號碼指派給通話佇列, 但必須是 Microsoft 服務號碼或混合式號碼。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。  您的需求取決於您的案例:

- 針對雲端呼叫佇列的新設定, 請按照[設定資源帳戶](configure-onprem-ra.md)中所述的步驟進行。 您將需要在線上或商務用 Skype Server 2019 中建立資源帳戶, 而且您可能也需要將電話號碼與通話佇列建立關聯。

除了上述需求之外, 下列需求必須設定為連線至 Microsoft 雲端通話佇列服務:

- 混合式連線性。 如果您已部署商務用 Skype Server, 且想要為您的內部部署使用者啟用雲端通話佇列, 您必須確保您在內部部署與線上環境之間有混合式連線性設定。 這有時稱為分割網域配置。

   如需詳細資訊, 請參閱[規劃商務用 Skype server 與 office 365 之間的混合式連接](plan-hybrid-connectivity.md), 以及[設定商務用 Skype 伺服器與 office 365 之間的混合](configure-hybrid-connectivity.md)式連線。

- 如果您要將電話號碼指派給資源帳戶, 您現在可以使用 [免付費電話系統虛擬使用者授權]。 這會提供手機系統功能給組織階層的電話號碼, 並可讓您建立自動語音應答及呼叫佇列功能。

- 針對每個通話佇列建立內部部署[資源帳戶](configure-onprem-ra.md), 並視需要指派授權和電話號碼。  

## <a name="additional-planning-resources"></a>其他規劃資源

標題為「小型企業」的教學課程[範例-設定自動](/microsoftteams/tutorial-org-aa)語音應答: 完成收集使用者需求之資訊的程式、規劃自動語音應答及使用者的結構 (以及可能通話佇列)、撰寫功能表提示, 以及在線上系統管理中心實施方案。 查看教學課程, 並使用 [在此練習] 建立您的方案。

當您有符合您需求的實體結構, 以及能有效引導客戶的腳本時, 請繼續[設定資源帳戶](configure-onprem-ra.md)。

## <a name="see-also"></a>請參閱

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面啟用自訂提示錄製](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[規劃商務用 Skype Server 與 Office 365 之間的混合式連接](plan-hybrid-connectivity.md)

[在商務用 Skype Server 和 Office 365 之間設定混合式連接](configure-hybrid-connectivity.md)

[管理 Microsoft 團隊中的資源帳戶](/MicrosoftTeams/manage-resource-accounts)
