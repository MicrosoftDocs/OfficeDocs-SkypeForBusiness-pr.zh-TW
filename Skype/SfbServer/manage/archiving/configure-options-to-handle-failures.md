---
title: 在商務用 Skype Server 中設定封存選項來處理失敗
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：瞭解如何在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話，以免封存。
ms.openlocfilehash: ed8a59a8c19ace9a83b699e1b69515f52c3af010
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992750"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>在商務用 Skype Server 中設定封存選項來處理失敗

**摘要：** 瞭解如何在商務用 Skype 伺服器發生故障時封鎖 IM 和會議會話，以免封存。
  
如果您的組織需要進行封存，您可以在商務用 Skype 伺服器失敗時封鎖 IM 和會議會話，避免封存。 這有時稱為 [重要模式]。 例如，如果儲存服務發生問題，系統會封鎖已啟用其通訊功能的使用者的 IM。 IM 和會議會在更正失敗之後自動復原。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用 [控制台] 設定 [重要] 模式

若要指定是否應允許通訊會話，以防發生無法進行封存的問題：
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。
    
4. 在歸檔設定清單中，按一下適當的全域、網站或池設定的名稱，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 若要設定在發生失敗時封存的行為方式，請選取或清除 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。
    
6. 按一下 [認可]****。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用 Windows PowerShell 來設定重要模式

您也可以在無法使用**CsArchivingConfiguration** Cmdlet 與 BlockOnArchiveFailure 參數的情況下，指定是否允許通訊會話，以防進行封存。
  
例如，下列命令會在發生存檔失敗時停用通訊：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

[下一步] 命令會在發生存檔失敗時啟用通訊：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

如需詳細資訊，請參閱[CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。
  

