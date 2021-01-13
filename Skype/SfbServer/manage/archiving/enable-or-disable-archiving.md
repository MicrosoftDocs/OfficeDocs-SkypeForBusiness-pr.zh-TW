---
title: 啟用或停用商務用 Skype Server 中的封存
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
ms.assetid: d5aed328-e89d-4a7b-b603-15ae5c33c5dd
description: 摘要：瞭解如何啟用或停用商務用 Skype Server 中的封存。
ms.openlocfilehash: 6d8f6f24bd4b10f7d33a00e218a494d6e8a823d1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817593"
---
# <a name="enable-or-disable-archiving-in-skype-for-business-server"></a>啟用或停用商務用 Skype Server 中的封存

**摘要：** 瞭解如何啟用或停用商務用 Skype Server 中的封存。
  
## <a name="enable-or-disable-archiving-by-using-the-control-panel"></a>使用控制台啟用或停用封存

1. 使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。 
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中 **，按一下 [****監視與** 封存]，然後按一下 [封存設定]。
    
4. 從封存設定清單中選取適當的全域、網站或集區設定，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細資料**]，然後執行下列動作：
    
   - 若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。
    
   - 若要同時啟用 IM 會話和會議的封存，請按一下 [封存 **im 和會議會話**]。
    
   - 若要停用設定的封存，請按一下 [ **停** 用封存]。
    
5. 按一下 **[認可]**。
    
## <a name="enable-or-disable-archiving-by-using-windows-powershell"></a>使用 Windows PowerShell 啟用或停用封存

您也可以使用 **get-csarchivingconfiguration** Cmdlet 來啟用或停用封存。 例如，下列命令會修改所有的封存設定設定，以便只封存 IM 會話。 此命令會呼叫不含任何參數的 **Get-CsArchivingConfiguration** Cmdlet，以傳回組織目前使用的所有封存設定設定。 然後，此集合會管線傳送至 **Where-Object** Cmdlet，該指令程式只會選取 EnableArchiving 屬性等於 (-eq) "ImAndWebConf" 的設定。 然後將篩選後的集合管線傳送至 **get-csarchivingconfiguration 指令程式** ，該指令程式會採用集合中的每個專案，並將 EnableArchiving 的值變更為 "ImOnly"：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableArchiving -eq "ImAndWebConf"} | Set-CsArchivingConfiguration -EnableArchiving "ImOnly"
```
