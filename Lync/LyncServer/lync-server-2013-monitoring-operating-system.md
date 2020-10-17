---
title: Lync Server 2013：監控作業系統
description: Lync Server 2013：監控作業系統。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring operating system
ms:assetid: 72406d3e-54c8-4796-8d6d-2144a5b6f030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720918(v=OCS.15)
ms:contentKeyID: 63969617
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9454b91a5f55467f93b41752686b4b0d727d935
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548059"
---
# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="027c8-103">Lync Server 2013 中的監控作業系統</span><span class="sxs-lookup"><span data-stu-id="027c8-103">Monitoring operating system in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="027c8-104">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="027c8-104">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="027c8-105">您必須監視 Lync Server 2013 中所有伺服器與元件的效能。</span><span class="sxs-lookup"><span data-stu-id="027c8-105">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="027c8-106">顯然，其中一個最重要的元件是作業系統本身。</span><span class="sxs-lookup"><span data-stu-id="027c8-106">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="027c8-107">Lync Server 2013 支援 x64 版本：</span><span class="sxs-lookup"><span data-stu-id="027c8-107">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="027c8-108">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="027c8-108">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="027c8-109">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="027c8-109">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="027c8-110">監視作業系統最透明的方式是使用 Windows Server 作業系統管理套件。</span><span class="sxs-lookup"><span data-stu-id="027c8-110">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="027c8-111">它可提供執行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 之電腦的基礎監控基礎，例如效能、健康情況及可用性。</span><span class="sxs-lookup"><span data-stu-id="027c8-111">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="027c8-112">透過偵測、警示及自動回應重要的事件和效能指標，這些管理元件可減少問題的解決時間，並增加執行 Windows Server 作業系統之系統的整體可用性和效能。</span><span class="sxs-lookup"><span data-stu-id="027c8-112">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="027c8-113">除了相關的 Windows Server management pack for System Center Operations Manager 之外，下列系統工具和資源可用於監視作業系統 (的健康情況，視作業系統版本) 而定。</span><span class="sxs-lookup"><span data-stu-id="027c8-113">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="027c8-114">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="027c8-114">Windows Server 2008 R2</span></span>

<span data-ttu-id="027c8-115">Windows Server 2008 R2 包含下列其他功能和工具，可協助系統管理員進行基本作業系統監控和管理：</span><span class="sxs-lookup"><span data-stu-id="027c8-115">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="027c8-116">**Windows Resource Monitor** 是一種強大的工具，可讓您瞭解程式和服務如何使用系統資源。</span><span class="sxs-lookup"><span data-stu-id="027c8-116">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="027c8-117">除了即時監控資源使用量之外，資源監視器也可協助分析無回應的處理常式、識別哪些應用程式正在使用檔案，以及控制程式和服務。</span><span class="sxs-lookup"><span data-stu-id="027c8-117">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="027c8-118">**可靠性分析元件** 是一個內建的代理程式，提供系統使用狀況與可靠性的詳細體驗資訊。</span><span class="sxs-lookup"><span data-stu-id="027c8-118">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="027c8-119">此資訊透過 WMI 介面公開，可供可擕式讀取器系統使用。</span><span class="sxs-lookup"><span data-stu-id="027c8-119">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="027c8-120">透過 WMI 介面公開可靠性分析元件，開發人員可以監視及分析應用程式，進而增強可靠性和效能。</span><span class="sxs-lookup"><span data-stu-id="027c8-120">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="027c8-121">**Windows Server 2008 R2** 使用內建的可靠性分析元件來計算可靠性索引，其可提供一段時間內整體系統使用量和穩定性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="027c8-121">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="027c8-122">可靠性分析元件也會持續追蹤可能會影響穩定性的任何重要變更，例如 Windows 更新和應用程式安裝。</span><span class="sxs-lookup"><span data-stu-id="027c8-122">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="027c8-123">Windows Server 2008 Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="027c8-123">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="027c8-124">Windows 可靠性和效能監視器是一種 MMC 嵌入式管理單元，結合了舊獨立工具的功能，包括效能記錄和警示、伺服器效能顧問和系統監視器。</span><span class="sxs-lookup"><span data-stu-id="027c8-124">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="027c8-125">它會提供圖形介面，以自訂效能資料收集和事件追蹤會話。</span><span class="sxs-lookup"><span data-stu-id="027c8-125">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="027c8-126">此外，它也包含可靠性監視器，也就是追蹤系統變更的 MMC 嵌入式管理單元，並比較系統穩定性的變化，並提供其關聯的圖形化視圖。</span><span class="sxs-lookup"><span data-stu-id="027c8-126">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="027c8-127">Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="027c8-127">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="027c8-128">雖然 Windows 可靠性和效能監視器會結合一些先前獨立工具（例如效能記錄和警示）和系統監視器與伺服器效能顧問的功能，但也會提供一些新功能給 Windows Server 2008 和 Windows Server 2008 R2，例如：</span><span class="sxs-lookup"><span data-stu-id="027c8-128">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="027c8-129">資料收集器集</span><span class="sxs-lookup"><span data-stu-id="027c8-129">Data Collector Sets</span></span>

  - <span data-ttu-id="027c8-130">資源檢視</span><span class="sxs-lookup"><span data-stu-id="027c8-130">Resource View</span></span>

  - <span data-ttu-id="027c8-131">可靠性監視器</span><span class="sxs-lookup"><span data-stu-id="027c8-131">Reliability Monitor</span></span>

  - <span data-ttu-id="027c8-132">用於建立記錄的嚮導與範本</span><span class="sxs-lookup"><span data-stu-id="027c8-132">Wizards and templates for creating logs</span></span>

