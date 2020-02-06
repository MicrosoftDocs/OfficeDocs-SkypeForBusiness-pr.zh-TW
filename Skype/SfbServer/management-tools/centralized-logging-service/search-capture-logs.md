---
title: 搜尋商務用 Skype 2015 中集中式記錄服務建立的擷取記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: 摘要：瞭解如何在商務用 Skype Server 2015 中搜尋及閱讀集中式記錄服務捕獲記錄。
ms.openlocfilehash: 234bcdcda4fbf4a0fa7cec364b9a8dbb7b757dc7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816572"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a>搜尋商務用 Skype 2015 中集中式記錄服務建立的擷取記錄
 
**摘要：** 瞭解如何在商務用 Skype Server 2015 中搜尋及閱讀集中式記錄服務捕獲記錄。
  
集中式記錄服務中的搜尋功能非常有用且功能強大，原因如下： 
  
- 您的搜尋和結果會根據您定義的準則，在單一電腦、[池]、[網站] 或 [全域範圍] 上執行。
    
- 您的搜尋可以是最初的廣義，然後縮小至更具針對性的準則，例如時間、元件或電腦。 您可以在相同的記錄中搜尋，且不需要在搜尋準則變更時再次執行記錄會議。
    
- 搜尋的結果是從作用域中的所有電腦和池收集、收集並匯總到單一輸出檔案，代表搜尋準則的所有結果（僅限於已執行的案例，以及由所捕獲的資料）。案例）。 您可以使用熟悉的工具（例如**Snooper**或**記事本**），從您的整個部署中讀取輸出檔案和追蹤訊息。
    
每一部電腦上的 CLSAgent 會根據案例或案例建立記錄（在任何指定時間，每個電腦都可以執行兩個案例）。 記錄及其相關聯的索引與快取檔案是由 CLSAgent 管理。 當您定義並執行搜尋時，[搜尋] 命令會指示 CLSAgent 應該要檢索哪些資訊。 CLSAgent 會針對記錄檔、快取檔案和索引檔案執行查詢，並將搜尋結果傳回 CLSContoller。 CLSController 會從搜尋範圍中的所有電腦和池接收搜尋結果。 然後 CLSController 會將記錄匯總（合併），並將它們轉換成時間增量順序、最舊的專案，並持續到最新專案的最後一段時間。
  
每次搜尋之後，會執行**CsClsLogging** Cmdlet，並會清洗搜尋所使用的快取（不會與 CLSAgent 所維護的快取檔案混淆）。 清除快取可協助確保 CLSController 中有乾淨的記錄和追蹤檔案擷取緩衝區，以便進行下一個搜尋操作。
  
若要充分發揮集中式記錄服務的優點，您必須充分瞭解如何將搜尋設定為僅傳回來自電腦的追蹤訊息，以及與您所研究之問題相關的池記錄。 存在
  
若要使用商務用 Skype Server Management Shell 執行集中式記錄服務搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是自訂的 RBAC 角色包含這兩個群組的其中一個。 若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從商務用 Skype Server Management 命令介面或 Windows PowerShell 提示中執行下列命令：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

例如：
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

本主題的剩餘部分將重點放在如何定義搜尋以優化疑難排解。
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>使用集中式記錄服務執行基本搜尋

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 請確定您在部署中的全域範圍內執行了 AlwaysOn 案例，然後在命令提示字元中輸入下列內容：
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> 根據預設，搜尋 CsClsLogging 會將搜尋結果傳送到主控台。 如果您想要將搜尋結果儲存至檔案，請使用-OutputFilePath _ \<字串的完整檔路徑\>_。 若要定義-OutputFilePath 參數，請在以引號括住的字串格式中，提供路徑和檔案名作為參數的一部分（例如，C:\LogFiles\SearchOutput.txt). 在這個範例中，您必須確保目錄 C:\LogFiles 存在，且您擁有在資料夾中讀取和寫入（NTFS 許可權修改）檔案的許可權。 輸出會附加到，且不會覆寫。 如果您需要個別的檔案，請為每個搜尋定義不同的檔案名。 
  
例如：
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>使用集中式記錄服務在池或電腦上執行基本搜尋

1. 若要將搜尋限制在特定的池或電腦上，請使用-電腦參數及電腦完整名稱的電腦（括在引號中，並以逗號分隔），如下所示：
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

例如：
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. 若要搜尋多台電腦，請輸入多個以引號括住的電腦名稱稱，並以逗號分隔，如下所示：
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. 如果您需要搜尋整個池（而非單一電腦），請將-電腦參數變更為 Pool、移除電腦名稱稱，然後將它取代為以逗號分隔的用引號括住的池中。
    
    例如：
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 使用搜尋命令時，pool 可以是部署中的任何一個池（例如前端池、邊緣池、持續聊天伺服器池），或是在您的部署中定義為一個池的其他人。
    
    例如：
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a>使用時間參數執行搜尋

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 根據預設，搜尋的時間特定參數的開始時間是在您啟動搜尋後五分鐘前的25分鐘。 換句話說，如果我們在 4:00:00 PM 進行搜尋，搜尋開始時間會顯示為 3:35:00 PM 至 4:05:00 PM。 如果您需要在目前時間前搜尋60分鐘或3小時，請使用-StartTime 參數並設定日期和時間字串，以指出您想要搜尋開始的時間。 
    
    例如，您可以使用-StartTime 和-EndTime 定義時間與日期範圍，在您的池中，在11/20/2012 上定義一個在 8 AM 和 9 AM 之間的搜尋。 您可以設定輸出路徑，將結果寫入名為 c:\logfile.txt 的檔案，如下所示：
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> 您指定的時間和日期字串可以是 "日期時間" 或 "時間日期"。 「命令會分析字串，並在執行您執行 Cmdlet 的電腦上，針對日期和時間以及您的地區設定和文化特性，使用適當的值。 
  
