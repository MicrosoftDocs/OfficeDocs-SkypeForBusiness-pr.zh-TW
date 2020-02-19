---
title: Lync Server 2013： 通話清單報告
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
ms.openlocfilehash: 0b53aa6929f5719b3d291e38cdfe3265cc0458f1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134229"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="935fb-102">Lync Server 2013 中的通話清單報告</span><span class="sxs-lookup"><span data-stu-id="935fb-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="935fb-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="935fb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="935fb-104">Call List Report 提供個別通話進行與接收您組織中的經驗品質 (QoE) 計量。</span><span class="sxs-lookup"><span data-stu-id="935fb-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="935fb-105">請注意，實際的計量報告取決於您如何存取通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="935fb-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="935fb-106">例如，如果您從[裝置報告在 Lync Server 2013 中](lync-server-2013-device-report.md)開啟報告，您會看到下列項目，也會在 「 裝置報告報告的評量等量值：</span><span class="sxs-lookup"><span data-stu-id="935fb-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="935fb-107">發話者的麥克風</span><span class="sxs-lookup"><span data-stu-id="935fb-107">Caller's microphone</span></span>

  - <span data-ttu-id="935fb-108">發話者的喇叭</span><span class="sxs-lookup"><span data-stu-id="935fb-108">Caller's speaker</span></span>

  - <span data-ttu-id="935fb-109">受話者的麥克風</span><span class="sxs-lookup"><span data-stu-id="935fb-109">Callee's microphone</span></span>

  - <span data-ttu-id="935fb-110">受話者的喇叭</span><span class="sxs-lookup"><span data-stu-id="935fb-110">Callee's speaker</span></span>

  - <span data-ttu-id="935fb-111">語音交換時間的比率</span><span class="sxs-lookup"><span data-stu-id="935fb-111">Ratio of voice switch time</span></span>

<span data-ttu-id="935fb-112">不過，如果您從[Lync Server 2013 中的 Location Report](lync-server-2013-location-report.md)開啟通話清單報告，您不會看到任何這些度量資訊;相反地，您會看到如下的計量：</span><span class="sxs-lookup"><span data-stu-id="935fb-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="935fb-113">往返時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="935fb-113">Round trip (ms)</span></span>

  - <span data-ttu-id="935fb-114">降低 (MOS)</span><span class="sxs-lookup"><span data-stu-id="935fb-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="935fb-115">封包遺失</span><span class="sxs-lookup"><span data-stu-id="935fb-115">Packet loss</span></span>

  - <span data-ttu-id="935fb-116">抖動 (ms)</span><span class="sxs-lookup"><span data-stu-id="935fb-116">Jitter (ms)</span></span>

<span data-ttu-id="935fb-117">這些是上 Location Report 報告的評量。</span><span class="sxs-lookup"><span data-stu-id="935fb-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="935fb-118">然而，從 Call List Report 您可以隨時按一下提供任何通話的完整 QoE 資訊的詳細資料] 計量。</span><span class="sxs-lookup"><span data-stu-id="935fb-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="935fb-119">存取通話清單報告</span><span class="sxs-lookup"><span data-stu-id="935fb-119">Accessing the Call List Report</span></span>

