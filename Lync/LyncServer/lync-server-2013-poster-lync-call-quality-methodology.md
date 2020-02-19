---
title: Lync Server 2013： 海報： Lync 通話品質方法
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
ms.openlocfilehash: e35627633839f294cebced6df47a90919e7fc5ef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a><span data-ttu-id="38ed8-102">Lync Server 2013 中的 Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="38ed8-102">Lync Call Quality Methodology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38ed8-103">_**主題上次修改日期：** 2016年-06-24_</span><span class="sxs-lookup"><span data-stu-id="38ed8-103">_**Topic Last Modified:** 2016-06-24_</span></span>

<span data-ttu-id="38ed8-104">本文是隨附的[Lync 通話品質方法](https://go.microsoft.com/fwlink/?linkid=391841)海報，您可以從下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="38ed8-104">This article is a companion to the [Lync Call Quality Methodology](https://go.microsoft.com/fwlink/?linkid=391841) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="38ed8-105">![海報中描述的 CQM 程序](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "海報中描述的 CQM 程序")</span><span class="sxs-lookup"><span data-stu-id="38ed8-105">![Poster describing the CQM process](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster describing the CQM process")</span></span>

<span data-ttu-id="38ed8-106">您可以使用此海報以了解 CQM、 通話品質方法 Lync 2013 和 2010，可協助您找出並消除問題影響通話品質和使用者經驗的 Lync 的實作，包括 enterprise voice 功能。</span><span class="sxs-lookup"><span data-stu-id="38ed8-106">You can use this poster to learn about CQM, the Call Quality Methodology for Lync 2013 and 2010 that helps you find and eliminate issues affecting call quality and user experience for Lync implementations that include enterprise voice features.</span></span> <span data-ttu-id="38ed8-107">通話品質方法就是新的疑難排解更妥善地可以專注於改善 Lync 中的企業語音服務的服務管理架構。</span><span class="sxs-lookup"><span data-stu-id="38ed8-107">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="38ed8-108">在本文中，您可以深入了解 CQM、 幾種類型的伺服器與解決方案，監控，以及如何收集的遙測資料處理的項目。</span><span class="sxs-lookup"><span data-stu-id="38ed8-108">In this article, you can learn more about CQM, the kinds of servers and solutions that are monitored, and what to do with the collected telemetry data.</span></span>

<span data-ttu-id="38ed8-109">如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。</span><span class="sxs-lookup"><span data-stu-id="38ed8-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="38ed8-110">海報說明下列領域：</span><span class="sxs-lookup"><span data-stu-id="38ed8-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="38ed8-111">Lync CQM 是什麼？</span><span class="sxs-lookup"><span data-stu-id="38ed8-111">What is Lync CQM?</span></span>

  - <span data-ttu-id="38ed8-112">優先順序： 執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="38ed8-112">Prioritize: Run Trending Queries</span></span>

  - <span data-ttu-id="38ed8-113">PCD</span><span class="sxs-lookup"><span data-stu-id="38ed8-113">PCD</span></span>

  - <span data-ttu-id="38ed8-114">Managed/Unmanaged</span><span class="sxs-lookup"><span data-stu-id="38ed8-114">Managed/Unmanaged</span></span>

  - <span data-ttu-id="38ed8-115">伺服器廠隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-115">The Server Plant Road</span></span>

  - <span data-ttu-id="38ed8-116">最後一個哩隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-116">The Last Mile Road</span></span>

  - <span data-ttu-id="38ed8-117">結束點隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-117">The End Points Road</span></span>

  - <span data-ttu-id="38ed8-118">服務管理</span><span class="sxs-lookup"><span data-stu-id="38ed8-118">Service Management</span></span>

  - <span data-ttu-id="38ed8-119">棋盤遊戲規則</span><span class="sxs-lookup"><span data-stu-id="38ed8-119">Board Game Rules</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a><span data-ttu-id="38ed8-120">Lync CQM 是什麼？</span><span class="sxs-lookup"><span data-stu-id="38ed8-120">What is Lync CQM?</span></span>

<span data-ttu-id="38ed8-121">通話品質方法就是新的疑難排解更妥善地可以專注於改善 Lync 中的企業語音服務的服務管理架構。</span><span class="sxs-lookup"><span data-stu-id="38ed8-121">Call Quality Methodology is a new troubleshooting and service management framework that can better focus efforts to improve enterprise voice services in Lync.</span></span> <span data-ttu-id="38ed8-122">當您使用 CQM 時，需要更輕鬆的方式就能保證通話品質及提升使用者滿意度，適用於企業語音服務。</span><span class="sxs-lookup"><span data-stu-id="38ed8-122">When you use CQM, less effort is needed to assure call quality and user satisfaction for enterprise voice services.</span></span> <span data-ttu-id="38ed8-123">[通話品質方法](https://go.microsoft.com/fwlink/p/?linkid=615208)會詳細說明 CQM。</span><span class="sxs-lookup"><span data-stu-id="38ed8-123">CQM is more fully explained in the [Call Quality Methodology](https://go.microsoft.com/fwlink/p/?linkid=615208).</span></span> <span data-ttu-id="38ed8-124">這篇文章和海報是該內容的摘要。</span><span class="sxs-lookup"><span data-stu-id="38ed8-124">This article and the poster are summaries of that content.</span></span>

<span data-ttu-id="38ed8-125">CQM 細分系統疑難排解到三個路徑或 「 通道 」。</span><span class="sxs-lookup"><span data-stu-id="38ed8-125">CQM breaks down System troubleshooting into three paths or “Roads.”</span></span> <span data-ttu-id="38ed8-126">這些是： 伺服器廠隨身攜帶，它看來伺服器和、 結束點隨身攜帶，查看使用者裝置和媒體用來執行通話，以及上次哩隨身攜帶，地址整合的傳統交換的電話網路之間的連結。</span><span class="sxs-lookup"><span data-stu-id="38ed8-126">These are: the Server Plant Road, which looks at the servers and the links between them, the End Points Road, which looks at user devices and media used to carry calls, and the Last Mile Road, which addresses integration of traditional switched telephone network calls.</span></span>

<span data-ttu-id="38ed8-127">每個途徑可分成數個區段相關的特定區域或主題，並在每個區段定義之所以資訊可接受的品質等級，不採取動作達成品質等級，與服務管理計畫就會處於維護的地方再移至下一個主題的品質等級。</span><span class="sxs-lookup"><span data-stu-id="38ed8-127">Each Road is divided into several segments relating to a specific area or topic, and at each segment definitions are made about what is an acceptable quality level, actions are taken to achieve that quality level, and a service management plan is put in place to maintain that quality level before moving on to the next topic.</span></span>

<span data-ttu-id="38ed8-128">海報會呈現為棋盤遊戲 Lync CQM 的三個播放，每個使用者都就會通過經歷下列其中一個通道。</span><span class="sxs-lookup"><span data-stu-id="38ed8-128">The poster presents Lync CQM as a board game for three players, each of whom will go through one of the roads.</span></span> <span data-ttu-id="38ed8-129">卡隨附下載可用來模擬呼叫必須克服的品質障礙。</span><span class="sxs-lookup"><span data-stu-id="38ed8-129">Cards included with the download are used to simulate impediments to call quality that must be overcome.</span></span> <span data-ttu-id="38ed8-130">提示與建議相關的目標，以及如何達成這些隨附沿著的三個路徑，以及要先實際的應用程式中的哪些隨身攜帶的優先順序指導方針 （在 [遊戲時，所有三個通道中會處理平行）。</span><span class="sxs-lookup"><span data-stu-id="38ed8-130">Hints and suggestions about targets and how to achieve them are included along the three paths, as well as prioritization guidelines for which road to pursue first in actual applications (in the game, all three roads are addressed in parallel).</span></span>

<span data-ttu-id="38ed8-131">CQM 如何運作中更早版本的 Lync？</span><span class="sxs-lookup"><span data-stu-id="38ed8-131">How does CQM work in earlier versions of Lync?</span></span> <span data-ttu-id="38ed8-132">CQM's new for Lync 2013 中，但是大部分的它可適用於與 Lync 2010 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="38ed8-132">CQM is new for Lync 2013, but most of it can be adapted to be used with Lync 2010.</span></span> <span data-ttu-id="38ed8-133">CQM 可能運作進行一定程度與 Microsoft Office Communicator，但這是未經測試，而且不受支援。</span><span class="sxs-lookup"><span data-stu-id="38ed8-133">CQM may work to a degree with Microsoft Office Communicator, but this is untested and not supported.</span></span>

<span data-ttu-id="38ed8-134">如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。</span><span class="sxs-lookup"><span data-stu-id="38ed8-134">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a><span data-ttu-id="38ed8-135">優先順序： 執行趨勢查詢</span><span class="sxs-lookup"><span data-stu-id="38ed8-135">Prioritize: Run Trending Queries</span></span>

<span data-ttu-id="38ed8-136">CQM 的第一步是執行每個趨勢查詢的兩週，並再分析結果。</span><span class="sxs-lookup"><span data-stu-id="38ed8-136">The first step in CQM is to run each of the trending queries for two weeks and then analyze the results.</span></span> <span data-ttu-id="38ed8-137">優先順序矯正措施的最大的資料流參與者、 最高不佳的資料流率，並受管理的區域 （您可以控制的項目）。</span><span class="sxs-lookup"><span data-stu-id="38ed8-137">Prioritize corrective action by the largest stream contributor, the highest poor stream ratio, and managed areas (ones you control).</span></span><span data-ttu-id="38ed8-138">如果 [音訊/視訊多點 Control Unit (AV MCU) 或中繼查詢顯示不佳的結果，請啟動紅色或伺服器廠隨身攜帶。</span><span class="sxs-lookup"><span data-stu-id="38ed8-138">  If the Audio/Video Multi-point Control Unit (AV MCU) or Mediation queries show poor results, start on the Red or Server Plant road.</span></span><span data-ttu-id="38ed8-139">如果有線或無線查詢顯示不佳的結果，請啟動藍色或最後一個哩隨身攜帶。</span><span class="sxs-lookup"><span data-stu-id="38ed8-139">  If the Wired or Wireless queries show poor results, start on the Blue or Last Mile road.</span></span><span data-ttu-id="38ed8-140">如果 VPN 或外部查詢顯示不佳的結果，請啟動綠色或結束點隨身攜帶。</span><span class="sxs-lookup"><span data-stu-id="38ed8-140">  If the VPN or External queries show poor results, start on the Green or End Points road.</span></span>

<span data-ttu-id="38ed8-141">開始使用您選擇 [隨身攜帶之後，定義每個區域 (Assert)，可以使用，以符合該目標 (Achieve)，然後實作留在目標 （維持） 的程序的目標。</span><span class="sxs-lookup"><span data-stu-id="38ed8-141">After you choose a road to start with, define a target for each area (Assert), work to meet that target (Achieve) and then implement procedures to stay on target (Maintain).</span></span> <span data-ttu-id="38ed8-142">您也可以使用此海報以遊戲，若要了解 CQM 背後的原則。</span><span class="sxs-lookup"><span data-stu-id="38ed8-142">You can also use this poster as a game to understand the principles behind CQM.</span></span>

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a><span data-ttu-id="38ed8-143">PCD</span><span class="sxs-lookup"><span data-stu-id="38ed8-143">PCD</span></span>

<span data-ttu-id="38ed8-144">PreCall 診斷工具 (PCD) 可協助您找出並診斷問題在周邊網路 （QoE 資料庫不會收集資訊 edge 或周邊網路），也要疑難排解中最後一個哩的連線。</span><span class="sxs-lookup"><span data-stu-id="38ed8-144">The PreCall Diagnostics tool (PCD) will help you identify and diagnose problems in your perimeter network (the QoE database doesn’t collect information on your edge or perimeter network) and also to troubleshoot connections in the Last Mile.</span></span> <span data-ttu-id="38ed8-145">為 Windows 8 新式應用程式或 Windows 桌面應用程式工具可供http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88。</span><span class="sxs-lookup"><span data-stu-id="38ed8-145">The tool is available as both a Windows 8 Modern App or a Windows Desktop App at http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88.</span></span>

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a><span data-ttu-id="38ed8-146">Managed/Unmanaged</span><span class="sxs-lookup"><span data-stu-id="38ed8-146">Managed/Unmanaged</span></span>

<span data-ttu-id="38ed8-147">Lync Server 部署和網路基礎結構通常可分成 managed 和 unmanaged 空格。</span><span class="sxs-lookup"><span data-stu-id="38ed8-147">The Lync Server deployment and network infrastructure can usually be divided into managed and unmanaged spaces.</span></span> <span data-ttu-id="38ed8-148">受管理的空間可包含您整個內有線的網路和伺服器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="38ed8-148">The managed space includes your entire inside wired network and server infrastructure.</span></span> <span data-ttu-id="38ed8-149">未受管理的空間是無線基礎結構，以及外部網路基礎結構。</span><span class="sxs-lookup"><span data-stu-id="38ed8-149">The unmanaged space is the wireless infrastructure and the outside network infrastructure.</span></span>

<span data-ttu-id="38ed8-150">進行這樣的區分會增加資料的緣故，並可協助您組織的焦點上會有可測量影響使用者的語音和視訊品質的工作負載。</span><span class="sxs-lookup"><span data-stu-id="38ed8-150">Making this distinction increases the clarity of your data and helps your organization focus on workloads that will have a measurable impact on your users’ voice and video quality.</span></span> <span data-ttu-id="38ed8-151">使用者可以品質不同期望如果來電會被放置在基礎結構上您擁有 （管理） 與基礎結構的 （未受管理） 的其他實體的控制下的部分。</span><span class="sxs-lookup"><span data-stu-id="38ed8-151">Users have a different expectation of quality if the call is placed on infrastructure that you own (managed) versus infrastructure that is partly under the control of some other entity (unmanaged).</span></span> <span data-ttu-id="38ed8-152">這並不是說無線使用者由左到自己的裝置有極佳的 Lync Server 體驗。</span><span class="sxs-lookup"><span data-stu-id="38ed8-152">This is not to say that wireless users are left to their own devices to have excellent Lync Server experiences.</span></span>

<span data-ttu-id="38ed8-153">改善的未受管理的空間中的語音品質必須要有高品質的受管理的空間中。</span><span class="sxs-lookup"><span data-stu-id="38ed8-153">Improving voice quality in the unmanaged space requires you to have high quality in the managed space.</span></span> <span data-ttu-id="38ed8-154">無線 (Wi-fi) 是否會被視為受管理或未受管理的空間是由您的組織。</span><span class="sxs-lookup"><span data-stu-id="38ed8-154">Whether wireless (Wi-Fi) is considered managed or unmanaged space is up to your organization.</span></span> <span data-ttu-id="38ed8-155">是解決方案所，不同於兩個的空格，以達到狀況良好的環境的技術。</span><span class="sxs-lookup"><span data-stu-id="38ed8-155">The techniques to achieve a healthy environment are different in the two spaces, as are the solutions.</span></span>

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a><span data-ttu-id="38ed8-156">伺服器廠隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-156">The Server Plant Road</span></span>

<span data-ttu-id="38ed8-157">區段 1 伺服器廠隨身攜帶的地址中的 Lync 實作實際的伺服器。</span><span class="sxs-lookup"><span data-stu-id="38ed8-157">Segment 1 of the Server Plant Road addresses the actual servers in the Lync implementation.</span></span> <span data-ttu-id="38ed8-158">收集有關伺服器本身及實作中的其角色 KHI 資料並分析結果。</span><span class="sxs-lookup"><span data-stu-id="38ed8-158">Gather KHI data regarding both the server itself and its role in the implementation and analyze the result.</span></span> <span data-ttu-id="38ed8-159">如果巨集指令已獲得保證，更正發現的任何問題。</span><span class="sxs-lookup"><span data-stu-id="38ed8-159">If action is warranted, correct any problems found.</span></span> <span data-ttu-id="38ed8-160">本主題的其他詳細資料會以[Lync Server 2013 中的機碼健康狀態指標](lync-server-2013-poster-key-health-indicators.md)時所附帶 KHI 海報的相關文件呈現。</span><span class="sxs-lookup"><span data-stu-id="38ed8-160">More detail on this topic is presented in the article about [Key Health Indicators in Lync Server 2013](lync-server-2013-poster-key-health-indicators.md) that accompanies the KHI poster.</span></span>

<span data-ttu-id="38ed8-161">下一個區段位址 AV MCU 伺服器和中繼伺服器之間的媒體資料流。</span><span class="sxs-lookup"><span data-stu-id="38ed8-161">The next segment addresses media streams between the AV MCU server and mediation server.</span></span> <span data-ttu-id="38ed8-162">首先決定不佳的資料流閾值的目標。</span><span class="sxs-lookup"><span data-stu-id="38ed8-162">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="38ed8-163">不佳的資料流通常是 PacketLossRate \> .01 或 PacketLossRateMax \> .05。</span><span class="sxs-lookup"><span data-stu-id="38ed8-163">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="38ed8-164">另一個令人滿意的目標是 PoorStreamsRatio \< 2%。</span><span class="sxs-lookup"><span data-stu-id="38ed8-164">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="38ed8-165">接下來，使用詳細的查詢來找出與不佳的資料流的 AVMCU 和中繼伺服器配對、 調查不佳的資料流的原因、 查看不佳的資料流路徑中的網路設備、 修復不佳的資料流，並定義網路最佳或 「 金會員 」 設定設備。</span><span class="sxs-lookup"><span data-stu-id="38ed8-165">Next, use detailed queries to find AVMCU and Mediation server pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="38ed8-166">若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。</span><span class="sxs-lookup"><span data-stu-id="38ed8-166">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="38ed8-167">接下來，檢查中繼伺服器與公用交換電話網路 (PSTN) 閘道間的媒體資料流。</span><span class="sxs-lookup"><span data-stu-id="38ed8-167">Next, examine the media streams between the Mediation server and the Public Switched Telephone Network (PSTN) gateway.</span></span> <span data-ttu-id="38ed8-168">首先決定不佳的資料流閾值的目標。</span><span class="sxs-lookup"><span data-stu-id="38ed8-168">Begin by determining your targets for poor stream thresholds.</span></span> <span data-ttu-id="38ed8-169">不佳的資料流通常是 PacketLossRate \> .01 或 PacketLossRateMax \> .05。</span><span class="sxs-lookup"><span data-stu-id="38ed8-169">Poor streams are usually PacketLossRate \> .01 or PacketLossRateMax \> .05.</span></span> <span data-ttu-id="38ed8-170">另一個令人滿意的目標是 PoorStreamsRatio \< 2%。</span><span class="sxs-lookup"><span data-stu-id="38ed8-170">Another desirable target is PoorStreamsRatio \< 2%.</span></span> <span data-ttu-id="38ed8-171">接下來，使用詳細的查詢來找出與不佳的資料流的中繼伺服器和閘道配對、 調查不佳的資料流的原因、 查看不佳的資料流路徑中的網路設備、 修復不佳的資料流，並定義網路最佳或 「 金會員 」 設定設備。</span><span class="sxs-lookup"><span data-stu-id="38ed8-171">Next, use detailed queries to find Mediation server and gateway pairs with poor streams, investigate the cause of poor streams, look at network equipment in the poor stream paths, remediate poor streams, and define optimal or “gold” configuration for network equipment.</span></span> <span data-ttu-id="38ed8-172">若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。</span><span class="sxs-lookup"><span data-stu-id="38ed8-172">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span>

<span data-ttu-id="38ed8-173">最後，檢查您 PSTN 閘道的狀況度量資訊。</span><span class="sxs-lookup"><span data-stu-id="38ed8-173">Finally, examine the health metrics for your PSTN gateway.</span></span> <span data-ttu-id="38ed8-174">識別顯示健康情況及定義對其目標的統計資料。</span><span class="sxs-lookup"><span data-stu-id="38ed8-174">Identify the statistics that show health and define targets against them.</span></span> <span data-ttu-id="38ed8-175">沒有特定的指引這裡提供最多可能閘道可用。</span><span class="sxs-lookup"><span data-stu-id="38ed8-175">No specific guidance is provided here as many possible gateways can be used.</span></span> <span data-ttu-id="38ed8-176">一旦建立目標，修復達成目標; 視程序中您可能會定義閘道 」 金會員 」 或最佳組態。</span><span class="sxs-lookup"><span data-stu-id="38ed8-176">Once targets are established, remediate as needed to achieve the target; in the process you will likely define a “gold” or optimal configuration for the gateway.</span></span> <span data-ttu-id="38ed8-177">若要維護您成就，實作程序和工具來管理組態漂移並報告新的問題領域。</span><span class="sxs-lookup"><span data-stu-id="38ed8-177">To maintain your achievement, implement processes and tools to manage configuration drift and to report new problem areas.</span></span> <span data-ttu-id="38ed8-178">請注意韌體和軟體更新可能會改變您的組態，或將引導您要變更 「 黃金 」 設定的定義，因此方法與照護這些活動。</span><span class="sxs-lookup"><span data-stu-id="38ed8-178">Be aware that firmware and software updates may alter your configuration or lead you to change the definition of the “gold” configuration, so approach these activities with care.</span></span>

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a><span data-ttu-id="38ed8-179">最後一個哩隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-179">The Last Mile Road</span></span>

<span data-ttu-id="38ed8-180">兩個方式用戶端連線至網路，有線預期提供最高品質，因此這必須是您最初的焦點的最後一個哩問題。</span><span class="sxs-lookup"><span data-stu-id="38ed8-180">Of the two ways clients connect to the network, wired is expected to deliver the highest quality and correspondingly this must be your initial focus for last mile issues.</span></span> <span data-ttu-id="38ed8-181">使用 CQM 有線的查詢 (LastMile\_0\_有線) 和它會提供不良的資料流比率資料。</span><span class="sxs-lookup"><span data-stu-id="38ed8-181">Use the CQM Wired query (LastMile\_0\_Wired) and the Poor Streams ratio data it provides.</span></span> <span data-ttu-id="38ed8-182">我們建議在定義的目標 PoorStreamsRatio \< 5%的站台\>300 資料流)。</span><span class="sxs-lookup"><span data-stu-id="38ed8-182">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="38ed8-183">若要達到目標，修復排序從最壞打算最佳，並實作 QoS 的子網路。</span><span class="sxs-lookup"><span data-stu-id="38ed8-183">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

<span data-ttu-id="38ed8-184">有線連線品質最佳化之後，改善無線品質變得更容易因為無線基礎結構在有線核心頂端位於每個位置。</span><span class="sxs-lookup"><span data-stu-id="38ed8-184">After you optimize the quality of your wired connections, improving wireless quality becomes easier because the wireless infrastructure sits atop the wired core at each location.</span></span> <span data-ttu-id="38ed8-185">在具有有線品質良好的網站不佳無線資料流必須歸因於特定的無線元件。</span><span class="sxs-lookup"><span data-stu-id="38ed8-185">Poor wireless streams in a site with good wired quality must be attributed to the specific wireless components.</span></span> <span data-ttu-id="38ed8-186">CQM 無線查詢 (LastMile\_1\_無線) 的日期範圍上運作，且會傳回所有內部的無線資料流環境中的 Lync 用戶端至或來自會議伺服器或中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="38ed8-186">The CQM Wireless query (LastMile\_1\_Wireless) operates on a date range and will return all internal wireless streams in your environment from Lync clients to or from either conferencing servers or mediation servers.</span></span> <span data-ttu-id="38ed8-187">我們建議在定義的目標 PoorStreamsRatio \< 5%的站台\>300 資料流)。</span><span class="sxs-lookup"><span data-stu-id="38ed8-187">We suggest defining a target PoorStreamsRatio \< 5% for sites with \> 300 streams).</span></span> <span data-ttu-id="38ed8-188">若要達到目標，修復排序從最壞打算最佳，並實作 QoS 的子網路。</span><span class="sxs-lookup"><span data-stu-id="38ed8-188">To achieve your targets, remediate subnets ordered from worst to best, and implement QoS.</span></span>

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a><span data-ttu-id="38ed8-189">結束點隨身攜帶</span><span class="sxs-lookup"><span data-stu-id="38ed8-189">The End Points Road</span></span>

<span data-ttu-id="38ed8-190">從開始到結束點隨身攜帶耳機與其他裝置以產生可接受的品質搭配 Lync 時已知的相關事宜。</span><span class="sxs-lookup"><span data-stu-id="38ed8-190">Begin inquiries into the End Points Road with the headsets and other devices known to produce acceptable quality when used with Lync.</span></span> <span data-ttu-id="38ed8-191">我們建議在目標 AvgSendListen MOS \> 3.6 的實作方式具有超過 100 個資料流。)識別問題的裝置來達成目標，以及修正或加以取代。</span><span class="sxs-lookup"><span data-stu-id="38ed8-191">We suggest a target AvgSendListen MOS \> 3.6 for implementations with over 100 streams.) Achieve the target by identifying problematic devices and fix or replace them.</span></span>

