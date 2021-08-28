---
title: 商務用 Skype 2015 中的集中式記錄服務
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 摘要：瞭解商務用 Skype Server 2015 中集中式記錄服務的服務元件和設定設定。
ms.openlocfilehash: 844492e0dddc5337a208bcf4e82fc8de88302884
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582677"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>商務用 Skype 2015 中的集中式記錄服務
 
**摘要：** 瞭解商務用 Skype Server 2015 中集中式記錄服務的服務元件和設定設定。
  
集中式記錄服務可： 
  
- 從中心位置以單一命令開始或停止記錄一或多部電腦及集區。
    
- 在一或多部電腦及集區上搜尋記錄。 您可以量身定制搜尋，以傳回所有機器上的所有記錄，或傳回更簡明的結果。
    
- 如下設定記錄工作階段：
    
  - 定義 **案例**，或使用預設案例。 集中式記錄服務中的案例是由範圍 (全域或網站) 所組成，案例名稱可識別案例的目的，以及一或多個提供者。 您可以在任何指定的時間，在電腦上執行預設案例及一個定義的案例。
    
  - 使用現有提供者或建立新的提供者。 Aprovider 定義記錄會話收集的內容、詳細資料層級、要追蹤的元件，以及所套用的旗標。
    
    > [!TIP]
    >  如果您熟悉 OCSLogger，termproviders 會參照 **元件** 的集合 (例如，S4、SIPStack) 、 **記錄類型** (例如，WPP、EventLog 或 IIS 日誌檔) 、 **追蹤層級** (例如，All、verbose、debug) 和 **旗標** (例如 TF_COMPONENT、TF_DIAG) 。 這些專案是在提供者 (Windows PowerShell 變數) 並傳遞至集中式記錄服務命令中定義。
  
  - 設定特定電腦及集區的記錄檔。
    
  - 從 [選項] **網站** (定義記錄會話的範圍，以在該網站上的電腦上執行記錄捕獲，只) 或 **全域** (，以在部署) 的所有電腦上執行記錄捕獲。
    
集中式記錄服務是一種功能強大的疑難排解工具，可讓您從根本原因分析到效能問題進行大規模或小規模的問題。 所有範例都是使用商務用 Skype Server 管理命令介面來顯示。 協助是透過工具本身為命令列工具提供，但是您可以從命令列執行的功能集有限。 透過使用商務用 Skype Server 管理命令介面，您可以存取更大、更具可設定的功能集，因此永遠都應該是第一項選擇。 
  
## <a name="logging-service-components"></a>記錄服務元件

 集中式記錄服務會在部署中的所有伺服器上執行，且由下列代理程式和服務所組成：
  
