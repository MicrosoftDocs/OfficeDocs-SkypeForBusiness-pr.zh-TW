---
title: 設定封存選項，以處理商務用 Skype Server 中的失敗
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31fd4e7c-3c68-48dd-9fad-8863831accd7
description: 摘要：瞭解如何在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以避免封存。
ms.openlocfilehash: 9a39c5f54fbdd4a738f4e67e7f70ff199a204672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817673"
---
# <a name="configure-archiving-options-to-handle-failures-in-skype-for-business-server"></a>設定封存選項，以處理商務用 Skype Server 中的失敗

**摘要：** 瞭解如何在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以防封存。
  
如果您的組織需要封存，您可以在商務用 Skype 伺服器失敗的情況下封鎖 IM 和會議會話，以避免封存。 這有時稱為重要模式。 例如，如果儲存服務發生問題，將會封鎖啟用封存之通訊的使用者的 IM。 IM 和會議會在失敗更正後自動復原。 
  
## <a name="configure-critical-mode-by-using-the-control-panel"></a>使用控制台設定重要模式

若要指定是否應該允許通訊會話，以防失敗的原因：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 按一下封存設定清單中適當的全域、網站或集區設定名稱，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]。
    
5. 若要設定當失敗發生時封存的運作方式，請選取或清除 [封存 **失敗時封鎖立即訊息 (IM) 或 web 會議會話** ] 核取方塊。
    
6. 按一下 **[認可]**。
    
## <a name="configure-critical-mode-by-using-windows-powershell"></a>使用 Windows PowerShell 設定重要模式

您也可以指定是否應該允許通訊會話，以防因無法使用 **get-csarchivingconfiguration 指令程式** 搭配 BlockOnArchiveFailure 參數進行封存。
  
例如，下列命令會在封存失敗時停用通訊：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True
```

下一個命令會在封存失敗的情況下啟用通訊：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False
```

如需詳細資訊，請參閱 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
  

