---
title: 在商務用 Skype Server 中修改會議配置設定
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
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議配置設定。
ms.openlocfilehash: cf04c8c9d503f60b81d8016a2942bb62005f81f3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60770271"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中修改會議配置設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中修改會議配置設定。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，修改會議設定設定。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改會議配置設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議** 設定]。
    
4. 在會議設定清單中，按一下您要變更的設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯會議** 設定] 中，修改設定名稱以外的任何設定，但無法修改。
    
6. 按一下 **[認可]**。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面修改會議配置設定

若要修改會議配置設定，請使用 **Set-CsMeetingConfiguration** Cmdlet。
  
下列範例所示的命令會修改指派給 Redmond 網站 ( 身分識別 site： Redmond) 的會議設定設定。 在此情況下，DesignateAsPresenter 屬性的值會設定為 [所有人]：
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

如需詳細資訊，包括完整的參數清單，請參閱 [Set-CsMeetingConfiguration](/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
