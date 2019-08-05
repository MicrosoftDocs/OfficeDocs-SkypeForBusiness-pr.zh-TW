---
title: 在商務用 Skype Server 中管理已歸檔資料的清除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: '摘要: 瞭解如何管理商務用 Skype Server 的存檔資料清除。'
ms.openlocfilehash: 193e17791290b384552542129d8d89c20296f109
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188209"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>在商務用 Skype Server 中管理已歸檔資料的清除

**摘要:** 瞭解如何管理商務用 Skype Server 的存檔資料清除。
  
存檔資料庫不是用於長期保留, 商務用 Skype 伺服器不會提供電子探索 (搜尋) 方案來儲存已歸檔的資料, 因此需要將資料移到其他儲存空間。 商務用 Skype 伺服器提供會話匯出工具, 可供您用來將存檔的資料匯出至可搜尋的腳本。 您必須定義何時清除封存和匯出的資料。 
  
如需使用**Export CsArchivingData** Cmdlet 匯出資料的詳細資訊, 請參閱[在商務用 Skype Server 中匯出封存的資料](export-archived-data.md)。
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>使用 [控制台] 管理資料清除

若要使用 [控制台] 管理已封存的資料, 請執行下列動作:
  
1. 從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [封存**配置**]。
    
4. 在歸檔設定清單中, 按一下適當的全域、網站或池設定的名稱, 按一下 [**編輯**], 按一下 [**顯示詳細資料**], 然後執行下列動作:
    
   - 若要啟用清除, 請選取 [**允許清除封存資料**] 核取方塊, 然後執行下列其中一項操作:
    
     - 若要清除所有記錄, 請按一下 [**清除匯出的封存資料], 並儲存已儲存的存檔資料 (天數)**, 然後指定天數。
    
     - 若只要清除已匯出的資料, 請按一下 [**僅清除匯出的存檔資料**]。
    
   - 若要停用清除, 請清除 [**允許清除封存資料**] 核取方塊。
    
5. 按一下 [認可]****。
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>使用 Windows PowerShell 管理資料清除

您可以使用下列 Windows PowerShell Cmdlet 來管理封存的資料清除:
  
- **CsArchivingConfiguration** Cmdlet 與 EnablePurging 參數可讓您啟用或停用清除已封存的資料。
    
- **Invoke-CsArchivingDatabasePurge**可讓您從封存資料庫手動清除記錄。
    
例如, 下列命令可讓您清除所有封存的資料。 執行此命令之後, 商務用 Skype Server 將清除早于指定的 KeepArchivingDataForDays 參數值的所有封存記錄。 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

下列命令會限制清除到已匯出到資料檔之已歸檔記錄 (使用**Export CSArchivingData** Cmdlet)。 您也必須將 PurgeExportedArchivesOnly 參數設定為 True ($True):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

執行此命令之後, 商務用 Skype 伺服器將只會清除符合兩個準則的封存記錄: 1) 它們比指定給 KeepArchivingDataForDays 參數的值還舊;而且, 2) 它們已使用**Export CsArchivingData** Cmdlet 進行匯出。
  
若要停用自動清除封存記錄, 請將 EnablePurging 參數設定為 False ($False):
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

下列範例使用**CsArchivingDatabasePurge** Cmdlet, 在 atl-sql-001.contoso.com 上的存檔資料庫中, 清除超過24小時的所有記錄。 若要確保所有記錄都已刪除, 包括尚未匯出的記錄, PurgeExportedArchivesOnly 參數會設定為 False ($False):
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
