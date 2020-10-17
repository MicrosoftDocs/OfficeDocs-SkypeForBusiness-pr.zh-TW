---
title: Lync Server 2013：通話清單報告
description: Lync Server 2013：通話清單報告。
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
ms.openlocfilehash: 5b08d4c5f3011facc9cd8d4f6b2800638f3cc896
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561689"
---
# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="78195-103">Lync Server 2013 中的通話清單報告</span><span class="sxs-lookup"><span data-stu-id="78195-103">Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78195-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="78195-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="78195-105">通話清單報告提供經驗品質 (QoE 在組織中撥打和接收的個別通話) 度量。</span><span class="sxs-lookup"><span data-stu-id="78195-105">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="78195-106">請注意，實際報告的衡量值將取決於您存取通話清單報告的方式。</span><span class="sxs-lookup"><span data-stu-id="78195-106">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="78195-107">例如，如果您 [在 Lync Server 2013 的設備報告中](lync-server-2013-device-report.md)開啟報表，您會看到下列的計量值，也就是在裝置報表上報告的計量：</span><span class="sxs-lookup"><span data-stu-id="78195-107">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="78195-108">來電者的麥克風</span><span class="sxs-lookup"><span data-stu-id="78195-108">Caller's microphone</span></span>

  - <span data-ttu-id="78195-109">來電者的喇叭</span><span class="sxs-lookup"><span data-stu-id="78195-109">Caller's speaker</span></span>

  - <span data-ttu-id="78195-110">被呼叫者的麥克風</span><span class="sxs-lookup"><span data-stu-id="78195-110">Callee's microphone</span></span>

  - <span data-ttu-id="78195-111">被呼叫者的喇叭</span><span class="sxs-lookup"><span data-stu-id="78195-111">Callee's speaker</span></span>

  - <span data-ttu-id="78195-112">語音切換時間的比例</span><span class="sxs-lookup"><span data-stu-id="78195-112">Ratio of voice switch time</span></span>

