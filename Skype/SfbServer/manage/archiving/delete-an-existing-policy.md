---
title: 在商務用 Skype Server 中刪除現有的存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要：瞭解如何刪除商務用 Skype Server 的存檔原則。
ms.openlocfilehash: 8e2a2c21f6d137fcdb87e69c041cf08143092be1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818925"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除現有的存檔原則

**摘要：** 瞭解如何刪除商務用 Skype Server 的存檔原則。
  
您可以刪除使用者原則或網站原則，但不能刪除全域原則。 如果您刪除全域原則，商務用 Skype 伺服器會自動將原則重設為預設值。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>使用 [控制台] 刪除原則

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
4. 在歸檔原則清單中，按一下您要刪除的使用者或網站原則，按一下 [**編輯**]，然後按一下 [**刪除**]。
    
5. 按一下 [認可]****。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 刪除原則

您也可以使用**CsArchivingPolicy** Cmdlet 刪除存檔原則。
  
例如，下列命令會刪除具有身分識別網站：雷德蒙的原則。 在網站層級設定的原則已刪除時，由「全域歸檔原則」所管理的使用者將會自動受全域存檔原則的管轄：
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

這個命令會移除已套用至每個使用者層級的所有存檔原則：
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

這個命令會移除已停用內部封存的所有存檔原則：
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

如需詳細資訊，請參閱[Remove CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) Cmdlet 的說明主題。
