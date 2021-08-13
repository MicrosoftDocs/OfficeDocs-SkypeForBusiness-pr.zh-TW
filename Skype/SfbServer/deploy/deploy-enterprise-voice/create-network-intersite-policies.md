---
title: 在商務用 Skype Server 中建立網路間原則
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
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: 建立網路間原則，以供商務用 Skype Server 中的企業語音通話許可控制使用。
ms.openlocfilehash: 8e5fb020ece1762868f9d943eb2aad955903b91329d636a981e644b2e9892b67
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54338751"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中建立網路間原則
 
建立網路間原則，以供商務用 Skype Server 中的企業語音通話許可控制使用。 
  
網路之間的網站間原則定義的頻寬限制是具有彼此的直接 WAN 連結的網站。
  
> [!IMPORTANT]
> 只有在兩個網站之間有直接的交叉連結時，  *才*  需要網路間原則。
  
在「北美地區」範例中，雷諾與阿布奎基網站之間有直接連結。 這兩個網站需要套用適當頻寬原則設定檔的網站間原則。 下列範例會套用20Mb_Link 設定檔。
  
### <a name="to-create-a-network-inter-site-policy"></a>建立網路間網站原則

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行 New-CsNetworkInterSitePolicy Cmdlet 來建立網路間原則，並為具有直接交叉連結的兩個網站套用適當的頻寬原則設定檔。 例如，執行：
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. 如有需要，請重複步驟2，為所有具有直接交叉連結的網站對建立網路間原則。
    
## <a name="see-also"></a>另請參閱

[新 CsNetworkInterSitePolicy](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[Get-CsNetworkInterSitePolicy](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[Set-CsNetworkInterSitePolicy](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[Remove-CsNetworkInterSitePolicy](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)