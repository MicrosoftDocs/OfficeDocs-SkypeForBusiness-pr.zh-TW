---
title: 在商務用 Skype Server 中刪除封存配置
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：瞭解如何在商務用 Skype Server 中刪除存檔設定。
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818935"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>在商務用 Skype Server 中刪除封存配置

**摘要：** 瞭解如何在商務用 Skype Server 中刪除封存配置。
  
您可以刪除網站配置或池設定，但無法刪除全域設定。 如果您刪除全域設定，系統會自動將其重設為預設值。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>使用 [控制台] 刪除封存配置

若要使用 [控制] 面板刪除封存配置：
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。
    
4. 在封存配置清單中，按一下您要刪除的網站或池設定，按一下 [**編輯**]，然後按一下 [**刪除**]。
    
    > [!NOTE]
    > 您也可以按一下全域設定，但如果您想要將全域設定重設為預設值，請選擇此選項。 
  
5. 按一下 [認可]****。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>使用 Windows PowerShell 刪除封存配置

您也可以使用**CsArchivingConfiguration** Cmdlet 刪除封存配置。
  
例如，下列命令會移除套用至雷德蒙者網站的存檔設定設定。 刪除網站範圍中設定的原則後，由全域存檔原則會自動控制先前由網站原則管理的使用者：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

下列命令會移除所有已套用至服務範圍的存檔設定：
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

[下一步] 命令會移除 Exchange 封存已停用的所有存檔設定：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

您也可以使用**CsArchivingConfiguration** Cmdlet，將全域設定重設為預設值。 例如，假設您已在全域層級啟用 IM 會話存檔;下列命令會將值重設為預設值（無），這會停用全域層級的存檔：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

如需詳細資訊，請參閱[Remove CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) Cmdlet 的說明主題。
