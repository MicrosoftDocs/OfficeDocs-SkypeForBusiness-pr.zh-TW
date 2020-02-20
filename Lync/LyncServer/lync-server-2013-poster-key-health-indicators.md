---
title: Lync Server 2013： 海報： 重要的健康狀態指標
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
ms.openlocfilehash: 2710e85eced76241f4946ef2746e544d07be941f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="c42ee-102">Lync Server 2013 中的索引鍵的健康狀態指標</span><span class="sxs-lookup"><span data-stu-id="c42ee-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c42ee-103">_**上次修改主題：** 2014年-02-10_</span><span class="sxs-lookup"><span data-stu-id="c42ee-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="c42ee-104">本文是隨附[機碼健康狀態指標： 維護狀況良好的 Lync 伺服器 Foundation](https://go.microsoft.com/fwlink/?linkid=391838)海報，您可以從下載中心下載。</span><span class="sxs-lookup"><span data-stu-id="c42ee-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="c42ee-105">![海報中描述疑難排解使用 KHI 資料](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "海報中描述疑難排解使用 KHI 資料")</span><span class="sxs-lookup"><span data-stu-id="c42ee-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="c42ee-106">您可以使用此海報以了解金鑰健康狀態指標 (KHIs)、 效能計數器臨界值的目標在於透露使用者體驗問題。</span><span class="sxs-lookup"><span data-stu-id="c42ee-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c42ee-107">收集 KHI 資料通常實作通話品質方法 (CQM) 的第一個步驟，這被著重於確保音訊品質的體驗 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="c42ee-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c42ee-108">如果您有關於如何使用 CQM 問題，您可以提交至 cqmfeedback@microsoft.com 問題。</span><span class="sxs-lookup"><span data-stu-id="c42ee-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="c42ee-109">海報說明下列領域：</span><span class="sxs-lookup"><span data-stu-id="c42ee-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="c42ee-110">什麼是索引鍵健康狀態指標？</span><span class="sxs-lookup"><span data-stu-id="c42ee-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="c42ee-111">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="c42ee-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="c42ee-112">所有伺服器角色的補救流程</span><span class="sxs-lookup"><span data-stu-id="c42ee-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="c42ee-113">詞彙</span><span class="sxs-lookup"><span data-stu-id="c42ee-113">Glossary</span></span>

  - <span data-ttu-id="c42ee-114">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-114">Front-end Servers</span></span>

  - <span data-ttu-id="c42ee-115">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="c42ee-116">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-116">Mediation Servers</span></span>

  - <span data-ttu-id="c42ee-117">Edge Server</span><span class="sxs-lookup"><span data-stu-id="c42ee-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="c42ee-118">什麼是索引鍵健康狀態指標？</span><span class="sxs-lookup"><span data-stu-id="c42ee-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="c42ee-119">索引鍵健康狀態指標是效能計數器臨界值的目標在於透露使用者體驗問題。</span><span class="sxs-lookup"><span data-stu-id="c42ee-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="c42ee-120">收集 KHI 資料通常實作通話品質方法 (CQM) 的第一個步驟，這被著重於確保音訊品質的體驗 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="c42ee-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="c42ee-121">KHIs 可用除了標準的 Lync 監控解決方案 （例如 System Center Operations Manager，綜合交易，監控伺服器），而不是這些解決方案取代。</span><span class="sxs-lookup"><span data-stu-id="c42ee-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="c42ee-122">收集 KHI 效能計數器，並填入 KHI 試算表隨附網路的快顯功能表會產生可協助您決定 Lync 部署的伺服器健康狀況的計分卡。</span><span class="sxs-lookup"><span data-stu-id="c42ee-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="c42ee-123">一旦填入，它會帶領您修復環境，並提供見解給其他專案關係人。</span><span class="sxs-lookup"><span data-stu-id="c42ee-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="c42ee-124">在每月付款評估 KHIs，並將它們納入任何部署進行中作業程序。</span><span class="sxs-lookup"><span data-stu-id="c42ee-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="c42ee-125">下載[Lync Server 網路指南](https://go.microsoft.com/fwlink/p/?linkid=390677)若要查看 KHIs 的完整清單，以取得相關的試算表。</span><span class="sxs-lookup"><span data-stu-id="c42ee-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="c42ee-126">收集 KHI 資料</span><span class="sxs-lookup"><span data-stu-id="c42ee-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="c42ee-127">執行 Lync Server 網路指南 》，每個 Lync 伺服器上所隨附的 KHI 指令碼。</span><span class="sxs-lookup"><span data-stu-id="c42ee-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="c42ee-128">這會建立資料收集器效能監視器的內容，並加以命名 KHI。</span><span class="sxs-lookup"><span data-stu-id="c42ee-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="c42ee-129">根據預設，資料會輪詢每隔 15 秒。</span><span class="sxs-lookup"><span data-stu-id="c42ee-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="c42ee-130">開始之前的公司的工作天，請移至每個 Lync 伺服器並啟動 KHI 資料收集器。</span><span class="sxs-lookup"><span data-stu-id="c42ee-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="c42ee-131">在那天結束時，停止 KHI 資料收集器，並將資料複製到一個集中的位置。</span><span class="sxs-lookup"><span data-stu-id="c42ee-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="c42ee-132">使用效能監視器來填滿隨附的 Lync Server 網路指南下載 KHI 試算表中後, 比較結果為建議的目標。</span><span class="sxs-lookup"><span data-stu-id="c42ee-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="c42ee-133">所有伺服器角色的補救流程</span><span class="sxs-lookup"><span data-stu-id="c42ee-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="c42ee-134">針對 Lync 實作中每部伺服器，請先確認伺服器元件的健康狀況和系統效能等於或高於所需的層級。</span><span class="sxs-lookup"><span data-stu-id="c42ee-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="c42ee-135">後，才應該您查看與整體 Lync 實作中的伺服器角色相關的指標。</span><span class="sxs-lookup"><span data-stu-id="c42ee-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="c42ee-136">首先 KHI 效能資料收集的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="c42ee-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="c42ee-137">針對每個系統角色 （本文稍後所述的詳細資料） 會決定在基本系統元件是否符合建議的目標。</span><span class="sxs-lookup"><span data-stu-id="c42ee-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="c42ee-138">如果沒有，修復的系統效能然後重新收集 KHI 資料，並確保系統健康狀況之前先查看 Lync 實作中的伺服器角色的特定評量。</span><span class="sxs-lookup"><span data-stu-id="c42ee-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="c42ee-139">元件運作情況的所有角色定義如下：</span><span class="sxs-lookup"><span data-stu-id="c42ee-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="c42ee-140">CPU 使用率\<80%</span><span class="sxs-lookup"><span data-stu-id="c42ee-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="c42ee-141">平均磁碟寫入\<10 毫秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="c42ee-142">磁碟讀取的平均\<10 毫秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="c42ee-143">可用記憶體\>20%系統總 MB</span><span class="sxs-lookup"><span data-stu-id="c42ee-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="c42ee-144">網路佇列長度\<2</span><span class="sxs-lookup"><span data-stu-id="c42ee-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="c42ee-145">捨棄封包 （輸入 / 輸出） = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="c42ee-146">詞彙</span><span class="sxs-lookup"><span data-stu-id="c42ee-146">Glossary</span></span>

<span data-ttu-id="c42ee-147">此海報中使用下列詞彙和縮略字：</span><span class="sxs-lookup"><span data-stu-id="c42ee-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="c42ee-148">為 MCU = 應用程式共用多點控制項單位</span><span class="sxs-lookup"><span data-stu-id="c42ee-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="c42ee-149">AV MCU = 音訊/視訊 MCU</span><span class="sxs-lookup"><span data-stu-id="c42ee-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="c42ee-150">IM MCU = 立即訊息的 MCU</span><span class="sxs-lookup"><span data-stu-id="c42ee-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="c42ee-151">UCWA = Unified 的 Communications Web API</span><span class="sxs-lookup"><span data-stu-id="c42ee-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="c42ee-152">AV Edge = 音訊/視訊 edge 透過周遊</span><span class="sxs-lookup"><span data-stu-id="c42ee-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="c42ee-153">AV 驗證 = Audio/Video 驗證</span><span class="sxs-lookup"><span data-stu-id="c42ee-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="c42ee-154">SIP 堆疊 = 包含 Lync 核心 SIP 實作</span><span class="sxs-lookup"><span data-stu-id="c42ee-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="c42ee-155">資料 Proxy = 用於 edge 會議</span><span class="sxs-lookup"><span data-stu-id="c42ee-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="c42ee-156">LySS = Lync 儲存體服務</span><span class="sxs-lookup"><span data-stu-id="c42ee-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="c42ee-157">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-157">Front-end Servers</span></span>

<span data-ttu-id="c42ee-158">下列建議 KHI 目標特有除了基本元件健康情況的前端伺服器：</span><span class="sxs-lookup"><span data-stu-id="c42ee-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c42ee-159">職能區域</span><span class="sxs-lookup"><span data-stu-id="c42ee-159">Functional area</span></span></th>
<th><span data-ttu-id="c42ee-160">目標評量</span><span class="sxs-lookup"><span data-stu-id="c42ee-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-161">IM/AS/AV MCU</span><span class="sxs-lookup"><span data-stu-id="c42ee-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="c42ee-162">MCU 健康狀態&lt;2</span><span class="sxs-lookup"><span data-stu-id="c42ee-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c42ee-163">Web 元件</span><span class="sxs-lookup"><span data-stu-id="c42ee-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="c42ee-164">通訊群組清單擴充 AD 逾時&lt;0</span><span class="sxs-lookup"><span data-stu-id="c42ee-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="c42ee-165">ABWQ 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="c42ee-166">LIS 失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="c42ee-167">驗證錯誤&lt;1/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c42ee-168">ASP.NET v4 要求拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-169">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="c42ee-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c42ee-170">平均內送郵件處理&lt;1 秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c42ee-171">捨棄連入的回應&lt;1/秒的傳入要求卸除&lt;1/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c42ee-172">佇列延遲&lt;100 毫秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c42ee-173">預存程序延遲&lt;100 毫秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="c42ee-174">節流要求 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="c42ee-175">驗證錯誤&lt;1/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c42ee-176">內送郵件逾時&lt;2</span><span class="sxs-lookup"><span data-stu-id="c42ee-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="c42ee-177">平均內送郵件保留&lt;1 秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="c42ee-178">流程控制的連線&lt;2</span><span class="sxs-lookup"><span data-stu-id="c42ee-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="c42ee-179">平均出佇列延遲&lt;2 秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c42ee-180">LySS</span><span class="sxs-lookup"><span data-stu-id="c42ee-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="c42ee-181">儲存體服務 DB 所使用的空間 % &lt; 80</span><span class="sxs-lookup"><span data-stu-id="c42ee-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="c42ee-182">#複本複寫失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="c42ee-183">#資料遺失事件的 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-184">SQL</span><span class="sxs-lookup"><span data-stu-id="c42ee-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="c42ee-185">頁面 life expectancy &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="c42ee-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c42ee-186">批次要求 / 秒&lt;2500年</span><span class="sxs-lookup"><span data-stu-id="c42ee-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="c42ee-187">後端 SQL 伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-187">Backend SQL Servers</span></span>

<span data-ttu-id="c42ee-188">下列建議 KHI 目標特有除了基本元件健康情況的 SQL 伺服器：</span><span class="sxs-lookup"><span data-stu-id="c42ee-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c42ee-189">職能區域</span><span class="sxs-lookup"><span data-stu-id="c42ee-189">Functional area</span></span></th>
<th><span data-ttu-id="c42ee-190">目標評量</span><span class="sxs-lookup"><span data-stu-id="c42ee-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-191">SQL</span><span class="sxs-lookup"><span data-stu-id="c42ee-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="c42ee-192">頁面 life expectancy &gt; 300 秒。</span><span class="sxs-lookup"><span data-stu-id="c42ee-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="c42ee-193">批次要求 / 秒&lt;2500年</span><span class="sxs-lookup"><span data-stu-id="c42ee-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="c42ee-194">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c42ee-194">Mediation Servers</span></span>

<span data-ttu-id="c42ee-195">下列建議 KHI 目標特有除了基本元件健康情況的中繼伺服器：</span><span class="sxs-lookup"><span data-stu-id="c42ee-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c42ee-196">職能區域</span><span class="sxs-lookup"><span data-stu-id="c42ee-196">Functional area</span></span></th>
<th><span data-ttu-id="c42ee-197">目標評量</span><span class="sxs-lookup"><span data-stu-id="c42ee-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-198">中繼伺服器服務</span><span class="sxs-lookup"><span data-stu-id="c42ee-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="c42ee-199">載入呼叫失敗索引 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="c42ee-200">由於 Proxy 通話失敗之&lt;10</span><span class="sxs-lookup"><span data-stu-id="c42ee-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="c42ee-201">由於閘道的通話失敗之&lt;10</span><span class="sxs-lookup"><span data-stu-id="c42ee-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="c42ee-202">呼叫 （近或拉） 拒絕 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="c42ee-203">媒體應徵者遺失 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="c42ee-204">媒體連線檢查失敗 = 0</span><span class="sxs-lookup"><span data-stu-id="c42ee-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="c42ee-205">Edge Server</span><span class="sxs-lookup"><span data-stu-id="c42ee-205">Edge Servers</span></span>

<span data-ttu-id="c42ee-206">下列建議 KHI 目標特有的 edge server，除了基本元件健康情況：</span><span class="sxs-lookup"><span data-stu-id="c42ee-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c42ee-207">職能區域</span><span class="sxs-lookup"><span data-stu-id="c42ee-207">Functional area</span></span></th>
<th><span data-ttu-id="c42ee-208">目標評量</span><span class="sxs-lookup"><span data-stu-id="c42ee-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-209">AV 驗證</span><span class="sxs-lookup"><span data-stu-id="c42ee-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="c42ee-210">不正確的要求&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c42ee-211">AV Edge</span><span class="sxs-lookup"><span data-stu-id="c42ee-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="c42ee-212">驗證]。 失敗&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c42ee-213">配置失敗&lt;20/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="c42ee-214">捨棄封包&lt;300/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c42ee-215">資料 Proxy</span><span class="sxs-lookup"><span data-stu-id="c42ee-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="c42ee-216">節流伺服器連線&lt;3</span><span class="sxs-lookup"><span data-stu-id="c42ee-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="c42ee-217">系統會節流&lt;1</span><span class="sxs-lookup"><span data-stu-id="c42ee-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c42ee-218">SIP 堆疊</span><span class="sxs-lookup"><span data-stu-id="c42ee-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="c42ee-219">超過限制中斷連線&lt;1</span><span class="sxs-lookup"><span data-stu-id="c42ee-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="c42ee-220">傳送閒置逾&lt;10</span><span class="sxs-lookup"><span data-stu-id="c42ee-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="c42ee-221">流程控制的連線&lt;100</span><span class="sxs-lookup"><span data-stu-id="c42ee-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="c42ee-222">捨棄的傳入要求&lt;1/秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="c42ee-223">平均郵件處理&lt;3 秒</span><span class="sxs-lookup"><span data-stu-id="c42ee-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c42ee-224">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c42ee-224">See Also</span></span>


[<span data-ttu-id="c42ee-225">Lync Server 網路指南</span><span class="sxs-lookup"><span data-stu-id="c42ee-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="c42ee-226">維護狀況良好的 Lync 伺服器 Foundation 主要的健康狀態指標：</span><span class="sxs-lookup"><span data-stu-id="c42ee-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="c42ee-227">Lync 通話品質方法</span><span class="sxs-lookup"><span data-stu-id="c42ee-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

