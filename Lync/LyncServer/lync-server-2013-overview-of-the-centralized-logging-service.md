---
title: Lync Server 2013：集中式記錄服務的簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="97531-102">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="97531-102">Overview of the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97531-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="97531-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="97531-104">集中式記錄服務的設計目的是為了提供受控制的資料收集方式，以及廣泛或窄的範圍。</span><span class="sxs-lookup"><span data-stu-id="97531-104">The Centralized Logging Service is designed to provide a means for controlled collection of data—with a broad or narrow scope.</span></span> <span data-ttu-id="97531-105">您可以同時從部署中的所有伺服器收集資料、定義要追蹤的特定元素、設定追蹤標記，以及從單一電腦或從所有伺服器的所有資料匯總中傳回搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="97531-105">You can collect data from all servers in the deployment concurrently, define specific elements to trace, set trace flags and return search results from a single computer or an aggregation of all data from all servers.</span></span> <span data-ttu-id="97531-106">集中式記錄服務會在您部署中的所有伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="97531-106">The Centralized Logging Service runs on all servers in your deployment.</span></span> <span data-ttu-id="97531-107">集中式記錄服務的架構由下列代理程式和服務所組成：</span><span class="sxs-lookup"><span data-stu-id="97531-107">The architecture of the Centralized Logging Service is comprised of the following agents and services:</span></span>

  - <span data-ttu-id="97531-108">*集中式記錄服務代理程式*   ClsAgent 是與控制器進行通訊的服務可執行檔，並會接收由管理員發出的命令。</span><span class="sxs-lookup"><span data-stu-id="97531-108">*Centralized Logging Service Agent*   ClsAgent.exe is the service executable that communicates with the controller and receives the commands that the controller is issued by the administrator.</span></span> <span data-ttu-id="97531-109">此代理程式是在每個 Lync Server 電腦上以服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="97531-109">The agent is run as a service on each Lync Server computer.</span></span> <span data-ttu-id="97531-110">當代理程式收到命令時，會執行命令、將訊息傳送給已定義的追蹤元件，然後將追蹤記錄寫入磁片。</span><span class="sxs-lookup"><span data-stu-id="97531-110">When the agent receives a command, it executes the command, sends messages to the defined components for tracing, and writes the trace logs to disk.</span></span> <span data-ttu-id="97531-111">它也會讀取其電腦的追蹤記錄，並在要求時將追蹤資料傳送回控制器。</span><span class="sxs-lookup"><span data-stu-id="97531-111">It also reads the trace logs for its computer and sends the trace data back to the controller when requested.</span></span> <span data-ttu-id="97531-112">ClsAgent 會偵聽下列埠上的命令： **tcp 50001**、 **Tcp 50002**和**TCP 50003**。</span><span class="sxs-lookup"><span data-stu-id="97531-112">The ClsAgent listens for commands on the following ports: **TCP 50001**, **TCP 50002**, and **TCP 50003**.</span></span>

  - <span data-ttu-id="97531-113">*集中式記錄服務控制器*   ClsControllerLib 是 Lync Server 管理命令介面和 ClsController 的命令執行引擎。</span><span class="sxs-lookup"><span data-stu-id="97531-113">*Centralized Logging Service Controller*   ClsControllerLib.dll is the command execution engine for the Lync Server Management Shell and for ClsController.exe.</span></span> <span data-ttu-id="97531-114">CLSControllerLib 會將開始、停止、清除及搜尋命令傳送到 ClsAgent。</span><span class="sxs-lookup"><span data-stu-id="97531-114">CLSControllerLib.dll sends Start, Stop, Flush, and Search commands to the ClsAgent.</span></span> <span data-ttu-id="97531-115">傳送搜尋命令時，會將產生的記錄傳回 ClsControllerLib 及匯總。</span><span class="sxs-lookup"><span data-stu-id="97531-115">When search commands are sent, the resulting logs are returned to the ClsControllerLib.dll and aggregated.</span></span> <span data-ttu-id="97531-116">控制器負責傳送命令至 agent、接收這些命令的狀態，以及管理從搜尋範圍內任何電腦上的所有代理程式傳回的搜尋記錄檔資料，並將記錄資料聚集成有意義且已排序輸出設定。</span><span class="sxs-lookup"><span data-stu-id="97531-116">The controller is responsible for sending commands to the agent, receiving the status of those commands and managing the search log file data as it is returned from all agents on any computer in the search scope, and aggregating the log data into a meaningful and ordered output set.</span></span> <span data-ttu-id="97531-117">下列主題中的資訊主要是使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="97531-117">The information in the following topics is focused on using the Lync Server Management Shell.</span></span> <span data-ttu-id="97531-118">ClsController 受限於 Lync Server 管理命令介面中提供的功能和功能子集。</span><span class="sxs-lookup"><span data-stu-id="97531-118">ClsController.exe is limited to a subset of the features and functions that are available in the Lync Server Management Shell.</span></span> <span data-ttu-id="97531-119">您可以在命令列中輸入 ClsController 的說明，方法是`ClsController`在 [預設目錄 C：\\Program files\\] 中\\輸入「Microsoft Lync\\Server 2013 ClsAgent」。</span><span class="sxs-lookup"><span data-stu-id="97531-119">Help for ClsController.exe is available at the command line by typing `ClsController` in the default directory C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\ClsAgent.</span></span>