<span data-ttu-id="935fb-120">可以從任何下列報告存取通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="935fb-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="935fb-121">[Lync Server 2013 中的 Location Report](lync-server-2013-location-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="935fb-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="935fb-122">[Lync Server 2013 中的 Device Report](lync-server-2013-device-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="935fb-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="935fb-123">[Lync Server 2013 中的 Media Quality Summary Report](lync-server-2013-media-quality-summary-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="935fb-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="935fb-124">[Lync Server 2013 中的 Server Performance Report](lync-server-2013-server-performance-report.md) (按一下 [通話數量] 或 [收訊不良通話百分比] 計量）</span><span class="sxs-lookup"><span data-stu-id="935fb-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="935fb-125">Call List Report 中您可以從存取[Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)詳細資料] 計量，即可。</span><span class="sxs-lookup"><span data-stu-id="935fb-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="935fb-126">通話清單報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="935fb-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="935fb-127">如果您忘記了哪些部分 （例如比率語音交換時間） 的通話清單報告計量實際測量，將滑鼠停留到計量標籤，工具提示會再出現提供該計量的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="935fb-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="935fb-128">篩選</span><span class="sxs-lookup"><span data-stu-id="935fb-128">Filters</span></span>

<span data-ttu-id="935fb-129">無。</span><span class="sxs-lookup"><span data-stu-id="935fb-129">None.</span></span> <span data-ttu-id="935fb-130">您無法篩選 Call List Report。</span><span class="sxs-lookup"><span data-stu-id="935fb-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="935fb-131">計量</span><span class="sxs-lookup"><span data-stu-id="935fb-131">Metrics</span></span>

<span data-ttu-id="935fb-132">下表列出每個呼叫 Call List Report 提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="935fb-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="935fb-133">通話清單報告計量</span><span class="sxs-lookup"><span data-stu-id="935fb-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="935fb-134">名稱</span><span class="sxs-lookup"><span data-stu-id="935fb-134">Name</span></span></th>
<th><span data-ttu-id="935fb-135">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="935fb-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="935fb-136">描述</span><span class="sxs-lookup"><span data-stu-id="935fb-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="935fb-137"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-138">否</span><span class="sxs-lookup"><span data-stu-id="935fb-138">No</span></span></p></td>
<td><p><span data-ttu-id="935fb-139">當您按一下此項目時，報告就會顯示其他資訊通話。</span><span class="sxs-lookup"><span data-stu-id="935fb-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-140"><strong>Caller</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-141">是</span><span class="sxs-lookup"><span data-stu-id="935fb-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-142">啟動通話者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="935fb-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-143"><strong>受話者</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-144">是</span><span class="sxs-lookup"><span data-stu-id="935fb-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-145">被呼叫者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="935fb-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-146"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-147">是</span><span class="sxs-lookup"><span data-stu-id="935fb-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-148">日期和時間通話的開始。</span><span class="sxs-lookup"><span data-stu-id="935fb-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-149"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-150">是</span><span class="sxs-lookup"><span data-stu-id="935fb-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-151">日期和時間通話的結束。</span><span class="sxs-lookup"><span data-stu-id="935fb-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-152"><strong>呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-153">是</span><span class="sxs-lookup"><span data-stu-id="935fb-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-154">啟動通話者的端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="935fb-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-155"><strong>被呼叫者使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-156">是</span><span class="sxs-lookup"><span data-stu-id="935fb-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-157">被呼叫者端點所用的軟體。</span><span class="sxs-lookup"><span data-stu-id="935fb-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-158"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-159">是</span><span class="sxs-lookup"><span data-stu-id="935fb-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-160">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="935fb-160">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="935fb-161">100 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="935fb-161">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="935fb-162">高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="935fb-162">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="935fb-163">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="935fb-163">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-164"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-165">是</span><span class="sxs-lookup"><span data-stu-id="935fb-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-166">平均量平均意見分數 (MOS) 降低在通話期間發生。</span><span class="sxs-lookup"><span data-stu-id="935fb-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="935fb-167">為 [高] 的 5.0，降低值可介於 0.0 的低。</span><span class="sxs-lookup"><span data-stu-id="935fb-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="935fb-168">為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="935fb-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="935fb-169">在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="935fb-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="935fb-170">在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="935fb-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="935fb-171">高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="935fb-171">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="935fb-172">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="935fb-172">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-173"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-174">是</span><span class="sxs-lookup"><span data-stu-id="935fb-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-175">RTP 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="935fb-175">Average rate of RTP packet loss.</span></span> <span data-ttu-id="935fb-176">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="935fb-176">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="935fb-177">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="935fb-177">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-178"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-179">是</span><span class="sxs-lookup"><span data-stu-id="935fb-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-180">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="935fb-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="935fb-181">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="935fb-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-182"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-183">是</span><span class="sxs-lookup"><span data-stu-id="935fb-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-184">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="935fb-184">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="935fb-185">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="935fb-185">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-186"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-187">是</span><span class="sxs-lookup"><span data-stu-id="935fb-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-188">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="935fb-188">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="935fb-189">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="935fb-189">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="935fb-190"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-191">是</span><span class="sxs-lookup"><span data-stu-id="935fb-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-192">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="935fb-192">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="935fb-193">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="935fb-193">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="935fb-194"><strong>連線能力</strong></span><span class="sxs-lookup"><span data-stu-id="935fb-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="935fb-195">是</span><span class="sxs-lookup"><span data-stu-id="935fb-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="935fb-196">無線通訊連結的類型。</span><span class="sxs-lookup"><span data-stu-id="935fb-196">Type of wireless communication link.</span></span> <span data-ttu-id="935fb-197">一般而言，這會是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="935fb-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="935fb-198">轉送</span><span class="sxs-lookup"><span data-stu-id="935fb-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="935fb-199">直接</span><span class="sxs-lookup"><span data-stu-id="935fb-199">Direct</span></span></p></li>
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

