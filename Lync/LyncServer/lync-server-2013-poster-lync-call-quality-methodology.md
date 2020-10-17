---
title: Lync Server 2013：標牌： Lync 通話品質方法
description: Lync Server 2013：標牌： Lync 通話品質方法。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0db34da35ce32d32aa00f10cd3523a0f508f8ffd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566329"
---
# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="a07d1-103">Lync Server 2013 中的 lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="a07d1-103">Lync Call Quality Methodology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a07d1-104">_**主題上次修改日期：** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="a07d1-104">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="a07d1-105">本文是 [Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841) 海報的隨附，您可以從下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="a07d1-105">This article is a companion to the [Lync Call Quality Methodology](https://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="a07d1-106">![描述 CQM 處理常式的海報](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 處理常式的海報")</span><span class="sxs-lookup"><span data-stu-id="a07d1-106">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="a07d1-107">您可以使用此海報來瞭解 CQM，這是 Lync 2013 和2010的通話品質方法，可協助您找出並消除影響包含企業語音功能之 Lync 實施之通話品質和使用者經驗的問題。</span><span class="sxs-lookup"><span data-stu-id="a07d1-107">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="a07d1-108">通話品質方法是一種新的疑難排解和服務管理架構，可更好地致力於改進 Lync 中的 enterprise voice 服務。</span><span class="sxs-lookup"><span data-stu-id="a07d1-108">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="a07d1-109">在本文中，您可深入瞭解 CQM、所監控的伺服器和解決方案種類，以及如何處理收集的遙測資料。</span><span class="sxs-lookup"><span data-stu-id="a07d1-109">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="a07d1-110">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="a07d1-110">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="a07d1-111">海報會說明下列方面：</span><span class="sxs-lookup"><span data-stu-id="a07d1-111">The poster explains the following areas:</span></span>

  - <span data-ttu-id="a07d1-112">何謂 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="a07d1-112">What is Lync CQM?</span></span>

  - <span data-ttu-id="a07d1-113">優先順序：執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="a07d1-113">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="a07d1-114">Pcd</span><span class="sxs-lookup"><span data-stu-id="a07d1-114">PCD</span></span>

  - <span data-ttu-id="a07d1-115">Managed/非管理</span><span class="sxs-lookup"><span data-stu-id="a07d1-115">Managed/Unmanaged</span></span>

  - <span data-ttu-id="a07d1-116">伺服器植物道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-116">The Server Plant Road</span></span>

  - <span data-ttu-id="a07d1-117">最後一個英里道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-117">The Last Mile Road</span></span>

  - <span data-ttu-id="a07d1-118">結束點道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-118">The End Points Road</span></span>

  - <span data-ttu-id="a07d1-119">服務管理</span><span class="sxs-lookup"><span data-stu-id="a07d1-119">Service Management</span></span>

  - <span data-ttu-id="a07d1-120">董事會遊戲規則</span><span class="sxs-lookup"><span data-stu-id="a07d1-120">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="a07d1-121">何謂 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="a07d1-121">What is Lync CQM?</span></span>