<span data-ttu-id="97531-120">**ClsController 通訊至 ClsAgent**</span><span class="sxs-lookup"><span data-stu-id="97531-120">**ClsController communications to ClsAgent**</span></span>

<span data-ttu-id="97531-121">![CLSController 和 CLSAgent 之間的關聯。](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "CLSController 和 CLSAgent 之間的關聯。")</span><span class="sxs-lookup"><span data-stu-id="97531-121">![Relationship between CLSController and CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relationship between CLSController and CLSAgent.")</span></span>

<span data-ttu-id="97531-122">您使用 Windows Server 命令列介面或使用 Lync Server Management Shell 發出命令。</span><span class="sxs-lookup"><span data-stu-id="97531-122">You issue commands using the Windows Server command-line interface or using the Lync Server Management Shell.</span></span> <span data-ttu-id="97531-123">這些命令會在您登入的電腦上執行，並傳送到您部署中的 ClsAgent 本機或其他電腦和池。</span><span class="sxs-lookup"><span data-stu-id="97531-123">The commands are executed on the computer you are logged in to and sent to the ClsAgent locally or to the other computers and pools in your deployment.</span></span>

<span data-ttu-id="97531-124">ClsAgent 會維護全部的索引檔案。在本機電腦上的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="97531-124">ClsAgent maintains an index file of all .CACHE files that it has on the local machine.</span></span> <span data-ttu-id="97531-125">ClsAgent 會將它們分攤80，讓它們均勻分佈于選項 CacheFileLocalFolders 所定義的各個卷上（也就是，本機快取位置和百分比可使用**Set-CsClsConfiguration** Cmdlet 來設定）。</span><span class="sxs-lookup"><span data-stu-id="97531-125">ClsAgent allocates them so that they are evenly distributed across volumes defined by the option CacheFileLocalFolders, never consuming more than 80% of each volume (that is, the local cache location and the percentage is configurable using the **Set-CsClsConfiguration** cmdlet).</span></span> <span data-ttu-id="97531-126">ClsAgent 也負責從本機電腦中老化舊的快取事件追蹤記錄（.etl）檔案。</span><span class="sxs-lookup"><span data-stu-id="97531-126">ClsAgent is also responsible for aging old cached event trace log (.etl) files off the local machine.</span></span> <span data-ttu-id="97531-127">兩周之後（也就是使用**CsClsConfiguration Cmdlet 設定**的時間範圍），這些檔案會複製到檔案共用，並從本機電腦刪除。</span><span class="sxs-lookup"><span data-stu-id="97531-127">After two weeks (that is, the timeframe is configurable using the **Set-CsClsConfiguration** cmdlet) these files are copied to a file share and deleted from the local computer.</span></span> <span data-ttu-id="97531-128">如需詳細資訊，請參閱[設定 CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="97531-128">For details, see [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration).</span></span> <span data-ttu-id="97531-129">當您收到搜尋要求時，會使用搜尋準則來選取一組快取的 .etl 檔案，以根據代理所維護之索引中的值來執行搜尋。</span><span class="sxs-lookup"><span data-stu-id="97531-129">When a search request is received, the search criteria is used to select the set of cached .etl files to perform the search based on the values in the index maintained by the agent.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97531-130">從本機電腦移至檔案共用的檔案，可以透過 ClsAgent 進行搜尋。</span><span class="sxs-lookup"><span data-stu-id="97531-130">Files that are moved to the file share from the local computer can be searched by ClsAgent.</span></span> <span data-ttu-id="97531-131">ClsAgent 將檔案移到檔案共用後，ClsAgent 不會維護檔案的老化與移除。</span><span class="sxs-lookup"><span data-stu-id="97531-131">Once ClsAgent moves the files to the file share, the aging and removal of files is not maintained by ClsAgent.</span></span> <span data-ttu-id="97531-132">您應該定義系統管理工作來監視檔案共用中的檔案大小，然後刪除檔案或封存檔案。</span><span class="sxs-lookup"><span data-stu-id="97531-132">You should define an administrative task to monitor the size of the files in the file share and delete them or archive them.</span></span>



</div>

<span data-ttu-id="97531-133">所產生的記錄檔案可以使用各種不同的工具來讀取和分析，包括**Snooper**和任何可讀取文字檔（例如**notepad.exe**）的工具。</span><span class="sxs-lookup"><span data-stu-id="97531-133">The resulting log files can be read and analyzed using a variety of tools, including **Snooper.exe** and any tool that can read a text file, such as **Notepad.exe**.</span></span> <span data-ttu-id="97531-134">Snooper 是 Lync Server 2013 調試工具的一部分，可從[http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)下載網頁。</span><span class="sxs-lookup"><span data-stu-id="97531-134">Snooper.exe is part of the Lync Server 2013 Debug Tools and is available as a Web download from [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257).</span></span>

<span data-ttu-id="97531-135">就像 OCSLogger，集中式記錄服務會有數個要追蹤的元件，並提供選取旗標（例如\_tf 元件和\_tf）的選項。</span><span class="sxs-lookup"><span data-stu-id="97531-135">Like OCSLogger, the Centralized Logging Service has several components to trace against, and provides options to select flags, such as TF\_COMPONENT and TF\_DIAG.</span></span> <span data-ttu-id="97531-136">集中式記錄服務也會保留 OCSLogger 的記錄層級選項。</span><span class="sxs-lookup"><span data-stu-id="97531-136">Centralized Logging Service also retains the logging level options of OCSLogger.</span></span>

<span data-ttu-id="97531-137">在命令列 ClsController 上使用 Lync Server 管理命令介面最重要的優點是，您可以使用選取的提供者來設定及定義新案例，這些提供者是針對問題空間、自訂標記和記錄層級。</span><span class="sxs-lookup"><span data-stu-id="97531-137">The most important advantage to using the Lync Server Management Shell over the command-line ClsController is that you can configure and define new scenarios using selected providers that target the problem space, custom flags, and logging levels.</span></span> <span data-ttu-id="97531-138">提供給 ClsController 的案例僅限於針對可執行檔所定義的情況。</span><span class="sxs-lookup"><span data-stu-id="97531-138">The scenarios available to ClsController are limited to those that are defined for the executable.</span></span>

<span data-ttu-id="97531-139">在舊版中，提供了 OCSLogger，讓系統管理員和支援人員從部署中的電腦收集追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="97531-139">In previous versions, OCSLogger.exe was provided to enable administrators and support personnel to collect trace files from computers in the deployment.</span></span> <span data-ttu-id="97531-140">OCSLogger （針對其所有優點）有一個不足之處。</span><span class="sxs-lookup"><span data-stu-id="97531-140">OCSLogger, for all of its strengths, had a shortcoming.</span></span> <span data-ttu-id="97531-141">您在指定時間只能在一部電腦上收集記錄。</span><span class="sxs-lookup"><span data-stu-id="97531-141">You could only collect logs on one computer at a given time.</span></span> <span data-ttu-id="97531-142">您可以使用個別的 OCSLogger 複本登入多部電腦，但最終會有多個記錄，而且沒有簡單的方法來匯總結果。</span><span class="sxs-lookup"><span data-stu-id="97531-142">You could log on to multiple computers by using separate copies of OCSLogger, but you ended up with multiple logs and no easy way to aggregate the results.</span></span>

<span data-ttu-id="97531-143">當使用者要求記錄搜尋時，ClsController 會決定要傳送要求的電腦（亦即根據選取的案例）。</span><span class="sxs-lookup"><span data-stu-id="97531-143">When a user requests a log search, the ClsController determines which machines to send the request to (that is, based on the scenarios selected).</span></span> <span data-ttu-id="97531-144">它也會判斷是否需要將搜尋傳送到已儲存的 .etl 檔案所在的檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="97531-144">It also determines whether the search needs to be sent to the file share where the saved .etl files are located.</span></span> <span data-ttu-id="97531-145">當搜尋結果傳回 ClsController 時，控制器會將結果合併成單一時間排序的結果集，並顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="97531-145">When the search results are returned to the ClsController, the controller merges the results into a single time-ordered result set that is presented to the user.</span></span> <span data-ttu-id="97531-146">使用者可以將搜尋結果儲存至本機電腦，以進行進一步分析。</span><span class="sxs-lookup"><span data-stu-id="97531-146">Users can save the search results to their local machine for further analysis.</span></span>

<span data-ttu-id="97531-147">當您開機記錄會話時，您會指定與您嘗試解決之問題相關的案例。</span><span class="sxs-lookup"><span data-stu-id="97531-147">When you start a logging session, you specify scenarios that are relative to the problem that you are trying to resolve.</span></span> <span data-ttu-id="97531-148">您可以隨時執行兩種情況。</span><span class="sxs-lookup"><span data-stu-id="97531-148">You can have two scenarios running at any time.</span></span> <span data-ttu-id="97531-149">這兩種案例的其中一個就是 AlwaysOn 案例。</span><span class="sxs-lookup"><span data-stu-id="97531-149">One of these two scenarios should be the AlwaysOn scenario.</span></span> <span data-ttu-id="97531-150">顧名思義，它應該一直在您的部署中執行，收集所有電腦、池及元件的資訊。</span><span class="sxs-lookup"><span data-stu-id="97531-150">As the name implies, it should always be running in your deployment, collecting information on all computers, pools, and components.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97531-151">根據預設，AlwaysOn 情況未在您的部署中執行。</span><span class="sxs-lookup"><span data-stu-id="97531-151">By default, the AlwaysOn scenario is not running in your deployment.</span></span> <span data-ttu-id="97531-152">您必須明確啟動案例。</span><span class="sxs-lookup"><span data-stu-id="97531-152">You must explicitly start the scenario.</span></span> <span data-ttu-id="97531-153">一旦開始，就會繼續執行，直到明確停止為止，且執行狀態將會在電腦重新開機後持續。</span><span class="sxs-lookup"><span data-stu-id="97531-153">Once started, it will continue to run until explicitly stopped, and the running state will persist through reboots of the computers.</span></span> <span data-ttu-id="97531-154">如需開始與停止案例的詳細資料，請參閱<A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">使用集中式記錄服務在 Lync server 2013 中捕獲記錄</A>，並在<A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">lync Server 2013 中使用 [停止] 作為集中式記錄服務</A>。</span><span class="sxs-lookup"><span data-stu-id="97531-154">For details on starting and stopping scenarios, see <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</A> and <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">Using Stop for the Centralized Logging Service in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="97531-155">發生問題時，請先開始與所報告問題相關的第二個案例。</span><span class="sxs-lookup"><span data-stu-id="97531-155">When a problem occurs, start a second scenario that relates to the problem reported.</span></span> <span data-ttu-id="97531-156">再現問題，並停止記錄第二個案例。</span><span class="sxs-lookup"><span data-stu-id="97531-156">Reproduce the problem, and stop the logging for the second scenario.</span></span> <span data-ttu-id="97531-157">相對於報告的問題開始進行記錄搜尋。</span><span class="sxs-lookup"><span data-stu-id="97531-157">Begin your log searches relative to the problem reported.</span></span> <span data-ttu-id="97531-158">記錄的匯總集合會產生一個記錄檔案，其中包含您網站中所有電腦的追蹤訊息，或部署的全域範圍。</span><span class="sxs-lookup"><span data-stu-id="97531-158">The aggregated collection of logs produces a log file that contains trace messages from all computers in your site or global scope of your deployment.</span></span> <span data-ttu-id="97531-159">如果搜尋傳回的資料超過您可以 feasibly 分析的資料（通常稱為 [信噪比]，而雜訊太高），您可以執行另一個含有較窄參數的搜尋。</span><span class="sxs-lookup"><span data-stu-id="97531-159">If the search returns more data than you can feasibly analyze (typically known as a signal-to-noise ratio, where the noise is too high), you run another search with narrower parameters.</span></span> <span data-ttu-id="97531-160">此時，您可以開始注意顯示的模式，並可協助您更清楚地瞭解問題。</span><span class="sxs-lookup"><span data-stu-id="97531-160">At this point, you can begin to notice patterns that show up and can help you get a clearer focus on the problem.</span></span> <span data-ttu-id="97531-161">最後，在您執行幾個精緻式搜尋之後，您可以找到與問題相關的資料，並找出根本原因。</span><span class="sxs-lookup"><span data-stu-id="97531-161">Ultimately, after you perform a couple of refined searches you can find data that is relevant to the problem and figure out the root cause.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="97531-162">當您在 Lync Server 中出現問題案例時，請先詢問自己「我已經知道問題為何？」。</span><span class="sxs-lookup"><span data-stu-id="97531-162">When presented with a problem scenario in Lync Server, start by asking yourself “What do I already know about the problem?”</span></span> <span data-ttu-id="97531-163">如果您要量化問題界限，您可以在 Lync Server 中消除大部分的運營實體部分。</span><span class="sxs-lookup"><span data-stu-id="97531-163">If you quantify the problem boundaries, you can eliminate a large part of the operational entities in Lync Server.</span></span><BR><span data-ttu-id="97531-164">考慮在尋找連絡人時，使用者無法取得目前結果的範例案例。</span><span class="sxs-lookup"><span data-stu-id="97531-164">Consider an example scenario where you know that users are not getting current results when looking for a contact.</span></span> <span data-ttu-id="97531-165">在媒體元件、企業語音、會議和許多其他元件中，沒有任何問題。</span><span class="sxs-lookup"><span data-stu-id="97531-165">There is no point in looking for problems in the media components, Enterprise Voice, conferencing, and a number of other components.</span></span> <span data-ttu-id="97531-166">您可能不知道問題的實際原因：在用戶端上，或是伺服器端問題？</span><span class="sxs-lookup"><span data-stu-id="97531-166">What you may not know is where the problem actually is: on the client, or is this a server-side problem?</span></span> <span data-ttu-id="97531-167">連絡人是由使用者複製程式從 Active Directory 收集，並透過通訊錄服務器（ABServer）傳送至用戶端。</span><span class="sxs-lookup"><span data-stu-id="97531-167">Contacts are collected from Active Directory by the User Replicator and delivered to the client by way of the Address Book Server (ABServer).</span></span> <span data-ttu-id="97531-168">ABServer 會從 RTC 資料庫取得它的更新（使用者複製程式寫入這些檔案），並將它們收集到通訊錄檔案（依預設值為 1:30 AM）。</span><span class="sxs-lookup"><span data-stu-id="97531-168">The ABServer gets its updates from the RTC database (where User Replicator wrote them) and collects them into address book files, by default – 1:30 AM.</span></span> <span data-ttu-id="97531-169">Lync Server 用戶端會根據隨機排程來取得新的通訊錄。</span><span class="sxs-lookup"><span data-stu-id="97531-169">The Lync Server clients retrieve the new address book on a randomized schedule.</span></span> <span data-ttu-id="97531-170">因為您知道程式的運作方式，所以您可以減少搜尋問題，因為使用者複製程式已從 Active Directory 收集資料，而 ABServer 無法檢索及建立通訊錄檔案，或用戶端無法下載通訊錄檔案。</span><span class="sxs-lookup"><span data-stu-id="97531-170">Because you know how the process works, you can reduce your search for the potential cause to an issue related to data being collected from Active Directory by the User Replicator, the ABServer not retrieving and creating the address book files, or the clients not downloading the address book file.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

