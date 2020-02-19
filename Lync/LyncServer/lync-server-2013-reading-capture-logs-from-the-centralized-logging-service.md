---
title: Lync Server 2013： 讀取擷取記錄從集中式記錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb1ec3ebde4f1277d6304190aceafa2e0fe2884
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="5f518-102">讀取 the Centralized Logging Service Lync Server 2013 中擷取記錄</span><span class="sxs-lookup"><span data-stu-id="5f518-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f518-103">_**主題上次修改日期：** 2016年-12 月 28 日_</span><span class="sxs-lookup"><span data-stu-id="5f518-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="5f518-104">執行搜尋，並可讓您可用於追蹤報告問題的檔案之後，您會發現 the Centralized Logging Service 的好處。</span><span class="sxs-lookup"><span data-stu-id="5f518-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="5f518-105">有多種方式，您可以讀取檔案。</span><span class="sxs-lookup"><span data-stu-id="5f518-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="5f518-106">輸出檔案會以標準文字格式，您可以使用 Notepad.exe 或任何其他的程式，可讓您能夠開啟和讀取的文字檔案。</span><span class="sxs-lookup"><span data-stu-id="5f518-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="5f518-107">較大的檔案，且更複雜的問題，您可以使用這類 Snooper.exe 是設計用來讀取並剖析從集中式記錄服務的記錄輸出的工具。</span><span class="sxs-lookup"><span data-stu-id="5f518-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="5f518-108">包含與 Lync Server 2013 偵錯工具可供個別下載 snooper。</span><span class="sxs-lookup"><span data-stu-id="5f518-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="5f518-109">您可以下載 Lync Server 2013 偵錯工具這裡： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)。</span><span class="sxs-lookup"><span data-stu-id="5f518-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="5f518-110">當您安裝 Lync Server 2013 偵錯工具時，簡短剪下和功能表項目不會建立。</span><span class="sxs-lookup"><span data-stu-id="5f518-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="5f518-111">安裝 Lync Server 2013 偵錯工具之後，開啟 [Windows 檔案總管、 命令列視窗或 Lync Server 管理命令介面，並移至目錄 （預設位置） c:\\Program Files\\Microsoft Lync Server 2013\\偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="5f518-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="5f518-112">連按兩下 [Snooper.exe 或輸入 Snooper.exe，，然後按 ENTER 鍵，如果您使用的命令列或 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="5f518-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5f518-113">本主題的目的並不是詳細資料，並討論疑難排解技巧。</span><span class="sxs-lookup"><span data-stu-id="5f518-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="5f518-114">疑難排解和其周圍的處理程序是複雜的主旨。</span><span class="sxs-lookup"><span data-stu-id="5f518-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="5f518-115">如需疑難排解基礎和疑難排解特定工作負載的詳細資訊，請參閱 Microsoft Lync Server 2010 Resource Kit 活頁簿在<A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>。</span><span class="sxs-lookup"><span data-stu-id="5f518-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="5f518-116">與程序仍然適用於 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5f518-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="5f518-117">Lync Server 2013 引進了 Snooper 包含一些新功能更新的版本。</span><span class="sxs-lookup"><span data-stu-id="5f518-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="5f518-118">下列螢幕擷取畫面顯示從 Office Communications Server 2007 的新版 Snooper。</span><span class="sxs-lookup"><span data-stu-id="5f518-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="5f518-119">![Office Communications 2007 版本 Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 版本 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="5f518-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="5f518-120">下列螢幕擷取畫面顯示的新版 Snooper 包含在 Lync Server 2013 偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="5f518-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="5f518-121">![Lync Server 2013 版本的 Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="5f518-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="5f518-122">下列螢幕擷取畫面顯示含有常用功能的工具列。</span><span class="sxs-lookup"><span data-stu-id="5f518-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="5f518-123">![Snooper 2013 工具列。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具列。")</span><span class="sxs-lookup"><span data-stu-id="5f518-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="5f518-124">並將值加入的最新功能是 [流程圖 （通話流程） 圖] 檢視。</span><span class="sxs-lookup"><span data-stu-id="5f518-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="5f518-125">您選取 [**郵件**] 索引標籤中的郵件流程，然後按一下 [**通話流程**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="5f518-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="5f518-126">當您繼續透過訊息、 通話流程圖表更新新的資料。</span><span class="sxs-lookup"><span data-stu-id="5f518-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="5f518-127">![Snooper 2013 通話流程圖表。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話流程圖表。")</span><span class="sxs-lookup"><span data-stu-id="5f518-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="5f518-128">您可以將滑鼠停留圖] 檢視，並取得有關郵件與內容設計的流量和郵件，以及伺服器元素的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5f518-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="5f518-129">按一下 [上移至 [郵件] 檢視中的訊息，任何通話流程箭號。</span><span class="sxs-lookup"><span data-stu-id="5f518-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="5f518-130">![呼叫流程圖訊息詳細資料。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "呼叫流程圖訊息詳細資料。")</span><span class="sxs-lookup"><span data-stu-id="5f518-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="5f518-131">若要在 Snooper 中開啟記錄檔</span><span class="sxs-lookup"><span data-stu-id="5f518-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="5f518-132">若要使用 Snooper 並開啟記錄檔，您需要的記錄檔的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="5f518-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="5f518-133">使用 Snooper 及存取記錄檔中，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含這兩個群組的自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="5f518-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="5f518-134">安裝後的 Lync Server 偵錯工具 (LyncDebugTools.msi)，將目錄變更為使用 Windows 檔案總管的 Snooper.exe 或從命令列的位置。</span><span class="sxs-lookup"><span data-stu-id="5f518-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="5f518-135">根據預設，偵錯工具都位於 c:\\Program Files\\Microsoft Lync Server 2013\\偵錯工具。</span><span class="sxs-lookup"><span data-stu-id="5f518-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="5f518-136">連按兩下 [或執行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="5f518-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="5f518-137">開啟 Snooper 後，**檔案**上按一下滑鼠右鍵按一下**OpenFile**、 尋找記錄檔、 中**開啟**] 對話方塊中，選取檔案，然後按一下 [**開啟**。</span><span class="sxs-lookup"><span data-stu-id="5f518-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="5f518-138">記錄檔的**追蹤**訊息會顯示在**追蹤**] 索引標籤按一下 [**郵件**] 索引標籤，若要檢視的收集的追蹤訊息內容。</span><span class="sxs-lookup"><span data-stu-id="5f518-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="5f518-139">若要顯示通話流程圖</span><span class="sxs-lookup"><span data-stu-id="5f518-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="5f518-140">若要使用 Snooper 並開啟記錄檔，您需要的記錄檔的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="5f518-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="5f518-141">若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組或包含這兩個群組的自訂 RBAC 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="5f518-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="5f518-142">開啟記錄檔並按一下 [**郵件**] 索引標籤、 [郵件] 檢視中選取交談或選取追蹤元件**追蹤**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="5f518-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="5f518-143">按一下 [**通話流程**。</span><span class="sxs-lookup"><span data-stu-id="5f518-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5f518-144">如果您按一下郵件或不屬於通話流程的追蹤，將不會顯示圖表及狀態郵件會出現在底部 Snooper 說明 「 此郵件不合格的 callfow 」。</span><span class="sxs-lookup"><span data-stu-id="5f518-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="5f518-145">選擇其他訊息或追蹤，如果訊息或追蹤是呼叫流程的一部分，呼叫流程將會出現。</span><span class="sxs-lookup"><span data-stu-id="5f518-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="5f518-146">透過訊息或追蹤行之間移動，並注意通話流程圖表是否更新或變成顯示新的圖表。</span><span class="sxs-lookup"><span data-stu-id="5f518-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="5f518-147">將滑鼠停留元素，以取得關於通話訊息、 端點及其他元件的資訊。</span><span class="sxs-lookup"><span data-stu-id="5f518-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