- 集中式記錄服務代理程式 ClsAgent 會在部署商務用 Skype Server 的每一部電腦上執行。 它會偵聽埠 **TCP 50001-50003**) 上的 (，以供來自 WCF ClsController 的命令，並將回應傳送回控制器。 它會記錄管理會話 (啟動/停止/更新) ，以及搜尋記錄檔。 它也會執行如記錄封存及清除的內務處理作業。 
    
- 集中式記錄服務控制器指令程式商務用 Skype Server 管理命令介面會將開始、停止、清除和搜尋命令傳送給 ClsAgent。 當傳送搜尋命令時，產生的記錄會傳回 ClsControllerLib.dll 並匯總。 控制器會將命令傳送給代理程式、接收這些命令的狀態，並在搜尋範圍中的任何電腦上的所有 agent 傳回時，管理搜尋記錄檔資料，並將記錄資料匯總到有意義的輸出集。 下列主題中的資訊重點在於使用商務用 Skype Server 管理命令介面。
    
**ClsController ClsAgent 的通訊**

![CLSController 和 CLSAgent 之間的關聯性。](../../media/Ops_CLS_Architecture.jpg)
  
您使用 Windows Server 命令列介面或使用商務用 Skype Server 管理命令介面發出命令。 命令會在您登入的電腦上執行，並傳送至本機的 ClsAgent，或部署中的其他電腦及集區。
  
ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔。 ClsAgent 會將其分配給它們，使其平均分散于選項 CacheFileLocalFolders 所定義的各個磁片區上，每個磁片區絕對使用超過 80% (也就是說，本機快取位置和百分比可使用 **Set-CsClsConfiguration** Cmdlet) 來設定。 ClsAgent 也負責帳齡舊的快取事件追蹤記錄檔 ( .etl) 本機電腦。 在兩周後 (也就是說，可使用 **Set-CsClsConfiguration** Cmdlet 來設定時間範圍) 這些檔案會複製到檔案共用，並從本機電腦刪除。 如需詳細資訊，請參閱 [Set-CsClsConfiguration](/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。 當接收搜尋要求時，搜尋準則是用來選取一組快取的 .etl 檔案，以根據代理程式所維護之索引中的值來執行搜尋。
  
> [!NOTE]
> 從本機電腦移至檔案共用的檔案，可依 ClsAgent 進行搜尋。 一旦 ClsAgent 將檔案移至檔案共用，檔案的老化和移除不會由 ClsAgent 維護。 您應定義管理工作，以監視檔案共用中的檔案大小，並刪除或封存檔案。 
  
您可以使用各種工具讀取及分析產生的記錄檔，包括 **Snooper.exe** 和任何可讀取文字檔的工具，例如 **Notepad.exe**。 Snooper.exe 是商務用 Skype Server 2015 調試工具的一部分，可供[網頁下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)使用。
  
就像 OCSLogger 一樣，集中式記錄服務也會有多個元件可供追蹤，並提供選擇旗標的選項，例如 TF_COMPONENT 和 TF_DIAG。 集中式記錄服務也會保留 OCSLogger 的記錄等級選項。
  
在命令列 ClsController 上使用商務用 Skype Server 管理命令介面最重要的優點是，您可以使用選取的提供者來設定及定義新的案例，該提供者會以問題空間、自訂旗標及記錄層級為目標。 可用於 ClsController 的案例只限于為可執行檔定義的案例。
  
在舊版中，提供 OCSLogger.exe，讓系統管理員和支援人員在部署中從電腦收集追蹤檔案。 OCSLogger，針對其所有優點，都有缺點。 在指定的時間，您只能在一部電腦上收集記錄檔。 您可以使用不同的 OCSLogger 副本登入多部電腦，但是會以多個記錄檔結束，而且不會有簡單的方法來匯總結果。
  
當使用者要求記錄搜尋時，ClsController 會根據) 所選案例，決定要將要求傳送給 (的機器。 此外，它也會判斷是否需要將搜尋傳送至儲存的 .etl 檔案所在的檔案共用。 當搜尋結果傳回 ClsController 時，控制器會將結果合併為使用者所呈現的單一時序結果集。 使用者可以將搜尋結果儲存至本機機器，以進行進一步分析。
  
當您開機記錄會話時，您會指定要嘗試解決之問題的相關案例。 您可以隨時執行兩個案例。 這兩種案例之一應該是 AlwaysOn 案例。 顧名思義，它應永遠在您的部署中執行，並收集所有電腦、集區和元件的資訊。
  
> [!IMPORTANT]
> 根據預設，AlwaysOn 案例不會在您的部署中執行。 您必須明確地啟動案例。 一旦開始，它會繼續執行，直到明確停止為止，而且執行狀態會持續重新開機電腦。 如需啟動和停止案例的詳細資訊，請參閱[商務用 Skype Server 2015 中的開始或停止 CLS 記錄捕獲](start-or-stop-log-capture.md)。 
  
發生問題時，請啟動與所報告問題相關的第二個案例。 再現問題，並停止記錄第二個案例。 相對於所報告的問題，開始進行記錄搜尋。 記錄的匯總集合會產生記錄檔，該檔案包含您的網站中所有電腦的追蹤訊息，或部署的全域範圍中的追蹤訊息。 如果搜尋傳回的資料多於您可以 feasibly 分析 (通常稱為雜訊對雜訊比例，在此情況下，噪音太高) ，您可以使用較窄的參數執行另一次搜尋。 此時，您可以開始注意所顯示的模式，並可協助您取得問題的更清晰的重點。 最後，在您執行一些精簡搜尋之後，您可以尋找與問題相關的資料，並找出根本原因。
  
> [!TIP]
> 在商務用 Skype Server 中出現問題的情況時，請從詢問您「我已經知道此問題的狀況為何？」。 如果您量化問題的界限，您可以在商務用 Skype Server 中消除大部分的運作實體部分。 
  
請考慮一個範例案例，您知道使用者在尋找連絡人時並未取得目前的結果。 沒有任何一點要尋找媒體元件、企業語音、會議及其他元件的一些問題。 您可能不會知道問題實際上是在用戶端上，還是伺服器端問題？ 使用者收集器會從 Active Directory 收集連絡人，並透過通訊錄服務器 (ABServer) 來傳遞給用戶端。 ABServer 會從 RTC 資料庫取得更新 (，在此情況下，使用者複寫器會將其寫入) 並將其收集到通訊錄檔案中（預設為-1:30 AM）。 商務用 Skype Server 用戶端會以隨機排程的，取回新的通訊錄。 因為您知道程式的運作方式，所以您可以縮小搜尋，以找出可能導致問題的潛在原因，以供使用者複寫器從 Active Directory 收集的資料，ABServer 不會檢索及建立通訊錄檔案，或用戶端不會下載通訊錄檔案。
  
## <a name="current-configuration"></a>目前設定

集中式記錄服務設定為定義記錄服務的預定目標、收集方式、收集位置及記錄設定的方式。 您可以將這些設定定義為全域 (，也就是針對整個部署) 或網站 (（也就是部署) 中已命名的網站）。 任何您定義的記錄都會依據您在進行開始、停止、清除及搜尋記錄命令時所使用的身分，而使用適當的設定。
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>顯示目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[**商務用 Skype 2015**]，然後按一下 [**商務用 Skype Server 管理命令** 介面]。
    
2. 在命令列提示輸入下列命令：
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > 您可以縮小或展開定義及範圍所傳回的設定設定範圍  `-Identity` ，例如 "Site:Redmond"，只傳回 Site Redmond 的 set-csclsconfiguration。 如果您想要有關設定之特定部分的詳細資料，您可以將輸出輸送到另一個 Windows PowerShell Cmdlet 中。 例如，若要取得網站 "Redmond" 設定中所定義案例的詳細資料，請輸入： `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Get-CsClsConfiguration 的輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    Cmdlet 的結果會顯示集中式記錄服務的目前設定。
    
|**設定設定**|**描述**|
|:-----|:-----|
|**Identity** <br/> |識別此組態的範圍及名稱。只有一個全域組態，而每個網站有一個組態。  <br/> |
|**Scenarios** <br/> |列出針對此組態定義的所有案例。  <br/> |
|**SearchTerms** <br/> |定義組態的搜尋字詞。 Microsoft 365 或 Office 365，而非內部部署。  <br/> |
|**SecurityGroups** <br/> |定義安全性群組，根據其所在的網站，控制誰 (亦即安全性群組的成員) 可以看到電腦。 在此內容中，網站是在拓撲產生器中定義的網站。  <br/> |
|**地區** <br/> |定義地區，用於將 SecurityGroups 集合至地區，例如 EMEA。  <br/> |
|**EtlFileRolloverSizeMB** <br/> |此參數指示在建立新的事件追蹤記錄 (.etl) 檔之前，記錄檔的大小上限。達到定義的大小時，即使還未達到 EtlFileRolloverMinutes 中設定的時間上限，還是會建立新的記錄檔。  <br/> |
|**EtlFileRolloverMinutes** <br/> |定義在建立新的 .etl 檔之前，記錄檔可以存在的時間上限 (分)。計時器逾期時，即使還未達到 EtlFileRolloverSizeMB 中設定的大小上限，還是會建立新的記錄檔。  <br/> |
|**TmfFileSearchPath** <br/> |搜尋追蹤訊息格式檔的位置。  <br/> |
|**CacheFileLocalFolders** <br/> |定義將快取檔案寫入電腦所在位置的路徑。CLSAgent 寫入快取檔案並在網路服務環境下執行。在此情況下，%TEMP% 會展開為 %WINDIR%\ServiceProfiles\NetworkService\AppData\Local。依據預設，快取檔案及記錄檔會寫入相同的目錄。  <br/> |
|**CacheFileNetworkFolder** <br/> |您可以定義通用命名慣例 (UNC) 路徑，以在記錄作業時接收快取檔案。  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |定義快取檔案保留的時間上限 (天)。  <br/> |
|**CacheFileMaxDiskUsage** <br/> |定義快取檔案可使用的磁碟空間百分比。  <br/> |
|**ComponentThrottleLimit** <br/> |定義在觸發自動節流限制器之前，元件每秒可以產生的追蹤上限。  <br/> |
|**ComponentThrottleSample** <br/> |60 秒內可超過 ComponentThrottleLimit 的次數。  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |允許執行的 CLSAgent 最小版本。 此元素是用於 Microsoft 365 或 Office 365。  <br/> |
