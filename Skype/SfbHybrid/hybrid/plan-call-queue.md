---
title: 規劃雲端通話佇列
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: wasseemh
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 在商務用 Skype Server 2019 中使用雲端自動 Attendant 概觀。
ms.openlocfilehash: 629c28e752b7316a3d2e7fda0acf7f457788d6a8
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918739"
---
# <a name="plan-cloud-call-queues"></a>規劃雲端通話佇列

雲端通話佇列是一種服務，可接受客戶通話、播放問候訊息，然後在搜尋預先配置的代理程式清單時，將這些通話排入等候佇列以接聽這些通話。 您可以在已啟用郵件功能的通訊群組清單或安全性群組中定義一組代理程式。 您的組織可以有一或多個通話佇列。 通話佇列通常會與自動參與人員搭配使用。

此外，雲端通話佇列也可提供：

- 當來電者等候等候時播放音樂
- 自訂通話佇列最大大小、超時及來電處理選項的設定

每個通話佇列都會被指派一個資源帳戶 **(** 請參閱在商務用 Skype Server 2019 系統上設定資源帳戶 [) ，](configure-onprem-ra.md) 這個帳戶會直接連結到 Microsoft Teams 系統管理中心的通話佇列。 請參閱 [建立雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue) ，以進一步瞭解什麼是通話佇列，以及通話佇列可用的選項和功能。

> [!NOTE]
> 您可以將多個電話號碼指派給通話佇列，但這些號碼必須是 Microsoft 服務號碼、直接路由號碼或混合式號碼。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。  您的需求視您的案例而不同：

- 若要設定新的雲端通話佇列設定，請遵循設定資源帳戶 [中列出的步驟](configure-onprem-ra.md)。 您必須在線上或商務用 Skype Server 2019 中建立資源帳戶，而且您可能也需要將電話號碼與通話佇列建立關聯。

除了上述要求之外，必須針對下列需求進行配置，以連接至 Microsoft Cloud 通話佇列服務：

- 混合式連接。 如果您已經部署商務用 Skype Server，而且想要為內部部署使用者啟用雲端通話佇列，您必須確保您的內部部署和線上環境之間已設定混合式連線。 這有時稱為分割網域組配置。

   詳細資訊請參閱規劃商務用 Skype Server 與 [Microsoft 365 或 Office 365](plan-hybrid-connectivity.md) 之間的混合式連接，以及設定商務用 Skype Server 與 [Microsoft 365 或 Office 365](configure-hybrid-connectivity.md)之間的混合式連接。

- 如果您要將電話號碼指派給資源帳戶，現在可以使用無成本的電話系統虛擬使用者授權。 這提供組織層級的電話號碼的電話系統功能，並可讓您建立自動撥打和通話佇列功能。

- 為每個 [通話佇列建立](configure-onprem-ra.md) 內部部署資源帳戶，並指派授權和電話號碼 ，如果需要。  

當您擁有符合您需求的實心結構，以及可有效率地引導客戶的腳本時，請繼續設定  [資源帳戶](configure-onprem-ra.md)。

## <a name="see-also"></a>另請參閱

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面錄製自訂提示](https://docs.microsoft.com/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](plan-hybrid-connectivity.md)

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連接](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理資源帳戶](/MicrosoftTeams/manage-resource-accounts)
