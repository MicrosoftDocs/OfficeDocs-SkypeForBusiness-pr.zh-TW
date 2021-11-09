---
title: 在商務用 Skype Server 中指定保留 CDR 資料
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 摘要：瞭解如何管理商務用 Skype Server (CDR) 資料的詳細通話記錄。
ms.openlocfilehash: b232e853e28f2dbdee33c666e65ca89932796941
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852007"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>在商務用 Skype Server 中指定保留 CDR 資料
 
**摘要：** 瞭解如何管理商務用 Skype Server (CDR) 資料的詳細通話記錄。
  
根據預設，[詳細通話記錄] (CDR) 資料會在60天之後清除。 您可以使用 [ **詳細通話記錄** ] 頁面上的設定，將資料保留較長或更短的時間週期。 如果您停用 CDR，啟用 CDR 之前所捕獲的資料也會受到清除。
  
> [!NOTE]
> 您應設定 CDR 和經驗品質 (QoE) 保留相同天數的資料。 「監控伺服器報告」頁面提供的 [通話詳細資料包告] 中的每個通話 (Cdr) ，包含 CDR 和 QoE 資訊。 如果 CDR 和 QoE 的清除持續時間不同，有些呼叫可能只會包含 CDR 資料，另有可能只包含 QoE 資料。 
  
使用下列程式可設定 CDR 資料的清除設定。 
  
### <a name="to-specify-retention-of-cdr-data"></a>指定保留 CDR 資料

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 之網路中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL，以開啟 [商務用 Skype Server 控制台]。  
    
3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[詳細通話記錄]**。
    
4. 在 [ **詳細通話記錄** ] 頁面上，按一下表格中的適當網站，然後按一下 [ **編輯**]，再按一下 [ **顯示詳細** 資料]。
    
5. 若要開啟清除，請選取 [ **啟用清除 cdr**]。
    
6. 在 [ **保持 cdr 的最大持續期間 (天數) ：** 選取應該保留詳細通話記錄的最大天數。
    
7. 在 [ **將錯誤報表的最大持續時間 (天數]) 中：** 選取應該保留錯誤報表的最大天數。
    
8. 按一下 **[認可]**。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 CDR 保留

您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>指定特定位置的 CDR 保留

- 此命令可讓您清除 Redmond 網站的 CDR 資料，並將網站設定為維護 CDR 資料和錯誤報表資料的20天。
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>指定多個位置的 CDR 保留

- 此命令會針對組織中使用的所有 CDR 設定設定，設定 CDR 保留。
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

如需詳細資訊，請參閱 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中的詳細通話記錄 (CDR) ](call-detail-recording-cdr.md)