---
title: Lync Server 2013： 通話詳細資料報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e14ca8565216efbdeaae3060587d5d18d919876
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="e179f-102">Lync Server 2013 中的通話詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="e179f-102">Call Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e179f-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="e179f-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e179f-104">Call Detail Report 提供個別通話; 的詳細的檢視報告中包含幾乎所有的經驗品質計量及統計資料收集的 Lync Server，分成報表區段如下：</span><span class="sxs-lookup"><span data-stu-id="e179f-104">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="e179f-105">通話資訊</span><span class="sxs-lookup"><span data-stu-id="e179f-105">Call Information</span></span>

  - <span data-ttu-id="e179f-106">呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="e179f-106">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="e179f-107">被呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="e179f-107">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="e179f-108">呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="e179f-108">Caller Client Event</span></span>

  - <span data-ttu-id="e179f-109">被呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="e179f-109">Callee Client Event</span></span>

  - <span data-ttu-id="e179f-110">音訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="e179f-110">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="e179f-111">視訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="e179f-111">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="e179f-112">音訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="e179f-112">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="e179f-113">視訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="e179f-113">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="e179f-p101">請注意，在指定報告上所見的類別及計量取決於兩個因素：工作階段類型，以及工作階段中所使用的端點類型。例如，純音訊通話不會報告視訊資料流計量，這是因為該通話沒有視訊資料流。同樣地，報告可能會只列出呼叫者統計資料，而沒有被呼叫者統計資料。這通常是因為被呼叫者並非使用 SIP 相容的裝置。端點會負責在通話結束時報告統計資料；不過行動電話 (對 SIP 或 SIP 統計資料一無所悉) 就無法報告該類資訊。如果您與某人通話，而他們使用行動電話接聽，則通話結束時將無法從該行動電話取得報告。</span><span class="sxs-lookup"><span data-stu-id="e179f-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="e179f-120">當您想確認指定通話為何發生媒體品質問題的確切原因時，[通話詳細資料報告] 最派得上用場。</span><span class="sxs-lookup"><span data-stu-id="e179f-120">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="e179f-121">存取通話詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="e179f-121">Accessing the Call Detail Report</span></span>

