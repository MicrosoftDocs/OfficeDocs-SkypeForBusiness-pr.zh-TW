---
title: 在商務用 Skype Server 中建立封存配置
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：瞭解如何建立商務用 Skype Server 的存檔設定。
ms.openlocfilehash: bc7319f2de8398dd3d9e9a79948d1af6eaeb98bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818955"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>在商務用 Skype Server 中建立封存配置

**摘要：** 瞭解如何建立商務用 Skype Server 的存檔設定。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用 [控制台] 設定存檔選項

若要設定特定網站或文件庫的存檔選項： 
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。
    
4. 在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作： 
    
   - 若要建立網站封存設定，請按一下 [**網站**設定]，然後在 [**選取網站**] 中，選取要設定為要存檔的網站。
    
   - 若要建立池存檔設定，請按一下 [**池**設定]，然後在 [**選取池**] 中，選取要設定為要存檔的池。
    
5. 在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：
    
   - 若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。
    
   - 若要在 IM 會話和網路會議中同時啟用封存功能，請按一下 [封存**im 和網路會議會話**]。
    
   - 若要停用此設定的封存，請按一下 [**停**用封存]。
    
6. 此外，在 [新增封存]**設定**中，請執行下列動作：
    
   - 若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。
    
   - 若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。
    
   - 若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：
    
     - 若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。
    
     - 若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。
    
7. 按一下 [認可]****。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用 Windows PowerShell 設定封存選項

您也可以使用**CsArchivingConfiguration** Cmdlet 來設定特定網站或文檔池的存檔選項。
  
下列命令會建立新的 [雷德蒙] 網站存檔設定的集合：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 
  
若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 下列範例會建立一個存檔設定的集合，預設只允許封存立即訊息會話：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會將新設定設為封存立即訊息會話，並封鎖封存服務的立即訊息無法使用：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

如需詳細資訊，請參閱[新版-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。