<span data-ttu-id="38ed8-192">接下來，檢查裝置或電腦處理的使用者通話音訊。</span><span class="sxs-lookup"><span data-stu-id="38ed8-192">Next, examine the device or PC processing the audio for end user calls.</span></span> <span data-ttu-id="38ed8-193">建議的目標品質評量是 AudioMicGlitchRate \<= 1。</span><span class="sxs-lookup"><span data-stu-id="38ed8-193">A suggested target quality metric is an AudioMicGlitchRate \<= 1.</span></span> <span data-ttu-id="38ed8-194">當您找出使用者系統的最佳系統組態，定義 「 最佳 」 的電腦組態，包括驅動程式版本。</span><span class="sxs-lookup"><span data-stu-id="38ed8-194">As you identify optimal system configurations for the user systems, define a “golden” PC configuration including driver versions.</span></span>

<span data-ttu-id="38ed8-195">現在檢查音訊資料流採取從 Lync 端點系統，這可能會造成音訊品質不佳的網路路徑。</span><span class="sxs-lookup"><span data-stu-id="38ed8-195">Now examine the network path an audio stream takes from a Lync endpoint system, which can cause poor audio quality.</span></span> <span data-ttu-id="38ed8-196">如果音訊，透過 VPN 連線可能會看到延遲問題。</span><span class="sxs-lookup"><span data-stu-id="38ed8-196">If audio travels over a VPN connection you might see latency issues.</span></span> <span data-ttu-id="38ed8-197">如果內部 Lync 用戶端無法建立另一個內部的 Lync 用戶端，雙方或對等通話直接媒體資料流，它將會回復為轉送透過 Lync Edge server，重新導向延遲問題，以及增加的潛在的路徑遺失及抖動。</span><span class="sxs-lookup"><span data-stu-id="38ed8-197">If an internal Lync client cannot establish a direct media stream to another internal Lync client for a two-party or peer-to-peer call, it will fall back to a path that relays through a Lync Edge server, again leading to latency issues as well as increased potential for loss and jitter.</span></span> <span data-ttu-id="38ed8-198">我們建議您透過 VPN 定義 0%的媒體品質計量。</span><span class="sxs-lookup"><span data-stu-id="38ed8-198">We suggest you define a quality metric of 0% Media over VPN.</span></span> <span data-ttu-id="38ed8-199">當您修復達到您設定的目標，找出問題子網路，並調查防火牆規則、 封包 shapers，以及其他相關網路設備組態。</span><span class="sxs-lookup"><span data-stu-id="38ed8-199">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

