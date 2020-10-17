---
title: Lync Server 2013：從集中式記錄服務讀取捕獲記錄檔
description: Lync Server 2013：從集中式記錄服務讀取捕獲記錄檔。
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
ms.openlocfilehash: fcdd70c924b49098814e80a375ae34d2bf48dc41
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559159"
---
# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="e5b59-103">在 Lync Server 2013 中讀取集中式記錄服務的捕獲記錄檔</span><span class="sxs-lookup"><span data-stu-id="e5b59-103">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5b59-104">_**主題上次修改日期：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="e5b59-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="e5b59-105">在您執行搜尋後，您就可以充分利用集中式記錄服務，您可以用來追蹤已報告問題的檔案。</span><span class="sxs-lookup"><span data-stu-id="e5b59-105">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="e5b59-106">您可以使用許多方式來讀取檔案。</span><span class="sxs-lookup"><span data-stu-id="e5b59-106">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="e5b59-107">輸出檔是標準的文字格式，您可以使用 Notepad.exe 或任何其他可讓您開啟及讀取文字檔的程式。</span><span class="sxs-lookup"><span data-stu-id="e5b59-107">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="e5b59-108">針對較大的檔案和更複雜的問題，您可以使用類似 Snooper.exe 的工具，以用於讀取及分析集中式記錄服務的記錄輸出。</span><span class="sxs-lookup"><span data-stu-id="e5b59-108">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="e5b59-109">Snooper 隨附的 Lync Server 2013 調試工具，可做為個別下載。</span><span class="sxs-lookup"><span data-stu-id="e5b59-109">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="e5b59-110">您可以在以下位置下載 Lync Server 2013 調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) 。</span><span class="sxs-lookup"><span data-stu-id="e5b59-110">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="e5b59-111">當您安裝 Lync Server 2013 調試工具時，不會建立簡短的剪下及功能表項目目。</span><span class="sxs-lookup"><span data-stu-id="e5b59-111">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="e5b59-112">安裝 Lync Server 2013 調試工具後，請開啟 Windows Explorer、命令列視窗或 Lync Server 管理命令介面，然後移至目錄 (預設位置) C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 調試工具。</span><span class="sxs-lookup"><span data-stu-id="e5b59-112">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="e5b59-113">在 [Snooper.exe] 或 [輸入 Snooper.exe] 中按兩下，如果使用命令列或 Lync Server 管理命令介面，請按 ENTER 鍵。</span><span class="sxs-lookup"><span data-stu-id="e5b59-113">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e5b59-114">本主題的目的不是詳細討論和討論疑難排解技術。</span><span class="sxs-lookup"><span data-stu-id="e5b59-114">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="e5b59-115">疑難排解及其周圍的程式是複雜的主體。</span><span class="sxs-lookup"><span data-stu-id="e5b59-115">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="e5b59-116">如需疑難排解基本及疑難排解特定工作負載的詳細資訊，請參閱《 Microsoft Lync Server 2010 Resource 工具組手冊》 <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A> 。</span><span class="sxs-lookup"><span data-stu-id="e5b59-116">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="https://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="e5b59-117">處理常式和程式仍適用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e5b59-117">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="e5b59-118">Lync Server 2013 引進 Snooper 的更新版本，包含一些新功能。</span><span class="sxs-lookup"><span data-stu-id="e5b59-118">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="e5b59-119">下列螢幕擷取畫面顯示 Office 通訊伺服器2007的 Snooper 版本。</span><span class="sxs-lookup"><span data-stu-id="e5b59-119">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="e5b59-120">![Office 通訊2007版本的 Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office 通訊2007版本的 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="e5b59-120">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="e5b59-121">下列螢幕擷取畫面顯示 Lync Server 2013 調試工具中所包含的新 Snooper 版本。</span><span class="sxs-lookup"><span data-stu-id="e5b59-121">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="e5b59-122">![Lync Server 2013 版本的 Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="e5b59-122">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="e5b59-123">下列螢幕擷取畫面顯示工具列使用常用的功能。</span><span class="sxs-lookup"><span data-stu-id="e5b59-123">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="e5b59-124">![Snooper 2013 工具列。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具列。")</span><span class="sxs-lookup"><span data-stu-id="e5b59-124">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="e5b59-125">而且，新增值的最新功能是流程圖表 (的通話流程) 圖表] 視圖。</span><span class="sxs-lookup"><span data-stu-id="e5b59-125">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="e5b59-126">您可以選取 [ **郵件** ] 索引標籤中的郵件流程，然後按一下 [ **通話流程** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e5b59-126">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="e5b59-127">當您繼續進行郵件時，通話流程圖表會以新的資料進行更新。</span><span class="sxs-lookup"><span data-stu-id="e5b59-127">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="e5b59-128">![Snooper 2013 通話流程圖表。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話流程圖表。")</span><span class="sxs-lookup"><span data-stu-id="e5b59-128">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="e5b59-129">您可以將游標移到圖表視圖上方，並取得流程和郵件以及伺服器元素的訊息和內容的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e5b59-129">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="e5b59-130">按一下任何呼叫流程箭號，以移至郵件視圖中的郵件。</span><span class="sxs-lookup"><span data-stu-id="e5b59-130">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="e5b59-131">![通話流程圖表郵件詳細資料。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "通話流程圖表郵件詳細資料。")</span><span class="sxs-lookup"><span data-stu-id="e5b59-131">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="e5b59-132">若要在 Snooper 中開啟記錄檔</span><span class="sxs-lookup"><span data-stu-id="e5b59-132">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="e5b59-133">若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。</span><span class="sxs-lookup"><span data-stu-id="e5b59-133">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="e5b59-134">若要使用 Snooper 和存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e5b59-134">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="e5b59-135">安裝 Lync Server 調試工具 ( # A0) 後，請使用 Windows Explorer 或命令列變更目錄至 Snooper.exe 的位置。</span><span class="sxs-lookup"><span data-stu-id="e5b59-135">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="e5b59-136">根據預設，調試工具位於 C： \\ Program Files \\ Microsoft Lync Server 2013 \\ 調試工具中。</span><span class="sxs-lookup"><span data-stu-id="e5b59-136">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="e5b59-137">按兩下或執行 Snooper.exe。</span><span class="sxs-lookup"><span data-stu-id="e5b59-137">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="e5b59-138">開啟 Snooper 後，以滑鼠 **按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，選取 [ **開啟** ] 對話方塊中的檔案，然後按一下 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e5b59-138">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="e5b59-139">記錄檔的 **追蹤** 訊息會顯示在 [ **追蹤** ] 索引標籤上。按一下 [ **訊息** ] 索引標籤，以查看收集之追蹤的郵件內容。</span><span class="sxs-lookup"><span data-stu-id="e5b59-139">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="e5b59-140">顯示通話流程圖表</span><span class="sxs-lookup"><span data-stu-id="e5b59-140">To display a call flow diagram</span></span>

