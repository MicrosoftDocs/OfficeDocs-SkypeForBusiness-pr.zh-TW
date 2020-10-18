---
title: 在集中式記錄服務建立的捕獲記錄中使用搜尋
description: 針對集中式記錄服務建立的捕獲記錄使用搜尋。
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
ms.openlocfilehash: 2f6517dd3a9df749d2fe65f1b594b9d21204d7fa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580249"
---
# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="293b0-103">在 Lync Server 2013 中使用集中式記錄服務所建立之捕獲記錄檔的搜尋</span><span class="sxs-lookup"><span data-stu-id="293b0-103">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="293b0-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="293b0-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="293b0-105">集中式記錄服務中的搜尋功能非常有用，而且很強大，原因如下：</span><span class="sxs-lookup"><span data-stu-id="293b0-105">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="293b0-106">搜尋和結果是依據您所定義的準則，在單一電腦、集區、網站或全域範圍上所執行的。</span><span class="sxs-lookup"><span data-stu-id="293b0-106">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="293b0-p101">您的搜尋可能一開始很廣泛，之後可以縮小至更具鎖定性的準則，如時間、元件或電腦。當搜尋準則變更時，擁有相同記錄的搜尋並不需要再次執行記錄工作階段。</span><span class="sxs-lookup"><span data-stu-id="293b0-p101">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer. You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="293b0-p102">系統會在範圍內的所有電腦和集區中收集搜尋的結果，並將其收集彙總為單一的輸出檔，由該輸出檔來代表搜尋準則的所有結果 (僅限已執行案例，且由案例擷取的資料)。您是使用類似 **Snooper** 或**記事本**之類的工具來讀取輸出檔，以及整個部署的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="293b0-p102">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios). You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="293b0-p103">每部個別電腦上的 CLSAgent 會依據案例 (任何給定時間每部電腦可以執行兩個案例) 來建立記錄。CLSAgent 會管理記錄和其相關聯的索引和快取檔案。當您定義並執行搜尋時，搜尋命令會指示 CLSAgent 所應擷取的資訊。CLSAgent 會依據記錄檔、快取檔案和索引檔案來執行查詢，並將搜尋結果傳至 CLSContoller。CLSController 會收到來自搜尋範圍內所有電腦和集區的搜尋結果。之後，CLSController 會彙總 (組合) 記錄，並以時間差順序排列，最舊的項目優先，依序進行，最新的項目則最後處理。</span><span class="sxs-lookup"><span data-stu-id="293b0-p103">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time). The logs and their associated index and cache files are managed by the CLSAgent. When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved. The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller. The CLSController receives the search results from all computers and pools in the scope of the search. The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="293b0-117">在每次搜尋之後，會執行 **Sync-CsClsLogging** Cmdlet，它會刷新搜尋所使用的快取 (不會混淆 CLSAgent) 所維護的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="293b0-117">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="293b0-118">清洗快取有助於確定在下一個搜尋作業的 CLSController 有乾淨的記錄檔和追蹤檔案擷取緩衝區。</span><span class="sxs-lookup"><span data-stu-id="293b0-118">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="293b0-119">若要取得集中式記錄服務的最大好處，您必須充分瞭解如何設定搜尋，只從電腦及集區記錄中只傳回追蹤訊息，這些記錄是與您正在搜尋之問題相關的。</span><span class="sxs-lookup"><span data-stu-id="293b0-119">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="293b0-120">問題</span><span class="sxs-lookup"><span data-stu-id="293b0-120">issues</span></span>

