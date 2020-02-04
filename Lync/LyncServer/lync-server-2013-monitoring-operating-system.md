---
title: Lync Server 2013：監控作業系統
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
ms.openlocfilehash: 42ac03f61fca5717d279d39e703a8ffa97e8c2cf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-operating-system-in-lync-server-2013"></a><span data-ttu-id="88fb2-102">Lync Server 2013 中的監控作業系統</span><span class="sxs-lookup"><span data-stu-id="88fb2-102">Monitoring operating system in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88fb2-103">_**主題上次修改日期：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="88fb2-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="88fb2-104">您必須監視 Lync Server 2013 中所有伺服器與元件的效能。</span><span class="sxs-lookup"><span data-stu-id="88fb2-104">You must monitor the performance of all servers and components in the Lync Server 2013.</span></span> <span data-ttu-id="88fb2-105">很明顯地，其中一個最重要的元件就是作業系統本身。</span><span class="sxs-lookup"><span data-stu-id="88fb2-105">Obviously, one of the most important components is the operating system itself.</span></span> <span data-ttu-id="88fb2-106">Lync Server 2013 支援 x64 版本的：</span><span class="sxs-lookup"><span data-stu-id="88fb2-106">Lync Server 2013 supports x64 editions of:</span></span>

  - <span data-ttu-id="88fb2-107">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="88fb2-107">Windows Server 2008 R2</span></span>

  - <span data-ttu-id="88fb2-108">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="88fb2-108">Windows Server 2012 and Windows Server 2012 R2</span></span>

<span data-ttu-id="88fb2-109">若要監視作業系統，最透明的方法是使用 Windows Server 作業系統管理套件。</span><span class="sxs-lookup"><span data-stu-id="88fb2-109">The most transparent way to monitor an operating system is by using Windows Server Operating System Management Pack.</span></span> <span data-ttu-id="88fb2-110">它提供執行 Windows Server 2012、Windows Server 2012 R2 和 Windows Server 2008 R2 之電腦的效能、健康情況及可用性等基本監視基礎。</span><span class="sxs-lookup"><span data-stu-id="88fb2-110">It provides the fundamental monitoring basics, such as performance, health, and availability for computers that are running Windows Server 2012, Windows Server 2012 R2, and Windows Server 2008 R2.</span></span>

<span data-ttu-id="88fb2-111">透過檢測、觸發及自動回應重要的事件和效能指標，這些管理套件減少了問題的解決時間，並增加執行 Windows Server 的系統的整體可用性與效能作業系統。</span><span class="sxs-lookup"><span data-stu-id="88fb2-111">By detecting, alerting, and automatically responding to important events and performance indicators, these management packs reduce resolution times for issues and increase the overall availability and performance of systems that are running the Windows Server operating systems.</span></span>

<span data-ttu-id="88fb2-112">除了適用于 System Center Operations Manager 的相關 Windows Server management pack 之外，下列系統工具和資源可用於監視作業系統的健康情況（視作業系統版本而定）。</span><span class="sxs-lookup"><span data-stu-id="88fb2-112">Apart from relevant Windows Server management packs for System Center Operations Manager, the following system tools and resources can be used to monitor the health of the operating system (depending on the operating system version).</span></span>

<div>

## <a name="windows-server2008r2"></a><span data-ttu-id="88fb2-113">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="88fb2-113">Windows Server 2008 R2</span></span>

