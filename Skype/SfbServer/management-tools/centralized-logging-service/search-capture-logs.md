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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
description: '摘要: 瞭解如何在商務用 Skype Server 2015 中搜尋及閱讀集中式記錄服務捕獲記錄。'
ms.openlocfilehash: 81bf539c6a06c52354db23bbeea97fb9525cbbd5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186802"
---
# <a name="search-capture-logs-created-by-the-centralized-logging-service-in-skype-for-business-server-2015"></a><span data-ttu-id="4de0b-103">搜尋商務用 Skype 2015 中集中式記錄服務建立的擷取記錄</span><span class="sxs-lookup"><span data-stu-id="4de0b-103">Search capture logs created by the Centralized Logging Service in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4de0b-104">**摘要:** 瞭解如何在商務用 Skype Server 2015 中搜尋及閱讀集中式記錄服務捕獲記錄。</span><span class="sxs-lookup"><span data-stu-id="4de0b-104">**Summary:** Learn how to search and read Centralized Logging Service capture logs in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4de0b-105">集中式記錄服務中的搜尋功能非常有用且功能強大, 原因如下:</span><span class="sxs-lookup"><span data-stu-id="4de0b-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span> 
  
- <span data-ttu-id="4de0b-106">您的搜尋和結果會根據您定義的準則, 在單一電腦、[池]、[網站] 或 [全域範圍] 上執行。</span><span class="sxs-lookup"><span data-stu-id="4de0b-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>
    
- <span data-ttu-id="4de0b-107">您的搜尋可以是最初的廣義, 然後縮小至更具針對性的準則, 例如時間、元件或電腦。</span><span class="sxs-lookup"><span data-stu-id="4de0b-107">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="4de0b-108">您可以在相同的記錄中搜尋, 且不需要在搜尋準則變更時再次執行記錄會議。</span><span class="sxs-lookup"><span data-stu-id="4de0b-108">You search against the same logs and don't need to run a logging session again when the search criteria changes.</span></span>
    
- <span data-ttu-id="4de0b-109">搜尋的結果是從作用域中的所有電腦和池收集、收集並匯總到單一輸出檔案, 代表搜尋準則的所有結果 (僅限於已執行的案例, 以及由所捕獲的資料)。案例)。</span><span class="sxs-lookup"><span data-stu-id="4de0b-109">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios).</span></span> <span data-ttu-id="4de0b-110">您可以使用熟悉的工具 (例如**Snooper**或**記事本**), 從您的整個部署中讀取輸出檔案和追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="4de0b-110">You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>
    
<span data-ttu-id="4de0b-111">每一部電腦上的 CLSAgent 會根據案例或案例建立記錄 (在任何指定時間, 每個電腦都可以執行兩個案例)。</span><span class="sxs-lookup"><span data-stu-id="4de0b-111">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time).</span></span> <span data-ttu-id="4de0b-112">記錄及其相關聯的索引與快取檔案是由 CLSAgent 管理。</span><span class="sxs-lookup"><span data-stu-id="4de0b-112">The logs and their associated index and cache files are managed by the CLSAgent.</span></span> <span data-ttu-id="4de0b-113">當您定義並執行搜尋時, [搜尋] 命令會指示 CLSAgent 應該要檢索哪些資訊。</span><span class="sxs-lookup"><span data-stu-id="4de0b-113">When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved.</span></span> <span data-ttu-id="4de0b-114">CLSAgent 會針對記錄檔、快取檔案和索引檔案執行查詢, 並將搜尋結果傳回 CLSContoller。</span><span class="sxs-lookup"><span data-stu-id="4de0b-114">The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller.</span></span> <span data-ttu-id="4de0b-115">CLSController 會從搜尋範圍中的所有電腦和池接收搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="4de0b-115">The CLSController receives the search results from all computers and pools in the scope of the search.</span></span> <span data-ttu-id="4de0b-116">然後 CLSController 會將記錄匯總 (合併), 並將它們轉換成時間增量順序、最舊的專案, 並持續到最新專案的最後一段時間。</span><span class="sxs-lookup"><span data-stu-id="4de0b-116">The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>
  
<span data-ttu-id="4de0b-117">每次搜尋之後, 會執行**CsClsLogging** Cmdlet, 並會清洗搜尋所使用的快取 (不會與 CLSAgent 所維護的快取檔案混淆)。</span><span class="sxs-lookup"><span data-stu-id="4de0b-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="4de0b-118">清除快取可協助確保 CLSController 中有乾淨的記錄和追蹤檔案擷取緩衝區, 以便進行下一個搜尋操作。</span><span class="sxs-lookup"><span data-stu-id="4de0b-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>
  