<span data-ttu-id="a07d1-122">通話品質方法是一種新的疑難排解和服務管理架構，可更好地致力於改進 Lync 中的 enterprise voice 服務。</span><span class="sxs-lookup"><span data-stu-id="a07d1-122">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="a07d1-123">當您使用 CQM 時，需要較低的工作量，以確保企業語音服務的通話品質和使用者滿意度。</span><span class="sxs-lookup"><span data-stu-id="a07d1-123">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="a07d1-124">在 [通話品質方法](https://go.microsoft.com/fwlink/p/?linkid=615208)中，CQM 更充分地說明。</span><span class="sxs-lookup"><span data-stu-id="a07d1-124">CQM is more fully explained in the [Call Quality Methodology](https://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="a07d1-125">本文和海報是該內容的摘要。</span><span class="sxs-lookup"><span data-stu-id="a07d1-125">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="a07d1-126">CQM 會將系統疑難排解細分為三個路徑或 "道路"。</span><span class="sxs-lookup"><span data-stu-id="a07d1-126">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="a07d1-127">這些是：伺服器植物道路，它會看一下伺服器及它們之間的連結、端點道路，看起來就像是用來用來進行通話的使用者裝置和媒體，最後一次的道路是用來處理傳統切換電話網絡通話的整合。</span><span class="sxs-lookup"><span data-stu-id="a07d1-127">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="a07d1-128">每個道路都會分成數個與特定區域或主題相關的區段，而且每個片段定義都是針對可接受的品質等級，採取動作以達成該品質階層，並將服務管理計畫放在保持品質層級，再繼續進行下一個主題。</span><span class="sxs-lookup"><span data-stu-id="a07d1-128">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="a07d1-129">海報會顯示 Lync CQM 做為三位玩家的董事會遊戲，每個玩家都會透過道路。</span><span class="sxs-lookup"><span data-stu-id="a07d1-129">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="a07d1-130">下載所含的卡片是用來模擬障礙，以通話必須克服的品質。</span><span class="sxs-lookup"><span data-stu-id="a07d1-130">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="a07d1-131">這三個路徑會包含目標的相關提示和建議，以及如何在遊戲中的實際應用程式中優先處理的優先順序指導方針，這三個道路都是以平行) 進行處理的 (。</span><span class="sxs-lookup"><span data-stu-id="a07d1-131">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="a07d1-132">CQM 在舊版 Lync 中的運作方式？</span><span class="sxs-lookup"><span data-stu-id="a07d1-132">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="a07d1-133">CQM 是 Lync 2013 的新功能，但大部分可以搭配用來搭配 Lync 2010 使用。</span><span class="sxs-lookup"><span data-stu-id="a07d1-133">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="a07d1-134">CQM 可能會使用 Microsoft Office Communicator 的程度，但這已經過測試，且不受支援。</span><span class="sxs-lookup"><span data-stu-id="a07d1-134">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="a07d1-135">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="a07d1-135">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="a07d1-136">優先順序：執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="a07d1-136">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="a07d1-137">CQM 的第一個步驟是執行每兩周的趨勢查詢，然後分析結果。</span><span class="sxs-lookup"><span data-stu-id="a07d1-137">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="a07d1-138">依最大的資料流程貢獻因素、最高不良的資料流程比率及受管理的區域，設定修正動作的優先順序， (您可以控制) 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-138">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="a07d1-139">如果 Audio/Video 的多重點控制項單位 (AV MCU) 或中繼查詢顯示結果不良，請從紅色或伺服器植物道路開始。</span><span class="sxs-lookup"><span data-stu-id="a07d1-139">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="a07d1-140">如果有線或無線查詢顯示結果不良，請從藍色或最近的道路開始。</span><span class="sxs-lookup"><span data-stu-id="a07d1-140">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="a07d1-141">如果 VPN 或外部查詢顯示結果不良，請從綠色或端點道路開始。</span><span class="sxs-lookup"><span data-stu-id="a07d1-141">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="a07d1-142">選擇開始的道路之後，請為每個區域 (Assert) 中定義目標，以符合該目標 (達成) ，然後執行程式以保持目標 (維護) 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-142">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="a07d1-143">您也可以將此標牌當做遊戲使用，以瞭解 CQM 背後的原則。</span><span class="sxs-lookup"><span data-stu-id="a07d1-143">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="a07d1-144">Pcd</span><span class="sxs-lookup"><span data-stu-id="a07d1-144">PCD</span></span>

<span data-ttu-id="a07d1-145">PreCall 診斷工具 (.PCD) 可協助您找出並診斷周邊網路中的問題 (QoE 資料庫不會收集 edge 或周邊網路) 上的資訊，同時也可疑難排解最後一個英里的連線。</span><span class="sxs-lookup"><span data-stu-id="a07d1-145">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="a07d1-146">這項工具既可以是 Windows 8 新式應用程式，也可以是 Windows 桌面應用程式 https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-146">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at https://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="a07d1-147">Managed/非管理</span><span class="sxs-lookup"><span data-stu-id="a07d1-147">Managed/Unmanaged</span></span>

<span data-ttu-id="a07d1-148">Lync Server 部署和網路基礎結構通常可分割為受管理和非管理的空間。</span><span class="sxs-lookup"><span data-stu-id="a07d1-148">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="a07d1-149">受管理的空間包含您整個內部有線網路和伺服器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="a07d1-149">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="a07d1-150">非管理的空間為無線基礎結構和外部網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="a07d1-150">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="a07d1-151">進行此項區分可提高資料的清晰度，並可協助您的組織專注于對使用者的語音及視頻品質有實實在在影響的工作負載。</span><span class="sxs-lookup"><span data-stu-id="a07d1-151">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="a07d1-152">如果呼叫是放在您 (擁有 (非) managed) 某些其他實體以外的基礎結構上，則使用者的品質期望會不同。</span><span class="sxs-lookup"><span data-stu-id="a07d1-152">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="a07d1-153">這並不是說無線使用者留下其專屬裝置，使其具備絕佳的 Lync 伺服器體驗。</span><span class="sxs-lookup"><span data-stu-id="a07d1-153">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="a07d1-154">在未管理的空間中提升語音品質需要您在受管理的空間中具有高品質。</span><span class="sxs-lookup"><span data-stu-id="a07d1-154">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="a07d1-155">無線 (Wi-Fi) 是否視為受管理或未受管理的空間是由您的組織所決定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-155">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="a07d1-156">實現狀況良好環境的技術在這兩個空白處是不同的解決方案。</span><span class="sxs-lookup"><span data-stu-id="a07d1-156">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="a07d1-157">伺服器植物道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-157">The Server Plant Road</span></span>

<span data-ttu-id="a07d1-158">「伺服器植物道路的第1部定址 Lync 實施中的實際伺服器。</span><span class="sxs-lookup"><span data-stu-id="a07d1-158">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="a07d1-159">收集有關伺服器本身及其在實施中之角色的 KHI 資料，並分析結果。</span><span class="sxs-lookup"><span data-stu-id="a07d1-159">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="a07d1-160">如果有必要採取行動，請更正發現的任何問題。</span><span class="sxs-lookup"><span data-stu-id="a07d1-160">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="a07d1-161">有關此主題的詳細資訊，請在 KHI 海報隨附的 [Lync Server 2013 中的重要狀況](lync-server-2013-poster-key-health-indicators.md) 指標一文仲介紹。</span><span class="sxs-lookup"><span data-stu-id="a07d1-161">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="a07d1-162">下一段是 AV MCU 伺服器和轉送伺服器之間的媒體資料流程。</span><span class="sxs-lookup"><span data-stu-id="a07d1-162">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="a07d1-163">請先決定資料流程閥值不良的目標。</span><span class="sxs-lookup"><span data-stu-id="a07d1-163">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="a07d1-164">不良的資料流程通常是 PacketLossRate \> .01 或 PacketLossRateMax \> 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-164">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="a07d1-165">另一個必要的目標是 PoorStreamsRatio \< 2%。</span><span class="sxs-lookup"><span data-stu-id="a07d1-165">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="a07d1-166">接下來，使用詳細的查詢來找出使用不良資料流程的 AVMCU 和轉送伺服器配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修復不良資料流程，以及為網路裝置定義最優或「黃金」設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-166">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="a07d1-167">若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。</span><span class="sxs-lookup"><span data-stu-id="a07d1-167">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="a07d1-168">接下來，檢查轉送伺服器和公用交換電話網路 (PSTN) 閘道之間的媒體資料流程。</span><span class="sxs-lookup"><span data-stu-id="a07d1-168">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="a07d1-169">請先決定資料流程閥值不良的目標。</span><span class="sxs-lookup"><span data-stu-id="a07d1-169">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="a07d1-170">不良的資料流程通常是 PacketLossRate \> .01 或 PacketLossRateMax \> 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-170">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="a07d1-171">另一個必要的目標是 PoorStreamsRatio \< 2%。</span><span class="sxs-lookup"><span data-stu-id="a07d1-171">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="a07d1-172">接下來，使用詳細的查詢來尋找具有不良資料流程的轉送伺服器和閘道配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修正不良的資料流程，以及為網路裝置定義最優或「黃金」設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-172">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="a07d1-173">若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。</span><span class="sxs-lookup"><span data-stu-id="a07d1-173">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="a07d1-174">最後，檢查您的 PSTN 閘道的健康情況計量。</span><span class="sxs-lookup"><span data-stu-id="a07d1-174">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="a07d1-175">識別顯示狀況的統計資料，並針對這些統計資料定義目標。</span><span class="sxs-lookup"><span data-stu-id="a07d1-175">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="a07d1-176">這裡不提供任何特定指導，因為可使用許多可能的閘道。</span><span class="sxs-lookup"><span data-stu-id="a07d1-176">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="a07d1-177">建立目標之後，視需要進行修正以取得目標;在此程式中，您可能會定義閘道的「黃金」或最佳設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-177">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="a07d1-178">若要維護您的成就，請執行程式及工具，以管理設定偏移，並報告新的問題範圍。</span><span class="sxs-lookup"><span data-stu-id="a07d1-178">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="a07d1-179">請注意，固件和軟體更新可能會變更您的設定，或會使您變更「黃金」設定的定義，所以請謹慎使用這些活動。</span><span class="sxs-lookup"><span data-stu-id="a07d1-179">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="a07d1-180">最後一個英里道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-180">The Last Mile Road</span></span>

<span data-ttu-id="a07d1-181">在用戶端連線到網路的兩種方式中，有線預期會提供最高的品質，而且必須是最後一個英里問題的初始焦點。</span><span class="sxs-lookup"><span data-stu-id="a07d1-181">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="a07d1-182">使用 CQM 有線查詢 (LastMile \_ 0 \_ 有線) 以及它所提供的不良資料流程比率資料。</span><span class="sxs-lookup"><span data-stu-id="a07d1-182">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="a07d1-183">建議您定義目標 PoorStreamsRatio \< 5% for sites with \> 300 資料流程) 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-183">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="a07d1-184">若要取得您的目標，請將從最差排序的子網修正為最佳，並執行 QoS。</span><span class="sxs-lookup"><span data-stu-id="a07d1-184">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="a07d1-185">在您優化有線連線的品質後，增強無線品質會變得更容易，因為無線基礎結構位於每個位置的有線核心。</span><span class="sxs-lookup"><span data-stu-id="a07d1-185">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="a07d1-186">具有良好有線品質的網站中的無線資料流程不良，必須依特定無線元件而歸對。</span><span class="sxs-lookup"><span data-stu-id="a07d1-186">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="a07d1-187">CQM 無線查詢 (LastMile \_ 1 \_ 無線) 會在日期範圍內運作，並且會傳回您環境中所有內部的無線資料流程，從 Lync 用戶端到或從會議服務器或轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="a07d1-187">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="a07d1-188">建議您定義目標 PoorStreamsRatio \< 5% for sites with \> 300 資料流程) 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-188">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="a07d1-189">若要取得您的目標，請將從最差排序的子網修正為最佳，並執行 QoS。</span><span class="sxs-lookup"><span data-stu-id="a07d1-189">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="a07d1-190">結束點道路</span><span class="sxs-lookup"><span data-stu-id="a07d1-190">The End Points Road</span></span>

