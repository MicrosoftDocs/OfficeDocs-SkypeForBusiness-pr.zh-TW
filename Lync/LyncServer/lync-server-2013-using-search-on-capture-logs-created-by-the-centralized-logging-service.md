---
title: 在集中式記錄服務所建立的捕獲記錄上使用搜尋
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using search on capture logs created by the Centralized Logging Service
ms:assetid: 1b75b218-d84f-47a7-8a0a-b7e016b1cc79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687982(v=OCS.15)
ms:contentKeyID: 49733571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47b9d11713e874915fac0e4b67099ce3f7456546
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-search-on-capture-logs-created-by-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="07989-102">在 Lync Server 2013 中使用集中式記錄服務所建立的捕獲記錄來進行搜尋</span><span class="sxs-lookup"><span data-stu-id="07989-102">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07989-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="07989-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="07989-104">集中式記錄服務中的搜尋功能非常有用且功能強大，原因如下：</span><span class="sxs-lookup"><span data-stu-id="07989-104">The search features in the Centralized Logging Service are useful and powerful for the following reasons:</span></span>

  - <span data-ttu-id="07989-105">您的搜尋和結果會根據您定義的準則，在單一電腦、[池]、[網站] 或 [全域範圍] 上執行。</span><span class="sxs-lookup"><span data-stu-id="07989-105">Your searches and the results are run on a single computer, a pool, a site, or a global scope, based on the criteria you define.</span></span>

  - <span data-ttu-id="07989-106">您的搜尋可以是最初的廣義，然後縮小至更具針對性的準則，例如時間、元件或電腦。</span><span class="sxs-lookup"><span data-stu-id="07989-106">Your searches can be initially broad and then narrowed down to more targeted criteria such as time, component, or computer.</span></span> <span data-ttu-id="07989-107">您可以在相同的記錄中搜尋，且不需要在搜尋準則變更時再次執行記錄會議。</span><span class="sxs-lookup"><span data-stu-id="07989-107">You search against the same logs and don’t need to run a logging session again when the search criteria changes.</span></span>

  - <span data-ttu-id="07989-108">搜尋的結果是從作用域中的所有電腦和池收集、收集並匯總到單一輸出檔案，代表搜尋準則的所有結果（僅限於已執行的案例，以及由所捕獲的資料）。案例）。</span><span class="sxs-lookup"><span data-stu-id="07989-108">The results of your search are gathered from all computers and pools in the scope, collected and aggregated into a single output file that represents all results of the search criteria (limited to the scenarios that have been running and the data captured by the scenarios).</span></span> <span data-ttu-id="07989-109">您可以使用熟悉的工具（例如**Snooper**或**記事本**），從您的整個部署中讀取輸出檔案和追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="07989-109">You use familiar tools such as **Snooper** or **Notepad** to read the output file and the trace messages from across your deployment.</span></span>

<span data-ttu-id="07989-110">每一部電腦上的 CLSAgent 會根據案例或案例建立記錄（在任何指定時間，每個電腦都可以執行兩個案例）。</span><span class="sxs-lookup"><span data-stu-id="07989-110">The CLSAgent on each individual computer creates the logs based on the scenario or scenarios (two scenarios per computer can be running at any given time).</span></span> <span data-ttu-id="07989-111">記錄及其相關聯的索引與快取檔案是由 CLSAgent 管理。</span><span class="sxs-lookup"><span data-stu-id="07989-111">The logs and their associated index and cache files are managed by the CLSAgent.</span></span> <span data-ttu-id="07989-112">當您定義並執行搜尋時，[搜尋] 命令會指示 CLSAgent 應該要檢索哪些資訊。</span><span class="sxs-lookup"><span data-stu-id="07989-112">When you define and execute a search, the search command instructs the CLSAgent on what information should be retrieved.</span></span> <span data-ttu-id="07989-113">CLSAgent 會針對記錄檔、快取檔案和索引檔案執行查詢，並將搜尋結果傳回 CLSContoller。</span><span class="sxs-lookup"><span data-stu-id="07989-113">The CLSAgent executes the query against the log files, cache files, and index files and returns the results of the search to the CLSContoller.</span></span> <span data-ttu-id="07989-114">CLSController 會從搜尋範圍中的所有電腦和池接收搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="07989-114">The CLSController receives the search results from all computers and pools in the scope of the search.</span></span> <span data-ttu-id="07989-115">然後 CLSController 會將記錄匯總（合併），並將它們轉換成時間增量順序、最舊的專案，並持續到最新專案的最後一段時間。</span><span class="sxs-lookup"><span data-stu-id="07989-115">The CLSController then aggregates (combines) the logs and puts them into time delta order, oldest entry first, and proceeding in time to the most recent entry last.</span></span>