<span data-ttu-id="4de0b-119">若要充分發揮集中式記錄服務的優點, 您必須充分瞭解如何將搜尋設定為僅傳回來自電腦的追蹤訊息, 以及與您所研究之問題相關的池記錄。</span><span class="sxs-lookup"><span data-stu-id="4de0b-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="4de0b-120">存在</span><span class="sxs-lookup"><span data-stu-id="4de0b-120">issues</span></span>
  
<span data-ttu-id="4de0b-121">若要使用商務用 Skype Server Management Shell 執行集中式記錄服務搜尋功能, 您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組的成員, 或是自訂的 RBAC 角色包含這兩個群組的其中一個。</span><span class="sxs-lookup"><span data-stu-id="4de0b-121">To run the Centralized Logging Service search functions by using the Skype for Business Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="4de0b-122">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單 (包括您自行建立的任何自訂 RBAC 角色), 請從商務用 Skype Server Management 命令介面或 Windows PowerShell 提示中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="4de0b-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Skype for Business Server Management Shell or the Windows PowerShell prompt:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Skype for Business Server 2015 cmdlet"}
```

<span data-ttu-id="4de0b-123">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-123">For example:</span></span>
  
```
Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}
```

<span data-ttu-id="4de0b-124">本主題的剩餘部分將重點放在如何定義搜尋以優化疑難排解。</span><span class="sxs-lookup"><span data-stu-id="4de0b-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>
  
### <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="4de0b-125">使用集中式記錄服務執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="4de0b-125">To run a basic search by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="4de0b-126">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-126">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4de0b-127">請確定您在部署中的全域範圍內執行了 AlwaysOn 案例, 然後在命令提示字元中輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="4de0b-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
   ```
   Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
   ```

> [!NOTE]
> <span data-ttu-id="4de0b-128">根據預設, 搜尋 CsClsLogging 會將搜尋結果傳送到主控台。</span><span class="sxs-lookup"><span data-stu-id="4de0b-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="4de0b-129">如果您想要將搜尋結果儲存至檔案, 請使用-OutputFilePath _ \<字串的完整檔路徑\>_。</span><span class="sxs-lookup"><span data-stu-id="4de0b-129">If you want to save the search results to a file, use -OutputFilePath  _\<string fully qualified file path\>_.</span></span> <span data-ttu-id="4de0b-130">若要定義-OutputFilePath 參數, 請在以引號括住的字串格式中, 提供路徑和檔案名作為參數的一部分 (例如,C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="4de0b-130">To define the -OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="4de0b-131">在這個範例中, 您必須確保目錄 C:\LogFiles 存在, 且您擁有在資料夾中讀取和寫入 (NTFS 許可權修改) 檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="4de0b-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="4de0b-132">輸出會附加到, 且不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="4de0b-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="4de0b-133">如果您需要個別的檔案, 請為每個搜尋定義不同的檔案名。</span><span class="sxs-lookup"><span data-stu-id="4de0b-133">If you need separate files, define a distinct file name for each search.</span></span> 
  
<span data-ttu-id="4de0b-134">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-134">For example:</span></span>
    
  ```
  Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

### <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="4de0b-135">使用集中式記錄服務在池或電腦上執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="4de0b-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1. <span data-ttu-id="4de0b-136">若要將搜尋限制在特定的池或電腦上, 請使用-電腦參數及電腦完整名稱的電腦 (括在引號中, 並以逗號分隔), 如下所示:</span><span class="sxs-lookup"><span data-stu-id="4de0b-136">To limit the search to a specific pool or computer, use the -Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
   ```
   Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
   ```

