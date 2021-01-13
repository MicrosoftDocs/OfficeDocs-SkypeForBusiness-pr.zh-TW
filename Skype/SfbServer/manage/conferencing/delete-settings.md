---
title: 在商務用 Skype Server 中刪除會議配置設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：瞭解如何在商務用 Skype Server 中刪除會議配置設定。
ms.openlocfilehash: 418ce7418be5a09658626491121dd2e2b3542110
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828177"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議配置設定。
  
您可以使用商務用 Skype Server 控制台或使用商務用 Skype Server 管理命令介面來刪除會議配置設定。
  
您可以刪除網站或使用者設定，但無法刪除全域設定。 如果您嘗試刪除全域設定，它會自動重設為預設值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台刪除會議配置設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。
    
4. 在會議設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面刪除會議設定設定

若要刪除會議設定，請使用 **Remove-CsMeetingConfiguration** Cmdlet。
  
下列命令會移除套用至 Redmond 網站的會議設定設定：
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

下一個命令會移除所有套用至網站範圍的會議設定設定：
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

如需詳細資訊，包括完整的參數清單，請參閱 [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

