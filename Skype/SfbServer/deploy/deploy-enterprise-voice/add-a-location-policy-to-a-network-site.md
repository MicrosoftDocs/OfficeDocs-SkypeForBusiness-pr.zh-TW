---
title: 在商務用 Skype Server 中新增位置原則至網路網站
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 在商務用 Skype Server Enterprise Voice 中, 為網路網站指派 E9-1-1 位置原則。
ms.openlocfilehash: 3653811298e7ce5659d4d416798010b3ac427732
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193887"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>在商務用 Skype Server 中新增位置原則至網路網站
 
在商務用 Skype Server Enterprise Voice 中, 為網路網站指派 E9-1-1 位置原則。 
  
下列範例示範如何將在 [商務用 Skype 伺服器] 的 [[建立位置原則](create-location-policies.md)] 中定義的**雷蒙德**位置原則新增到現有的網路網站, 以及如何建立使用**雷蒙德**位置原則的新網路網站。
  
如需使用網路網站的詳細資訊, 請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔:
  
- **新-CsNetworkSite**
    
- **CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **移除-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>將位置原則指派給現有的網路網站

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行下列 Cmdlet 來修改現有的網路網站。
    
    將**雷德蒙**標記的位置原則指派給名為 [**雷蒙德**] 的現有網路網站。
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>將位置原則指派給新的網路網站

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行下列 Cmdlet 以建立新的網路網站。
    
    在網路區域中建立新的網路網站, 並指派**雷德蒙**標記的位置原則。
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