<span data-ttu-id="4de0b-137">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-137">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
  ```

2. <span data-ttu-id="4de0b-138">若要搜尋多台電腦, 請輸入多個以引號括住的電腦名稱稱, 並以逗號分隔, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="4de0b-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
   ```
   Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"
   ```

3. <span data-ttu-id="4de0b-139">如果您需要搜尋整個池 (而非單一電腦), 請將-電腦參數變更為 Pool、移除電腦名稱稱, 然後將它取代為以逗號分隔的用引號括住的池中。</span><span class="sxs-lookup"><span data-stu-id="4de0b-139">If you need to search an entire pool instead of a single computer, change the -Computers parameter to -Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="4de0b-140">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-140">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="4de0b-141">使用搜尋命令時, pool 可以是部署中的任何一個池 (例如前端池、邊緣池、持續聊天伺服器池), 或是在您的部署中定義為一個池的其他人。</span><span class="sxs-lookup"><span data-stu-id="4de0b-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="4de0b-142">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-142">For example:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

### <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="4de0b-143">使用時間參數執行搜尋</span><span class="sxs-lookup"><span data-stu-id="4de0b-143">To run a search by using time parameters</span></span>

1. <span data-ttu-id="4de0b-144">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-144">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4de0b-145">根據預設, 搜尋的時間特定參數的開始時間是在您啟動搜尋後五分鐘前的25分鐘。</span><span class="sxs-lookup"><span data-stu-id="4de0b-145">By default, the beginning time for a search's time-specific parameters is 25 minutes prior to five minutes after the time you initiate the search.</span></span> <span data-ttu-id="4de0b-146">換句話說, 如果我們在 4:00:00 PM 進行搜尋, 搜尋開始時間會顯示為 3:35:00 PM 至 4:05:00 PM。</span><span class="sxs-lookup"><span data-stu-id="4de0b-146">In other words, if we search at 4:00:00 PM, then the search start time will show as 3:35:00 PM to 4:05:00 PM.</span></span> <span data-ttu-id="4de0b-147">如果您需要在目前時間前搜尋60分鐘或3小時, 請使用-StartTime 參數並設定日期和時間字串, 以指出您想要搜尋開始的時間。</span><span class="sxs-lookup"><span data-stu-id="4de0b-147">If you need to search 60 minutes or 3 hours prior to the current time, use the -StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span> 
    
    <span data-ttu-id="4de0b-148">例如, 您可以使用-StartTime 和-EndTime 定義時間與日期範圍, 在您的池中, 在11/20/2012 上定義一個在 8 AM 和 9 AM 之間的搜尋。</span><span class="sxs-lookup"><span data-stu-id="4de0b-148">For example, by using -StartTime and -EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="4de0b-149">您可以設定輸出路徑, 將結果寫入名為 c:\logfile.txt 的檔案, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="4de0b-149">You can set the output path to write the results to a file named c:\logfile.txt as follows:</span></span>
    
   ```
   Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

> [!NOTE]
> <span data-ttu-id="4de0b-150">您指定的時間和日期字串可以是 "日期時間" 或 "時間日期"。</span><span class="sxs-lookup"><span data-stu-id="4de0b-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="4de0b-151">「命令會分析字串, 並在執行您執行 Cmdlet 的電腦上, 針對日期和時間以及您的地區設定和文化特性, 使用適當的值。</span><span class="sxs-lookup"><span data-stu-id="4de0b-151">" The command will parse the string and use the appropriate values for date and time and your locale and culture settings on the machine you are running cmdlet from.</span></span> 
  
3. <span data-ttu-id="4de0b-152">如果您想要從11/20/2012 開始的11:00:00 開始檢索記錄, 您可以定義-StartTime。</span><span class="sxs-lookup"><span data-stu-id="4de0b-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the -StartTime.</span></span> <span data-ttu-id="4de0b-153">除非您定義特定的 EndTime, 否則搜尋的預設時間範圍是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="4de0b-153">The default time range for the search is 30 minutes unless you define a specific -EndTime.</span></span> <span data-ttu-id="4de0b-154">產生的搜尋會從已定義的電腦或池中傳回來自 11:00:00 AM 到 11:30:00 AM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="4de0b-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
<span data-ttu-id="4de0b-155">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-155">For example:</span></span>
    
  ```
  Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

4. <span data-ttu-id="4de0b-156">若要在特定的一段時間內進行記錄搜尋, 請定義 [StartTime] 和 [EndTime]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-156">To conduct a search of logs within a specific period of time, define a -StartTime and an -EndTime.</span></span> <span data-ttu-id="4de0b-157">在電腦 edge01.contoso.net 上, 您需要從 1 PM 到 2:45 PM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="4de0b-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span> 
    
<span data-ttu-id="4de0b-158">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-158">For example:</span></span>
    
  ```
  Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

### <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="4de0b-159">使用其他準則和相符選項執行高級搜尋</span><span class="sxs-lookup"><span data-stu-id="4de0b-159">To run an advanced search by using other criteria and matching options</span></span>

1. <span data-ttu-id="4de0b-160">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-160">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4de0b-161">若要執行命令來收集特定元件的蹤跡, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="4de0b-161">To run a command to collect traces for specific components, type the following:</span></span>
    
   ```
   Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
   ```

<span data-ttu-id="4de0b-162">例如：</span><span class="sxs-lookup"><span data-stu-id="4de0b-162">For example:</span></span>
    
  ```
  Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
  ```

