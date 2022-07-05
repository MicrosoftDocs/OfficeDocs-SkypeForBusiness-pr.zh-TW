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
ms.localizationpriority: medium
ms.collection: ''
description: 使用雲端自動語音應答與 商務用 Skype Server 2019 的概觀。
ms.openlocfilehash: df8013a4abc2029d585032b3d0bce810175e04f4
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615419"
---
# <a name="plan-cloud-call-queues"></a>規劃雲端通話佇列

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

雲端通話佇列是一項服務，可接受客戶通話、播放問候訊息，然後在搜尋預先設定的代理程式清單以接聽這些通話時，將這些通話放在等候佇列中。 您可以在擁有郵件功能的通訊群組清單或安全性群組中定義一組代理程式。 您的組織可以有一或多個通話佇列。 通話佇列通常與自動語音應答搭配使用。

此外，雲端通話佇列可以提供：

- 來電者在等候等候時播放音樂
- 通話佇列大小上限、逾時和通話處理選項的自訂設定

每個通話佇列都會獲指派 **資源帳戶** (請參閱在您的 商務用 Skype Server 2019 系統上設定 [資源帳戶](configure-onprem-ra.md)) ，該帳戶會直接連結至 Microsoft Teams 系統管理中心的通話佇列。 如需通話 [佇列](/MicrosoftTeams/create-a-phone-system-call-queue) 的詳細資訊，以及通話佇列有哪些選項和功能，請參閱建立雲端通話佇列。

> [!NOTE]
> 您可以將多個電話號碼指派給通話佇列，但必須是 Microsoft 服務號碼、直接路由號碼或混合式號碼。

## <a name="requirements"></a>需求

下列需求假設您已在支援的拓撲中部署 商務用 Skype Server 2019。  您的需求取決於您的案例：

- 如需新的雲端通話佇列設定，請遵循設定 [資源帳戶](configure-onprem-ra.md)中所述的步驟。 您必須在線上或在 2019 商務用 Skype Server建立資源帳戶，而且您可能也需要將電話號碼與通話佇列產生關聯。

除了上述需求之外，還必須將下列需求設定為連線到 Microsoft Cloud 通話佇列服務：

- 混合式連線能力。 如果您已部署商務用 Skype Server，而且想要為內部部署使用者啟用雲端通話佇列，則必須確定您已在內部部署與線上環境之間設定混合式連線。 這有時稱為分割網域組態。

   如需詳細資訊，請參閱[規劃 商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式聯](plan-hybrid-connectivity.md)機，以及設定[商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](configure-hybrid-connectivity.md)。

- 如果您要將電話號碼指派給資源帳戶，您現在可以使用免費 **Microsoft Teams 電話資源帳戶** 授權。 這可為組織層級的電話號碼提供電話系統功能，並可讓您建立自動語音應答和通話佇列功能。

- 為每個通話佇列建立內部部署 [資源帳戶](configure-onprem-ra.md) ，並視需要指派授權和電話號碼。  

當您有符合需求的穩固結構，以及有效率地引導客戶的腳本時，請繼續設定  [資源帳戶](configure-onprem-ra.md)。

## <a name="see-also"></a>另請參閱

[設定資源帳戶](configure-onprem-ra.md)

[使用電話使用者介面錄製自訂提示](/exchange/voice-mail-unified-messaging/greetings-announcements-menus-and-prompts/enable-custom-prompt-recording)

[什麼是雲端自動語音應答？](/SkypeForBusiness/what-is-phone-system-in-office-365/what-are-phone-system-auto-attendants)

[設定雲端自動語音應答](/MicrosoftTeams/create-a-phone-system-auto-attendant)

[規劃商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](plan-hybrid-connectivity.md)

[設定 商務用 Skype Server 與 Microsoft 365 或 Office 365 之間的混合式連線](configure-hybrid-connectivity.md)

[在 Microsoft Teams 中管理資源帳戶](/MicrosoftTeams/manage-resource-accounts)