<span data-ttu-id="38ed8-200">傳輸控制通訊協定 (TCP) 或使用者資料包通訊協定 (UDP)，可以使用 IP 封包。</span><span class="sxs-lookup"><span data-stu-id="38ed8-200">IP Packets can use either Transmission Control Protocol (TCP) or User Datagram Protocol (UDP).</span></span> <span data-ttu-id="38ed8-201">TCP 是最佳的資料流。</span><span class="sxs-lookup"><span data-stu-id="38ed8-201">TCP is optimal for data streams.</span></span> <span data-ttu-id="38ed8-202">UDP 是無連線且更有效率的媒體因為 TCP 復原機制無法解決即時媒體中的遺失。</span><span class="sxs-lookup"><span data-stu-id="38ed8-202">UDP is connectionless and is more efficient for media since TCP recovery mechanisms cannot address loss in real time media.</span></span> <span data-ttu-id="38ed8-203">Lync 一律偏好 UDP，但如果無法建立 UDP 工作階段，就會還原成 TCP。</span><span class="sxs-lookup"><span data-stu-id="38ed8-203">Lync always prefers UDP, but will revert to TCP if a UDP session cannot be established.</span></span> <span data-ttu-id="38ed8-204">透過 TCP 的媒體工作階段會透過 UDP 展示差的品質。</span><span class="sxs-lookup"><span data-stu-id="38ed8-204">Media sessions over TCP will exhibit poorer quality than over UDP.</span></span> <span data-ttu-id="38ed8-205">建議 0%連線的品質定義 over TCP。</span><span class="sxs-lookup"><span data-stu-id="38ed8-205">We recommend a quality definition of 0% connections over TCP.</span></span> <span data-ttu-id="38ed8-206">當您修復達到您設定的目標，找出問題子網路，並調查防火牆規則、 封包 shapers，以及其他相關網路設備組態。</span><span class="sxs-lookup"><span data-stu-id="38ed8-206">As you remediate to achieve the target you set, identify problem subnets and investigate firewall rules, packet shapers, and other relevant network equipment configuration.</span></span>

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a><span data-ttu-id="38ed8-207">服務管理</span><span class="sxs-lookup"><span data-stu-id="38ed8-207">Service Management</span></span>