<span data-ttu-id="4de0b-163">產生的搜尋會傳回在過去30分鐘內, 您部署中所有電腦和池中都有 SIPStack、S4 和 UserServices 追蹤元件的所有記錄專案。</span><span class="sxs-lookup"><span data-stu-id="4de0b-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>
    
3. <span data-ttu-id="4de0b-164">若要將使用相同元件的搜尋限制為僅限您的前端池 (名為 pool01.contoso.net), 請輸入:</span><span class="sxs-lookup"><span data-stu-id="4de0b-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

4. <span data-ttu-id="4de0b-165">具有多個參數之命令的預設搜尋邏輯是使用邏輯或與每個已定義的參數。</span><span class="sxs-lookup"><span data-stu-id="4de0b-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="4de0b-166">您可以透過指定 **-MatchAll**參數來變更此行為。</span><span class="sxs-lookup"><span data-stu-id="4de0b-166">You can change this behavior by specifying the **-MatchAll** parameter.</span></span> <span data-ttu-id="4de0b-167">若要這樣做, 請輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="4de0b-167">To do this, type the following:</span></span>
    
   ```
   Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

5. <span data-ttu-id="4de0b-168">如果您的案例已設定為持續執行 (例如 AlwaysOn), 或您已定義長時間執行的案例記錄, 可能會將本機電腦放到檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="4de0b-168">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="4de0b-169">您可以使用 CacheFileNetworkFolder 參數來定義檔案共用, 方法是使用 New-CsClsConfiguration 來建立新的設定, 或使用 Set-CsClsConfiguration 修改現有的配置。</span><span class="sxs-lookup"><span data-stu-id="4de0b-169">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="4de0b-170">如果您不希望搜尋將檔案共用包含在要搜尋的記錄集合中, 請使用 SkipNetworkLogs 參數, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="4de0b-170">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
   ```
   Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"
   ```

## <a name="read-capture-logs-from-the-centralized-logging-service"></a><span data-ttu-id="4de0b-171">從集中式記錄服務讀取捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="4de0b-171">Read capture logs from the Centralized Logging Service</span></span>

<span data-ttu-id="4de0b-172">您可以在執行搜尋之後, 充分發揮集中式記錄服務的益處, 而且您有一個檔案可用來追蹤已報告的問題。</span><span class="sxs-lookup"><span data-stu-id="4de0b-172">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="4de0b-173">您可以透過多種方式來讀取檔案。</span><span class="sxs-lookup"><span data-stu-id="4de0b-173">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="4de0b-174">輸出檔案是標準的文字格式, 您可以使用 Notepad.exe 或任何其他能讓您開啟並讀取文字檔的程式。</span><span class="sxs-lookup"><span data-stu-id="4de0b-174">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="4de0b-175">針對較大的檔案和更複雜的問題, 您可以使用類似 Snooper 的工具, 該工具是專門用來從集中式記錄服務讀取及分析記錄輸出。</span><span class="sxs-lookup"><span data-stu-id="4de0b-175">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="4de0b-176">Snooper 包含在可單獨下載的調試工具中。</span><span class="sxs-lookup"><span data-stu-id="4de0b-176">Snooper is included with the Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="4de0b-177">您可以在此處下載調試工具: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257)。</span><span class="sxs-lookup"><span data-stu-id="4de0b-177">You can download the Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?LinkId=285257).</span></span> <span data-ttu-id="4de0b-178">當您安裝 [調試工具] 時, 不會建立快捷方式和功能表項目。</span><span class="sxs-lookup"><span data-stu-id="4de0b-178">When you install the Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="4de0b-179">安裝調試工具之後, 請開啟 Windows 資源管理器、命令列視窗或商務用 Skype Server 管理命令介面, 然後移至目錄 (預設位置) C:\Program Files\Skype for Business Server 2015 \ 調試工具。</span><span class="sxs-lookup"><span data-stu-id="4de0b-179">After you install the Debug Tools, open Windows Explorer, a command-line window, or Skype for Business Server Management Shell and go to the directory (default location) C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="4de0b-180">按兩下 Snooper 或輸入 Snooper, 如果您使用的是命令列或商務用 Skype Server 管理命令介面, 請按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="4de0b-180">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Skype for Business Server Management Shell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4de0b-181">本主題的目的不是詳細說明並討論疑難排解技巧。</span><span class="sxs-lookup"><span data-stu-id="4de0b-181">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="4de0b-182">疑難排解及周圍的程式是一種複雜的主題。</span><span class="sxs-lookup"><span data-stu-id="4de0b-182">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="4de0b-183">如需疑難排解基本功能及特定工作負荷疑難排解的詳細資料, 請參閱 Microsoft Lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003)資源套件活頁簿。</span><span class="sxs-lookup"><span data-stu-id="4de0b-183">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at [https://go.microsoft.com/fwlink/p/?linkId=211003](https://go.microsoft.com/fwlink/p/?linkId=211003).</span></span> <span data-ttu-id="4de0b-184">流程與程式仍適用于商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="4de0b-184">The processes and procedures still apply to Skype for Business Server 2015.</span></span> 
  
### <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="4de0b-185">若要在 Snooper 中開啟記錄檔</span><span class="sxs-lookup"><span data-stu-id="4de0b-185">To open a log file in Snooper</span></span>

1. <span data-ttu-id="4de0b-186">若要使用 Snooper 及開啟記錄檔, 您必須具備記錄檔案的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="4de0b-186">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="4de0b-187">若要使用 Snooper 及存取記錄檔, 您必須是 CsAdministrator 的成員, 或是 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組, 或是包含這兩個群組中任一群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4de0b-187">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> 
    
2. <span data-ttu-id="4de0b-188">安裝調試工具 (LyncDebugTools) 之後, 請使用 Windows 資源管理器或從命令列將目錄變更為 Snooper 的位置。</span><span class="sxs-lookup"><span data-stu-id="4de0b-188">After the installation of the Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="4de0b-189">根據預設, 調試工具位於 C:\Program Files\Skype for Business Server 2015 \ 調試工具中。</span><span class="sxs-lookup"><span data-stu-id="4de0b-189">By default, the debugging tools are located in C:\Program Files\Skype for Business Server 2015\Debugging Tools.</span></span> <span data-ttu-id="4de0b-190">按兩下或執行 Snooper。</span><span class="sxs-lookup"><span data-stu-id="4de0b-190">Double-click or run Snooper.exe.</span></span>
    
3. <span data-ttu-id="4de0b-191">開啟 Snooper 之後, 以滑鼠右鍵按一下\*\*\*\*[檔案], 按一下 [ **OpenFile**], 尋找您的記錄檔, 在 [**開啟**舊檔] 對話方塊中選取檔案, 然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-191">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>
    
4. <span data-ttu-id="4de0b-192">記錄檔的**追蹤**訊息會顯示在 [**追蹤**] 索引標籤上。按一下 [**郵件**] 索引標籤即可查看所收集追蹤的訊息內容。</span><span class="sxs-lookup"><span data-stu-id="4de0b-192">The log file's **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>
    
### <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="4de0b-193">顯示 [通話流程圖] 圖表</span><span class="sxs-lookup"><span data-stu-id="4de0b-193">To display a call flow diagram</span></span>

1. <span data-ttu-id="4de0b-194">若要使用 Snooper 及開啟記錄檔, 您必須具備記錄檔案的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="4de0b-194">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="4de0b-195">若要使用 Snooper 及存取記錄檔, 您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制 (RBAC) 安全性群組的成員, 或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="4de0b-195">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>
    
2. <span data-ttu-id="4de0b-196">開啟記錄檔, 然後按一下 [**訊息**] 索引標籤, 在 [訊息] 視圖中選取交談, 或選取 [**追蹤**] 索引標籤上的追蹤元件。</span><span class="sxs-lookup"><span data-stu-id="4de0b-196">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>
    
3. <span data-ttu-id="4de0b-197">按一下 [**通話流程**]。</span><span class="sxs-lookup"><span data-stu-id="4de0b-197">Click **Call Flow**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="4de0b-198">如果您按一下不屬於通話流程的訊息或追蹤, 圖表就不會出現, 且 Snooper 底部會出現狀態訊息, 指出「此訊息不符合資格, 無法 callfow」。</span><span class="sxs-lookup"><span data-stu-id="4de0b-198">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating "This message is not eligible for callfow".</span></span> <span data-ttu-id="4de0b-199">如果郵件或追蹤是通話流程的一部分, 請選擇 [其他訊息] 或 [追蹤], 就會顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="4de0b-199">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span> 
  
4. <span data-ttu-id="4de0b-200">在訊息或追蹤線之間移動, 並注意 [通話流程圖] 圖表是否會更新或變更以顯示新圖表。</span><span class="sxs-lookup"><span data-stu-id="4de0b-200">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>
    
5. <span data-ttu-id="4de0b-201">將游標暫留在元素上, 以取得通話訊息、端點及其他元件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4de0b-201">Hover over elements to get information about call messages, endpoints, and other components.</span></span>
