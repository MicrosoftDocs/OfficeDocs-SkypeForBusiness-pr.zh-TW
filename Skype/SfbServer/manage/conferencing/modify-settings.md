---
title: 在商務用 Skype Server 中修改會議設定設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d1f9ac-0029-429b-be2b-d7591abfc192
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議設定設定。
ms.openlocfilehash: 2e9d8a737a2bfc48cdcbe39540a22e4c236003b3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992850"
---
# <a name="modify-meeting-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中修改會議設定設定
 
**摘要：** 瞭解如何在商務用 Skype Server 中修改會議設定設定。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來修改會議設定設定。
  
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改會議設定設定

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議配置**]。
    
4. 在會議配置清單中，按一下您要變更的設定，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯會議**設定] 中，修改任何設定的設定，除了不能修改的配置名稱。
    
6. 按一下 [認可]****。
    
## <a name="modify-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改會議設定設定

若要修改會議設定設定，請使用**CsMeetingConfiguration** Cmdlet。
  
下列範例所示的命令會修改指派給雷德蒙者網站（身分識別網站：雷蒙德）的會議設定設定。 在這種情況下，DesignateAsPresenter 屬性的值會設定為 [所有人]：
  
```PowerShell
Set-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

如需詳細資訊（包括完整的參數清單），請參閱[設定 CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps)。
  

