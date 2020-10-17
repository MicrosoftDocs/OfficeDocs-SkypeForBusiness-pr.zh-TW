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
ms.openlocfilehash: 276cc87d6ec943332fc30dc21c0906a03703382d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529950"
---
# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="62e55-102">在 Lync Server 2013 中使用集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="62e55-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62e55-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="62e55-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="62e55-104">集中式記錄服務是 Lync Server 2013 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="62e55-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="62e55-105">它是舊版 **OCSLogger** 和 **OCSTracer** 工具的增強替代功能。</span><span class="sxs-lookup"><span data-stu-id="62e55-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="62e55-106">您可以使用集中式記錄服務來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="62e55-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="62e55-107">開始從單一位置和命令登入一或多個電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="62e55-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="62e55-108">停止從單一位置和命令登入一或多個電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="62e55-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="62e55-p102">搜尋一或多個電腦和集區上的記錄檔，找出單一位置或命令。您可以量身打造搜尋命令，傳回所有電腦上擷取和儲存的整個記錄檔彙總，或傳回會擷取特定資料的已整理結果。</span><span class="sxs-lookup"><span data-stu-id="62e55-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="62e55-111">如下設定記錄工作階段：</span><span class="sxs-lookup"><span data-stu-id="62e55-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="62e55-112">定義**案例**，或使用預設案例。</span><span class="sxs-lookup"><span data-stu-id="62e55-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="62e55-113">集中式記錄服務中的 *案例* 是由範圍 (全域或網站) 所組成，案例名稱可識別案例的目的，以及一或多個提供者。</span><span class="sxs-lookup"><span data-stu-id="62e55-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="62e55-114">您可以在任何指定的時間於一部電腦上執行兩個案例。</span><span class="sxs-lookup"><span data-stu-id="62e55-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="62e55-p104">使用現有*提供者*或建立新的提供者。*提供者*定義記錄工作階段所收集的內容、內容的詳細程度、要追蹤哪些元件，以及要套用哪些旗標。</span><span class="sxs-lookup"><span data-stu-id="62e55-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="62e55-117">如果您熟悉 OCSLogger，<EM>提供者</EM>一詞是指<STRONG>元件</STRONG> (例如，S4、SIPStack)、<STRONG>記錄類型</STRONG> (例如，WPP、EventLog 或 IIS logfile)、<STRONG>記錄層次</STRONG> (例如，全部、詳細、偵錯) 及<STRONG>旗標</STRONG> (例如，TF_COMPONENT、TF_DIAG) 的集合。</span><span class="sxs-lookup"><span data-stu-id="62e55-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="62e55-118">這些專案是在提供者 (Windows PowerShell 變數) 並傳遞至集中式記錄服務命令中定義的。</span><span class="sxs-lookup"><span data-stu-id="62e55-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="62e55-119">設定要從中收集記錄的電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="62e55-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="62e55-120">從選項**網站** (僅在該網站中的電腦執行記錄擷取) 或**全域** (在部署中所有的電腦上執行記錄擷取) 定義記錄工作階段的範圍。</span><span class="sxs-lookup"><span data-stu-id="62e55-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="62e55-121">集中式記錄服務功能極為強大，可滿足幾乎所有對問題疑難排解的需求。</span><span class="sxs-lookup"><span data-stu-id="62e55-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="62e55-122">從根本原因分析到效能問題，集中式記錄服務可能是任何系統管理員的重要工具。</span><span class="sxs-lookup"><span data-stu-id="62e55-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="62e55-123">所有範例都是使用 Lync Server 管理命令介面來顯示。</span><span class="sxs-lookup"><span data-stu-id="62e55-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="62e55-124">集中式記錄服務會有一個命令列元件，稱為 **CLSController.exe**。</span><span class="sxs-lookup"><span data-stu-id="62e55-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="62e55-125">命令列工具本身提供說明。</span><span class="sxs-lookup"><span data-stu-id="62e55-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="62e55-126">不過，不過，您只能從命令列執行有限的功能。</span><span class="sxs-lookup"><span data-stu-id="62e55-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="62e55-127">使用 Lync Server 管理命令介面，您可以存取更大、更具可設定的功能。</span><span class="sxs-lookup"><span data-stu-id="62e55-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="62e55-128">使用集中式記錄服務時，請務必將 Lync Server 管理命令介面視為第一種和最重要的方法。</span><span class="sxs-lookup"><span data-stu-id="62e55-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="62e55-129">本節中的主題說明如何使用集中式記錄服務，以及如何使用其許多功能的範例。</span><span class="sxs-lookup"><span data-stu-id="62e55-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="62e55-130">本章節內容</span><span class="sxs-lookup"><span data-stu-id="62e55-130">In This Section</span></span>

  - [<span data-ttu-id="62e55-131">Lync Server 2013 中的集中式記錄服務概述</span><span class="sxs-lookup"><span data-stu-id="62e55-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="62e55-132">在 Lync Server 2013 中管理集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="62e55-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="62e55-133">瞭解 Lync Server 2013 中的集中式記錄服務設定設定</span><span class="sxs-lookup"><span data-stu-id="62e55-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="62e55-134">使用 Start 進行集中式記錄服務以在 Lync Server 2013 中捕獲記錄</span><span class="sxs-lookup"><span data-stu-id="62e55-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="62e55-135">在 Lync Server 2013 中使用停用集中式記錄服務</span><span class="sxs-lookup"><span data-stu-id="62e55-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="62e55-136">在 Lync Server 2013 中使用集中式記錄服務所建立之捕獲記錄檔的搜尋</span><span class="sxs-lookup"><span data-stu-id="62e55-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="62e55-137">在 Lync Server 2013 中讀取集中式記錄服務的捕獲記錄檔</span><span class="sxs-lookup"><span data-stu-id="62e55-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

