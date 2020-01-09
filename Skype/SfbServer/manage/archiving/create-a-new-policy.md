---
title: 在商務用 Skype Server 中建立新的存檔原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：瞭解如何為商務用 Skype Server 建立新的存檔原則。
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992730"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中建立新的存檔原則

**摘要：** 瞭解如何為商務用 Skype Server 建立新的存檔原則。
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來建立新的存檔原則。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>使用 [控制台] 建立新的存檔原則

若要使用 [控制台] 建立新的存檔原則：
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。
    
4. 按一下 [**新增**]，然後執行下列其中一項操作： 
    
   - 若要建立網站層級的歸檔原則，請按一下 [**網站原則**]，然後在 [**選取網站**] 中，按一下要套用原則的網站。
    
   - 若要建立使用者層級的歸檔原則，按一下 [**使用者原則**]。
    
5. 在**新**的 [封存原則] 中，執行下列動作：
    
   - 在 [**名稱**] 中，指定新原則的名稱（例如，externalContoso）。
    
   - 在 [**描述**] 中，提供原則的詳細資料（例如 Contoso 的外部使用者歸檔原則）。
    
   - 若要控制與內部使用者通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
   - 若要控制與外部使用者通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。
    
6. 按一下 [認可]****。
    
    > [!IMPORTANT]
    > 使用者原則的設定只會套用到您要套用原則的特定使用者和使用者群組。 如需詳細資訊，請參閱[將存檔原則套用到商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 建立新的存檔原則

您也可以使用 Windows PowerShell **CsArchivingPolicy** Cmdlet 來建立新的存檔原則。 如需詳細資訊，請參閱[新版-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) Cmdlet 的說明主題。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>在網站層級建立新的存檔原則

這個命令會為雷德蒙的網站建立新的存檔原則：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>在每個使用者層級建立新的存檔原則

若要在每個使用者層級建立新的存檔原則，只需在建立原則時指定唯一的身分識別：
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>建立新的歸檔原則以啟用內部通訊會話的歸檔

由於前面的命令中未指定任何參數（除了強制身分識別參數以外），新原則將針對其所有屬性使用預設值。 若要建立使用不同屬性值的原則，只要包含適當的參數和參數值即可。 例如，下列命令會建立允許封存內部立即訊息會話的存檔原則： 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>若要建立新的存檔原則來啟用內部和外部通訊會話的存檔

您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會設定新的原則，以封存內部和外部立即訊息會話：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
