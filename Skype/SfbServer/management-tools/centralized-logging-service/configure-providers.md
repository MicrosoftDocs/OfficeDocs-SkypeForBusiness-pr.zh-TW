---
title: 設定商務用 Skype 2015 中集中式記錄服務的提供者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6a197ecf-b56b-45e0-8e7c-f532ec5164ff
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中設定集中式記錄服務的案例提供者。'
ms.openlocfilehash: a9987d99b2caf00acc92de92a8d997845ad8f921
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186823"
---
# <a name="configure-providers-for-centralized-logging-service-in-skype-for-business-server-2015"></a>設定商務用 Skype 2015 中集中式記錄服務的提供者
 
**摘要:** 瞭解如何在商務用 Skype Server 2015 中設定集中式記錄服務的案例提供者。
  
集中式記錄服務提供者的概念與設定是最重要的功能之一。 Theproviders [直接對應到商務用 skype 伺服器追蹤模型中的商務用 Skype Server 角色元件]。 提供者會定義要追蹤的商務用 Skype Server 2015 元件、要收集的訊息類型 (例如, 致命、錯誤或警告), 以及旗標 (例如 TF_Connection 或 TF_Diag)。 提供者是每個商務用 Skype Server 伺服器角色中可追蹤的元件。 使用提供者, 您可以定義元件的追蹤層級與類型 (例如, S4、SIPStack、IM 和目前狀態)。 已定義的提供者會在案例中用來針對特定的邏輯集合, 針對特定的問題條件來分組所有提供者。
  
