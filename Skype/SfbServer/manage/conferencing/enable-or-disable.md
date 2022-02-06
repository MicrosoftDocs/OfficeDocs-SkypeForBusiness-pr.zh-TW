---
title: 啟用或停用商務用 Skype Server 中的電話撥入式會議
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要：瞭解如何使用控制台或管理命令介面來啟用或停用商務用 Skype Server 中的電話撥入式會議。
---

# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的電話撥入式會議
 
**總結：** 瞭解如何使用控制台或管理命令介面來啟用或停用商務用 Skype Server 中的電話撥入式會議。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面來啟用電話撥入式會議。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台來啟用或停用電話撥入式會議

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。
    
4. 在會議原則清單中，選取要啟用電話撥入式會議的原則，然後按一下 **[編輯]**，再按一下 **[顯示詳細資料]**。 
    
5. 若要允許使用者藉由撥入電話來加入會議，請勾選 **[啟用 PSTN 電話撥入式會議]** 核取方塊。根據預設，使用者可以使用公用交換電話網路 (PSTN) 來撥入會議。
    
6. 按一下 **[認可]**。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面來啟用或停用電話撥入式會議

若要啟用或停用電話撥入式會議，請使用具有 EnableDialInConferencing 參數的 **Set-CsConferencingPolicy** Cmdlet，如下所示：
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

如需詳細資訊，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
