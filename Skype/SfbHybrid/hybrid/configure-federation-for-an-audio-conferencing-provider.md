---
title: 在混合式部署中設定音訊會議提供者的同盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: '摘要: 瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。'
ms.openlocfilehash: faeae07c0662bc252e07bbf66ec463355e439461
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185461"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>在混合式部署中設定音訊會議提供者的同盟

**摘要:** 瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。

如果您想要在混合式部署中使用音訊會議提供者 (ACP), 您需要在內部部署和 ACP 夥伴之間設定同盟作為允許的合作夥伴伺服器。 您可以將 ACP 夥伴網域和 Edge 伺服器 (也稱為 [存取代理伺服器]) 新增到內部部署的 [聯盟網域] 清單中, 以設定同盟。 您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。 如需其他詳細資料, 請與您的 ACP 提供者聯繫。 您的 ACP 合作夥伴接著需要將內部部署邊緣伺服器池的 FQDN 新增到其允許的聯盟網域清單。

- **新增 ACP 網域和 Edge 伺服器作為允許的聯盟網域**

    若要將 ACP 網域新增為允許的夥伴伺服器 (允許聯盟網域), 請依照[設定支援的外部網域](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步驟操作。 針對 Edge 伺服器, 新增 ACP 合作夥伴邊緣伺服器的 FQDN。 您可能需要與您的 ACP 夥伴聯繫, 以取得其 Edge 伺服器的 FQDN, 您的 ACP 也可能會將其稱為存取 Proxy。

- **將 Edge 伺服器池的 FQDN 提供給 ACP 合作夥伴**

    ACP 合作夥伴需要設定同盟, 只要將 Edge 伺服器池的 FQDN 新增為允許的聯盟網域, 即可將您的內部部署網域新增為允許的合作夥伴伺服器。


