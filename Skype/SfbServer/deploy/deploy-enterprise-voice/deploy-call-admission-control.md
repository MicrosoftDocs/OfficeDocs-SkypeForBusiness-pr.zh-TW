---
title: 在商務用 Skype Server 中部署呼叫許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話許可控制 (CAC) 是一個方案, 可判斷是否可以根據可用頻寬建立即時會話, 以協助避免使用者在擁擠的網路上發生的音訊/視頻品質不佳。
ms.openlocfilehash: 0b2df103c432cd6b304f93b3a36af6e87c4bc2e7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233519"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中部署呼叫許可控制
 
通話許可控制 (CAC) 是一個方案, 可判斷是否可以根據可用頻寬建立即時會話, 以協助避免使用者在擁擠的網路上發生的音訊/視頻品質不佳。 如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>部署通話許可控制

1.  收集商業網路拓朴所需的所有資訊, 如範例所述[: 在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 如果您還沒有這麼做, 您必須定義網路區域和網站, 並將子網與網路網站建立關聯。 如需詳細資訊, 請參閱[在商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)。
    
3. 建立頻寬原則設定檔, 如在[商務用 Skype Server 中建立頻寬原則設定檔中](create-bandwidth-policy-profiles.md)的詳細資訊
    
4. 建立網路區域連結, 具體請見在[商務用 Skype Server 中建立網路區域連結](create-network-region-links.md)的詳細資訊。
    
5. 在[商務用 Skype Server 中建立網路 interregional 路由](create-network-interregional-routes.md), 以建立網路區域內路由的詳細資訊。
    
6. 建立網路站間原則, 具體請見在[商務用 Skype Server 中建立網路站間原則](create-network-intersite-policies.md)。
    
7. 啟用 [呼叫許可控制], 如在[商務用 Skype Server 的 [啟用呼叫許可控制](enable-call-admission-control.md)] 中詳細說明。
    
8. 檢查一些最終設定, 以確保所有專案都設定正確。 如需詳細資訊, 請參閱[呼叫許可控制部署: 適用于商務用 Skype Server 的最終檢查清單](final-checklist.md)。
    

