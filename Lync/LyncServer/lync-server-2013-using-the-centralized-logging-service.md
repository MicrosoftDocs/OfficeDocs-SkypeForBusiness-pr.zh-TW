---
title: Lync Server 2013： 使用集中式的記錄服務
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
ms.openlocfilehash: 565c71a2a4e52b50b4807d7a5c5673e24c0a1a71
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-centralized-logging-service-in-lync-server-2013"></a><span data-ttu-id="260e4-102">使用 Lync Server 2013 中的集中式的記錄服務</span><span class="sxs-lookup"><span data-stu-id="260e4-102">Using the Centralized Logging Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="260e4-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="260e4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="260e4-104">The Centralized Logging Service 是在 Lync Server 2013 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="260e4-104">The Centralized Logging Service is a new feature in Lync Server 2013.</span></span> <span data-ttu-id="260e4-105">它是舊版 **OCSLogger** 和 **OCSTracer** 工具的增強替代功能。</span><span class="sxs-lookup"><span data-stu-id="260e4-105">It is an enhanced replacement for the **OCSLogger** and **OCSTracer** tools that were provided in previous releases.</span></span> <span data-ttu-id="260e4-106">您可以使用集中式記錄服務若要執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="260e4-106">You can use the Centralized Logging Service to perform the following tasks:</span></span>

  - <span data-ttu-id="260e4-107">開始從單一位置和命令登入一或多個電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="260e4-107">Start logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="260e4-108">停止從單一位置和命令登入一或多個電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="260e4-108">Stop logging on one or more computers and pools from a single location and command.</span></span>

  - <span data-ttu-id="260e4-p102">搜尋一或多個電腦和集區上的記錄檔，找出單一位置或命令。您可以量身打造搜尋命令，傳回所有電腦上擷取和儲存的整個記錄檔彙總，或傳回會擷取特定資料的已整理結果。</span><span class="sxs-lookup"><span data-stu-id="260e4-p102">Search logs on one or more computers and pools for a single location and command. You can tailor the search command to return the entire aggregation of logs that were captured and stored on all machines, or return a trimmed-down result that captures specific data.</span></span>

  - <span data-ttu-id="260e4-111">如下設定記錄工作階段：</span><span class="sxs-lookup"><span data-stu-id="260e4-111">Configure logging sessions as follows:</span></span>
    
      - <span data-ttu-id="260e4-112">定義**案例**，或使用預設案例。</span><span class="sxs-lookup"><span data-stu-id="260e4-112">Define a **Scenario**, or use a default scenario.</span></span> <span data-ttu-id="260e4-113">Centralized Logging Service 中的*案例*組成範圍 (全域或網站)，來識別此案例中，與一或多個提供者的目的分析藍本名稱。</span><span class="sxs-lookup"><span data-stu-id="260e4-113">A *scenario* in Centralized Logging Service is made up of scope (global or site), a scenario name to identify the purpose of the scenario, and one or more providers.</span></span> <span data-ttu-id="260e4-114">您可以在任何指定的時間於一部電腦上執行兩個案例。</span><span class="sxs-lookup"><span data-stu-id="260e4-114">You can run two scenarios at any given time on a computer.</span></span>
    
      - <span data-ttu-id="260e4-p104">使用現有*提供者*或建立新的提供者。*提供者*定義記錄工作階段所收集的內容、內容的詳細程度、要追蹤哪些元件，以及要套用哪些旗標。</span><span class="sxs-lookup"><span data-stu-id="260e4-p104">Use an existing *provider* or create a new provider. A *provider* defines what the logging session collects, what level of detail, what components to trace, and what flags are applied.</span></span>
        
        <div>
        

        > [!TIP]  
        > <span data-ttu-id="260e4-117">如果您熟悉 OCSLogger，<EM>提供者</EM>一詞是指<STRONG>元件</STRONG> (例如，S4、SIPStack)、<STRONG>記錄類型</STRONG> (例如，WPP、EventLog 或 IIS logfile)、<STRONG>記錄層次</STRONG> (例如，全部、詳細、偵錯) 及<STRONG>旗標</STRONG> (例如，TF_COMPONENT、TF_DIAG) 的集合。</span><span class="sxs-lookup"><span data-stu-id="260e4-117">If you are familiar with OCSLogger, the term <EM>providers</EM> refers to the collection of <STRONG>components</STRONG> (for example, S4, SIPStack), a <STRONG>logging type</STRONG> (for example, WPP, EventLog, or IIS logfile), a <STRONG>tracing level</STRONG> (for example, All, verbose, debug), and <STRONG>flags</STRONG> (for example, TF_COMPONENT, TF_DIAG).</span></span> <span data-ttu-id="260e4-118">這些項目會提供者 （Windows PowerShell 變數） 中所定義，並傳遞至 Centralized Logging Service 命令。</span><span class="sxs-lookup"><span data-stu-id="260e4-118">These items are defined in the provider (a Windows PowerShell variable) and passed into the Centralized Logging Service command.</span></span>

        
        </div>
    
      - <span data-ttu-id="260e4-119">設定要從中收集記錄的電腦和集區。</span><span class="sxs-lookup"><span data-stu-id="260e4-119">Configure the computers and pools that you want to collect logs from.</span></span>
    
      - <span data-ttu-id="260e4-120">從選項**網站** (僅在該網站中的電腦執行記錄擷取) 或**全域** (在部署中所有的電腦上執行記錄擷取) 定義記錄工作階段的範圍。</span><span class="sxs-lookup"><span data-stu-id="260e4-120">Define the scope for the logging session from the options **Site** (run logging captures on computers in that site only), or **Global** (run logging capture on all computers in the deployment).</span></span>