<span data-ttu-id="027c8-133">**資料收集器集會將** 資料收集器群組成可重複使用的元素，以用於不同的效能監視案例。</span><span class="sxs-lookup"><span data-stu-id="027c8-133">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="027c8-134">在將一組資料收集器儲存為資料收集器集後，可透過單一屬性變更將作業（例如排程）套用至整個集。Windows 可靠性和效能監視器包含預設的資料收集器集範本，可協助系統管理員立即開始收集伺服器角色或監控案例特有的效能資料。</span><span class="sxs-lookup"><span data-stu-id="027c8-134">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="027c8-135">Windows 可靠性和效能監視器的首頁是新的 [ **資源 View** ] 畫面，可提供 CPU、磁片、網路及記憶體使用量的即時圖形概述。</span><span class="sxs-lookup"><span data-stu-id="027c8-135">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="027c8-136">透過展開每個受監視的元素，系統管理員便可識別哪些處理常式正在使用哪些資源。</span><span class="sxs-lookup"><span data-stu-id="027c8-136">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="027c8-137">在舊版 Windows 中，只有在工作管理員的有限表單中，才可取得處理常式特有的資料。</span><span class="sxs-lookup"><span data-stu-id="027c8-137">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="027c8-138">**可靠性監視器** 會計算系統穩定性指數，反映未預期的問題是否會降低系統的可靠性。</span><span class="sxs-lookup"><span data-stu-id="027c8-138">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="027c8-139">一段時間的穩定性索引圖表會快速識別發生問題的日期。</span><span class="sxs-lookup"><span data-stu-id="027c8-139">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="027c8-140">伴隨的系統穩定性報告提供詳細資料，可協助疑難排解可靠性降低的原因。</span><span class="sxs-lookup"><span data-stu-id="027c8-140">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="027c8-141">透過查看系統的變更 (安裝或移除應用程式、作業系統的更新，或新增或修改驅動程式) 並排存在失敗 (應用程式失敗、作業系統損毀或硬體失敗) ，您可以快速開發解決問題的策略。</span><span class="sxs-lookup"><span data-stu-id="027c8-141">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="027c8-142">現在可以透過 **嚮導介面**，將計數器新增至記錄檔並排程其開始、停止和持續時間。</span><span class="sxs-lookup"><span data-stu-id="027c8-142">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="027c8-143">此外，將此設定另存為範本，可讓系統管理員在其他電腦上收集相同的記錄，而不需重複資料收集器選取及排程處理常式。</span><span class="sxs-lookup"><span data-stu-id="027c8-143">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="027c8-144">效能記錄和警示功能已融入 Windows 可靠性和效能監視器中，以用於任何資料收集器集。</span><span class="sxs-lookup"><span data-stu-id="027c8-144">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

