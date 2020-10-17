---
title: Lync Server 2013： AudioStream 表格
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
ms.openlocfilehash: 331b2afbfa4b6c4147ffab3765af4e9e5031c190
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502870"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="f021a-102">Lync Server 2013 中的 AudioStream 表格</span><span class="sxs-lookup"><span data-stu-id="f021a-102">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f021a-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f021a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f021a-104">每筆記錄代表一個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-104">Each record represents one audio stream.</span></span> <span data-ttu-id="f021a-105">一個音訊媒體行通常包含兩個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f021a-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f021a-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f021a-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f021a-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f021a-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f021a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f021a-112">主要</span><span class="sxs-lookup"><span data-stu-id="f021a-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f021a-113">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f021a-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-115">int</span><span class="sxs-lookup"><span data-stu-id="f021a-115">int</span></span></p></td>
<td><p><span data-ttu-id="f021a-116">主要</span><span class="sxs-lookup"><span data-stu-id="f021a-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f021a-117">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f021a-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="f021a-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f021a-120">主要</span><span class="sxs-lookup"><span data-stu-id="f021a-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f021a-121">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f021a-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-123">int</span><span class="sxs-lookup"><span data-stu-id="f021a-123">int</span></span></p></td>
<td><p><span data-ttu-id="f021a-124">主要</span><span class="sxs-lookup"><span data-stu-id="f021a-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f021a-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="f021a-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-127">int</span><span class="sxs-lookup"><span data-stu-id="f021a-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-128">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="f021a-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-130">int</span><span class="sxs-lookup"><span data-stu-id="f021a-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-131">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="f021a-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-133">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="f021a-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-134">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="f021a-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-136">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="f021a-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-137">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="f021a-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-139">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="f021a-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-140">通話期間的猝量遺失期間的封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="f021a-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-142">int</span><span class="sxs-lookup"><span data-stu-id="f021a-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-143">通話期間的猝量遺失期間的封包遺失平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-145">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="f021a-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-146">封包遺失失敗之間的平均封包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="f021a-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-148">int</span><span class="sxs-lookup"><span data-stu-id="f021a-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-149">封包遺失的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-151">臨界值</span><span class="sxs-lookup"><span data-stu-id="f021a-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-152">音訊資料流程的封包計數。</span><span class="sxs-lookup"><span data-stu-id="f021a-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-154">臨界值</span><span class="sxs-lookup"><span data-stu-id="f021a-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-155">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="f021a-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-157">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-158">整個通話的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="f021a-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="f021a-159">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="f021a-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="f021a-160">此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。</span><span class="sxs-lookup"><span data-stu-id="f021a-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="f021a-161">可接受的品質應小於0.5。</span><span class="sxs-lookup"><span data-stu-id="f021a-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-163">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-164">通話期間的最大網路 MOS 降級。</span><span class="sxs-lookup"><span data-stu-id="f021a-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-166">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-167">抖動導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="f021a-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-169">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-170">封包遺失導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="f021a-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-172">int</span><span class="sxs-lookup"><span data-stu-id="f021a-172">int</span></span></p></td>
<td><p><span data-ttu-id="f021a-173">Foreign</span><span class="sxs-lookup"><span data-stu-id="f021a-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f021a-174">用於通話的音訊編解碼器，參考來源為 PayloadDescription Table。</span><span class="sxs-lookup"><span data-stu-id="f021a-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-176">int</span><span class="sxs-lookup"><span data-stu-id="f021a-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-177">音訊資料流程的取樣速率。</span><span class="sxs-lookup"><span data-stu-id="f021a-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-178"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-179">int</span><span class="sxs-lookup"><span data-stu-id="f021a-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-180">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="f021a-181">若為可接受的品質，則應小於100ms。</span><span class="sxs-lookup"><span data-stu-id="f021a-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-183">int</span><span class="sxs-lookup"><span data-stu-id="f021a-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-184">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-186">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-187">通話的平均寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="f021a-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="f021a-188">此度量取決於所用的封包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="f021a-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="f021a-189">範圍為 [1.0 至 5.0]。</span><span class="sxs-lookup"><span data-stu-id="f021a-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-191">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-192">通話的最小寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="f021a-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-194">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-195">已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="f021a-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-197">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-198">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f021a-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-200">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-201">從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="f021a-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-203">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-204">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f021a-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-206">位</span><span class="sxs-lookup"><span data-stu-id="f021a-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-207">指示是否要將音訊 FEC 用於通話的旗標。</span><span class="sxs-lookup"><span data-stu-id="f021a-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-209">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-210">音訊修復所產生之隱藏樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f021a-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-212">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-213">音訊修復所產生之延伸樣本的平均比率為典型範例。</span><span class="sxs-lookup"><span data-stu-id="f021a-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-215">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="f021a-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-216">音訊修復所產生之壓縮樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f021a-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-217"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-218">位</span><span class="sxs-lookup"><span data-stu-id="f021a-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-219">接收接收方的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="f021a-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-220"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-221">位</span><span class="sxs-lookup"><span data-stu-id="f021a-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-222">接收寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="f021a-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-224">位</span><span class="sxs-lookup"><span data-stu-id="f021a-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f021a-225">1表示資料流程是從來電者流向被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="f021a-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="f021a-226">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="f021a-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-228">float</span><span class="sxs-lookup"><span data-stu-id="f021a-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-229">抖動到達時間的標準差。</span><span class="sxs-lookup"><span data-stu-id="f021a-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="f021a-230">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-232">float</span><span class="sxs-lookup"><span data-stu-id="f021a-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-233">修復所隱藏的封包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="f021a-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f021a-234">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-236">float</span><span class="sxs-lookup"><span data-stu-id="f021a-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-237">修復所隱藏之封包的標準差。</span><span class="sxs-lookup"><span data-stu-id="f021a-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f021a-238">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-240">float</span><span class="sxs-lookup"><span data-stu-id="f021a-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-241">修復丟棄的封包比率與接收的封包總數。</span><span class="sxs-lookup"><span data-stu-id="f021a-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f021a-242">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-244">float</span><span class="sxs-lookup"><span data-stu-id="f021a-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-245">與接收的封包總數相比，使用轉寄錯誤修正資料包的比例。</span><span class="sxs-lookup"><span data-stu-id="f021a-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f021a-246">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-248">float</span><span class="sxs-lookup"><span data-stu-id="f021a-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-249">修復壓縮的音訊封包數目上限。</span><span class="sxs-lookup"><span data-stu-id="f021a-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="f021a-250">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-252">float</span><span class="sxs-lookup"><span data-stu-id="f021a-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-253">會指出通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f021a-254">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-256">float</span><span class="sxs-lookup"><span data-stu-id="f021a-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-257">會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</span><span class="sxs-lookup"><span data-stu-id="f021a-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f021a-258">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-260">float</span><span class="sxs-lookup"><span data-stu-id="f021a-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-261">會指出通話在競爭網路資源時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f021a-262">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-264">int</span><span class="sxs-lookup"><span data-stu-id="f021a-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-265">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="f021a-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f021a-266">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-268">int</span><span class="sxs-lookup"><span data-stu-id="f021a-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-269">通話期間測量的頻寬預估最大值。</span><span class="sxs-lookup"><span data-stu-id="f021a-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f021a-270">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-272">int</span><span class="sxs-lookup"><span data-stu-id="f021a-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-273">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="f021a-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f021a-274">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-276">int</span><span class="sxs-lookup"><span data-stu-id="f021a-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-277">通話期間測量的平均頻寬預估量。</span><span class="sxs-lookup"><span data-stu-id="f021a-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f021a-278">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-280">float</span><span class="sxs-lookup"><span data-stu-id="f021a-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-281">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="f021a-281">Total amount of one-way latency.</span></span> <span data-ttu-id="f021a-282">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-283">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-285">float</span><span class="sxs-lookup"><span data-stu-id="f021a-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-286">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="f021a-286">Average amount of one-way latency.</span></span> <span data-ttu-id="f021a-287">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-288">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-290">float</span><span class="sxs-lookup"><span data-stu-id="f021a-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-291">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="f021a-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f021a-292">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-293">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-295">int</span><span class="sxs-lookup"><span data-stu-id="f021a-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-296">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="f021a-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="f021a-297">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="f021a-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f021a-298">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-299">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-301">float</span><span class="sxs-lookup"><span data-stu-id="f021a-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-302">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="f021a-302">Total one-way burst density.</span></span> <span data-ttu-id="f021a-303">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="f021a-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f021a-304">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-305">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-307">float</span><span class="sxs-lookup"><span data-stu-id="f021a-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-308">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-308">Total one-way burst duration.</span></span> <span data-ttu-id="f021a-309">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="f021a-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f021a-310">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-311">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-313">int</span><span class="sxs-lookup"><span data-stu-id="f021a-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-314">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="f021a-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="f021a-315">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f021a-316">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-317">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-319">float</span><span class="sxs-lookup"><span data-stu-id="f021a-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-320">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="f021a-320">Total one-way gap density.</span></span> <span data-ttu-id="f021a-321">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f021a-322">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-323">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-325">float</span><span class="sxs-lookup"><span data-stu-id="f021a-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-326">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="f021a-326">Total one-way gap duration.</span></span> <span data-ttu-id="f021a-327">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="f021a-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f021a-328">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="f021a-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f021a-329">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-331">float</span><span class="sxs-lookup"><span data-stu-id="f021a-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-332">解碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="f021a-333">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-335">float</span><span class="sxs-lookup"><span data-stu-id="f021a-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-336">透過聲音回聲效果取消器呈現為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f021a-337">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-339">float</span><span class="sxs-lookup"><span data-stu-id="f021a-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-340">套用轉寄錯誤修正後的封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="f021a-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f021a-341">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f021a-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-343">float</span><span class="sxs-lookup"><span data-stu-id="f021a-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-344">編碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="f021a-345">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f021a-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f021a-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f021a-347">float</span><span class="sxs-lookup"><span data-stu-id="f021a-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f021a-348">以身歷聲的回聲效果取消器取得之來電所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="f021a-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f021a-349">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="f021a-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

