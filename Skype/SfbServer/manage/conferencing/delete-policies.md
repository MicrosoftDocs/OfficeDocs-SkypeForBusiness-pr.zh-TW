---
title: 在商務用 Skype Server 中刪除會議原則
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 摘要：瞭解如何在商務用 Skype Server 中刪除會議原則。
ms.openlocfilehash: d77910cb5fe39dcb47564b1b456a314ae03584a5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60773693"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除會議原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中刪除會議原則。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來刪除會議原則。
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台刪除會議原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。
    
4. 在會議原則清單中，按一下您要刪除的網站或使用者原則，按一下 [ **編輯**]，然後按一下 [ **刪除**]。
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面刪除會議原則

若要刪除會議原則，請使用 **Remove-CsConferencingPolicy** Cmdlet。
  
下列命令可移除具有 Identity RedmondConferencingPolicy 的會議原則：
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

下一個命令會刪除任何允許外部使用者錄製會議的會議原則：
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

如需詳細資訊，包括完整的語法及參數清單，請參閱 [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)。
