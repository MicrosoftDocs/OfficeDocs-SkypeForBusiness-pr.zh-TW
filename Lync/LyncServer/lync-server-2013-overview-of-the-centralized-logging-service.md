---
title: Lync Server 2013：集中式記錄服務概述
description: Lync Server 2013：集中式記錄服務的簡介。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a357063ff80611789981f5e98a69899ea5cd27a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560909"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="d49e1-103">Lync Server 2013 中的集中式記錄服務概述</span><span class="sxs-lookup"><span data-stu-id="d49e1-103">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49e1-104">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="d49e1-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="d49e1-105">集中式記錄服務的設計目的是要提供一種具有廣泛或窄範圍之資料的可控集合方式。</span><span class="sxs-lookup"><span data-stu-id="d49e1-105">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="d49e1-106">您可以同時從部署的所有伺服器收集資料、定義要追蹤的特定元素、設定追蹤旗標，以及從單一電腦或所有伺服器的所有資料匯總中傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="d49e1-106">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="d49e1-107">集中式記錄服務會在您部署中的所有伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="d49e1-107">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="d49e1-108">集中式記錄服務的架構是由下列代理程式和服務所組成：</span><span class="sxs-lookup"><span data-stu-id="d49e1-108">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="d49e1-109">*集中式記錄服務代理程式*    ClsAgent.exe 是與控制器通訊的服務可執行檔，並接收由系統管理員發出的控制器命令。</span><span class="sxs-lookup"><span data-stu-id="d49e1-109">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="d49e1-110">代理程式會在每一部 Lync Server 電腦上以服務的身分執行。</span><span class="sxs-lookup"><span data-stu-id="d49e1-110">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="d49e1-111">當代理程式收到命令時，它會執行命令、將郵件傳送至已定義的追蹤元件，然後將追蹤記錄檔寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="d49e1-111">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="d49e1-112">它也會讀取其電腦的追蹤記錄檔，並在要求時將追蹤資料傳送回控制器。</span><span class="sxs-lookup"><span data-stu-id="d49e1-112">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="d49e1-113">ClsAgent 會偵聽下列埠上的命令： **tcp 50001**、 **Tcp 50002**及 **tcp 50003**。</span><span class="sxs-lookup"><span data-stu-id="d49e1-113">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="d49e1-114">*集中式記錄服務控制器*    ClsControllerLib.dll 是 Lync Server 管理命令介面和 ClsController.exe 的命令執行引擎。</span><span class="sxs-lookup"><span data-stu-id="d49e1-114">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="d49e1-115">CLSControllerLib.dll 會將開始、停止、清除和搜尋命令傳送給 ClsAgent。</span><span class="sxs-lookup"><span data-stu-id="d49e1-115">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="d49e1-116">當傳送搜尋命令時，產生的記錄會傳回 ClsControllerLib.dll 並匯總。</span><span class="sxs-lookup"><span data-stu-id="d49e1-116">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="d49e1-117">控制器負責將命令傳送給代理程式、接收這些命令的狀態，以及在搜尋範圍中的任何電腦上的所有 agent 傳回時，管理搜尋記錄檔資料，並將記錄資料聚合到有意義的已排序輸出集。</span><span class="sxs-lookup"><span data-stu-id="d49e1-117">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="d49e1-118">下列主題中的資訊重點是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="d49e1-118">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="d49e1-119">ClsController.exe 會限制在 Lync Server 管理命令介面中提供的功能和功能的子集。</span><span class="sxs-lookup"><span data-stu-id="d49e1-119">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="d49e1-120">您可以在命令列上輸入「 `ClsController` \\ \\ \\ Microsoft Lync Server 2013 ClsAgent 中的預設目錄 C： Program files 通用檔案，以取得 ClsController.exe 的協助 \\ 。</span><span class="sxs-lookup"><span data-stu-id="d49e1-120">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="d49e1-121">**ClsController ClsAgent 的通訊**</span><span class="sxs-lookup"><span data-stu-id="d49e1-121">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="d49e1-122">![CLSController 和 CLSAgent 之間的關聯性。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之間的關聯性。")</span><span class="sxs-lookup"><span data-stu-id="d49e1-122">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="d49e1-123">使用 Windows Server 命令列介面或 Lync Server 管理命令介面發出命令。</span><span class="sxs-lookup"><span data-stu-id="d49e1-123">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="d49e1-124">命令會在您登入的電腦上執行，並傳送至本機的 ClsAgent，或部署中的其他電腦及集區。</span><span class="sxs-lookup"><span data-stu-id="d49e1-124">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="d49e1-125">ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔。</span><span class="sxs-lookup"><span data-stu-id="d49e1-125">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="d49e1-126">ClsAgent 會將其分配給它們，使其平均分散于選項 CacheFileLocalFolders 所定義的各個磁片區上，每個磁片區絕對使用超過 80% (也就是說，本機快取位置和百分比可使用 **Set-CsClsConfiguration** Cmdlet) 來設定。</span><span class="sxs-lookup"><span data-stu-id="d49e1-126">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="d49e1-127">ClsAgent 也負責帳齡舊的快取事件追蹤記錄檔 ( .etl) 本機電腦。</span><span class="sxs-lookup"><span data-stu-id="d49e1-127">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="d49e1-128">在兩周後 (也就是說，可使用 **Set-CsClsConfiguration** Cmdlet 來設定時間範圍) 這些檔案會複製到檔案共用，並從本機電腦刪除。</span><span class="sxs-lookup"><span data-stu-id="d49e1-128">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="d49e1-129">如需詳細資訊，請參閱 [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="d49e1-129">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="d49e1-130">當接收搜尋要求時，搜尋準則是用來選取一組快取的 .etl 檔案，以根據代理程式所維護之索引中的值來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="d49e1-130">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d49e1-131">從本機電腦移至檔案共用的檔案，可依 ClsAgent 進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="d49e1-131">Files that are moved to the file share from the local computer can be searched by ClsAgent.</span></span> <span data-ttu-id="d49e1-132">一旦 ClsAgent 將檔案移至檔案共用，檔案的老化和移除不會由 ClsAgent 維護。</span><span class="sxs-lookup"><span data-stu-id="d49e1-132">Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent.</span></span> <span data-ttu-id="d49e1-133">您應定義管理工作，以監視檔案共用中的檔案大小，並刪除或封存檔案。</span><span class="sxs-lookup"><span data-stu-id="d49e1-133">You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="d49e1-134">您可以使用各種工具讀取及分析產生的記錄檔，包括 **Snooper.exe** 和任何可讀取文字檔的工具，例如 **Notepad.exe**。</span><span class="sxs-lookup"><span data-stu-id="d49e1-134">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="d49e1-135">Snooper.exe 是 Lync Server 2013 調試工具的一部分，可從下載網頁 [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。</span><span class="sxs-lookup"><span data-stu-id="d49e1-135">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="d49e1-136">就像 OCSLogger 一樣，集中式記錄服務也會有多個元件可供追蹤，並提供選擇旗標（如 TF COMPONENT 和 TF options）的選項 \_ \_ 。</span><span class="sxs-lookup"><span data-stu-id="d49e1-136">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="d49e1-137">集中式記錄服務也會保留 OCSLogger 的記錄等級選項。</span><span class="sxs-lookup"><span data-stu-id="d49e1-137">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="d49e1-138">在命令列 ClsController 上使用 Lync Server 管理命令介面最重要的優點是，您可以使用選取的提供者來設定及定義新的案例，其是以問題空間、自訂旗標及記錄層級為目標。</span><span class="sxs-lookup"><span data-stu-id="d49e1-138">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="d49e1-139">可用於 ClsController 的案例只限于為可執行檔定義的案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-139">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="d49e1-140">在舊版中，提供 OCSLogger.exe，讓系統管理員和支援人員在部署中從電腦收集追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="d49e1-140">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment.</span></span> <span data-ttu-id="d49e1-141">OCSLogger，針對其所有優點，都有缺點。</span><span class="sxs-lookup"><span data-stu-id="d49e1-141">OCSLogger, for all of its strengths, had a shortcoming.</span></span> <span data-ttu-id="d49e1-142">在指定的時間，您只能在一部電腦上收集記錄檔。</span><span class="sxs-lookup"><span data-stu-id="d49e1-142">You could only collect logs on one computer at a given time.</span></span> <span data-ttu-id="d49e1-143">您可以使用不同的 OCSLogger 副本登入多部電腦，但是會以多個記錄檔結束，而且不會有簡單的方法來匯總結果。</span><span class="sxs-lookup"><span data-stu-id="d49e1-143">You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="d49e1-144">當使用者要求記錄搜尋時，ClsController 會根據) 所選案例，決定要將要求傳送給 (的機器。</span><span class="sxs-lookup"><span data-stu-id="d49e1-144">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected).</span></span> <span data-ttu-id="d49e1-145">此外，它也會判斷是否需要將搜尋傳送至儲存的 .etl 檔案所在的檔案共用。</span><span class="sxs-lookup"><span data-stu-id="d49e1-145">It also determines whether the search needs to be sent to the file share where the saved .etl files are located.</span></span> <span data-ttu-id="d49e1-146">當搜尋結果傳回 ClsController 時，控制器會將結果合併為使用者所呈現的單一時序結果集。</span><span class="sxs-lookup"><span data-stu-id="d49e1-146">When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user.</span></span> <span data-ttu-id="d49e1-147">使用者可以將搜尋結果儲存至本機機器，以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="d49e1-147">Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="d49e1-148">當您開機記錄會話時，您會指定要嘗試解決之問題的相關案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-148">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve.</span></span> <span data-ttu-id="d49e1-149">您可以隨時執行兩個案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-149">You can have two scenarios running at any time.</span></span> <span data-ttu-id="d49e1-150">這兩種案例之一應該是 AlwaysOn 案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-150">One of these two scenarios should be the AlwaysOn scenario.</span></span> <span data-ttu-id="d49e1-151">顧名思義，它應永遠在您的部署中執行，並收集所有電腦、集區和元件的資訊。</span><span class="sxs-lookup"><span data-stu-id="d49e1-151">As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d49e1-152">根據預設，AlwaysOn 案例不會在您的部署中執行。</span><span class="sxs-lookup"><span data-stu-id="d49e1-152">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="d49e1-153">您必須明確地啟動案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-153">You must explicitly start the scenario.</span></span> <span data-ttu-id="d49e1-154">一旦開始，它會繼續執行，直到明確停止為止，而且執行狀態會持續重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="d49e1-154">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="d49e1-155">如需啟動和停止案例的詳細資訊，請參閱 <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用 Start for a 集中式記錄服務來捕獲 Lync server 2013 中的記錄</A> ，並 <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">在 lync Server 2013 中使用「集中式記錄」服務的 Stop</A>。</span><span class="sxs-lookup"><span data-stu-id="d49e1-155">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d49e1-156">發生問題時，請啟動與所報告問題相關的第二個案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-156">When a problem occurs, start a second scenario that relates to the problem reported.</span></span> <span data-ttu-id="d49e1-157">再現問題，並停止記錄第二個案例。</span><span class="sxs-lookup"><span data-stu-id="d49e1-157">Reproduce the problem, and stop the logging for the second scenario.</span></span> <span data-ttu-id="d49e1-158">相對於所報告的問題，開始進行記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="d49e1-158">Begin your log searches relative to the problem reported.</span></span> <span data-ttu-id="d49e1-159">記錄的匯總集合會產生記錄檔，該檔案包含您的網站中所有電腦的追蹤訊息，或部署的全域範圍中的追蹤訊息。</span><span class="sxs-lookup"><span data-stu-id="d49e1-159">The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment.</span></span> <span data-ttu-id="d49e1-160">如果搜尋傳回的資料多於您可以 feasibly 分析 (通常稱為雜訊對雜訊比例，在此情況下，噪音太高) ，您可以使用較窄的參數執行另一次搜尋。</span><span class="sxs-lookup"><span data-stu-id="d49e1-160">If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters.</span></span> <span data-ttu-id="d49e1-161">此時，您可以開始注意所顯示的模式，並可協助您取得問題的更清晰的重點。</span><span class="sxs-lookup"><span data-stu-id="d49e1-161">At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem.</span></span> <span data-ttu-id="d49e1-162">最後，在您執行一些精簡搜尋之後，您可以尋找與問題相關的資料，並找出根本原因。</span><span class="sxs-lookup"><span data-stu-id="d49e1-162">Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="d49e1-163">當您在 Lync Server 中呈現問題案例時，請從提問「我已經知道這個問題的資訊」。</span><span class="sxs-lookup"><span data-stu-id="d49e1-163">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="d49e1-164">如果您量化問題的界限，您可以在 Lync Server 中消除大部分的運作實體部分。</span><span class="sxs-lookup"><span data-stu-id="d49e1-164">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="d49e1-165">請考慮一個範例案例，您知道使用者在尋找連絡人時並未取得目前的結果。</span><span class="sxs-lookup"><span data-stu-id="d49e1-165">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="d49e1-166">沒有任何一點要尋找媒體元件、Enterprise Voice、會議及許多其他元件的問題。</span><span class="sxs-lookup"><span data-stu-id="d49e1-166">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="d49e1-167">您可能不會知道問題實際上是在用戶端上，還是伺服器端問題？</span><span class="sxs-lookup"><span data-stu-id="d49e1-167">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="d49e1-168">使用者收集器會從 Active Directory 收集連絡人，並透過通訊錄服務器 (ABServer) 來傳遞給用戶端。</span><span class="sxs-lookup"><span data-stu-id="d49e1-168">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="d49e1-169">ABServer 會從 RTC (資料庫中取得更新，以供使用者複寫器寫入其) 並將其收集到通訊錄檔案中（預設為 1:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="d49e1-169">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="d49e1-170">Lync Server 用戶端會以隨機排程的，取回新的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="d49e1-170">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="d49e1-171">因為您知道程式的運作方式，所以您可以縮小搜尋，以找出可能導致問題的潛在原因，以供使用者複寫器從 Active Directory 收集的資料，ABServer 不會檢索及建立通訊錄檔案，或用戶端不會下載通訊錄檔案。</span><span class="sxs-lookup"><span data-stu-id="d49e1-171">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

