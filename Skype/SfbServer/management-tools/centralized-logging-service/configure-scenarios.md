---
title: 在商務用 Skype Server 2015 中設定集中式記錄服務的案例
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6c3bf826-e7fd-4002-95dc-01020641ef01
description: 摘要：瞭解如何在商務用 Skype Server 2015 中建立、修改及移除集中式記錄服務的案例。
ms.openlocfilehash: 10225be172d91aba18db29a1a6669cfbe8656fa6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855440"
---
# <a name="configure-scenarios-for-the-centralized-logging-service-in-skype-for-business-server-2015"></a>在商務用 Skype Server 2015 中設定集中式記錄服務的案例
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中建立、修改及移除集中式記錄服務的案例。
  
案例會定義範圍 (，例如全域、網站、集區或電腦) ，以及要在集中式記錄服務中使用的提供者。 使用案例，您可以啟用或停用提供者的追蹤功能 (例如，S4、SIPStack、IM 及顯示狀態) 。 透過設定案例，您可以將特定邏輯集合的所有提供者分組，以解決特定問題的條件。 如果您發現案例必須修改以滿足疑難排解和記錄需求，則商務用 Skype Server 2015 調試工具會為您提供一個名為 ClsScenarioEdit 的 Windows PowerShell 模組，此模組包含 namedEdit-new-csclsscenario 函數的 sharepointsync.psm1。 模組的用途是編輯指定之案例的屬性。 本主題提供此模組的運作方式範例。 請先下載商務用 Skype Server 2015[調試工具](https://go.microsoft.com/fwlink/p/?LinkId=285257)，再繼續進行。
  
> [!IMPORTANT]
> 針對任何指定的範圍（即 site、global、pool 或 computer），您可以在任何指定時間執行最多兩個案例。 若要判斷目前正在執行的案例，請使用 Windows PowerShell 和[Get-CsClsScenario](/powershell/module/skype/get-csclsscenario?view=skype-ps)。 您可以使用 Windows PowerShell 和[Set-CsClsScenario](/powershell/module/skype/set-csclsscenario?view=skype-ps)，動態變更正在執行的案例。 您可以修改在記錄會話期間執行哪些案例，以調整或精煉所收集的資料，以及提供者。 
  
若要使用商務用 Skype Server 管理命令介面執行集中式記錄服務功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。 若要傳回所有獲指派此 Cmdlet 的 rbac 角色清單，包括您自行建立的任何自訂 rbac 角色，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主題的其餘部分著重于如何定義案例、修改案例、檢索正在執行的案例、移除案例，以及指定案例中包含的專案，以優化疑難排解。 您可以使用商務用 Skype Server 管理命令介面發出 Windows PowerShell 命令。 當您使用 Windows PowerShell 時，您可以定義在記錄會話中使用的新案例。
  
在[商務用 Skype 2015 的集中式記錄服務](centralized-logging-service.md)中引入時，案例的元素如下：
  
- **提供者** 如果您熟悉 OCSLogger，提供者就是您所選擇的元件，以告知 OCSLogger 追蹤引擎應從何處收集記錄。 提供者是相同的元件，在許多情況下，與 OCSLogger 中的元件具有相同的名稱。 如果您不熟悉 OCSLogger，提供者是集中式記錄服務可從中收集記錄的伺服器角色特定元件。 如需提供者設定的詳細資訊，請參閱[在商務用 Skype Server 2015 中設定集中式記錄服務的提供者](configure-providers.md)。
    
- 身分 **識別** 參數識別碼會設定案例的範圍和名稱。 例如，您可以設定範圍「全域」，並以 "LyssServiceScenario" 識別案例。 當您結合這兩個時，您會定義身分識別 (例如，"global/LyssServiceScenario" ) 。
    
    您也可以選擇使用-Name 和-Parent 參數。 您可以定義 Name 參數來唯一地識別案例。 如果您使用 Name，您也必須使用 Parent 將案例新增至全域或網站。 
    
    > [!IMPORTANT]
    > 如果您使用 Name 和 Parent 參數，則無法使用 **-Identity** 參數。
  
### <a name="to-create-a-new-scenario-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario Cmdlet 建立新的案例

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 若要建立記錄會話的新案例，請使用 [New-CsClsProvider](/powershell/module/skype/new-csclsprovider?view=skype-ps) 及定義案例的名稱 (也就是說，它會如何唯一識別) 。 從 WPP (選擇一種記錄格式，也就是 Windows 軟體追蹤預處理程式，也就是預設的) 、EventLog (，也就是 Windows 事件記錄格式) 或 IISLog (，也就是根據 IIS 記錄檔格式) 的 ASCII 格式檔案。 接下來，以本主題所述) 中的 [記錄層級]，將 Level (定義為 [定義]，並在本主題) 的 [旗標] 底下標示 (。
    
    在此範例案例中，我們使用 LyssProvider 做為範例提供者變數。
    
    若要使用定義的選項建立案例，請輸入：
    
   ```PowerShell
   New-CsClsScenario -Identity <scope>/<unique scenario name> -Provider <provider variable>
   ```

    例如：
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider $LyssProvider
   ```

    使用-Name 及-Parent 的替代格式：
    
   ```PowerShell
   New-CsClsScenario -Name "LyssServiceScenario" -Parent "site:Redmond" -Provider $LyssProvider
   ```

### <a name="to-create-a-new-scenario-with-multiple-providers-with-the-new-csclsscenario-cmdlet"></a>使用 New-CsClsScenario Cmdlet 建立多個提供者的新案例

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 每個範圍最多隻能有兩個案例。 不過，您不受限於提供者數目的集合。 在此範例中，假設我們已建立三個提供者，而且您想要將所有三個提供者全部指派給您所定義的案例。 提供者變數名稱為 LyssProvider、ABServerProvider 及 SIPStackProvider。 若要定義或指派多個提供者至案例，請在商務用 Skype Server 管理命令介面或 Windows PowerShell 命令提示字元處，輸入下列命令：
    
   ```PowerShell
   New-CsClsScenario -Identity "site:Redmond/CollectDataScenario" -Provider @{Add=$LyssProvider, $ABServerProvider,  $SIPStackProvider}
   ```

    > [!NOTE]
    > 如 Windows PowerShell 所知，用來建立值之雜湊表的約定 `@{<variable>=<value1>, <value2>, <value>…}` 是眾所周知的 assplatting。 如需 Windows PowerShell 中 splatting 的詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=267760](/previous-versions/technet-magazine/gg675931(v=msdn.10)) 。 
  
### <a name="to-modify-an-existing-scenario-with-the-set-csclsscenario-cmdlet"></a>使用 Set-CsClsScenario Cmdlet 修改現有的案例

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 每個範圍最多隻能有兩個案例。 您可以變更任何時間執行的案例，甚至是在處理記錄捕獲會話時。 如果您重新定義執行案例，目前的記錄會話會停止使用已移除的案例，然後開始使用新的案例。 不過，已移除之案例所捕獲的記錄資訊仍會保留在捕獲的記錄檔中。 若要定義新的案例，請執行下列 (，也就是，假設已定義的提供者新增名為 "S4Provider" ) ：
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Add=<new provider to add>}
   ```

    例如：
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Add=$S4Provider}
   ```

    如果您想要取代提供者，請定義單一提供者或以逗號分隔的提供者清單以取代目前的集合。 如果您只想要取代許多提供者之一，請將目前的提供者新增至新的提供者，以建立一組新的提供者，以包含新的提供者和現有的提供者。 若要以新集合取代所有提供者，請輸入下列專案：
    
   ```PowerShell
   Set-CsClsScenario -Identity <name of scope and scenario defined by New-CsClsScenario> -Provider @{Replace=<providers to replace existing provider set>}
   ```

    例如，若要以 $LyssServiceProvider 取代目前的 $LyssProvider、$ABServerProvider 及 $SIPStackProvider 的集合：
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider}
   ```

    若要使用 $LyssServiceProvider 從目前的 $LyssProvider、$ABServerProvider 及 $SIPStackProvider 取代 $LyssProvider 提供者，請輸入下列專案：
    
   ```PowerShell
   Set-CsClsScenario -Identity "site:Redmond/LyssServiceScenario" -Provider @{Replace=$LyssServiceProvider, $ABServerProvider, $SIPStackProvider}
   ```