<span data-ttu-id="38ed8-208">服務管理功能的結束狀態的 CQM，以及所有三個通道的目的地。</span><span class="sxs-lookup"><span data-stu-id="38ed8-208">Service management is the end state of CQM, and the destination for all three roads.</span></span> <span data-ttu-id="38ed8-209">若要維護的通話品質的高層級，請監視這些區域：</span><span class="sxs-lookup"><span data-stu-id="38ed8-209">To maintain high levels of call quality, monitor these areas:</span></span>

1.  <span data-ttu-id="38ed8-210">**使用者**-修復活動應使用者滿意度中會顯示可測量的增加。</span><span class="sxs-lookup"><span data-stu-id="38ed8-210">**Users** - Remediation activities should show a measurable increase in user satisfaction.</span></span> <span data-ttu-id="38ed8-211">您可以測量這問題票證或其他的意見反應機制。</span><span class="sxs-lookup"><span data-stu-id="38ed8-211">You can measure this by problem tickets or other feedback mechanisms.</span></span> <span data-ttu-id="38ed8-212">您也可以發佈品質計量。</span><span class="sxs-lookup"><span data-stu-id="38ed8-212">You can also publish quality metrics.</span></span>

2.  <span data-ttu-id="38ed8-213">**處理程序**-定義每日、 每週及每月處理程序 operationalize CQM。</span><span class="sxs-lookup"><span data-stu-id="38ed8-213">**Process** - define daily, weekly and monthly processes to operationalize CQM.</span></span> <span data-ttu-id="38ed8-214">監視節奏持續開始較高的頻率 （每日），您會修復時，並移至較低頻率 （每月） 為您穩定。</span><span class="sxs-lookup"><span data-stu-id="38ed8-214">Monitoring rhythm starts at a higher frequency while you are remediating (daily) and moves to a lower frequency (monthly) as you stabilize.</span></span>

