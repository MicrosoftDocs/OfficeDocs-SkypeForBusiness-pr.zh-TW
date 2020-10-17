---
title: Lync Server 2013：詳細通話報告
description: Lync Server 2013：詳細通話報告。
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
ms.openlocfilehash: d72ae6c1c1ec869041eee5b0dc35941c33609710
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561769"
---
# <a name="call-detail-report-in-lync-server-2013"></a><span data-ttu-id="b4b97-103">Lync Server 2013 中的詳細通話報告</span><span class="sxs-lookup"><span data-stu-id="b4b97-103">Call Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4b97-104">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="b4b97-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="b4b97-105">[通話詳細資料包告] 提供個別通話的詳細資訊，請參閱報告包括所有的經驗品質統計資料，以及 Lync Server 收集的統計資料，劃分成報表區段，例如：</span><span class="sxs-lookup"><span data-stu-id="b4b97-105">The Call Detail Report provides a detailed look at an individual call; the report includes nearly all the Quality of Experience metrics and statistics collected by Lync Server, divided into report sections such as:</span></span>

  - <span data-ttu-id="b4b97-106">通話資訊</span><span class="sxs-lookup"><span data-stu-id="b4b97-106">Call Information</span></span>

  - <span data-ttu-id="b4b97-107">呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="b4b97-107">Caller Device and Signal Metrics</span></span>

  - <span data-ttu-id="b4b97-108">被呼叫者裝置和訊號計量</span><span class="sxs-lookup"><span data-stu-id="b4b97-108">Callee Device and Signal metrics</span></span>

  - <span data-ttu-id="b4b97-109">呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="b4b97-109">Caller Client Event</span></span>

  - <span data-ttu-id="b4b97-110">被呼叫者用戶端事件</span><span class="sxs-lookup"><span data-stu-id="b4b97-110">Callee Client Event</span></span>

  - <span data-ttu-id="b4b97-111">音訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="b4b97-111">Audio Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b4b97-112">視訊資料流 (呼叫者至被呼叫者)</span><span class="sxs-lookup"><span data-stu-id="b4b97-112">Video Stream (Caller to Callee)</span></span>

  - <span data-ttu-id="b4b97-113">音訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="b4b97-113">Audio Stream (Callee to Caller)</span></span>

  - <span data-ttu-id="b4b97-114">視訊資料流 (被呼叫者至呼叫者)</span><span class="sxs-lookup"><span data-stu-id="b4b97-114">Video Stream (Callee to Caller)</span></span>

<span data-ttu-id="b4b97-p101">請注意，在指定報告上所見的類別及計量取決於兩個因素：工作階段類型，以及工作階段中所使用的端點類型。例如，純音訊通話不會報告視訊資料流計量，這是因為該通話沒有視訊資料流。同樣地，報告可能會只列出呼叫者統計資料，而沒有被呼叫者統計資料。這通常是因為被呼叫者並非使用 SIP 相容的裝置。端點會負責在通話結束時報告統計資料；不過行動電話 (對 SIP 或 SIP 統計資料一無所悉) 就無法報告該類資訊。如果您與某人通話，而他們使用行動電話接聽，則通話結束時將無法從該行動電話取得報告。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p101">Keep in mind that the categories and the metrics you see on a given report depend on two things: the type of session and the type of endpoints used in the session. For example, an audio-only call will not report metrics for video streams; that's because the call didn't have a video stream. Likewise, you might have a report that lists caller statistics but not callee statistics. That's typically because the callee was not using a SIP-compliant device. Endpoints are responsible for reporting statistics at the end of a call; however, a cell phone (which knows nothing about SIP or SIP statistics) is unable to report that kind of information. If you call someone and they answer you on their cell phone, you will not get a report from that cell phone when the call ends.</span></span>

<span data-ttu-id="b4b97-121">當您想確認指定通話為何發生媒體品質問題的確切原因時，[通話詳細資料報告] 最派得上用場。</span><span class="sxs-lookup"><span data-stu-id="b4b97-121">The Call Detail Report is most useful when you are trying to determine exactly why a given call experienced media quality problems.</span></span>

<div>

## <a name="accessing-the-call-detail-report"></a><span data-ttu-id="b4b97-122">存取通話詳細資料報告</span><span class="sxs-lookup"><span data-stu-id="b4b97-122">Accessing the Call Detail Report</span></span>

