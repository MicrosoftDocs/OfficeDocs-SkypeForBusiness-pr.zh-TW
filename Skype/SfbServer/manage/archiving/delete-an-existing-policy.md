---
title: 在商務用 Skype Server 中刪除現有的封存原則
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要：瞭解如何刪除商務用 Skype 伺服器的封存原則。
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817613"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除現有的封存原則

**摘要：** 瞭解如何刪除商務用 Skype 伺服器的封存原則。
  
您可以刪除使用者原則或網站原則，但不能刪除全域原則。 如果您刪除全域原則，商務用 Skype 伺服器會自動將原則重設為預設值。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>使用控制台刪除原則

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。
    
4. 在封存原則清單中，依序按一下您要刪除的使用者或網站原則、**[編輯]** 和 **[刪除]**。
    
5. 按一下 **[認可]**。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 刪除原則

您也可以使用 **Remove-grant-csarchivingpolicy** Cmdlet 刪除封存原則。
  
例如，下列命令會刪除 Identity 為 site： Redmond 的原則。 當刪除在網站層級設定的原則時，系統會自動依全域封存原則來控制先前由網站原則管理的使用者：
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

此命令會移除所有套用至每個使用者層級的封存原則：
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

這個命令會移除所有已停用內部封存的封存原則：
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

如需詳細資訊，請參閱 [grant-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) Cmdlet 的 [說明] 主題。
