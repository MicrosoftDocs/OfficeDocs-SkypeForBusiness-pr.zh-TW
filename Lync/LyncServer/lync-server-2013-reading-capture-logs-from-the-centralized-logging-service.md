---
title: Lync Server 2013：從集中式記錄服務讀取捕獲記錄
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reading capture logs from the Centralized Logging Service
ms:assetid: c86ccf61-d86f-4ebd-b8d1-984a1b73005d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721879(v=OCS.15)
ms:contentKeyID: 49733813
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55bfeaa5bc9a2e89d8c52529c5d05ae7e3ee8feb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reading-capture-logs-from-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="e2ded-102">從 Lync Server 2013 中的集中式記錄服務讀取捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="e2ded-102">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ded-103">_**主題上次修改日期：** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="e2ded-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="e2ded-104">您可以在執行搜尋之後，充分發揮集中式記錄服務的益處，而且您有一個檔案可用來追蹤已報告的問題。</span><span class="sxs-lookup"><span data-stu-id="e2ded-104">You realize the real benefit of the Centralized Logging Service after you run the search and you have a file that you can use to track down a reported problem.</span></span> <span data-ttu-id="e2ded-105">您可以透過多種方式來讀取檔案。</span><span class="sxs-lookup"><span data-stu-id="e2ded-105">There are a number of ways that you can read the file.</span></span> <span data-ttu-id="e2ded-106">輸出檔案是標準的文字格式，您可以使用 Notepad.exe 或任何其他能讓您開啟並讀取文字檔的程式。</span><span class="sxs-lookup"><span data-stu-id="e2ded-106">The output file is in a standard text format and you can use Notepad.exe or any other programs that will allow you to open and read a text file.</span></span> <span data-ttu-id="e2ded-107">針對較大的檔案和更複雜的問題，您可以使用類似 Snooper 的工具，該工具是專門用來從集中式記錄服務讀取及分析記錄輸出。</span><span class="sxs-lookup"><span data-stu-id="e2ded-107">For larger files and more complex issues, you could use a tool like Snooper.exe that is designed to read and parse the logging output from the Centralized Logging Service.</span></span> <span data-ttu-id="e2ded-108">Snooper 隨附于 Lync Server 2013 調試工具中，可做為個別下載。</span><span class="sxs-lookup"><span data-stu-id="e2ded-108">Snooper is included with the Lync Server 2013 Debug Tools that are available as a separate download.</span></span> <span data-ttu-id="e2ded-109">您可以在此處下載 Lync Server 2013 調試工具： [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257)。</span><span class="sxs-lookup"><span data-stu-id="e2ded-109">You can download the Lync Server 2013 Debug Tools here: [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257).</span></span> <span data-ttu-id="e2ded-110">當您安裝 Lync Server 2013 調試工具時，不會建立簡短的剪下和功能表項目。</span><span class="sxs-lookup"><span data-stu-id="e2ded-110">When you install the Lync Server 2013 Debug Tools, short cuts and menu items are not created.</span></span> <span data-ttu-id="e2ded-111">安裝 Lync Server 2013 調試工具之後，請開啟 Windows 資源管理器、命令列視窗或 Lync Server 管理命令介面，然後移至目錄（預設位置） C：\\Program Files\\Microsoft Lync Server 2013\\調試工具。</span><span class="sxs-lookup"><span data-stu-id="e2ded-111">After you install the Lync Server 2013 Debug Tools, open Windows Explorer, a command-line window, or Lync Server Management Shell and go to the directory (default location) C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="e2ded-112">按兩下 Snooper 或輸入 Snooper，然後在您使用命令列或 Lync Server 管理命令介面時，按下 ENTER。</span><span class="sxs-lookup"><span data-stu-id="e2ded-112">Double-click Snooper.exe or type Snooper.exe, and then press ENTER if you are using the command line or Lync Server Management Shell.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="e2ded-113">本主題的目的不是詳細說明並討論疑難排解技巧。</span><span class="sxs-lookup"><span data-stu-id="e2ded-113">The intent of this topic is not to detail and discuss troubleshooting techniques.</span></span> <span data-ttu-id="e2ded-114">疑難排解及周圍的程式是一種複雜的主題。</span><span class="sxs-lookup"><span data-stu-id="e2ded-114">Troubleshooting and the processes around it is a complex subject.</span></span> <span data-ttu-id="e2ded-115">如需疑難排解基本功能及特定工作負荷疑難排解的詳細資料，請參閱 Microsoft Lync Server 2010 <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>資源套件活頁簿。</span><span class="sxs-lookup"><span data-stu-id="e2ded-115">For details about troubleshooting basics and troubleshooting specific workloads, see the Microsoft Lync Server 2010 Resource Kit book at <A href="http://go.microsoft.com/fwlink/p/?linkid=211003">https://go.microsoft.com/fwlink/p/?linkId=211003</A>.</span></span> <span data-ttu-id="e2ded-116">程式和程式也適用于 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e2ded-116">The processes and procedures still apply to Lync Server 2013.</span></span>



