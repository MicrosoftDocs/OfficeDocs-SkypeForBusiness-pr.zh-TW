---
title: 在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
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
ms.assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
description: 摘要：瞭解商務用 Skype Server 中的通話詳細資料錄製（CDR）。
ms.openlocfilehash: 88e86aaec7ca922db39b8c74dc1b354ab0389ba7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818043"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a>在商務用 Skype Server 中建立或修改 CDR 配置設定的集合
 
**摘要：** 瞭解商務用 Skype Server 中的通話詳細資料錄製（CDR）。
  
通話詳細資料錄製（CDR）可讓您追蹤諸如對等立即訊息會話、透過網際網路通訊協定（VoIP）電話撥打電話及會議呼叫等專案的使用方式。 此使用量資料包括呼叫者、呼叫者及交談時間的相關資訊。
  
當您安裝商務用 Skype Server 時，系統會為您建立單一、全域的 CDR 配置設定。 系統管理員也可以選擇在網站範圍中建立自訂設定。 只要使用這些網站範圍的設定，就會優先于全域設定。 例如，如果您為雷德蒙的網站建立網站範圍的設定，則這些設定（而不是 [全域設定]）將會用於管理雷德蒙者中的 CDR。
  
您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 來建立 CDR 配置設定。 您可以使用商務用 Skype Server 的 [控制台] 或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) Cmdlet 來修改現有的設定。 如果您使用商務用 Skype Server 的 [控制台] 來建立或修改設定，您可以使用下列選項：
  
|**UI 設定**|**PowerShell 參數**|**說明**|
|:-----|:-----|:-----|
|名稱  <br/> |Identity  <br/> |所建立的 CDR 配置設定的唯一識別碼。 這些設定只能在網站範圍建立。  <br/> |
|啟用 CDRs 的監控  <br/> |EnableCDR  <br/> |指出是否已啟用 CDR。  <br/> |
|啟用清除 CDRs  <br/> |EnablePurging  <br/> |指出 CDR 記錄是否會定期從 CDR 資料庫中刪除。  <br/> |
|保留 CDRs 的最大持續時間（天）  <br/> |KeepCallDetailForDays  <br/> |表示 CDR 記錄將保留在 CDR 資料庫中的天數。 任何超過指定天數的記錄都會自動刪除。 （請注意，清除功能只會在已啟用清除時才會發生。）  <br/> |
|針對最大持續時間（天）保留錯誤報表資料  <br/> |KeepErrorReportForDays  <br/> |表示保留 CDR 錯誤報表的天數。 任何超過指定天數的報告都會自動刪除。 CDR 錯誤報表是用戶端應用程式上傳的診斷報告。  <br/> |
   
> [!NOTE]
> 新的-CsCdrConfiguration 和 CsCdrConfiguration Cmdlet 包括在商務用 Skype Server [控制台] 中無法使用的其他選項。 如需詳細資訊，請參閱[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)和[設定 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps)的協助主題。
  
### <a name="to-create-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 建立 CDR 配置設定

1. 在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。
    
2. 在 [**通話詳細資料記錄**] 索引標籤上，按一下 [**新增**]。
    
3. 在 [**選取網站**] 對話方塊中，選取要建立新配置設定的網站。 如果對話方塊是空白的，則表示您的所有網站都已指派給 CDR 配置設定的集合。 每個網站僅限一個此類集合。 在這種情況下，您可以刪除並重新建立設定，或直接修改現有的設定。
    
4. 在 [**新增通話詳細資料錄製（CDR）設定**] 對話方塊中，選取所要的選項，然後按一下 [**確認**]。
    
### <a name="to-modify-existing-cdr-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用商務用 Skype Server [控制台] 修改現有的 CDR 配置設定

1. 在商務用 Skype Server 的 [控制台] 中，按一下 [**監視及**封存]。
    
2. 按兩下要修改的設定集合，或選取該收藏，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。 請注意，您一次只能修改單一集合。 若要對多個收藏進行相同的變更，請改用商務用 Skype Server 管理命令介面。
    
3. 在 [**編輯通話詳細資料錄製（CDR）] 設定**對話方塊中，選取所要的選項，然後按一下 [**確認**]。
    
## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 建立 CDR 配置設定

您也可以使用 Windows PowerShell 和**CsCdrConfiguration** Cmdlet 來建立 CDR 配置設定。 您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。 如需使用遠端 Windows PowerShell 連線至商務用 Skype Server 的詳細資料，請參閱博客文章[：「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)」。 在商務用 Skype 伺服器中，程式是一樣的。
  
### <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a>若要建立新的 CDR 配置設定集合

 這個命令會建立套用至雷德蒙網站的 CDR 設定設定的新集合：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a>若要建立停用通話詳細資料錄製的 CDR 配置設定集合

 因為在上述命令中沒有指定任何參數（強制身分識別參數以外），所以新的配置設定集合會將預設值用於其所有屬性。 若要建立使用不同屬性值的設定，只要包含適當的參數和參數值即可。 例如，若要建立通話詳細資料設定的集合，根據預設，允許停用通話詳細資料錄製使用如下所示的命令：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a>建立新的 CDR 配置設定集合時，指定多個屬性值

 您可以透過包含多個參數來修改多個屬性值。 例如，這個命令會將新設定設定為將呼叫詳細資料記錄保持在30天，並將錯誤報表保留90天：
    
  ```PowerShell
  New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90
  ```

如需詳細資訊，請參閱[新版-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) Cmdlet 的說明主題。
  