<span data-ttu-id="07989-116">每次搜尋之後，會執行**CsClsLogging** Cmdlet，並會清洗搜尋所使用的快取（不會與 CLSAgent 所維護的快取檔案混淆）。</span><span class="sxs-lookup"><span data-stu-id="07989-116">After each search, the **Sync-CsClsLogging** cmdlet is run and it flushes the cache used by searches (not to be confused with the cache files maintained by the CLSAgent).</span></span> <span data-ttu-id="07989-117">清除快取可協助確保 CLSController 中有乾淨的記錄和追蹤檔案擷取緩衝區，以便進行下一個搜尋操作。</span><span class="sxs-lookup"><span data-stu-id="07989-117">Flushing the cache helps to ensure that there is a clean log and trace file capture buffer at the CLSController for the next search operation.</span></span>

<span data-ttu-id="07989-118">若要充分發揮集中式記錄服務的優點，您必須充分瞭解如何將搜尋設定為僅傳回來自電腦的追蹤訊息，以及與您所研究之問題相關的池記錄。</span><span class="sxs-lookup"><span data-stu-id="07989-118">To get the most benefit from the Centralized Logging Service, you need a good understanding of how to configure search to return only trace messages from the computer and pool logs that are relevant to the issue that you are researching.</span></span> <span data-ttu-id="07989-119">存在</span><span class="sxs-lookup"><span data-stu-id="07989-119">issues</span></span>

<span data-ttu-id="07989-120">若要使用 Lync Server 管理命令介面執行集中式記錄服務搜尋功能，您必須是 CsAdministrator 或 CsServerAdministrator 角色式存取控制（RBAC）安全性群組的成員，或是包含下列內容的自訂 RBAC 角色：這兩個群組的其中一個。</span><span class="sxs-lookup"><span data-stu-id="07989-120">To run the Centralized Logging Service search functions by using the Lync Server Management Shell, you must be a member of either the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span> <span data-ttu-id="07989-121">若要傳回已指派這個 Cmdlet 的所有 RBAC 角色清單（包括您自行建立的任何自訂 RBAC 角色），請從 Lync Server 管理命令介面或 Windows PowerShell 提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="07989-121">To return a list of all the RBAC roles that this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Lync Server Management Shell or the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

<span data-ttu-id="07989-122">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-122">For example:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<span data-ttu-id="07989-123">本主題的剩餘部分將重點放在如何定義搜尋以優化疑難排解。</span><span class="sxs-lookup"><span data-stu-id="07989-123">The remainder of this topic focuses on how to define a search to optimize your troubleshooting.</span></span>

<div>

