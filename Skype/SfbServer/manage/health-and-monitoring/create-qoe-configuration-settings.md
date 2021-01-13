---
title: 在商務用 Skype Server 中建立經驗品質設定設定
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
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：瞭解商務用 Skype Server 中 (QoE) 設定的經驗品質。
ms.openlocfilehash: d1d0b299b5cf0bbaf3627b7c90f90e7e1d958d10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816993"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立經驗品質設定設定
 
**摘要：** 深入瞭解商務用 Skype Server 中 (QoE) 設定的經驗品質。
  
「經驗品質 (QoE)」計量在追蹤組織中進行之音訊和視訊通話的品質，包括遺失的網路封包數量、背景雜訊和「抖動」(封包延遲差異) 等項目的數量。這些計量會儲存在與其他資料 (例如詳細通話記錄) 不同的資料庫中，讓您可獨立於其他資料記錄來啟用和停用 QoE。
  
當您安裝商務用 Skype Server 時，會為您建立單一、全域 QoE 設定的集合。 系統管理員也可以選擇建立網站範圍的自訂設定。 只要使用這些網站範圍的設定，其優先順序就高於全域設定。 例如，如果為 Redmond 網站建立網站範圍的設定，則會使用這些設定 (而非全域設定) 來管理 Redmond 的 QoE。
  
您可以使用商務用 Skype Server 控制台或 [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 來建立 QoE 設定設定。 如果您使用商務用 Skype Server 控制台建立新的設定，您可以使用下列選項：
  
|**UI 設定**|**PowerShell 參數**|**描述**|
|:-----|:-----|:-----|
|名稱  <br/> |身分識別  <br/> |要建立之設定的唯一識別碼。QoE 組態設定僅可在網站範圍內建立。  <br/> |
|啟用 QoE 資料的監控  <br/> |EnableQoE  <br/> |指定是否將收集 QoE 記錄並儲存至監控資料庫。  <br/> |
|啟用 QoE 資料的清除  <br/> |EnablePurging  <br/> |指定是否在 **[將 QoE 資料保留最大持續期間 (天)]** 屬性中定義的期間經過之後，將清除記錄。 <br/> |
|將 QoE 資料保留最大持續期間 (天)  <br/> |KeepQoEDataForDays  <br/> |QoE 資料從資料庫清除之前將會儲存的天數。如果停用清除，將會忽略此值。  <br/> |
   
> [!NOTE]
> New-CsQoEConfiguration Cmdlet 包含商務用 Skype Server [控制台] 中無法使用的其他選項。 如需詳細資訊，請參閱 CsQoEConfiguration 的「 [新增-](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 說明主題。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立 QoE 配置設定

1. 以 RTCUniversalServerAdmins 群組成員的身分，或是 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色的成員身分登入電腦。 如需詳細資訊，請參閱＜**Delegate Setup Permissions**＞。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。  
    
3. 在左導覽列中，按一下 **[監控和封存]**，然後按一下 **[經驗品質資料]**。
    
4. 在 **[經驗品質資料]** 頁面上，按一下 **[新增]**。
    
5. 在 **[選取站台]** 中，按一下要套用原則的網站，並按一下 **[確定]**。
    
6. 在 **[新的經驗品質設定]** 中，執行下列動作：
    
   - 選取 **[啟用經驗品質 (QoE) 資料的監控]** 開啟監控功能。
    
   - 選取 **[啟用經驗品質 (QoE) 資料的清除]** 開啟清除功能。
    
   - 在 **[將 QoE 資料保留最大持續期間 (天)]** 中，選取應該保留 QoE 記錄的最大天數。
    
7. 按一下 **[認可]**。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 QoE 設定設定

您可以使用 Windows PowerShell 和 New-CsQoEConfiguration Cmdlet 來建立 QoE 設定設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線到商務用 Skype 伺服器的詳細資訊，請參閱博客文章 [：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 商務用 Skype Server 中的程式相同。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>建立新的 QoE 組態設定集合

 下列命令會建立要套用至 Redmond 網站的新 QoE 組態設定集合：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>建立新的 QoE 組態設定集合並停用 QoE 監控

 因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。例如，若要建立預設為允許停用經驗品質記錄之 QoE 組態設定的集合，請使用如下的命令：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>建立新的 QoE 組態設定集合時指定多個屬性值

 您可藉由包含多個參數來指定多個參數值。例如，下列命令會將新設定架構為將 QoE 資料保留 30 天，並在上午 3:00 清除舊資料：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

如需詳細資訊，請參閱 [CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
  

