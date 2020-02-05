---
title: 在商務用 Skype Server 中設定媒體旁路，以永遠略過中繼伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 在商務用 Skype Server Enterprise Voice 中啟用媒體旁路，以永遠略過轉送伺服器。
ms.openlocfilehash: cde2a1bff41016e05ac6c74978fa65b45f11a1e7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768266"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>在商務用 Skype Server 中設定媒體旁路，以永遠略過中繼伺服器
 
在商務用 Skype Server Enterprise Voice 中啟用媒體旁路，以永遠略過轉送伺服器。 
  
 如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在商務用 Skype 端點和任何對等的使用者都有良好的連線能力，您可以在主幹連線上設定媒體旁路。
  
如果您在商務用 Skype 端點與所有對等都已啟用媒體旁路的中繼伺服器之間沒有良好的連線性，您必須設定全域媒體旁路設定，才能使用網站和區域資訊使用 [媒體旁路]。 這可讓您在判斷媒體繞過中繼伺服器的時間進行更多控制。 若要這樣做，請使用 [在[商務用 Skype 伺服器中設定媒體旁路全域設定] 中的步驟，以使用網站和區域資訊](use-site-and-region-information.md)，並改為[將子網與網路網站建立關聯](deploy-network.md#BKMK_AssociateSubnets)。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>若要讓媒體不使用全域方式，就能一直略過中繼伺服器

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中，按一下 [**網路**設定]。
    
3. 按兩下清單中的**全域**配置。
    
4. 在 [**編輯全域設定**] 頁面上，選取 [**啟用旁路媒體**] 核取方塊。
    
5. 按一下 [**永遠略過**]。
    
6. 按一下 [認可]****。
    
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[在商務用 Skype Server 中部署媒體旁路](deploy-media-bypass.md)

