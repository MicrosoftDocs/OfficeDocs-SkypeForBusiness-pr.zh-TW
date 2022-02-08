---
title: 在商務用 Skype Server 中規劃 Edge Server 部署
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 摘要：規劃商務用 Skype Server Edge 環境。 本主題將向您介紹 Edge 概念，讓您瞭解更深入的主題。
ms.openlocfilehash: 97b34ba69be5a7461c1ff1f1847c66898b5dface
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387931"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>在商務用 Skype Server 中規劃 Edge Server 部署
 
**總結：** 規劃商務用 Skype Server Edge 環境。 本主題將向您介紹 Edge 概念，讓您瞭解更深入的主題。
  
當您有在內部運作的商務用 Skype Server 環境時，您可能需要將 edge Server 或 edge 集區引入環境。 如果您想讓商務用 Skype Server 所提供的服務供內部網路以外的人員使用，這個角色就很重要。 這些可能包括：
  
- 遠端使用者：暫時或以不間斷的方式進行異地的員工。
    
- 同盟使用者：您的夥伴組織的員工。
    
- 行動使用者。
    
- 您想要邀請參加會議及簡報的潛在客戶、合作夥伴甚至匿名使用者。
    
外部使用者存取權是指 Edge Server 所提供的內容，讓這一切都能做到。 您的內部使用者可以享用您的商務用 Skype Server 部署所主控的下列服務：
  
- 通訊的 IM 和目前狀態：已授權的外部使用者可以加入 IM 交談和會議。 使用者可以取得目前狀態資訊) 其他使用者 (的狀態資訊。 如果您是使用公用 IM 提供者（即「完全對等」通訊），將無法執行多方會議。 但同時支援 SIP 和 XMPP 通訊協定。
    
- 音訊/視頻 (A/V) 會議：授權的外部使用者可以參與您的商務用 Skype Server 音訊和視訊會議。
    
- Web 會議：您授權的外部使用者可以參與您的商務用 Skype 會議。 如果您願意，也可以為遠端使用者、同盟使用者和匿名使用者啟用參與。 公用 IM 使用者無法參與會議。 還有一些選項可讓這些使用者參與應用程式和桌面共用，甚至可充當會議召集人或簡報者。
    
支援行動裝置存取，企業語音。 如果您想要授與外部使用者的許可權，甚至匿名使用者也可以邀請外部使用者加入這些會議。
  
如果這聽起來像是您的組織需要的專案，則規劃 Edge 環境將會是部署它的一個重要説明。 為了進一步閱讀，我們有下列主題。

> [!NOTE]
> XMPP 的閘道和 proxy 可用於商務用 Skype Server 2015，但在商務用 Skype Server 2019 中已不再支援。 如需詳細資訊，請參閱 [遷移 XMPP 同盟](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 。 
  
## <a name="planning-topics"></a>規劃主題：

規劃文章包括：
  
- [商務用 Skype Server 2015 中的 Edge Server 系統需求](system-requirements.md)
    
- [商務用 Skype Server 2015 中的 Edge Server 環境需求](edge-environmental-requirements.md)
    
- [商務用 Skype Server 2015 中的 Edge Server 案例](scenarios.md)
    