<span data-ttu-id="a07d1-191">在與 Lync 搭配使用時，會以耳機和其他設備所知道的點，來開始查詢。</span><span class="sxs-lookup"><span data-stu-id="a07d1-191">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="a07d1-192">我們建議使用目標 AvgSendListen MOS \> 3.6，以實現具有超過100資料流程的執行。 ) 會識別有問題的裝置，並修正或取代，以實現目標。</span><span class="sxs-lookup"><span data-stu-id="a07d1-192">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="a07d1-193">接下來，檢查裝置或電腦處理音訊的使用者通話。</span><span class="sxs-lookup"><span data-stu-id="a07d1-193">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="a07d1-194">建議的目標品質度量為 AudioMicGlitchRate \< = 1。</span><span class="sxs-lookup"><span data-stu-id="a07d1-194">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="a07d1-195">當您識別使用者系統的最佳系統設定時，請定義包含驅動程式版本的「黃金」 PC 設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-195">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="a07d1-196">現在，檢查音訊資料流程從 Lync 端點系統取得的網路路徑，這可能會導致音訊品質不良。</span><span class="sxs-lookup"><span data-stu-id="a07d1-196">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="a07d1-197">如果音訊透過 VPN 連線，您可能會看到延遲問題。</span><span class="sxs-lookup"><span data-stu-id="a07d1-197">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="a07d1-198">若內部 Lync 用戶端無法建立直接媒體資料流程給兩方或對等通話的另一個內部 Lync 用戶端，它會回復至透過 Lync Edge server 轉送的路徑，進而導致遺失和抖動的可能性變得更高。</span><span class="sxs-lookup"><span data-stu-id="a07d1-198">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="a07d1-199">我們建議您透過 VPN 定義品質衡量值為0% 的媒體。</span><span class="sxs-lookup"><span data-stu-id="a07d1-199">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="a07d1-200">當您進行修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-200">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="a07d1-201">IP 封包可以使用傳輸控制通訊協定 (TCP) 或使用者資料包協定 (UDP) 。</span><span class="sxs-lookup"><span data-stu-id="a07d1-201">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="a07d1-202">TCP 是資料流程的最佳功能。</span><span class="sxs-lookup"><span data-stu-id="a07d1-202">TCP is optimal for data streams.</span></span> <span data-ttu-id="a07d1-203">UDP 是不需連線的，更有效率的媒體，因為 TCP 復原機制無法處理即時媒體的遺失。</span><span class="sxs-lookup"><span data-stu-id="a07d1-203">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="a07d1-204">Lync 一定會喜歡 UDP，但如果無法建立 UDP 會話，則會還原為 TCP。</span><span class="sxs-lookup"><span data-stu-id="a07d1-204">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="a07d1-205">透過 TCP 的媒體會話會顯示出品質不如透過 UDP 的情況。</span><span class="sxs-lookup"><span data-stu-id="a07d1-205">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="a07d1-206">我們建議您透過 TCP 的高品質定義來定義0% 連線。</span><span class="sxs-lookup"><span data-stu-id="a07d1-206">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="a07d1-207">當您進行修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。</span><span class="sxs-lookup"><span data-stu-id="a07d1-207">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="a07d1-208">服務管理</span><span class="sxs-lookup"><span data-stu-id="a07d1-208">Service Management</span></span>

