---
title: Lync Server 2013： AppSharingStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974473"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="389cb-102">Lync Server 2013 中的 AppSharingStream 表格</span><span class="sxs-lookup"><span data-stu-id="389cb-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="389cb-103">_**主題上次修改日期：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="389cb-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="389cb-104">AppSharingStream 表格包含用於應用程式共用之網路資料流程的經驗品質度量單位。</span><span class="sxs-lookup"><span data-stu-id="389cb-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="389cb-105">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="389cb-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="389cb-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="389cb-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="389cb-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="389cb-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="389cb-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="389cb-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="389cb-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="389cb-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="389cb-113">會話開始的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-115">int</span><span class="sxs-lookup"><span data-stu-id="389cb-115">int</span></span></p></td>
<td><p><span data-ttu-id="389cb-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="389cb-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="389cb-117">使用順序識別碼來區分在相同日期和同一時間啟動的會話。</span><span class="sxs-lookup"><span data-stu-id="389cb-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="389cb-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="389cb-120">主要、外部</span><span class="sxs-lookup"><span data-stu-id="389cb-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="389cb-121">代表通話中使用的影片線條類型。</span><span class="sxs-lookup"><span data-stu-id="389cb-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="389cb-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="389cb-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="389cb-123">0-音訊</span><span class="sxs-lookup"><span data-stu-id="389cb-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="389cb-124">1–影片</span><span class="sxs-lookup"><span data-stu-id="389cb-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="389cb-125">2-全景影片</span><span class="sxs-lookup"><span data-stu-id="389cb-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="389cb-126">3-應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="389cb-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-128">int</span><span class="sxs-lookup"><span data-stu-id="389cb-128">int</span></span></p></td>
<td><p><span data-ttu-id="389cb-129">首選</span><span class="sxs-lookup"><span data-stu-id="389cb-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="389cb-130">應用程式共用資料流程的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="389cb-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-132">int</span><span class="sxs-lookup"><span data-stu-id="389cb-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-133">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="389cb-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="389cb-134">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="389cb-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-136">int</span><span class="sxs-lookup"><span data-stu-id="389cb-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-137">在 RTP 資料包抵達之間檢測到最大抖動。</span><span class="sxs-lookup"><span data-stu-id="389cb-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="389cb-138">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="389cb-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-139"><strong>環路</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-140">int</span><span class="sxs-lookup"><span data-stu-id="389cb-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-141">即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="389cb-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="389cb-142">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="389cb-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="389cb-143">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="389cb-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="389cb-144">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="389cb-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-146">int</span><span class="sxs-lookup"><span data-stu-id="389cb-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-147">即時傳輸通訊協定資料包要傳送到另一個端點的最大值（以毫秒為單位），然後返回。</span><span class="sxs-lookup"><span data-stu-id="389cb-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="389cb-148">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="389cb-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="389cb-149">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="389cb-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="389cb-150">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="389cb-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-152">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-153">即時傳輸通訊協定（RTP）資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="389cb-154">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="389cb-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="389cb-155">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="389cb-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-157">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-158">即時傳輸通訊協定（RTP）資料包遺失率的最大值。</span><span class="sxs-lookup"><span data-stu-id="389cb-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="389cb-159">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="389cb-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="389cb-160">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="389cb-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-162">int</span><span class="sxs-lookup"><span data-stu-id="389cb-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-163">已傳送的資料包數目。</span><span class="sxs-lookup"><span data-stu-id="389cb-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-165">int</span><span class="sxs-lookup"><span data-stu-id="389cb-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-166">會話結束時可使用的估計單向頻寬。</span><span class="sxs-lookup"><span data-stu-id="389cb-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="389cb-167">以每秒位數報告。</span><span class="sxs-lookup"><span data-stu-id="389cb-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-169">int</span><span class="sxs-lookup"><span data-stu-id="389cb-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-170">應用程式共用負載的描述。</span><span class="sxs-lookup"><span data-stu-id="389cb-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-172">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-173">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="389cb-173">Total amount of one-way latency.</span></span> <span data-ttu-id="389cb-174">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-176">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-177">單向延隔時間的平均量。</span><span class="sxs-lookup"><span data-stu-id="389cb-177">Average amount of one-way latency.</span></span> <span data-ttu-id="389cb-178">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-180">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-181">單向延隔時間的最大值。</span><span class="sxs-lookup"><span data-stu-id="389cb-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="389cb-182">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-184">int</span><span class="sxs-lookup"><span data-stu-id="389cb-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-185">單向突發發生次數總計。</span><span class="sxs-lookup"><span data-stu-id="389cb-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="389cb-186">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="389cb-187">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-189">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-190">總計單向突發密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-190">Total one-way burst density.</span></span> <span data-ttu-id="389cb-191">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="389cb-192">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-194">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-195">總計單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-195">Total one-way burst duration.</span></span> <span data-ttu-id="389cb-196">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="389cb-197">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-199">int</span><span class="sxs-lookup"><span data-stu-id="389cb-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-200">總的單向間距發生情況。</span><span class="sxs-lookup"><span data-stu-id="389cb-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="389cb-201">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="389cb-202">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-204">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-205">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-205">Total one-way gap density.</span></span> <span data-ttu-id="389cb-206">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="389cb-207">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-209">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-210">總共一個單向間距時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-210">Total one-way gap duration.</span></span> <span data-ttu-id="389cb-211">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="389cb-212">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-214">varChar （256）</span><span class="sxs-lookup"><span data-stu-id="389cb-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-215">應用程式角色（共用或檢視器）與內容類型。</span><span class="sxs-lookup"><span data-stu-id="389cb-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-217">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-218">遠端桌面通訊協定（RDP）磚的總處理時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-219">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-221">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-222">遠端桌面通訊協定（RDP）磚的平均處理時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-223">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-225">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-226">遠端桌面通訊協定（RDP）磚的最大處理時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-227">較高的總計相當於觀賞體驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="389cb-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-229">int</span><span class="sxs-lookup"><span data-stu-id="389cb-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-230">遠端桌面通訊協定（RDP）磚處理時間的突發事件發生方式。</span><span class="sxs-lookup"><span data-stu-id="389cb-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-231">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-233">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-234">遠端桌面通訊協定（RDP）磚處理時間的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-235">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-237">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-238">遠端桌面通訊協定（RDP）磚處理時間中的爆發時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-239">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="389cb-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-241">int</span><span class="sxs-lookup"><span data-stu-id="389cb-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-242">遠端桌面通訊協定（RDP）磚處理時間中的差距出現次數。</span><span class="sxs-lookup"><span data-stu-id="389cb-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-244">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-245">遠端桌面通訊協定（RDP）磚處理時間的差距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-246">低差距密度可讓您獲得更佳的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="389cb-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-248">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-249">遠端桌面通訊協定（RDP）磚處理時間中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="389cb-250">短差距期間會等同于更佳的觀賞體驗。</span><span class="sxs-lookup"><span data-stu-id="389cb-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-252">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-253">捕獲磚的總速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="389cb-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-255">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-256">捕獲磚的平均速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="389cb-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-258">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-259">捕獲磚的最大速率（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="389cb-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-261">在 t</span><span class="sxs-lookup"><span data-stu-id="389cb-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-262">在捕獲磚（每秒磚數）中，突發發生的頻率。</span><span class="sxs-lookup"><span data-stu-id="389cb-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-264">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-265">捕獲磚（每秒磚）的流量峰值密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-267">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-268">以捕獲磚（每秒磚）為單位的爆發時段。</span><span class="sxs-lookup"><span data-stu-id="389cb-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-270">int</span><span class="sxs-lookup"><span data-stu-id="389cb-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-271">間距出現在捕獲磚的速率中（每秒磚）。</span><span class="sxs-lookup"><span data-stu-id="389cb-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-273">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-274">已捕獲磚（每秒磚）中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-276">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-277">所捕獲磚（每秒磚）中的差距間隔時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-279">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-280">未到達檢視器的內容總百分比，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-282">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-283">未到達檢視器的內容平均百分比，而是由新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-285">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-286">未到達檢視器的內容的最大百分比，而是由新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-288">int</span><span class="sxs-lookup"><span data-stu-id="389cb-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-289">無法到達檢視器的內容突發事件，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-291">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-292">未到達檢視器之內容的突發密度，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-294">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-295">無法到達檢視器之內容的爆發持續時間，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-297">int</span><span class="sxs-lookup"><span data-stu-id="389cb-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-298">未到達檢視器之內容的差距出現次數，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-300">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-301">未到達檢視器之內容的差距密度，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-303">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-304">未到達檢視器之內容的差距持續時間，但已被新內容捨棄並覆寫。</span><span class="sxs-lookup"><span data-stu-id="389cb-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-306">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-307">圖形來源的畫面總 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="389cb-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-309">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-310">圖形來源的平均幀 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="389cb-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-312">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-313">圖形來源中的最大幀 scraped 數。</span><span class="sxs-lookup"><span data-stu-id="389cb-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-315">int</span><span class="sxs-lookup"><span data-stu-id="389cb-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-316">來自圖形來源的 [幀 scraped] 中的 [突發] 出現次數。</span><span class="sxs-lookup"><span data-stu-id="389cb-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-318">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-319">圖形來源的 [幀 scraped] 中的 [暴沖密度]。</span><span class="sxs-lookup"><span data-stu-id="389cb-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-321">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-322">圖形來源的 [幀 scraped] 中的 [突發期間]。</span><span class="sxs-lookup"><span data-stu-id="389cb-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-324">int</span><span class="sxs-lookup"><span data-stu-id="389cb-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-325">圖形來源的 [幀 scraped] 中的空隙出現次數。</span><span class="sxs-lookup"><span data-stu-id="389cb-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-327">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-328">圖形來源的 [框架 scraped] 中的間距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-330">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-331">圖形來源的 [框架 scraped] 中的 [空隙] 工期。</span><span class="sxs-lookup"><span data-stu-id="389cb-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-333">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-334">檢視器接收的傳入畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="389cb-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-336">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-337">檢視器接收到的平均接收畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-339">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-340">檢視器接收到的傳入磚速率上限。</span><span class="sxs-lookup"><span data-stu-id="389cb-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-342">int</span><span class="sxs-lookup"><span data-stu-id="389cb-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-343">檢視器接收到的傳入磚速率中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="389cb-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-345">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-346">檢視器接收的傳入磚速率中的高載密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-348">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-349">檢視器接收的傳入磚速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-351">int</span><span class="sxs-lookup"><span data-stu-id="389cb-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-352">檢視器接收的傳入磚速率中的間距值。</span><span class="sxs-lookup"><span data-stu-id="389cb-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-354">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-355">檢視器接收的傳入磚速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-357">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-358">檢視器接收到的內送磚速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-360">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-361">檢視器接收的傳入畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="389cb-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-363">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-364">檢視器接收到的平均接收畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-366">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-367">檢視器接收到的最大傳入畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-369">int</span><span class="sxs-lookup"><span data-stu-id="389cb-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-370">檢視器接收到的傳入畫面播放速率中的爆發次數。</span><span class="sxs-lookup"><span data-stu-id="389cb-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-372">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-373">檢視器接收到的傳入畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-375">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-376">檢視器接收到的傳入畫面播放速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-378">int</span><span class="sxs-lookup"><span data-stu-id="389cb-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-379">檢視器接收到的內送畫面播放速率中出現的間距。</span><span class="sxs-lookup"><span data-stu-id="389cb-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-381">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-382">檢視器接收的傳入畫面播放速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-384">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-385">檢視器接收的傳入畫面播放速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-387">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-388">寄件者的外寄磚率總計。</span><span class="sxs-lookup"><span data-stu-id="389cb-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-390">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-391">寄件者的平均外寄磚速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-393">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-394">寄件者的最大外寄磚速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-396">int</span><span class="sxs-lookup"><span data-stu-id="389cb-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-397">寄件者的傳出磚速率中的突發事件。</span><span class="sxs-lookup"><span data-stu-id="389cb-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-399">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-400">寄件者的傳出磚速率的高載密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-402">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-403">寄件者的傳出磚頻率內的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-405">int</span><span class="sxs-lookup"><span data-stu-id="389cb-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-406">寄件者的外寄磚頻率中出現空隙。</span><span class="sxs-lookup"><span data-stu-id="389cb-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-408">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-409">寄件者的外寄磚工資率的差距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-411">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-412">寄件者的外寄磚工資率的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-414">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-415">寄件者的外寄畫面播放速率總計。</span><span class="sxs-lookup"><span data-stu-id="389cb-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-417">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-418">寄件者的平均傳出畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-420">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-421">寄件者的最大外寄畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="389cb-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-423">int</span><span class="sxs-lookup"><span data-stu-id="389cb-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-424">寄件者在外寄畫面播放速率中的突發事件。</span><span class="sxs-lookup"><span data-stu-id="389cb-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-426">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-427">寄件者的外寄畫面播放速率中的暴沖密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-429">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-430">寄件者的外寄畫面播放速率中的爆發持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-432">int</span><span class="sxs-lookup"><span data-stu-id="389cb-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-433">寄件者的外寄畫面播放速率中出現空隙。</span><span class="sxs-lookup"><span data-stu-id="389cb-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-435">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-436">寄件者的外寄畫面播放速率中的差距密度。</span><span class="sxs-lookup"><span data-stu-id="389cb-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-438">浮</span><span class="sxs-lookup"><span data-stu-id="389cb-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-439">寄件者的外寄畫面播放速率中的差距持續時間。</span><span class="sxs-lookup"><span data-stu-id="389cb-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-441">int</span><span class="sxs-lookup"><span data-stu-id="389cb-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-442">平均視頻解析度高度（以圖元為單位）。</span><span class="sxs-lookup"><span data-stu-id="389cb-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-444">int</span><span class="sxs-lookup"><span data-stu-id="389cb-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-445">以圖元為單位的平均視頻解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="389cb-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-446"><strong>進貨</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-447">稍微</span><span class="sxs-lookup"><span data-stu-id="389cb-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-448">入站傳輸的平均畫面播放速率（在每秒的幀數）。</span><span class="sxs-lookup"><span data-stu-id="389cb-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="389cb-449"><strong>發</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-450">稍微</span><span class="sxs-lookup"><span data-stu-id="389cb-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-451">輸出傳送的平均畫面播放速率（在每秒的幀數）。</span><span class="sxs-lookup"><span data-stu-id="389cb-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="389cb-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="389cb-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="389cb-453">稍微</span><span class="sxs-lookup"><span data-stu-id="389cb-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="389cb-454">1表示資料流程方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="389cb-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="389cb-455">0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="389cb-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