## <a name="to-run-a-basic-search-by-using-the-centralized-logging-service"></a><span data-ttu-id="07989-124">使用集中式記錄服務執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="07989-124">To run a basic search by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="07989-125">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="07989-125">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07989-126">請確定您在部署中的全域範圍內執行了 AlwaysOn 案例，然後在命令提示字元中輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="07989-126">Make sure that you have the AlwaysOn scenario running in your deployment at the global scope and then type the following at a command prompt:</span></span>
    
        Search-CsClsLogging -OutputFilePath <string value of path and file to write the output file>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="07989-127">根據預設，搜尋 CsClsLogging 會將搜尋結果傳送到主控台。</span><span class="sxs-lookup"><span data-stu-id="07989-127">By default, Search-CsClsLogging sends the results of the search to the console.</span></span> <span data-ttu-id="07989-128">如果您想要將搜尋結果儲存至檔案，請使用– OutputFilePath &lt;字串的完整檔路徑&gt;。</span><span class="sxs-lookup"><span data-stu-id="07989-128">If you want to save the search results to a file, use –OutputFilePath &lt;string fully qualified file path&gt;.</span></span> <span data-ttu-id="07989-129">若要定義– OutputFilePath 參數，請在以引號括住的字串格式中，提供路徑和檔案名作為參數的一部分（例如，C:\LogFiles\SearchOutput.txt).</span><span class="sxs-lookup"><span data-stu-id="07989-129">To define the –OutputFilePath parameter, supply a path and a filename as part of the parameter in a string format enclosed in quotation marks (for example; C:\LogFiles\SearchOutput.txt).</span></span> <span data-ttu-id="07989-130">在這個範例中，您必須確保目錄 C:\LogFiles 存在，且您擁有在資料夾中讀取和寫入（NTFS 許可權修改）檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="07989-130">In this example, you must ensure that the directory C:\LogFiles exists and that you have permissions to Read and Write (NTFS permission Modify) files in the folder.</span></span> <span data-ttu-id="07989-131">輸出會附加到，且不會覆寫。</span><span class="sxs-lookup"><span data-stu-id="07989-131">The output is appended to and is not overwritten.</span></span> <span data-ttu-id="07989-132">如果您需要個別的檔案，請為每個搜尋定義不同的檔案名。</span><span class="sxs-lookup"><span data-stu-id="07989-132">If you need separate files, define a distinct file name for each search.</span></span>

    
    </div>
    
    <span data-ttu-id="07989-133">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-133">For example:</span></span>
    
        Search-CsClsLogging -OutputFilePath "C:\LogFiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-basic-search-on-a-pool-or-computer-by-using-the-centralized-logging-service"></a><span data-ttu-id="07989-134">使用集中式記錄服務在池或電腦上執行基本搜尋</span><span class="sxs-lookup"><span data-stu-id="07989-134">To run a basic search on a pool or computer by using the Centralized Logging Service</span></span>

1.  <span data-ttu-id="07989-135">若要將搜尋限制在特定的池或電腦上，請使用–電腦參數及電腦完整名稱的電腦（以引號括住，並以英文逗號分隔），如下所示：</span><span class="sxs-lookup"><span data-stu-id="07989-135">To limit the search to a specific pool or computer, use the –Computers parameter with the computer defined by a computer fully qualified name, enclosed in quotation marks and separated by a comma as follows:</span></span>
    
        Search-CsClsLogging -Computers <string value of computer names> -OutputFilePath <string value of path and file to write the output file>
    
    <span data-ttu-id="07989-136">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-136">For example:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

2.  <span data-ttu-id="07989-137">若要搜尋多台電腦，請輸入多個以引號括住的電腦名稱稱，並以逗號分隔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="07989-137">To search more than one computer, type multiple computer names enclosed in quotation marks and separated by commas, such as the following:</span></span>
    
        Search-CsClsLogging -Computers "fe01.contoso.net", "fe02.contoso.net", "fe03.contoso.net" -OutputFilePath "C:\LogFiles\logfile.txt"

3.  <span data-ttu-id="07989-138">如果您需要搜尋整個池，而不是單台電腦，請將–電腦參數變更為 [Pool]，移除電腦名稱稱，然後以逗號分隔的以引號隔開的方式來取代它。</span><span class="sxs-lookup"><span data-stu-id="07989-138">If you need to search an entire pool instead of a single computer, change the –Computers parameter to –Pools, remove the computer name, and replace it with the pool or pools in quotation marks separated by commas.</span></span>
    
    <span data-ttu-id="07989-139">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-139">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="07989-140">使用搜尋命令時，pool 可以是部署中的任何一個池（例如前端池、邊緣池、持續聊天伺服器池），或是在您的部署中定義為一個池的其他人。</span><span class="sxs-lookup"><span data-stu-id="07989-140">When using the search commands, pools can be any pool in your deployment, such as Front End pools, Edge pools, Persistent Chat Server pools, or others that are defined as a pool in your deployment.</span></span>
    
    <span data-ttu-id="07989-141">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-141">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net", "pchatpool01.contoso.net", "intedgepool01.contoso.net" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-a-search-by-using-time-parameters"></a><span data-ttu-id="07989-142">使用時間參數執行搜尋</span><span class="sxs-lookup"><span data-stu-id="07989-142">To run a search by using time parameters</span></span>