<span data-ttu-id="a07d1-209">服務管理是 CQM 的結束狀態，及所有三個道路的目的地。</span><span class="sxs-lookup"><span data-stu-id="a07d1-209">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="a07d1-210">若要維持高水準的通話品質，請監視以下區域：</span><span class="sxs-lookup"><span data-stu-id="a07d1-210">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="a07d1-211">**使用者** -修復活動應顯示使用者滿意度的可衡量增加。</span><span class="sxs-lookup"><span data-stu-id="a07d1-211">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="a07d1-212">您可以依問題票證或其他意見反應機制來衡量這種情況。</span><span class="sxs-lookup"><span data-stu-id="a07d1-212">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="a07d1-213">您也可以發佈品質度量。</span><span class="sxs-lookup"><span data-stu-id="a07d1-213">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="a07d1-214">**Process** -定義 operationalize CQM 每日、每週及每月的處理常式。</span><span class="sxs-lookup"><span data-stu-id="a07d1-214">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="a07d1-215">在您對 (每日) 進行補救時，監控 rhythm 會在較高的頻率開始， (每月) 以穩定狀態移至較低頻率。</span><span class="sxs-lookup"><span data-stu-id="a07d1-215">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="a07d1-216">**工具** -識別用來測量和修正的工具。</span><span class="sxs-lookup"><span data-stu-id="a07d1-216">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="a07d1-217">您可能會發現自動化執行 CQM 查詢以支援您的程式是很有用的。</span><span class="sxs-lookup"><span data-stu-id="a07d1-217">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="a07d1-218">修復可能需要其他工具，以強制執行網元上的標準化設定或疑難排解不良資料流程中的遺失。</span><span class="sxs-lookup"><span data-stu-id="a07d1-218">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="a07d1-219">董事會遊戲規則</span><span class="sxs-lookup"><span data-stu-id="a07d1-219">Board Game Rules</span></span>