<span data-ttu-id="88fb2-114">Windows Server 2008 R2 包含下列其他功能與工具，可協助系統管理員進行基本的作業系統監視與管理：</span><span class="sxs-lookup"><span data-stu-id="88fb2-114">Windows Server 2008 R2 includes the following additional features and tools to help administrators with basic operating system monitoring and management:</span></span>

  - <span data-ttu-id="88fb2-p103">**Windows 資源監視器**  是一款強大的工具，可讓您透過程序和服務瞭解系統資源的使用情況。除了即時監控資源使用量之外，資源監視器還能協助分析無回應的程序、找出哪些應用程式在使用檔案，並控制程序與服務。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p103">**Windows Resource Monitor** is a powerful tool for understanding how system resources are used by processes and services. In addition to monitoring resource usage in real time, a Resource Monitor can help analyze unresponsive processes, identify which applications are using files, and control processes and services.</span></span>

  - <span data-ttu-id="88fb2-p104">**可靠性分析元件** 是一款隨附的代理程式，可提供系統使用量和可靠性的詳細體驗資訊。這項資訊會透過 WMI 介面公開，讓可攜式讀取器系統使用。透過 WMI 介面公開可靠性分析元件，開發人員就能監控並分析應用程式，增加可靠性和效能。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p104">**Reliability Analysis Component** is an in-box agent that provides detailed experience information on system usage and reliability. This information is exposed through a WMI interface to make it available for consumption by Portable Readers Systems. By exposing Reliability Analysis Component through a WMI interface, developers can monitor and analyze applications, increasing reliability and performance.</span></span>

  - <span data-ttu-id="88fb2-120">**Windows Server 2008 R2**使用內建的可靠性分析元件來計算可靠性索引，這會提供總體系統使用方式及時間的穩定性資訊。</span><span class="sxs-lookup"><span data-stu-id="88fb2-120">**Windows Server 2008 R2** uses the built-in Reliability Analysis Component to calculate a reliability index, which provides information about overall system usage and stability over time.</span></span> <span data-ttu-id="88fb2-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span><span class="sxs-lookup"><span data-stu-id="88fb2-121">The Reliability Analysis Component also keeps track of any important changes to the system that are likely to influence stability, such as Windows updates and application installations.</span></span>

</div>

<div>

## <a name="windows-server2008-windows-reliability-and-performance-monitor"></a><span data-ttu-id="88fb2-122">Windows Server 2008 Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="88fb2-122">Windows Server 2008 Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="88fb2-p106">Windows 可靠性和效能監視器是一款 MMC 嵌入式管理單元，結合了先前的獨立工具的功能，包括效能記錄和警示、伺服器效能顧問及系統監視器。其提供圖形介面供自訂效能資料收集和事件追蹤工作階段。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p106">Windows Reliability and Performance Monitor is an MMC Snap-in that combines the functionality of previous stand-alone tools including Performance Logs and Alerts, Server Performance Advisor, and System Monitor. It provides a graphical interface for customizing performance data collection and Event Trace Sessions.</span></span>

<span data-ttu-id="88fb2-125">其也包含可靠性監視器，這是一款 MMC 嵌入式管理單元，可追蹤系統變更並與系統穩定性的變更作比較，並提供關係圖檢視。</span><span class="sxs-lookup"><span data-stu-id="88fb2-125">It also includes Reliability Monitor, an MMC Snap-in that tracks changes to the system and compares them to changes in system stability, and it provides a graphical view of their relationship.</span></span>

</div>

<div>

## <a name="windows-reliability-and-performance-monitor"></a><span data-ttu-id="88fb2-126">Windows 可靠性和效能監視器</span><span class="sxs-lookup"><span data-stu-id="88fb2-126">Windows Reliability and Performance Monitor</span></span>

<span data-ttu-id="88fb2-127">雖然 Windows 可靠性和效能監視器結合了一些舊版獨立工具（例如效能記錄和警報）的功能，以及系統監視器和伺服器效能審察程式，但它也提供一些新功能給 Windows Server 2008，並Windows Server 2008 R2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="88fb2-127">While Windows Reliability and Performance Monitor combine functionalities of some former stand-alone tools such as Performance Logs and Alerts, and System Monitor and Server Performance Advisor, it also provides some new functionality to Windows Server 2008 and Windows Server 2008 R2, such as the following:</span></span>

  - <span data-ttu-id="88fb2-128">資料收集器集</span><span class="sxs-lookup"><span data-stu-id="88fb2-128">Data Collector Sets</span></span>

  - <span data-ttu-id="88fb2-129">資源檢視</span><span class="sxs-lookup"><span data-stu-id="88fb2-129">Resource View</span></span>

  - <span data-ttu-id="88fb2-130">可靠性監視器</span><span class="sxs-lookup"><span data-stu-id="88fb2-130">Reliability Monitor</span></span>

  - <span data-ttu-id="88fb2-131">建立記錄的精靈和範本</span><span class="sxs-lookup"><span data-stu-id="88fb2-131">Wizards and templates for creating logs</span></span>

