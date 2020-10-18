---
title: Lync Server 2013： AppSharingStream 表格
description: Lync Server 2013： AppSharingStream 表格。
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
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574719"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="1b830-103">Lync Server 2013 中的 AppSharingStream 表格</span><span class="sxs-lookup"><span data-stu-id="1b830-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b830-104">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="1b830-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="1b830-105">AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質計量。</span><span class="sxs-lookup"><span data-stu-id="1b830-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="1b830-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1b830-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b830-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1b830-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1b830-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1b830-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b830-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-112">Datetime</span><span class="sxs-lookup"><span data-stu-id="1b830-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="1b830-113">主要、外部</span><span class="sxs-lookup"><span data-stu-id="1b830-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b830-114">會話開始的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-116">int</span><span class="sxs-lookup"><span data-stu-id="1b830-116">int</span></span></p></td>
<td><p><span data-ttu-id="1b830-117">主要、外部</span><span class="sxs-lookup"><span data-stu-id="1b830-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b830-118">用來區分在相同日期和同一時間開始之會話的連續識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b830-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="1b830-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="1b830-121">主要，外部</span><span class="sxs-lookup"><span data-stu-id="1b830-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1b830-122">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="1b830-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="1b830-123">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="1b830-123">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="1b830-124">0–音訊</span><span class="sxs-lookup"><span data-stu-id="1b830-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="1b830-125">1–影片</span><span class="sxs-lookup"><span data-stu-id="1b830-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="1b830-126">2–全景影片</span><span class="sxs-lookup"><span data-stu-id="1b830-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="1b830-127">3–應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="1b830-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-129">int</span><span class="sxs-lookup"><span data-stu-id="1b830-129">int</span></span></p></td>
<td><p><span data-ttu-id="1b830-130">主要</span><span class="sxs-lookup"><span data-stu-id="1b830-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="1b830-131">應用程式共用資料流程的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="1b830-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-133">int</span><span class="sxs-lookup"><span data-stu-id="1b830-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-134">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="1b830-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1b830-135"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="1b830-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-137">int</span><span class="sxs-lookup"><span data-stu-id="1b830-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-138">在 RTP 封包抵達之間偵測到的最大抖動。</span><span class="sxs-lookup"><span data-stu-id="1b830-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="1b830-139"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="1b830-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-140"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-141">int</span><span class="sxs-lookup"><span data-stu-id="1b830-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-142">Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。</span><span class="sxs-lookup"><span data-stu-id="1b830-142">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="1b830-143">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="1b830-143">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1b830-144">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b830-144">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="1b830-145">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="1b830-145">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-147">int</span><span class="sxs-lookup"><span data-stu-id="1b830-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-148">Real-Time 傳輸通訊協定資料包移至另一個端點後，所需的 (（毫秒）) 數目上限。</span><span class="sxs-lookup"><span data-stu-id="1b830-148">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="1b830-149">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="1b830-149">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="1b830-150">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b830-150">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="1b830-151">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="1b830-151">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-153">float</span><span class="sxs-lookup"><span data-stu-id="1b830-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-154"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-154">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="1b830-155">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b830-155">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="1b830-156">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="1b830-156">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-158">float</span><span class="sxs-lookup"><span data-stu-id="1b830-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-159"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的最大速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-159">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="1b830-160">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="1b830-160">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="1b830-161">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="1b830-161">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-163">int</span><span class="sxs-lookup"><span data-stu-id="1b830-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-164">傳送的封包數目。</span><span class="sxs-lookup"><span data-stu-id="1b830-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-165"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-166">int</span><span class="sxs-lookup"><span data-stu-id="1b830-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-167">在會話結束時可使用的預估單向頻寬。</span><span class="sxs-lookup"><span data-stu-id="1b830-167">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="1b830-168">每秒的位數報告。</span><span class="sxs-lookup"><span data-stu-id="1b830-168">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-170">int</span><span class="sxs-lookup"><span data-stu-id="1b830-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-171">應用程式共用負載的描述。</span><span class="sxs-lookup"><span data-stu-id="1b830-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-173">float</span><span class="sxs-lookup"><span data-stu-id="1b830-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-174">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="1b830-174">Total amount of one-way latency.</span></span> <span data-ttu-id="1b830-175">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-175">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-177">float</span><span class="sxs-lookup"><span data-stu-id="1b830-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-178">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="1b830-178">Average amount of one-way latency.</span></span> <span data-ttu-id="1b830-179">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-179">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-181">float</span><span class="sxs-lookup"><span data-stu-id="1b830-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-182">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="1b830-182">Maximum amount of one-way latency.</span></span> <span data-ttu-id="1b830-183">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-183">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-185">int</span><span class="sxs-lookup"><span data-stu-id="1b830-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-186">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-186">Total one-way burst occurrences.</span></span> <span data-ttu-id="1b830-187">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-187">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b830-188">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-188">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-190">float</span><span class="sxs-lookup"><span data-stu-id="1b830-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-191">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-191">Total one-way burst density.</span></span> <span data-ttu-id="1b830-192">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-192">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b830-193">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-193">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-195">float</span><span class="sxs-lookup"><span data-stu-id="1b830-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-196">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-196">Total one-way burst duration.</span></span> <span data-ttu-id="1b830-197">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-197">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="1b830-198">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-198">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-200">int</span><span class="sxs-lookup"><span data-stu-id="1b830-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-201">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-201">Total one-way gap occurrences.</span></span> <span data-ttu-id="1b830-202">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-202">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b830-203">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-203">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-205">float</span><span class="sxs-lookup"><span data-stu-id="1b830-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-206">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-206">Total one-way gap density.</span></span> <span data-ttu-id="1b830-207">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-207">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b830-208">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-208">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-210">float</span><span class="sxs-lookup"><span data-stu-id="1b830-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-211">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-211">Total one-way gap duration.</span></span> <span data-ttu-id="1b830-212">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-212">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="1b830-213">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="1b830-213">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-215">varChar (256) </span><span class="sxs-lookup"><span data-stu-id="1b830-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-216"> (共用或檢視器的應用程式角色) 和內容類型。</span><span class="sxs-lookup"><span data-stu-id="1b830-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-218">float</span><span class="sxs-lookup"><span data-stu-id="1b830-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-219">遠端桌面通訊協定 (RDP) 麻將牌的總處理時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-219">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-220">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-220">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-222">float</span><span class="sxs-lookup"><span data-stu-id="1b830-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-223">遠端桌面通訊協定 (RDP) 磚的平均處理時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-223">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-224">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-224">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-226">float</span><span class="sxs-lookup"><span data-stu-id="1b830-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-227">遠端桌面通訊協定 (RDP) 磚的處理時間上限。</span><span class="sxs-lookup"><span data-stu-id="1b830-227">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-228">較高的總數相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="1b830-228">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-230">int</span><span class="sxs-lookup"><span data-stu-id="1b830-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-231">遠端桌面通訊協定 (RDP) 的處理時間中的爆發發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-231">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-232">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-232">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-234">float</span><span class="sxs-lookup"><span data-stu-id="1b830-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-235">遠端桌面通訊協定 (RDP) 磚的處理時間中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-235">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-236">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-236">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-238">float</span><span class="sxs-lookup"><span data-stu-id="1b830-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-239">遠端桌面通訊協定 (RDP 的處理時間中的暴沖持續時間) 磚。</span><span class="sxs-lookup"><span data-stu-id="1b830-239">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-240">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="1b830-240">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-242">int</span><span class="sxs-lookup"><span data-stu-id="1b830-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-243">遠端桌面通訊協定的處理時間中的缺口發生次數 (RDP) 麻將牌。</span><span class="sxs-lookup"><span data-stu-id="1b830-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-245">float</span><span class="sxs-lookup"><span data-stu-id="1b830-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-246">遠端桌面通訊協定 (RDP) 圖塊的處理時間中的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-246">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-247">低間距密度相當於更好的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="1b830-247">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-249">float</span><span class="sxs-lookup"><span data-stu-id="1b830-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-250">遠端桌面通訊協定 (RDP 的處理時間中的缺口持續時間) 麻將牌。</span><span class="sxs-lookup"><span data-stu-id="1b830-250">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="1b830-251">短的缺口持續時間等於更好的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="1b830-251">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-253">float</span><span class="sxs-lookup"><span data-stu-id="1b830-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-254">每秒 (每秒磚) 中的捕獲磚總速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-256">float</span><span class="sxs-lookup"><span data-stu-id="1b830-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-257">每秒 (每秒磚的已捕獲磚的平均速率) 。</span><span class="sxs-lookup"><span data-stu-id="1b830-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-259">float</span><span class="sxs-lookup"><span data-stu-id="1b830-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-260">每秒 (每秒的磚) 中所捕獲的麻將牌的最大速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-262">在 t</span><span class="sxs-lookup"><span data-stu-id="1b830-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-263">以每秒 (每秒磚數為單位所捕獲的麻將牌的速率) 中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-265">float</span><span class="sxs-lookup"><span data-stu-id="1b830-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-266">) 中每秒 (以每秒所捕獲的麻將牌速率為單位的流量密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-268">float</span><span class="sxs-lookup"><span data-stu-id="1b830-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-269">以每秒磚數 (為單位的每秒) 中捕獲的磚的流量。</span><span class="sxs-lookup"><span data-stu-id="1b830-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-271">int</span><span class="sxs-lookup"><span data-stu-id="1b830-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-272">以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-274">float</span><span class="sxs-lookup"><span data-stu-id="1b830-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-275">以每秒貼圖)  (所捕獲的麻將牌速率為單位的間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-277">float</span><span class="sxs-lookup"><span data-stu-id="1b830-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-278">以每秒貼圖)  (所捕獲的麻將牌速率為單位的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-280">float</span><span class="sxs-lookup"><span data-stu-id="1b830-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-281">未到達檢視器而被捨棄並以全新內容覆寫之內容的總百分比。</span><span class="sxs-lookup"><span data-stu-id="1b830-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-283">float</span><span class="sxs-lookup"><span data-stu-id="1b830-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-284">未到達檢視器而被捨棄並以全新內容覆寫之內容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="1b830-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-286">float</span><span class="sxs-lookup"><span data-stu-id="1b830-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-287">未到達檢視器而被捨棄並以全新內容覆寫之內容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="1b830-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-289">int</span><span class="sxs-lookup"><span data-stu-id="1b830-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-290">未到達檢視器而被捨棄並以全新內容覆寫之內容的爆發發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-292">float</span><span class="sxs-lookup"><span data-stu-id="1b830-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-293">未到達檢視器之內容的暴沖密度，但已被捨棄並以全新內容覆寫。</span><span class="sxs-lookup"><span data-stu-id="1b830-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-295">float</span><span class="sxs-lookup"><span data-stu-id="1b830-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-296">未到達檢視器而被捨棄並以全新內容覆寫之內容的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-298">int</span><span class="sxs-lookup"><span data-stu-id="1b830-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-299">未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-301">float</span><span class="sxs-lookup"><span data-stu-id="1b830-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-302">未到達檢視器之內容的缺口密度，但已被捨棄並以全新內容覆寫。</span><span class="sxs-lookup"><span data-stu-id="1b830-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-304">float</span><span class="sxs-lookup"><span data-stu-id="1b830-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-305">未到達檢視器而被捨棄並以全新內容覆寫之內容的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-307">float</span><span class="sxs-lookup"><span data-stu-id="1b830-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-308">從圖形來源消去的框架總數目。</span><span class="sxs-lookup"><span data-stu-id="1b830-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-310">float</span><span class="sxs-lookup"><span data-stu-id="1b830-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-311">從圖形來源消去的平均框架數目。</span><span class="sxs-lookup"><span data-stu-id="1b830-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-313">float</span><span class="sxs-lookup"><span data-stu-id="1b830-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-314">從圖形來源消去的最大相框數目。</span><span class="sxs-lookup"><span data-stu-id="1b830-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-316">int</span><span class="sxs-lookup"><span data-stu-id="1b830-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-317">從圖形來源消去的幀中的出現爆發。</span><span class="sxs-lookup"><span data-stu-id="1b830-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-319">float</span><span class="sxs-lookup"><span data-stu-id="1b830-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-320">從圖形來源消去之框架中的流量密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-322">float</span><span class="sxs-lookup"><span data-stu-id="1b830-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-323">從圖形來源消去之框架中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-325">int</span><span class="sxs-lookup"><span data-stu-id="1b830-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-326">從圖形來源消去之框架中的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-328">float</span><span class="sxs-lookup"><span data-stu-id="1b830-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-329">從圖形來源消去之框架中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-331">float</span><span class="sxs-lookup"><span data-stu-id="1b830-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-332">從圖形來源消去之框架中的空隙 duration。</span><span class="sxs-lookup"><span data-stu-id="1b830-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-334">float</span><span class="sxs-lookup"><span data-stu-id="1b830-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-335">檢視器接收到的內送框架速率總數。</span><span class="sxs-lookup"><span data-stu-id="1b830-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-337">float</span><span class="sxs-lookup"><span data-stu-id="1b830-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-338">檢視器接收的平均內送框架速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-340">float</span><span class="sxs-lookup"><span data-stu-id="1b830-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-341">檢視器所收到的傳入磚率上限。</span><span class="sxs-lookup"><span data-stu-id="1b830-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-343">int</span><span class="sxs-lookup"><span data-stu-id="1b830-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-344">由檢視器接收的傳入磚速率中的突發流量。</span><span class="sxs-lookup"><span data-stu-id="1b830-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-346">float</span><span class="sxs-lookup"><span data-stu-id="1b830-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-347">由檢視器接收的傳入磚速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-349">float</span><span class="sxs-lookup"><span data-stu-id="1b830-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-350">由檢視器接收的傳入磚速率中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-352">int</span><span class="sxs-lookup"><span data-stu-id="1b830-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-353">由 viewer 接收的內送磚速率中的間距發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-355">float</span><span class="sxs-lookup"><span data-stu-id="1b830-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-356">由 viewer 接收的內送磚速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-358">float</span><span class="sxs-lookup"><span data-stu-id="1b830-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-359">依檢視器接收的內送磚速率中的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-361">float</span><span class="sxs-lookup"><span data-stu-id="1b830-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-362">檢視器接收到的內送框架速率總數。</span><span class="sxs-lookup"><span data-stu-id="1b830-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-364">float</span><span class="sxs-lookup"><span data-stu-id="1b830-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-365">檢視器接收的平均內送框架速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-367">float</span><span class="sxs-lookup"><span data-stu-id="1b830-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-368">檢視器接收到的內送框架速率上限。</span><span class="sxs-lookup"><span data-stu-id="1b830-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-370">int</span><span class="sxs-lookup"><span data-stu-id="1b830-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-371">檢視器接收的內送畫面播放速率中的突發流量發生方式。</span><span class="sxs-lookup"><span data-stu-id="1b830-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-373">float</span><span class="sxs-lookup"><span data-stu-id="1b830-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-374">由檢視器接收的內送畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-376">float</span><span class="sxs-lookup"><span data-stu-id="1b830-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-377">以瀏覽器接收的傳入相框速率中的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-379">int</span><span class="sxs-lookup"><span data-stu-id="1b830-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-380">檢視器接收的內送畫面播放速率中的間距發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-382">float</span><span class="sxs-lookup"><span data-stu-id="1b830-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-383">檢視器接收的內送框架速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-385">float</span><span class="sxs-lookup"><span data-stu-id="1b830-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-386">依檢視器接收的內送框架速率中的間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-388">float</span><span class="sxs-lookup"><span data-stu-id="1b830-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-389">寄件者的傳出磚總速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-391">float</span><span class="sxs-lookup"><span data-stu-id="1b830-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-392">寄件者的平均傳出磚速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-394">float</span><span class="sxs-lookup"><span data-stu-id="1b830-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-395">寄件者的傳出磚流量上限。</span><span class="sxs-lookup"><span data-stu-id="1b830-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-397">int</span><span class="sxs-lookup"><span data-stu-id="1b830-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-398">以寄件者的傳出磚速率表示的突發流量發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-400">float</span><span class="sxs-lookup"><span data-stu-id="1b830-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-401">以傳送者之傳出磚速率表示的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-403">float</span><span class="sxs-lookup"><span data-stu-id="1b830-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-404">以寄件者的傳出磚速率表示的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-406">int</span><span class="sxs-lookup"><span data-stu-id="1b830-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-407">以寄件者的傳出磚速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-409">float</span><span class="sxs-lookup"><span data-stu-id="1b830-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-410">以寄件者的傳出磚速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-412">float</span><span class="sxs-lookup"><span data-stu-id="1b830-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-413">以寄件者的傳出磚速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-415">float</span><span class="sxs-lookup"><span data-stu-id="1b830-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-416">寄件者的傳出畫面速率總數。</span><span class="sxs-lookup"><span data-stu-id="1b830-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-418">float</span><span class="sxs-lookup"><span data-stu-id="1b830-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-419">寄件者的平均傳出畫面速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-421">float</span><span class="sxs-lookup"><span data-stu-id="1b830-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-422">寄件者的最大傳出畫面速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-424">int</span><span class="sxs-lookup"><span data-stu-id="1b830-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-425">寄件者的傳出畫面速率中的暴沖出現次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-427">float</span><span class="sxs-lookup"><span data-stu-id="1b830-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-428">寄件者的傳出畫面速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-430">float</span><span class="sxs-lookup"><span data-stu-id="1b830-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-431">以寄件者的傳出畫面速率表示的暴沖持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-433">int</span><span class="sxs-lookup"><span data-stu-id="1b830-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-434">以寄件者的傳出畫面速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="1b830-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-436">float</span><span class="sxs-lookup"><span data-stu-id="1b830-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-437">寄件者的傳出畫面速率中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="1b830-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-439">float</span><span class="sxs-lookup"><span data-stu-id="1b830-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-440">以寄件者的傳出畫面速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="1b830-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-442">int</span><span class="sxs-lookup"><span data-stu-id="1b830-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-443">影片的平均解析度高度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="1b830-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-445">int</span><span class="sxs-lookup"><span data-stu-id="1b830-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-446">影片的平均解析度寬度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="1b830-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-447"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-448">位</span><span class="sxs-lookup"><span data-stu-id="1b830-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-449">輸入傳輸的平均每秒幀 () 的平均框架速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b830-450"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-451">位</span><span class="sxs-lookup"><span data-stu-id="1b830-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-452">輸出傳輸) 每秒幀中 (的平均框架速率。</span><span class="sxs-lookup"><span data-stu-id="1b830-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b830-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="1b830-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="1b830-454">位</span><span class="sxs-lookup"><span data-stu-id="1b830-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1b830-455">1表示資料流程的方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="1b830-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="1b830-456">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="1b830-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

