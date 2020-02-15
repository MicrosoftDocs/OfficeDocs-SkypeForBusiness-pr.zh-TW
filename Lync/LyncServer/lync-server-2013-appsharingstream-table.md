---
title: 'Lync Server 2013: AppSharingStream 表'
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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="96e37-102">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="96e37-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96e37-103">_**上次修改主題：** 2014年-02-21_</span><span class="sxs-lookup"><span data-stu-id="96e37-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="96e37-104">AppSharingStream 表包含用於應用程式共用的網路資料流的經驗品質計量。</span><span class="sxs-lookup"><span data-stu-id="96e37-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="96e37-105">Microsoft Lync Server 2013 中已採用此表格。</span><span class="sxs-lookup"><span data-stu-id="96e37-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96e37-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="96e37-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="96e37-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="96e37-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96e37-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="96e37-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="96e37-112">主要、外部</span><span class="sxs-lookup"><span data-stu-id="96e37-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96e37-113">日期和啟動工作階段的時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-115">int</span><span class="sxs-lookup"><span data-stu-id="96e37-115">int</span></span></p></td>
<td><p><span data-ttu-id="96e37-116">主要、外部</span><span class="sxs-lookup"><span data-stu-id="96e37-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96e37-117">用來區分工作階段的開始日期相同，並同時連續的識別碼。</span><span class="sxs-lookup"><span data-stu-id="96e37-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="96e37-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96e37-120">主要，外部</span><span class="sxs-lookup"><span data-stu-id="96e37-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96e37-121">代表呼叫時所使用的視訊線的類型。</span><span class="sxs-lookup"><span data-stu-id="96e37-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="96e37-122">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="96e37-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="96e37-123">0 – 音訊</span><span class="sxs-lookup"><span data-stu-id="96e37-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="96e37-124">1 – 影片</span><span class="sxs-lookup"><span data-stu-id="96e37-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="96e37-125">2 – 全景視訊</span><span class="sxs-lookup"><span data-stu-id="96e37-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="96e37-126">3 – 應用程式/桌面共用</span><span class="sxs-lookup"><span data-stu-id="96e37-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-128">int</span><span class="sxs-lookup"><span data-stu-id="96e37-128">int</span></span></p></td>
<td><p><span data-ttu-id="96e37-129">主要</span><span class="sxs-lookup"><span data-stu-id="96e37-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="96e37-130">應用程式共用資料流的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="96e37-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-132">int</span><span class="sxs-lookup"><span data-stu-id="96e37-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-133">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="96e37-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="96e37-134">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-136">int</span><span class="sxs-lookup"><span data-stu-id="96e37-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-137">偵測到 RTP 封包抵達之間的最大抖動。</span><span class="sxs-lookup"><span data-stu-id="96e37-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="96e37-138">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-139"><strong>來回</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-140">int</span><span class="sxs-lookup"><span data-stu-id="96e37-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-141">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="96e37-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="96e37-142">200 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="96e37-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="96e37-143">高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="96e37-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="96e37-144">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="96e37-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-146">int</span><span class="sxs-lookup"><span data-stu-id="96e37-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-147">最大量 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="96e37-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="96e37-148">200 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="96e37-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="96e37-149">高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="96e37-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="96e37-150">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="96e37-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-152">float</span><span class="sxs-lookup"><span data-stu-id="96e37-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-153">即時傳輸通訊協定 (RTP) 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="96e37-154">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="96e37-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="96e37-155">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-157">float</span><span class="sxs-lookup"><span data-stu-id="96e37-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-158">即時傳輸通訊協定 (RTP) 封包遺失量的最大速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="96e37-159">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="96e37-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="96e37-160">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-162">int</span><span class="sxs-lookup"><span data-stu-id="96e37-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-163">傳送的封包數。</span><span class="sxs-lookup"><span data-stu-id="96e37-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-165">int</span><span class="sxs-lookup"><span data-stu-id="96e37-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-166">估計可用的單向頻寬工作階段的結尾。</span><span class="sxs-lookup"><span data-stu-id="96e37-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="96e37-167">報告每秒位元數。</span><span class="sxs-lookup"><span data-stu-id="96e37-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-169">int</span><span class="sxs-lookup"><span data-stu-id="96e37-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-170">共用裝載的應用程式的描述。</span><span class="sxs-lookup"><span data-stu-id="96e37-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-172">float</span><span class="sxs-lookup"><span data-stu-id="96e37-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-173">總數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-173">Total amount of one-way latency.</span></span> <span data-ttu-id="96e37-174">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-176">float</span><span class="sxs-lookup"><span data-stu-id="96e37-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-177">平均量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-177">Average amount of one-way latency.</span></span> <span data-ttu-id="96e37-178">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-180">float</span><span class="sxs-lookup"><span data-stu-id="96e37-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-181">最大數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="96e37-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="96e37-182">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-184">int</span><span class="sxs-lookup"><span data-stu-id="96e37-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-185">總單向的高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="96e37-186">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="96e37-187">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-189">float</span><span class="sxs-lookup"><span data-stu-id="96e37-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-190">總單向的高載密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-190">Total one-way burst density.</span></span> <span data-ttu-id="96e37-191">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="96e37-192">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-194">float</span><span class="sxs-lookup"><span data-stu-id="96e37-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-195">總單向的高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-195">Total one-way burst duration.</span></span> <span data-ttu-id="96e37-196">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="96e37-197">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-199">int</span><span class="sxs-lookup"><span data-stu-id="96e37-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-200">總單向的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="96e37-201">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="96e37-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="96e37-202">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-204">float</span><span class="sxs-lookup"><span data-stu-id="96e37-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-205">總單向的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-205">Total one-way gap density.</span></span> <span data-ttu-id="96e37-206">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="96e37-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="96e37-207">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-209">float</span><span class="sxs-lookup"><span data-stu-id="96e37-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-210">總單向缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-210">Total one-way gap duration.</span></span> <span data-ttu-id="96e37-211">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="96e37-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="96e37-212">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="96e37-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-214">varChar(256)</span><span class="sxs-lookup"><span data-stu-id="96e37-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-215">應用程式角色 （共享者或檢視器） 及內容類型。</span><span class="sxs-lookup"><span data-stu-id="96e37-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-217">float</span><span class="sxs-lookup"><span data-stu-id="96e37-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-218">遠端桌面通訊協定 (RDP) 磚的總處理時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-219">較高的總等於長的延遲時間，以檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="96e37-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-221">float</span><span class="sxs-lookup"><span data-stu-id="96e37-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-222">平均處理時間遠端桌面通訊協定 (RDP) 磚。</span><span class="sxs-lookup"><span data-stu-id="96e37-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-223">較高的總等於長的延遲時間，以檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="96e37-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-225">float</span><span class="sxs-lookup"><span data-stu-id="96e37-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-226">遠端桌面通訊協定 (RDP) 磚的最大處理時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-227">較高的總等於長的延遲時間，以檢視體驗。</span><span class="sxs-lookup"><span data-stu-id="96e37-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-229">int</span><span class="sxs-lookup"><span data-stu-id="96e37-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-230">遠端桌面通訊協定 (RDP) 磚之處理時間內，高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-231">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-233">float</span><span class="sxs-lookup"><span data-stu-id="96e37-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-234">遠端桌面通訊協定 (RDP) 磚之處理時間內，高載密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-235">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-237">float</span><span class="sxs-lookup"><span data-stu-id="96e37-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-238">高載持續時間在遠端桌面通訊協定 (RDP) 磚之處理時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-239">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="96e37-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-241">int</span><span class="sxs-lookup"><span data-stu-id="96e37-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-242">遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-244">float</span><span class="sxs-lookup"><span data-stu-id="96e37-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-245">遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-246">低表示的缺口密度等於較佳的檢視經驗。</span><span class="sxs-lookup"><span data-stu-id="96e37-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-248">float</span><span class="sxs-lookup"><span data-stu-id="96e37-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-249">遠端桌面通訊協定 (RDP) 磚之處理時間內的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="96e37-250">簡短表示的缺口持續時間等同於較佳的檢視經驗。</span><span class="sxs-lookup"><span data-stu-id="96e37-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-252">float</span><span class="sxs-lookup"><span data-stu-id="96e37-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-253">擷取磚 （單位為每秒磚數） 的總速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-255">float</span><span class="sxs-lookup"><span data-stu-id="96e37-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-256">擷取磚 （單位為每秒磚數） 的平均速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-258">float</span><span class="sxs-lookup"><span data-stu-id="96e37-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-259">擷取磚 （單位為每秒磚數） 的最大速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-261">int</span><span class="sxs-lookup"><span data-stu-id="96e37-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-262">高載發生次數 （單位為每秒磚數） 擷取磚的速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-264">float</span><span class="sxs-lookup"><span data-stu-id="96e37-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-265">高載密度 （單位為每秒磚數） 擷取磚的速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-267">float</span><span class="sxs-lookup"><span data-stu-id="96e37-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-268">高載持續時間 （單位為每秒磚數） 擷取磚的速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-270">int</span><span class="sxs-lookup"><span data-stu-id="96e37-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-271">（單位為每秒磚數） 擷取磚速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-273">float</span><span class="sxs-lookup"><span data-stu-id="96e37-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-274">（單位為每秒磚數） 擷取磚速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-276">float</span><span class="sxs-lookup"><span data-stu-id="96e37-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-277">（單位為每秒磚數） 擷取磚速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-279">float</span><span class="sxs-lookup"><span data-stu-id="96e37-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-280">未抵達檢視者而被捨棄並以更新內容覆寫之內容的總百分比。</span><span class="sxs-lookup"><span data-stu-id="96e37-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-282">float</span><span class="sxs-lookup"><span data-stu-id="96e37-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-283">未抵達檢視者而被捨棄並以更新內容覆寫之內容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="96e37-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-285">float</span><span class="sxs-lookup"><span data-stu-id="96e37-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-286">未抵達檢視者而被捨棄並以更新內容覆寫之內容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="96e37-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-288">int</span><span class="sxs-lookup"><span data-stu-id="96e37-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-289">高載發生次數未抵達檢視者而被捨棄並以更新內容覆寫之內容。</span><span class="sxs-lookup"><span data-stu-id="96e37-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-291">float</span><span class="sxs-lookup"><span data-stu-id="96e37-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-292">高載密度未抵達檢視者而被捨棄並以更新內容覆寫之內容。</span><span class="sxs-lookup"><span data-stu-id="96e37-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-294">float</span><span class="sxs-lookup"><span data-stu-id="96e37-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-295">高載持續時間之內容的未抵達檢視者而被捨棄並以更新內容覆寫。</span><span class="sxs-lookup"><span data-stu-id="96e37-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-297">int</span><span class="sxs-lookup"><span data-stu-id="96e37-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-298">未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-300">float</span><span class="sxs-lookup"><span data-stu-id="96e37-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-301">未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-303">float</span><span class="sxs-lookup"><span data-stu-id="96e37-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-304">未抵達檢視者而被捨棄並以更新內容覆寫之內容的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-306">float</span><span class="sxs-lookup"><span data-stu-id="96e37-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-307">從圖形來源消去的總數。</span><span class="sxs-lookup"><span data-stu-id="96e37-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-309">float</span><span class="sxs-lookup"><span data-stu-id="96e37-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-310">從圖形來源消去的平均數。</span><span class="sxs-lookup"><span data-stu-id="96e37-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-312">float</span><span class="sxs-lookup"><span data-stu-id="96e37-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-313">從圖形來源消去的數目上限。</span><span class="sxs-lookup"><span data-stu-id="96e37-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-315">int</span><span class="sxs-lookup"><span data-stu-id="96e37-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-316">從圖形來源消高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-318">float</span><span class="sxs-lookup"><span data-stu-id="96e37-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-319">從圖形來源消高載密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-321">float</span><span class="sxs-lookup"><span data-stu-id="96e37-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-322">從圖形來源消高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-324">int</span><span class="sxs-lookup"><span data-stu-id="96e37-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-325">從圖形來源消表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-327">float</span><span class="sxs-lookup"><span data-stu-id="96e37-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-328">從圖形來源消表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-330">float</span><span class="sxs-lookup"><span data-stu-id="96e37-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-331">從圖形來源消表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-333">float</span><span class="sxs-lookup"><span data-stu-id="96e37-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-334">以檢視者接收到的總傳入畫面速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-336">float</span><span class="sxs-lookup"><span data-stu-id="96e37-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-337">以檢視者接收到的平均傳入畫面速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-339">float</span><span class="sxs-lookup"><span data-stu-id="96e37-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-340">以檢視者接收到的最大的傳入磚速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-342">int</span><span class="sxs-lookup"><span data-stu-id="96e37-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-343">高載發生次數的傳入磚速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-345">float</span><span class="sxs-lookup"><span data-stu-id="96e37-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-346">高載密度的傳入磚速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-348">float</span><span class="sxs-lookup"><span data-stu-id="96e37-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-349">高載持續時間的傳入磚速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-351">int</span><span class="sxs-lookup"><span data-stu-id="96e37-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-352">以檢視者接收到的傳入磚速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-354">float</span><span class="sxs-lookup"><span data-stu-id="96e37-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-355">以檢視者接收到的傳入磚速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-357">float</span><span class="sxs-lookup"><span data-stu-id="96e37-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-358">以檢視者接收到的傳入磚速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-360">float</span><span class="sxs-lookup"><span data-stu-id="96e37-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-361">以檢視者接收到的總傳入畫面速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-363">float</span><span class="sxs-lookup"><span data-stu-id="96e37-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-364">以檢視者接收到的平均傳入畫面速率。</span><span class="sxs-lookup"><span data-stu-id="96e37-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-366">float</span><span class="sxs-lookup"><span data-stu-id="96e37-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-367">最大傳入畫面速率為以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-369">int</span><span class="sxs-lookup"><span data-stu-id="96e37-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-370">高載發生次數的傳入畫面速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-372">float</span><span class="sxs-lookup"><span data-stu-id="96e37-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-373">高載密度的傳入畫面速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-375">float</span><span class="sxs-lookup"><span data-stu-id="96e37-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-376">高載持續時間的傳入畫面速率，以檢視者接收到。</span><span class="sxs-lookup"><span data-stu-id="96e37-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-378">int</span><span class="sxs-lookup"><span data-stu-id="96e37-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-379">以檢視者接收到的傳入畫面速率表示的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="96e37-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-381">float</span><span class="sxs-lookup"><span data-stu-id="96e37-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-382">以檢視者接收到的傳入畫面速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-384">float</span><span class="sxs-lookup"><span data-stu-id="96e37-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-385">以檢視者接收到的傳入畫面速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-387">float</span><span class="sxs-lookup"><span data-stu-id="96e37-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-388">傳出磚總速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-390">float</span><span class="sxs-lookup"><span data-stu-id="96e37-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-391">傳出磚平均速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-393">float</span><span class="sxs-lookup"><span data-stu-id="96e37-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-394">最大傳出磚速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-396">int</span><span class="sxs-lookup"><span data-stu-id="96e37-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-397">表示之高載發生次數之傳出磚速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-399">float</span><span class="sxs-lookup"><span data-stu-id="96e37-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-400">表示之高載密度之傳出磚速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-402">float</span><span class="sxs-lookup"><span data-stu-id="96e37-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-403">表示之高載持續時間之傳出磚速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-405">int</span><span class="sxs-lookup"><span data-stu-id="96e37-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-406">表示的缺口發生次數之傳出磚速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-408">float</span><span class="sxs-lookup"><span data-stu-id="96e37-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-409">寄件者之傳出磚速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-411">float</span><span class="sxs-lookup"><span data-stu-id="96e37-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-412">寄件者之傳出磚速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-414">float</span><span class="sxs-lookup"><span data-stu-id="96e37-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-415">傳出畫面總速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-417">float</span><span class="sxs-lookup"><span data-stu-id="96e37-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-418">傳出畫面平均速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-420">float</span><span class="sxs-lookup"><span data-stu-id="96e37-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-421">最大傳出畫面速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-423">int</span><span class="sxs-lookup"><span data-stu-id="96e37-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-424">表示之高載發生次數之傳出畫面速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-426">float</span><span class="sxs-lookup"><span data-stu-id="96e37-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-427">表示之高載密度之傳出畫面速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-429">float</span><span class="sxs-lookup"><span data-stu-id="96e37-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-430">表示之高載持續時間之傳出畫面速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-432">int</span><span class="sxs-lookup"><span data-stu-id="96e37-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-433">表示的缺口發生次數之傳出畫面速率寄件者。</span><span class="sxs-lookup"><span data-stu-id="96e37-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-435">float</span><span class="sxs-lookup"><span data-stu-id="96e37-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-436">寄件者之傳出畫面速率表示的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="96e37-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-438">float</span><span class="sxs-lookup"><span data-stu-id="96e37-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-439">寄件者之傳出畫面速率表示的缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="96e37-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-441">int</span><span class="sxs-lookup"><span data-stu-id="96e37-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-442">平均視訊解析度高度，以像素為單位。</span><span class="sxs-lookup"><span data-stu-id="96e37-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-444">int</span><span class="sxs-lookup"><span data-stu-id="96e37-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-445">平均視訊解析度寬度，以像素為單位。</span><span class="sxs-lookup"><span data-stu-id="96e37-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-446"><strong>輸入</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-447">位元</span><span class="sxs-lookup"><span data-stu-id="96e37-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-448">平均畫面速率 （以每秒畫面數） 輸入傳輸。</span><span class="sxs-lookup"><span data-stu-id="96e37-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96e37-449"><strong>輸出</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-450">位元</span><span class="sxs-lookup"><span data-stu-id="96e37-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-451">平均播放速率 （以每秒） 輸出傳輸的。</span><span class="sxs-lookup"><span data-stu-id="96e37-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96e37-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="96e37-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="96e37-453">位元</span><span class="sxs-lookup"><span data-stu-id="96e37-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96e37-454">1 表示資料流是從發話者流向受話者。</span><span class="sxs-lookup"><span data-stu-id="96e37-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="96e37-455">0 表示資料流是從受話者流向發話者。</span><span class="sxs-lookup"><span data-stu-id="96e37-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

