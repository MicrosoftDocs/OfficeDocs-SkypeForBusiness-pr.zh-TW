---
title: Lync Server 2013：海報：主要健康情況指示符
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9454197642ac87f5d8bc0d768795854d792f9a31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="e5212-102">Lync Server 2013 中的主要健康情況指示</span><span class="sxs-lookup"><span data-stu-id="e5212-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5212-103">_**主題上次修改日期：** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="e5212-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="e5212-104">本文將提供[主要的健康情況指示符：維護健康的 Lync 伺服器海報的基礎](http://go.microsoft.com/fwlink/?linkid=391838)，您可以從下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="e5212-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="e5212-105">![標牌說明使用 KHI 資料](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "海報說明使用 KHI 資料進行疑難排解")的疑難排解</span><span class="sxs-lookup"><span data-stu-id="e5212-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="e5212-106">您可以使用此海報來瞭解主要的健康情況指標（KHIs）、效能計數器，以及可顯示使用者經驗問題的閾值。</span><span class="sxs-lookup"><span data-stu-id="e5212-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="e5212-107">收集 KHI 資料通常是實施通話品質方法（CQM）的第一個步驟，主要是為了確保 Lync 使用者的音質音訊體驗。</span><span class="sxs-lookup"><span data-stu-id="e5212-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="e5212-108">如果您有關于如何使用 CQM 的問題，您可以將問題提交至 cqmfeedback@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="e5212-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="e5212-109">海報說明下欄區域：</span><span class="sxs-lookup"><span data-stu-id="e5212-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="e5212-110">什麼是關鍵健康情況指示器？</span><span class="sxs-lookup"><span data-stu-id="e5212-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="e5212-111">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="e5212-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="e5212-112">所有伺服器角色的修正流程</span><span class="sxs-lookup"><span data-stu-id="e5212-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="e5212-113">詞彙表</span><span class="sxs-lookup"><span data-stu-id="e5212-113">Glossary</span></span>

  - <span data-ttu-id="e5212-114">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-114">Front-end Servers</span></span>

  - <span data-ttu-id="e5212-115">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="e5212-116">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-116">Mediation Servers</span></span>

  - <span data-ttu-id="e5212-117">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="e5212-118">什麼是關鍵健康情況指示器？</span><span class="sxs-lookup"><span data-stu-id="e5212-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="e5212-119">金鑰健康情況指標是效能計數器，其閾值可產生使用者經驗問題。</span><span class="sxs-lookup"><span data-stu-id="e5212-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="e5212-120">收集 KHI 資料通常是實施通話品質方法（CQM）的第一個步驟，主要是為了確保 Lync 使用者的音質音訊體驗。</span><span class="sxs-lookup"><span data-stu-id="e5212-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="e5212-121">除了標準的 Lync 監視解決方案（例如 System Center Operations Manager、綜合交易、監視伺服器）之外，還會使用 KHIs，而不是這些方案。</span><span class="sxs-lookup"><span data-stu-id="e5212-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="e5212-122">收集 KHI 效能計數器，並填入隨附網路指南的 KHI 試算表，以產生可協助您判斷 Lync 部署的伺服器健康情況的計分卡。</span><span class="sxs-lookup"><span data-stu-id="e5212-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="e5212-123">完成填入之後，它會引導您修復環境，並提供其他相關人員的深入見解。</span><span class="sxs-lookup"><span data-stu-id="e5212-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="e5212-124">每月評估 KHIs，並將它們併入任何部署的日常運作程式中。</span><span class="sxs-lookup"><span data-stu-id="e5212-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="e5212-125">下載[Lync Server 網路指南](http://go.microsoft.com/fwlink/p/?linkid=390677)以查看完整的 KHIs 清單，並取得相關的試算表。</span><span class="sxs-lookup"><span data-stu-id="e5212-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="e5212-126">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="e5212-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="e5212-127">在每個 Lync 伺服器上，執行 Lync Server 網路指南隨附的 KHI 腳本。</span><span class="sxs-lookup"><span data-stu-id="e5212-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="e5212-128">這會在效能監視器中建立資料收集器，並將它命名為 KHI。</span><span class="sxs-lookup"><span data-stu-id="e5212-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="e5212-129">根據預設，資料會每隔15秒輪詢一次。</span><span class="sxs-lookup"><span data-stu-id="e5212-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="e5212-130">在公司的工作日開始之前，請移至每個 Lync 伺服器，然後啟動 KHI 資料收集器。</span><span class="sxs-lookup"><span data-stu-id="e5212-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="e5212-131">在該日期結束時，請停止 KHI 資料收集器，然後將資料複製到中央位置。</span><span class="sxs-lookup"><span data-stu-id="e5212-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="e5212-132">使用效能監視器填入 Lync Server 網路指南隨附的 KHI 試算表之後，請將結果與建議的目標進行比較。</span><span class="sxs-lookup"><span data-stu-id="e5212-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="e5212-133">所有伺服器角色的修正流程</span><span class="sxs-lookup"><span data-stu-id="e5212-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="e5212-134">針對 Lync 實現中的每個伺服器，首先確認伺服器的元件健康情況與系統效能位於想要的層級。</span><span class="sxs-lookup"><span data-stu-id="e5212-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="e5212-135">只有在該情況下，才能查看在整個 Lync 實現中與伺服器角色相關的標記。</span><span class="sxs-lookup"><span data-stu-id="e5212-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="e5212-136">首先，收集所有伺服器的 KHI 效能資料。</span><span class="sxs-lookup"><span data-stu-id="e5212-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="e5212-137">針對每個系統角色（本檔稍後討論的詳細資料）判斷基本系統元件是否符合建議的目標。</span><span class="sxs-lookup"><span data-stu-id="e5212-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="e5212-138">如果不是，請修正系統效能，然後重新收集 KHI 資料，並確保系統健康情況，然後才能在 Lync 實現中查看伺服器角色的特定度量單位。</span><span class="sxs-lookup"><span data-stu-id="e5212-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="e5212-139">所有角色的元件健康情況定義為：</span><span class="sxs-lookup"><span data-stu-id="e5212-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="e5212-140">CPU 利用率\< 80%</span><span class="sxs-lookup"><span data-stu-id="e5212-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="e5212-141">平均磁片寫入\< 10 ms</span><span class="sxs-lookup"><span data-stu-id="e5212-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="e5212-142">平均磁片讀取\< 10 ms</span><span class="sxs-lookup"><span data-stu-id="e5212-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="e5212-143">可用的\>記憶體20% 系統總 MB</span><span class="sxs-lookup"><span data-stu-id="e5212-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="e5212-144">網路佇列長度\< 2</span><span class="sxs-lookup"><span data-stu-id="e5212-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="e5212-145">捨棄的資料包（in/out） = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="e5212-146">詞彙表</span><span class="sxs-lookup"><span data-stu-id="e5212-146">Glossary</span></span>

