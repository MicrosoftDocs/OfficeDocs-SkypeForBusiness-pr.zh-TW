---
title: 在商務用 Skype Server 中建立網路站間原則
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 建立網路間策略, 這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。
ms.openlocfilehash: dceb48d0e87706d71de8c69b5622fbab468273b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190444"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路站間原則
 
建立網路間策略, 這些原則是由商務用 Skype Server 中的企業語音通話許可控制所使用。 
  
網路間原則: 定義在它們之間有直接 WAN 連結的網站之間的頻寬限制。
  
> [!IMPORTANT]
> *只有*在兩個網路網站之間有直接的交叉連結時, 才能使用網路間原則原則。
  
在北美的 [北美] 地區, Reno 和 Albuquerque 網站之間有直接連結。 這兩個網站需要一個網站間原則, 以套用適當的頻寬原則設定檔。 下列範例會套用20Mb_Link 設定檔。
  
### <a name="to-create-a-network-inter-site-policy"></a>建立網路站間原則原則

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行新的 CsNetworkInterSitePolicy Cmdlet 來建立網路間原則原則, 並針對有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。 例如，執行：
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 如有需要, 請重複步驟 2, 為所有具備直接交叉連結的網路網站組建立網路站間原則。
    
## <a name="see-also"></a>另請參閱

[新-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[移除-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
