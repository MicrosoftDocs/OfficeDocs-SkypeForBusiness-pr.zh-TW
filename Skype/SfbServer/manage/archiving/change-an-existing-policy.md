---
title: 變更商務用 Skype Server 中的現有封存原則
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
ms.assetid: 4cf600be-ba3d-4bce-aa22-e158b9ccf8a9
description: 摘要：瞭解如何變更使用者的商務用 Skype Server 的封存原則。
ms.openlocfilehash: 555a8822ddf563b8ddce88ed94d56f153c93c795
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767954"
---
# <a name="change-an-existing-archiving-policy-in-skype-for-business-server"></a>變更商務用 Skype Server 中的現有封存原則
 
**摘要：** 瞭解如何變更使用者的商務用 Skype Server 的封存原則。
  
當您第一次部署商務用 Skype Server 時，您會設定初始封存原則，以決定部署中使用者的封存實施方式。 本主題說明如何管理和修正原則。 
  
## <a name="change-archiving-policies-by-using-the-control-panel"></a>使用控制台變更封存原則

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
4. 在原則清單中，執行下列其中一項操作： 
    
   - 若要變更整個部署的原則，請按一下原則清單中的 [ **全域** ]，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
   - 若要變更單一網站的原則，請按一下原則清單中的網站名稱，再按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。
    
   - 若要變更單一使用者或使用者群組的原則，請按一下原則清單中的使用者或使用者群組名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 在 [ **編輯封存原則** ] 頁面上，執行下列動作：
    
   - 若要啟用或停用原則的內部封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。
    
   - 若要啟用或停用原則的外部封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
    > [!IMPORTANT]
    > 使用者原則的設定僅能套用至您套用該原則的特定使用者和使用者群組。 如需詳細資訊，請參閱[將封存原則套用至商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。 
  
## <a name="change-archiving-policies-by-using-windows-powershell"></a>使用 Windows PowerShell 變更封存原則

您也可以使用 Windows PowerShell **Set-CsArchivingPolicy** Cmdlet 變更封存原則。
  
### <a name="enable-archiving-policies"></a>啟用封存原則

若要啟用內部通訊會話的封存，請將 ArchiveInternal 參數的值設為 True ($True) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True
```

若要啟用外部通訊會話的封存，請將 ArchiveExternal 參數的值設為 True ($True) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveExternal $True
```

若要同時啟用內部和外部通訊會話的封存，請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 True： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

### <a name="disable-archiving-policies"></a>停用封存原則

若要完全停用封存，請將 ArchiveInternal 和 ArchiveExternal 參數的值設為 False， ($False) ： 
  
```PowerShell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $False -ArchiveExternal $False
```