3. 如果您想要從11/20/2012 開始的11:00:00 開始檢索記錄，您可以定義-StartTime。 除非您定義特定的 EndTime，否則搜尋的預設時間範圍是30分鐘。 產生的搜尋會從已定義的電腦或池中傳回來自 11:00:00 AM 到 11:30:00 AM 的記錄。
    
例如：
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. 若要在特定的一段時間內進行記錄搜尋，請定義 [StartTime] 和 [EndTime]。 在電腦 edge01.contoso.net 上，您需要從 1 PM 到 2:45 PM 的記錄。 
    
例如：
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>使用其他準則和相符選項執行高級搜尋

1. 啟動商務用 Skype Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**商務用 skype 2015**]，然後按一下 [**商務用 skype Server management Shell**]。
    
2. 若要執行命令來收集特定元件的蹤跡，請輸入下列內容：
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

例如：
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

產生的搜尋會傳回在過去30分鐘內，您部署中所有電腦和池中都有 SIPStack、S4 和 UserServices 追蹤元件的所有記錄專案。
    
3. 若要將使用相同元件的搜尋限制為僅限您的前端池（名為 pool01.contoso.net），請輸入：
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. 具有多個參數之命令的預設搜尋邏輯是使用邏輯或與每個已定義的參數。 您可以透過指定 **-MatchAll**參數來變更此行為。 若要這樣做，請輸入下列內容：
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. 如果您的案例已設定為持續執行（例如 AlwaysOn），或您已定義長時間執行的案例記錄，可能會將本機電腦放到檔案共用上。 您可以使用 CacheFileNetworkFolder 參數來定義檔案共用，方法是使用 New-CsClsConfiguration 來建立新的設定，或使用 Set-CsClsConfiguration 修改現有的配置。 如果您不希望搜尋將檔案共用包含在要搜尋的記錄集合中，請使用 SkipNetworkLogs 參數，如下所示：
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a>從集中式記錄服務讀取捕獲記錄

您可以在執行搜尋之後，充分發揮集中式記錄服務的益處，而且您有一個檔案可用來追蹤已報告的問題。 您可以透過多種方式來讀取檔案。 輸出檔案是標準的文字格式，您可以使用 Notepad.exe 或任何其他能讓您開啟並讀取文字檔的程式。 針對較大的檔案和更複雜的問題，您可以使用類似 Snooper 的工具，該工具是專門用來從集中式記錄服務讀取及分析記錄輸出。 Snooper 包含在可單獨下載的調試工具中。 您可以在此處下載調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。 當您安裝 [調試工具] 時，不會建立快捷方式和功能表項目。 安裝調試工具之後，請開啟 Windows 資源管理器、命令列視窗或商務用 Skype Server 管理命令介面，然後移至目錄（預設位置） C:\Program Files\Skype for Business Server 2015 \ 調試工具。 按兩下 Snooper 或輸入 Snooper，如果您使用的是命令列或商務用 Skype Server 管理命令介面，請按 ENTER。
  
> [!IMPORTANT]
> 本主題的目的不是詳細說明並討論疑難排解技巧。 疑難排解及周圍的程式是一種複雜的主題。 如需疑難排解基本功能及特定工作負荷疑難排解的詳細資料，請參閱 Microsoft Lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)資源套件活頁簿。 流程與程式仍適用于商務用 Skype Server 2015。 
  
### <a name="to-open-a-log-file-in-snooper"></a>若要在 Snooper 中開啟記錄檔

1. 若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。 若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 的成員，或是 CsServerAdministrator 角色的存取控制（RBAC）安全性群組，或是包含這兩個群組中任一群組的自訂 RBAC 角色。 
    
2. 安裝調試工具（LyncDebugTools）之後，請使用 Windows 資源管理器或從命令列將目錄變更為 Snooper 的位置。 根據預設，調試工具位於 C:\Program Files\Skype for Business Server 2015 \ 調試工具中。 按兩下或執行 Snooper。
    
3. 開啟 Snooper 之後，以滑鼠**按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，在 [**開啟**舊檔] 對話方塊中選取檔案，然後按一下 [**開啟**]。
    
4. 記錄檔的**追蹤**訊息會顯示在 [**追蹤**] 索引標籤上。按一下 [**郵件**] 索引標籤即可查看所收集追蹤的訊息內容。
    
### <a name="to-display-a-call-flow-diagram"></a>顯示 [通話流程圖] 圖表

1. 若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。 若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是包含這兩個群組的自訂 RBAC 角色。
    
2. 開啟記錄檔，然後按一下 [**訊息**] 索引標籤，在 [訊息] 視圖中選取交談，或選取 [**追蹤**] 索引標籤上的追蹤元件。
    
3. 按一下 [**通話流程**]。
    
> [!NOTE]
> 如果您按一下不屬於通話流程的訊息或追蹤，圖表就不會出現，且 Snooper 底部會出現狀態訊息，指出「此訊息不符合資格，無法 callfow」。 如果郵件或追蹤是通話流程的一部分，請選擇 [其他訊息] 或 [追蹤]，就會顯示通話流程。 
  
4. 在訊息或追蹤線之間移動，並注意 [通話流程圖] 圖表是否會更新或變更以顯示新圖表。
    
5. 將游標暫留在元素上，以取得通話訊息、端點及其他元件的相關資訊。
