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
ms.openlocfilehash: ce2954f848d448676aea2931cda4dffa8ddc0c5d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-list-report-in-lync-server-2013"></a><span data-ttu-id="191d1-102">Lync Server 2013 中的通話清單報告</span><span class="sxs-lookup"><span data-stu-id="191d1-102">Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="191d1-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="191d1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="191d1-104">[通話清單] 報告提供在貴組織中撥打及接聽的個別通話的經驗品質（QoE）度量單位。</span><span class="sxs-lookup"><span data-stu-id="191d1-104">The Call List Report provides Quality of Experience (QoE) metrics for individual calls made and received in your organization.</span></span> <span data-ttu-id="191d1-105">請注意，報告的實際度量單位會視您存取通話清單報告的方式而定。</span><span class="sxs-lookup"><span data-stu-id="191d1-105">Note that the actual metrics reported will depend on how you access the Call List report.</span></span> <span data-ttu-id="191d1-106">例如，如果您從[Lync Server 2013 的裝置報表](lync-server-2013-device-report.md)開啟報表，您會看到如下所示的度量標準，也就是在裝置報表上報告的度量值：</span><span class="sxs-lookup"><span data-stu-id="191d1-106">For example, if you open the report from the [Device Report in Lync Server 2013](lync-server-2013-device-report.md), you'll see metrics such as the following, metrics that are also reported on the Device Report:</span></span>

  - <span data-ttu-id="191d1-107">來電者麥克風</span><span class="sxs-lookup"><span data-stu-id="191d1-107">Caller's microphone</span></span>

  - <span data-ttu-id="191d1-108">來電者的喇叭</span><span class="sxs-lookup"><span data-stu-id="191d1-108">Caller's speaker</span></span>

  - <span data-ttu-id="191d1-109">被呼叫者的麥克風</span><span class="sxs-lookup"><span data-stu-id="191d1-109">Callee's microphone</span></span>

  - <span data-ttu-id="191d1-110">被呼叫者的喇叭</span><span class="sxs-lookup"><span data-stu-id="191d1-110">Callee's speaker</span></span>

  - <span data-ttu-id="191d1-111">語音切換時間的比率</span><span class="sxs-lookup"><span data-stu-id="191d1-111">Ratio of voice switch time</span></span>

<span data-ttu-id="191d1-112">不過，如果您在[Lync Server 2013](lync-server-2013-location-report.md)的 [位置] 報告中開啟 [通話清單] 報告，就不會看到任何這些指標;相反地，您會看到如下所示的統計資料：</span><span class="sxs-lookup"><span data-stu-id="191d1-112">However, if you open the Call List Report from the [Location Report in Lync Server 2013](lync-server-2013-location-report.md), you won't see any of those metrics; instead, you'll see metrics like these:</span></span>

  - <span data-ttu-id="191d1-113">往返行程（毫秒）</span><span class="sxs-lookup"><span data-stu-id="191d1-113">Round trip (ms)</span></span>

  - <span data-ttu-id="191d1-114">下降（MOS）</span><span class="sxs-lookup"><span data-stu-id="191d1-114">Degradation (MOS)</span></span>

  - <span data-ttu-id="191d1-115">資料包遺失</span><span class="sxs-lookup"><span data-stu-id="191d1-115">Packet loss</span></span>

  - <span data-ttu-id="191d1-116">抖動（毫秒）</span><span class="sxs-lookup"><span data-stu-id="191d1-116">Jitter (ms)</span></span>

<span data-ttu-id="191d1-117">這些是在位置報告上報告的度量單位。</span><span class="sxs-lookup"><span data-stu-id="191d1-117">Those are the metrics reported on the Location Report.</span></span> <span data-ttu-id="191d1-118">不過，您隨時可以在通話清單報告中按一下詳細資料，以提供任何通話的完整 QoE 資訊。</span><span class="sxs-lookup"><span data-stu-id="191d1-118">However, from the Call List Report you can always click the Detail metric to provide complete QoE information for any call.</span></span>

