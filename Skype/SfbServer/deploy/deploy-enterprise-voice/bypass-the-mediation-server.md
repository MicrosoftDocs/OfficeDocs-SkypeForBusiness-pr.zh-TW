---
title: 設定商務用 Skype Server 中的媒體旁路，以永遠略過轉送伺服器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 啟用媒體旁路，以在商務用 Skype Server 企業語音中永遠略過轉送伺服器。
ms.openlocfilehash: ef6bf5b68e5d333b1786b6fc6237784b4f5395f0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392235"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>設定商務用 Skype Server 中的媒體旁路，以永遠略過轉送伺服器
 
啟用媒體旁路，以在商務用 Skype Server 企業語音中永遠略過轉送伺服器。 
  
 如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在商務用 Skype 端點和任何對等的使用者之間，您已設定主幹連線上的媒體旁路。
  
如果您在商務用 Skype 端點和所有對等之間沒有良好的連線能力，且其各自的主幹連線已啟用媒體旁路，您必須設定全域媒體旁路設定，以在使用媒體旁路時使用網站與地區資訊。 如此可對媒體略過中繼伺服器的時機有更精確的控制。 若要這麼做，請使用在[商務用 Skype Server 中設定媒體旁路全域設定中的步驟，使用網站與地區資訊](use-site-and-region-information.md)，並改為[將子網與網路網站產生關聯](deploy-network.md#BKMK_AssociateSubnets)。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>全面啟用媒體旁路以永遠略過中繼伺服器

1. 開啟商務用 Skype Server 控制台]。
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 按兩下清單中的 **[全域]** 設定。
    
4. 在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。
    
5. 按一下 **[永遠略過]**。
    
6. 按一下 **[認可]**。
    
## <a name="see-also"></a>另請參閱

[在商務用 Skype 中規劃媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[在商務用 Skype Server 中部署媒體旁路](deploy-media-bypass.md)

