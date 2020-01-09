---
title: 商務用 Skype 2015 中的集中式記錄服務
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
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 摘要：瞭解商務用 Skype Server 2015 中集中式記錄服務的服務元件和設定設定。
ms.openlocfilehash: 1dfdc0de999e79182e5beb57c6d51ecc75359672
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992600"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>商務用 Skype 2015 中的集中式記錄服務
 
**摘要：** 瞭解商務用 Skype Server 2015 中集中式記錄服務的服務元件和設定設定。
  
集中式記錄服務可以： 
  
- 從中央位置使用單一命令，在一或多部電腦和池上開始或停止記錄。
    
- 在一或多台電腦和池中搜尋記錄。 您可以將搜尋調整成傳回所有電腦上的所有記錄，或傳回更簡明的結果。
    
- 設定記錄會話的方式如下：
    
  - 定義**案例**，或使用預設情況。 集中式記錄服務中的案例是由範圍（全域或網站）、案例名稱來識別案例的用途及一或多個提供者所組成。 您可以在任何指定時間，在電腦上執行預設案例與一個已定義的案例。
    
  - 使用現有的提供者或建立新的提供者。 Aprovider 會定義記錄會話收集的內容、詳細資料層級、要追蹤哪些元件，以及要套用哪些旗標。
    
    > [!TIP]
    >  如果您熟悉 OCSLogger，termproviders 會參照**元件**集合（例如，S4、SIPStack）、**記錄類型**（例如，WPP、EventLog 或 IIS logfile）、**追蹤等級**（例如，All、verbose、debug）及**旗標**（例如 TF_COMPONENT、TF_DIAG）。 這些專案是在提供者（Windows PowerShell 變數）中定義，並傳遞到集中式記錄服務命令。
  
  - 針對特定電腦和池設定記錄。
    
  - 從 [選項]**網站**定義記錄會話的範圍（以在該網站上的電腦上執行記錄捕獲），或 [**全域**] （在部署中的所有電腦上執行記錄捕獲）。
    
集中式記錄服務是一種功能強大的疑難排解工具，可讓您從根本原因分析到效能問題的問題。 所有範例都是使用商務用 Skype Server Management Shell 來顯示。 說明是透過工具本身提供給命令列工具的，但您可以從命令列執行的一組函數是有限的。 透過使用商務用 Skype Server 管理命令介面，您可以存取更大且更具可設定的功能，讓您的第一個選擇。 
  
## <a name="logging-service-components"></a>記錄服務元件

 集中式記錄服務會在您部署中的所有伺服器上執行，且由下列代理程式和服務所組成：
  
- 集中式記錄服務代理程式 ClsAgent 會在每一台已部署商務用 Skype Server 的電腦上執行。 它會偵聽（在埠**TCP 50001-50003**）上從 CLSCONTROLLER over WCF 的命令，並將回應傳送回控制器。 它會記錄管理會話（開始/停止/更新），以及搜尋記錄。 它也會執行記錄歸檔等日常作業，例如記錄封存和清除。 
    
- 集中式記錄服務控制器 Cmdlet 商務用 Skype 伺服器管理 Shell 會將開始、停止、清除及搜尋命令傳送給 ClsAgent。 傳送搜尋命令時，會將產生的記錄傳回 ClsControllerLib 及匯總。 控制器會將命令傳送給 agent、接收這些命令的狀態，並管理從搜尋範圍內任何電腦上的所有代理程式傳回的搜尋記錄檔資料，並將記錄資料匯總到有意義且已排序的輸出集合。 下列主題中的資訊主要是使用商務用 Skype Server 管理命令介面。
    
**ClsController 通訊至 ClsAgent**

![CLSController 與 CLSAgent 之間的關係。](../../media/Ops_CLS_Architecture.jpg)
  
您使用 Windows Server 命令列介面或使用商務用 Skype Server Management Shell 發出命令。 這些命令會在您登入的電腦上執行，並傳送到您部署中的 ClsAgent 本機或其他電腦和池。
  
ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔案。 ClsAgent 會將它們分攤80，讓它們均勻分佈于選項 CacheFileLocalFolders 所定義的各個卷上（也就是，本機快取位置和百分比可使用**Set-CsClsConfiguration** Cmdlet 來設定）。 ClsAgent 也負責從本機電腦中老化舊的快取事件追蹤記錄（.etl）檔案。 兩周之後（也就是使用**CsClsConfiguration Cmdlet 設定**的時間範圍），這些檔案會複製到檔案共用，並從本機電腦刪除。 如需詳細資訊，請參閱[設定 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps)。 當您收到搜尋要求時，會使用搜尋準則來選取一組快取的 .etl 檔案，以根據代理所維護之索引中的值來執行搜尋。
  
