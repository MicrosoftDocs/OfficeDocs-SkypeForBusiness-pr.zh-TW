---
title: Lync Server 2013：標牌： Lync 通話品質方法
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
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724973"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="33e5b-102">Lync Server 2013 中的 lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="33e5b-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33e5b-103">_**主題上次修改日期：** 2016-06-24_</span><span class="sxs-lookup"><span data-stu-id="33e5b-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="33e5b-104">本文隨附于[Lync 通話品質方法](http://go.microsoft.com/fwlink/?linkid=391841)海報，您可以從下載中心下載它。</span><span class="sxs-lookup"><span data-stu-id="33e5b-104">This article is a companion to the [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="33e5b-105">![描述 CQM 程序的海報](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "描述 CQM 程序的海報")</span><span class="sxs-lookup"><span data-stu-id="33e5b-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="33e5b-106">您可以使用此海報來瞭解 CQM，這是 Lync 2013 和2010的通話品質方法，可協助您找到並消除影響 Lync 實現中包含企業語音功能之通話品質與使用者體驗的問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="33e5b-107">通話品質方法是一種新的疑難排解與服務管理架構，可讓您更好地專注于在 Lync 中改善企業語音服務。</span><span class="sxs-lookup"><span data-stu-id="33e5b-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="33e5b-108">在本文中，您可以深入瞭解 CQM、所監視的伺服器和解決方案類型，以及如何處理收集的遙測資料。</span><span class="sxs-lookup"><span data-stu-id="33e5b-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="33e5b-109">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="33e5b-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="33e5b-110">海報說明下欄區域：</span><span class="sxs-lookup"><span data-stu-id="33e5b-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="33e5b-111">什麼是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="33e5b-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="33e5b-112">優先順序：執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="33e5b-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="33e5b-113">PCD</span><span class="sxs-lookup"><span data-stu-id="33e5b-113">PCD</span></span>

  - <span data-ttu-id="33e5b-114">Managed/非託管</span><span class="sxs-lookup"><span data-stu-id="33e5b-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="33e5b-115">伺服器植物道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-115">The Server Plant Road</span></span>

  - <span data-ttu-id="33e5b-116">最後一英里的道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-116">The Last Mile Road</span></span>

  - <span data-ttu-id="33e5b-117">端點道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-117">The End Points Road</span></span>

  - <span data-ttu-id="33e5b-118">服務管理</span><span class="sxs-lookup"><span data-stu-id="33e5b-118">Service Management</span></span>

  - <span data-ttu-id="33e5b-119">棋盤遊戲規則</span><span class="sxs-lookup"><span data-stu-id="33e5b-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="33e5b-120">什麼是 Lync CQM？</span><span class="sxs-lookup"><span data-stu-id="33e5b-120">What is Lync CQM?</span></span>

<span data-ttu-id="33e5b-121">通話品質方法是一種新的疑難排解與服務管理架構，可讓您更好地專注于在 Lync 中改善企業語音服務。</span><span class="sxs-lookup"><span data-stu-id="33e5b-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="33e5b-122">當您使用 CQM 時，需要較少的精力，以確保通話品質與企業語音服務的使用者滿意度。</span><span class="sxs-lookup"><span data-stu-id="33e5b-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="33e5b-123">CQM 在[通話品質方法](http://go.microsoft.com/fwlink/p/?linkid=615208)中會有更完整的說明。</span><span class="sxs-lookup"><span data-stu-id="33e5b-123">CQM is more fully explained in the [Call Quality Methodology](http://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="33e5b-124">本文和海報都是該內容的摘要。</span><span class="sxs-lookup"><span data-stu-id="33e5b-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="33e5b-125">CQM 會將系統疑難排解分解為三個路徑或 "道路"。</span><span class="sxs-lookup"><span data-stu-id="33e5b-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="33e5b-126">這些是： [伺服器植物] 道路，會在伺服器和連結之間的連結上，[端點道路] 會顯示使用者裝置和用來進行通話的媒體，以及可解決傳統交換電話網絡通話的問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="33e5b-127">每個道路都分為數個與特定區域或主題有關的區段，每個區段定義都會針對可接受的品質等級進行，採取行動來達到該品質等級，並將服務管理方案納入維護該品質等級，然後再移至下一個主題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="33e5b-128">海報提供 Lync CQM 做為三台玩家的棋盤遊戲，每個玩家都會透過其中一個道路進行。</span><span class="sxs-lookup"><span data-stu-id="33e5b-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="33e5b-129">下載所含的卡片是用來模擬障礙，以進行必須克服的通話品質。</span><span class="sxs-lookup"><span data-stu-id="33e5b-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="33e5b-130">您可以在三個路徑中包含有關目標及如何取得它們的提示與建議，以及優先順序指導方針，讓您在實際的應用程式中先開始進行，並以平行的方式來處理三個道路。</span><span class="sxs-lookup"><span data-stu-id="33e5b-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="33e5b-131">CQM 在舊版 Lync 中的運作方式為何？</span><span class="sxs-lookup"><span data-stu-id="33e5b-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="33e5b-132">CQM 是 Lync 2013 的新功能，但大部分都可以調整為與 Lync 2010 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="33e5b-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="33e5b-133">CQM 可能會在 Microsoft Office Communicator 上發揮作用，但這是經過測試且不受支援。</span><span class="sxs-lookup"><span data-stu-id="33e5b-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="33e5b-134">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="33e5b-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="33e5b-135">優先順序：執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="33e5b-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="33e5b-136">CQM 中的第一個步驟是執行兩周的每個趨勢查詢，然後分析結果。</span><span class="sxs-lookup"><span data-stu-id="33e5b-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="33e5b-137">依最大的資料流程參與者、最高不良的資料流程比率，以及受管理的區域（您所控制的）來確定修正動作的優先順序。</span><span class="sxs-lookup"><span data-stu-id="33e5b-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="33e5b-138">如果音訊/視頻多重點控制單位（AV MCU）或轉送查詢顯示的結果不佳，請從紅色或伺服器植物道路開始。</span><span class="sxs-lookup"><span data-stu-id="33e5b-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="33e5b-139">如果有線或無線查詢顯示的結果不佳，請從藍色或最後一個英里道路開始。</span><span class="sxs-lookup"><span data-stu-id="33e5b-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="33e5b-140">如果 VPN 或外部查詢顯示的結果不佳，請從綠色或終點道路開始。</span><span class="sxs-lookup"><span data-stu-id="33e5b-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="33e5b-141">在您選擇開始使用的道路之後，為每一個區域定義一個目標（Assert）、工作以符合該目標（完成），然後執行程式來維持目標（維護）。</span><span class="sxs-lookup"><span data-stu-id="33e5b-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="33e5b-142">您也可以使用這個標牌做為遊戲，瞭解 CQM 背後的原則。</span><span class="sxs-lookup"><span data-stu-id="33e5b-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="33e5b-143">PCD</span><span class="sxs-lookup"><span data-stu-id="33e5b-143">PCD</span></span>

<span data-ttu-id="33e5b-144">PreCall 診斷工具（PCD）可協助您找出並診斷周邊網路中的問題（QoE 資料庫不會在您的邊緣或周邊網路上收集資訊），也可讓您在最後一個英里中針對連線進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="33e5b-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="33e5b-145">此工具既可以是 Windows 8 新式 App，也可在 Windows 桌面應用程式http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88中使用。</span><span class="sxs-lookup"><span data-stu-id="33e5b-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="33e5b-146">Managed/非託管</span><span class="sxs-lookup"><span data-stu-id="33e5b-146">Managed/Unmanaged</span></span>

<span data-ttu-id="33e5b-147">Lync Server 部署和網路基礎結構通常可以劃分成受管理且未受管理的空間。</span><span class="sxs-lookup"><span data-stu-id="33e5b-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="33e5b-148">受管理的空間包括您整個內部有線網路和伺服器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="33e5b-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="33e5b-149">未受管理的空間是無線結構和外部網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="33e5b-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="33e5b-150">如此一來，就能增加資料的明晰性，並協助貴組織將重點放在對使用者的語音及視頻品質有顯著影響的工作負載上。</span><span class="sxs-lookup"><span data-stu-id="33e5b-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="33e5b-151">如果將呼叫放在您所擁有（受管理）與部分其他實體（非託管）控制的基礎結構中，使用者會有不同的品質預期。</span><span class="sxs-lookup"><span data-stu-id="33e5b-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="33e5b-152">這並不表示無線使用者已離開其自己的裝置，以提供絕佳的 Lync 伺服器體驗。</span><span class="sxs-lookup"><span data-stu-id="33e5b-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="33e5b-153">在非託管空間中改善語音品質，需要您在受管理的空間中擁有高品質。</span><span class="sxs-lookup"><span data-stu-id="33e5b-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="33e5b-154">是否認為無線（Wi-fi）是由您的組織決定。</span><span class="sxs-lookup"><span data-stu-id="33e5b-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="33e5b-155">在這兩個空間中，達到良好環境的技巧會有所不同，就像使用這些方案一樣。</span><span class="sxs-lookup"><span data-stu-id="33e5b-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="33e5b-156">伺服器植物道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-156">The Server Plant Road</span></span>

<span data-ttu-id="33e5b-157">伺服器工廠中的第1區段會解決 Lync 實現中的實際伺服器。</span><span class="sxs-lookup"><span data-stu-id="33e5b-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="33e5b-158">在實施中收集伺服器本身及其角色的 KHI 資料，並分析結果。</span><span class="sxs-lookup"><span data-stu-id="33e5b-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="33e5b-159">如果有保修措施，請修正發現的任何問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="33e5b-160">有關本主題的詳細資訊，請參閱 KHI 海報隨附的[Lync Server 2013 中的主要健康情況指示](lync-server-2013-poster-key-health-indicators.md)文。</span><span class="sxs-lookup"><span data-stu-id="33e5b-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="33e5b-161">下一個區段是在 AV MCU 伺服器與中繼伺服器之間的媒體資料流程。</span><span class="sxs-lookup"><span data-stu-id="33e5b-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="33e5b-162">首先，決定您的目標是否有不佳的資料流程閥值。</span><span class="sxs-lookup"><span data-stu-id="33e5b-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="33e5b-163">較差的資料流程通常\>是 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="33e5b-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="33e5b-164">另一個預期的目標\<是 PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="33e5b-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="33e5b-165">接著，使用詳細的查詢來找出含不良資料流程的 AVMCU 和轉送伺服器配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修正不正確的資料流程，以及為網路定義最佳或「黃金」設定設備.</span><span class="sxs-lookup"><span data-stu-id="33e5b-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="33e5b-166">若要維持您的成就，請執行流程與工具來管理設定的偏移，並報告新的問題區域。</span><span class="sxs-lookup"><span data-stu-id="33e5b-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="33e5b-167">接著，請檢查在中繼伺服器與公用交換電話網絡（PSTN）閘道之間的媒體資料流程。</span><span class="sxs-lookup"><span data-stu-id="33e5b-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="33e5b-168">首先，決定您的目標是否有不佳的資料流程閥值。</span><span class="sxs-lookup"><span data-stu-id="33e5b-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="33e5b-169">較差的資料流程通常\>是 PacketLossRate .01 \>或 PacketLossRateMax。</span><span class="sxs-lookup"><span data-stu-id="33e5b-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="33e5b-170">另一個預期的目標\<是 PoorStreamsRatio 2%。</span><span class="sxs-lookup"><span data-stu-id="33e5b-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="33e5b-171">接著，使用詳細的查詢來找出具有不良資料流程的中繼伺服器和閘道配對、調查不良資料流程的原因、查看不良資料流程路徑中的網路設備、修正不良資料流程，以及為網路定義最佳或「黃金」設定設備.</span><span class="sxs-lookup"><span data-stu-id="33e5b-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="33e5b-172">若要維持您的成就，請執行流程與工具來管理設定的偏移，並報告新的問題區域。</span><span class="sxs-lookup"><span data-stu-id="33e5b-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="33e5b-173">最後，請檢查您 PSTN 閘道的健康情況指標。</span><span class="sxs-lookup"><span data-stu-id="33e5b-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="33e5b-174">找出顯示健康情況的統計資料，並針對它們定義目標。</span><span class="sxs-lookup"><span data-stu-id="33e5b-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="33e5b-175">此處未提供任何特定指導方針，因為有許多可能的閘道可供使用。</span><span class="sxs-lookup"><span data-stu-id="33e5b-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="33e5b-176">建立目標之後，請視需要修正以達到目標;在此程式中，您可能會定義閘道的 "金色" 或最佳配置。</span><span class="sxs-lookup"><span data-stu-id="33e5b-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="33e5b-177">若要維持您的成就，請執行流程與工具來管理設定的偏移，並報告新的問題區域。</span><span class="sxs-lookup"><span data-stu-id="33e5b-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="33e5b-178">請注意，固件和軟體更新可能會改變您的設定，或讓您變更「黃金」設定的定義，所以請小心地進行這些動作。</span><span class="sxs-lookup"><span data-stu-id="33e5b-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="33e5b-179">最後一英里的道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-179">The Last Mile Road</span></span>

<span data-ttu-id="33e5b-180">在用戶端連線到網路的兩種方式中，有線預期會提供最高品質，而且必須是您最後一個取得英里問題的初始焦點。</span><span class="sxs-lookup"><span data-stu-id="33e5b-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="33e5b-181">使用 CQM 有線查詢（LastMile\_0\_有線）以及它提供的不良資料流程比率資料。</span><span class="sxs-lookup"><span data-stu-id="33e5b-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="33e5b-182">我們建議您為含\< \> 300 串流的網站定義目標 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="33e5b-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="33e5b-183">若要取得您的目標，請將從最差訂購的子網修正成最佳，並實施 QoS。</span><span class="sxs-lookup"><span data-stu-id="33e5b-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="33e5b-184">在您優化有線連線品質之後，改善無線品質會變得更容易，因為無線基礎結構在每個位置放在有線核心中。</span><span class="sxs-lookup"><span data-stu-id="33e5b-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="33e5b-185">在具有良好有線品質的網站中，較差的無線資料流程，必須有特定的無線元件。</span><span class="sxs-lookup"><span data-stu-id="33e5b-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="33e5b-186">CQM 無線查詢（LastMile\_1\_無線）是在日期範圍執行，並將您環境中的所有內部無線資料流程從 Lync 用戶端傳回或從會議服務器或轉送伺服器返回。</span><span class="sxs-lookup"><span data-stu-id="33e5b-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="33e5b-187">我們建議您為含\< \> 300 串流的網站定義目標 PoorStreamsRatio 5%）。</span><span class="sxs-lookup"><span data-stu-id="33e5b-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="33e5b-188">若要取得您的目標，請將從最差訂購的子網修正成最佳，並實施 QoS。</span><span class="sxs-lookup"><span data-stu-id="33e5b-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="33e5b-189">端點道路</span><span class="sxs-lookup"><span data-stu-id="33e5b-189">The End Points Road</span></span>

<span data-ttu-id="33e5b-190">在與 Lync 搭配使用時，使用耳機和其他已知可產生可接受品質的裝置，在端點中開始查詢。</span><span class="sxs-lookup"><span data-stu-id="33e5b-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="33e5b-191">我們建議使用超過100個\>資料流程之實現的目標 AvgSendListen MOS 3.6。）透過找出有問題的裝置並修正或取代，來取得目標。</span><span class="sxs-lookup"><span data-stu-id="33e5b-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="33e5b-192">接下來，請檢查裝置或電腦處理音訊，以供使用者通話。</span><span class="sxs-lookup"><span data-stu-id="33e5b-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="33e5b-193">建議的目標品質指標是 AudioMicGlitchRate \<= 1。</span><span class="sxs-lookup"><span data-stu-id="33e5b-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="33e5b-194">當您識別使用者系統的最佳系統設定時，請定義包括驅動程式版本在內的 "黃金" 電腦設定。</span><span class="sxs-lookup"><span data-stu-id="33e5b-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="33e5b-195">現在，請檢查音訊資料流程從 Lync 端點系統取得的網路路徑，這可能會導致音訊品質不佳。</span><span class="sxs-lookup"><span data-stu-id="33e5b-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="33e5b-196">如果音訊是穿過 VPN 連線，您可能會看到延遲問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="33e5b-197">如果內部 Lync 用戶端無法為兩方或對等呼叫的另一個內部 Lync 用戶端建立直接媒體資料流程，它會回到可透過 Lync Edge 伺服器中繼的路徑，進而帶來延遲問題，並增加遺失和抖動。</span><span class="sxs-lookup"><span data-stu-id="33e5b-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="33e5b-198">我們建議您將品質指標定義為0% 媒體超過 VPN。</span><span class="sxs-lookup"><span data-stu-id="33e5b-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="33e5b-199">當您修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。</span><span class="sxs-lookup"><span data-stu-id="33e5b-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="33e5b-200">IP 資料包可以使用傳輸控制通訊協定（TCP）或使用者資料包通訊協定（UDP）。</span><span class="sxs-lookup"><span data-stu-id="33e5b-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="33e5b-201">TCP 對於資料流程而言是最佳的。</span><span class="sxs-lookup"><span data-stu-id="33e5b-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="33e5b-202">UDP 是無中斷且更有效率的媒體，因為 TCP 恢復機制無法及時處理即時媒體的遺失。</span><span class="sxs-lookup"><span data-stu-id="33e5b-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="33e5b-203">Lync 一直傾向使用 UDP，但如果無法建立 UDP 會話，就會還原為 TCP。</span><span class="sxs-lookup"><span data-stu-id="33e5b-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="33e5b-204">TCP 上的媒體會話會顯示比 UDP 更差的品質。</span><span class="sxs-lookup"><span data-stu-id="33e5b-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="33e5b-205">我們建議將品質定義為在 TCP 上使用0% 連線。</span><span class="sxs-lookup"><span data-stu-id="33e5b-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="33e5b-206">當您修正以達到您設定的目標時，請找出問題的子網，並調查防火牆規則、資料包 shapers，以及其他相關的網路設備設定。</span><span class="sxs-lookup"><span data-stu-id="33e5b-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="33e5b-207">服務管理</span><span class="sxs-lookup"><span data-stu-id="33e5b-207">Service Management</span></span>

<span data-ttu-id="33e5b-208">服務管理是 CQM 的結束狀態，以及所有三個道路的目的地。</span><span class="sxs-lookup"><span data-stu-id="33e5b-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="33e5b-209">若要維持高層次的通話品質，請監視以下區域：</span><span class="sxs-lookup"><span data-stu-id="33e5b-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="33e5b-210">**使用者**修正活動應該顯示使用者滿意度中可衡量的增加。</span><span class="sxs-lookup"><span data-stu-id="33e5b-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="33e5b-211">您可以透過問題入場券或其他意見反應機制來衡量這個問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="33e5b-212">您也可以發佈品質統計資料。</span><span class="sxs-lookup"><span data-stu-id="33e5b-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="33e5b-213">**Process** -定義每日、每週及每月處理 operationalize CQM。</span><span class="sxs-lookup"><span data-stu-id="33e5b-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="33e5b-214">[監視律動] 會在您進行修正時以較高的頻率啟動（每日），並隨著您的穩定而移至較低的頻率（每月）。</span><span class="sxs-lookup"><span data-stu-id="33e5b-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="33e5b-215">[**工具**]-識別測量與修正的工具。</span><span class="sxs-lookup"><span data-stu-id="33e5b-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="33e5b-216">您可能會發現自動執行 CQM 查詢以支援您的程式非常有用。</span><span class="sxs-lookup"><span data-stu-id="33e5b-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="33e5b-217">修正可能需要額外的工具，例如，在網路元素上強制執行標準化設定，或在糟糕的資料流程中排除遺失問題。</span><span class="sxs-lookup"><span data-stu-id="33e5b-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="33e5b-218">棋盤遊戲規則</span><span class="sxs-lookup"><span data-stu-id="33e5b-218">Board Game Rules</span></span>

<span data-ttu-id="33e5b-219">您可以使用這個標牌做為 CQM 的參照，或做為遊戲的做法來練習概念。</span><span class="sxs-lookup"><span data-stu-id="33e5b-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="33e5b-220">若要播放，您需要 1 6 側骰子及隨附的卡片。</span><span class="sxs-lookup"><span data-stu-id="33e5b-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="33e5b-221">可在標準 Avery 5871 名片上列印的卡片可下載版本。</span><span class="sxs-lookup"><span data-stu-id="33e5b-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="33e5b-222">遊戲是針對3個玩家。</span><span class="sxs-lookup"><span data-stu-id="33e5b-222">The game is for 3 players.</span></span> <span data-ttu-id="33e5b-223">玩家可以使用三種路徑來達到所需品質並達到中心服務管理狀態：伺服器工廠、終點及最後一英里。</span><span class="sxs-lookup"><span data-stu-id="33e5b-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="33e5b-224">每個路徑都已停止在您斷言品質目標、實現目標，以及維護系統方面的方式上。</span><span class="sxs-lookup"><span data-stu-id="33e5b-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="33e5b-225">將卡片放在上方所示的區域中，然後繪製5張卡片。</span><span class="sxs-lookup"><span data-stu-id="33e5b-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="33e5b-226">查看您繪製的卡片，並將它們放在相關的版面區段上。</span><span class="sxs-lookup"><span data-stu-id="33e5b-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="33e5b-227">每個玩家都會逐步透過其路線中的卡片逐步移動，以斷言品質目標、取得這些目標，以及維持服務等級。</span><span class="sxs-lookup"><span data-stu-id="33e5b-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="33e5b-228">當所有玩家都達到中心服務管理狀態時，遊戲就會完成。</span><span class="sxs-lookup"><span data-stu-id="33e5b-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="33e5b-229">遊戲卡下載提供更詳細的規則。</span><span class="sxs-lookup"><span data-stu-id="33e5b-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="33e5b-230">若要**斷言**品質目標，請查看適用于該目標的參數，並向外移出您要的內容，而不會選擇接受。</span><span class="sxs-lookup"><span data-stu-id="33e5b-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="33e5b-231">我們建議使用起點，但您必須進行最終通話。</span><span class="sxs-lookup"><span data-stu-id="33e5b-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="33e5b-232">例外狀況是 KHI 資料，而您應該使用 Microsoft 建立的標準。</span><span class="sxs-lookup"><span data-stu-id="33e5b-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="33e5b-233">請參閱隨附的 KHI 海報。</span><span class="sxs-lookup"><span data-stu-id="33e5b-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="33e5b-234">若要在遊戲中**實現**，請使用提供的卡片來代替 KHI 資料和系統查詢。</span><span class="sxs-lookup"><span data-stu-id="33e5b-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="33e5b-235">如果您在遊戲開始時沒有繪製與指定方位有關的卡片，您可以繼續進行。</span><span class="sxs-lookup"><span data-stu-id="33e5b-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="33e5b-236">如果有相關的卡片，請滾動骰子。</span><span class="sxs-lookup"><span data-stu-id="33e5b-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="33e5b-237">如果您是在卡片上所顯示的數位底下滾動，表示您已成功完成。</span><span class="sxs-lookup"><span data-stu-id="33e5b-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="33e5b-238">如果您要將指標放在指定的數位上，您必須從投影片組中繪製另一個卡片。</span><span class="sxs-lookup"><span data-stu-id="33e5b-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="33e5b-239">如果卡片指出兩個或多個玩家需要滾片，就必須全部順利完成。</span><span class="sxs-lookup"><span data-stu-id="33e5b-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="33e5b-240">若要在遊戲中**維護**，請將與 Lync 環境相關的服務管理方案向外醒目。</span><span class="sxs-lookup"><span data-stu-id="33e5b-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="33e5b-241">請參閱</span><span class="sxs-lookup"><span data-stu-id="33e5b-241">See Also</span></span>


[<span data-ttu-id="33e5b-242">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="33e5b-242">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="33e5b-243">金鑰健康指示：維護正常 Lync 伺服器的基礎</span><span class="sxs-lookup"><span data-stu-id="33e5b-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="33e5b-244">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="33e5b-244">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

