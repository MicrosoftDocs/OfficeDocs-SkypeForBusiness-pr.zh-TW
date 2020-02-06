---
title: 在商務用 Skype Server 中規劃 Edge 伺服器部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要：規劃商務用 Skype Server Edge 環境。 本主題將向您介紹邊緣概念，並讓您以更深入的主題進行組織。
ms.openlocfilehash: f19f00aab393ed94735f47f2e66ab0a2869d2d7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803363"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃 Edge 伺服器部署
 
**摘要：** 規劃商務用 Skype Server Edge 環境。 本主題將向您介紹邊緣概念，並讓您以更深入的主題進行組織。
  
當您在內部使用商務用 Skype Server 環境時，下一個步驟可能是將 Edge 伺服器或邊緣池引入環境。 如果您想要將商務用 Skype 伺服器所提供的服務供內部網路以外的人員使用，此角色將是至關重要的。 這些可能包括：
  
- 遠端使用者：暫時或以不間斷的方式進行非現場的員工。
    
- 聯盟使用者：您的合作夥伴組織的員工。
    
- 行動使用者。
    
- 您想要邀請加入會議和簡報的潛在客戶、合作夥伴甚至匿名使用者。
    
外部使用者存取權是指邊緣伺服器所提供的功能，可讓所有這些都發生。 您的內部使用者將能享用由您的商務用 Skype Server 部署所託管的下列服務：
  
- 通訊的 IM 和目前狀態：已授權的外部使用者可以在 IM 交談和會議中加入。 他們可以取得其他使用者的目前狀態資訊（也就是誰取得目前狀態資訊）。 如果您使用的是公用 IM 提供者，就不能執行多方會議，那就是完全對等通訊。 但支援 SIP 與 XMPP 通訊協定。
    
- 音訊/視頻（A/V）會議：獲授權的外部使用者可以參與商務用 Skype Server 音訊與視訊會議。
    
- 網路會議：您的授權外部使用者可以參與您的商務用 Skype 會議。 如果您想要的話，也可以為遠端使用者、同盟使用者及匿名使用者啟用參與。 公用 IM 使用者無法參與會議。 您也可以選擇讓這些使用者參與應用程式和桌面共用，甚至充當會議召集人或簡報者。
    
支援行動裝置存取，就像企業版語音一樣。 您可以邀請外部使用者參加您想要他們加入的會議，甚至是匿名使用者（如果您想要賦予他們許可權）。
  
如果這聽起來像是您組織所需的專案，則規劃 Edge 環境將是部署它的一個大協助。 如需進一步閱讀，我們有下列主題。

> [!NOTE]
> XMPP 閘道和 proxy 可在商務用 Skype Server 2015 中使用，但商務用 Skype Server 2019 已不再支援。 如需詳細資訊，請參閱[遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md)。 
  
## <a name="planning-topics"></a>規劃主題：

規劃文章包括：
  
- [商務用 Skype Server 2015 中的 Edge 伺服器系統需求](system-requirements.md)
    
- [商務用 Skype Server 2015 中的邊緣伺服器環境需求](edge-environmental-requirements.md)
    
- [商務用 Skype Server 2015 中的邊緣伺服器案例](scenarios.md)
    

