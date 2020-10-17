---
title: Lync Server 2013：標牌：重要健康情況指示器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513380"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="3cc1f-102">Lync Server 2013 中的主要健康情況指示器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-102">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cc1f-103">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="3cc1f-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="3cc1f-104">本文是與 [主要健康狀態指示器有關的基礎：維護狀況良好的 Lync 伺服器](https://go.microsoft.com/fwlink/?linkid=391838) 海報，您可以從下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="3cc1f-105">![使用 KHI 資料進行疑難排解說明的海報](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "使用 KHI 資料進行疑難排解說明的海報")</span><span class="sxs-lookup"><span data-stu-id="3cc1f-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="3cc1f-106">您可以使用此海報來瞭解主要健康情況指示器 (KHIs) 、效能計數器，其臨界值是用於顯示使用者經驗問題。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3cc1f-107">收集 KHI 資料通常是實施通話品質方法 (CQM) （主要是為了確保 Lync 使用者的品質音訊體驗）的第一步。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3cc1f-108">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="3cc1f-109">海報會說明下列方面：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="3cc1f-110">重要狀況指示器為何？</span><span class="sxs-lookup"><span data-stu-id="3cc1f-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="3cc1f-111">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="3cc1f-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="3cc1f-112">所有伺服器角色的修正流程</span><span class="sxs-lookup"><span data-stu-id="3cc1f-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="3cc1f-113">詞彙</span><span class="sxs-lookup"><span data-stu-id="3cc1f-113">Glossary</span></span>

  - <span data-ttu-id="3cc1f-114">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-114">Front-end Servers</span></span>

  - <span data-ttu-id="3cc1f-115">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="3cc1f-116">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-116">Mediation Servers</span></span>

  - <span data-ttu-id="3cc1f-117">Edge Server</span><span class="sxs-lookup"><span data-stu-id="3cc1f-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="3cc1f-118">重要狀況指示器為何？</span><span class="sxs-lookup"><span data-stu-id="3cc1f-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="3cc1f-119">主要狀況指標是效能計數器，其臨界值是用於顯示使用者經驗問題。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="3cc1f-120">收集 KHI 資料通常是實施通話品質方法 (CQM) （主要是為了確保 Lync 使用者的品質音訊體驗）的第一步。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="3cc1f-121">KHIs 是除了標準的 Lync 監控解決方案 (（例如 System Center Operations Manager、綜合交易、監控伺服器) ，而不是那些解決方案）以外的使用。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="3cc1f-122">收集 KHI 效能計數器，並填入網路指南隨附的 KHI 試算表，以產生可協助您判斷 Lync 部署之伺服器健康情況的計分卡。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="3cc1f-123">一旦填滿後，它會引導您修復環境並對其他專案關係人提供進一步的洞察力。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="3cc1f-124">每月評估 KHIs，並將其併入任何部署的日常運作處理常式。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="3cc1f-125">下載 [Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677) 以查看完整的 KHIs 清單，並取得相關的試算表。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="3cc1f-126">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="3cc1f-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="3cc1f-127">在每一部 Lync Server 上執行 Lync Server 網路指南隨附的 KHI 腳本。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="3cc1f-128">這會在 [效能監視器] 內建立資料收集器，並將其命名為 KHI。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="3cc1f-129">依預設，每15秒會輪詢一次資料。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="3cc1f-130">在公司的工作日開始之前，請移至每一部 Lync 伺服器並啟動 KHI Data 收集器。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="3cc1f-131">在該天結束時，停止 KHI 資料收集器，並將資料複製到中央位置。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="3cc1f-132">使用 [效能監視器] 填滿 Lync Server 網路指南下載所包含的 KHI 試算表後，請將結果與建議的目標進行比較。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="3cc1f-133">所有伺服器角色的修正流程</span><span class="sxs-lookup"><span data-stu-id="3cc1f-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="3cc1f-134">針對 Lync 實施中的每一部伺服器，先驗證服務器的元件健康情況和系統效能是在所需的層級。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="3cc1f-135">只有在這之後，才應該查看與整體 Lync 實施中的伺服器角色相關的指示器。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="3cc1f-136">請先收集所有伺服器的 KHI 效能資料。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="3cc1f-137">針對每個系統角色 (稍後將在本檔中討論的詳細資料) 判斷基本系統元件是否符合建議的目標。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="3cc1f-138">否則，請先修正系統效能，然後重新收集 KHI 資料，並確保系統健康情況，再查看 Lync 實施中的伺服器角色特有的計量。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="3cc1f-139">所有角色的元件健康情況定義為：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="3cc1f-140">CPU 使用率 \< 80%</span><span class="sxs-lookup"><span data-stu-id="3cc1f-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="3cc1f-141">平均磁片寫入 \< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="3cc1f-142">平均磁片讀取 \< 10 毫秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="3cc1f-143">可用記憶體 \> 20% 的系統總 MB</span><span class="sxs-lookup"><span data-stu-id="3cc1f-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="3cc1f-144">網路佇列長度 \< 2</span><span class="sxs-lookup"><span data-stu-id="3cc1f-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="3cc1f-145">丟棄的封包 (入/出) = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="3cc1f-146">詞彙</span><span class="sxs-lookup"><span data-stu-id="3cc1f-146">Glossary</span></span>

<span data-ttu-id="3cc1f-147">此海報使用下列術語及首字母縮寫：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="3cc1f-148">以 MCU = 應用程式共用多點控制單位</span><span class="sxs-lookup"><span data-stu-id="3cc1f-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="3cc1f-149">AV MCU = Audio/Video MCU</span><span class="sxs-lookup"><span data-stu-id="3cc1f-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="3cc1f-150">IM MCU = 立即訊息 MCU</span><span class="sxs-lookup"><span data-stu-id="3cc1f-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="3cc1f-151">UCWA = 整合通訊網頁 API</span><span class="sxs-lookup"><span data-stu-id="3cc1f-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="3cc1f-152">AV Edge = 透過 Edge 遍歷音訊/視頻</span><span class="sxs-lookup"><span data-stu-id="3cc1f-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="3cc1f-153">AV 驗證 = Audio/Video 驗證</span><span class="sxs-lookup"><span data-stu-id="3cc1f-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="3cc1f-154">SIP 堆疊 = 包含 Lync 核心 SIP 實施</span><span class="sxs-lookup"><span data-stu-id="3cc1f-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="3cc1f-155">資料 Proxy = 用於 edge 會議</span><span class="sxs-lookup"><span data-stu-id="3cc1f-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="3cc1f-156">LySS = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="3cc1f-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="3cc1f-157">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-157">Front-end Servers</span></span>

<span data-ttu-id="3cc1f-158">除了基本元件健康情況之外，下列建議的 KHI 目標是前端伺服器特有的：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cc1f-159">功能區域</span><span class="sxs-lookup"><span data-stu-id="3cc1f-159">Functional area</span></span></th>
<th><span data-ttu-id="3cc1f-160">目標度量</span><span class="sxs-lookup"><span data-stu-id="3cc1f-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="3cc1f-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-162">MCU 健康狀態 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3cc1f-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc1f-163">Web 元件</span><span class="sxs-lookup"><span data-stu-id="3cc1f-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-164">通訊群組清單展開 AD 超時 &lt; 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="3cc1f-165">ABWQ 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="3cc1f-166">.LIS 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="3cc1f-167">驗證錯誤 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3cc1f-168">ASP.NET v4 要求遭到拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-169">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="3cc1f-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-170">平均傳入郵件處理 &lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3cc1f-171">撥出的回應丟棄 &lt; 1/秒傳入的要求中斷 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3cc1f-172">佇列延遲 &lt; 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3cc1f-173">過程延遲 &lt; 100 毫秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="3cc1f-174">節流要求 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="3cc1f-175">驗證錯誤 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3cc1f-176">傳入的郵件超時 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3cc1f-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="3cc1f-177">平均傳入郵件保留 &lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="3cc1f-178">流程式控制制的連接 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="3cc1f-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="3cc1f-179">平均輸出佇列延遲 &lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc1f-180">LySS</span><span class="sxs-lookup"><span data-stu-id="3cc1f-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-181">Storage Service DB 80 使用的空間百分比 &lt;</span><span class="sxs-lookup"><span data-stu-id="3cc1f-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="3cc1f-182"># 複製副本複寫失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="3cc1f-183"># 資料遺失事件 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-184">SQL</span><span class="sxs-lookup"><span data-stu-id="3cc1f-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-185">頁面壽命預期 &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3cc1f-186">批次要求數/秒 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="3cc1f-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="3cc1f-187">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-187">Backend SQL Servers</span></span>

<span data-ttu-id="3cc1f-188">除了基本元件健康情況之外，下列建議的 KHI 目標是針對 SQL server 所特有的：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cc1f-189">功能區域</span><span class="sxs-lookup"><span data-stu-id="3cc1f-189">Functional area</span></span></th>
<th><span data-ttu-id="3cc1f-190">目標度量</span><span class="sxs-lookup"><span data-stu-id="3cc1f-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-191">SQL</span><span class="sxs-lookup"><span data-stu-id="3cc1f-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-192">頁面壽命預期 &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="3cc1f-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="3cc1f-193">批次要求數/秒 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="3cc1f-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="3cc1f-194">轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="3cc1f-194">Mediation Servers</span></span>

<span data-ttu-id="3cc1f-195">除了基本元件健康情況之外，下列建議的 KHI 目標是轉送伺服器所特有的：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cc1f-196">功能區域</span><span class="sxs-lookup"><span data-stu-id="3cc1f-196">Functional area</span></span></th>
<th><span data-ttu-id="3cc1f-197">目標度量</span><span class="sxs-lookup"><span data-stu-id="3cc1f-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-198">轉送伺服器服務</span><span class="sxs-lookup"><span data-stu-id="3cc1f-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-199">載入呼叫失敗索引 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="3cc1f-200">因 Proxy 10 而失敗的通話 &lt;</span><span class="sxs-lookup"><span data-stu-id="3cc1f-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="3cc1f-201">閘道10導致呼叫失敗 &lt;</span><span class="sxs-lookup"><span data-stu-id="3cc1f-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="3cc1f-202">呼叫 () 拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="3cc1f-203">缺少媒體候選人 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="3cc1f-204">Media Connectivity 檢查失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="3cc1f-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="3cc1f-205">Edge Server</span><span class="sxs-lookup"><span data-stu-id="3cc1f-205">Edge Servers</span></span>

<span data-ttu-id="3cc1f-206">除了基本元件健康情況之外，下列建議的 KHI 目標是針對 edge server 所特有的：</span><span class="sxs-lookup"><span data-stu-id="3cc1f-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cc1f-207">功能區域</span><span class="sxs-lookup"><span data-stu-id="3cc1f-207">Functional area</span></span></th>
<th><span data-ttu-id="3cc1f-208">目標度量</span><span class="sxs-lookup"><span data-stu-id="3cc1f-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-209">AV 驗證</span><span class="sxs-lookup"><span data-stu-id="3cc1f-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-210">錯誤要求 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc1f-211">AV Edge</span><span class="sxs-lookup"><span data-stu-id="3cc1f-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-212">驗證失敗 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3cc1f-213">分配失敗 &lt; 20/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="3cc1f-214">每秒丟棄的封包 &lt;</span><span class="sxs-lookup"><span data-stu-id="3cc1f-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cc1f-215">資料 Proxy</span><span class="sxs-lookup"><span data-stu-id="3cc1f-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-216">節流伺服器連接 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="3cc1f-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="3cc1f-217">系統為節流 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="3cc1f-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cc1f-218">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="3cc1f-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="3cc1f-219">超過限制的連線數 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="3cc1f-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="3cc1f-220">傳送超時 &lt; 10</span><span class="sxs-lookup"><span data-stu-id="3cc1f-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="3cc1f-221">資料流程控制的連接 &lt; 100</span><span class="sxs-lookup"><span data-stu-id="3cc1f-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="3cc1f-222">傳入的要求丟棄 &lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="3cc1f-223">平均郵件處理 &lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="3cc1f-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3cc1f-224">另請參閱</span><span class="sxs-lookup"><span data-stu-id="3cc1f-224">See Also</span></span>


[<span data-ttu-id="3cc1f-225">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="3cc1f-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="3cc1f-226">主要健康情況指示器：維護狀況良好的 Lync 伺服器的基礎</span><span class="sxs-lookup"><span data-stu-id="3cc1f-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="3cc1f-227">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="3cc1f-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