3.  <span data-ttu-id="38ed8-215">[**工具**]-找出兩個量值的工具及修復。</span><span class="sxs-lookup"><span data-stu-id="38ed8-215">**Tools** - identify tools to both measure and remediate.</span></span> <span data-ttu-id="38ed8-216">您可能會發現很有用來自動化執行 CQM 查詢以支援您的程序。</span><span class="sxs-lookup"><span data-stu-id="38ed8-216">You may find it useful to automate running the CQM queries to support your processes.</span></span> <span data-ttu-id="38ed8-217">修復可能需要額外的工具，以強制執行標準化的設定網路元素或疑難排解遺失不佳的資料流中的範例。</span><span class="sxs-lookup"><span data-stu-id="38ed8-217">Remediation may require additional tools for example to enforce standardized configurations on network elements or troubleshooting loss in poor streams.</span></span>

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a><span data-ttu-id="38ed8-218">棋盤遊戲規則</span><span class="sxs-lookup"><span data-stu-id="38ed8-218">Board Game Rules</span></span>

<span data-ttu-id="38ed8-219">您可以使用此海報 CQM 實作參考或遊戲的身分來練習概念。</span><span class="sxs-lookup"><span data-stu-id="38ed8-219">You can use this poster either as a reference to a CQM implementation or as a game to practice the concepts.</span></span> <span data-ttu-id="38ed8-220">若要播放，您將需要一個六角死及所提供的卡片。</span><span class="sxs-lookup"><span data-stu-id="38ed8-220">To play, you will need one six-sided die and the cards provided.</span></span> <span data-ttu-id="38ed8-221">使用標準 Avery 5871 名片上要列印的卡片可下載的版本。</span><span class="sxs-lookup"><span data-stu-id="38ed8-221">A downloadable version of the cards is available to print on standard Avery 5871 business cards.</span></span>

