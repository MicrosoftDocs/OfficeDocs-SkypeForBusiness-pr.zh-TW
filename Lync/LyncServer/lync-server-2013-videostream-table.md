---
title: Lync Server 2013： VideoStream 表格
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
ms.openlocfilehash: ef5c417ff391bb3ec5954cf12d00f6de3d2e6d9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518560"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="0427d-102">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="0427d-102">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0427d-103">_**主題上次修改日期：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="0427d-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="0427d-104">每筆記錄代表一個視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-104">Each record represents one video stream.</span></span> <span data-ttu-id="0427d-105">一個影片媒體行通常包含兩個影片。</span><span class="sxs-lookup"><span data-stu-id="0427d-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0427d-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="0427d-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="0427d-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="0427d-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0427d-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-111">datetime</span><span class="sxs-lookup"><span data-stu-id="0427d-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="0427d-112">主要</span><span class="sxs-lookup"><span data-stu-id="0427d-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="0427d-113">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="0427d-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-115">int</span><span class="sxs-lookup"><span data-stu-id="0427d-115">int</span></span></p></td>
<td><p><span data-ttu-id="0427d-116">主要</span><span class="sxs-lookup"><span data-stu-id="0427d-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="0427d-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中從 MediaLine 表格</a>參考的 R。</span><span class="sxs-lookup"><span data-stu-id="0427d-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="0427d-120">主要</span><span class="sxs-lookup"><span data-stu-id="0427d-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="0427d-121">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="0427d-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-123">int</span><span class="sxs-lookup"><span data-stu-id="0427d-123">int</span></span></p></td>
<td><p><span data-ttu-id="0427d-124">主要</span><span class="sxs-lookup"><span data-stu-id="0427d-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="0427d-125">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="0427d-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-127">Smallint</span><span class="sxs-lookup"><span data-stu-id="0427d-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="0427d-128">外部、主要</span><span class="sxs-lookup"><span data-stu-id="0427d-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="0427d-129">負載描述。</span><span class="sxs-lookup"><span data-stu-id="0427d-129">Payload description.</span></span> <span data-ttu-id="0427d-130">如需詳細資訊，請參閱 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0427d-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-132">int</span><span class="sxs-lookup"><span data-stu-id="0427d-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-133">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="0427d-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-135">int</span><span class="sxs-lookup"><span data-stu-id="0427d-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-136">影片中的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="0427d-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-137"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-138">int</span><span class="sxs-lookup"><span data-stu-id="0427d-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-139">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="0427d-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-141">int</span><span class="sxs-lookup"><span data-stu-id="0427d-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-142">影片資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="0427d-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-144">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-145">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="0427d-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-147">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-148">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="0427d-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-150">int</span><span class="sxs-lookup"><span data-stu-id="0427d-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-151">影片的封包計數 (即時傳輸通訊協定，RTP) 。</span><span class="sxs-lookup"><span data-stu-id="0427d-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-153">int</span><span class="sxs-lookup"><span data-stu-id="0427d-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-154">視頻資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="0427d-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-156">char (9) </span><span class="sxs-lookup"><span data-stu-id="0427d-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-157">影片解析度（圖元寬度乘以圖元高度）。</span><span class="sxs-lookup"><span data-stu-id="0427d-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="0427d-158">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="0427d-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-160">int</span><span class="sxs-lookup"><span data-stu-id="0427d-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-161">視頻資料流程的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-163">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-164">收到的影片框架速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-166">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-167">傳送的影片畫面速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-169">int</span><span class="sxs-lookup"><span data-stu-id="0427d-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-170">影片會話期間的最大影片位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-172">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-173">丟失之總影片幀的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-175">位</span><span class="sxs-lookup"><span data-stu-id="0427d-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-176">無法使用。</span><span class="sxs-lookup"><span data-stu-id="0427d-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-178">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-179">丟失之總影片幀的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-181">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-182">一般交換格式之通話的百分比 (CIF) 解析度。</span><span class="sxs-lookup"><span data-stu-id="0427d-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-184">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-185">VGA 解析度之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-187">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-188">HD720 解析度之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-190">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-191">未放下框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-193">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-194">以 B 框架丟棄的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-196">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-197">具有 BP 框架丟棄之通話持續時間的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-199">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-200">具有 BPSP 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-202">Tinyint</span><span class="sxs-lookup"><span data-stu-id="0427d-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-203">具有 BPSPI 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-204"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-205">位</span><span class="sxs-lookup"><span data-stu-id="0427d-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-206">接收接收方的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="0427d-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-207"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-208">位</span><span class="sxs-lookup"><span data-stu-id="0427d-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-209">接收寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="0427d-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-211">位</span><span class="sxs-lookup"><span data-stu-id="0427d-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="0427d-212">1表示資料流程的方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="0427d-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="0427d-213">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="0427d-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-215">float</span><span class="sxs-lookup"><span data-stu-id="0427d-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-216">會指出通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="0427d-217">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-219">float</span><span class="sxs-lookup"><span data-stu-id="0427d-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-220">會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</span><span class="sxs-lookup"><span data-stu-id="0427d-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="0427d-221">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-223">float</span><span class="sxs-lookup"><span data-stu-id="0427d-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-224">會指出通話在競爭網路資源時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="0427d-225">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-227">int</span><span class="sxs-lookup"><span data-stu-id="0427d-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-228">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="0427d-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0427d-229">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-231">int</span><span class="sxs-lookup"><span data-stu-id="0427d-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-232">通話期間測量的頻寬預估最大值。</span><span class="sxs-lookup"><span data-stu-id="0427d-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0427d-233">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-235">int</span><span class="sxs-lookup"><span data-stu-id="0427d-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-236">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="0427d-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0427d-237">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-239">int</span><span class="sxs-lookup"><span data-stu-id="0427d-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-240">通話期間測量的平均頻寬預估量。</span><span class="sxs-lookup"><span data-stu-id="0427d-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="0427d-241">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-243">float</span><span class="sxs-lookup"><span data-stu-id="0427d-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-244">端點決定網路連線無法支援多種顯示的情況影片所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="0427d-245">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-247">float</span><span class="sxs-lookup"><span data-stu-id="0427d-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-248">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="0427d-248">Total amount of one-way latency.</span></span> <span data-ttu-id="0427d-249">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-250">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-252">float</span><span class="sxs-lookup"><span data-stu-id="0427d-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-253">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="0427d-253">Average amount of one-way latency.</span></span> <span data-ttu-id="0427d-254">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-255">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-257">float</span><span class="sxs-lookup"><span data-stu-id="0427d-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-258">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="0427d-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="0427d-259">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-260">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-262">int</span><span class="sxs-lookup"><span data-stu-id="0427d-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-263">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="0427d-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="0427d-264">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="0427d-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0427d-265">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-266">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-268">int</span><span class="sxs-lookup"><span data-stu-id="0427d-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-269">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="0427d-269">Total one-way burst density.</span></span> <span data-ttu-id="0427d-270">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="0427d-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0427d-271">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-272">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-274">float</span><span class="sxs-lookup"><span data-stu-id="0427d-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-275">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="0427d-275">Total one-way burst duration.</span></span> <span data-ttu-id="0427d-276">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="0427d-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="0427d-277">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-278">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-280">int</span><span class="sxs-lookup"><span data-stu-id="0427d-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-281">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="0427d-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="0427d-282">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0427d-283">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-284">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-286">float</span><span class="sxs-lookup"><span data-stu-id="0427d-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-287">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="0427d-287">Total one-way gap density.</span></span> <span data-ttu-id="0427d-288">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0427d-289">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-290">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-292">float</span><span class="sxs-lookup"><span data-stu-id="0427d-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-293">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="0427d-293">Total one-way gap duration.</span></span> <span data-ttu-id="0427d-294">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="0427d-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="0427d-295">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="0427d-296">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-298">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="0427d-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-299">視頻封包遺失的速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="0427d-300">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-302">int</span><span class="sxs-lookup"><span data-stu-id="0427d-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-303">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="0427d-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="0427d-304">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-306">Smallint</span><span class="sxs-lookup"><span data-stu-id="0427d-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="0427d-307">Foreign</span><span class="sxs-lookup"><span data-stu-id="0427d-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0427d-308">寄件者使用的影片編解碼器類型。</span><span class="sxs-lookup"><span data-stu-id="0427d-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="0427d-309">如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0427d-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0427d-310">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-312">int</span><span class="sxs-lookup"><span data-stu-id="0427d-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-313">寄件者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="0427d-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="0427d-314">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-316">int</span><span class="sxs-lookup"><span data-stu-id="0427d-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-317">寄件者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="0427d-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="0427d-318">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-320">float</span><span class="sxs-lookup"><span data-stu-id="0427d-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-321">寄件者使用的平均視頻畫面播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="0427d-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="0427d-322">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-324">int</span><span class="sxs-lookup"><span data-stu-id="0427d-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-325">寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="0427d-326">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-328">int</span><span class="sxs-lookup"><span data-stu-id="0427d-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-329">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-331">int</span><span class="sxs-lookup"><span data-stu-id="0427d-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-332">寄件者使用的影片資料流程數目上限。</span><span class="sxs-lookup"><span data-stu-id="0427d-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="0427d-333">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-335">Smallint</span><span class="sxs-lookup"><span data-stu-id="0427d-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="0427d-336">Foreign</span><span class="sxs-lookup"><span data-stu-id="0427d-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="0427d-337">接收器使用的影片代碼。</span><span class="sxs-lookup"><span data-stu-id="0427d-337">Video codes used by the receiver.</span></span> <span data-ttu-id="0427d-338">如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="0427d-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="0427d-339">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-341">int</span><span class="sxs-lookup"><span data-stu-id="0427d-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-342">接收器使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="0427d-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="0427d-343">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-345">int</span><span class="sxs-lookup"><span data-stu-id="0427d-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-346">接收器使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="0427d-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="0427d-347">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-349">float</span><span class="sxs-lookup"><span data-stu-id="0427d-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-350">接收器所用的平均影片速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="0427d-351">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-353">int</span><span class="sxs-lookup"><span data-stu-id="0427d-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-354">接收器的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="0427d-355">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-357">int</span><span class="sxs-lookup"><span data-stu-id="0427d-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-358">接收器的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="0427d-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="0427d-359">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-361">int</span><span class="sxs-lookup"><span data-stu-id="0427d-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-362">接收器的影片流量上限。</span><span class="sxs-lookup"><span data-stu-id="0427d-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="0427d-363">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-365">int</span><span class="sxs-lookup"><span data-stu-id="0427d-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-366">接收器的最小影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="0427d-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="0427d-367">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-369">int</span><span class="sxs-lookup"><span data-stu-id="0427d-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-370">影片模式 (例如，收件者的畫廊或單一 stream) 。</span><span class="sxs-lookup"><span data-stu-id="0427d-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="0427d-371">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-373">float</span><span class="sxs-lookup"><span data-stu-id="0427d-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-374">套用轉寄錯誤修正後的封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="0427d-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="0427d-375">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-377">float</span><span class="sxs-lookup"><span data-stu-id="0427d-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-378">動態功能旗標使用中的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="0427d-379">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-381">char (9) </span><span class="sxs-lookup"><span data-stu-id="0427d-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-382">通話期間測量的最小解析度。</span><span class="sxs-lookup"><span data-stu-id="0427d-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="0427d-383">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-385">float</span><span class="sxs-lookup"><span data-stu-id="0427d-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-386">低於低位元速率閾值的通話百分比 (70 千位/秒) 。</span><span class="sxs-lookup"><span data-stu-id="0427d-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="0427d-387">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-389">float</span><span class="sxs-lookup"><span data-stu-id="0427d-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-390">低於低機架速率閾值的通話百分比 (7.5 每秒，輸入) 的框架。</span><span class="sxs-lookup"><span data-stu-id="0427d-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="0427d-391">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-393">float</span><span class="sxs-lookup"><span data-stu-id="0427d-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-394">最低解析度發生之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="0427d-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="0427d-395">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="0427d-396">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0427d-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-398">float</span><span class="sxs-lookup"><span data-stu-id="0427d-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-399">通話的長度（秒）。</span><span class="sxs-lookup"><span data-stu-id="0427d-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="0427d-400">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0427d-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="0427d-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="0427d-402">位</span><span class="sxs-lookup"><span data-stu-id="0427d-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="0427d-403">會指出資料是否已從多個呼叫匯總。</span><span class="sxs-lookup"><span data-stu-id="0427d-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="0427d-404">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="0427d-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

