---
title: 在商務用 Skype Server 中修改會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 摘要：瞭解如何在商務用 Skype Server 中修改會議原則。
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991808"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a>在商務用 Skype Server 中修改會議原則
 
**摘要：** 瞭解如何在商務用 Skype Server 中修改會議原則。
  
您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來修改會議原則。
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 的 [控制台] 修改會議原則

1. 從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。
    
2.  開啟商務用 Skype Server 的 [控制台]。
    
3. 在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。
    
4. 在會議原則清單中，按一下您要變更的原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯會議原則**] 中，修改任何原則設定，除了不能修改的原則名稱以外。
    
6. 按一下 [認可]****。
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>使用商務用 Skype Server Management Shell 來修改會議原則

若要修改會議原則，請使用**CsConferencingPolicy** Cmdlet。
  
下列範例會修改會議原則 SalesConferencingPolicy 的屬性值。 該命令會將 AllowConferenceRecording 屬性的值設定為 False：
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

如需詳細資訊（包括完整語法及參數清單），請參閱[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

