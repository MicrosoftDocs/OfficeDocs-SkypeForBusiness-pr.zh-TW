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
ms.openlocfilehash: 59799e9b6feb076575d8187936a42a408d0dba2b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="5fb75-102">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="5fb75-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fb75-103">_**上次修改主題：** 2013 年 12 月 13 日_</span><span class="sxs-lookup"><span data-stu-id="5fb75-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="5fb75-104">每筆記錄代表一個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="5fb75-104">Each record represents one video stream.</span></span> <span data-ttu-id="5fb75-105">視訊媒體上的一行通常包含兩個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="5fb75-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5fb75-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5fb75-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5fb75-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5fb75-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-111">datetime</span><span class="sxs-lookup"><span data-stu-id="5fb75-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5fb75-112">主要</span><span class="sxs-lookup"><span data-stu-id="5fb75-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fb75-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="5fb75-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-115">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-115">int</span></span></p></td>
<td><p><span data-ttu-id="5fb75-116">主要</span><span class="sxs-lookup"><span data-stu-id="5fb75-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fb75-117">R 參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="5fb75-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="5fb75-120">主要</span><span class="sxs-lookup"><span data-stu-id="5fb75-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fb75-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="5fb75-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-123">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-123">int</span></span></p></td>
<td><p><span data-ttu-id="5fb75-124">主要</span><span class="sxs-lookup"><span data-stu-id="5fb75-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="5fb75-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="5fb75-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-127">smallint</span><span class="sxs-lookup"><span data-stu-id="5fb75-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="5fb75-128">外部、 主要</span><span class="sxs-lookup"><span data-stu-id="5fb75-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="5fb75-129">裝載的描述。</span><span class="sxs-lookup"><span data-stu-id="5fb75-129">Payload description.</span></span> <span data-ttu-id="5fb75-130">請參閱如需詳細資訊，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 中的為 PayloadDescription table</a> 。</span><span class="sxs-lookup"><span data-stu-id="5fb75-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-132">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-133">即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="5fb75-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-135">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-136">視訊工作階段期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="5fb75-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-137"><strong>來回</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-138">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-139">RTCP 統計資料中的來回時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-141">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-142">視訊資料流的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-144">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-145">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-147">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-148">觀察到的通話期間的最大封包遺失。</span><span class="sxs-lookup"><span data-stu-id="5fb75-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-150">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-151">視訊資料流 （即時傳輸通訊協定 （RTP）） 的封包計數。</span><span class="sxs-lookup"><span data-stu-id="5fb75-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-153">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-154">視訊資料流的頻寬預估值。</span><span class="sxs-lookup"><span data-stu-id="5fb75-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-156">char(9)</span><span class="sxs-lookup"><span data-stu-id="5fb75-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-157">以像素為單位寬度乘以像素為單位的高度的視訊解析度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="5fb75-158">報告做為字串。</span><span class="sxs-lookup"><span data-stu-id="5fb75-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-160">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-161">視訊資料流的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-163">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-164">已接收視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-166">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-167">傳送視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-169">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-170">視訊工作階段期間的最大視訊位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-172">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-173">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-175">位元</span><span class="sxs-lookup"><span data-stu-id="5fb75-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-176">無法使用。</span><span class="sxs-lookup"><span data-stu-id="5fb75-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-178">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-179">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-182">常見 Interchange Format (CIF) 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-185">VGA 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-188">HD720 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-191">未捨棄框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-194">捨棄 B 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-197">捨棄 BP 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-200">Bpsp 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="5fb75-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-203">Bpspi 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-204"><strong>輸入</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-205">位元</span><span class="sxs-lookup"><span data-stu-id="5fb75-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-206">所收到的接收端的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="5fb75-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-207"><strong>輸出</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-208">位元</span><span class="sxs-lookup"><span data-stu-id="5fb75-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-209">所收到的一邊寄件者的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="5fb75-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-211">位元</span><span class="sxs-lookup"><span data-stu-id="5fb75-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5fb75-212">1 表示資料流是從發話者流向受話者。</span><span class="sxs-lookup"><span data-stu-id="5fb75-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="5fb75-213">0 表示資料流是從受話者流向發話者。</span><span class="sxs-lookup"><span data-stu-id="5fb75-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-215">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-216">指出通話處於遺漏壅塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="5fb75-217">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-219">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-220">會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="5fb75-221">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-223">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-224">會指出當通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="5fb75-225">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-227">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-228">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="5fb75-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5fb75-229">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-231">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-232">通話期間測量的頻寬預估最大數量。</span><span class="sxs-lookup"><span data-stu-id="5fb75-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5fb75-233">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-235">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-236">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="5fb75-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5fb75-237">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-239">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-240">通話期間測量的頻寬預估平均量。</span><span class="sxs-lookup"><span data-stu-id="5fb75-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="5fb75-241">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-243">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-244">結束點決定的網路連線無法支援 multiview 視訊通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="5fb75-245">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-247">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-248">總數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-248">Total amount of one-way latency.</span></span> <span data-ttu-id="5fb75-249">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-250">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-252">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-253">平均量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-253">Average amount of one-way latency.</span></span> <span data-ttu-id="5fb75-254">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-255">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-257">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-258">最大數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="5fb75-259">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-260">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-262">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-263">總單向的高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="5fb75-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="5fb75-264">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="5fb75-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="5fb75-265">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-266">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-268">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-269">總單向的高載密度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-269">Total one-way burst density.</span></span> <span data-ttu-id="5fb75-270">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="5fb75-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="5fb75-271">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-272">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-274">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-275">總單向的高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-275">Total one-way burst duration.</span></span> <span data-ttu-id="5fb75-276">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="5fb75-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="5fb75-277">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-278">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-280">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-281">總單向的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="5fb75-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="5fb75-282">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="5fb75-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="5fb75-283">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-284">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-286">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-287">總單向的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-287">Total one-way gap density.</span></span> <span data-ttu-id="5fb75-288">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="5fb75-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="5fb75-289">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-290">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-292">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-293">總單向缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="5fb75-293">Total one-way gap duration.</span></span> <span data-ttu-id="5fb75-294">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="5fb75-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="5fb75-295">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="5fb75-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="5fb75-296">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-298">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="5fb75-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-299">視訊封包丟失的速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="5fb75-300">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-302">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-303">分配給視訊的頻寬平均量。</span><span class="sxs-lookup"><span data-stu-id="5fb75-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="5fb75-304">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-306">smallint</span><span class="sxs-lookup"><span data-stu-id="5fb75-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="5fb75-307">Foreign</span><span class="sxs-lookup"><span data-stu-id="5fb75-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5fb75-308">使用寄件者的視訊轉碼器類型。</span><span class="sxs-lookup"><span data-stu-id="5fb75-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="5fb75-309">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="5fb75-310">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-312">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-313">寄件者所使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="5fb75-314">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-316">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-317">寄件者所使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="5fb75-318">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-320">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-321">寄件者所使用的平均視訊播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="5fb75-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="5fb75-322">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-324">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-325">寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="5fb75-326">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-328">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-329">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-331">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-332">最大數目由寄件者的視訊資料流的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="5fb75-333">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-335">smallint</span><span class="sxs-lookup"><span data-stu-id="5fb75-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="5fb75-336">Foreign</span><span class="sxs-lookup"><span data-stu-id="5fb75-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5fb75-337">接收者使用的視訊的代碼。</span><span class="sxs-lookup"><span data-stu-id="5fb75-337">Video codes used by the receiver.</span></span> <span data-ttu-id="5fb75-338">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="5fb75-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="5fb75-339">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-341">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-342">接收者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-343">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-345">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-346">接收者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-347">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-349">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-350">接收者使用的平均視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-351">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-353">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-354">接收者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-355">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-357">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-358">接收者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="5fb75-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-359">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-361">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-362">接收者的最大視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="5fb75-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-363">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-365">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-366">接收者的最小視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="5fb75-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-367">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-369">int</span><span class="sxs-lookup"><span data-stu-id="5fb75-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-370">（例如圖庫或單一資料流） 接收者的視訊模式。</span><span class="sxs-lookup"><span data-stu-id="5fb75-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="5fb75-371">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-373">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-374">封包遺失率之後已套用正向錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="5fb75-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="5fb75-375">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-377">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-378">動態功能旗幟的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="5fb75-379">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-381">char(9)</span><span class="sxs-lookup"><span data-stu-id="5fb75-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-382">通話期間測量最小解析。</span><span class="sxs-lookup"><span data-stu-id="5fb75-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="5fb75-383">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-385">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-386">低位元速率臨界值 （每秒 70 kbps） 以下的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="5fb75-387">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-389">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-390">低播放速率臨界值以下的通話百分比 （每秒 7.5 個畫面輸入）。</span><span class="sxs-lookup"><span data-stu-id="5fb75-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="5fb75-391">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-393">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-394">以最低解析度進行的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="5fb75-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="5fb75-395">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="5fb75-396">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5fb75-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-398">float</span><span class="sxs-lookup"><span data-stu-id="5fb75-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-399">以秒為單位之通話的長度。</span><span class="sxs-lookup"><span data-stu-id="5fb75-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="5fb75-400">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5fb75-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="5fb75-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="5fb75-402">位元</span><span class="sxs-lookup"><span data-stu-id="5fb75-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5fb75-403">會指出資料是否已彙總從多個通話。</span><span class="sxs-lookup"><span data-stu-id="5fb75-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="5fb75-404">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="5fb75-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