1.  <span data-ttu-id="07989-143">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="07989-143">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07989-144">根據預設，搜尋的時間特定參數的開始時間是在您啟動搜尋之前的30分鐘。</span><span class="sxs-lookup"><span data-stu-id="07989-144">By default, the beginning time for a search's time-specific parameters is 30 minutes prior to the time you initiate the search.</span></span> <span data-ttu-id="07989-145">換句話說，如果您在 4:00:00 PM 啟動搜尋，搜尋將會搜尋您在 3:30:00 PM 定義的電腦和池的記錄，直到 4:00:00 PM 為止。</span><span class="sxs-lookup"><span data-stu-id="07989-145">In other words, if you initiate your search at 4:00:00 PM, the search will search the logs for the computers and pools that you define from 3:30:00 PM until 4:00:00 PM.</span></span> <span data-ttu-id="07989-146">如果您需要在目前時間前搜尋60分鐘或3小時，請使用– StartTime 參數並設定日期和時間字串，以指出您想要搜尋開始的時間。</span><span class="sxs-lookup"><span data-stu-id="07989-146">If you need to search 60 minutes or 3 hours prior to the current time, use the –StartTime parameter and set the date and time string to indicate the time you want the search to start.</span></span>
    
    <span data-ttu-id="07989-147">例如，您可以使用– StartTime 和– EndTime 定義時間與日期範圍，在您的池中，在11/20/2012 上定義一個從 8 AM 到 9 AM 的搜尋。</span><span class="sxs-lookup"><span data-stu-id="07989-147">For example, by using –StartTime and –EndTime to define a time and date range, you can define a search between 8 AM and 9 AM on 11/20/2012 on your pool.</span></span> <span data-ttu-id="07989-148">您可以設定輸出路徑，將結果寫入名為 c：\\logfile 的檔案，如下所示：</span><span class="sxs-lookup"><span data-stu-id="07989-148">You can set the output path to write the results to a file named c:\\logfile.txt as follows:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 08:00:00 AM" -EndTime "11/20/2012 09:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="07989-149">您指定的時間和日期字串可以是 "日期時間" 或 "時間日期"。</span><span class="sxs-lookup"><span data-stu-id="07989-149">The time and date string that you specify can be "date time" or "time date.</span></span> <span data-ttu-id="07989-150">「命令會分析字串，並針對日期和時間使用適當的值。</span><span class="sxs-lookup"><span data-stu-id="07989-150">" The command will parse the string and use the appropriate values for date and time.</span></span>

    
    </div>

3.  <span data-ttu-id="07989-151">如果您想要從11/20/2012 開始的11:00:00 開始檢索記錄，您可以定義– StartTime。</span><span class="sxs-lookup"><span data-stu-id="07989-151">If you want to retrieve logs beginning at 11:00:00 AM on 11/20/2012, you define the –StartTime.</span></span> <span data-ttu-id="07989-152">除非您定義特定– EndTime，否則搜尋的預設時間範圍是30分鐘。</span><span class="sxs-lookup"><span data-stu-id="07989-152">The default time range for the search is 30 minutes unless you define a specific –EndTime.</span></span> <span data-ttu-id="07989-153">產生的搜尋會從已定義的電腦或池中傳回來自 11:00:00 AM 到 11:30:00 AM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="07989-153">The resulting search will return logs from the defined computer or pools from 11:00:00 AM to 11:30:00 AM.</span></span>
    
    <span data-ttu-id="07989-154">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-154">For example:</span></span>
    
        Search-CsClsLogging -Pools "pool01.contoso.net" -StartTime "11/20/2012 11:00:00 AM" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="07989-155">若要在特定的一段時間內搜尋記錄，請定義-StartTime 和-EndTime。</span><span class="sxs-lookup"><span data-stu-id="07989-155">To conduct a search of logs within a specific period of time, define a –StartTime and an –EndTime.</span></span> <span data-ttu-id="07989-156">在電腦 edge01.contoso.net 上，您需要從 1 PM 到 2:45 PM 的記錄。</span><span class="sxs-lookup"><span data-stu-id="07989-156">You need logs from 1 PM to 2:45 PM on the computer edge01.contoso.net.</span></span>
    
    <span data-ttu-id="07989-157">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-157">For example:</span></span>
    
        Search-CsClsLogging -Computers "edge01.contoso.net" -StartTime "11/20/2012 1:00:00 PM" -EndTime "11/20/2012 2:45:00 PM" -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

