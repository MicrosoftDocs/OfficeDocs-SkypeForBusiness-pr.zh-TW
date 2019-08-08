---
title: 在商務用 Skype Server 中設定媒體旁路全域設定以使用網站和區域資訊
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 將 [旁路媒體] 設定為僅適用于商務用 Skype Server Enterprise Voice 中的特定網站和區域。
ms.openlocfilehash: 3bfb3dca6e53316d5c1de71abad976ae9223c787
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240284"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>在商務用 Skype Server 中設定媒體旁路全域設定以使用網站和區域資訊
 
將 [旁路媒體] 設定為僅適用于商務用 Skype Server Enterprise Voice 中的特定網站和區域。 
  
 如果您使用本主題中的步驟來設定媒體旁路的全域設定, 假設您在所有的商務用 Skype 端點和任何對等的用戶端, 都無法在幹線連線上設定媒體旁路。
  
> [!NOTE]
> 網路區域和網路網站資訊都是在 [呼叫許可控制] 中共用, 當兩個專案都啟用時, 媒體就會繞過高級企業語音功能。 因此, 如果您已設定 [通話許可控制], 則不需要您使用下列程式來編輯專門針對媒體旁路的網站和區域資訊。 如果您尚未設定 [通話許可控制] 的網路區域和網站, 且您想要變更媒體旁路設定, 請遵循此程式中的步驟。 
  
若要讓 [媒體旁路] 正常運作, 在拓撲建立器中定義的網站與在您設定網路區域和網路網站時所定義的網站, 都必須是一致性。 例如, 如果您在拓撲建立器中定義了一個已部署 PSTN 閘道的分支網站, 則必須使用企業語音原則來設定分支網站, 讓分支網站使用者能夠透過 PSTN 路由其 PSTN 通話分支網站上的閘道。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>若要設定媒體旁路的網站和區域資訊

1. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
2. 在左側導覽列中, 按一下 [**網路**設定]。
    
3. 在資料表中按兩下**全域**配置。
    
4. 在 [**編輯全域設定**] 頁面上, 選取 [**啟用旁路媒體**] 核取方塊。
    
5. 按一下 [**使用網站和地區**設定]。
    
6. 如有需要, 請選取 [為**未對應的網站啟用旁路**] 核取方塊。
    
    > [!NOTE]
    > 只有當您有一個或多個大型網站與不含頻寬限制 (例如大型中央網站) 的同一個區域相關聯時, 才選取此核取方塊, 但您還有一些與有頻寬的相同區域相關聯的分支網站限制. 當您針對未對應的網站啟用 [旁路] 時, 系統會簡化配置, 讓您只指定與分支網站相關聯的子網, 而不需要指定與所有網站相關聯的所有子網。 如果已啟用 [通話許可控制], 建議您不要選取此核取方塊。 
  
7. 按一下 [認可]****。
    
接著, 將子網新增至網路網站, 如[將子網與網路網站建立關聯](deploy-network.md#BKMK_AssociateSubnets)中所述。 將所有子網與網路網站建立關聯之後, 就會完成媒體略過部署。
> [!IMPORTANT]
> 如果您還沒有建立網路區域和網路網站, 您必須先建立這些區域, 才能繼續進行媒體旁路部署。 如需詳細資訊, 請參閱[在商務用 Skype 中部署網路區域、網站和子網](deploy-network.md)。 
  
## <a name="see-also"></a>另請參閱

[建立子網路與網路站台的關聯](deploy-network.md#BKMK_AssociateSubnets)

