---
title: Lync Server 2013： AudioStream 表格
description: Lync Server 2013： AudioStream 表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552339"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="df219-103">Lync Server 2013 中的 AudioStream 表格</span><span class="sxs-lookup"><span data-stu-id="df219-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df219-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="df219-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="df219-105">每筆記錄代表一個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-105">Each record represents one audio stream.</span></span> <span data-ttu-id="df219-106">一個音訊媒體行通常包含兩個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df219-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="df219-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="df219-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="df219-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="df219-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="df219-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="df219-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="df219-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df219-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="df219-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-112">datetime</span><span class="sxs-lookup"><span data-stu-id="df219-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="df219-113">主要</span><span class="sxs-lookup"><span data-stu-id="df219-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="df219-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="df219-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="df219-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-116">int</span><span class="sxs-lookup"><span data-stu-id="df219-116">int</span></span></p></td>
<td><p><span data-ttu-id="df219-117">主要</span><span class="sxs-lookup"><span data-stu-id="df219-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="df219-118">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="df219-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="df219-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="df219-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="df219-121">主要</span><span class="sxs-lookup"><span data-stu-id="df219-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="df219-122">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="df219-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="df219-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-124">int</span><span class="sxs-lookup"><span data-stu-id="df219-124">int</span></span></p></td>
<td><p><span data-ttu-id="df219-125">主要</span><span class="sxs-lookup"><span data-stu-id="df219-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="df219-126">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="df219-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="df219-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-128">int</span><span class="sxs-lookup"><span data-stu-id="df219-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-129">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="df219-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-131">int</span><span class="sxs-lookup"><span data-stu-id="df219-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-132">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="df219-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="df219-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-134">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="df219-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-135">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="df219-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-137">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="df219-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-138">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="df219-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="df219-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-140">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="df219-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-141">通話期間的猝量遺失期間的封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="df219-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="df219-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-143">int</span><span class="sxs-lookup"><span data-stu-id="df219-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-144">通話期間的猝量遺失期間的封包遺失平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="df219-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="df219-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-146">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="df219-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-147">封包遺失失敗之間的平均封包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="df219-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="df219-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-149">int</span><span class="sxs-lookup"><span data-stu-id="df219-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-150">封包遺失的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="df219-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="df219-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-152">臨界值</span><span class="sxs-lookup"><span data-stu-id="df219-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-153">音訊資料流程的封包計數。</span><span class="sxs-lookup"><span data-stu-id="df219-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-154"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="df219-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-155">臨界值</span><span class="sxs-lookup"><span data-stu-id="df219-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-156">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="df219-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-158">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-159">整個通話的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="df219-159">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="df219-160">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="df219-160">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="df219-161">此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。</span><span class="sxs-lookup"><span data-stu-id="df219-161">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="df219-162">可接受的品質應小於0.5。</span><span class="sxs-lookup"><span data-stu-id="df219-162">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-164">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-165">通話期間的最大網路 MOS 降級。</span><span class="sxs-lookup"><span data-stu-id="df219-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-167">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-168">抖動導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="df219-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-170">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-171">封包遺失導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="df219-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="df219-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-173">int</span><span class="sxs-lookup"><span data-stu-id="df219-173">int</span></span></p></td>
<td><p><span data-ttu-id="df219-174">Foreign</span><span class="sxs-lookup"><span data-stu-id="df219-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="df219-175">用於通話的音訊編解碼器，參考來源為 PayloadDescription Table。</span><span class="sxs-lookup"><span data-stu-id="df219-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="df219-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-177">int</span><span class="sxs-lookup"><span data-stu-id="df219-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-178">音訊資料流程的取樣速率。</span><span class="sxs-lookup"><span data-stu-id="df219-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-179"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="df219-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-180">int</span><span class="sxs-lookup"><span data-stu-id="df219-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-181">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="df219-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="df219-182">若為可接受的品質，則應小於100ms。</span><span class="sxs-lookup"><span data-stu-id="df219-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-184">int</span><span class="sxs-lookup"><span data-stu-id="df219-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-185">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="df219-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="df219-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-187">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-188">通話的平均寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="df219-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="df219-189">此度量取決於所用的封包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="df219-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="df219-190">範圍為 [1.0 至 5.0]。</span><span class="sxs-lookup"><span data-stu-id="df219-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="df219-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-192">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-193">通話的最小寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="df219-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="df219-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-195">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-196">已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="df219-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="df219-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-198">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-199">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="df219-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="df219-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-201">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-202">從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="df219-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="df219-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-204">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="df219-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-205">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="df219-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="df219-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-207">位</span><span class="sxs-lookup"><span data-stu-id="df219-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-208">指示是否要將音訊 FEC 用於通話的旗標。</span><span class="sxs-lookup"><span data-stu-id="df219-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-210">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="df219-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-211">音訊修復所產生之隱藏樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="df219-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-213">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="df219-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-214">音訊修復所產生之延伸樣本的平均比率為典型範例。</span><span class="sxs-lookup"><span data-stu-id="df219-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="df219-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-216">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="df219-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-217">音訊修復所產生之壓縮樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="df219-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-218"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="df219-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-219">位</span><span class="sxs-lookup"><span data-stu-id="df219-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-220">接收接收方的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="df219-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-221"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="df219-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-222">位</span><span class="sxs-lookup"><span data-stu-id="df219-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-223">接收寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="df219-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="df219-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-225">位</span><span class="sxs-lookup"><span data-stu-id="df219-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="df219-226">1表示資料流程是從來電者流向被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="df219-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="df219-227">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="df219-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="df219-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-229">float</span><span class="sxs-lookup"><span data-stu-id="df219-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-230">抖動到達時間的標準差。</span><span class="sxs-lookup"><span data-stu-id="df219-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="df219-231">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-233">float</span><span class="sxs-lookup"><span data-stu-id="df219-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-234">修復所隱藏的封包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="df219-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="df219-235">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="df219-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-237">float</span><span class="sxs-lookup"><span data-stu-id="df219-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-238">修復所隱藏之封包的標準差。</span><span class="sxs-lookup"><span data-stu-id="df219-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="df219-239">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="df219-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-241">float</span><span class="sxs-lookup"><span data-stu-id="df219-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-242">修復丟棄的封包比率與接收的封包總數。</span><span class="sxs-lookup"><span data-stu-id="df219-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="df219-243">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="df219-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-245">float</span><span class="sxs-lookup"><span data-stu-id="df219-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-246">與接收的封包總數相比，使用轉寄錯誤修正資料包的比例。</span><span class="sxs-lookup"><span data-stu-id="df219-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="df219-247">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="df219-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-249">float</span><span class="sxs-lookup"><span data-stu-id="df219-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-250">修復壓縮的音訊封包數目上限。</span><span class="sxs-lookup"><span data-stu-id="df219-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="df219-251">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-253">float</span><span class="sxs-lookup"><span data-stu-id="df219-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-254">會指出通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="df219-255">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-257">float</span><span class="sxs-lookup"><span data-stu-id="df219-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-258">會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</span><span class="sxs-lookup"><span data-stu-id="df219-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="df219-259">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-261">float</span><span class="sxs-lookup"><span data-stu-id="df219-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-262">會指出通話在競爭網路資源時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="df219-263">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="df219-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-265">int</span><span class="sxs-lookup"><span data-stu-id="df219-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-266">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="df219-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="df219-267">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-269">int</span><span class="sxs-lookup"><span data-stu-id="df219-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-270">通話期間測量的頻寬預估最大值。</span><span class="sxs-lookup"><span data-stu-id="df219-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="df219-271">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="df219-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-273">int</span><span class="sxs-lookup"><span data-stu-id="df219-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-274">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="df219-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="df219-275">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="df219-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-277">int</span><span class="sxs-lookup"><span data-stu-id="df219-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-278">通話期間測量的平均頻寬預估量。</span><span class="sxs-lookup"><span data-stu-id="df219-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="df219-279">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="df219-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-281">float</span><span class="sxs-lookup"><span data-stu-id="df219-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-282">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="df219-282">Total amount of one-way latency.</span></span> <span data-ttu-id="df219-283">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-283">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-284">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="df219-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-286">float</span><span class="sxs-lookup"><span data-stu-id="df219-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-287">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="df219-287">Average amount of one-way latency.</span></span> <span data-ttu-id="df219-288">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-288">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-289">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="df219-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-291">float</span><span class="sxs-lookup"><span data-stu-id="df219-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-292">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="df219-292">Maximum amount of one-way latency.</span></span> <span data-ttu-id="df219-293">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-293">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-294">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="df219-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-296">int</span><span class="sxs-lookup"><span data-stu-id="df219-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-297">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="df219-297">Total one-way burst occurrences.</span></span> <span data-ttu-id="df219-298">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="df219-298">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="df219-299">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-299">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-300">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="df219-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-302">float</span><span class="sxs-lookup"><span data-stu-id="df219-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-303">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="df219-303">Total one-way burst density.</span></span> <span data-ttu-id="df219-304">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="df219-304">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="df219-305">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-305">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-306">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="df219-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-308">float</span><span class="sxs-lookup"><span data-stu-id="df219-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-309">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="df219-309">Total one-way burst duration.</span></span> <span data-ttu-id="df219-310">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="df219-310">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="df219-311">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-311">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-312">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="df219-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-314">int</span><span class="sxs-lookup"><span data-stu-id="df219-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-315">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="df219-315">Total one-way gap occurrences.</span></span> <span data-ttu-id="df219-316">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-316">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="df219-317">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-317">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-318">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="df219-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-320">float</span><span class="sxs-lookup"><span data-stu-id="df219-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-321">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="df219-321">Total one-way gap density.</span></span> <span data-ttu-id="df219-322">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-322">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="df219-323">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-323">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-324">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="df219-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-326">float</span><span class="sxs-lookup"><span data-stu-id="df219-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-327">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="df219-327">Total one-way gap duration.</span></span> <span data-ttu-id="df219-328">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="df219-328">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="df219-329">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="df219-329">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="df219-330">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-332">float</span><span class="sxs-lookup"><span data-stu-id="df219-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-333">解碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="df219-334">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-336">float</span><span class="sxs-lookup"><span data-stu-id="df219-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-337">透過聲音回聲效果取消器呈現為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="df219-338">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="df219-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-340">float</span><span class="sxs-lookup"><span data-stu-id="df219-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-341">套用轉寄錯誤修正後的封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="df219-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="df219-342">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df219-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-344">float</span><span class="sxs-lookup"><span data-stu-id="df219-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-345">編碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="df219-346">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df219-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="df219-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="df219-348">float</span><span class="sxs-lookup"><span data-stu-id="df219-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="df219-349">以身歷聲的回聲效果取消器取得之來電所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="df219-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="df219-350">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="df219-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

