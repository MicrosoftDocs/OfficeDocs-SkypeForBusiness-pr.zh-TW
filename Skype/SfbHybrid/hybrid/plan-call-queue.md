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
description: 在商務用 Skype Server 2019 中使用雲端自動語音應答的概覽。
ms.openlocfilehash: 62731691f4e56c923d2dd8fa6057f244776ec65b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110489"
---
# <a name="plan-cloud-call-queues"></a>規劃雲端通話佇列

雲端通話佇列是一種服務，可接受客戶的來電、播放問候語訊息，然後在等候佇列中進行這些呼叫，然後搜尋預先設定的代理程式清單，以接聽這些呼叫。 您可以在啟用郵件功能的通訊群組清單或安全性群組中定義一組代理人。 您的組織可以有一或多個通話佇列。 通話佇列通常會與自動語音應答一起使用。

此外，雲端通話佇列可以提供：

- 來電者等候通話時的音樂
- 通話佇列的自訂設定大小上限、timeout 及通話處理選項

為每個通話佇列指派一個 **資源帳戶** (請參閱設定商務用 Skype Server 2019 系統上) 的 [資源帳戶](configure-onprem-ra.md) ，此系統會直接連結到 Microsoft 團隊系統管理中心中的呼叫佇列。 如需通話佇列的詳細資訊，以及通話佇列的選項及功能，請參閱 [Create a 雲端通話佇列](/MicrosoftTeams/create-a-phone-system-call-queue) 。

> [!NOTE]
> 您可以將多個電話號碼指派給通話佇列，但必須是 Microsoft 服務號碼、直接路由號碼或混合號碼。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署商務用 Skype Server 2019。  您的需求取決於您的案例：

- 若為雲端通話佇列的新設定，請遵循 [設定資源帳戶](configure-onprem-ra.md)中所述的步驟。 您必須在線上或商務用 Skype Server 2019 中建立資源帳戶，而且您可能還需要將電話號碼與通話佇列相關聯。

除了上述需求之外，還必須設定下列需求，才能連線至 Microsoft 雲端通話佇列服務：

- 混合連接。 如果您已部署商務用 Skype Server，而您想要為您的內部部署使用者啟用雲端通話佇列，您必須確定您的內部部署與線上環境之間已設定混合式連線能力。 這有時稱為分割網域設定。

   如需詳細資訊，請參閱 [規劃商務用 Skype server 與 microsoft 365 或 office 365 之間的混合](plan-hybrid-connectivity.md) 式連線，以及 [設定商務用 Skype server 與 Microsoft 365 或 office 365 的混合](configure-hybrid-connectivity.md)式連線。

- 若要將電話號碼指派給資源帳戶，您現在可以使用「成本免費電話系統虛擬使用者」授權。 這為組織層級的電話號碼提供電話系統功能，並讓您建立自動語音應答及通話佇列功能。

- 針對每個通話佇列建立內部部署 [資源帳戶](configure-onprem-ra.md) ，並視需要指派授權和電話號碼。  

當您具有符合您需求的實體結構，以及可有效指導客戶有效的腳本時，請繼續  [設定資源帳戶](configure-onprem-ra.md)。

## <a name="see-also"></a>另請參閱

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面錄製自訂提示](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](plan-hybrid-connectivity.md)

[設定商務用 Skype Server 與 Microsoft 365 或 Office 365 的混合式連線](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理資源帳戶](/MicrosoftTeams/manage-resource-accounts)