---
title: 在商務用 Skype Server 中指定 CDR 資料的保留
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: '摘要: 瞭解如何管理商務用 Skype Server 的通話詳細資料錄製 (CDR) 資料。'
ms.openlocfilehash: a775098a4c41bccca42fe1d95c5f1dbf0d22f2bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188674"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a>在商務用 Skype Server 中指定 CDR 資料的保留
 
**摘要:** 瞭解如何管理商務用 Skype Server 的通話詳細資料錄製 (CDR) 資料。
  
根據預設, 通話詳細資料錄製 (CDR) 資料會在60天之後清除。 您可以使用 [**通話詳細資料記錄**] 頁面上的設定, 將資料保留較長或較短的時間週期。 如果您停用 CDR, 在啟用 CDR 之前捕獲的資料, 也會受到清除。
  
> [!NOTE]
> 您應該設定 CDR 和體驗品質 (QoE), 以保留相同天數的資料。 [監視伺服器報告] 頁面提供的呼叫詳細資料包告 (CDRs) 中的每個通話, 包括 CDR 和 QoE 資訊。 如果 CDR 與 QoE 的清除持續時間不一樣, 有些通話可能只會包含 CDR 資料, 而其他可能只包含 QoE 資料。 
  
使用下列程式來設定 CDR 資料的清除設定。 
  
### <a name="to-specify-retention-of-cdr-data"></a>指定保留 CDR 資料

1. 從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦.
    
2. 開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。  
    
3. 在左側導覽列中, 按一下 [**監視及**封存], 然後按一下 [**呼叫詳細資料錄製**]。
    
4. 在 [**通話詳細資料記錄**] 頁面上, 按一下表格中的適當網站, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。
    
5. 若要開啟清除, 請選取 [**啟用清除 CDRs**]。
    
6. 在 **[保留 CDRs 的最大持續時間 (天數)** ] 中: 選取應保留通話詳細資料錄製的最大天數。
    
7. 若要在**最大持續時間 (天) 內保留錯誤報表資料:** 請選取要保留錯誤報表的最大天數。
    
8. 按一下 [認可]****。
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 指定 CDR 保留

您可以使用 Windows PowerShell 和 CsCdrConfiguration Cmdlet 來建立 CDR 保留設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料, 請參閱博客文章[: 「快速入門: 使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中, 程式是一樣的。
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a>針對特定位置指定 CDR 保留

- 這個命令可讓您清除雷德蒙網站的 CDR 資料, 並將網站設定為維持 CDR 資料, 以及20天的錯誤報表資料。
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a>若要為多個位置指定 CDR 保留

- 這個命令會針對組織中使用的所有 CDR 配置設定, 設定 CDR 保留。
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

如需詳細資訊, 請參閱[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。
  
## <a name="see-also"></a>另請參閱

[在商務用 Skype Server 中呼叫詳細資料錄製 (CDR)](call-detail-recording-cdr.md)