<span data-ttu-id="a07d1-220">您可以使用此標牌做為參考 CQM 的執行，也可以做為遊戲以練習概念。</span><span class="sxs-lookup"><span data-stu-id="a07d1-220">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="a07d1-221">若要播放，您需要 1 6 邊片及隨附的卡。</span><span class="sxs-lookup"><span data-stu-id="a07d1-221">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="a07d1-222">可在標準 Avery 5871 名片上列印的卡片可下載版本。</span><span class="sxs-lookup"><span data-stu-id="a07d1-222">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="a07d1-223">遊戲適用于3玩家。</span><span class="sxs-lookup"><span data-stu-id="a07d1-223">The game is for 3 players.</span></span> <span data-ttu-id="a07d1-224">玩家可使用三種路徑來達到所需的品質，並達到中心服務管理狀態：伺服器植物、端點及最後英里。</span><span class="sxs-lookup"><span data-stu-id="a07d1-224">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="a07d1-225">每個路徑會沿著您用來斷言品質目標的方式、達到目標，以及維護系統的一個方面而停止。</span><span class="sxs-lookup"><span data-stu-id="a07d1-225">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="a07d1-226">將卡片放在上述區域，然後再繪製5張牌。</span><span class="sxs-lookup"><span data-stu-id="a07d1-226">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="a07d1-227">回顧您已繪製的卡片，並將其放在相關的董事會區段。</span><span class="sxs-lookup"><span data-stu-id="a07d1-227">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="a07d1-228">每一部玩家會逐步移動名片上的各卡片，以判斷品質目標，達到這些目標，以及維護服務等級。</span><span class="sxs-lookup"><span data-stu-id="a07d1-228">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="a07d1-229">當所有玩家都達到中央服務管理狀態時，遊戲即完成。</span><span class="sxs-lookup"><span data-stu-id="a07d1-229">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="a07d1-230">隨遊戲卡下載提供更詳細的規則。</span><span class="sxs-lookup"><span data-stu-id="a07d1-230">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="a07d1-231">若要 **斷言** 品質目標，請複查適用于該目標的參數，並將您不會選擇接受的內容放在適當的狀態。</span><span class="sxs-lookup"><span data-stu-id="a07d1-231">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="a07d1-232">我們建議的起始點，但是您必須進行最後的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a07d1-232">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="a07d1-233">例外狀況是 KHI 資料，其中應使用 Microsoft 所建立的標準。</span><span class="sxs-lookup"><span data-stu-id="a07d1-233">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="a07d1-234">請參閱隨附的 KHI 海報。</span><span class="sxs-lookup"><span data-stu-id="a07d1-234">See the accompanying KHI poster.</span></span>

