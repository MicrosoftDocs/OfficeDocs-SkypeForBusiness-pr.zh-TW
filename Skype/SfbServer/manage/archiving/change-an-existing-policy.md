---
title: 在商務用 Skype Server 中變更現有的存檔原則
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：瞭解如何變更商務用 Skype Server 的使用者歸檔原則。
ms.openlocfilehash: 010365b5805517db8f40aa7e3e839fdb15115c06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818985"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中變更現有的存檔原則
 
**摘要：** 瞭解如何變更商務用 Skype Server 的使用者歸檔原則。
  
當您第一次部署商務用 Skype Server 時，您會設定初始的存檔原則，決定如何針對您的部署中的使用者執行封存。 本主題說明如何管理及修正原則。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用 [控制台] 變更存檔原則

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
4. 在原則清單中，執行下列其中一項操作： 
    
   - 若要變更整個部署的原則，請在原則清單中按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
   - 若要變更單一網站的原則，請在原則清單中按一下該網站的名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
   - 若要變更單一使用者或使用者群組的原則，請在原則清單中按一下 [使用者] 或 [使用者組名]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯存檔原則**] 頁面上，執行下列動作：
    
   - 若要啟用或停用原則的內部存檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
   - 若要啟用或停用原則的外部封存，請選取或清除 [封存**外部通訊**] 核取方塊。
    
6. 按一下 [認可]****。
    
    > [!IMPORTANT]
    > 使用者原則的設定只會套用到您要套用原則的特定使用者和使用者群組。 如需詳細資訊，請參閱[將存檔原則套用到商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 變更存檔原則

您也可以使用 Windows PowerShell **CsArchivingPolicy** Cmdlet 變更存檔原則。
  
### <a name="enable-archiving-policies"></a>啟用存檔原則

若要啟用內部通訊會話的歸檔，請將 ArchiveInternal 參數的值設定為 True （$True）： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

若要啟用外部通訊會話的存檔，請將 ArchiveExternal 參數的值設定為 True （$True）： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

若要同時啟用內部和外部通訊會話的存檔，請將 ArchiveInternal 和 ArchiveExternal 參數的值設定為 True： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>停用封存原則

若要完全停用存檔，請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 False （$False）： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