<span data-ttu-id="e5212-147">此海報中使用下列條款與縮寫：</span><span class="sxs-lookup"><span data-stu-id="e5212-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="e5212-148">在 MCU = 應用程式共用多重點控制單元時</span><span class="sxs-lookup"><span data-stu-id="e5212-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="e5212-149">AV MCU = 音訊/視頻 MCU</span><span class="sxs-lookup"><span data-stu-id="e5212-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="e5212-150">IM MCU = 立即訊息 MCU</span><span class="sxs-lookup"><span data-stu-id="e5212-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="e5212-151">UCWA = 整合通訊網頁 API</span><span class="sxs-lookup"><span data-stu-id="e5212-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="e5212-152">AV 邊緣 = 透過邊緣遍歷音訊/視頻</span><span class="sxs-lookup"><span data-stu-id="e5212-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="e5212-153">AV 驗證 = 音訊/視頻驗證</span><span class="sxs-lookup"><span data-stu-id="e5212-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="e5212-154">SIP 堆疊 = 包含 Lync 的核心 SIP 實現</span><span class="sxs-lookup"><span data-stu-id="e5212-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="e5212-155">資料 Proxy = 用於 edge 會議</span><span class="sxs-lookup"><span data-stu-id="e5212-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="e5212-156">LySS = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="e5212-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="e5212-157">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-157">Front-end Servers</span></span>

<span data-ttu-id="e5212-158">除了基本的元件健康情況之外，下列建議的 KHI 目標是針對前端伺服器所專用：</span><span class="sxs-lookup"><span data-stu-id="e5212-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5212-159">功能區域</span><span class="sxs-lookup"><span data-stu-id="e5212-159">Functional area</span></span></th>
<th><span data-ttu-id="e5212-160">目標度量</span><span class="sxs-lookup"><span data-stu-id="e5212-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5212-161">AS/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="e5212-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="e5212-162">MCU 健康狀態&lt;2</span><span class="sxs-lookup"><span data-stu-id="e5212-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5212-163">網頁元件</span><span class="sxs-lookup"><span data-stu-id="e5212-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="e5212-164">通訊群組清單展開廣告&lt;超時0</span><span class="sxs-lookup"><span data-stu-id="e5212-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="e5212-165">ABWQ 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="e5212-166">.LIS 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="e5212-167">驗證錯誤&lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e5212-168">ASP.NET v4 要求遭到拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5212-169">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="e5212-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="e5212-170">平均傳入訊息處理&lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="e5212-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="e5212-171">傳入回應丟棄&lt; 1/秒傳入的要求&lt;中斷 1/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e5212-172">佇列滯後&lt;時間 100 ms</span><span class="sxs-lookup"><span data-stu-id="e5212-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="e5212-173">過程中&lt;的延遲時間 100 ms</span><span class="sxs-lookup"><span data-stu-id="e5212-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="e5212-174">受限制的要求 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="e5212-175">驗證錯誤&lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e5212-176">傳入的訊息超時&lt; 2</span><span class="sxs-lookup"><span data-stu-id="e5212-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="e5212-177">平均傳入訊息保留&lt; 1 秒</span><span class="sxs-lookup"><span data-stu-id="e5212-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="e5212-178">流程式控制制的&lt;連接2</span><span class="sxs-lookup"><span data-stu-id="e5212-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="e5212-179">Avg. 超時列隊延遲&lt; 2 秒</span><span class="sxs-lookup"><span data-stu-id="e5212-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5212-180">LySS</span><span class="sxs-lookup"><span data-stu-id="e5212-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="e5212-181">Storage Services DB &lt; 80 使用的空間百分比</span><span class="sxs-lookup"><span data-stu-id="e5212-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="e5212-182">#複製複本複製失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="e5212-183">#資料遺失事件 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5212-184">語句</span><span class="sxs-lookup"><span data-stu-id="e5212-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="e5212-185">頁生命預期&gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="e5212-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="e5212-186">批次要求/ &lt;秒2500</span><span class="sxs-lookup"><span data-stu-id="e5212-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="e5212-187">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-187">Backend SQL Servers</span></span>