> [!NOTE]
> 從本機電腦移至檔案共用的檔案，可以透過 ClsAgent 進行搜尋。 ClsAgent 將檔案移到檔案共用後，ClsAgent 不會維護檔案的老化與移除。 您應該定義系統管理工作來監視檔案共用中的檔案大小，然後刪除檔案或封存檔案。 
  
所產生的記錄檔案可以使用各種不同的工具來讀取和分析，包括**Snooper**和任何可讀取文字檔（例如**notepad.exe**）的工具。 Snooper 是商務用 Skype Server 2015 調試工具的一部分，可在[網頁版下載](https://go.microsoft.com/fwlink/p/?LinkId=285257)中取得。
  
就像 OCSLogger，集中式記錄服務會有數個要追蹤的元件，並提供選取旗標的選項，例如 TF_COMPONENT 和 TF_DIAG。 集中式記錄服務也會保留 OCSLogger 的記錄層級選項。
  
在命令列 ClsController 上使用商務用 Skype Server Management Shell 的最重要優點，就是您可以使用選取的提供者來設定及定義新案例，這些提供者是針對問題空間、自訂標記及記錄層級。 提供給 ClsController 的案例僅限於針對可執行檔所定義的情況。
  
在舊版中，提供了 OCSLogger，讓系統管理員和支援人員從部署中的電腦收集追蹤檔案。 OCSLogger （針對其所有優點）有一個不足之處。 您在指定時間只能在一部電腦上收集記錄。 您可以使用個別的 OCSLogger 複本登入多部電腦，但最終會有多個記錄，而且沒有簡單的方法來匯總結果。
  
當使用者要求記錄搜尋時，ClsController 會決定要傳送要求的電腦（亦即根據選取的案例）。 它也會判斷是否需要將搜尋傳送到已儲存的 .etl 檔案所在的檔案共用位置。 當搜尋結果傳回 ClsController 時，控制器會將結果合併成單一時間排序的結果集，並顯示給使用者。 使用者可以將搜尋結果儲存至本機電腦，以進行進一步分析。
  
當您開機記錄會話時，您會指定與您嘗試解決之問題相關的案例。 您可以隨時執行兩種情況。 這兩種案例的其中一個就是 AlwaysOn 案例。 顧名思義，它應該一直在您的部署中執行，收集所有電腦、池及元件的資訊。
  
> [!IMPORTANT]
> 根據預設，AlwaysOn 情況未在您的部署中執行。 您必須明確啟動案例。 一旦開始，就會繼續執行，直到明確停止為止，且執行狀態將會在電腦重新開機後持續。 如需開始與停止案例的詳細資料，請參閱[在商務用 Skype Server 2015 中開始或停止 CLS 記錄捕獲](start-or-stop-log-capture.md)。 
  
發生問題時，請先開始與所報告問題相關的第二個案例。 再現問題，並停止記錄第二個案例。 相對於報告的問題開始進行記錄搜尋。 記錄的匯總集合會產生一個記錄檔案，其中包含您網站中所有電腦的追蹤訊息，或部署的全域範圍。 如果搜尋傳回的資料超過您可以 feasibly 分析的資料（通常稱為 [信噪比]，而雜訊太高），您可以執行另一個含有較窄參數的搜尋。 此時，您可以開始注意顯示的模式，並可協助您更清楚地瞭解問題。 最後，在您執行幾個精緻式搜尋之後，您可以找到與問題相關的資料，並找出根本原因。
  
> [!TIP]
> 當您在商務用 Skype Server 中出現問題案例時，請先詢問自己「我已經知道問題為何？」。 如果您要量化問題界限，您可以在商務用 Skype Server 中消除大部分的運營實體部分。 
  
考慮在尋找連絡人時，使用者無法取得目前結果的範例案例。 在媒體元件、企業語音、會議和許多其他元件中，沒有任何問題。 您可能不知道問題的實際原因：在用戶端上，或是伺服器端問題？ 連絡人是由使用者複製程式從 Active Directory 收集，並透過通訊錄服務器（ABServer）傳送至用戶端。 ABServer 會從 RTC 資料庫取得它的更新（使用者複製程式寫入這些檔案），並將它們收集到通訊錄檔案（依預設值為 1:30 AM）。 商務用 Skype Server 用戶端會根據隨機排程來取得新的通訊錄。 因為您知道程式的運作方式，所以您可以減少搜尋問題，因為使用者複製程式已從 Active Directory 收集資料，而 ABServer 無法檢索及建立通訊錄檔案，或用戶端無法下載通訊錄檔案。
  
## <a name="current-configuration"></a>目前的設定

集中式記錄服務會設定為定義記錄服務的預期收集方式、收集方式、收集來源，以及記錄設定的位置。 您可以全域定義這些設定（也就是整個部署）或網站（也就是您部署中的命名網站）。 您定義的任何記錄，都會使用適合用來啟動、停止、清除及搜尋記錄的身分識別的設定。
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>顯示目前的集中式記錄服務設定

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 在命令列提示處輸入下列內容：
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > 您可以縮小或擴大由定義`-Identity`和範圍（例如「Site：北京」）傳回的設定設定範圍，只傳回網站雷蒙德的 CsClsConfiguration。 如果您想要有關設定的指定部分的詳細資料，您可以將輸出輸送至另一個 Windows PowerShell Cmdlet。 例如，若要取得網站「雷蒙德」設定中所定義之案例的詳細資料，請輸入：`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Get-CsClsConfiguration 輸出範例。](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    此 Cmdlet 的結果會顯示集中式記錄服務的目前設定。
    
|**配置設定**|**描述**|
|:-----|:-----|
|**Identity** <br/> |識別此設定的範圍和名稱。 只有一個全域配置，且每個網站都有一個設定。  <br/> |
|**案例** <br/> |此設定所定義之所有案例的清單。  <br/> |
|**SearchTerms** <br/> |已定義配置的搜尋字詞。 Office 365，而非內部部署。  <br/> |
|**SecurityGroups** <br/> |已定義的安全性群組可控制誰（也就是安全性群組的成員）可以查看以他們所在的網站為基礎的電腦。 在此內容中，網站是在拓撲建立器中定義的網站。  <br/> |
|**地區** <br/> |已定義的區域是用來將 SecurityGroups 收集到某個地區（例如 EMEA）。  <br/> |
|**EtlFileRolloverSizeMB** <br/> |在建立新的事件追蹤記錄（.etl）檔案之前，此參數會指出記錄檔的大小上限。 即使在 EtlFileRolloverMinutes 中設定的最大時間尚未達到，也會在已定義的大小達到時建立新的記錄檔。  <br/> |
|**EtlFileRolloverMinutes** <br/> |已定義在建立新的 .etl 檔案之前可以經過的最大時間長度（以分鐘為單位）。 當計時器過期時，即使已在 EtlFileRolloverSizeMB 中設定的大小上限尚未達到，新的記錄檔案也會建立。  <br/> |
|**TmfFileSearchPath** <br/> |[追蹤郵件格式] 檔案的搜尋位置。  <br/> |
|**CacheFileLocalFolders** <br/> |已定義在電腦上寫入快取檔案之位置的路徑。 CLSAgent 會寫入快取檔案，並在網路服務的內容下執行。 在此案例中，% TEMP% 會展開為%WINDIR%\ServiceProfiles\NetworkService\AppData\Local。 根據預設，會將緩存檔案和記錄檔寫入相同的目錄。  <br/> |
|**CacheFileNetworkFolder** <br/> |您可以定義通用命名慣例（UNC）路徑，以在記錄作業期間接收快取檔案。  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |定義為保留快取檔案的最長時間（以天為單位）。  <br/> |
|**CacheFileMaxDiskUsage** <br/> |定義為快取檔案可以使用的磁碟空間百分比。  <br/> |
|**ComponentThrottleLimit** <br/> |在觸發自動節流 limiter 前，定義為每秒可產生的追蹤數上限。  <br/> |
|**ComponentThrottleSample** <br/> |ComponentThrottleLimit 可超過60秒數的次數。  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |允許執行的 CLSAgent 最低版本。 此元素適用于 Office 365。  <br/> |
   

