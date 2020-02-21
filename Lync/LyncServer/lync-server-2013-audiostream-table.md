---
title: 'Lync Server 2013: AudioStream 表格'
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
ms.openlocfilehash: e2da0884915f44246e316f80cb9fd35fb7aecaad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195766"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="eff54-102">Lync Server 2013 中的 AudioStream 表格</span><span class="sxs-lookup"><span data-stu-id="eff54-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eff54-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="eff54-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="eff54-104">每筆記錄代表一個音訊資料流。</span><span class="sxs-lookup"><span data-stu-id="eff54-104">Each record represents one audio stream.</span></span> <span data-ttu-id="eff54-105">音訊媒體上的一行通常包含兩個音訊資料流。</span><span class="sxs-lookup"><span data-stu-id="eff54-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eff54-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="eff54-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="eff54-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="eff54-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eff54-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-111">datetime</span><span class="sxs-lookup"><span data-stu-id="eff54-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="eff54-112">主要</span><span class="sxs-lookup"><span data-stu-id="eff54-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff54-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="eff54-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-115">int</span><span class="sxs-lookup"><span data-stu-id="eff54-115">int</span></span></p></td>
<td><p><span data-ttu-id="eff54-116">主要</span><span class="sxs-lookup"><span data-stu-id="eff54-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff54-117">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="eff54-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="eff54-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="eff54-120">主要</span><span class="sxs-lookup"><span data-stu-id="eff54-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff54-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="eff54-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-123">int</span><span class="sxs-lookup"><span data-stu-id="eff54-123">int</span></span></p></td>
<td><p><span data-ttu-id="eff54-124">主要</span><span class="sxs-lookup"><span data-stu-id="eff54-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="eff54-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="eff54-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-127">int</span><span class="sxs-lookup"><span data-stu-id="eff54-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-128">即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="eff54-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-130">int</span><span class="sxs-lookup"><span data-stu-id="eff54-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-131">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="eff54-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-133">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="eff54-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-134">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="eff54-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-136">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="eff54-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-137">觀察到的通話期間的最大封包遺失。</span><span class="sxs-lookup"><span data-stu-id="eff54-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-138"><strong>密度連續</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-139">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="eff54-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-140">量激增時的通話期間的封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="eff54-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-142">int</span><span class="sxs-lookup"><span data-stu-id="eff54-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-143">封包遺失量激增時的通話期間的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-145">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="eff54-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-146">封包遺失量激增之間的間歇期封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="eff54-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-148">int</span><span class="sxs-lookup"><span data-stu-id="eff54-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-149">封包遺失量激增之間的間歇期平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-151">臨界值</span><span class="sxs-lookup"><span data-stu-id="eff54-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-152">音訊資料流的封包計數。</span><span class="sxs-lookup"><span data-stu-id="eff54-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-154">臨界值</span><span class="sxs-lookup"><span data-stu-id="eff54-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-155">音訊資料流的頻寬預估值。</span><span class="sxs-lookup"><span data-stu-id="eff54-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-157">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-158">整個通話的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="eff54-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="eff54-159">範圍是介於 0.0 到 5.0。</span><span class="sxs-lookup"><span data-stu-id="eff54-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="eff54-160">此評量顯示網路 MOS 降低由於抖動和封包遺失量。</span><span class="sxs-lookup"><span data-stu-id="eff54-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="eff54-161">可接受的品質它應該小於 0.5。</span><span class="sxs-lookup"><span data-stu-id="eff54-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-163">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-164">通話期間的最大網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="eff54-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-166">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-167">抖動所導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="eff54-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-169">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-170">封包遺失所導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="eff54-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-172">int</span><span class="sxs-lookup"><span data-stu-id="eff54-172">int</span></span></p></td>
<td><p><span data-ttu-id="eff54-173">Foreign</span><span class="sxs-lookup"><span data-stu-id="eff54-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="eff54-174">音訊轉碼器通話，參考來源： PayloadDescription Table。</span><span class="sxs-lookup"><span data-stu-id="eff54-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-176">int</span><span class="sxs-lookup"><span data-stu-id="eff54-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-177">音訊資料流的取樣率。</span><span class="sxs-lookup"><span data-stu-id="eff54-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-178"><strong>來回</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-179">int</span><span class="sxs-lookup"><span data-stu-id="eff54-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-180">RTCP 統計資料中的來回時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="eff54-181">可接受的品質這應該是小於 100 毫秒。</span><span class="sxs-lookup"><span data-stu-id="eff54-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-183">int</span><span class="sxs-lookup"><span data-stu-id="eff54-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-184">音訊資料流的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-186">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-187">平均寬頻網路 MOS 通話。</span><span class="sxs-lookup"><span data-stu-id="eff54-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="eff54-188">此評量取決於封包遺失、 抖動，以及使用轉碼器。</span><span class="sxs-lookup"><span data-stu-id="eff54-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="eff54-189">範圍是 [1.0 到 5.0]。</span><span class="sxs-lookup"><span data-stu-id="eff54-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-191">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-192">最小寬頻網路 MOS 通話。</span><span class="sxs-lookup"><span data-stu-id="eff54-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-194">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-195">平均預測的寬頻傾聽 MOS 分數所傳送之音訊，包括語音層級、 雜訊層級和擷取裝置特性。</span><span class="sxs-lookup"><span data-stu-id="eff54-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-197">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-198">最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="eff54-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-200">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-201">從包括語音層級、 雜訊層級、 轉碼器、 網路狀況和擷取裝置特性網路接收之音訊的平均預測的寬頻傾聽 MOS 分數。</span><span class="sxs-lookup"><span data-stu-id="eff54-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-203">decimal(3,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-204">最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="eff54-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-206">位元</span><span class="sxs-lookup"><span data-stu-id="eff54-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-207">指出是否將音訊 FEC 用於通話的旗標。</span><span class="sxs-lookup"><span data-stu-id="eff54-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-209">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-210">一般樣本的音訊修復所產生之隱藏樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-212">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-213">一般樣本的音訊修復所產生的延伸樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-215">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="eff54-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-216">一般樣本的音訊修復所產生之壓縮樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-217"><strong>輸入</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-218">位元</span><span class="sxs-lookup"><span data-stu-id="eff54-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-219">所收到的接收端的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="eff54-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-220"><strong>輸出</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-221">位元</span><span class="sxs-lookup"><span data-stu-id="eff54-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-222">所收到的一邊寄件者的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="eff54-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-224">位元</span><span class="sxs-lookup"><span data-stu-id="eff54-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="eff54-225">1 表示資料流是從發話者流向受話者。</span><span class="sxs-lookup"><span data-stu-id="eff54-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="eff54-226">0 表示資料流是從受話者流向發話者。</span><span class="sxs-lookup"><span data-stu-id="eff54-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-228">float</span><span class="sxs-lookup"><span data-stu-id="eff54-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-229">抖動到達時間的標準差。</span><span class="sxs-lookup"><span data-stu-id="eff54-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="eff54-230">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-232">float</span><span class="sxs-lookup"><span data-stu-id="eff54-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-233">修復隱藏封包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="eff54-234">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-236">float</span><span class="sxs-lookup"><span data-stu-id="eff54-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-237">修復隱藏封包率的標準差。</span><span class="sxs-lookup"><span data-stu-id="eff54-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="eff54-238">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-240">float</span><span class="sxs-lookup"><span data-stu-id="eff54-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-241">修復捨棄封收到封包總數相比的封包的比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="eff54-242">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-244">float</span><span class="sxs-lookup"><span data-stu-id="eff54-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-245">收到封包總數相比的正向錯誤修正封包的比率。</span><span class="sxs-lookup"><span data-stu-id="eff54-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="eff54-246">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-248">float</span><span class="sxs-lookup"><span data-stu-id="eff54-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-249">音訊修復所壓縮的封包的數目上限。</span><span class="sxs-lookup"><span data-stu-id="eff54-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="eff54-250">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-252">float</span><span class="sxs-lookup"><span data-stu-id="eff54-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-253">指出通話處於遺漏壅塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="eff54-254">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-256">float</span><span class="sxs-lookup"><span data-stu-id="eff54-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-257">會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="eff54-258">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-260">float</span><span class="sxs-lookup"><span data-stu-id="eff54-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-261">會指出當通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="eff54-262">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-264">int</span><span class="sxs-lookup"><span data-stu-id="eff54-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-265">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="eff54-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff54-266">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-268">int</span><span class="sxs-lookup"><span data-stu-id="eff54-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-269">通話期間測量的頻寬預估最大數量。</span><span class="sxs-lookup"><span data-stu-id="eff54-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff54-270">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-272">int</span><span class="sxs-lookup"><span data-stu-id="eff54-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-273">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="eff54-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff54-274">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-276">int</span><span class="sxs-lookup"><span data-stu-id="eff54-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-277">通話期間測量的頻寬預估平均量。</span><span class="sxs-lookup"><span data-stu-id="eff54-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="eff54-278">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-280">float</span><span class="sxs-lookup"><span data-stu-id="eff54-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-281">總數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eff54-281">Total amount of one-way latency.</span></span> <span data-ttu-id="eff54-282">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-283">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-285">float</span><span class="sxs-lookup"><span data-stu-id="eff54-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-286">平均量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eff54-286">Average amount of one-way latency.</span></span> <span data-ttu-id="eff54-287">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-288">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-290">float</span><span class="sxs-lookup"><span data-stu-id="eff54-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-291">最大數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="eff54-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="eff54-292">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-293">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-295">int</span><span class="sxs-lookup"><span data-stu-id="eff54-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-296">總單向的高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="eff54-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="eff54-297">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="eff54-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff54-298">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-299">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-301">float</span><span class="sxs-lookup"><span data-stu-id="eff54-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-302">總單向的高載密度。</span><span class="sxs-lookup"><span data-stu-id="eff54-302">Total one-way burst density.</span></span> <span data-ttu-id="eff54-303">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="eff54-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff54-304">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-305">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-307">float</span><span class="sxs-lookup"><span data-stu-id="eff54-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-308">總單向的高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-308">Total one-way burst duration.</span></span> <span data-ttu-id="eff54-309">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="eff54-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="eff54-310">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-311">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-313">int</span><span class="sxs-lookup"><span data-stu-id="eff54-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-314">總單向的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="eff54-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="eff54-315">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="eff54-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff54-316">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-317">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-319">float</span><span class="sxs-lookup"><span data-stu-id="eff54-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-320">總單向的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="eff54-320">Total one-way gap density.</span></span> <span data-ttu-id="eff54-321">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="eff54-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff54-322">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-323">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-325">float</span><span class="sxs-lookup"><span data-stu-id="eff54-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-326">總單向缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="eff54-326">Total one-way gap duration.</span></span> <span data-ttu-id="eff54-327">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="eff54-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="eff54-328">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="eff54-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="eff54-329">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-331">float</span><span class="sxs-lookup"><span data-stu-id="eff54-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-332">解碼為立體聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="eff54-333">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-335">float</span><span class="sxs-lookup"><span data-stu-id="eff54-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-336">由柔和式迴音效果取消器轉換為立體聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="eff54-337">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-339">float</span><span class="sxs-lookup"><span data-stu-id="eff54-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-340">封包遺失率之後已套用正向錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="eff54-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="eff54-341">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eff54-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-343">float</span><span class="sxs-lookup"><span data-stu-id="eff54-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-344">編碼為立體聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="eff54-345">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eff54-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="eff54-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="eff54-347">float</span><span class="sxs-lookup"><span data-stu-id="eff54-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="eff54-348">由柔和式迴音效果取消器擷取為立體聲的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="eff54-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="eff54-349">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="eff54-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