<span data-ttu-id="e5212-188">除了基本的元件健康情況之外，下列建議的 KHI 目標是由 SQL server 所專用：</span><span class="sxs-lookup"><span data-stu-id="e5212-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5212-189">功能區域</span><span class="sxs-lookup"><span data-stu-id="e5212-189">Functional area</span></span></th>
<th><span data-ttu-id="e5212-190">目標度量</span><span class="sxs-lookup"><span data-stu-id="e5212-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5212-191">語句</span><span class="sxs-lookup"><span data-stu-id="e5212-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="e5212-192">頁生命預期&gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="e5212-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="e5212-193">批次要求/ &lt;秒2500</span><span class="sxs-lookup"><span data-stu-id="e5212-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="e5212-194">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-194">Mediation Servers</span></span>

<span data-ttu-id="e5212-195">除了基本的元件健康情況之外，下列建議的 KHI 目標是針對轉送伺服器所專用的：</span><span class="sxs-lookup"><span data-stu-id="e5212-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5212-196">功能區域</span><span class="sxs-lookup"><span data-stu-id="e5212-196">Functional area</span></span></th>
<th><span data-ttu-id="e5212-197">目標度量</span><span class="sxs-lookup"><span data-stu-id="e5212-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5212-198">中繼伺服器服務</span><span class="sxs-lookup"><span data-stu-id="e5212-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="e5212-199">載入通話失敗索引 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="e5212-200">由於 Proxy &lt;10 而失敗的通話</span><span class="sxs-lookup"><span data-stu-id="e5212-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="e5212-201">閘道&lt;10 導致無法通話</span><span class="sxs-lookup"><span data-stu-id="e5212-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="e5212-202">來電（或撥出）遭到拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="e5212-203">媒體候選人遺失 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="e5212-204">媒體連線檢查失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="e5212-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="e5212-205">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="e5212-205">Edge Servers</span></span>

<span data-ttu-id="e5212-206">除了基本的元件健康情況之外，下列建議的 KHI 目標是針對邊緣伺服器所專用：</span><span class="sxs-lookup"><span data-stu-id="e5212-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5212-207">功能區域</span><span class="sxs-lookup"><span data-stu-id="e5212-207">Functional area</span></span></th>
<th><span data-ttu-id="e5212-208">目標度量</span><span class="sxs-lookup"><span data-stu-id="e5212-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5212-209">防病毒驗證</span><span class="sxs-lookup"><span data-stu-id="e5212-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="e5212-210">錯誤的&lt;要求 20/sec</span><span class="sxs-lookup"><span data-stu-id="e5212-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5212-211">AV 邊緣</span><span class="sxs-lookup"><span data-stu-id="e5212-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="e5212-212">驗證失敗&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="e5212-213">分攤失敗&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="e5212-214">丟棄&lt;300/秒的 Packets</span><span class="sxs-lookup"><span data-stu-id="e5212-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5212-215">資料 Proxy</span><span class="sxs-lookup"><span data-stu-id="e5212-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="e5212-216">[已限制&lt;伺服器連接] 3</span><span class="sxs-lookup"><span data-stu-id="e5212-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="e5212-217">系統是節流&lt;1</span><span class="sxs-lookup"><span data-stu-id="e5212-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5212-218">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="e5212-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="e5212-219">超過限制的連線&lt;數1</span><span class="sxs-lookup"><span data-stu-id="e5212-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="e5212-220">傳送已超時&lt;10</span><span class="sxs-lookup"><span data-stu-id="e5212-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="e5212-221">流程式控制制的&lt;連線100</span><span class="sxs-lookup"><span data-stu-id="e5212-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="e5212-222">來電中斷&lt; 1/秒</span><span class="sxs-lookup"><span data-stu-id="e5212-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="e5212-223">平均處理郵件處理&lt; 3 秒</span><span class="sxs-lookup"><span data-stu-id="e5212-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5212-224">請參閱</span><span class="sxs-lookup"><span data-stu-id="e5212-224">See Also</span></span>


[<span data-ttu-id="e5212-225">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="e5212-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="e5212-226">金鑰健康指示：維護正常 Lync 伺服器的基礎</span><span class="sxs-lookup"><span data-stu-id="e5212-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="e5212-227">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="e5212-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