<span data-ttu-id="78195-113">不過，如果您在 [Lync Server 2013 的位置報告中](lync-server-2013-location-report.md)開啟通話清單報告，您就不會看到任何這類度量。相反地，您會看到如下的計量：</span><span class="sxs-lookup"><span data-stu-id="78195-113">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="78195-114">來回行程 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="78195-114">Round trip (ms)</span></span>

  - <span data-ttu-id="78195-115">MOS) 降級 (</span><span class="sxs-lookup"><span data-stu-id="78195-115">Degradation (MOS)</span></span>

  - <span data-ttu-id="78195-116">封包遺失</span><span class="sxs-lookup"><span data-stu-id="78195-116">Packet loss</span></span>

  - <span data-ttu-id="78195-117">抖動 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="78195-117">Jitter (ms)</span></span>

<span data-ttu-id="78195-118">這些是在位置報告上報告的統計資料。</span><span class="sxs-lookup"><span data-stu-id="78195-118">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="78195-119">不過，從通話清單報告您可以隨時按一下 [詳細資料] 度量，以提供任何呼叫的完整 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="78195-119">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="78195-120">存取通話清單報告</span><span class="sxs-lookup"><span data-stu-id="78195-120">Accessing the Call List Report</span></span>

<span data-ttu-id="78195-121">您可以從下列任何報告中存取通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="78195-121">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="78195-122">[Lync Server 2013 (中的位置報告](lync-server-2013-location-report.md)，方法是按一下 [通話量] 或 [不良通話百分比] 度量) </span><span class="sxs-lookup"><span data-stu-id="78195-122">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="78195-123">[Lync Server 2013 (中的裝置報表](lync-server-2013-device-report.md)，方法是按一下 [通話量] 或 [通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="78195-123">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="78195-124">[Lync Server 2013 (中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)，請按一下 [通話量] 或 [不良通話百分比] 度量) </span><span class="sxs-lookup"><span data-stu-id="78195-124">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="78195-125">[Lync server 2013 (中的伺服器效能報告](lync-server-2013-server-performance-report.md)，按一下 [通話量] 或 [通話百分比] 度量值) </span><span class="sxs-lookup"><span data-stu-id="78195-125">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="78195-126">在 [通話清單報告] 中，按一下 [詳細資料] 度量，即可存取 [Lync Server 2013 中的 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="78195-126">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="78195-127">充分利用通話清單報告</span><span class="sxs-lookup"><span data-stu-id="78195-127">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="78195-128">如果您無法記下某些「通話清單報告」度量 (例如，) 實際測量的比例語音切換時間，請將滑鼠停留在公制標籤上;然後會出現工具提示，提供度量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="78195-128">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="78195-129">篩選</span><span class="sxs-lookup"><span data-stu-id="78195-129">Filters</span></span>

<span data-ttu-id="78195-130">無。</span><span class="sxs-lookup"><span data-stu-id="78195-130">None.</span></span> <span data-ttu-id="78195-131">您無法篩選通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="78195-131">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="78195-132">指標</span><span class="sxs-lookup"><span data-stu-id="78195-132">Metrics</span></span>

<span data-ttu-id="78195-133">下表列出通話清單報告中每次通話所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="78195-133">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="78195-134">通話清單報告計量</span><span class="sxs-lookup"><span data-stu-id="78195-134">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78195-135">姓名</span><span class="sxs-lookup"><span data-stu-id="78195-135">Name</span></span></th>
<th><span data-ttu-id="78195-136">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="78195-136">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="78195-137">描述</span><span class="sxs-lookup"><span data-stu-id="78195-137">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78195-138"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="78195-138"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-139">否</span><span class="sxs-lookup"><span data-stu-id="78195-139">No</span></span></p></td>
<td><p><span data-ttu-id="78195-140">當您按一下此專案時，報告會顯示通話的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="78195-140">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-141"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="78195-141"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-142">是</span><span class="sxs-lookup"><span data-stu-id="78195-142">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-143">發起通話之人員的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="78195-143">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-144"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="78195-144"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-145">是</span><span class="sxs-lookup"><span data-stu-id="78195-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-146">呼叫者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="78195-146">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-147"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="78195-147"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-148">是</span><span class="sxs-lookup"><span data-stu-id="78195-148">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-149">通話的開始日期與時間。</span><span class="sxs-lookup"><span data-stu-id="78195-149">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-150"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="78195-150"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-151">是</span><span class="sxs-lookup"><span data-stu-id="78195-151">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-152">通話的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="78195-152">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-153"><strong>呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="78195-153"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-154">是</span><span class="sxs-lookup"><span data-stu-id="78195-154">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-155">起始通話之人員端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="78195-155">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-156"><strong>被呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="78195-156"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-157">是</span><span class="sxs-lookup"><span data-stu-id="78195-157">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-158">呼叫者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="78195-158">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-159"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="78195-159"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-160">是</span><span class="sxs-lookup"><span data-stu-id="78195-160">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-161">即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。</span><span class="sxs-lookup"><span data-stu-id="78195-161">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="78195-162">在100毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="78195-162">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="78195-163">高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="78195-163">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="78195-164">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="78195-164">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-165"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="78195-165"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-166">是</span><span class="sxs-lookup"><span data-stu-id="78195-166">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-167">通話期間 (MOS) 效能的平均平均觀點量。</span><span class="sxs-lookup"><span data-stu-id="78195-167">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="78195-168">降級值的範圍從低0.0 到高5.0。</span><span class="sxs-lookup"><span data-stu-id="78195-168">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="78195-169">值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="78195-169">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="78195-170">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="78195-170">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="78195-171">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="78195-171">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="78195-172">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="78195-172">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="78195-173">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="78195-173">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-174"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="78195-174"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-175">是</span><span class="sxs-lookup"><span data-stu-id="78195-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-176">RTP 封包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="78195-176">Average rate of RTP packet loss.</span></span> <span data-ttu-id="78195-177">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="78195-177">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="78195-178">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="78195-178">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-179"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="78195-179"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-180">是</span><span class="sxs-lookup"><span data-stu-id="78195-180">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-181">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="78195-181">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="78195-182"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="78195-182">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-183"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="78195-183"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-184">是</span><span class="sxs-lookup"><span data-stu-id="78195-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-185">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="78195-185">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="78195-186"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="78195-186">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-187"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="78195-187"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-188">是</span><span class="sxs-lookup"><span data-stu-id="78195-188">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-189">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="78195-189">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="78195-190"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="78195-190">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78195-191"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="78195-191"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-192">是</span><span class="sxs-lookup"><span data-stu-id="78195-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-193">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="78195-193">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="78195-194"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="78195-194">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78195-195"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="78195-195"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="78195-196">是</span><span class="sxs-lookup"><span data-stu-id="78195-196">Yes</span></span></p></td>
<td><p><span data-ttu-id="78195-197">無線通訊連結的類型。</span><span class="sxs-lookup"><span data-stu-id="78195-197">Type of wireless communication link.</span></span> <span data-ttu-id="78195-198">這通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="78195-198">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78195-199">繼 電器</span><span class="sxs-lookup"><span data-stu-id="78195-199">Relay</span></span></p></li>
<li><p><span data-ttu-id="78195-200">直接</span><span class="sxs-lookup"><span data-stu-id="78195-200">Direct</span></span></p></li>
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