<span data-ttu-id="38ed8-222">遊戲是 3 的玩家。</span><span class="sxs-lookup"><span data-stu-id="38ed8-222">The game is for 3 players.</span></span> <span data-ttu-id="38ed8-223">有三種路徑的玩家可用來達成所需的品質，並達到中心服務管理狀態： 伺服器廠、 結束點和最後一個哩。</span><span class="sxs-lookup"><span data-stu-id="38ed8-223">There are three paths the players can use to achieve the desired quality and reach the center Service Management state: Server Plant, End Point, and Last Mile.</span></span> <span data-ttu-id="38ed8-224">每個路徑有停駐點沿著您 Assert 品質目標，達成目標，以及維護系統的層面的方式。</span><span class="sxs-lookup"><span data-stu-id="38ed8-224">Each path has stops along the way where you Assert quality targets, Achieve goals, and Maintain an aspect of your system.</span></span> <span data-ttu-id="38ed8-225">將卡放在指定的區域，與上述並再繪製 5 卡。</span><span class="sxs-lookup"><span data-stu-id="38ed8-225">Place the cards in the indicated area above, and then draw 5 cards.</span></span> <span data-ttu-id="38ed8-226">檢閱已繪製，並將其放在相關棋盤區段上的卡片。</span><span class="sxs-lookup"><span data-stu-id="38ed8-226">Review the cards you’ve drawn and place them on the relevant board segment.</span></span> <span data-ttu-id="38ed8-227">每個玩家卡透過依其路徑移動逐步解說，要達成這些目標、 和維護的服務層級宣告品質目標。</span><span class="sxs-lookup"><span data-stu-id="38ed8-227">Each player moves through the cards on their path step by step, asserting quality targets, achieving those targets, and maintaining the service levels.</span></span> <span data-ttu-id="38ed8-228">所有的玩家達到中心服務管理狀態時，就會完成遊戲。</span><span class="sxs-lookup"><span data-stu-id="38ed8-228">The game is completed when all players reach the center Service Management state.</span></span> <span data-ttu-id="38ed8-229">遊戲卡下載會提供更詳細的規則。</span><span class="sxs-lookup"><span data-stu-id="38ed8-229">More detailed rules are provided with the game card download.</span></span>

