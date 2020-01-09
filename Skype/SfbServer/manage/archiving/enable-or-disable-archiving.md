---
title: 在商務用 Skype Server 中啟用或停用封存
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：瞭解如何在商務用 Skype Server 中啟用或停用封存。
ms.openlocfilehash: 603ffece7d3b0dabe27ee95d27eaee1e84f48fb9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991578"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>在商務用 Skype Server 中啟用或停用封存

**摘要：** 瞭解如何在商務用 Skype Server 中啟用或停用封存。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用 [控制台] 啟用或停用封存

1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。
    
4. 從存檔設定清單中選取適當的全域、網站或池設定，按一下 [**編輯**]，按一下 [**顯示詳細資料**]，然後執行下列動作：
    
   - 若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。
    
   - 若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 及會議會話**]。
    
   - 若要停用存檔以進行設定，請按一下 [**停**用封存]。
    
5. 按一下 [認可]****。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用 Windows PowerShell 啟用或停用封存

您也可以使用**CsArchivingConfiguration** Cmdlet 來啟用或停用封存。 例如，下列命令會修改所有的存檔設定設定，以便只封存 IM 會話。 此命令會呼叫無任何參數的**CsArchivingConfiguration** Cmdlet，以傳回目前在組織中使用的所有存檔設定設定。 然後，該集合會以管道傳送到**物件**Cmdlet，該 Cmdlet 只會選取 EnableArchiving 屬性等於（-eq） "ImAndWebConf" 的那些設定。 篩選後的集合接著會傳送到**CsArchivingConfiguration** Cmdlet，這會採用集合中的每個專案，並將 EnableArchiving 的值變更為 "ImOnly"：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
