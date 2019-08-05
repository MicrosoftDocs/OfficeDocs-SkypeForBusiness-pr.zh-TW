---
title: 在商務用 Skype Server 中啟用呼叫許可控制
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
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 在商務用 Skype Server Enterprise Voice 中啟用 [通話許可控制]。
ms.openlocfilehash: ed770a79a7237de682822e8280a13de4516921ec
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192076"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用呼叫許可控制
 
在商務用 Skype Server Enterprise Voice 中啟用 [通話許可控制]。 
  
在您設定 [通話許可控制] 部署的網路設定之後, 您必須啟用 CAC, 才能使您的頻寬原則生效。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management 命令介面啟用呼叫許可控制

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 執行 CsNetworkConfiguration Cmdlet 以在您的網路中啟用 CAC。 例如，執行：
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    如果您想要在網路中停用 CAC, 請執行下列動作:
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 啟用呼叫許可控制

1. 開啟商務用 Skype Server 的 [控制台]。
    
2. 在左側導覽列中, 按一下 [**網路**設定]。
    
3. 按一下 [**全域**導覽] 按鈕。
    
4. 按一下清單中的 [**全域**], 然後選取 [**編輯**] 功能表上的 [**顯示詳細資料**]。
    
5. 在 [**編輯全域設定**] 頁面上, 選取 [**啟用通話許可控制**] 核取方塊。
    
    > [!NOTE]
    > 如果您想要在整個部署中停用 [呼叫許可控制], 請清除此核取方塊。 
  
6. 按一下 [認可]****。 
    
## <a name="see-also"></a>另請參閱

[CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[移除-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
