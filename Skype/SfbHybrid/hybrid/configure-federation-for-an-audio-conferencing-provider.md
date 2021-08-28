---
title: 為混合式部署中的音訊會議提供者設定同盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 摘要：瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。
ms.openlocfilehash: 25bd691186d5d37dc272b420e68bb71a7d181de1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597887"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>為混合式部署中的音訊會議提供者設定同盟

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


**摘要：** 瞭解如何在商務用 Skype Online 中設定音訊會議提供者的同盟。

如果您想要在混合部署中使用音訊會議提供者 (ACP)  (內部部署與線上) ，您必須設定內部部署與 ACP 夥伴之間的同盟為允許的夥伴伺服器。 您可以新增 ACP partner domain 及 Edge server (此設定同盟也稱為存取 Proxy) 內部部署的同盟網域清單。 您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。 如需其他詳細資料，請與您的 ACP 提供者聯繫。 您的 ACP 合作夥伴必須將您的內部部署 Edge Server 集區的 FQDN 新增至其允許的同盟網域清單。

- **將 ACP 網域和 Edge Server 新增為允許的同盟網域**

    若要將 ACP 網域新增為允許的同盟伺服器 (允許的同盟網域) ，請依照 [Configure Support for The 允許的外部網域](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)中的步驟進行。 針對 Edge Server，新增 ACP partner Edge Server 的 FQDN。 您可能需要聯繫 ACP 合作夥伴，以取得其 Edge Server 的 FQDN，而您的 ACP 也可能會將其稱為存取 Proxy。

- **提供 Edge Server 集區的 FQDN 至 ACP partner**

    ACP 合作夥伴必須將 Edge Server 集區的 FQDN 新增為允許的同盟網域，才能設定同盟以將您的內部部署網域新增為允許的夥伴伺服器。