### <a name="to-remove-an-existing-scenario-with-the-remove-csclsscenario-cmdlet"></a>使用 Remove-CsClsScenario Cmdlet 移除現有的案例

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 如果您想要移除先前定義的案例，請輸入下列專案：
    
   ```PowerShell
   Remove-CsClsScenario -Identity <name of scope and scenario>
   ```

    例如，若要移除已定義的案例網站： Redmond/LyssServiceScenario：
    
   ```PowerShell
   Remove-CsClsScenario -Identity "site:Redmond/LyssServiceScenario"
   ```

**Remove-CsClsScenario** Cmdlet 會移除指定的案例，但已捕獲的追蹤仍可用於您要搜尋的記錄檔。
### <a name="to-load-and-unload-the-edit-csclsscenario-cmdlet-using-the-clsscenarioeditpsm1-module"></a>使用 ClsScenarioEdit 模組載入和卸載 Edit-CsClsScenario Cmdlet sharepointsync.psm1

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
    > [!IMPORTANT]
    > ClsScenarioEdit sharepointsync.psm1 模組是以個別的 Web 下載形式提供。 模組是商務用 Skype Server 2015 調試工具的一部分。 根據預設，調試工具會安裝在目錄 C:\Program Files \ 商務用 Skype Server 2015 \ 調試工具中。 
  