<span data-ttu-id="260e4-121">The Centralized Logging Service 具有強大的功能，而且可以符合幾乎所有的問題的疑難排解需求 — 大型或小型。</span><span class="sxs-lookup"><span data-stu-id="260e4-121">The Centralized Logging Service is extremely powerful and can meet nearly all of the needs for troubleshooting problems—large or small.</span></span> <span data-ttu-id="260e4-122">從效能問題的根本原因分析，the Centralized Logging Service 可以是任何系統管理員的重要工具。</span><span class="sxs-lookup"><span data-stu-id="260e4-122">From root cause analysis to performance problems, the Centralized Logging Service can be an important tool for any administrator.</span></span> <span data-ttu-id="260e4-123">所有範例會都顯示使用 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="260e4-123">All examples are shown using the Lync Server Management Shell.</span></span> <span data-ttu-id="260e4-124">沒有 the Centralized Logging Service 呼叫**CLSController.exe**的命令列元件。</span><span class="sxs-lookup"><span data-stu-id="260e4-124">There is a command-line component for the Centralized Logging Service called **CLSController.exe**.</span></span> <span data-ttu-id="260e4-125">命令列工具本身提供說明。</span><span class="sxs-lookup"><span data-stu-id="260e4-125">Help is provided for the command-line tool through the tool itself.</span></span> <span data-ttu-id="260e4-126">不過，不過，您只能從命令列執行有限的功能。</span><span class="sxs-lookup"><span data-stu-id="260e4-126">However, there is a limited set of functions that you can execute from the command line.</span></span> <span data-ttu-id="260e4-127">使用 Lync Server 管理命令介面，您可以存取一組更大且更可設定的功能。</span><span class="sxs-lookup"><span data-stu-id="260e4-127">By using Lync Server Management Shell, you have access to a much larger and much more configurable set of features.</span></span> <span data-ttu-id="260e4-128">使用集中式記錄服務時，應一律做為第一個及最重要方法考量 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="260e4-128">You should always consider Lync Server Management Shell as the first and foremost method when using the Centralized Logging Service.</span></span>

<span data-ttu-id="260e4-129">本節中的主題說明如何使用集中式記錄服務及如何使用其中眾多功能的範例。</span><span class="sxs-lookup"><span data-stu-id="260e4-129">The topics in this section explain how to use the Centralized Logging Service and examples of how to use its many features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="260e4-130">本章節內容</span><span class="sxs-lookup"><span data-stu-id="260e4-130">In This Section</span></span>

  - [<span data-ttu-id="260e4-131">Lync Server 2013 中的集中式的記錄服務概觀</span><span class="sxs-lookup"><span data-stu-id="260e4-131">Overview of the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-overview-of-the-centralized-logging-service.md)

  - [<span data-ttu-id="260e4-132">管理 Lync Server 2013 中的集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="260e4-132">Managing the Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-managing-the-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="260e4-133">了解在 Lync Server 2013 中的集中式記錄服務組態設定</span><span class="sxs-lookup"><span data-stu-id="260e4-133">Understanding Centralized Logging Service configuration settings in Lync Server 2013</span></span>](lync-server-2013-understanding-centralized-logging-service-configuration-settings.md)

  - [<span data-ttu-id="260e4-134">將 Start 用於集中式記錄服務以擷取在 Lync Server 2013 中的記錄</span><span class="sxs-lookup"><span data-stu-id="260e4-134">Using Start for the Centralized Logging Service to capture logs in Lync Server 2013</span></span>](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)

  - [<span data-ttu-id="260e4-135">將 Stop 用於 Lync Server 2013 中的集中式的記錄服務</span><span class="sxs-lookup"><span data-stu-id="260e4-135">Using Stop for the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-stop-for-the-centralized-logging-service.md)

  - [<span data-ttu-id="260e4-136">使用集中式記錄服務在 Lync Server 2013 中建立的擷取記錄上的搜尋</span><span class="sxs-lookup"><span data-stu-id="260e4-136">Using search on capture logs created by the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-using-search-on-capture-logs-created-by-the-centralized-logging-service.md)

  - [<span data-ttu-id="260e4-137">讀取 the Centralized Logging Service Lync Server 2013 中擷取記錄</span><span class="sxs-lookup"><span data-stu-id="260e4-137">Reading capture logs from the Centralized Logging Service in Lync Server 2013</span></span>](lync-server-2013-reading-capture-logs-from-the-centralized-logging-service.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

