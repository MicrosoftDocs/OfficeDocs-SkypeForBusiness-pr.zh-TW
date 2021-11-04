---
title: 在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：瞭解商務用 Skype Server 中的詳細通話記錄 (CDR) 。
ms.openlocfilehash: 9e77cc7782116f317504cbbee98d0731d69ed5e8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60751742"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
 
**摘要：** 瞭解商務用 Skype Server 中的詳細通話記錄 (CDR) 。
  
 (CDR) 的詳細資料記錄可讓您追蹤對等立即訊息會話的使用方式，例如對等立即訊息會話、透過網際網路通訊協定 (VoIP) 電話及會議通話等事項。 這個使用狀況資料包含有關通話者雙方身分、通話時間以及通話時間長度的資訊。
  
當您安裝時商務用 Skype Server 會為您建立單一、全域的 CDR 配置設定集合。 系統管理員也可以選擇建立網站範圍的自訂設定。 只要使用這些網站範圍的設定，其優先順序就高於全域設定。 例如，如果您為 Redmond 網站建立網站範圍的設定，則這些設定 (，而不是通用設定) 將用來管理 Redmond 中的 CDR。
  
您可以使用商務用 Skype Server 控制台] 或[New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 來建立 CDR 設定設定。 您可以使用商務用 Skype Server 控制台或[Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 來修改現有的設定。 如果您使用商務用 Skype Server 控制台建立或修改設定，您可以使用下列選項：
  
|**UI 設定**|**PowerShell 參數**|**描述**|
|:-----|:-----|:-----|
|名稱  <br/> |身分識別  <br/> |要建立之 CDR 設定設定的唯一識別碼。 這些設定只可在網站範圍建立。  <br/> |
|啟用 Cdr 的監控  <br/> |EnableCDR  <br/> |表示是否啟用 CDR。  <br/> |
|啟用清除 Cdr  <br/> |EnablePurging  <br/> |會指出是否要定期從 CDR 資料庫中刪除 CDR 記錄。  <br/> |
|將 Cdr 保留最大持續期間 (天數)   <br/> |KeepCallDetailForDays  <br/> |會指出 CDR 記錄會保留在 CDR 資料庫中的天數。 任何早于指定天數的記錄會自動刪除。  (請注意，只有在啟用清除功能時，才會進行清除。 )   <br/> |
|將錯誤報表資料保留最大持續 (天數)   <br/> |KeepErrorReportForDays  <br/> |指出 CDR 錯誤報表保留的天數。 任何早于指定天數的報告都會自動刪除。 CDR 錯誤報表是由用戶端應用程式上傳的診斷報告。  <br/> |
   
> [!NOTE]
> New-CsCdrConfiguration 和 Set-CsCdrConfiguration Cmdlet 包含商務用 Skype Server 控制台中無法使用的其他選項。 如需詳細資訊，請參閱 [新的 CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 和 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) 的 [說明] 主題。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台建立 CDR 配置設定

1. 在商務用 Skype Server 控制台中，按一下 [**監視與** 封存]。
    
2. 在 [ **詳細通話記錄** ] 索引標籤上，按一下 [ **新增**]。
    
3. 在 [ **選取網站** ] 對話方塊中，選取要建立新設定的網站。 如果對話方塊是空白的，表示您的所有網站都已指派 CDR 設定的集合。 每個網站都限制為單一這類集合。 在這種情況下，您可以先刪除然後重新建立設定，或是只修改現有的設定。
    
4. 在 [ **新的詳細通話記錄] (CDR) 設定** ] 對話方塊中，進行想要的選擇，然後按一下 [ **認可**]。
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server 控制台修改現有 CDR 設定設定

1. 在商務用 Skype Server 控制台中，按一下 [**監視與** 封存]。
    
2. 按兩下要修改的設定集合，或選取集合，按一下 [ **編輯**]，然後按一下 [ **顯示詳細資料**]。 請注意，您一次只能修改單一集合。 若要對多個集合進行相同的變更，請改用商務用 Skype Server 管理命令介面。
    
3. 在 [ **編輯詳細通話記錄 (CDR) 設定** ] 對話方塊中，進行想要的選擇，然後按一下 [ **認可**]。
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 CDR 配置設定

您也可以使用 Windows PowerShell 和 **New-CsCdrConfiguration** Cmdlet 來建立 CDR 配置設定。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行此指令程式。 如需使用遠端 Windows PowerShell 連線到商務用 Skype Server 的詳細資訊，請參閱[Microsoft Lync remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/)。 商務用 Skype Server 中的程式相同。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>若要建立新的 CDR 配置設定集合

 此命令會為 Redmond 網站建立新的 CDR 設定設定集合：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>建立停用詳細通話記錄的 CDR 設定設定集合

 因為上述命令未指定參數 (除了必要的 Identity 參數)，新的組態設定集合會將預設值用於其所有屬性。 若要使用不同的屬性值來建立設定，只要包含適當的參數及參數值即可。 例如，若要建立通話詳細資料設定的集合，根據預設，允許停用詳細通話記錄，請使用類似如下的命令：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>若要在建立新的 CDR 配置設定集合時指定多個屬性值

 您可以包含多個參數來修改多個屬性值。 例如，此命令會設定新的設定，將詳細通話記錄保留30天和錯誤報表的90天：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

如需詳細資訊，請參閱 [CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 的 [說明] 主題。
