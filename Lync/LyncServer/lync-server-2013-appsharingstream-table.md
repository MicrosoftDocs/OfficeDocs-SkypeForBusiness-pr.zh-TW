---
title: Lync Server 2013： AppSharingStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="37d7d-102">Lync Server 2013 中的 AppSharingStream 表格</span><span class="sxs-lookup"><span data-stu-id="37d7d-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37d7d-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="37d7d-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="37d7d-104">AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質度量單位。</span><span class="sxs-lookup"><span data-stu-id="37d7d-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="37d7d-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="37d7d-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="37d7d-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="37d7d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="37d7d-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="37d7d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="37d7d-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="37d7d-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="37d7d-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37d7d-113">會話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-115">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-115">int</span></span></p></td>
<td><p><span data-ttu-id="37d7d-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="37d7d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37d7d-117">使用順序識別碼來區分在相同日期和同一時間啟動的會話。</span><span class="sxs-lookup"><span data-stu-id="37d7d-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="37d7d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="37d7d-120">主要、外部</span><span class="sxs-lookup"><span data-stu-id="37d7d-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="37d7d-121">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="37d7d-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="37d7d-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="37d7d-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="37d7d-123">0-音訊</span><span class="sxs-lookup"><span data-stu-id="37d7d-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="37d7d-124">1–影片</span><span class="sxs-lookup"><span data-stu-id="37d7d-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="37d7d-125">2-全景影片</span><span class="sxs-lookup"><span data-stu-id="37d7d-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="37d7d-126">3-應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="37d7d-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-128">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-128">int</span></span></p></td>
<td><p><span data-ttu-id="37d7d-129">首選</span><span class="sxs-lookup"><span data-stu-id="37d7d-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="37d7d-130">應用程式共用資料流程的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="37d7d-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-132">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-133">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="37d7d-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="37d7d-134">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="37d7d-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-136">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-137">在 RTP 資料包抵達之間檢測到最大抖動。</span><span class="sxs-lookup"><span data-stu-id="37d7d-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="37d7d-138">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="37d7d-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-139"><strong>環路</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-140">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-141">即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="37d7d-142">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="37d7d-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="37d7d-143">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="37d7d-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="37d7d-144">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="37d7d-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-146">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-147">即時傳輸通訊協定資料包要傳送到另一個端點的最大值（以毫秒為單位），然後返回。</span><span class="sxs-lookup"><span data-stu-id="37d7d-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="37d7d-148">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="37d7d-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="37d7d-149">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="37d7d-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="37d7d-150">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="37d7d-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-152">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-153">即時傳輸通訊協定（RTP）資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="37d7d-154">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="37d7d-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="37d7d-155">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="37d7d-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-157">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-158">即時傳輸通訊協定（RTP）資料包遺失率的最大值。</span><span class="sxs-lookup"><span data-stu-id="37d7d-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="37d7d-159">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="37d7d-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="37d7d-160">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="37d7d-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-162">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-163">已傳送的資料包數目。</span><span class="sxs-lookup"><span data-stu-id="37d7d-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-165">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-166">會話結束時可使用的估計單向頻寬。</span><span class="sxs-lookup"><span data-stu-id="37d7d-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="37d7d-167">以每秒位數報告。</span><span class="sxs-lookup"><span data-stu-id="37d7d-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-169">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-170">應用程式共用負載的描述。</span><span class="sxs-lookup"><span data-stu-id="37d7d-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-172">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-173">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="37d7d-173">Total amount of one-way latency.</span></span> <span data-ttu-id="37d7d-174">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-176">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-177">單向延隔時間的平均量。</span><span class="sxs-lookup"><span data-stu-id="37d7d-177">Average amount of one-way latency.</span></span> <span data-ttu-id="37d7d-178">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-180">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-181">單向延隔時間的最大值。</span><span class="sxs-lookup"><span data-stu-id="37d7d-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="37d7d-182">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-184">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-185">單向突發發生次數總計。</span><span class="sxs-lookup"><span data-stu-id="37d7d-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="37d7d-186">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="37d7d-187">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-189">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-190">總計單向突發密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-190">Total one-way burst density.</span></span> <span data-ttu-id="37d7d-191">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="37d7d-192">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-194">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-195">總計單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-195">Total one-way burst duration.</span></span> <span data-ttu-id="37d7d-196">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="37d7d-197">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-199">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-200">總的單向間距發生情況。</span><span class="sxs-lookup"><span data-stu-id="37d7d-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="37d7d-201">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="37d7d-202">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-204">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-205">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-205">Total one-way gap density.</span></span> <span data-ttu-id="37d7d-206">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="37d7d-207">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-209">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-210">總共一個單向間距時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-210">Total one-way gap duration.</span></span> <span data-ttu-id="37d7d-211">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="37d7d-212">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-214">varChar （256）</span><span class="sxs-lookup"><span data-stu-id="37d7d-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-215">應用程式角色（共用或檢視器）與內容類型。</span><span class="sxs-lookup"><span data-stu-id="37d7d-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-217">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-218">遠端桌面通訊協定（RDP）磚的總處理時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-219">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-221">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-222">遠端桌面通訊協定（RDP）磚的平均處理時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-223">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-225">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-226">遠端桌面通訊協定（RDP）磚的最大處理時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-227">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="37d7d-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-229">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-230">遠端桌面通訊協定（RDP）磚處理時間的突發事件發生方式。</span><span class="sxs-lookup"><span data-stu-id="37d7d-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-231">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-233">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-234">遠端桌面通訊協定（RDP）磚處理時間的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-235">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-237">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-238">遠端桌面通訊協定（RDP）磚處理時間中的爆發時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-239">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="37d7d-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-241">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-242">遠端桌面通訊協定（RDP）磚處理時間中的差距出現次數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-244">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-245">遠端桌面通訊協定（RDP）磚處理時間的差距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-246">低差距密度可讓您獲得更佳的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="37d7d-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-248">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-249">遠端桌面通訊協定（RDP）磚處理時間中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="37d7d-250">短差距期間會等同于更佳的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="37d7d-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-252">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-253">捕獲磚的總速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-255">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-256">捕獲磚的平均速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-258">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-259">捕獲磚的最大速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-261">在 t</span><span class="sxs-lookup"><span data-stu-id="37d7d-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-262">在捕獲磚（每秒磚數）中，突發發生的頻率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-264">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-265">捕獲磚（每秒磚）的流量峰值密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-267">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-268">以捕獲磚（每秒磚）為單位的爆發時段。</span><span class="sxs-lookup"><span data-stu-id="37d7d-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-270">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-271">間距出現在捕獲磚的速率中（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-273">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-274">已捕獲磚（每秒磚）中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-276">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-277">所捕獲磚（每秒磚）中的差距間隔時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-279">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-280">未到達檢視器的內容總百分比，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-282">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-283">未到達檢視器的內容平均百分比，而是由新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-285">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-286">未到達檢視器的內容的最大百分比，而是由新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-288">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-289">無法到達檢視器的內容突發事件，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-291">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-292">未到達檢視器之內容的突發密度，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-294">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-295">無法到達檢視器之內容的爆發持續時間，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-297">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-298">未到達檢視器之內容的差距出現次數，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-300">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-301">未到達檢視器之內容的差距密度，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-303">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-304">未到達檢視器之內容的差距持續時間，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="37d7d-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-306">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-307">圖形來源的畫面總 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-309">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-310">圖形來源的平均幀 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-312">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-313">圖形來源中的最大幀 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-315">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-316">來自圖形來源的 [幀 scraped] 中的 [突發] 出現次數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-318">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-319">圖形來源的 [幀 scraped] 中的 [暴沖密度]。</span><span class="sxs-lookup"><span data-stu-id="37d7d-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-321">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-322">圖形來源的 [幀 scraped] 中的 [突發期間]。</span><span class="sxs-lookup"><span data-stu-id="37d7d-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-324">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-325">圖形來源的 [幀 scraped] 中的空隙出現次數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-327">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-328">圖形來源的 [框架 scraped] 中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-330">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-331">圖形來源的 [框架 scraped] 中的 [空隙] 工期。</span><span class="sxs-lookup"><span data-stu-id="37d7d-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-333">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-334">檢視器接收的傳入畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="37d7d-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-336">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-337">檢視器接收到的平均接收畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-339">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-340">檢視器接收到的傳入磚速率上限。</span><span class="sxs-lookup"><span data-stu-id="37d7d-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-342">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-343">檢視器接收到的傳入磚速率中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-345">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-346">檢視器接收的傳入磚速率中的高載密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-348">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-349">檢視器接收的傳入磚速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-351">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-352">檢視器接收的傳入磚速率中的間距值。</span><span class="sxs-lookup"><span data-stu-id="37d7d-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-354">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-355">檢視器接收的傳入磚速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-357">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-358">檢視器接收到的內送磚速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-360">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-361">檢視器接收的傳入畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="37d7d-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-363">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-364">檢視器接收到的平均接收畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-366">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-367">檢視器接收到的最大傳入畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-369">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-370">檢視器接收到的傳入畫面播放速率中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="37d7d-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-372">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-373">檢視器接收到的傳入畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-375">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-376">檢視器接收到的傳入畫面播放速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-378">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-379">檢視器接收到的內送畫面播放速率中出現的間距。</span><span class="sxs-lookup"><span data-stu-id="37d7d-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-381">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-382">檢視器接收的傳入畫面播放速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-384">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-385">檢視器接收的傳入畫面播放速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-387">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-388">寄件者的外寄磚率總計。</span><span class="sxs-lookup"><span data-stu-id="37d7d-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-390">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-391">寄件者的平均外寄磚速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-393">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-394">寄件者的最大外寄磚速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-396">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-397">寄件者的傳出磚速率中的突發事件。</span><span class="sxs-lookup"><span data-stu-id="37d7d-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-399">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-400">寄件者的傳出磚速率的高載密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-402">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-403">寄件者的傳出磚頻率內的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-405">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-406">寄件者的外寄磚頻率中出現空隙。</span><span class="sxs-lookup"><span data-stu-id="37d7d-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-408">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-409">寄件者的外寄磚工資率的差距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-411">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-412">寄件者的外寄磚工資率的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-414">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-415">寄件者的外寄畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="37d7d-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-417">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-418">寄件者的平均傳出畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-420">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-421">寄件者的最大外寄畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="37d7d-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-423">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-424">寄件者在外寄畫面播放速率中的突發事件。</span><span class="sxs-lookup"><span data-stu-id="37d7d-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-426">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-427">寄件者的外寄畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-429">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-430">寄件者的外寄畫面播放速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-432">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-433">寄件者的外寄畫面播放速率中出現空隙。</span><span class="sxs-lookup"><span data-stu-id="37d7d-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-435">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-436">寄件者的外寄畫面播放速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-438">浮</span><span class="sxs-lookup"><span data-stu-id="37d7d-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-439">寄件者的外寄畫面播放速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="37d7d-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-441">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-442">平均視頻解析度高度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-444">int</span><span class="sxs-lookup"><span data-stu-id="37d7d-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-445">以圖元為單位的平均視頻解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="37d7d-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-446"><strong>進貨</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-447">稍微</span><span class="sxs-lookup"><span data-stu-id="37d7d-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-448">入站傳輸的平均畫面播放速率（在每秒的幀數）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="37d7d-449"><strong>發</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-450">稍微</span><span class="sxs-lookup"><span data-stu-id="37d7d-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-451">輸出傳送的平均畫面播放速率（在每秒的幀數）。</span><span class="sxs-lookup"><span data-stu-id="37d7d-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="37d7d-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="37d7d-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="37d7d-453">稍微</span><span class="sxs-lookup"><span data-stu-id="37d7d-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="37d7d-454">1表示資料流程方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="37d7d-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="37d7d-455">0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="37d7d-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