2. 從 Windows PowerShell 輸入：
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功載入模組時，會傳回 Windows PowerShell 命令提示字元。 若要確認是否已載入模組且 Edit-CsClsScenario 可用，請輸入  `Get-Help Edit-CsClsScenario` 。 您應該會看到 EditCsClsScenario 語法的基本摘要。 
  
3. 若要卸載模組，請輸入：
    
   ```PowerShell
   Remove-Module ClsController
   ```

    > [!TIP]
    > 成功卸載模組後，您會回到 Windows PowerShell 命令提示字元。 若要確認模組已卸載，請輸入  `Get-Help Edit-CsClsScenario` 。 Windows PowerShell 會嘗試尋找 Cmdlet 的說明，但失敗。 
  
### <a name="to-remove-an-existing-provider-from-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模組從案例中移除現有的提供者

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 從 Windows PowerShell 輸入：
    
   ```PowerShell
   Import-Module "CDBurn\OCO\amd64\Support"
   ```

    > [!TIP]
    > 成功載入模組時，會傳回 Windows PowerShell 命令提示字元。 若要確認是否已載入模組且 Edit-CsClsScenario 可用，請輸入  `Get-Help Edit-CsClsScenario` 。 您應該會看到 EditCsClsScenario 語法的基本摘要。 
  
3. 若要從 AlwaysOn 案例中移除提供者，請輸入：
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to remove> -Remove
   ```

   例如：
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Remove
   ```

   參數 ScenarioName 和 ProviderName 都是位置 (也就是說，它們必須在命令列) 參數的預期位置中定義。 若案例名稱位於第二個位置，而且提供者位於第三個位置（相對於第一個位置的 Cmdlet 名稱），便不必明確定義參數名稱。 使用此資訊，上一個命令會輸入為：
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Remove
   ```

   參數值的位置放置只適用于-案例和-提供者。 所有其他參數必須明確定義。
    
### <a name="to-add-a-provider-to-a-scenario-with-the-edit-clscontroller-module"></a>使用 Edit-ClsController 模組將提供者新增至案例

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 若要將提供者新增至 AlwaysOn 案例中，請輸入：
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName <string of the scenario to edit> -ProviderName <string of the provider to add> -Level <string of type level> -Flags <string of type flags>
   ```

    例如：
    
   ```PowerShell
   Edit-CsClsScenario -ScenarioName AlwaysOn -ProviderName ChatServer -Level Info -Flags TF_COMPONENT
   ```

    -Loglevel 可為嚴重、錯誤、警告、Info、Verbose、Debug 或 All 類型。 -旗可以是提供者所支援的任何旗標，例如 TF_COMPONENT、TF_DIAG。 -旗也可以是全部值
    
   您也可以使用 Cmdlet 的位置功能來輸入上述範例。 例如，若要將提供者 ChatServer 新增至 AlwaysOn 案例中，請輸入：
    
   ```PowerShell
   Edit-CsClsScenario AlwaysOn ChatServer -Level Info -Flags ALL
   ```