<span data-ttu-id="88fb2-p107">**資料收集器集**會將資料收集器分組成可重複使用的元素，以搭配其他效能監控案例使用。將資料收集器的群組儲存為資料收集器集之後，像是排程這類作業，只要變更單一屬性就能套用至整個集。Windows 可靠性和效能監視器包含預設的資料收集器集範本，可協助系統管理員立即開始收集對伺服器角色或監控案例特定的效能資料。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p107">**Data Collector Set** groups data collectors into reusable elements for use with different performance monitoring scenarios. After a group of data collectors are stored as a Data Collector Set, operations such as scheduling can be applied to the whole set through a single property change.Windows Reliability and Performance Monitor includes default Data Collector Set templates to help system administrators begin immediately collecting performance data that is specific to a server role or monitoring scenario.</span></span>

<span data-ttu-id="88fb2-p108">Windows 可靠性和效能監視器的首頁是全新的**資源檢視**畫面，其中提供 CPU、磁碟、網路和記憶體使用量的即時圖形概觀。展開每個監控的元素之後，系統管理員就能找出哪些程序在使用哪些資源。在舊版 Windows 中，這項即時的程序特定資料於 [工作管理員] 中為限定使用的。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p108">The home page of Windows Reliability and Performance Monitor is the new **Resource View** screen, which provides a real-time graphical overview of CPU, disk, network, and memory usage. By expanding each of these monitored elements, system administrators can identify which processes are using which resources. In earlier versions of Windows, this real-time, process-specific data was available only in limited form in Task Manager.</span></span>

<span data-ttu-id="88fb2-p109">**可靠性監視器** 會計算系統穩定性指數，以反映出未預期的問題是否降低系統的可靠性。隨時間的穩定性指數圖表可快速找出開始發生問題的日期。隨附的系統穩定性報告則可提供詳細資料，以協助疑難排解降低可靠性的原因。透過並行檢視系統變更 (安裝或移除應用程式、更新作業系統或新增或修改驅動程式) 和故障 (應用程式故障、作業系統當機或硬體故障) 情形，就能快速制定解決問題的策略。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p109">**Reliability Monitor** calculates a System Stability Index that reflects whether unexpected issues reduced the reliability of the system. A graph of the Stability Index over time quickly identifies dates when issues began to occur. The accompanying System Stability Report provides details to help troubleshoot the cause of reduced reliability. By viewing changes to the system (installation or removal of applications, updates to the operating system, or addition or modification of drivers) side by side with failures (application failures, operating system crashes, or hardware failures), a strategy for addressing the issues can be developed quickly.</span></span>

<span data-ttu-id="88fb2-p110">將計數器新增至記錄檔並排程其開始、停止和持續期間等這些動作，現在可透過**精靈介面**來執行。除此之外，將此設定另存為範本還能讓系統管理員在其他電腦上收集相同的記錄，而不必重複資料收集器選擇和排程程序。效能記錄和警示功能已併入 Windows 可靠性和效能監視器中，可搭配任何資料收集器集使用。</span><span class="sxs-lookup"><span data-stu-id="88fb2-p110">Adding counters to log files and scheduling their start, stop, and duration can now be performed through a **Wizard interface**. In addition, saving this configuration as a template enables system administrators to collect the same log on other computers without repeating the data collector selection and scheduling processes. Performance Logs and Alerts features were incorporated into the Windows Reliability and Performance Monitor for use with any Data Collector Set.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

