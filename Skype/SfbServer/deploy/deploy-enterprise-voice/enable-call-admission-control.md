---
title: 在商務用 Skype Server 中啟用通話許可控制
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 啟用商務用 Skype Server 企業語音中的通話許可控制。
ms.openlocfilehash: b35e55bbe0a9929222eb5d67f7449e2247cf91e0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60775773"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用通話許可控制
 
啟用商務用 Skype Server 企業語音中的通話許可控制。 
  
在設定通話許可控制部署的網路設定後，必須啟用 CAC，您的頻寬原則才能生效。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來啟用通話許可控制

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 執行 Set-CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。例如，執行：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    如果您要在網路中停用 CAC，請執行下列命令：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來啟用通話許可控制

1. 開啟商務用 Skype Server 控制台]。
    
2. 在左導覽列中，按一下 **[網路組態]**。
    
3. 按一下 **[通用]** 導覽按鈕。
    
4. 按一下清單中的 **[通用]**，然後選取 **[編輯]** 功能表上的 **[顯示詳細資料]**。
    
5. 在 **[編輯通用設定]** 頁面上，選取 **[啟用通話許可控制台]** 核取方塊。
    
    > [!NOTE]
    > 如果您要在整個部署中停用通話許可控制，請清除此核取方塊。 
  
6. 按一下 [認可]。 
    
## <a name="see-also"></a>另請參閱

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)