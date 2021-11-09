---
title: 在商務用 Skype Server 中修改會議原則
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議原則。
ms.openlocfilehash: 0c9b2f24fac8303a28f4e7408d23e950f5586785
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852077"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中修改會議原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中修改會議原則。
  
您可以使用商務用 Skype Server 控制台] 或使用商務用 Skype Server 管理命令介面，修改會議原則。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改會議原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 控制台]。
    
3. 在左導覽列中，按一下 [ **會議**]，然後按一下 [ **會議原則**]。
    
4. 在會議原則清單中，按一下您要變更的原則，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯會議原則**] 中，修改原則名稱以外的任何原則設定，但無法修改。
    
6. 按一下 **[認可]**。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server 管理命令介面修改會議原則

若要修改會議原則，請使用 **Set-CsConferencingPolicy** Cmdlet。
  
下列範例會修改會議原則 SalesConferencingPolicy 的屬性值。 此命令會將 AllowConferenceRecording 屬性的值設定為 False：
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

如需詳細資訊，包括完整的語法及參數清單，請參閱 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
