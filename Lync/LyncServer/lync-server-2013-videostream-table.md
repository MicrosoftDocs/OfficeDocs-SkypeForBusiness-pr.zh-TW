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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="3a6e7-102">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="3a6e7-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a6e7-103">_**上次修改主題：** 2013 年 12 月 13 日_</span><span class="sxs-lookup"><span data-stu-id="3a6e7-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="3a6e7-104">每筆記錄代表一個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-104">Each record represents one video stream.</span></span> <span data-ttu-id="3a6e7-105">視訊媒體上的一行通常包含兩個視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a6e7-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="3a6e7-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="3a6e7-108"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="3a6e7-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="3a6e7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-112">主要</span><span class="sxs-lookup"><span data-stu-id="3a6e7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-113">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-115">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-115">int</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-116">主要</span><span class="sxs-lookup"><span data-stu-id="3a6e7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-117">R 參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-120">主要</span><span class="sxs-lookup"><span data-stu-id="3a6e7-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-121">參考來源： <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a>。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-123">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-123">int</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-124">主要</span><span class="sxs-lookup"><span data-stu-id="3a6e7-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-127">smallint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-128">外部、 主要</span><span class="sxs-lookup"><span data-stu-id="3a6e7-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-129">裝載的描述。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-129">Payload description.</span></span> <span data-ttu-id="3a6e7-130">請參閱如需詳細資訊，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 中的為 PayloadDescription table</a> 。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-132">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-133">即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-135">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-136">視訊工作階段期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-137"><strong>來回</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-138">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-139">RTCP 統計資料中的來回時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-141">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-142">視訊資料流的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-144">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-145">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-147">decimal(5,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-148">觀察到的通話期間的最大封包遺失。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-150">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-151">視訊資料流 （即時傳輸通訊協定 （RTP）） 的封包計數。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-153">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-154">視訊資料流的頻寬預估值。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-156">char(9)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-157">以像素為單位寬度乘以像素為單位的高度的視訊解析度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="3a6e7-158">報告做為字串。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-160">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-161">視訊資料流的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-163">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-164">已接收視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-166">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-167">傳送視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-169">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-170">視訊工作階段期間的最大視訊位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-172">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-173">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-175">位元</span><span class="sxs-lookup"><span data-stu-id="3a6e7-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-176">無法使用。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-178">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-179">便會遺失之視訊框總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-182">常見 Interchange Format (CIF) 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-185">VGA 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-188">HD720 解析度之通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-191">未捨棄框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-194">捨棄 B 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-197">捨棄 BP 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-200">Bpsp 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-203">Bpspi 框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-204"><strong>輸入</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-205">位元</span><span class="sxs-lookup"><span data-stu-id="3a6e7-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-206">所收到的接收端的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-207"><strong>輸出</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-208">位元</span><span class="sxs-lookup"><span data-stu-id="3a6e7-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-209">所收到的一邊寄件者的資料流資料。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-211">位元</span><span class="sxs-lookup"><span data-stu-id="3a6e7-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="3a6e7-212">1 表示資料流是從發話者流向受話者。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="3a6e7-213">0 表示資料流是從受話者流向發話者。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-215">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-216">指出通話處於遺漏壅塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="3a6e7-217">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-219">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-220">會指出在這期間抵達造成壅塞的網路封包延遲抵達的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="3a6e7-221">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-223">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-224">會指出當通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="3a6e7-225">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-227">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-228">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="3a6e7-229">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-231">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-232">通話期間測量的頻寬預估最大數量。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="3a6e7-233">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-235">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-236">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="3a6e7-237">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-239">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-240">通話期間測量的頻寬預估平均量。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="3a6e7-241">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-243">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-244">結束點決定的網路連線無法支援 multiview 視訊通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="3a6e7-245">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-247">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-248">總數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-248">Total amount of one-way latency.</span></span> <span data-ttu-id="3a6e7-249">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-250">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-252">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-253">平均量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-253">Average amount of one-way latency.</span></span> <span data-ttu-id="3a6e7-254">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-255">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-257">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-258">最大數量單向延遲的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="3a6e7-259">相對單向延遲測量用戶端與伺服器之間的延遲時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-260">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-262">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-263">總單向的高載發生次數。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="3a6e7-264">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="3a6e7-265">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-266">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-268">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-269">總單向的高載密度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-269">Total one-way burst density.</span></span> <span data-ttu-id="3a6e7-270">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="3a6e7-271">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-272">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-274">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-275">總單向的高載持續時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-275">Total one-way burst duration.</span></span> <span data-ttu-id="3a6e7-276">「 爆發的 「 傳輸是傳輸資料流向中而不穩定的資料流是不可預期的連續的位置。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="3a6e7-277">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-278">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-280">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-281">總單向的缺口發生次數。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="3a6e7-282">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="3a6e7-283">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-284">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-286">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-287">總單向的缺口密度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-287">Total one-way gap density.</span></span> <span data-ttu-id="3a6e7-288">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="3a6e7-289">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-290">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-292">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-293">總單向缺口持續時間。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-293">Total one-way gap duration.</span></span> <span data-ttu-id="3a6e7-294">「 爆發的 「 傳輸是傳輸資料流向無法預測激增而不穩定的資料流; 中的位置間斷的傷害指出這些激增之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="3a6e7-295">此評量測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="3a6e7-296">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-298">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-299">視訊封包丟失的速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="3a6e7-300">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-302">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-303">分配給視訊的頻寬平均量。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="3a6e7-304">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-306">smallint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-307">Foreign</span><span class="sxs-lookup"><span data-stu-id="3a6e7-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-308">使用寄件者的視訊轉碼器類型。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="3a6e7-309">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="3a6e7-310">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-312">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-313">寄件者所使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="3a6e7-314">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-316">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-317">寄件者所使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="3a6e7-318">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-320">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-321">寄件者所使用的平均視訊播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="3a6e7-322">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-324">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-325">寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="3a6e7-326">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-328">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-329">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-331">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-332">最大數目由寄件者的視訊資料流的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="3a6e7-333">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-335">smallint</span><span class="sxs-lookup"><span data-stu-id="3a6e7-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-336">Foreign</span><span class="sxs-lookup"><span data-stu-id="3a6e7-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3a6e7-337">接收者使用的視訊的代碼。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-337">Video codes used by the receiver.</span></span> <span data-ttu-id="3a6e7-338">請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="3a6e7-339">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-341">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-342">接收者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-343">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-345">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-346">接收者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-347">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-349">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-350">接收者使用的平均視訊播放速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-351">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-353">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-354">接收者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-355">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-357">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-358">接收者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-359">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-361">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-362">接收者的最大視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-363">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-365">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-366">接收者的最小視訊資料流。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-367">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-369">int</span><span class="sxs-lookup"><span data-stu-id="3a6e7-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-370">（例如圖庫或單一資料流） 接收者的視訊模式。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="3a6e7-371">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-373">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-374">封包遺失率之後已套用正向錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="3a6e7-375">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-377">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-378">動態功能旗幟的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="3a6e7-379">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-381">char(9)</span><span class="sxs-lookup"><span data-stu-id="3a6e7-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-382">通話期間測量最小解析。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="3a6e7-383">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-385">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-386">低位元速率臨界值 （每秒 70 kbps） 以下的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="3a6e7-387">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-389">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-390">低播放速率臨界值以下的通話百分比 （每秒 7.5 個畫面輸入）。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="3a6e7-391">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-393">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-394">以最低解析度進行的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="3a6e7-395">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="3a6e7-396">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a6e7-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-398">float</span><span class="sxs-lookup"><span data-stu-id="3a6e7-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-399">以秒為單位之通話的長度。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="3a6e7-400">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a6e7-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="3a6e7-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="3a6e7-402">位元</span><span class="sxs-lookup"><span data-stu-id="3a6e7-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a6e7-403">會指出資料是否已彙總從多個通話。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="3a6e7-404">Microsoft Lync Server 2013 中已引進此欄。</span><span class="sxs-lookup"><span data-stu-id="3a6e7-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

