---
title: 在商務用 Skype Server 中建立新的封存原則
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 摘要：瞭解如何為商務用 Skype Server 建立新的封存原則。
ms.openlocfilehash: a07edaae5d8c7c7cafc0e9a76d2b2d7574c5713b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767891"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中建立新的封存原則

**摘要：** 瞭解如何為商務用 Skype Server 建立新的封存原則。
  
您可以使用 [控制台] 或使用 Windows PowerShell Cmdlet 來建立新的封存原則。
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a>使用控制台建立新的封存原則

若要使用 [控制台] 建立新的封存原則：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
4. 按一下 **[新增]**，然後執行下列其中一項作業： 
    
   - 若要建立網站層級的封存原則，請按一下 [ **網站原則**]，然後在 [ **選取網站**] 中，按一下要套用該原則的網站。
    
   - 若要建立使用者層級的封存原則，請按一下 **[使用者原則]**。
    
5. 在 **[新增封存原則]** 中，執行下列動作：
    
   - 在 **[名稱]** 中，指定新原則的名稱 (例如，externalContoso)。
    
   - 在 **[描述]** 中，提供該原則的相關詳細資料 (例如，Contoso 的外部使用者封存原則)。
    
   - 若要控制對與內部使用者通訊所進行的封存，請選取或清除 **[封存內部通訊]** 核取方塊。
    
   - 若要控制對與外部使用者通訊所進行的封存，請選取或清除 **[封存外部通訊]** 核取方塊。
    
6. 按一下 **[認可]**。
    
    > [!IMPORTANT]
    > 使用者原則的設定僅能套用至您套用該原則的特定使用者和使用者群組。 如需詳細資訊，請參閱[將封存原則套用至商務用 Skype Server 中的使用者](apply-a-policy-to-users.md)。 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 建立新的封存原則

您也可以使用 Windows PowerShell **New-CsArchivingPolicy** Cmdlet 來建立新的封存原則。 如需詳細資訊，請參閱 [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a>在網站層級建立新的封存原則

此命令可以建立 Redmond 網站的新封存原則：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a>在每個使用者層級建立新的封存原則

若要在每個使用者層級建立新的封存原則，只需在建立原則時指定唯一的身分識別：
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a>若要建立新的封存原則以啟用內部通訊會話的封存

由於未在前述命令中指定任何參數 (除了必要的 Identity  參數以外)，因此新原則將針對它們的所有屬性使用預設值。 若要建立使用不同屬性值的原則，只需包含適當的參數和參數值。 例如，下列命令會建立允許封存內部立即訊息會話的封存原則： 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a>若要建立新的封存原則以啟用內部和外部通訊會話的封存

多項屬性值可透過加入多個參數加以修改。 例如，此命令會設定新原則，以封存內部及外部立即訊息會話：
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```