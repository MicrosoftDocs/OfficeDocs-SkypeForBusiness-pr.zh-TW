---
title: Lync Server 2013：AudioStream 表格
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="712af-102">Lync Server 2013 中的 AudioStream 表格</span><span class="sxs-lookup"><span data-stu-id="712af-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="712af-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="712af-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="712af-104">每個記錄代表一個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-104">Each record represents one audio stream.</span></span> <span data-ttu-id="712af-105">一個音訊媒體行通常包含兩個音訊資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="712af-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="712af-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="712af-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="712af-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="712af-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="712af-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="712af-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="712af-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="712af-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="712af-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-111">datetime</span><span class="sxs-lookup"><span data-stu-id="712af-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="712af-112">首選</span><span class="sxs-lookup"><span data-stu-id="712af-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="712af-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="712af-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="712af-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-115">int</span><span class="sxs-lookup"><span data-stu-id="712af-115">int</span></span></p></td>
<td><p><span data-ttu-id="712af-116">首選</span><span class="sxs-lookup"><span data-stu-id="712af-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="712af-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="712af-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="712af-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="712af-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="712af-120">首選</span><span class="sxs-lookup"><span data-stu-id="712af-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="712af-121">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="712af-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="712af-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-123">int</span><span class="sxs-lookup"><span data-stu-id="712af-123">int</span></span></p></td>
<td><p><span data-ttu-id="712af-124">首選</span><span class="sxs-lookup"><span data-stu-id="712af-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="712af-125">媒體線中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="712af-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="712af-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-127">int</span><span class="sxs-lookup"><span data-stu-id="712af-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-128">從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="712af-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-130">int</span><span class="sxs-lookup"><span data-stu-id="712af-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-131">通話期間網路抖動的最大值。</span><span class="sxs-lookup"><span data-stu-id="712af-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="712af-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-133">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="712af-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-134">通話期間的平均資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="712af-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-136">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="712af-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-137">通話期間觀察到的最大資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="712af-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="712af-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-139">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="712af-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-140">通話期間猝發損失期間的平均資料包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="712af-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="712af-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-142">int</span><span class="sxs-lookup"><span data-stu-id="712af-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-143">通話期間猝發損失期間的平均資料包遺失時間。</span><span class="sxs-lookup"><span data-stu-id="712af-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="712af-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-145">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="712af-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-146">在突發資料包遺失之間的間隔期間的平均資料包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="712af-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="712af-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-148">int</span><span class="sxs-lookup"><span data-stu-id="712af-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-149">猝發資料包遺失之間的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="712af-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="712af-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-151">Int</span><span class="sxs-lookup"><span data-stu-id="712af-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-152">音訊資料流程的 [資料包計數]。</span><span class="sxs-lookup"><span data-stu-id="712af-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="712af-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-154">Int</span><span class="sxs-lookup"><span data-stu-id="712af-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-155">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="712af-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-157">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-158">整個通話的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="712af-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="712af-159">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="712af-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="712af-160">這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。</span><span class="sxs-lookup"><span data-stu-id="712af-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="712af-161">針對可接受的品質，它應該小於0.5。</span><span class="sxs-lookup"><span data-stu-id="712af-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-163">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-164">通話期間網路 MOS 的最大下降。</span><span class="sxs-lookup"><span data-stu-id="712af-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-166">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-167">抖動造成的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="712af-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-169">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-170">因數據包遺失而造成的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="712af-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="712af-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-172">int</span><span class="sxs-lookup"><span data-stu-id="712af-172">int</span></span></p></td>
<td><p><span data-ttu-id="712af-173">外</span><span class="sxs-lookup"><span data-stu-id="712af-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="712af-174">用於通話的音訊編解碼器，從 PayloadDescription 資料表中引用。</span><span class="sxs-lookup"><span data-stu-id="712af-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="712af-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-176">int</span><span class="sxs-lookup"><span data-stu-id="712af-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-177">音訊資料流程的採樣速率。</span><span class="sxs-lookup"><span data-stu-id="712af-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-178"><strong>環路</strong></span><span class="sxs-lookup"><span data-stu-id="712af-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-179">int</span><span class="sxs-lookup"><span data-stu-id="712af-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-180">從 RTCP 統計資料中往返的時間。</span><span class="sxs-lookup"><span data-stu-id="712af-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="712af-181">針對可接受的品質，這應該小於100ms。</span><span class="sxs-lookup"><span data-stu-id="712af-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-183">int</span><span class="sxs-lookup"><span data-stu-id="712af-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-184">音訊資料流程的最大往返行程時間。</span><span class="sxs-lookup"><span data-stu-id="712af-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="712af-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-186">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-187">通話的平均 wideband 網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="712af-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="712af-188">這個指標取決於所使用的資料包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="712af-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="712af-189">範圍是 [1.0 到 5.0]。</span><span class="sxs-lookup"><span data-stu-id="712af-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="712af-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-191">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-192">通話的最小 wideband 網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="712af-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="712af-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-194">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-195">已傳送音訊的平均預計 wideband 偵聽 MOS 分數，包括語音等級、雜訊等級及捕捉裝置特徵。</span><span class="sxs-lookup"><span data-stu-id="712af-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="712af-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-197">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-198">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="712af-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="712af-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-200">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-201">從網路接收的音訊的平均預計 wideband，包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置功能。</span><span class="sxs-lookup"><span data-stu-id="712af-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="712af-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-203">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="712af-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-204">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="712af-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="712af-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-206">稍微</span><span class="sxs-lookup"><span data-stu-id="712af-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-207">指示是否已使用音訊 FEC 進行通話的標記。</span><span class="sxs-lookup"><span data-stu-id="712af-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-209">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="712af-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-210">從音訊康復產生的隱藏樣本到典型範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="712af-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-212">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="712af-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-213">從音訊康復產生的延伸樣本數與典型範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="712af-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="712af-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-215">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="712af-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-216">從音訊修復到典型範例所產生之壓縮樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="712af-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-217"><strong>進貨</strong></span><span class="sxs-lookup"><span data-stu-id="712af-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-218">稍微</span><span class="sxs-lookup"><span data-stu-id="712af-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-219">收到接收器端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="712af-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-220"><strong>發</strong></span><span class="sxs-lookup"><span data-stu-id="712af-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-221">稍微</span><span class="sxs-lookup"><span data-stu-id="712af-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-222">收到寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="712af-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="712af-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-224">稍微</span><span class="sxs-lookup"><span data-stu-id="712af-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="712af-225">1表示資料流程方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="712af-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="712af-226">0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="712af-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="712af-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-228">浮</span><span class="sxs-lookup"><span data-stu-id="712af-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-229">抖動到貨時間的標準差。</span><span class="sxs-lookup"><span data-stu-id="712af-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="712af-230">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-232">浮</span><span class="sxs-lookup"><span data-stu-id="712af-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-233">Healer 所隱藏之資料包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="712af-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="712af-234">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="712af-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-236">浮</span><span class="sxs-lookup"><span data-stu-id="712af-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-237">Healer 所隱藏之資料包之比率的標準差。</span><span class="sxs-lookup"><span data-stu-id="712af-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="712af-238">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="712af-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-240">浮</span><span class="sxs-lookup"><span data-stu-id="712af-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-241">Healer 丟棄的資料包與接收的總數據包數目之比。</span><span class="sxs-lookup"><span data-stu-id="712af-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="712af-242">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="712af-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-244">浮</span><span class="sxs-lookup"><span data-stu-id="712af-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-245">與接收到的總數據包數目相比，已使用的轉寄錯誤修正資料包的比例。</span><span class="sxs-lookup"><span data-stu-id="712af-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="712af-246">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="712af-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-248">浮</span><span class="sxs-lookup"><span data-stu-id="712af-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-249">Healer 壓縮的音訊資料包數目上限。</span><span class="sxs-lookup"><span data-stu-id="712af-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="712af-250">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-252">浮</span><span class="sxs-lookup"><span data-stu-id="712af-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-253">表示通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="712af-254">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-256">浮</span><span class="sxs-lookup"><span data-stu-id="712af-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-257">指出因網路資料包損損，導致堵塞的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="712af-258">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-260">浮</span><span class="sxs-lookup"><span data-stu-id="712af-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-261">表示通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="712af-262">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="712af-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-264">int</span><span class="sxs-lookup"><span data-stu-id="712af-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-265">呼叫期間測量的最小頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="712af-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="712af-266">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-268">int</span><span class="sxs-lookup"><span data-stu-id="712af-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-269">呼叫期間測量的最大頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="712af-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="712af-270">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="712af-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-272">int</span><span class="sxs-lookup"><span data-stu-id="712af-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-273">在通話期間測量之頻寬估計的標準差。</span><span class="sxs-lookup"><span data-stu-id="712af-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="712af-274">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="712af-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-276">int</span><span class="sxs-lookup"><span data-stu-id="712af-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-277">通話期間平均測量的頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="712af-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="712af-278">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="712af-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-280">浮</span><span class="sxs-lookup"><span data-stu-id="712af-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-281">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="712af-281">Total amount of one-way latency.</span></span> <span data-ttu-id="712af-282">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-283">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="712af-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-285">浮</span><span class="sxs-lookup"><span data-stu-id="712af-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-286">單向延隔時間的平均量。</span><span class="sxs-lookup"><span data-stu-id="712af-286">Average amount of one-way latency.</span></span> <span data-ttu-id="712af-287">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-288">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="712af-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-290">浮</span><span class="sxs-lookup"><span data-stu-id="712af-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-291">單向延隔時間的最大值。</span><span class="sxs-lookup"><span data-stu-id="712af-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="712af-292">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-293">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="712af-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-295">int</span><span class="sxs-lookup"><span data-stu-id="712af-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-296">單向突發發生次數總計。</span><span class="sxs-lookup"><span data-stu-id="712af-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="712af-297">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="712af-298">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-299">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="712af-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-301">浮</span><span class="sxs-lookup"><span data-stu-id="712af-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-302">總計單向突發密度。</span><span class="sxs-lookup"><span data-stu-id="712af-302">Total one-way burst density.</span></span> <span data-ttu-id="712af-303">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="712af-304">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-305">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="712af-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-307">浮</span><span class="sxs-lookup"><span data-stu-id="712af-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-308">總計單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="712af-308">Total one-way burst duration.</span></span> <span data-ttu-id="712af-309">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="712af-310">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-311">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="712af-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-313">int</span><span class="sxs-lookup"><span data-stu-id="712af-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-314">總的單向間距發生情況。</span><span class="sxs-lookup"><span data-stu-id="712af-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="712af-315">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="712af-316">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-317">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="712af-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-319">浮</span><span class="sxs-lookup"><span data-stu-id="712af-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-320">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="712af-320">Total one-way gap density.</span></span> <span data-ttu-id="712af-321">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="712af-322">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-323">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="712af-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-325">浮</span><span class="sxs-lookup"><span data-stu-id="712af-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-326">總共一個單向間距時間。</span><span class="sxs-lookup"><span data-stu-id="712af-326">Total one-way gap duration.</span></span> <span data-ttu-id="712af-327">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="712af-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="712af-328">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="712af-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="712af-329">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-331">浮</span><span class="sxs-lookup"><span data-stu-id="712af-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-332">解碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="712af-333">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-335">浮</span><span class="sxs-lookup"><span data-stu-id="712af-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-336">以身歷聲顯示的通話百分比，透過聲音回音 canceller。</span><span class="sxs-lookup"><span data-stu-id="712af-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="712af-337">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="712af-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-339">浮</span><span class="sxs-lookup"><span data-stu-id="712af-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-340">已套用轉寄錯誤修正之後的資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="712af-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="712af-341">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="712af-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-343">浮</span><span class="sxs-lookup"><span data-stu-id="712af-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-344">編碼為身歷聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="712af-345">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="712af-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="712af-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="712af-347">浮</span><span class="sxs-lookup"><span data-stu-id="712af-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="712af-348">以身歷聲的 canceller 所捕獲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="712af-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="712af-349">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="712af-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

