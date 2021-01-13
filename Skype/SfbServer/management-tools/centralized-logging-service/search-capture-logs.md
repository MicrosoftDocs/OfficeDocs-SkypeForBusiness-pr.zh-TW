---
title: 商務用 Skype Server 2015 中的集中式記錄服務所建立的搜尋捕獲記錄檔
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：瞭解如何在商務用 Skype Server 2015 中搜尋及讀取集中式記錄服務捕獲記錄。
ms.openlocfilehash: 1a030e18f9e59fa26c4bd51aa8c6e69dd96004ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835123"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="6c33f-103">商務用 Skype Server 2015 中的集中式記錄服務所建立的搜尋捕獲記錄檔</span><span class="sxs-lookup"><span data-stu-id="6c33f-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6c33f-104">**摘要：** 瞭解如何在商務用 Skype Server 2015 中搜尋及讀取集中式記錄服務捕獲記錄。</span><span class="sxs-lookup"><span data-stu-id="6c33f-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6c33f-105">集中式記錄服務中的搜尋功能非常有用，而且很強大，原因如下：</span><span class="sxs-lookup"><span data-stu-id="6c33f-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="6c33f-106">搜尋和結果是依據您所定義的準則，在單一電腦、集區、網站或全域範圍上所執行的。</span><span class="sxs-lookup"><span data-stu-id="6c33f-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="6c33f-107">您的搜尋可能一開始很廣泛，之後可以縮小至更具鎖定性的準則，如時間、元件或電腦。</span><span class="sxs-lookup"><span data-stu-id="6c33f-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="6c33f-108">您可以對相同的記錄進行搜尋，而且不需要在搜尋準則變更時再次執行記錄會話。</span><span class="sxs-lookup"><span data-stu-id="6c33f-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="6c33f-p102">系統會在範圍內的所有電腦和集區中收集搜尋的結果，並將其收集彙總為單一的輸出檔，由該輸出檔來代表搜尋準則的所有結果 (僅限已執行案例，且由案例擷取的資料)。您是使用類似 **Snooper** 或 **記事本** 之類的工具來讀取輸出檔，以及整個部署的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="6c33f-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="6c33f-p103">每部個別電腦上的 CLSAgent 會依據案例 (任何給定時間每部電腦可以執行兩個案例) 來建立記錄。CLSAgent 會管理記錄和其相關聯的索引和快取檔案。當您定義並執行搜尋時，搜尋命令會指示 CLSAgent 所應擷取的資訊。CLSAgent 會依據記錄檔、快取檔案和索引檔案來執行查詢，並將搜尋結果傳至 CLSContoller。CLSController 會收到來自搜尋範圍內所有電腦和集區的搜尋結果。之後，CLSController 會彙總 (組合) 記錄，並以時間差順序排列，最舊的項目優先，依序進行，最新的項目則最後處理。</span><span class="sxs-lookup"><span data-stu-id="6c33f-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="6c33f-117">在每次搜尋之後，會執行 **Sync-CsClsLogging** Cmdlet，它會刷新搜尋所使用的快取 (不會混淆 CLSAgent) 所維護的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="6c33f-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="6c33f-118">清洗快取有助於確定在下一個搜尋作業的 CLSController 有乾淨的記錄檔和追蹤檔案擷取緩衝區。</span><span class="sxs-lookup"><span data-stu-id="6c33f-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="6c33f-119">若要取得集中式記錄服務的最大好處，您必須充分瞭解如何設定搜尋，只從電腦及集區記錄中只傳回追蹤訊息，這些記錄是與您正在搜尋之問題相關的。</span><span class="sxs-lookup"><span data-stu-id="6c33f-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="6c33f-120">問題</span><span class="sxs-lookup"><span data-stu-id="6c33f-120">issues</span></span>
  
<span data-ttu-id="6c33f-121">若要使用商務用 Skype Server 管理命令介面來執行集中式記錄服務搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="6c33f-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="6c33f-122">若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包括您自行建立的任何自訂 RBAC 角色) ，請從商務用 Skype Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="6c33f-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="6c33f-123">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-123">For example:</span></span>
  