若要使用商務用 Skype Server Management 命令介面執行集中式記錄服務功能, 您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組的成員, 或是一個自訂的 RBAC 角色,包含這兩個群組中的任一個。 若要傳回已指派這個 Cmdlet 的所有角色式存取控制 (RBAC) 角色的清單 (包括您自行建立的任何自訂 RBAC 角色), 請從商務用 Skype Server Management 命令介面或 Windows PowerShell 中執行下列命令。提示符
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主題的其餘部分將重點放在如何定義提供者、修改提供者以及提供者定義所包含的內容來優化您的疑難排解。 有兩種方式可以發出集中式記錄服務命令。 您可以在 [商務伺服器 2015 \ CLSAgent] 的 [目錄 C:\Program Files\Common Files\Skype 中, 使用預設位置的 CLSController。 或者, 您可以使用商務用 Skype Server Management Shell 來頒發 Windows PowerShell 命令。 使用 Windows PowerShell, 您可以定義在記錄會話中使用的新提供者, 並完全控制自己的建立、收集的內容, 以及它們收集資料的層級。
  
> [!IMPORTANT]
> 如前文所述, 提供者功能非常強大。 不過, 案例的功能更強大, 因為它們包含在提供者所代表的元件上設定和執行追蹤所需的所有資訊的 embodiment。 隨著案例成為提供者集合, 與執行的批次處理檔案相比, 這可能是鬆散的, 在命令列中, 您可以使用包含上百個命令的批次檔案來收集大量的資訊, 而不是一次發出一個命令。 
  
[集中式記錄] 服務提供已為您定義的許多案例, 而不是要求您深入瞭解提供者的詳細資料。 提供的案例涵蓋絕大多數您可能會遇到的問題。 在少數情況下, 您可能需要建立並定義提供者, 並將其指派給案例。 我們強烈建議您先熟悉所提供的各個案例, 然後再調查需要建立新的提供者和案例的需求。 您可以在這裡找到有關建立提供者的資訊, 讓您熟悉案例如何使用提供者元素來收集追蹤資訊, 目前不提供提供者本身的詳細資料。 
  
在[商務用 Skype 2015 的集中式記錄服務](centralized-logging-service.md)中引入, 定義用來在方案中使用之提供者的主要元素如下:
  
- **提供者**如果您熟悉 OCSLogger, 提供者就是您選擇的元件, 可讓您告訴 OCSLogger 追蹤引擎應該從哪個部分收集記錄。 提供者是相同的元件, 且在許多情況下, 與 OCSLogger 中的元件名稱相同。 如果您不熟悉 OCSLogger, 提供者是集中式記錄服務可以從中收集記錄的伺服器角色特定元件。 在集中式記錄服務的情況下, CLSAgent 是集中式記錄服務的結構元件, 可追蹤您在提供者配置中定義的元件。
    
- **記錄層級**OCSLogger 提供選項, 可為收集的資料選擇多個詳細資料層級。 這個功能是集中式記錄服務和案例的有機組成部分, 且由**Type**參數定義。 您可以從下列選項中進行選擇:
    
  - **全部**收集已定義提供者記錄的 [致命]、[錯誤]、[警告]、[詳細] 和 [調試資訊] 類型的追蹤訊息。
    
  - **致命**只收集定義為 "致命" 的追蹤訊息。
    
  - **錯誤**只收集定義為「錯誤」或「致命」的追蹤訊息。
    
  - **警告**只收集 "Warning"、"錯誤" 和 "致命" 類型的追蹤訊息。
    
  - **資訊**只收集指出已定義之提供者的資訊訊息的追蹤訊息, 以及致命、錯誤和警告訊息。
    
  - **詳細**資訊收集已定義提供者之 [致命]、[錯誤]、[警告] 和 [詳細] 類型的所有追蹤訊息。
    
  - **調試 (調試**) 實質上相當於已定義提供者的「全部」, 收集類型為致命、錯誤、警告、資訊、詳細及調試的痕跡。
    
- **旗標**OCSLogger 提供選項, 為每個提供者選擇您可以從追蹤檔案中檢索之資訊類型的每個提供者的標記。 您可以根據提供者選擇下列標誌:
    
  - **TF_Connection**提供與連接相關的記錄專案。 這些記錄包含與特定元件建立的連線的相關資訊。 這也可能包含大量的網路層級資訊 (也就是不含連線概念的元件)。
    
  - **TF_Security**提供與安全性有關的所有事件/記錄專案。 例如, 在 SipStack 中, 這些是安全事件, 例如網域驗證失敗, 以及用戶端驗證/授權失敗。
    
  - **TF_Diag**提供診斷事件, 您可以用來診斷或疑難排解元件。 例如, 在 SipStack 中, 這些是證書失敗, 或 DNS 警告/錯誤。
    
  - **TF_Protocol**提供通訊協定, 例如 SIP 及組合的群組編解碼器套件訊息。
    
  - **TF_Component**啟用記錄提供者指定的元件。
    
  - **全部**設定提供者可用的所有可用旗標。
    
### <a name="to-review-information-about-existing-centralized-logging-service-scenario-providers"></a>若要查看現有集中式記錄服務案例提供者的相關資訊

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 若要查看現有提供者的設定, 請輸入下列內容:
    
   ```
   Get-CsClsScenario -Identity <scope and scenario name>
   ```

    例如, 若要查看全域會議助理的相關資訊, 請輸入:
    
   ```
   Get-CsClsScenario -Identity "global/CAA"
   ```

    該命令會顯示包含相關聯標誌、設定和元件的提供者清單。 如果顯示的資訊不足, 或者清單對於預設的 Windows PowerShell 清單格式而言太長, 您可以透過定義不同的輸出方法來顯示其他資訊。 若要這樣做, 請輸入:
    
   ```
   Get-CsClsScenario -Identity "global/CAA" | Select-Object -ExpandProperty Provider
   ```

    這個命令的輸出會以五行格式顯示每個提供者, 其中包含提供者名稱、記錄類型、記錄層級、旗標、GUID 和角色, 每個提供者都在個別的行上。 
    
### <a name="to-define-a-new-centralized-logging-service-scenario-provider"></a>定義新的集中式記錄服務案例提供者

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 案例提供者包含要追蹤的元件、要使用的旗標, 以及要收集的詳細資料層級。 若要執行此動作, 請輸入:
    
   ```
   $<variableName> = New-CsClsProvider -Name <provider component> -Type <log type> -Level <log level detail type> -Flags <provider trace log flags>
   ```

    例如, [追蹤提供者] 定義定義要收集哪些內容, 以及從 Lyss 提供者的詳細資料層級看起來如下:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Info" -Flags "All"
   ```

層級會收集致命、錯誤、警告及資訊訊息。 所使用的標誌全都是為 Lyss 提供者所定義的, 且包含 TF_Connection、TF_Diag 和 TF_Protocol。定義 $LyssProvider 變數之後, 您可以使用**新的-CsClsScenario** Cmdlet 來收集來自 Lyss 提供者的追蹤。 若要完成建立並將提供者指派給新的案例, 請輸入:

```
New-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
```

其中 $LyssProvider 是包含使用**新 CsClsProvider**建立之已定義之案例的變數。
### <a name="to-change-an-existing-centralized-logging-service-scenario-provider"></a>變更現有的集中式記錄服務案例提供者

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 若要更新或變更現有提供者的設定, 請輸入:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "TF_Connection, TF_Diag"
   ```

    然後, 您可以輸入下列內容來更新案例以指派提供者:
    
   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider $LyssProvider
   ```

此命令的最終結果是案例網站: [雷德蒙]/[RedmondLyssInfo] 會針對指派給它的提供者更新旗標和層級。 您可以使用 [取得 CsClsScenario] 來查看新案例。 如需詳細資訊, 請參閱[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)。
> [!CAUTION]
> **新的-ClsCsProvider**不會檢查以判斷旗標是否有效。 確認旗標 (例如 TF_DIAG 或 TF_CONNECTION) 拼寫正確無誤。 如果旗標沒有正確拼寫, 提供者就無法傳回預期的記錄資訊。
  
如果您想要在此案例中新增其他提供者, 請輸入下列專案:

```
Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Add=$ABSProvider, $CASProvider, S4Provider}
```

每個使用 Add 指令定義的提供者, 都已使用**新的-CsClsProvider**程式進行定義。
### <a name="to-remove-a-scenario-provider"></a>移除案例提供者

1. 啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。
    
2. 提供的 Cmdlet 可讓您更新現有的提供者, 並建立新的提供者。 若要移除提供者, 您必須使用提供者參數的 Replace 指令來**設定-CsClsScenario**。 完全移除提供者的唯一方式是將它替換成相同名稱的重新定義提供者, 並使用 Update 指令。 例如, 我們的提供者 LyssProvider 是使用 WPP 作為記錄類型、將 level 設定為 Debug, 以及旗標和 TF_DIAG 來定義。 您必須將 [旗標] 變更為 [全部]。 若要變更提供者, 請輸入下列內容:
    
   ```
   $LyssProvider = New-CsClsProvider -Name "Lyss" -Type "WPP" -Level "Debug" -Flags "All"
   ```

   ```
   Set-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo" -Provider @{Replace=$LyssProvider}
   ```

3. 如果您想要完全移除某個案例, 以及與其相關聯的提供者, 請輸入下列內容:
    
   ```
   Remove-CsClsScenario -Identity <scope and name of scenario>
   ```

    例如：
    
   ```
   Remove-CsClsScenario -Identity "site:Redmond/RedmondLyssInfo"
   ```

    > [!CAUTION]
    > Cmdlet**移除-CsClsScenario**不會提示您進行確認。 隨後會刪除該案例, 以及已指派給它的提供者。 您可以重新執行用來建立該案例的命令來重新建立。 沒有復原已移除之案例或提供者的程式。
  
當您使用**CsClsScenario** Cmdlet 移除案例時, 您會完全移除範圍中的案例。 若要使用您所建立的案例, 以及該案例中的提供者, 您可以建立新的提供者, 並將它們指派給新的案例。
## <a name="see-also"></a>另請參閱

[CsClsScenario](https://docs.microsoft.com/powershell/module/skype/get-csclsscenario?view=skype-ps)
  
[新-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/new-csclsscenario?view=skype-ps)
  
[移除-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/remove-csclsscenario?view=skype-ps)
  
[Set-CsClsScenario](https://docs.microsoft.com/powershell/module/skype/set-csclsscenario?view=skype-ps)
  
[新-CsClsProvider](https://docs.microsoft.com/powershell/module/skype/new-csclsprovider?view=skype-ps)
