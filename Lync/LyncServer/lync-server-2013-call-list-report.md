---
title: Lync Server 2013：通話清單報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d9d437b32907108d5666ef9e1b175c170030585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526290"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="9b3fc-102">Lync Server 2013 中的通話清單報告</span><span class="sxs-lookup"><span data-stu-id="9b3fc-102">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b3fc-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9b3fc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9b3fc-104">通話清單報告提供經驗品質 (QoE 在組織中撥打和接收的個別通話) 度量。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="9b3fc-105">請注意，實際報告的衡量值將取決於您存取通話清單報告的方式。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="9b3fc-106">例如，如果您 [在 Lync Server 2013 的設備報告中](lync-server-2013-device-report.md)開啟報表，您會看到下列的計量值，也就是在裝置報表上報告的計量：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="9b3fc-107">來電者的麥克風</span><span class="sxs-lookup"><span data-stu-id="9b3fc-107">Caller's microphone</span></span>

  - <span data-ttu-id="9b3fc-108">來電者的喇叭</span><span class="sxs-lookup"><span data-stu-id="9b3fc-108">Caller's speaker</span></span>

  - <span data-ttu-id="9b3fc-109">被呼叫者的麥克風</span><span class="sxs-lookup"><span data-stu-id="9b3fc-109">Callee's microphone</span></span>

  - <span data-ttu-id="9b3fc-110">被呼叫者的喇叭</span><span class="sxs-lookup"><span data-stu-id="9b3fc-110">Callee's speaker</span></span>

  - <span data-ttu-id="9b3fc-111">語音切換時間的比例</span><span class="sxs-lookup"><span data-stu-id="9b3fc-111">Ratio of voice switch time</span></span>

<span data-ttu-id="9b3fc-112">不過，如果您在 [Lync Server 2013 的位置報告中](lync-server-2013-location-report.md)開啟通話清單報告，您就不會看到任何這類度量。相反地，您會看到如下的計量：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="9b3fc-113">來回行程 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-113">Round trip (ms)</span></span>

  - <span data-ttu-id="9b3fc-114">MOS) 降級 (</span><span class="sxs-lookup"><span data-stu-id="9b3fc-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="9b3fc-115">封包遺失</span><span class="sxs-lookup"><span data-stu-id="9b3fc-115">Packet loss</span></span>

  - <span data-ttu-id="9b3fc-116">抖動 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-116">Jitter (ms)</span></span>

<span data-ttu-id="9b3fc-117">這些是在位置報告上報告的統計資料。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="9b3fc-118">不過，從通話清單報告您可以隨時按一下 [詳細資料] 度量，以提供任何呼叫的完整 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="9b3fc-119">存取通話清單報告</span><span class="sxs-lookup"><span data-stu-id="9b3fc-119">Accessing the Call List Report</span></span>

<span data-ttu-id="9b3fc-120">您可以從下列任何報告中存取通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="9b3fc-121">[Lync Server 2013 (中的位置報告](lync-server-2013-location-report.md)，方法是按一下 [通話量] 或 [不良通話百分比] 度量) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="9b3fc-122">[Lync Server 2013 (中的裝置報表](lync-server-2013-device-report.md)，方法是按一下 [通話量] 或 [通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="9b3fc-123">[Lync Server 2013 (中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)，請按一下 [通話量] 或 [不良通話百分比] 度量) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="9b3fc-124">[Lync server 2013 (中的伺服器效能報告](lync-server-2013-server-performance-report.md)，按一下 [通話量] 或 [通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="9b3fc-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="9b3fc-125">在 [通話清單報告] 中，按一下 [詳細資料] 度量，即可存取 [Lync Server 2013 中的 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="9b3fc-126">充分利用通話清單報告</span><span class="sxs-lookup"><span data-stu-id="9b3fc-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="9b3fc-127">如果您無法記下某些「通話清單報告」度量 (例如，) 實際測量的比例語音切換時間，請將滑鼠停留在公制標籤上;然後會出現工具提示，提供度量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="9b3fc-128">篩選</span><span class="sxs-lookup"><span data-stu-id="9b3fc-128">Filters</span></span>

<span data-ttu-id="9b3fc-129">無。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-129">None.</span></span> <span data-ttu-id="9b3fc-130">您無法篩選通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="9b3fc-131">指標</span><span class="sxs-lookup"><span data-stu-id="9b3fc-131">Metrics</span></span>

<span data-ttu-id="9b3fc-132">下表列出通話清單報告中每次通話所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="9b3fc-133">通話清單報告計量</span><span class="sxs-lookup"><span data-stu-id="9b3fc-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9b3fc-134">姓名</span><span class="sxs-lookup"><span data-stu-id="9b3fc-134">Name</span></span></th>
<th><span data-ttu-id="9b3fc-135">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="9b3fc-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="9b3fc-136">描述</span><span class="sxs-lookup"><span data-stu-id="9b3fc-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-137"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-138">否</span><span class="sxs-lookup"><span data-stu-id="9b3fc-138">No</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-139">當您按一下此專案時，報告會顯示通話的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-141">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-142">發起通話之人員的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-143"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-144">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-145">呼叫者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-146"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-147">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-148">通話的開始日期與時間。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-149"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-150">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-151">通話的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-152"><strong>呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-153">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-154">起始通話之人員端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-155"><strong>被呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-156">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-157">呼叫者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-158"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-159">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-160">即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-160">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="9b3fc-161">在100毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-161">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9b3fc-162">高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-162">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="9b3fc-163">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-163">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-164"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-165">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-166">通話期間 (MOS) 效能的平均平均觀點量。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="9b3fc-167">降級值的範圍從低0.0 到高5.0。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="9b3fc-168">值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="9b3fc-169">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="9b3fc-170">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="9b3fc-171">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-171">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="9b3fc-172">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-172">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-173"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-174">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-175">RTP 封包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-175">Average rate of RTP packet loss.</span></span> <span data-ttu-id="9b3fc-176">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-176">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="9b3fc-177">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-177">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-178"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-179">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-180">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9b3fc-181"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-182"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-183">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-184">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-184">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="9b3fc-185"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-185">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-186"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-187">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-188">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-188">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="9b3fc-189"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-189">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9b3fc-190"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-191">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-192">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-192">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="9b3fc-193"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-193">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9b3fc-194"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="9b3fc-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="9b3fc-195">是</span><span class="sxs-lookup"><span data-stu-id="9b3fc-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="9b3fc-196">無線通訊連結的類型。</span><span class="sxs-lookup"><span data-stu-id="9b3fc-196">Type of wireless communication link.</span></span> <span data-ttu-id="9b3fc-197">這通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="9b3fc-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="9b3fc-198">繼 電器</span><span class="sxs-lookup"><span data-stu-id="9b3fc-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="9b3fc-199">直接</span><span class="sxs-lookup"><span data-stu-id="9b3fc-199">Direct</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

