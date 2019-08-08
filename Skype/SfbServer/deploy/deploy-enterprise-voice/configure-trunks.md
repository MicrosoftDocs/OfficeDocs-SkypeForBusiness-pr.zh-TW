---
title: 在商務用 Skype Server 中設定 trunks
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
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '摘要: 瞭解如何在商務用 Skype Server 的中繼伺服器與對等企業語音之間設定幹線。'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233851"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>在商務用 Skype Server 中設定 trunks
 
**摘要:** 瞭解如何在商務用 Skype Server 的中繼伺服器與對等企業語音之間設定幹線。
  
在企業語音部署中, 您可以設定在中繼伺服器與一或多個下列對等之間的幹線, 為貴組織中的企業語音用戶端和裝置提供公用交換電話網絡 (PSTN) 連線:
  
- 網際網路電話服務提供者 (ITSP) 的 SIP 中繼連線
    
- PSTN 閘道
    
- 私人分支 exchange (PBX)
    
如需詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃 PSTN](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)連線。
  
商務用 Skype Server 功能支援閘道與中繼伺服器之間的多個關聯性。 這些關聯是透過定義幹線來建立的, 這是中繼伺服器池與公用交換式電話網絡 (PSTN) 閘道、會話邊界控制器 (SBC) 或 IP PBX 之間的邏輯關聯。 使用 [拓撲建立器], 將閘道與中繼伺服器 (也就是 trunks) 建立關聯。
  
- 若要在商務用 Skype Server 中指派或移除主幹, 您必須先在拓撲產生器中定義主幹。 主幹包含下列關聯: 中繼伺服器的完整功能變數名稱 (FQDN)、中繼伺服器偵聽埠、閘道 FQDN, 以及閘道偵聽埠。
    
- 若要設定多個 trunks, 您可以在同一個閘道與中繼伺服器之間建立多個關聯性。 這可為企業語音結構提供額外的復原能力, 這在私人分支 exchange (PBX) interoperational 案例中特別有用。 
    
定義主幹時, 必須與路由建立關聯。 若要將主幹與路線建立關聯, 您可以在 [拓撲建立器] 中定義主幹的簡單名稱。 在商務用 Skype Server [控制台] 中, 此簡單名稱會用來做為主幹名稱, 其中 trunks 可以與路線建立關聯。 簡單的主幹名稱是從商務用 Skype Server Management Shell 中作為閘道名稱使用。 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

系統管理員必須選取與中繼伺服器相關聯的預設主幹。 從拓撲建立器, 以滑鼠右鍵按一下關聯的中繼伺服器, 然後按一下 [**屬性**]。 指定中繼伺服器的預設閘道。 
  