<span data-ttu-id="b4b97-123">您可從下列報告中存取 [通話詳細資料報告]：</span><span class="sxs-lookup"><span data-stu-id="b4b97-123">The Call Detail Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="b4b97-124">[在 [Lync Server 2013] 中的位置報告](lync-server-2013-location-report.md)，按一下 [通話量] 或 [低通話百分比] 計量 () </span><span class="sxs-lookup"><span data-stu-id="b4b97-124">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking either the Call volume or the Poor call percentage metric)</span></span>

  - <span data-ttu-id="b4b97-125">[Lync Server 2013 (中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)：按一下 [通話量] 或 [通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="b4b97-125">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b4b97-126">[Lync server 2013 (中的媒體質量比較報告](lync-server-2013-media-quality-comparison-report.md)，方法是按一下 [ [lync server 2013] 中的 [通話清單報告](lync-server-2013-call-list-report.md)]，然後按一下 [詳細資料] 度量) 。</span><span class="sxs-lookup"><span data-stu-id="b4b97-126">The [Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (by clicking the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) and then clicking the Detail metric).</span></span>

  - <span data-ttu-id="b4b97-127">[在 Lync Server 2013 (中](lync-server-2013-server-performance-report.md)，按一下 [通話量] 或 [通話不良百分比] 度量，以執行伺服器效能報告) </span><span class="sxs-lookup"><span data-stu-id="b4b97-127">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking either the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="b4b97-128">[Lync Server 2013 (中的通話清單報告](lync-server-2013-call-list-report.md)，請按一下詳細資料度量) </span><span class="sxs-lookup"><span data-stu-id="b4b97-128">The [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) (by clicking the Detail metric)</span></span>

<span data-ttu-id="b4b97-129">從 [通話詳細資料包告] 中，按一下下列其中一個計量，即可 [在 Lync Server 2013 中存取裝置報告](lync-server-2013-device-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="b4b97-129">From within the Call Detail Report you can access the [Device Report in Lync Server 2013](lync-server-2013-device-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="b4b97-130">擷取裝置</span><span class="sxs-lookup"><span data-stu-id="b4b97-130">Capture device</span></span>

  - <span data-ttu-id="b4b97-131">轉換裝置</span><span class="sxs-lookup"><span data-stu-id="b4b97-131">Render device</span></span>

<span data-ttu-id="b4b97-132">按一下 [A/V Edge Server] 計量也可存取 [伺服器媒體品質趨勢報告]。</span><span class="sxs-lookup"><span data-stu-id="b4b97-132">You can also access the Server Media Quality Trend Report by clicking the A/V edge server metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a><span data-ttu-id="b4b97-133">發揮通話詳細資料報告的最大效用</span><span class="sxs-lookup"><span data-stu-id="b4b97-133">Making the Best Use of the Call Detail Report</span></span>

<span data-ttu-id="b4b97-p102">[通話詳細資料報告] 通常涵蓋超過 250 個不同的計量，包括麥克風時間戳記漂移、低 SNR 時間及近端回音時間等項目。如果不記得這些計量實際上測量什麼，可嘗試將滑鼠移至計量標籤上，通常會顯示工具提示來說明該計量。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p102">The Call Detail Report typically includes over 250 different metrics, including such items as Microphone timestamp drift, Low SNR time, and Near end to echo time. If you can't remember what all of these metrics actually measure, try holding your mouse over the metric label; often-times, a tooltip will appear describing that metric.</span></span>

<span data-ttu-id="b4b97-p103">如果找不到某個計量，可在搜尋方塊中輸入部分計量標籤，然後按一下 [搜尋]。例如，如果找不到 [低 Low SNR 時間] 計量，可在搜尋方塊中輸入 SNR，然後按一下 [搜尋]。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p103">If you have problems locating a metric, type part of the metric label in the search box and then click Find. For example, if you can't find the Low SNR time metric, type SNR in the search box and then click Find.</span></span>

<span data-ttu-id="b4b97-138">請注意，報告只追蹤通話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b4b97-138">Note that the report only tracks information about a call.</span></span> <span data-ttu-id="b4b97-139">不會記錄通話本身。</span><span class="sxs-lookup"><span data-stu-id="b4b97-139">The call itself is not recorded.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b4b97-140">篩選</span><span class="sxs-lookup"><span data-stu-id="b4b97-140">Filters</span></span>

<span data-ttu-id="b4b97-p105">無。您無法篩選詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p105">None. You cannot filter the Call Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b4b97-143">指標</span><span class="sxs-lookup"><span data-stu-id="b4b97-143">Metrics</span></span>

<span data-ttu-id="b4b97-144">下表列出每個通話的詳細通話報告。</span><span class="sxs-lookup"><span data-stu-id="b4b97-144">The following table lists the information provided in the Call Detail Report for each call.</span></span>

### <a name="call-detail-report-metrics"></a><span data-ttu-id="b4b97-145">詳細通話報告計量</span><span class="sxs-lookup"><span data-stu-id="b4b97-145">Call Detail Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4b97-146">姓名</span><span class="sxs-lookup"><span data-stu-id="b4b97-146">Name</span></span></th>
<th><span data-ttu-id="b4b97-147">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="b4b97-147">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b4b97-148">描述</span><span class="sxs-lookup"><span data-stu-id="b4b97-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-149"><strong>  呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-149"><strong>Caller PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-150">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-150">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-p106">撥打通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p106">P-Asserted-Identity of the user who initiated the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-153"><strong>呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-153"><strong>Caller URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-154">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-154">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-155">撥打通話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b4b97-155">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-156"><strong>呼叫者者端點</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-156"><strong>Caller endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-157">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-157">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-158">用來撥打通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="b4b97-158">Device used to make the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-159"><strong>呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-159"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-160">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-160">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-161">撥打通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="b4b97-161">Software used on the device that made the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-162"><strong>通話開始</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-162"><strong>Call start</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-163">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-163">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-164">啟動通話的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="b4b97-164">Date and time that the call was initially placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-165"><strong>中繼伺服器旁路通話</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-165"><strong>Mediation Server bypass call</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-166">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-166">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-167">指出通話是連接至 PSTN 語音閘道或完整 IP-PBX，而未通過中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4b97-167">Indicates whether the call connected to a PSTN voice gateway or qualified IP-PBX without passing through the Mediation Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-168"><strong>呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-168"><strong>Caller OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-169">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-169">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-170">呼叫者電腦的作業系統。</span><span class="sxs-lookup"><span data-stu-id="b4b97-170">Operating system of the caller's computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-171"><strong>呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-171"><strong>Caller CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-172">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-172">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-173">安裝在啟動通話之使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="b4b97-173">CPU installed in the computer of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-174"><strong>呼叫者 CPU 核心編號</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-174"><strong>Caller CPU core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-175">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-175">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-176">啟動通話者所使用電腦的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="b4b97-176">Processor number in the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-177"><strong>呼叫者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-177"><strong>Caller CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-178">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-178">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-179">啟動通話者所使用電腦的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="b4b97-179">Clock speed of the CPU of the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-180"><strong>呼叫者 CPU 模擬</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-180"><strong>Caller CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-181">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-181">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-182">啟動通話者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="b4b97-182">Virtualization (if any) used on the computer used by the person who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-183"><strong>被呼叫者 PAI</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-183"><strong>Callee PAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-184">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-184">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-p107">受邀加入通話之使用者的 P-Asserted-Identity。P-Asserted-Identity 可用來傳達信任網路中之使用者經驗證的身分識別。</span><span class="sxs-lookup"><span data-stu-id="b4b97-p107">P-Asserted-Identity of the user who was invited to join the call. The P-Asserted-Identity is used to convey the proven identity of a user within a trusted network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-187"><strong>被呼叫者 URI</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-187"><strong>Callee URI</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-188">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-188">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-189">被呼叫使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="b4b97-189">SIP address of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-190"><strong>被呼叫者端點</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-190"><strong>Callee endpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-191">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-191">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-192">用來接收通話的裝置。</span><span class="sxs-lookup"><span data-stu-id="b4b97-192">Device used to receive the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-193"><strong>被呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-193"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-194">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-194">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-195">接收通話之裝置上所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="b4b97-195">Software used on the device that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-196"><strong>Duration</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-196"><strong>Duration</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-197">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-197">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-198">通話時間長度。</span><span class="sxs-lookup"><span data-stu-id="b4b97-198">Length of time for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-199"><strong>媒體旁路警告旗標</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-199"><strong>Media bypass warning flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-200">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-200">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-201">略過中繼伺服器時發出的警告。</span><span class="sxs-lookup"><span data-stu-id="b4b97-201">Warning issued when the Mediation Server was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-202"><strong>被呼叫者 OS</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-202"><strong>Callee OS</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-203">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-203">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-204">被呼叫使用者的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="b4b97-204">Operating system of the computer for the user who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-205"><strong>被呼叫者 CPU</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-205"><strong>Callee CPU</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-206">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-206">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-207">安裝在被呼叫使用者電腦上的 CPU。</span><span class="sxs-lookup"><span data-stu-id="b4b97-207">CPU installed in the computer of the user who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-208"><strong>被呼叫者核心編號</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-208"><strong>Callee core number</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-209">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-209">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-210">被呼叫者所使用電腦中的處理器編號。</span><span class="sxs-lookup"><span data-stu-id="b4b97-210">Processor number in the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b97-211"><strong>被呼叫者 CPU 速度</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-211"><strong>Callee CPU speed</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-212">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-212">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-213">被呼叫者所使用電腦中的 CPU 時脈速度。</span><span class="sxs-lookup"><span data-stu-id="b4b97-213">Clock speed of the CPU of the computer used by the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b97-214"><strong>被呼叫者 CPU 虛擬</strong></span><span class="sxs-lookup"><span data-stu-id="b4b97-214"><strong>Callee CPU virtualization</strong></span></span></p></td>
<td><p><span data-ttu-id="b4b97-215">否</span><span class="sxs-lookup"><span data-stu-id="b4b97-215">No</span></span></p></td>
<td><p><span data-ttu-id="b4b97-216">被呼叫者所使用電腦上的虛擬化 (若有的話)。</span><span class="sxs-lookup"><span data-stu-id="b4b97-216">Virtualization (if any) used on the computer used by the person who was called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

