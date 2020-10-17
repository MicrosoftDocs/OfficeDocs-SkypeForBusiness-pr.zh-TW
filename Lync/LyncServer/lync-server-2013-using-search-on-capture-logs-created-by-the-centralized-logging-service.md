---
title: 在集中式記錄服務建立的捕獲記錄中使用搜尋
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b054f3ea8a1054be1e920fbbacbfe2e88b157ba7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518760"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>在 Lync Server 2013 中使用集中式記錄服務所建立之捕獲記錄檔的搜尋

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

集中式記錄服務中的搜尋功能非常有用，而且很強大，原因如下：

  - 搜尋和結果是依據您所定義的準則，在單一電腦、集區、網站或全域範圍上所執行的。

  - 您的搜尋可能一開始很廣泛，之後可以縮小至更具鎖定性的準則，如時間、元件或電腦。當搜尋準則變更時，擁有相同記錄的搜尋並不需要再次執行記錄工作階段。

  - 系統會在範圍內的所有電腦和集區中收集搜尋的結果，並將其收集彙總為單一的輸出檔，由該輸出檔來代表搜尋準則的所有結果 (僅限已執行案例，且由案例擷取的資料)。您是使用類似 **Snooper** 或**記事本**之類的工具來讀取輸出檔，以及整個部署的追蹤訊息。

每部個別電腦上的 CLSAgent 會依據案例 (任何給定時間每部電腦可以執行兩個案例) 來建立記錄。CLSAgent 會管理記錄和其相關聯的索引和快取檔案。當您定義並執行搜尋時，搜尋命令會指示 CLSAgent 所應擷取的資訊。CLSAgent 會依據記錄檔、快取檔案和索引檔案來執行查詢，並將搜尋結果傳至 CLSContoller。CLSController 會收到來自搜尋範圍內所有電腦和集區的搜尋結果。之後，CLSController 會彙總 (組合) 記錄，並以時間差順序排列，最舊的項目優先，依序進行，最新的項目則最後處理。

在每次搜尋之後，會執行 **Sync-CsClsLogging** Cmdlet，它會刷新搜尋所使用的快取 (不會混淆 CLSAgent) 所維護的快取檔案。 清洗快取有助於確定在下一個搜尋作業的 CLSController 有乾淨的記錄檔和追蹤檔案擷取緩衝區。

若要取得集中式記錄服務的最大好處，您必須充分瞭解如何設定搜尋，只從電腦及集區記錄中只傳回追蹤訊息，這些記錄是與您正在搜尋之問題相關的。 問題

若要使用 Lync Server 管理命令介面來執行集中式記錄服務搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。 若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從 Lync Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘部分著重說明如何定義搜尋以優化疑難排解。

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>使用集中式記錄服務執行基本搜尋

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  請確定您已在全域範圍的部署中執行 AlwaysOn 案例，然後在命令提示字元處輸入下列命令：
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > 根據預設，Search-CsClsLogging 會將搜尋結果傳送至主控台。 如果您想要將搜尋結果儲存至檔案，請使用– OutputFilePath &lt; 字串完整的檔路徑 &gt; 。 若要定義– OutputFilePath 參數，請以引號括住的字串格式，提供路徑和檔案名做為參數的一部分 (例如，C:\LogFiles\SearchOutput.txt) 。 在此範例中，您必須確定目錄 C:\LogFiles 存在，且您具有讀取和寫入 (NTFS 許可權的許可權，才能修改資料夾中) 檔案。 輸出會附加到，而且不會覆寫。 如果您需要個別的檔案，請為每個搜尋定義不同的檔案名。

    
    </div>
    
    例如：
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>使用集中式記錄服務，在集區或電腦上執行基本搜尋

1.  若要將搜尋限制在特定集區或電腦上，請使用– computer 參數搭配電腦完全限定名稱所定義的電腦，並以引號括住，並以逗號分隔，如下所示：
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    例如：
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  若要搜尋一部以上的電腦，請輸入多個以引號括住的電腦名稱稱，並以逗號隔開，如下所示：
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  如果您需要搜尋整個集區，而不是單一電腦，請將-computer 參數變更為–集區、移除電腦名稱稱，然後以逗號分隔的引號或集區取代。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  使用搜尋命令時，集區可以是部署中的任何集區，例如前端集區、Edge 集區、Persistent Chat Server 集區，或定義為部署中集區的其他集區。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>使用時間參數執行搜尋

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  根據預設，搜尋的時間特有參數的開始時間為30分鐘，在您啟動搜尋的時間之前。 換句話說，如果您在 4:00:00 PM 啟動搜尋，則搜尋會搜尋記錄檔，以供您從 3:30:00 PM 定義的電腦及集區，直到 4:00:00 PM 為止。 如果您需要在目前的時間之前搜尋60分鐘或3小時，請使用– StartTime 參數，並設定日期和時間字串，以指出您要搜尋開始的時間。
    
    例如，您可以使用– StartTime 和– EndTime 來定義時間和日期範圍，您可以在您的集區上的11/20/2012 上的淩晨8點到9點之間定義搜尋。 您可以設定輸出路徑，將結果寫入名為 c：logfile.txt 的檔案， \\ 如下所示：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > 您指定的時間和日期字串可以是 "date time" 或 "time date。 「命令會剖析字串，並使用適當的日期和時間值。

    
    </div>

3.  如果您想要從11/20/2012 上的 11:00:00 AM 開始取得記錄檔，請定義– StartTime。 除非您定義特定– EndTime，否則搜尋的預設時間範圍是30分鐘。 結果搜尋會從所定義的電腦或集區傳回記錄，從 11:00:00 AM 到 11:30:00 AM。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  若要在特定時間內執行記錄檔的搜尋，請定義– StartTime 和– EndTime。 您需要在 edge01.contoso.net 電腦上以 1 PM 到 2:45 PM 的記錄。
    
    例如：
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>使用其他準則及符合選項執行高級搜尋

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  若要執行命令來收集特定元件的追蹤，請輸入下列專案：
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    例如：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    結果搜尋會傳回所有在您的部署中，所有電腦及集區上都有 SIPStack、S4 及 UserServices 追蹤元件的記錄專案，且過去30分鐘。

3.  若要將使用相同元件的搜尋限制在您的前端集區中（名為 pool01.contoso.net），請輸入：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  具有多個參數的命令的預設搜尋邏輯是使用邏輯或每個已定義的參數。 您可以指定 **-MatchAll** 參數來變更此行為。 若要這麼做，請輸入下列專案：
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  如果您的案例已設定為持續執行（例如 AlwaysOn），或是定義長時間執行案例記錄檔可能會從本機電腦移至檔案共用。 您可以使用 CacheFileNetworkFolder 參數，使用 New-CsClsConfiguration 建立新的設定或修改具有 Set-CsClsConfiguration 的現有設定，以定義檔共用。 如果您不想讓搜尋在要搜尋的記錄檔集合中包含檔案共用，請使用 SkipNetworkLogs 參數，如下所示：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