<span data-ttu-id="293b0-121">若要使用 Lync Server 管理命令介面來執行集中式記錄服務搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組的成員，或是包含這兩個群組之任一個自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="293b0-121">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="293b0-122">若要傳回所有獲指派此 Cmdlet 的 RBAC 角色清單 (包含您自行建立的自訂 RBAC 角色) ，請從 Lync Server 管理命令介面或 Windows PowerShell 提示中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="293b0-122">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="293b0-123">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-123">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="293b0-124">本主題的其餘部分著重說明如何定義搜尋以優化疑難排解。</span><span class="sxs-lookup"><span data-stu-id="293b0-124">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="293b0-125">使用集中式記錄服務執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="293b0-125">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="293b0-126">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="293b0-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="293b0-127">請確定您已在全域範圍的部署中執行 AlwaysOn 案例，然後在命令提示字元處輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="293b0-127">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="293b0-128">根據預設，Search-CsClsLogging 會將搜尋結果傳送至主控台。</span><span class="sxs-lookup"><span data-stu-id="293b0-128">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="293b0-129">如果您想要將搜尋結果儲存至檔案，請使用– OutputFilePath &lt; 字串完整的檔路徑 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="293b0-129">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="293b0-130">若要定義– OutputFilePath 參數，請以引號括住的字串格式，提供路徑和檔案名做為參數的一部分 (例如，C:\LogFiles\SearchOutput.txt) 。</span><span class="sxs-lookup"><span data-stu-id="293b0-130">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="293b0-131">在此範例中，您必須確定目錄 C:\LogFiles 存在，且您具有讀取和寫入 (NTFS 許可權的許可權，才能修改資料夾中) 檔案。</span><span class="sxs-lookup"><span data-stu-id="293b0-131">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="293b0-132">輸出會附加到，而且不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="293b0-132">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="293b0-133">如果您需要個別的檔案，請為每個搜尋定義不同的檔案名。</span><span class="sxs-lookup"><span data-stu-id="293b0-133">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="293b0-134">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-134">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="293b0-135">使用集中式記錄服務，在集區或電腦上執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="293b0-135">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="293b0-136">若要將搜尋限制在特定集區或電腦上，請使用– computer 參數搭配電腦完全限定名稱所定義的電腦，並以引號括住，並以逗號分隔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="293b0-136">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="293b0-137">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-137">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="293b0-138">若要搜尋一部以上的電腦，請輸入多個以引號括住的電腦名稱稱，並以逗號隔開，如下所示：</span><span class="sxs-lookup"><span data-stu-id="293b0-138">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="293b0-139">如果您需要搜尋整個集區，而不是單一電腦，請將-computer 參數變更為–集區、移除電腦名稱稱，然後以逗號分隔的引號或集區取代。</span><span class="sxs-lookup"><span data-stu-id="293b0-139">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="293b0-140">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-140">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="293b0-141">使用搜尋命令時，集區可以是部署中的任何集區，例如前端集區、Edge 集區、Persistent Chat Server 集區，或定義為部署中集區的其他集區。</span><span class="sxs-lookup"><span data-stu-id="293b0-141">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="293b0-142">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-142">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="293b0-143">使用時間參數執行搜尋</span><span class="sxs-lookup"><span data-stu-id="293b0-143">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="293b0-144">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="293b0-144">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="293b0-145">根據預設，搜尋的時間特有參數的開始時間為30分鐘，在您啟動搜尋的時間之前。</span><span class="sxs-lookup"><span data-stu-id="293b0-145">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search.</span></span> <span data-ttu-id="293b0-146">換句話說，如果您在 4:00:00 PM 啟動搜尋，則搜尋會搜尋記錄檔，以供您從 3:30:00 PM 定義的電腦及集區，直到 4:00:00 PM 為止。</span><span class="sxs-lookup"><span data-stu-id="293b0-146">In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM.</span></span> <span data-ttu-id="293b0-147">如果您需要在目前的時間之前搜尋60分鐘或3小時，請使用– StartTime 參數，並設定日期和時間字串，以指出您要搜尋開始的時間。</span><span class="sxs-lookup"><span data-stu-id="293b0-147">If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="293b0-148">例如，您可以使用– StartTime 和– EndTime 來定義時間和日期範圍，您可以在您的集區上的11/20/2012 上的淩晨8點到9點之間定義搜尋。</span><span class="sxs-lookup"><span data-stu-id="293b0-148">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="293b0-149">您可以設定輸出路徑，將結果寫入名為 c：logfile.txt 的檔案， \\ 如下所示：</span><span class="sxs-lookup"><span data-stu-id="293b0-149">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="293b0-150">您指定的時間和日期字串可以是 "date time" 或 "time date。</span><span class="sxs-lookup"><span data-stu-id="293b0-150">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="293b0-151">「命令會剖析字串，並使用適當的日期和時間值。</span><span class="sxs-lookup"><span data-stu-id="293b0-151">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="293b0-152">如果您想要從11/20/2012 上的 11:00:00 AM 開始取得記錄檔，請定義– StartTime。</span><span class="sxs-lookup"><span data-stu-id="293b0-152">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime.</span></span> <span data-ttu-id="293b0-153">除非您定義特定– EndTime，否則搜尋的預設時間範圍是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="293b0-153">The default time range for the search is 30 minutes unless you define a specific –EndTime.</span></span> <span data-ttu-id="293b0-154">結果搜尋會從所定義的電腦或集區傳回記錄，從 11:00:00 AM 到 11:30:00 AM。</span><span class="sxs-lookup"><span data-stu-id="293b0-154">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="293b0-155">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-155">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="293b0-156">若要在特定時間內執行記錄檔的搜尋，請定義– StartTime 和– EndTime。</span><span class="sxs-lookup"><span data-stu-id="293b0-156">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime.</span></span> <span data-ttu-id="293b0-157">您需要在 edge01.contoso.net 電腦上以 1 PM 到 2:45 PM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="293b0-157">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="293b0-158">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-158">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="293b0-159">使用其他準則及符合選項執行高級搜尋</span><span class="sxs-lookup"><span data-stu-id="293b0-159">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="293b0-160">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="293b0-160">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="293b0-161">若要執行命令來收集特定元件的追蹤，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="293b0-161">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="293b0-162">例如：</span><span class="sxs-lookup"><span data-stu-id="293b0-162">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="293b0-163">結果搜尋會傳回所有在您的部署中，所有電腦及集區上都有 SIPStack、S4 及 UserServices 追蹤元件的記錄專案，且過去30分鐘。</span><span class="sxs-lookup"><span data-stu-id="293b0-163">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="293b0-164">若要將使用相同元件的搜尋限制在您的前端集區中（名為 pool01.contoso.net），請輸入：</span><span class="sxs-lookup"><span data-stu-id="293b0-164">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="293b0-165">具有多個參數的命令的預設搜尋邏輯是使用邏輯或每個已定義的參數。</span><span class="sxs-lookup"><span data-stu-id="293b0-165">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="293b0-166">您可以指定 **-MatchAll** 參數來變更此行為。</span><span class="sxs-lookup"><span data-stu-id="293b0-166">You can change this behavior by specifying the **–MatchAll** parameter.</span></span> <span data-ttu-id="293b0-167">若要這麼做，請輸入下列專案：</span><span class="sxs-lookup"><span data-stu-id="293b0-167">To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="293b0-168">如果您的案例已設定為持續執行（例如 AlwaysOn），或是定義長時間執行案例記錄檔可能會從本機電腦移至檔案共用。</span><span class="sxs-lookup"><span data-stu-id="293b0-168">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="293b0-169">您可以使用 CacheFileNetworkFolder 參數，使用 New-CsClsConfiguration 建立新的設定或修改具有 Set-CsClsConfiguration 的現有設定，以定義檔共用。</span><span class="sxs-lookup"><span data-stu-id="293b0-169">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="293b0-170">如果您不想讓搜尋在要搜尋的記錄檔集合中包含檔案共用，請使用 SkipNetworkLogs 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="293b0-170">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