```PowerShell
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="6c33f-124">本主題的其餘部分著重說明如何定義搜尋以優化疑難排解。</span><span class="sxs-lookup"><span data-stu-id="6c33f-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="6c33f-125">使用集中式記錄服務執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="6c33f-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="6c33f-126">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6c33f-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6c33f-127">請確定您已在全域範圍的部署中執行 AlwaysOn 案例，然後在命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="6c33f-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="6c33f-128">根據預設，Search-CsClsLogging 會將搜尋結果傳送至主控台。</span><span class="sxs-lookup"><span data-stu-id="6c33f-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="6c33f-129">如果您想要將搜尋結果儲存至檔案，請使用-OutputFilePath  _\<string fully qualified file path\>_ 。</span><span class="sxs-lookup"><span data-stu-id="6c33f-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="6c33f-130">若要定義-OutputFilePath 參數，請以引號括住的字串格式，提供路徑和檔案名做為參數的一部分 (例如，C:\LogFiles\SearchOutput.txt) 。</span><span class="sxs-lookup"><span data-stu-id="6c33f-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="6c33f-131">在此範例中，您必須確定目錄 C:\LogFiles 存在，且您具有讀取和寫入 (NTFS 許可權的許可權，才能修改資料夾中) 檔案。</span><span class="sxs-lookup"><span data-stu-id="6c33f-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="6c33f-132">輸出會附加到，而且不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="6c33f-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="6c33f-133">如果您需要個別的檔案，請為每個搜尋定義不同的檔案名。</span><span class="sxs-lookup"><span data-stu-id="6c33f-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="6c33f-134">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-134">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="6c33f-135">使用集中式記錄服務，在集區或電腦上執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="6c33f-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="6c33f-136">若要將搜尋限制在特定集區或電腦上，請將-computer 參數與電腦完整名稱所定義的電腦搭配使用-computer 參數，並以引號括住，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c33f-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="6c33f-137">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-137">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="6c33f-138">若要搜尋一部以上的電腦，請輸入多個以引號括住的電腦名稱稱，並以逗號隔開，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c33f-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="6c33f-139">如果您需要搜尋整個集區，而不是單一電腦，請將-computer 參數變更為集區、移除電腦名稱稱，然後以逗號分隔的引號或集區取代。</span><span class="sxs-lookup"><span data-stu-id="6c33f-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="6c33f-140">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-140">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="6c33f-141">使用搜尋命令時，集區可以是部署中的任何集區，例如前端集區、Edge 集區、Persistent Chat Server 集區，或定義為部署中集區的其他集區。</span><span class="sxs-lookup"><span data-stu-id="6c33f-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="6c33f-142">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-142">For example:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="6c33f-143">使用時間參數執行搜尋</span><span class="sxs-lookup"><span data-stu-id="6c33f-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="6c33f-144">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6c33f-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6c33f-145">根據預設，搜尋的時間特有參數的開始時間是在您啟動搜尋之後五分鐘之前的25分鐘。</span><span class="sxs-lookup"><span data-stu-id="6c33f-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="6c33f-146">換句話說，如果我們在 4:00:00 PM 進行搜尋，則搜尋開始時間會顯示為 3:35:00 PM 至 4:05:00 PM。</span><span class="sxs-lookup"><span data-stu-id="6c33f-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="6c33f-147">如果您需要在目前的時間之前搜尋60分鐘或3小時，請使用-StartTime 參數，並設定日期和時間字串，以表示您想要搜尋開始的時間。</span><span class="sxs-lookup"><span data-stu-id="6c33f-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="6c33f-148">例如，使用-StartTime 和-EndTime 若要定義時間和日期範圍，您可以在您的集區上的11/20/2012 上的淩晨8點到9點之間定義搜尋。</span><span class="sxs-lookup"><span data-stu-id="6c33f-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="6c33f-149">您可以設定輸出路徑，將結果寫入名為 c:\logfile.txt 的檔案中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c33f-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="6c33f-150">您指定的時間和日期字串可以是 "date time" 或 "time date。</span><span class="sxs-lookup"><span data-stu-id="6c33f-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="6c33f-151">「命令會剖析字串，並在您執行 Cmdlet 的機器上，使用適當的日期和時間值，以及您的地區設定和區域性設定。</span><span class="sxs-lookup"><span data-stu-id="6c33f-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="6c33f-152">如果您想要從11/20/2012 上的 11:00:00 AM 開始取得記錄檔，請定義-StartTime。</span><span class="sxs-lookup"><span data-stu-id="6c33f-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="6c33f-153">除非您定義特定的-EndTime，否則搜尋的預設時間範圍是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="6c33f-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="6c33f-154">結果搜尋會從所定義的電腦或集區傳回記錄，從 11:00:00 AM 到 11:30:00 AM。</span><span class="sxs-lookup"><span data-stu-id="6c33f-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="6c33f-155">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-155">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="6c33f-156">若要在特定時間內執行記錄檔的搜尋，請定義-StartTime 和-EndTime。</span><span class="sxs-lookup"><span data-stu-id="6c33f-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="6c33f-157">您需要在 edge01.contoso.net 電腦上以 1 PM 到 2:45 PM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="6c33f-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="6c33f-158">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="6c33f-159">使用其他準則及符合選項執行高級搜尋</span><span class="sxs-lookup"><span data-stu-id="6c33f-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="6c33f-160">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="6c33f-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6c33f-161">若要執行命令來收集特定元件的追蹤，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="6c33f-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="6c33f-162">例如：</span><span class="sxs-lookup"><span data-stu-id="6c33f-162">For example:</span></span>
    
  ```PowerShell
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="6c33f-163">結果搜尋會傳回所有在您的部署中，所有電腦及集區上都有 SIPStack、S4 及 UserServices 追蹤元件的記錄專案，且過去30分鐘。</span><span class="sxs-lookup"><span data-stu-id="6c33f-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="6c33f-164">若要將使用相同元件的搜尋限制在您的前端集區中（名為 pool01.contoso.net），請輸入：</span><span class="sxs-lookup"><span data-stu-id="6c33f-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="6c33f-165">具有多個參數的命令的預設搜尋邏輯是使用邏輯或每個已定義的參數。</span><span class="sxs-lookup"><span data-stu-id="6c33f-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="6c33f-166">您可以指定 **-MatchAll** 參數來變更此行為。</span><span class="sxs-lookup"><span data-stu-id="6c33f-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="6c33f-167">若要這麼做，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="6c33f-167">To do this, type the following:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="6c33f-168">如果您的案例已設定為持續執行（例如 AlwaysOn），或是定義長時間執行案例記錄檔可能會從本機電腦移至檔案共用。</span><span class="sxs-lookup"><span data-stu-id="6c33f-168">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="6c33f-169">您可以使用 CacheFileNetworkFolder 參數，使用 New-CsClsConfiguration 建立新的設定或修改具有 Set-CsClsConfiguration 的現有設定，以定義檔共用。</span><span class="sxs-lookup"><span data-stu-id="6c33f-169">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="6c33f-170">如果您不想讓搜尋在要搜尋的記錄檔集合中包含檔案共用，請使用 SkipNetworkLogs 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6c33f-170">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```PowerShell
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="6c33f-171">從集中式記錄服務讀取捕獲記錄檔</span><span class="sxs-lookup"><span data-stu-id="6c33f-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="6c33f-172">在您執行搜尋後，您就可以充分利用集中式記錄服務，您可以用來追蹤已報告問題的檔案。</span><span class="sxs-lookup"><span data-stu-id="6c33f-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="6c33f-173">您可以使用許多方式來讀取檔案。</span><span class="sxs-lookup"><span data-stu-id="6c33f-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="6c33f-174">輸出檔是標準的文字格式，您可以使用 Notepad.exe 或任何其他可讓您開啟及讀取文字檔的程式。</span><span class="sxs-lookup"><span data-stu-id="6c33f-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="6c33f-175">針對較大的檔案和更複雜的問題，您可以使用類似 Snooper.exe 的工具，以用於讀取及分析集中式記錄服務的記錄輸出。</span><span class="sxs-lookup"><span data-stu-id="6c33f-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="6c33f-176">Snooper 包含可供個別下載之調試工具。</span><span class="sxs-lookup"><span data-stu-id="6c33f-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="6c33f-177">您可以在以下位置下載調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257) 。</span><span class="sxs-lookup"><span data-stu-id="6c33f-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="6c33f-178">當您安裝調試工具時，不會建立簡短的剪下及功能表項目目。</span><span class="sxs-lookup"><span data-stu-id="6c33f-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="6c33f-179">安裝調試工具之後，請開啟 Windows Explorer、命令列視窗或商務用 Skype Server 管理命令介面，然後移至 (預設位置的目錄) C:\Program Files\Skype for Business Server 2015 \ 調試工具。</span><span class="sxs-lookup"><span data-stu-id="6c33f-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="6c33f-180">在 [Snooper.exe] 或 [輸入 Snooper.exe] 中按兩下，如果使用命令列或商務用 Skype Server 管理命令介面，請按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="6c33f-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6c33f-181">本主題的目的不是詳細討論和討論疑難排解技術。</span><span class="sxs-lookup"><span data-stu-id="6c33f-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="6c33f-182">疑難排解及其周圍的程式是複雜的主體。</span><span class="sxs-lookup"><span data-stu-id="6c33f-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="6c33f-183">如需疑難排解基本及疑難排解特定工作負載的詳細資訊，請參閱《 Microsoft Lync Server 2010 Resource 工具組手冊》 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003) 。</span><span class="sxs-lookup"><span data-stu-id="6c33f-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="6c33f-184">處理常式和程式仍適用于商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="6c33f-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="6c33f-185">若要在 Snooper 中開啟記錄檔</span><span class="sxs-lookup"><span data-stu-id="6c33f-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="6c33f-186">若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。</span><span class="sxs-lookup"><span data-stu-id="6c33f-186">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="6c33f-187">若要使用 Snooper 和存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="6c33f-187">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="6c33f-188">在安裝調試工具 ( # A0) 之後，使用 Windows Explorer 或從命令列變更目錄至 Snooper.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="6c33f-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="6c33f-189">根據預設，調試工具位於 C:\Program Files\Skype for Business Server 2015 \ 調試工具。</span><span class="sxs-lookup"><span data-stu-id="6c33f-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="6c33f-190">按兩下或執行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="6c33f-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="6c33f-191">開啟 Snooper 後，以滑鼠 **按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，選取 [ **開啟** ] 對話方塊中的檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="6c33f-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="6c33f-192">記錄檔的 **追蹤** 訊息會顯示在 [ **追蹤** ] 索引標籤上。按一下 [ **訊息** ] 索引標籤，以查看收集之追蹤的郵件內容。</span><span class="sxs-lookup"><span data-stu-id="6c33f-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="6c33f-193">顯示通話流程圖表</span><span class="sxs-lookup"><span data-stu-id="6c33f-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="6c33f-194">若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。</span><span class="sxs-lookup"><span data-stu-id="6c33f-194">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="6c33f-195">若要使用 Snooper 並存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="6c33f-195">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="6c33f-196">開啟記錄檔，然後按一下 [ **訊息** ] 索引標籤，在 [ **追蹤** ] 索引標籤上選取 [交談]，或選取一個追蹤元件。</span><span class="sxs-lookup"><span data-stu-id="6c33f-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="6c33f-197">按一下 [ **通話流程**]。</span><span class="sxs-lookup"><span data-stu-id="6c33f-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="6c33f-198">如果您按一下的訊息或追蹤不是通話流程的一部分，將不會顯示圖表，而且會在 Snooper 的底部顯示狀態訊息，指出「這封郵件不符合 callfow」。</span><span class="sxs-lookup"><span data-stu-id="6c33f-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="6c33f-199">選擇 [另一封郵件] 或 [追蹤]，如果郵件或追蹤屬於通話流程的一部分，就會顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="6c33f-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="6c33f-200">在訊息或追蹤列間移動，並附注通話流程圖表是否更新或變更，以顯示新的圖表。</span><span class="sxs-lookup"><span data-stu-id="6c33f-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="6c33f-201">將游標移到元素上，以取得通話訊息、端點及其他元件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="6c33f-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