1.  <span data-ttu-id="e5b59-141">若要使用 Snooper 及開啟記錄檔，您需要有記錄檔的讀取權。</span><span class="sxs-lookup"><span data-stu-id="e5b59-141">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="e5b59-142">若要使用 Snooper 並存取記錄檔，您必須是 CsAdministrator 的成員或 CsServerAdministrator 角色型存取控制 (RBAC) 安全性群組，或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e5b59-142">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="e5b59-143">開啟記錄檔，然後按一下 [ **訊息** ] 索引標籤，在 [ **追蹤** ] 索引標籤上選取 [交談]，或選取一個追蹤元件。</span><span class="sxs-lookup"><span data-stu-id="e5b59-143">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="e5b59-144">按一下 [ **通話流程**]。</span><span class="sxs-lookup"><span data-stu-id="e5b59-144">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5b59-145">如果您按一下的訊息或追蹤不是通話流程的一部分，將不會顯示圖表，而且會在 Snooper 的底部顯示狀態訊息，指出「這封郵件不符合 callfow」。</span><span class="sxs-lookup"><span data-stu-id="e5b59-145">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="e5b59-146">選擇 [另一封郵件] 或 [追蹤]，如果郵件或追蹤屬於通話流程的一部分，就會顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="e5b59-146">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="e5b59-147">在訊息或追蹤列間移動，並附注通話流程圖表是否更新或變更，以顯示新的圖表。</span><span class="sxs-lookup"><span data-stu-id="e5b59-147">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="e5b59-148">將游標移到元素上，以取得通話訊息、端點及其他元件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e5b59-148">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