<span data-ttu-id="38ed8-230">**Assert**品質目標，以檢閱適用於該目標和狀態參數能功能將而且不會選擇要接受。</span><span class="sxs-lookup"><span data-stu-id="38ed8-230">To **Assert** a quality target, review the parameters applicable to that target, and state out loud what you will and won’t choose to accept.</span></span> <span data-ttu-id="38ed8-231">我們建議的起始點，但您必須進行的最後呼叫。</span><span class="sxs-lookup"><span data-stu-id="38ed8-231">We have recommended beginning points, but you must make the final call.</span></span> <span data-ttu-id="38ed8-232">例外狀況是 KHI 資料，其中應該使用 Microsoft 所建立的標準。</span><span class="sxs-lookup"><span data-stu-id="38ed8-232">The exception is KHI data, where the standards established by Microsoft should be used.</span></span> <span data-ttu-id="38ed8-233">請參閱隨附 KHI 海報。</span><span class="sxs-lookup"><span data-stu-id="38ed8-233">See the accompanying KHI poster.</span></span>

<span data-ttu-id="38ed8-234">若要在遊戲**Achieve**使用取代 KHI 資料及系統查詢所提供的卡片。</span><span class="sxs-lookup"><span data-stu-id="38ed8-234">To **Achieve** in the game, use the cards provided in place of KHI data and system queries.</span></span> <span data-ttu-id="38ed8-235">如果您沒有不繪製指定的外觀與相關的卡片遊戲開頭，您可以繼續過去它。</span><span class="sxs-lookup"><span data-stu-id="38ed8-235">If at the start of the game you did not draw a card relating to a given aspect, you can continue past it.</span></span> <span data-ttu-id="38ed8-236">如果沒有相關的卡片，回復死。</span><span class="sxs-lookup"><span data-stu-id="38ed8-236">If there is a relevant card, roll the die.</span></span> <span data-ttu-id="38ed8-237">如果您復原在卡片上編號] 下，您都已成功。</span><span class="sxs-lookup"><span data-stu-id="38ed8-237">If you rolled under the number indicated on the card, you have succeeded.</span></span> <span data-ttu-id="38ed8-238">如果您將位於或超過指定的數字，您必須從艙面繪製其他卡片。</span><span class="sxs-lookup"><span data-stu-id="38ed8-238">If you roll at or over the indicated number, you must draw another card from the deck.</span></span> <span data-ttu-id="38ed8-239">如果卡片會指出兩個以上的玩家需要回復，它們必須全部回復成功。</span><span class="sxs-lookup"><span data-stu-id="38ed8-239">If the card indicates two or more players need to roll, they must all roll successfully.</span></span>

<span data-ttu-id="38ed8-240">要**維持**在遊戲，狀態出過吵雜有關該方面的 Lync 環境與服務管理計劃。</span><span class="sxs-lookup"><span data-stu-id="38ed8-240">To **Maintain** in the game, state out loud the service management plan regarding that aspect of the Lync environment.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="38ed8-241">另請參閱</span><span class="sxs-lookup"><span data-stu-id="38ed8-241">See Also</span></span>


[<span data-ttu-id="38ed8-242">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="38ed8-242">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="38ed8-243">維護狀況良好的 Lync 伺服器 Foundation 主要的健康狀態指標：</span><span class="sxs-lookup"><span data-stu-id="38ed8-243">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="38ed8-244">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="38ed8-244">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

