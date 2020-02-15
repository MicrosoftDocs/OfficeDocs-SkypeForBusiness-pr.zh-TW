---
title: 使用集中式記錄服務所建立的擷取記錄上的搜尋
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
ms.openlocfilehash: 9f9571f2efe08eb13091c3d3660e7760a8e805c8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a>使用集中式記錄服務在 Lync Server 2013 中建立的擷取記錄上的搜尋

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-21_

The Centralized Logging Service 中的搜尋功能是非常實用和強大的原因如下：

  - 搜尋和結果是依據您所定義的準則，在單一電腦、集區、網站或全域範圍上所執行的。

  - 您的搜尋可能一開始很廣泛，之後可以縮小至更具鎖定性的準則，如時間、元件或電腦。當搜尋準則變更時，擁有相同記錄的搜尋並不需要再次執行記錄工作階段。

  - 系統會在範圍內的所有電腦和集區中收集搜尋的結果，並將其收集彙總為單一的輸出檔，由該輸出檔來代表搜尋準則的所有結果 (僅限已執行案例，且由案例擷取的資料)。您是使用類似 **Snooper** 或**記事本**之類的工具來讀取輸出檔，以及整個部署的追蹤訊息。

每部個別電腦上的 CLSAgent 會依據案例 (任何給定時間每部電腦可以執行兩個案例) 來建立記錄。CLSAgent 會管理記錄和其相關聯的索引和快取檔案。當您定義並執行搜尋時，搜尋命令會指示 CLSAgent 所應擷取的資訊。CLSAgent 會依據記錄檔、快取檔案和索引檔案來執行查詢，並將搜尋結果傳至 CLSContoller。CLSController 會收到來自搜尋範圍內所有電腦和集區的搜尋結果。之後，CLSController 會彙總 (組合) 記錄，並以時間差順序排列，最舊的項目優先，依序進行，最新的項目則最後處理。

每個搜尋之後**Sync-csclslogging** cmdlet 執行時，會清除 （不適用於由 clsagent 的通訊所維護的快取檔案與混淆） 搜尋所使用的快取。 清除快取，可協助確保在下一個搜尋作業 CLSController 已清除記錄檔和追蹤檔案擷取緩衝區。

若要獲得最大從 the Centralized Logging Service，您需要的確實了解如何設定搜尋以返回只追蹤訊息從電腦和集區的記錄檔與相關的問題，您正在研究。 問題

若要使用 Lync Server 管理命令介面中執行 Centralized Logging Service 搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含的自訂 RBAC 角色的成員其中一個這兩個群組。 若要傳回所有獲指派此 cmdlet 的 RBAC 角色清單 （包括您自行建立的任何自訂 RBAC 角色），請從 [Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

例如：

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

本主題的其餘部分著重於如何定義搜尋，以最佳化您的疑難排解。

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a>若要使用集中式記錄服務來執行基本搜尋

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  請確定您有在全域範圍部署中執行 AlwaysOn 案例，然後在命令提示字元處輸入下列：
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > 根據預設，Search-csclslogging 會將搜尋結果傳送至主控台。 如果您想要將搜尋結果儲存至檔案，使用 – OutputFilePath&lt;字串完整的檔案路徑&gt;。 若要定義 – OutputFilePath 參數，請提供路徑及檔案名稱 （例如，以引號括住的字串格式中的參數的一部分C:\LogFiles\SearchOutput.txt)。 在這個範例中，您必須確定 C:\LogFiles 存在的目錄，並可讀取及寫入 （NTFS 權限修改） 檔案的資料夾中的權限。 輸出附加至，並且不會覆寫。 如果您需要個別的檔案，定義每個搜尋的不同的檔案名稱。

    
    </div>
    
    例如：
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a>若要使用 the Centralized Logging Service 集區或電腦上執行基本搜尋

1.  若要限制只搜尋特定的集區或電腦，使用 – Computers 參數與電腦的電腦完整名稱所定義，以引號括住並以逗號分隔，如下所示：
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    例如：
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  若要搜尋多部電腦，請輸入多個電腦名稱以引號括住，並以逗號分隔，如下所示：
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  如果您需要搜尋整個而不是在單一電腦集區，變更為 – 集區]，移除電腦名稱，並取代 – Computers 參數它與集區或引號括住的集區以逗號隔開。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  使用搜尋命令，當集區可以是在您部署中，例如前端集區、 Edge 集區、 Persistent Chat Server 集區]，或是其他集區部署中所定義的任何集區。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a>若要使用時間參數來執行搜尋

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  根據預設，搜尋特定時間參數的開始時間是 30 分鐘，在您啟動搜尋的時間之前。 也就是說，如果您起始下午 4:00:00 搜尋，搜尋會搜尋的電腦和集區，您定義從 3:30:00 PM 4:00:00 PM 之前的記錄檔。 如果您需要 60 分鐘或 3 小時前目前時間搜尋，使用 – StartTime 參數，並設定的日期和時間的字串，指出您想要開始搜尋的時間。
    
    例如，藉由使用 – StartTime 和 – EndTime 定義的時間和日期範圍，您可以定義上午 8 和 9 AM 之間搜尋在 2012 年 11/20/上您的集區。 您可以設定將結果寫入名為 c: csv 檔案的輸出路徑\\logfile.txt，如下所示：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > 您指定的時間和日期字串可以是 「 日期時間 」 或 「 時間日期。 「 命令會剖析字串，並使用適當的值為日期和時間。

    
    </div>

3.  如果您想要擷取開頭 11:00:00 AM 2012/11/20 上的記錄檔，您可以定義 – StartTime。 搜尋] 的預設時間範圍是 30 分鐘，除非您定義特定的 – EndTime。 產生搜尋會傳回記錄檔，從已定義的電腦或集區隔離 11:00:00 到上午 11:30:00。
    
    例如：
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  若要在一段特定時間內進行搜尋的記錄，定義 – StartTime 和 – EndTime。 您必須從下午 1 電腦 edge01.contoso.net 下午 2:45 到的記錄檔。
    
    例如：
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a>若要使用其他準則和比對選項執行進階的搜尋

1.  啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。

2.  若要執行命令以收集特定元件的追蹤，請輸入下列命令：
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    例如：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    產生搜尋將傳回的追蹤元件裡包含 SIPStack、 S4 和 UserServices 所有電腦和集區在過去 30 分鐘部署中的所有記錄項目。

3.  若要限制只是前端集區名稱為 pool01.contoso.net 相同元件的搜尋，請輸入：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  具有多個參數的命令的預設搜尋邏輯是每個已定義的參數搭配使用的邏輯 OR。 您可以藉由指定 **– MatchAll**參數變更此行為。 若要這麼做，請輸入下列命令：
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  如果您的案例設為執行不斷，例如 AlwaysOn，或您已定義記錄檔可能會回復移出 3 本機電腦上的檔案共用的長時間執行案例。 您可以藉由使用 New-csclsconfiguration 來建立新的組態或修改現有的設定與 Set-csclsconfiguration 使用 CacheFileNetworkFolder 參數定義的檔案共用。 如果您不想要搜尋的記錄檔之集合中包含的檔案共用的搜尋，使用 SkipNetworkLogs 參數，如下所示：
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

