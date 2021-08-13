---
title: 在商務用 Skype Server 中設定媒體旁路通用設定以使用網站與地區資訊
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 設定媒體旁路，只用于商務用 Skype Server 企業語音中的特定網站和地區。
ms.openlocfilehash: 38fa42374b4b5dd8c8f304de04c9beeb59f2635d955b2e9ee5afb1fb16de7789
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322335"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>在商務用 Skype Server 中設定媒體旁路通用設定以使用網站與地區資訊
 
設定媒體旁路，只用于商務用 Skype Server 企業語音中的特定網站和地區。 
  
 如果您使用本主題中的步驟來設定媒體旁路的全域設定，假設您在所有的商務用 Skype 端點和您在主幹連線上設定媒體旁路的任何對等機之間沒有良好的連線能力。
  
> [!NOTE]
> 若已啟用通話許可控制與媒體旁路進階 Enterprise Voice 功能，則網路地區和網路網站資訊會由這兩項功能共用。因此，如果您已經設定通話許可控制，則不需要使用下列程序特別針對媒體旁路來編輯網站與地區資訊。如果您尚未設定通話許可控制的網路地區和網站，而想要變更媒體旁路設定，請遵循此程序中的步驟。 
  
若要讓媒體旁路正常運作，在拓撲產生器中定義的網站與設定網路地區和網站時所定義的網站之間，必須是一致的一致性。 例如，如果您已在拓撲產生器中定義的分支網站，只部署了 PSTN 閘道，則該分支網站必須設定企業語音原則，讓分支網站使用者能夠透過分支網站的 pstn 閘道路由傳送 pstn 電話。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>設定媒體旁路的網站與地區資訊

1. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 連按兩下表格中的 **[全域]** 組態。
    
4. 在 **[編輯通用設定]** 頁面上，選取 **[啟用媒體旁路]** 核取方塊。
    
5. 按一下 **[使用網站和地區設定]**。
    
6. 如有必要，請選取 **[啟用非對應網站的旁路]** 核取方塊。
    
    > [!NOTE]
    > 如果您有一或多個與相同區域關聯的大型網站沒有頻寬限制 (例如，大型中央網站)，但也有一些與相同區域關聯的分支網站具有頻寬限制，請選取此核取方塊。當您啟用非對應網站的旁路時，設定作業比較精簡，因為您只需指定與分支網站關聯的子網路，而不需指定與所有網站關聯的所有子網路。如果已啟用通話許可控制，則建議您不要選取此核取方塊。 
  
7. 按一下 **[認可]**。
    
接下來，將子網新增至網站（如 [將子網與網路網站關聯](deploy-network.md#BKMK_AssociateSubnets)）中所述。 將所有子網與網站建立關聯之後，媒體旁路部署即完成。
> [!IMPORTANT]
> 如果您尚未建立網路地區和網路網站，您必須先予以建立，才能繼續進行媒體旁路部署。 如需詳細資訊，請參閱[在商務用 Skype 中部署網路地區、網站和子網](deploy-network.md)。 
  
## <a name="see-also"></a>另請參閱

[建立子網與網路網站的關聯](deploy-network.md#BKMK_AssociateSubnets)