<div>

## <a name="accessing-the-call-list-report"></a><span data-ttu-id="191d1-119">存取通話清單報告</span><span class="sxs-lookup"><span data-stu-id="191d1-119">Accessing the Call List Report</span></span>

<span data-ttu-id="191d1-120">您可以從下列任何一種報告存取通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="191d1-120">The Call List Report can be accessed from any of the following reports:</span></span>

  - <span data-ttu-id="191d1-121">[Lync Server 2013 中的位置報告](lync-server-2013-location-report.md)（按一下通話量或較差的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="191d1-121">The [Location Report in Lync Server 2013](lync-server-2013-location-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="191d1-122">[Lync Server 2013 中的裝置報告](lync-server-2013-device-report.md)（按一下通話量或較差的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="191d1-122">The [Device Report in Lync Server 2013](lync-server-2013-device-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="191d1-123">[Lync Server 2013 中的媒體質量摘要報告](lync-server-2013-media-quality-summary-report.md)（按一下通話量或較差的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="191d1-123">The [Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

  - <span data-ttu-id="191d1-124">[Lync server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)（按一下通話量或較差的通話百分比指標）</span><span class="sxs-lookup"><span data-stu-id="191d1-124">The [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Call volume or Poor call percentage metric)</span></span>

<span data-ttu-id="191d1-125">在通話清單報告中，您可以按一下詳細資料度量，[以存取 Lync Server 2013 中的 [通話詳細資料] 報告](lync-server-2013-call-detail-report.md)。</span><span class="sxs-lookup"><span data-stu-id="191d1-125">From within the Call List Report you can access the [Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) by clicking the Detail metric.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a><span data-ttu-id="191d1-126">充分利用通話清單報告</span><span class="sxs-lookup"><span data-stu-id="191d1-126">Making the Best Use of the Call List Report</span></span>

<span data-ttu-id="191d1-127">如果您不記得一些通話清單報告的度量單位（例如語音切換時間）實際測量，請將滑鼠停留在公制標籤上;接著會出現工具提示，提供規格的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="191d1-127">If you can't remember what some of the Call List Report metrics (such as Ratio voice switch time) actually measure, hold your mouse over the metric label; a tool tip will then appear giving you a brief description of the metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="191d1-128">濾鏡</span><span class="sxs-lookup"><span data-stu-id="191d1-128">Filters</span></span>

<span data-ttu-id="191d1-129">無。</span><span class="sxs-lookup"><span data-stu-id="191d1-129">None.</span></span> <span data-ttu-id="191d1-130">您無法篩選通話清單報告。</span><span class="sxs-lookup"><span data-stu-id="191d1-130">You cannot filter the Call List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="191d1-131">指標</span><span class="sxs-lookup"><span data-stu-id="191d1-131">Metrics</span></span>

<span data-ttu-id="191d1-132">下表列出 [通話清單] 報告中針對每個通話提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="191d1-132">The following table lists the information provided in the Call List Report for each call.</span></span>

### <a name="call-list-report-metrics"></a><span data-ttu-id="191d1-133">通話清單報告度量單位</span><span class="sxs-lookup"><span data-stu-id="191d1-133">Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="191d1-134">名稱</span><span class="sxs-lookup"><span data-stu-id="191d1-134">Name</span></span></th>
<th><span data-ttu-id="191d1-135">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="191d1-135">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="191d1-136">說明</span><span class="sxs-lookup"><span data-stu-id="191d1-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="191d1-137"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-137"><strong>Details</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-138">否</span><span class="sxs-lookup"><span data-stu-id="191d1-138">No</span></span></p></td>
<td><p><span data-ttu-id="191d1-139">當您按一下此專案時，報告會顯示通話的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="191d1-139">When you click this item, the report shows additional information on the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-140"><strong>呼叫</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-140"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-141">是</span><span class="sxs-lookup"><span data-stu-id="191d1-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-142">啟動通話之人的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="191d1-142">SIP address of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-143"><strong>方</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-143"><strong>Callee</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-144">是</span><span class="sxs-lookup"><span data-stu-id="191d1-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-145">呼叫者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="191d1-145">SIP address of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-146"><strong>開始時間</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-146"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-147">是</span><span class="sxs-lookup"><span data-stu-id="191d1-147">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-148">通話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="191d1-148">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-149"><strong>結束時間</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-149"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-150">是</span><span class="sxs-lookup"><span data-stu-id="191d1-150">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-151">通話結束的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="191d1-151">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-152"><strong>本機號碼使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-152"><strong>Caller user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-153">是</span><span class="sxs-lookup"><span data-stu-id="191d1-153">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-154">啟動通話之人的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="191d1-154">Software used by the endpoint of the person who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-155"><strong>被呼叫使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-155"><strong>Callee user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-156">是</span><span class="sxs-lookup"><span data-stu-id="191d1-156">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-157">呼叫者的端點所使用的軟體。</span><span class="sxs-lookup"><span data-stu-id="191d1-157">Software used by the endpoint of the person who was called.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-158"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-158"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-159">是</span><span class="sxs-lookup"><span data-stu-id="191d1-159">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-160">即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="191d1-160">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="191d1-161">100毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="191d1-161">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="191d1-162">高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="191d1-162">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="191d1-163">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="191d1-163">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-164"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-164"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-165">是</span><span class="sxs-lookup"><span data-stu-id="191d1-165">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-166">通話期間平均觀念得分（MOS）的平均數量下降。</span><span class="sxs-lookup"><span data-stu-id="191d1-166">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="191d1-167">降級值的範圍可從低0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="191d1-167">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="191d1-168">0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="191d1-168">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="191d1-169">過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。</span><span class="sxs-lookup"><span data-stu-id="191d1-169">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="191d1-170">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="191d1-170">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="191d1-171">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="191d1-171">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="191d1-172">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="191d1-172">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-173"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-173"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-174">是</span><span class="sxs-lookup"><span data-stu-id="191d1-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-175">RTP 資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="191d1-175">Average rate of RTP packet loss.</span></span> <span data-ttu-id="191d1-176">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="191d1-176">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="191d1-177">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="191d1-177">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-178"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-178"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-179">是</span><span class="sxs-lookup"><span data-stu-id="191d1-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-180">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="191d1-180">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="191d1-181">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="191d1-181">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-182"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-182"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-183">是</span><span class="sxs-lookup"><span data-stu-id="191d1-183">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-184">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="191d1-184">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="191d1-185">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="191d1-185">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-186"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-186"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-187">是</span><span class="sxs-lookup"><span data-stu-id="191d1-187">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-188">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="191d1-188">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="191d1-189">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="191d1-189">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="191d1-190"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-190"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-191">是</span><span class="sxs-lookup"><span data-stu-id="191d1-191">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-192">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="191d1-192">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="191d1-193">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="191d1-193">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="191d1-194"><strong>連通</strong></span><span class="sxs-lookup"><span data-stu-id="191d1-194"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="191d1-195">是</span><span class="sxs-lookup"><span data-stu-id="191d1-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="191d1-196">[無線通訊] 連結的類型。</span><span class="sxs-lookup"><span data-stu-id="191d1-196">Type of wireless communication link.</span></span> <span data-ttu-id="191d1-197">通常，這是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="191d1-197">Typically, this is one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="191d1-198">轉送</span><span class="sxs-lookup"><span data-stu-id="191d1-198">Relay</span></span></p></li>
<li><p><span data-ttu-id="191d1-199">播放</span><span class="sxs-lookup"><span data-stu-id="191d1-199">Direct</span></span></p></li>
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

