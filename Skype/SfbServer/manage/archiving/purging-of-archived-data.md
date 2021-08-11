---
title: 管理商務用 Skype Server 中封存資料的清除
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：瞭解如何管理商務用 Skype Server 的封存資料清除。
ms.openlocfilehash: f6eafbacedc715dc3684a16eb17cd5e1b1ae59923046af5cf180e92bbf6a2266
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307074"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>管理商務用 Skype Server 中封存資料的清除

**摘要：** 瞭解如何管理商務用 Skype Server 的封存資料清除。
  
封存資料庫不適用於長期保留，而且商務用 Skype Server 不會提供電子探索 (的封存資料的搜尋) 方案，因此資料必須移至其他儲存區。 商務用 Skype Server 提供的會話匯出工具，可用來將封存的資料匯出至可搜尋的記錄。 您必須定義何時清除已封存及匯出的資料。 
  
如需使用 **Export-CsArchivingData** Cmdlet 匯出資料的詳細資訊，請參閱 [在商務用 Skype Server 中匯出封存的資料](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>使用控制台管理資料清除

若要使用 [控制台] 管理封存資料的清除，請執行下列動作：
  
1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 按一下封存組態清單中適當的全域、網站或集區組態名稱，再依序按一下 [編輯] 和 [顯示詳細資料]，然後執行下列作業：
    
   - 若要啟用清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項：
    
     - 若要清除所有記錄，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。
    
     - 若只要清除已匯出的資料，請按一下 **[只清除匯出的封存資料]**。
    
   - 若要停用清除，請清除 **[啟用封存資料的清除]** 核取方塊。
    
5. 按一下 **[認可]**。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>使用 Windows PowerShell 管理資料清除

您可以使用下列 Windows PowerShell Cmdlet 來管理封存資料的清除：
  
- **Set-get-csarchivingconfiguration** Cmdlet 搭配 EnablePurging 參數可讓您啟用或停用封存資料的清除。
    
- **Invoke-CsArchivingDatabasePurge** 可讓您手動清除封存資料庫中的記錄。
    
例如，下列命令可啟用所有封存資料的清除。 在執行這個命令之後，商務用 Skype Server 會清除超過為 KeepArchivingDataForDays 參數所指定之值的所有封存記錄。 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

下列命令會限制使用 **Export-CSArchivingData** Cmdlet) ，清除已匯出至資料檔案 (已封存記錄。 您也必須將 PurgeExportedArchivesOnly 參數設定為 True ($True) ：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

在執行這個命令之後，商務用 Skype Server 只會清除符合兩個準則的封存記錄： 1) 超過為 KeepArchivingDataForDays 參數所指定的值）。而且，2) 使用 **Export-CsArchivingData** Cmdlet 匯出。
  
若要停用自動清除封存記錄，請將 EnablePurging 參數設定為 False ($False) ：
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

下列範例會使用 **Invoke-CsArchivingDatabasePurge** Cmdlet，從 atl-sql-001.contoso.com 上的封存資料庫中清除超過24小時的所有記錄。 為了確保刪除所有記錄（包括尚未匯出的記錄），PurgeExportedArchivesOnly 參數會設定為 False ($False) ：
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