<span data-ttu-id="a07d1-235">若要在遊戲中 **取得** ，請使用提供的卡片取代 KHI 資料和系統查詢。</span><span class="sxs-lookup"><span data-stu-id="a07d1-235">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="a07d1-236">如果遊戲開始時您未繪製與指定的方位相關的卡片，您可以繼續過去。</span><span class="sxs-lookup"><span data-stu-id="a07d1-236">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="a07d1-237">如果有相關的卡片，請翻轉骰子。</span><span class="sxs-lookup"><span data-stu-id="a07d1-237">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="a07d1-238">如果您是以卡片上所指出的數位來擲出，表明您已成功。</span><span class="sxs-lookup"><span data-stu-id="a07d1-238">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="a07d1-239">如果您在指定的數位上進行擲出或移過，您必須從卡片組中畫出另一個卡片。</span><span class="sxs-lookup"><span data-stu-id="a07d1-239">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="a07d1-240">如果此卡片指出兩個以上的玩家必須滾出，必須全部順利滾。</span><span class="sxs-lookup"><span data-stu-id="a07d1-240">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="a07d1-241">若要在遊戲中 **維護** ，請進一步瞭解 Lync 環境的相關服務管理計畫。</span><span class="sxs-lookup"><span data-stu-id="a07d1-241">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a07d1-242">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a07d1-242">See Also</span></span>


[<span data-ttu-id="a07d1-243">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="a07d1-243">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="a07d1-244">主要健康情況指示器：維護狀況良好的 Lync 伺服器的基礎</span><span class="sxs-lookup"><span data-stu-id="a07d1-244">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="a07d1-245">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="a07d1-245">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