</div>

<span data-ttu-id="e2ded-117">Lync Server 2013 引進了一份更新版本的 Snooper，其中包含一些新功能。</span><span class="sxs-lookup"><span data-stu-id="e2ded-117">Lync Server 2013 introduces an updated version of Snooper that includes some new features.</span></span> <span data-ttu-id="e2ded-118">下列螢幕擷取畫面顯示 Office 通訊伺服器2007的 Snooper 版本。</span><span class="sxs-lookup"><span data-stu-id="e2ded-118">The following screen shot shows the version of Snooper from Office Communications Server 2007.</span></span>

<span data-ttu-id="e2ded-119">![Office 通訊2007版本的 Snooper。](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office 通訊2007版本的 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="e2ded-119">![Office Communications 2007 version of Snooper.](images/JJ721879.129503a8-8edd-4bb0-a68f-c43f9a548b93(OCS.15).jpg "Office Communications 2007 version of Snooper.")</span></span>

<span data-ttu-id="e2ded-120">下列螢幕擷取畫面顯示 Lync Server 2013 調試工具中所包含的新 Snooper 版本。</span><span class="sxs-lookup"><span data-stu-id="e2ded-120">The following screen shot shows the new version of Snooper included in the Lync Server 2013 Debug Tools.</span></span>

<span data-ttu-id="e2ded-121">![Lync Server 2013 版本的 Snooper。](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 版本的 Snooper。")</span><span class="sxs-lookup"><span data-stu-id="e2ded-121">![Lync Server 2013 version of Snooper.](images/JJ721879.131495dd-8220-4ae4-af37-0ac5c318fd45(OCS.15).jpg "Lync Server 2013 version of Snooper.")</span></span>

<span data-ttu-id="e2ded-122">下列螢幕擷取畫面顯示工具列，其中包含常用的函數。</span><span class="sxs-lookup"><span data-stu-id="e2ded-122">The following screen shot shows the toolbar with frequently used functions.</span></span>

<span data-ttu-id="e2ded-123">![Snooper 2013 工具列。](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 工具列。")</span><span class="sxs-lookup"><span data-stu-id="e2ded-123">![Snooper 2013 toolbar.](images/JJ721879.989249c5-a33e-4251-b8b4-411019cc12b2(OCS.15).jpg "Snooper 2013 toolbar.")</span></span>

<span data-ttu-id="e2ded-124">而且，新增值的最新功能就是流程圖（[通話流程]）圖表視圖。</span><span class="sxs-lookup"><span data-stu-id="e2ded-124">And, the newest feature that adds value is the Flow Chart (call flow) diagram view.</span></span> <span data-ttu-id="e2ded-125">您可以在 [**郵件**] 索引標籤中選取郵件流程，然後按一下 [**通話流程**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e2ded-125">You select a message flow in the **Message** tab and click the **Call Flow** button.</span></span> <span data-ttu-id="e2ded-126">當您在郵件中進行時，會使用新的資料來更新通話流程圖表。</span><span class="sxs-lookup"><span data-stu-id="e2ded-126">As you proceed through the messages, the call flow diagram updates with new data.</span></span>

<span data-ttu-id="e2ded-127">![Snooper 2013 通話流程圖表。](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 通話流程圖表。")</span><span class="sxs-lookup"><span data-stu-id="e2ded-127">![Snooper 2013 call flow diagram.](images/JJ721879.bb8be45d-a842-48fe-86f8-380207d70bab(OCS.15).jpg "Snooper 2013 call flow diagram.")</span></span>

<span data-ttu-id="e2ded-128">您可以將游標暫留在圖表視圖上，並取得流程與訊息以及伺服器元素的訊息和內容的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e2ded-128">You can hover over the diagram view and get details about the messages and content of the flows and messages as well as the server elements.</span></span> <span data-ttu-id="e2ded-129">按一下任何通話流程箭號，即可移至 [郵件] 視圖中的郵件。</span><span class="sxs-lookup"><span data-stu-id="e2ded-129">Click on any call flow arrow to go to the message in the Messages view.</span></span>

<span data-ttu-id="e2ded-130">![通話流程圖表訊息詳細資料。](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "通話流程圖表訊息詳細資料。")</span><span class="sxs-lookup"><span data-stu-id="e2ded-130">![Call flow diagram message details.](images/JJ721879.1147d720-38a9-4bda-8361-78f27ecde3d1(OCS.15).jpg "Call flow diagram message details.")</span></span>

<div>

## <a name="to-open-a-log-file-in-snooper"></a><span data-ttu-id="e2ded-131">若要在 Snooper 中開啟記錄檔</span><span class="sxs-lookup"><span data-stu-id="e2ded-131">To open a log file in Snooper</span></span>

1.  <span data-ttu-id="e2ded-132">若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="e2ded-132">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="e2ded-133">若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 的成員，或是 CsServerAdministrator 角色的存取控制（RBAC）安全性群組，或是包含這兩個群組中任一群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e2ded-133">To use Snooper and access the log files you must be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="e2ded-134">安裝 Lync Server 調試工具（LyncDebugTools）之後，請使用 Windows 資源管理器或從命令列將目錄變更為 Snooper 的位置。</span><span class="sxs-lookup"><span data-stu-id="e2ded-134">After the installation of the Lync Server Debugging Tools (LyncDebugTools.msi), change directory to the location of Snooper.exe using Windows Explorer or from the command line.</span></span> <span data-ttu-id="e2ded-135">根據預設，調試工具位於 C：\\Program Files\\Microsoft Lync Server 2013\\調試工具中。</span><span class="sxs-lookup"><span data-stu-id="e2ded-135">By default, the debugging tools are located in C:\\Program Files\\Microsoft Lync Server 2013\\Debugging Tools.</span></span> <span data-ttu-id="e2ded-136">按兩下或執行 Snooper。</span><span class="sxs-lookup"><span data-stu-id="e2ded-136">Double-click or run Snooper.exe.</span></span>

3.  <span data-ttu-id="e2ded-137">開啟 Snooper 之後，以滑鼠**按右鍵 [檔案]，按一下**[ **OpenFile**]，尋找您的記錄檔，在 [**開啟**舊檔] 對話方塊中選取檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e2ded-137">After Snooper is open, right-click **File**, click **OpenFile**, find your log files, select a file in the **Open** dialog box, and then click **Open**.</span></span>

4.  <span data-ttu-id="e2ded-138">記錄檔的**追蹤**訊息會顯示在 [**追蹤**] 索引標籤上。按一下 [**郵件**] 索引標籤即可查看所收集追蹤的訊息內容。</span><span class="sxs-lookup"><span data-stu-id="e2ded-138">The log file’s **Trace** messages are displayed on the **Trace** tab. Click the **Messages** tab to view the message contents of the collected traces.</span></span>

</div>

<div>

## <a name="to-display-a-call-flow-diagram"></a><span data-ttu-id="e2ded-139">顯示 [通話流程圖] 圖表</span><span class="sxs-lookup"><span data-stu-id="e2ded-139">To display a call flow diagram</span></span>

1.  <span data-ttu-id="e2ded-140">若要使用 Snooper 及開啟記錄檔，您必須具備記錄檔案的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="e2ded-140">To use Snooper and open log files, you need read access to the log files.</span></span> <span data-ttu-id="e2ded-141">若要使用 Snooper 及存取記錄檔，您必須是 CsAdministrator 或 CsServerAdministrator 角色的存取控制（RBAC）安全性群組的成員，或是包含這兩個群組的自訂 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e2ded-141">To use Snooper and access the log files, you need to be a member of the CsAdministrator or the CsServerAdministrator role-based access control (RBAC) security groups, or a custom RBAC role that contains either of these two groups.</span></span>

2.  <span data-ttu-id="e2ded-142">開啟記錄檔，然後按一下 [**訊息**] 索引標籤，在 [訊息] 視圖中選取交談，或選取 [**追蹤**] 索引標籤上的追蹤元件。</span><span class="sxs-lookup"><span data-stu-id="e2ded-142">Open a log file and click the **Messages** tab, select a conversation in the messages view or select a trace component on the **Trace** tab.</span></span>

3.  <span data-ttu-id="e2ded-143">按一下 [**通話流程**]。</span><span class="sxs-lookup"><span data-stu-id="e2ded-143">Click **Call Flow**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2ded-144">如果您按一下不屬於通話流程的訊息或追蹤，圖表就不會出現，且 Snooper 底部會出現狀態訊息，指出「此訊息不符合資格，無法 callfow」。</span><span class="sxs-lookup"><span data-stu-id="e2ded-144">If you click on a message or trace that is not part of a call flow, the diagram will not appear and a status message appears at the bottom of Snooper stating “This message is not eligible for callfow”.</span></span> <span data-ttu-id="e2ded-145">如果郵件或追蹤是通話流程的一部分，請選擇 [其他訊息] 或 [追蹤]，就會顯示通話流程。</span><span class="sxs-lookup"><span data-stu-id="e2ded-145">Choose another message or trace and the call flow will appear if the message or trace is part of a call flow.</span></span>

    
    </div>

4.  <span data-ttu-id="e2ded-146">在訊息或追蹤線之間移動，並注意 [通話流程圖] 圖表是否會更新或變更以顯示新圖表。</span><span class="sxs-lookup"><span data-stu-id="e2ded-146">Move through the Messages or the Trace lines and note whether the call flow diagram updates or changes to display a new diagram.</span></span>

5.  <span data-ttu-id="e2ded-147">將游標暫留在元素上，以取得通話訊息、端點及其他元件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e2ded-147">Hover over elements to get information about call messages, endpoints, and other components.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