<div>

## <a name="to-run-an-advanced-search-by-using-other-criteria-and-matching-options"></a><span data-ttu-id="07989-158">使用其他準則和相符選項執行高級搜尋</span><span class="sxs-lookup"><span data-stu-id="07989-158">To run an advanced search by using other criteria and matching options</span></span>

1.  <span data-ttu-id="07989-159">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="07989-159">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07989-160">若要執行命令來收集特定元件的蹤跡，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="07989-160">To run a command to collect traces for specific components, type the following:</span></span>
    
        Search-CsClsLogging -Components <components to search on> -OutputFilePath <fully qualified path to output logs>
    
    <span data-ttu-id="07989-161">例如：</span><span class="sxs-lookup"><span data-stu-id="07989-161">For example:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"
    
    <span data-ttu-id="07989-162">產生的搜尋會傳回在過去30分鐘內，您部署中所有電腦和池中都有 SIPStack、S4 和 UserServices 追蹤元件的所有記錄專案。</span><span class="sxs-lookup"><span data-stu-id="07989-162">The resulting search returns all log entries that have trace components for SIPStack, S4, and UserServices on all computers and pools in your deployment for the past 30 minutes.</span></span>

3.  <span data-ttu-id="07989-163">若要將使用相同元件的搜尋限制為僅限您的前端池（名為 pool01.contoso.net），請輸入：</span><span class="sxs-lookup"><span data-stu-id="07989-163">To limit the search with the same components to just your Front End pool named pool01.contoso.net, type:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -OutputFilePath "C:\Logfiles\logfile.txt"

4.  <span data-ttu-id="07989-164">具有多個參數之命令的預設搜尋邏輯是使用邏輯或與每個已定義的參數。</span><span class="sxs-lookup"><span data-stu-id="07989-164">The default search logic for commands with multiple parameters is to use the logical OR with each of the defined parameters.</span></span> <span data-ttu-id="07989-165">您可以透過指定 **– MatchAll**參數來變更此行為。</span><span class="sxs-lookup"><span data-stu-id="07989-165">You can change this behavior by specifying the **–MatchAll** parameter.</span></span> <span data-ttu-id="07989-166">若要這樣做，請輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="07989-166">To do this, type the following:</span></span>
    
        Search-CsClsLogging -CallId "d0af828e49fa4dcb99f5f80223a634bc" -Components "SIPStack","S4","UserServices" -MatchAll -OutputFilePath "C:\Logfiles\logfile.txt"

5.  <span data-ttu-id="07989-167">如果您的案例已設定為持續執行（例如 AlwaysOn），或您已定義長時間執行的案例記錄，可能會將本機電腦放到檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="07989-167">If your scenarios are set to run constantly, such as AlwaysOn, or you have defined a long-running scenario logs may roll off of the local machine onto the file share.</span></span> <span data-ttu-id="07989-168">您可以使用 CacheFileNetworkFolder 參數來定義檔案共用，方法是使用 New-CsClsConfiguration 來建立新的設定，或使用 Set-CsClsConfiguration 修改現有的配置。</span><span class="sxs-lookup"><span data-stu-id="07989-168">You define the file share by using the CacheFileNetworkFolder parameter by using New-CsClsConfiguration to create a new configuration or modifying an existing configuration with Set-CsClsConfiguration.</span></span> <span data-ttu-id="07989-169">如果您不希望搜尋將檔案共用包含在要搜尋的記錄集合中，請使用 SkipNetworkLogs 參數，如下所示：</span><span class="sxs-lookup"><span data-stu-id="07989-169">If you do not want the search to include the file share in the collection of logs to search, use the SkipNetworkLogs parameter as follows:</span></span>
    
        Search-CsClsLogging -Components "SIPStack","S4","UserServices" -StartTime "11/1/2012 00:00:01 AM" -EndTime "11/20/2012 2:45:00 PM" -SkipNetworkLogs -OutputFilePath "C:\Logfiles\logfile.txt"

</div>

</div>

<span> </span>

</div>

</div>

</div>

