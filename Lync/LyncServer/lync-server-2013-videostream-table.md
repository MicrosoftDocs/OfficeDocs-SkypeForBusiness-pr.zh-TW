---
title: 'Lync Server 2013: VideoStream 表格'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="69259-102">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="69259-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69259-103">_**上次修改主題：** 2013 年 12 月 13 日_</span><span class="sxs-lookup"><span data-stu-id="69259-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="69259-104">每筆記錄代表一個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="69259-104">Each record represents one video stream.</span></span> <span data-ttu-id="69259-105">視訊媒體上的一行通常包含兩個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="69259-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69259-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="69259-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="69259-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="69259-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="69259-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="69259-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="69259-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="69259-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69259-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="69259-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-111">datetime</span><span class="sxs-lookup"><span data-stu-id="69259-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="69259-112">主要</span><span class="sxs-lookup"><span data-stu-id="69259-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="69259-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="69259-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="69259-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-115">int</span><span class="sxs-lookup"><span data-stu-id="69259-115">int</span></span></p></td>
<td><p><span data-ttu-id="69259-116">主要</span><span class="sxs-lookup"><span data-stu-id="69259-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="69259-117">R 參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="69259-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="69259-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="69259-120">主要</span><span class="sxs-lookup"><span data-stu-id="69259-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="69259-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="69259-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="69259-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-123">int</span><span class="sxs-lookup"><span data-stu-id="69259-123">int</span></span></p></td>
<td><p><span data-ttu-id="69259-124">主要</span><span class="sxs-lookup"><span data-stu-id="69259-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="69259-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="69259-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="69259-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-127">smallint</span><span class="sxs-lookup"><span data-stu-id="69259-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="69259-128">外部、 主要</span><span class="sxs-lookup"><span data-stu-id="69259-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="69259-129">裝載的描述。</span><span class="sxs-lookup"><span data-stu-id="69259-129">Payload description.</span></span> <span data-ttu-id="69259-130">請參閱如需詳細資訊，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 中的為 PayloadDescription table</a> 。</span><span class="sxs-lookup"><span data-stu-id="69259-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="69259-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-132">int</span><span class="sxs-lookup"><span data-stu-id="69259-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-133">即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="69259-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-135">int</span><span class="sxs-lookup"><span data-stu-id="69259-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-136">視訊工作階段期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="69259-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-137"><strong>來回</strong></span><span class="sxs-lookup"><span data-stu-id="69259-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-138">int</span><span class="sxs-lookup"><span data-stu-id="69259-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-139">RTCP 統計資料中的來回時間。</span><span class="sxs-lookup"><span data-stu-id="69259-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-141">int</span><span class="sxs-lookup"><span data-stu-id="69259-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-142">視訊資料流的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="69259-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="69259-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-144">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="69259-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-145">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="69259-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-147">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="69259-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-148">觀察到的通話期間的最大封包遺失。</span><span class="sxs-lookup"><span data-stu-id="69259-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="69259-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-150">int</span><span class="sxs-lookup"><span data-stu-id="69259-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-151">視訊資料流 （即時傳輸通訊協定 （RTP）） 的封包計數。</span><span class="sxs-lookup"><span data-stu-id="69259-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="69259-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-153">int</span><span class="sxs-lookup"><span data-stu-id="69259-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-154">視訊資料流的頻寬預估值。</span><span class="sxs-lookup"><span data-stu-id="69259-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="69259-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-156">char(9)</span><span class="sxs-lookup"><span data-stu-id="69259-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-157">以像素為單位寬度乘以像素為單位的高度的視訊解析度。</span><span class="sxs-lookup"><span data-stu-id="69259-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="69259-158">報告做為字串。</span><span class="sxs-lookup"><span data-stu-id="69259-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="69259-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-160">int</span><span class="sxs-lookup"><span data-stu-id="69259-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-161">視訊資料流的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="69259-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-163">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="69259-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-164">已接收視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="69259-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="69259-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-166">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="69259-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-167">傳送視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="69259-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-169">int</span><span class="sxs-lookup"><span data-stu-id="69259-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-170">視訊工作階段期間的最大視訊位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="69259-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-172">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="69259-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-173">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="69259-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-175">位元</span><span class="sxs-lookup"><span data-stu-id="69259-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-176">無法使用。</span><span class="sxs-lookup"><span data-stu-id="69259-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="69259-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-178">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="69259-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-179">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-182">常見 Interchange Format (CIF) 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-185">VGA 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-188">HD720 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-191">未捨棄框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-194">捨棄 B 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-197">捨棄 BP 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-200">Bpsp 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="69259-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="69259-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-203">Bpspi 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-204"><strong>輸入</strong></span><span class="sxs-lookup"><span data-stu-id="69259-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-205">位元</span><span class="sxs-lookup"><span data-stu-id="69259-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-206">所收到的接收端的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="69259-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-207"><strong>輸出</strong></span><span class="sxs-lookup"><span data-stu-id="69259-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-208">位元</span><span class="sxs-lookup"><span data-stu-id="69259-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-209">所收到的一邊寄件者的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="69259-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="69259-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-211">位元</span><span class="sxs-lookup"><span data-stu-id="69259-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="69259-212">1 表示資料流是從發話者流向受話者。</span><span class="sxs-lookup"><span data-stu-id="69259-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="69259-213">0 表示資料流是從受話者流向發話者。</span><span class="sxs-lookup"><span data-stu-id="69259-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-215">float</span><span class="sxs-lookup"><span data-stu-id="69259-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-216">指出通話處於遺漏壅塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="69259-217">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-219">float</span><span class="sxs-lookup"><span data-stu-id="69259-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-220">會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="69259-221">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-223">float</span><span class="sxs-lookup"><span data-stu-id="69259-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-224">會指出當通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="69259-225">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="69259-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-227">int</span><span class="sxs-lookup"><span data-stu-id="69259-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-228">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="69259-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="69259-229">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-231">int</span><span class="sxs-lookup"><span data-stu-id="69259-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-232">通話期間測量的頻寬預估最大數量。</span><span class="sxs-lookup"><span data-stu-id="69259-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="69259-233">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="69259-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-235">int</span><span class="sxs-lookup"><span data-stu-id="69259-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-236">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="69259-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="69259-237">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="69259-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-239">int</span><span class="sxs-lookup"><span data-stu-id="69259-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-240">通話期間測量的頻寬預估平均量。</span><span class="sxs-lookup"><span data-stu-id="69259-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="69259-241">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="69259-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-243">float</span><span class="sxs-lookup"><span data-stu-id="69259-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-244">結束點決定的網路連線無法支援 multiview 視訊通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="69259-245">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="69259-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-247">float</span><span class="sxs-lookup"><span data-stu-id="69259-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-248">總數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-248">Total amount of one-way latency.</span></span> <span data-ttu-id="69259-249">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="69259-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-250">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="69259-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-252">float</span><span class="sxs-lookup"><span data-stu-id="69259-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-253">平均量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-253">Average amount of one-way latency.</span></span> <span data-ttu-id="69259-254">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="69259-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-255">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-257">float</span><span class="sxs-lookup"><span data-stu-id="69259-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-258">最大數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="69259-259">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="69259-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-260">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="69259-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-262">int</span><span class="sxs-lookup"><span data-stu-id="69259-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-263">總單向的高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="69259-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="69259-264">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="69259-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="69259-265">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-266">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="69259-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-268">int</span><span class="sxs-lookup"><span data-stu-id="69259-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-269">總單向的高載密度。</span><span class="sxs-lookup"><span data-stu-id="69259-269">Total one-way burst density.</span></span> <span data-ttu-id="69259-270">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="69259-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="69259-271">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-272">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="69259-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-274">float</span><span class="sxs-lookup"><span data-stu-id="69259-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-275">總單向的高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="69259-275">Total one-way burst duration.</span></span> <span data-ttu-id="69259-276">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="69259-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="69259-277">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-278">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="69259-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-280">int</span><span class="sxs-lookup"><span data-stu-id="69259-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-281">總單向的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="69259-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="69259-282">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="69259-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="69259-283">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-284">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="69259-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-286">float</span><span class="sxs-lookup"><span data-stu-id="69259-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-287">總單向的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="69259-287">Total one-way gap density.</span></span> <span data-ttu-id="69259-288">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="69259-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="69259-289">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-290">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="69259-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-292">float</span><span class="sxs-lookup"><span data-stu-id="69259-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-293">總單向缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="69259-293">Total one-way gap duration.</span></span> <span data-ttu-id="69259-294">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="69259-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="69259-295">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="69259-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="69259-296">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="69259-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-298">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="69259-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-299">視訊封包丟失的速率。</span><span class="sxs-lookup"><span data-stu-id="69259-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="69259-300">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="69259-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-302">int</span><span class="sxs-lookup"><span data-stu-id="69259-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-303">分配給視訊的頻寬平均量。</span><span class="sxs-lookup"><span data-stu-id="69259-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="69259-304">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="69259-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-306">smallint</span><span class="sxs-lookup"><span data-stu-id="69259-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="69259-307">Foreign</span><span class="sxs-lookup"><span data-stu-id="69259-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69259-308">使用寄件者的視訊轉碼器類型。</span><span class="sxs-lookup"><span data-stu-id="69259-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="69259-309">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="69259-310">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="69259-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-312">int</span><span class="sxs-lookup"><span data-stu-id="69259-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-313">寄件者所使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="69259-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="69259-314">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="69259-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-316">int</span><span class="sxs-lookup"><span data-stu-id="69259-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-317">寄件者所使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="69259-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="69259-318">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="69259-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-320">float</span><span class="sxs-lookup"><span data-stu-id="69259-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-321">寄件者所使用的平均視訊播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="69259-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="69259-322">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="69259-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-324">int</span><span class="sxs-lookup"><span data-stu-id="69259-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-325">寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="69259-326">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="69259-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-328">int</span><span class="sxs-lookup"><span data-stu-id="69259-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-329">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-331">int</span><span class="sxs-lookup"><span data-stu-id="69259-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-332">最大數目由寄件者的視訊資料流的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="69259-333">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="69259-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-335">smallint</span><span class="sxs-lookup"><span data-stu-id="69259-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="69259-336">Foreign</span><span class="sxs-lookup"><span data-stu-id="69259-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="69259-337">接收者使用的視訊的代碼。</span><span class="sxs-lookup"><span data-stu-id="69259-337">Video codes used by the receiver.</span></span> <span data-ttu-id="69259-338">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="69259-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="69259-339">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="69259-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-341">int</span><span class="sxs-lookup"><span data-stu-id="69259-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-342">接收者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="69259-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="69259-343">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="69259-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-345">int</span><span class="sxs-lookup"><span data-stu-id="69259-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-346">接收者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="69259-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="69259-347">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="69259-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-349">float</span><span class="sxs-lookup"><span data-stu-id="69259-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-350">接收者使用的平均視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="69259-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="69259-351">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="69259-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-353">int</span><span class="sxs-lookup"><span data-stu-id="69259-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-354">接收者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="69259-355">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="69259-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-357">int</span><span class="sxs-lookup"><span data-stu-id="69259-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-358">接收者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="69259-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="69259-359">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="69259-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-361">int</span><span class="sxs-lookup"><span data-stu-id="69259-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-362">接收者的最大視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="69259-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="69259-363">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="69259-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-365">int</span><span class="sxs-lookup"><span data-stu-id="69259-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-366">接收者的最小視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="69259-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="69259-367">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="69259-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-369">int</span><span class="sxs-lookup"><span data-stu-id="69259-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-370">（例如圖庫或單一資料流） 接收者的視訊模式。</span><span class="sxs-lookup"><span data-stu-id="69259-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="69259-371">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="69259-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-373">float</span><span class="sxs-lookup"><span data-stu-id="69259-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-374">封包遺失率之後已套用正向錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="69259-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="69259-375">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-377">float</span><span class="sxs-lookup"><span data-stu-id="69259-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-378">動態功能旗幟的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="69259-379">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="69259-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-381">char(9)</span><span class="sxs-lookup"><span data-stu-id="69259-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-382">通話期間測量最小解析。</span><span class="sxs-lookup"><span data-stu-id="69259-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="69259-383">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-385">float</span><span class="sxs-lookup"><span data-stu-id="69259-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-386">低位元速率臨界值 （每秒 70 kbps） 以下的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="69259-387">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-389">float</span><span class="sxs-lookup"><span data-stu-id="69259-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-390">低播放速率臨界值以下的通話百分比 （每秒 7.5 個畫面輸入）。</span><span class="sxs-lookup"><span data-stu-id="69259-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="69259-391">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="69259-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-393">float</span><span class="sxs-lookup"><span data-stu-id="69259-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-394">以最低解析度進行的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="69259-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="69259-395">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="69259-396">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69259-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="69259-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-398">float</span><span class="sxs-lookup"><span data-stu-id="69259-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-399">以秒為單位之通話的長度。</span><span class="sxs-lookup"><span data-stu-id="69259-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="69259-400">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69259-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="69259-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="69259-402">位元</span><span class="sxs-lookup"><span data-stu-id="69259-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="69259-403">會指出資料是否已彙總從多個通話。</span><span class="sxs-lookup"><span data-stu-id="69259-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="69259-404">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="69259-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

