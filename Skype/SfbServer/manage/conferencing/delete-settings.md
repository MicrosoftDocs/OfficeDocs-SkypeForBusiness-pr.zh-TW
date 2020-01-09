---
title: 刪除商務用 Skype Server 中的會議設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 摘要：瞭解如何在商務用 Skype Server 中刪除會議配置設定。
ms.openlocfilehash: cbf63ba635077dd61599d4bc84a740906b662a6c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991858"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a>刪除商務用 Skype Server 中的會議設定設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議配置設定。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server 管理命令介面，刪除會議設定設定。
  
您可以刪除網站或使用者設定，但無法刪除全域配置。 如果您嘗試刪除全域設定，系統會自動將其重設為預設值。
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 刪除會議設定設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。
    
4. 在會議設定清單中，按一下您要刪除的網站或池設定，按一下 [**編輯**]，然後按一下 [**刪除**]。
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 刪除會議設定設定

若要刪除會議設定，請使用**CsMeetingConfiguration** Cmdlet。
  
下列命令會移除套用至雷德蒙網站的會議設定設定：
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

[下一步] 命令會移除所有套用至網站範圍的會議設定：
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

如需詳細資訊（包括完整的參數清單），請參閱[移除-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps)。
  

