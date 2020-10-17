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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499500"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="e89b0-102">Lync Server 2013 中的 AppSharingStream 表格</span><span class="sxs-lookup"><span data-stu-id="e89b0-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e89b0-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="e89b0-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="e89b0-104">AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質計量。</span><span class="sxs-lookup"><span data-stu-id="e89b0-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="e89b0-105">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e89b0-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e89b0-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e89b0-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e89b0-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e89b0-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="e89b0-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="e89b0-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="e89b0-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e89b0-113">會話開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-115">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-115">int</span></span></p></td>
<td><p><span data-ttu-id="e89b0-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="e89b0-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e89b0-117">用來區分在相同日期和同一時間開始之會話的連續識別碼。</span><span class="sxs-lookup"><span data-stu-id="e89b0-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="e89b0-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e89b0-120">主要，外部</span><span class="sxs-lookup"><span data-stu-id="e89b0-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e89b0-121">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="e89b0-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="e89b0-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="e89b0-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e89b0-123">0–音訊</span><span class="sxs-lookup"><span data-stu-id="e89b0-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="e89b0-124">1–影片</span><span class="sxs-lookup"><span data-stu-id="e89b0-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="e89b0-125">2–全景影片</span><span class="sxs-lookup"><span data-stu-id="e89b0-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="e89b0-126">3–應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="e89b0-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-128">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-128">int</span></span></p></td>
<td><p><span data-ttu-id="e89b0-129">主要</span><span class="sxs-lookup"><span data-stu-id="e89b0-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="e89b0-130">應用程式共用資料流程的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="e89b0-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-132">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-133">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="e89b0-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e89b0-134"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="e89b0-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-136">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-137">在 RTP 封包抵達之間偵測到的最大抖動。</span><span class="sxs-lookup"><span data-stu-id="e89b0-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e89b0-138"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="e89b0-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-139"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-140">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-141">Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。</span><span class="sxs-lookup"><span data-stu-id="e89b0-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="e89b0-142">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="e89b0-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e89b0-143">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="e89b0-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="e89b0-144">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="e89b0-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-146">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-147">Real-Time 傳輸通訊協定資料包移至另一個端點後，所需的 (（毫秒）) 數目上限。</span><span class="sxs-lookup"><span data-stu-id="e89b0-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="e89b0-148">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="e89b0-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e89b0-149">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="e89b0-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="e89b0-150">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="e89b0-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-152">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-153"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="e89b0-154">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="e89b0-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="e89b0-155">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="e89b0-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-157">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-158"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的最大速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="e89b0-159">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="e89b0-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="e89b0-160">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="e89b0-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-162">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-163">傳送的封包數目。</span><span class="sxs-lookup"><span data-stu-id="e89b0-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-165">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-166">在會話結束時可使用的預估單向頻寬。</span><span class="sxs-lookup"><span data-stu-id="e89b0-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="e89b0-167">每秒的位數報告。</span><span class="sxs-lookup"><span data-stu-id="e89b0-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-169">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-170">應用程式共用負載的描述。</span><span class="sxs-lookup"><span data-stu-id="e89b0-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-172">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-173">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="e89b0-173">Total amount of one-way latency.</span></span> <span data-ttu-id="e89b0-174">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-176">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-177">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="e89b0-177">Average amount of one-way latency.</span></span> <span data-ttu-id="e89b0-178">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-180">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-181">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="e89b0-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="e89b0-182">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-184">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-185">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="e89b0-186">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e89b0-187">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-189">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-190">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-190">Total one-way burst density.</span></span> <span data-ttu-id="e89b0-191">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e89b0-192">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-194">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-195">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-195">Total one-way burst duration.</span></span> <span data-ttu-id="e89b0-196">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="e89b0-197">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-199">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-200">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="e89b0-201">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e89b0-202">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-204">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-205">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-205">Total one-way gap density.</span></span> <span data-ttu-id="e89b0-206">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e89b0-207">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-209">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-210">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-210">Total one-way gap duration.</span></span> <span data-ttu-id="e89b0-211">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="e89b0-212">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e89b0-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-214">varChar (256) </span><span class="sxs-lookup"><span data-stu-id="e89b0-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-215"> (共用或檢視器的應用程式角色) 和內容類型。</span><span class="sxs-lookup"><span data-stu-id="e89b0-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-217">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-218">遠端桌面通訊協定 (RDP) 麻將牌的總處理時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-219">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-221">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-222">遠端桌面通訊協定 (RDP) 磚的平均處理時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-223">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-225">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-226">遠端桌面通訊協定 (RDP) 磚的處理時間上限。</span><span class="sxs-lookup"><span data-stu-id="e89b0-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-227">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="e89b0-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-229">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-230">遠端桌面通訊協定 (RDP) 的處理時間中的爆發發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-231">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-233">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-234">遠端桌面通訊協定 (RDP) 磚的處理時間中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-235">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-237">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-238">遠端桌面通訊協定 (RDP 的處理時間中的暴沖持續時間) 磚。</span><span class="sxs-lookup"><span data-stu-id="e89b0-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-239">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="e89b0-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-241">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-242">遠端桌面通訊協定的處理時間中的缺口發生次數 (RDP) 麻將牌。</span><span class="sxs-lookup"><span data-stu-id="e89b0-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-244">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-245">遠端桌面通訊協定 (RDP) 圖塊的處理時間中的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-246">低間距密度相當於更好的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="e89b0-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-248">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-249">遠端桌面通訊協定 (RDP 的處理時間中的缺口持續時間) 麻將牌。</span><span class="sxs-lookup"><span data-stu-id="e89b0-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="e89b0-250">短的缺口持續時間等於更好的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="e89b0-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-252">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-253">每秒 (每秒磚) 中的捕獲磚總速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-255">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-256">每秒 (每秒磚的已捕獲磚的平均速率) 。</span><span class="sxs-lookup"><span data-stu-id="e89b0-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-258">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-259">每秒 (每秒的磚) 中所捕獲的麻將牌的最大速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-261">在 t</span><span class="sxs-lookup"><span data-stu-id="e89b0-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-262">以每秒 (每秒磚數為單位所捕獲的麻將牌的速率) 中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-264">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-265">) 中每秒 (以每秒所捕獲的麻將牌速率為單位的流量密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-267">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-268">以每秒磚數 (為單位的每秒) 中捕獲的磚的流量。</span><span class="sxs-lookup"><span data-stu-id="e89b0-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-270">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-271">以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-273">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-274">以每秒貼圖)  (所捕獲的麻將牌速率為單位的間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-276">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-277">以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-279">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-280">未到達檢視器而被捨棄並以全新內容覆寫之內容的總百分比。</span><span class="sxs-lookup"><span data-stu-id="e89b0-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-282">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-283">未到達檢視器而被捨棄並以全新內容覆寫之內容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="e89b0-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-285">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-286">未到達檢視器而被捨棄並以全新內容覆寫之內容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="e89b0-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-288">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-289">未到達檢視器而被捨棄並以全新內容覆寫之內容的爆發發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-291">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-292">未到達檢視器之內容的暴沖密度，但已被捨棄並以全新內容覆寫。</span><span class="sxs-lookup"><span data-stu-id="e89b0-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-294">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-295">未到達檢視器而被捨棄並以全新內容覆寫之內容的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-297">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-298">未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-300">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-301">未到達檢視器之內容的缺口密度，但已被捨棄並以全新內容覆寫。</span><span class="sxs-lookup"><span data-stu-id="e89b0-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-303">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-304">未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-306">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-307">從圖形來源消去的框架總數目。</span><span class="sxs-lookup"><span data-stu-id="e89b0-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-309">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-310">從圖形來源消去的平均框架數目。</span><span class="sxs-lookup"><span data-stu-id="e89b0-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-312">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-313">從圖形來源消去的最大相框數目。</span><span class="sxs-lookup"><span data-stu-id="e89b0-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-315">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-316">從圖形來源消去的幀中的出現爆發。</span><span class="sxs-lookup"><span data-stu-id="e89b0-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-318">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-319">從圖形來源消去之框架中的流量密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-321">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-322">從圖形來源消去之框架中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-324">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-325">從圖形來源消去之框架中的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-327">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-328">從圖形來源消去之框架中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-330">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-331">從圖形來源消去之框架中的空隙 duration。</span><span class="sxs-lookup"><span data-stu-id="e89b0-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-333">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-334">檢視器接收到的內送框架速率總數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-336">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-337">檢視器接收的平均內送框架速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-339">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-340">檢視器所收到的傳入磚率上限。</span><span class="sxs-lookup"><span data-stu-id="e89b0-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-342">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-343">由檢視器接收的傳入磚速率中的突發流量。</span><span class="sxs-lookup"><span data-stu-id="e89b0-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-345">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-346">由檢視器接收的傳入磚速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-348">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-349">由檢視器接收的傳入磚速率中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-351">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-352">由 viewer 接收的內送磚速率中的間距發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-354">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-355">由 viewer 接收的內送磚速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-357">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-358">依檢視器接收的內送磚速率中的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-360">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-361">檢視器接收到的內送框架速率總數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-363">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-364">檢視器接收的平均內送框架速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-366">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-367">檢視器接收到的內送框架速率上限。</span><span class="sxs-lookup"><span data-stu-id="e89b0-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-369">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-370">檢視器接收的內送畫面播放速率中的突發流量發生方式。</span><span class="sxs-lookup"><span data-stu-id="e89b0-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-372">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-373">由檢視器接收的內送畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-375">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-376">以瀏覽器接收的傳入相框速率中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-378">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-379">檢視器接收的內送畫面播放速率中的間距發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-381">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-382">檢視器接收的內送框架速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-384">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-385">依檢視器接收的內送框架速率中的間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-387">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-388">寄件者的傳出磚總速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-390">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-391">寄件者的平均傳出磚速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-393">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-394">寄件者的傳出磚流量上限。</span><span class="sxs-lookup"><span data-stu-id="e89b0-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-396">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-397">以寄件者的傳出磚速率表示的突發流量發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-399">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-400">以傳送者之傳出磚速率表示的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-402">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-403">以寄件者的傳出磚速率表示的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-405">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-406">以寄件者的傳出磚速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-408">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-409">以寄件者的傳出磚速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-411">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-412">以寄件者的傳出磚速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-414">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-415">寄件者的傳出畫面速率總數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-417">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-418">寄件者的平均傳出畫面速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-420">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-421">寄件者的最大傳出畫面速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-423">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-424">寄件者的傳出畫面速率中的暴沖出現次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-426">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-427">寄件者的傳出畫面速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-429">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-430">以寄件者的傳出畫面速率表示的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-432">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-433">以寄件者的傳出畫面速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="e89b0-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-435">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-436">寄件者的傳出畫面速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="e89b0-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-438">float</span><span class="sxs-lookup"><span data-stu-id="e89b0-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-439">以寄件者的傳出畫面速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="e89b0-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-441">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-442">影片的平均解析度高度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="e89b0-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-444">int</span><span class="sxs-lookup"><span data-stu-id="e89b0-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-445">影片的平均解析度寬度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="e89b0-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-446"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-447">位</span><span class="sxs-lookup"><span data-stu-id="e89b0-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-448">輸入傳輸的平均每秒幀 () 的平均框架速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e89b0-449"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-450">位</span><span class="sxs-lookup"><span data-stu-id="e89b0-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-451">輸出傳輸) 每秒幀中 (的平均框架速率。</span><span class="sxs-lookup"><span data-stu-id="e89b0-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e89b0-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e89b0-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e89b0-453">位</span><span class="sxs-lookup"><span data-stu-id="e89b0-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e89b0-454">1表示資料流程的方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="e89b0-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="e89b0-455">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="e89b0-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

