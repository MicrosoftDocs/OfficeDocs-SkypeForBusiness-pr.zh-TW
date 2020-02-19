---
title: Lync Server 2013： 監視作業系統
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
ms.openlocfilehash: ea10d7dff41f310e41c1257fa858d0b5d9226bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134549"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="68636-102">Lync Server 2013 中的監視作業系統</span><span class="sxs-lookup"><span data-stu-id="68636-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68636-103">_**主題上次修改日期：** 2015年-01-26_</span><span class="sxs-lookup"><span data-stu-id="68636-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="68636-104">您必須監視效能的所有伺服器和 Lync Server 2013 中的元件。</span><span class="sxs-lookup"><span data-stu-id="68636-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="68636-105">很明顯地，下列其中一個最重要的元件是作業系統本身。</span><span class="sxs-lookup"><span data-stu-id="68636-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="68636-106">Lync Server 2013 支援 x64 版本的：</span><span class="sxs-lookup"><span data-stu-id="68636-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="68636-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="68636-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="68636-108">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="68636-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="68636-109">監視作業系統的最透明方法是使用 Windows Server 作業系統管理組件。</span><span class="sxs-lookup"><span data-stu-id="68636-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="68636-110">執行 Windows Server 2012、 Windows Server 2012 R2 和 Windows Server 2008 R2 的電腦提供基礎監視基本項目，例如效能、 健康情況及可用性。</span><span class="sxs-lookup"><span data-stu-id="68636-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="68636-111">藉由偵測、 警示，並自動回應重要事件及效能指標，這些管理組件減少問題的解決時間，並增加整體的可用性和正在執行 Windows Server 的系統的效能作業系統。</span><span class="sxs-lookup"><span data-stu-id="68636-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="68636-112">不同相關 Windows Server 管理組件的 System Center Operations Manager，於下列系統工具和資源可以用來監視健康狀況的作業系統 （根據作業系統的版本）。</span><span class="sxs-lookup"><span data-stu-id="68636-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="68636-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="68636-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="68636-114">Windows Server 2008 R2 包括下列額外的功能和工具，以協助系統管理員使用基本的作業系統監控與管理：</span><span class="sxs-lookup"><span data-stu-id="68636-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="68636-115">**Windows 資源監視器**是功能強大的工具，了解如何使用系統資源的程序和服務。</span><span class="sxs-lookup"><span data-stu-id="68636-115">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services.</span></span> <span data-ttu-id="68636-116">除了監視即時的資源使用量，資源監視器可協助分析回應程序，請識別哪些應用程式正在使用的檔案，以及控制程序和服務。</span><span class="sxs-lookup"><span data-stu-id="68636-116">In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="68636-117">**可靠性分析元件**是內建代理程式上，提供詳細的經驗資訊系統使用狀況和可靠性。</span><span class="sxs-lookup"><span data-stu-id="68636-117">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability.</span></span> <span data-ttu-id="68636-118">這項資訊公開 WMI 介面，以使其可耗用透過可攜式讀者系統。</span><span class="sxs-lookup"><span data-stu-id="68636-118">This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems.</span></span> <span data-ttu-id="68636-119">藉由透過 WMI 介面公開可靠性分析元件，開發人員可以監視及分析應用程式、 增加可靠性和效能。</span><span class="sxs-lookup"><span data-stu-id="68636-119">By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="68636-120">**Windows Server 2008 R2**使用內建的可靠性分析元件來計算可靠性索引中，提供一段時間整體系統使用狀況] 和 [穩定性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="68636-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="68636-121">可靠性分析元件也會追蹤的系統，可能會影響所展現的穩定性，例如 Windows 更新和應用程式安裝任何重要變更。</span><span class="sxs-lookup"><span data-stu-id="68636-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="68636-122">Windows Server 2008 Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="68636-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="68636-123">Windows 可靠性和效能監視器是 MMC 嵌入式管理單元，結合了前一個獨立的工具，包括效能記錄檔和提醒、 伺服器效能顧問，以及系統監視器的功能。</span><span class="sxs-lookup"><span data-stu-id="68636-123">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor.</span></span> <span data-ttu-id="68636-124">它提供圖形化介面自訂效能資料收集和事件追蹤工作階段。</span><span class="sxs-lookup"><span data-stu-id="68636-124">It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="68636-125">它還包含可靠性監視器] MMC 嵌入式管理單元中，系統會追蹤的變更，然後比較它們變更在系統所展現的穩定性，並提供其關聯的一種圖形檢視。</span><span class="sxs-lookup"><span data-stu-id="68636-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="68636-126">Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="68636-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="68636-127">Windows 可靠性和效能監視器結合例如效能記錄檔及警示和系統監視器和伺服器效能顧問某些離職獨立工具的功能，它還提供一些新功能至 Windows Server 2008 和Windows Server 2008 R2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="68636-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="68636-128">資料收集器集合工具</span><span class="sxs-lookup"><span data-stu-id="68636-128">Data Collector Sets</span></span>

  - <span data-ttu-id="68636-129">[資源] 檢視</span><span class="sxs-lookup"><span data-stu-id="68636-129">Resource View</span></span>

  - <span data-ttu-id="68636-130">可靠性監視器</span><span class="sxs-lookup"><span data-stu-id="68636-130">Reliability Monitor</span></span>

  - <span data-ttu-id="68636-131">精靈和範本來建立記錄檔</span><span class="sxs-lookup"><span data-stu-id="68636-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="68636-132">**資料收集器集合工具**資料收集器群組到可重複使用元素搭配不同的效能監視案例。</span><span class="sxs-lookup"><span data-stu-id="68636-132">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios.</span></span> <span data-ttu-id="68636-133">一群資料收集器儲存為資料收集器集合工具之後，作業，例如排程可以套用至整個集透過單一屬性變更。Windows 可靠性和效能監視器包含預設資料收集器集合範本，可協助系統管理員開始立即收集效能資料的特定伺服器角色或監視案例。</span><span class="sxs-lookup"><span data-stu-id="68636-133">After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="68636-134">[首頁] 頁面上的 Windows 可靠性和效能監視器是新的 **[資源] 檢視**畫面，可提供 CPU、 磁碟、 網路和記憶體使用量的即時圖形化概觀。</span><span class="sxs-lookup"><span data-stu-id="68636-134">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage.</span></span> <span data-ttu-id="68636-135">藉由展開每個這些受監視的項目，系統管理員可以識別哪一個程序所使用的資源。</span><span class="sxs-lookup"><span data-stu-id="68636-135">By expanding each of these monitored elements, system administrators can identify which processes are using which resources.</span></span> <span data-ttu-id="68636-136">在舊版 Windows 中，此即時、 程序特有的資料是只能在有限的表單在 [工作管理員] 中。</span><span class="sxs-lookup"><span data-stu-id="68636-136">In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="68636-137">**可靠性監視器**計算反映未預期的問題是否降低系統的可靠性系統所展現的穩定性索引。</span><span class="sxs-lookup"><span data-stu-id="68636-137">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system.</span></span> <span data-ttu-id="68636-138">經過一段時間的穩定性索引圖形快速識別問題開始發生時的日期。</span><span class="sxs-lookup"><span data-stu-id="68636-138">A graph of the Stability Index over time quickly identifies dates when issues began to occur.</span></span> <span data-ttu-id="68636-139">隨附的系統所展現的穩定性報告提供詳細資料] 來協助疑難排解降低可靠性的原因。</span><span class="sxs-lookup"><span data-stu-id="68636-139">The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability.</span></span> <span data-ttu-id="68636-140">藉由檢視變更為並排失敗 （應用程式故障、 作業系統損毀或硬體故障），系統 （安裝或移除應用程式、 更新作業系統，或是新增或修改驅動程式） 的策略解決問題可以快速地開發。</span><span class="sxs-lookup"><span data-stu-id="68636-140">By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="68636-141">新增的計數器，以記錄檔及排程其開始、 停止]，並持續時間現在可透過**精靈介面**來執行。</span><span class="sxs-lookup"><span data-stu-id="68636-141">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**.</span></span> <span data-ttu-id="68636-142">此外，這種組態儲存為範本可讓系統管理員收集相同的記錄在其他電腦上沒有重複的資料收集器選取範圍和排程處理程序。</span><span class="sxs-lookup"><span data-stu-id="68636-142">In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes.</span></span> <span data-ttu-id="68636-143">效能記錄檔及警示功能會併入 「 Windows 可靠性和效能監視器搭配任何資料收集器集合工具。</span><span class="sxs-lookup"><span data-stu-id="68636-143">Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