<span data-ttu-id="e179f-122">您可從下列報告中存取 [通話詳細資料報告]：</span><span class="sxs-lookup"><span data-stu-id="e179f-122">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="e179f-123">[Lync Server 2013 中的 Location Report](lync-server-2013-location-report.md) (按一下 [通話數] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="e179f-123">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="e179f-124">[Lync Server 2013 中的 Media Quality Summary Report](lync-server-2013-media-quality-summary-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="e179f-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="e179f-125">[Lync Server 2013 中的媒體品質比較報告](lync-server-2013-media-quality-comparison-report.md)([ [Lync Server 2013 中 Call List Report](lync-server-2013-call-list-report.md) ，然後按一下 [詳細資料] 計量）。</span><span class="sxs-lookup"><span data-stu-id="e179f-125">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="e179f-126">[Lync Server 2013 中的 Server Performance Report](lync-server-2013-server-performance-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="e179f-126">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="e179f-127">[Lync Server 2013 中 Call List Report](lync-server-2013-call-list-report.md) (按一下 [詳細資料] 計量）</span><span class="sxs-lookup"><span data-stu-id="e179f-127">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="e179f-128">Call Detail Report 內您可以從存取[裝置報告在 Lync Server 2013](lync-server-2013-device-report.md)藉由按一下下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="e179f-128">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e179f-129">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="e179f-129">Capture device</span></span>

  - <span data-ttu-id="e179f-130">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="e179f-130">Render device</span></span>

<span data-ttu-id="e179f-131">按一下 [A/V Edge Server] 計量也可存取 [伺服器媒體品質趨勢報告]。</span><span class="sxs-lookup"><span data-stu-id="e179f-131">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="e179f-132">發揮通話詳細資料報告的最大效用</span><span class="sxs-lookup"><span data-stu-id="e179f-132">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="e179f-p102">[通話詳細資料報告] 通常涵蓋超過 250 個不同的計量，包括麥克風時間戳記漂移、低 SNR 時間及近端回音時間等項目。如果不記得這些計量實際上測量什麼，可嘗試將滑鼠移至計量標籤上，通常會顯示工具提示來說明該計量。</span><span class="sxs-lookup"><span data-stu-id="e179f-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="e179f-p103">如果找不到某個計量，可在搜尋方塊中輸入部分計量標籤，然後按一下 [搜尋]。例如，如果找不到 [低 Low SNR 時間] 計量，可在搜尋方塊中輸入 SNR，然後按一下 [搜尋]。</span><span class="sxs-lookup"><span data-stu-id="e179f-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="e179f-137">請注意報表僅會追蹤通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e179f-137">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="e179f-138">呼叫本身不在記錄中。</span><span class="sxs-lookup"><span data-stu-id="e179f-138">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e179f-139">篩選</span><span class="sxs-lookup"><span data-stu-id="e179f-139">Filters</span></span>

<span data-ttu-id="e179f-p105">無。您無法篩選詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="e179f-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e179f-142">計量</span><span class="sxs-lookup"><span data-stu-id="e179f-142">Metrics</span></span>

<span data-ttu-id="e179f-143">下表列出每個通話的詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="e179f-143">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="e179f-144">詳細通話報告計量</span><span class="sxs-lookup"><span data-stu-id="e179f-144">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e179f-145">名稱</span><span class="sxs-lookup"><span data-stu-id="e179f-145">Name</span></span></th>
<th><span data-ttu-id="e179f-146">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="e179f-146">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e179f-147">描述</span><span class="sxs-lookup"><span data-stu-id="e179f-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e179f-148"><strong>  呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-148"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-149">否</span><span class="sxs-lookup"><span data-stu-id="e179f-149">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-p106">撥打通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="e179f-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-152"><strong>呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-152"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-153">否</span><span class="sxs-lookup"><span data-stu-id="e179f-153">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-154">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="e179f-154">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-155"><strong>呼叫者者端點</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-155"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-156">否</span><span class="sxs-lookup"><span data-stu-id="e179f-156">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-157">用來撥打通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="e179f-157">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-158"><strong>呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-158"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-159">否</span><span class="sxs-lookup"><span data-stu-id="e179f-159">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-160">撥打通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="e179f-160">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-161"><strong>通話開始</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-161"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-162">否</span><span class="sxs-lookup"><span data-stu-id="e179f-162">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-163">啟動通話的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="e179f-163">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-164"><strong>中繼伺服器旁路通話</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-164"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-165">否</span><span class="sxs-lookup"><span data-stu-id="e179f-165">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-166">指出通話是連接至 PSTN 語音閘道或完整 IP-PBX，而未通過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="e179f-166">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-167"><strong>呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-167"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-168">否</span><span class="sxs-lookup"><span data-stu-id="e179f-168">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-169">呼叫者電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="e179f-169">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-170"><strong>呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-170"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-171">否</span><span class="sxs-lookup"><span data-stu-id="e179f-171">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-172">安裝在啟動通話之使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="e179f-172">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-173"><strong>呼叫者 CPU 核心編號</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-173"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-174">否</span><span class="sxs-lookup"><span data-stu-id="e179f-174">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-175">啟動通話者所使用電腦的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="e179f-175">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-176"><strong>呼叫者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-176"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-177">否</span><span class="sxs-lookup"><span data-stu-id="e179f-177">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-178">啟動通話者所使用電腦的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="e179f-178">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-179"><strong>呼叫者 CPU 模擬</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-179"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-180">否</span><span class="sxs-lookup"><span data-stu-id="e179f-180">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-181">啟動通話者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="e179f-181">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-182"><strong>被呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-182"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-183">否</span><span class="sxs-lookup"><span data-stu-id="e179f-183">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-p107">受邀加入通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="e179f-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-186"><strong>被呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-186"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-187">否</span><span class="sxs-lookup"><span data-stu-id="e179f-187">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-188">被呼叫使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="e179f-188">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-189"><strong>被呼叫者端點</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-189"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-190">否</span><span class="sxs-lookup"><span data-stu-id="e179f-190">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-191">用來接收通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="e179f-191">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-192"><strong>被呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-192"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-193">否</span><span class="sxs-lookup"><span data-stu-id="e179f-193">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-194">接收通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="e179f-194">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-195"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-195"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-196">否</span><span class="sxs-lookup"><span data-stu-id="e179f-196">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-197">通話時間長度。</span><span class="sxs-lookup"><span data-stu-id="e179f-197">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-198"><strong>媒體旁路警告旗標</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-198"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-199">否</span><span class="sxs-lookup"><span data-stu-id="e179f-199">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-200">略過中繼伺服器時發出的警告。</span><span class="sxs-lookup"><span data-stu-id="e179f-200">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-201"><strong>被呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-201"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-202">否</span><span class="sxs-lookup"><span data-stu-id="e179f-202">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-203">被呼叫使用者的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="e179f-203">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-204"><strong>被呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-204"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-205">否</span><span class="sxs-lookup"><span data-stu-id="e179f-205">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-206">安裝在被呼叫使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="e179f-206">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-207"><strong>被呼叫者核心編號</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-207"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-208">否</span><span class="sxs-lookup"><span data-stu-id="e179f-208">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-209">被呼叫者所使用電腦中的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="e179f-209">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e179f-210"><strong>被呼叫者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-210"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-211">否</span><span class="sxs-lookup"><span data-stu-id="e179f-211">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-212">被呼叫者所使用電腦中的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="e179f-212">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e179f-213"><strong>被呼叫者 CPU 虛擬</strong></span><span class="sxs-lookup"><span data-stu-id="e179f-213"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="e179f-214">否</span><span class="sxs-lookup"><span data-stu-id="e179f-214">No</span></span></p></td>
<td><p><span data-ttu-id="e179f-215">被呼叫者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="e179f-215">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

