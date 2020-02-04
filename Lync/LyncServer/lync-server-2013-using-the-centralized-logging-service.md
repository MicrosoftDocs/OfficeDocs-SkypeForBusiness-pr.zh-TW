---
title: Lync Server 2013：使用集中式記錄服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Centralized Logging Service
ms:assetid: 7b05aaef-f0ea-4649-ba8a-02e68b0cdf23
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688101(v=OCS.15)
ms:contentKeyID: 49733700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fb3687d036f7d72160c8af0e168a40d09c84e4b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="7fdb9-102">在 Lync Server 2013 中使用集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="7fdb9-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fdb9-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7fdb9-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7fdb9-104">[集中式記錄服務] 是 Lync Server 2013 的新功能。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="7fdb9-105">它是先前版本中提供的**OCSLogger**和**OCSTracer**工具的增強式取代。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="7fdb9-106">您可以使用集中式記錄服務來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="7fdb9-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="7fdb9-107">從單一位置和命令在一或多部電腦和池上開始記錄。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="7fdb9-108">從單一位置和命令停止記錄一或多台電腦和池。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="7fdb9-109">在一或多台電腦和池上搜尋記錄，以尋找單一位置和命令。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-109">Search logs on one or more computers and pools for a single location and command.</span></span> <span data-ttu-id="7fdb9-110">您可以調整 search 命令，以傳回已捕獲並儲存在所有電腦上的整個記錄匯總，或傳回可捕獲特定資料的修整結果。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-110">You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="7fdb9-111">設定記錄會話的方式如下：</span><span class="sxs-lookup"><span data-stu-id="7fdb9-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="7fdb9-112">定義**案例**，或使用預設情況。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="7fdb9-113">集中式記錄服務中的*案例*是由範圍（全域或網站）、案例名稱來識別案例的用途及一或多個提供者所組成。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="7fdb9-114">您可以在任何指定時間在電腦上執行兩種案例。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="7fdb9-115">使用現有的*提供者*或建立新的提供者。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-115">Use an existing *provider* or create a new provider.</span></span> <span data-ttu-id="7fdb9-116">*提供者*定義記錄會話收集的內容、詳細資料層級、要追蹤哪些元件，以及要套用哪些旗標。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-116">A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="7fdb9-117">如果您熟悉 OCSLogger，則「詞彙<EM>提供者</EM>」會參照<STRONG>元件</STRONG>集合（例如，S4、SIPStack）、<STRONG>記錄類型</STRONG>（例如，WPP、EventLog 或 IIS logfile）、<STRONG>追蹤等級</STRONG>（例如，All、verbose、debug）及<STRONG>旗標</STRONG>（例如 TF_COMPONENT、TF_DIAG）。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="7fdb9-118">這些專案是在提供者（Windows PowerShell 變數）中定義，並傳遞到集中式記錄服務命令。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="7fdb9-119">設定您要從中收集記錄的電腦和池。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="7fdb9-120">從 [選項]**網站**中定義記錄會話的範圍（僅限在該網站的電腦上執行記錄捕獲），或 [**全域**] （在部署中的所有電腦上執行記錄捕獲）。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="7fdb9-121">集中式記錄服務功能極其強大，而且幾乎能滿足所有疑難排解問題的需求（大或小）。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="7fdb9-122">從根本原因分析到效能問題，集中式記錄服務可能是任何系統管理員的重要工具。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="7fdb9-123">所有範例都是使用 Lync Server 管理命令介面來顯示。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="7fdb9-124">集中式記錄服務有一個名為**CLSController**的命令列元件。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="7fdb9-125">透過工具本身的命令列工具提供說明。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="7fdb9-126">不過，您可以從命令列執行一組有限的函數。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="7fdb9-127">透過使用 Lync Server 管理命令介面，您可以存取更大且更具可設定的功能。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="7fdb9-128">使用集中式記錄服務時，您必須先將 Lync Server 管理命令介面視為第一個和最重要的方法。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="7fdb9-129">本節中的主題說明如何使用集中式記錄服務，以及如何使用其多種功能的範例。</span><span class="sxs-lookup"><span data-stu-id="7fdb9-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7fdb9-130">本節內容</span><span class="sxs-lookup"><span data-stu-id="7fdb9-130">In This Section</span></span>

  - [<span data-ttu-id="7fdb9-131">Lync Server 2013 中的集中式記錄服務概覽</span><span class="sxs-lookup"><span data-stu-id="7fdb9-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="7fdb9-132">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="7fdb9-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="7fdb9-133">瞭解 Lync Server 2013 中的集中式記錄服務配置設定</span><span class="sxs-lookup"><span data-stu-id="7fdb9-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - <span data-ttu-id="7fdb9-134">[在 Lync Server 2013 中使用 [開始使用集中式記錄服務] 來捕獲記錄](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)</span><span class="sxs-lookup"><span data-stu-id="7fdb9-134">[Using Start for the Centralized Logging Service to capture logs in Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)</span></span>

  - [<span data-ttu-id="7fdb9-135">在 Lync Server 2013 中針對集中式記錄服務使用停止功能</span><span class="sxs-lookup"><span data-stu-id="7fdb9-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="7fdb9-136">在 Lync Server 2013 中使用集中式記錄服務所建立的捕獲記錄來進行搜尋</span><span class="sxs-lookup"><span data-stu-id="7fdb9-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="7fdb9-137">從 Lync Server 2013 中的集中式記錄服務讀取捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="7fdb9-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

