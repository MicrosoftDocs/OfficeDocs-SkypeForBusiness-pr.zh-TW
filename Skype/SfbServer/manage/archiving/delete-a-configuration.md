---
title: 在商務用 Skype Server 中刪除封存設定
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：瞭解如何在商務用 Skype Server 中刪除封存設定。
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095407"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除封存設定

**摘要：** 瞭解如何在商務用 Skype Server 中刪除封存設定。
  
您可以刪除網站設定或集區設定，但無法刪除全域設定。 如果您刪除全域設定，它會自動重設為預設值。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>使用控制台刪除封存設定

若要使用 [控制台] 刪除封存設定，請執行下列動作：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 在封存設定清單中，按一下您要刪除的網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **刪除**]。
    
    > [!NOTE]
    > 您也可以按一下 [通用] 設定，但只有在您想要將全域設定重設為預設值時，才選擇此選項。 
  
5. 按一下 **[認可]**。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>使用 Windows PowerShell 刪除封存設定

您也可以使用 **Remove-CsArchivingConfiguration** Cmdlet 刪除封存設定。
  
例如，下列命令會移除套用至 Redmond 網站的封存設定設定。 在刪除網站範圍內設定的原則時，以前由網站原則管理的使用者將會自動受全域封存原則管理：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

下列命令會移除套用至服務範圍的所有封存設定：
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

下一個命令會移除已停用 Exchange 封存的所有封存設定設定：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

您也可以使用 **Remove-CsArchivingConfiguration** Cmdlet，將全域設定重設為預設值。 例如，假設您已在全域層級啟用 IM 會話封存，則為下列命令會將值重設為預設值 [無]，這樣會停用全域層級的封存：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

如需詳細資訊，請參閱 [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。