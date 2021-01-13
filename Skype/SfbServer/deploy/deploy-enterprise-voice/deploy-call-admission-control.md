---
title: 在商務用 Skype Server 中部署通話許可控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: 通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836883"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中部署通話許可控制
 
通話許可控制 (CAC) 是一種方案，可判斷即時會話是否可以根據可用的頻寬建立，以協助避免網路擁塞之使用者的音訊/視頻品質不良。 如需詳細資訊，請參閱 [在商務用 Skype Server 中規劃通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
### <a name="to-deploy-call-admission-control"></a>若要部署通話許可控制

1.  收集商業網路拓撲的所有必要資訊，如範例所述 [：在商務用 Skype Server 中收集通話許可控制需求](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)。
    
2. 若尚未這麼做，則必須定義網路地區和網站，並將子網與網站產生關聯。 如需詳細資訊，請參閱 [在商務用 Skype 中部署網路地區、網站和子網](deploy-network.md)。
    
3. 建立頻寬原則設定檔，如在[商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md)的詳細資訊
    
4. 建立網路地區連結，如 [在商務用 Skype Server 中建立網路地區連結](create-network-region-links.md)的詳細資訊。
    
5. 建立網路間區域路由，如在商務用 [Skype Server 中建立網路 interregional 路由](create-network-interregional-routes.md)的詳細資訊。
    
6. 建立網路站間原則，如在 [商務用 Skype Server 中建立網路網站間原則](create-network-intersite-policies.md)的詳細資訊。
    
7. 啟用通話許可控制，如 [在商務用 Skype Server 中啟用通話許可控制中](enable-call-admission-control.md)的詳細資訊。
    
8. 請查看一些最後的設定，以確保已正確設定所有專案。 如需詳細資訊，請參閱 [通話許可控制部署：商務用 Skype 伺服器的最終檢查清單](final-checklist.md)。
    

