---
title: 在商務用 Skype Server 中將位置原則新增至網路網站
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: 將 E9-1-1 位置原則指派給商務用 Skype Server 企業語音中的網路網站。
ms.openlocfilehash: ae35958d9ff95e32f129d3992d52145e3bef51b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848046"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a>在商務用 Skype Server 中將位置原則新增至網路網站
 
將 E9-1-1 位置原則指派給商務用 Skype Server 企業語音中的網路網站。 
  
下列範例顯示如何將在 [商務用 Skype Server 建立位置](create-location-policies.md)原則中定義的 **Redmond** 位置原則新增至現有的網路網站，以及如何建立使用 **Redmond** 位置原則的新網路網站。
  
如需使用網路網站的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：
  
- **New-CsNetworkSite**
    
- **Get-CsNetworkSite**
    
- **Set-CsNetworkSite**
    
- **Remove-CsNetworkSite**
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a>若要指派位置原則給現有網路網站

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列 Cmdlet 來修改現有的網路網站。
    
    將 **雷德蒙** 標位置原則指派給名為 **redmond** 的現有網路網站。
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a>若要指派位置原則給新的網路網站

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行下列 Cmdlet 來建立新的網路網站。
    
    在網路地區中建立新的網路網站，並指派具有 **Redmond** 標記的位置原則。
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


