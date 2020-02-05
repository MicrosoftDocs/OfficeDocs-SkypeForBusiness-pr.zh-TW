---
title: 設定混合式部署中的音訊會議提供者的同盟
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
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
description: 摘要： 了解如何在 Skype for Business Online 設定音訊會議提供者同盟。
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726883"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a>設定混合式部署中的音訊會議提供者的同盟

**摘要：** 了解如何在 Skype for Business Online 設定音訊會議提供者同盟。

如果您想要在混合式部署 （內部部署與線上） 中使用音訊會議提供者 (ACP)，您需要將您的內部部署和 ACP 夥伴之間的同盟設定為允許協力程式伺服器。 您可以設定同盟新增 Edge server （這也稱為 Access Proxy） 與 ACP 協力廠商網域到同盟網域清單為您的內部部署。 ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。 如需詳細資訊，請連絡您 ACP 提供者。 ACP 夥伴然後必須允許同盟的網域清單中新增您的內部部署 Edge Server 集區的 FQDN。

- **新增 Edge Server 與 ACP 網域為允許同盟網域**

    若要新增 ACP 網域為允許協力程式伺服器 （允許同盟網域），請遵循[設定支援允許的外部網域](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx)中的步驟。 針對 Edge Server] 新增 ACP 夥伴的 Edge Server 的 FQDN。 您可能需要您取得其 Edge Server，可能也會參照您 ACP 作為其 Access Proxy FQDN 的 ACP 合作夥伴連絡。

- **ACP 協力廠商提供 Edge Server 集區的 FQDN**

    ACP 合作夥伴必須設定為允許協力程式伺服器新增您的內部部署網域新增 Edge Server 集區的 FQDN，以允許同盟網域同盟。


