---
title: Lync Server 2013： VideoStream 表格
description: Lync Server 2013： VideoStream 表格。
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567989"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="2652f-103">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="2652f-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2652f-104">_**主題上次修改日期：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="2652f-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="2652f-105">每筆記錄代表一個視頻資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-105">Each record represents one video stream.</span></span> <span data-ttu-id="2652f-106">一個影片媒體行通常包含兩個影片。</span><span class="sxs-lookup"><span data-stu-id="2652f-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2652f-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="2652f-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="2652f-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="2652f-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2652f-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2652f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2652f-113">主要</span><span class="sxs-lookup"><span data-stu-id="2652f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="2652f-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="2652f-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-116">int</span><span class="sxs-lookup"><span data-stu-id="2652f-116">int</span></span></p></td>
<td><p><span data-ttu-id="2652f-117">主要</span><span class="sxs-lookup"><span data-stu-id="2652f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="2652f-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中從 MediaLine 表格</a>參考的 R。</span><span class="sxs-lookup"><span data-stu-id="2652f-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-120">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="2652f-121">主要</span><span class="sxs-lookup"><span data-stu-id="2652f-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="2652f-122">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="2652f-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-124">int</span><span class="sxs-lookup"><span data-stu-id="2652f-124">int</span></span></p></td>
<td><p><span data-ttu-id="2652f-125">主要</span><span class="sxs-lookup"><span data-stu-id="2652f-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="2652f-126">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="2652f-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-128">Smallint</span><span class="sxs-lookup"><span data-stu-id="2652f-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="2652f-129">外部、主要</span><span class="sxs-lookup"><span data-stu-id="2652f-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="2652f-130">負載描述。</span><span class="sxs-lookup"><span data-stu-id="2652f-130">Payload description.</span></span> <span data-ttu-id="2652f-131">如需詳細資訊，請參閱 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2652f-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-133">int</span><span class="sxs-lookup"><span data-stu-id="2652f-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-134">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="2652f-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-136">int</span><span class="sxs-lookup"><span data-stu-id="2652f-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-137">影片中的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="2652f-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-138"><strong>往返</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-139">int</span><span class="sxs-lookup"><span data-stu-id="2652f-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-140">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="2652f-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-142">int</span><span class="sxs-lookup"><span data-stu-id="2652f-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-143">影片資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="2652f-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-145">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-146">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="2652f-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-148">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-149">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="2652f-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-151">int</span><span class="sxs-lookup"><span data-stu-id="2652f-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-152">影片的封包計數 (即時傳輸通訊協定，RTP) 。</span><span class="sxs-lookup"><span data-stu-id="2652f-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-154">int</span><span class="sxs-lookup"><span data-stu-id="2652f-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-155">視頻資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="2652f-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-157">char (9) </span><span class="sxs-lookup"><span data-stu-id="2652f-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-158">影片解析度（圖元寬度乘以圖元高度）。</span><span class="sxs-lookup"><span data-stu-id="2652f-158">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="2652f-159">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="2652f-159">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-161">int</span><span class="sxs-lookup"><span data-stu-id="2652f-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-162">視頻資料流程的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-164">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-165">收到的影片框架速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-167">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-168">傳送的影片畫面速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-170">int</span><span class="sxs-lookup"><span data-stu-id="2652f-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-171">影片會話期間的最大影片位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-173">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-174">丟失之總影片幀的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-176">位</span><span class="sxs-lookup"><span data-stu-id="2652f-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-177">無法使用。</span><span class="sxs-lookup"><span data-stu-id="2652f-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-179">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-180">丟失之總影片幀的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-182">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-183">一般交換格式之通話的百分比 (CIF) 解析度。</span><span class="sxs-lookup"><span data-stu-id="2652f-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-185">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-186">VGA 解析度之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-188">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-189">HD720 解析度之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-191">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-192">未放下框架的通話時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-194">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-195">以 B 框架丟棄的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-197">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-198">具有 BP 框架丟棄之通話持續時間的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-200">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-201">具有 BPSP 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-203">Tinyint</span><span class="sxs-lookup"><span data-stu-id="2652f-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-204">具有 BPSPI 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-205"><strong>入境</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-206">位</span><span class="sxs-lookup"><span data-stu-id="2652f-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-207">接收接收方的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="2652f-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-208"><strong>出境</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-209">位</span><span class="sxs-lookup"><span data-stu-id="2652f-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-210">接收寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="2652f-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-212">位</span><span class="sxs-lookup"><span data-stu-id="2652f-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="2652f-213">1表示資料流程的方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="2652f-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="2652f-214">0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="2652f-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-216">float</span><span class="sxs-lookup"><span data-stu-id="2652f-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-217">會指出通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="2652f-218">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-220">float</span><span class="sxs-lookup"><span data-stu-id="2652f-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-221">會指出在此通話所占的百分比，造成擁塞是由網路封包的延遲抵達所造成。</span><span class="sxs-lookup"><span data-stu-id="2652f-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="2652f-222">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-224">float</span><span class="sxs-lookup"><span data-stu-id="2652f-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-225">會指出通話在競爭網路資源時的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="2652f-226">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-228">int</span><span class="sxs-lookup"><span data-stu-id="2652f-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-229">通話期間測量的頻寬預估最小值。</span><span class="sxs-lookup"><span data-stu-id="2652f-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2652f-230">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-232">int</span><span class="sxs-lookup"><span data-stu-id="2652f-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-233">通話期間測量的頻寬預估最大值。</span><span class="sxs-lookup"><span data-stu-id="2652f-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2652f-234">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-236">int</span><span class="sxs-lookup"><span data-stu-id="2652f-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-237">通話期間測量的頻寬預估標準差。</span><span class="sxs-lookup"><span data-stu-id="2652f-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2652f-238">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-240">int</span><span class="sxs-lookup"><span data-stu-id="2652f-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-241">通話期間測量的平均頻寬預估量。</span><span class="sxs-lookup"><span data-stu-id="2652f-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="2652f-242">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-244">float</span><span class="sxs-lookup"><span data-stu-id="2652f-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-245">端點決定網路連線無法支援多種顯示的情況影片所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="2652f-246">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-248">float</span><span class="sxs-lookup"><span data-stu-id="2652f-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-249">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="2652f-249">Total amount of one-way latency.</span></span> <span data-ttu-id="2652f-250">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-250">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-251">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-253">float</span><span class="sxs-lookup"><span data-stu-id="2652f-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-254">單向延遲的平均金額。</span><span class="sxs-lookup"><span data-stu-id="2652f-254">Average amount of one-way latency.</span></span> <span data-ttu-id="2652f-255">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-255">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-256">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-258">float</span><span class="sxs-lookup"><span data-stu-id="2652f-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-259">單向延遲的最大值。</span><span class="sxs-lookup"><span data-stu-id="2652f-259">Maximum amount of one-way latency.</span></span> <span data-ttu-id="2652f-260">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-260">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-261">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-263">int</span><span class="sxs-lookup"><span data-stu-id="2652f-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-264">總單向突發的發生次數。</span><span class="sxs-lookup"><span data-stu-id="2652f-264">Total one-way burst occurrences.</span></span> <span data-ttu-id="2652f-265">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="2652f-265">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2652f-266">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-266">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-267">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-269">int</span><span class="sxs-lookup"><span data-stu-id="2652f-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-270">總單向爆炸流量密度。</span><span class="sxs-lookup"><span data-stu-id="2652f-270">Total one-way burst density.</span></span> <span data-ttu-id="2652f-271">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="2652f-271">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2652f-272">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-272">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-273">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-275">float</span><span class="sxs-lookup"><span data-stu-id="2652f-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-276">總單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="2652f-276">Total one-way burst duration.</span></span> <span data-ttu-id="2652f-277">"爆發" 傳輸是一種傳輸，其資料流程中的資料流程與穩定的資料流程相反。</span><span class="sxs-lookup"><span data-stu-id="2652f-277">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="2652f-278">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-278">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-279">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-281">int</span><span class="sxs-lookup"><span data-stu-id="2652f-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-282">對單向間隔的總發生次數。</span><span class="sxs-lookup"><span data-stu-id="2652f-282">Total one-way gap occurrences.</span></span> <span data-ttu-id="2652f-283">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-283">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2652f-284">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-284">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-285">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-287">float</span><span class="sxs-lookup"><span data-stu-id="2652f-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-288">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="2652f-288">Total one-way gap density.</span></span> <span data-ttu-id="2652f-289">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-289">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2652f-290">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-290">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-291">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-293">float</span><span class="sxs-lookup"><span data-stu-id="2652f-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-294">總的單向間距持續時間。</span><span class="sxs-lookup"><span data-stu-id="2652f-294">Total one-way gap duration.</span></span> <span data-ttu-id="2652f-295">"爆發" 傳輸是一種傳輸，其中資料流程的資料流程與穩定的資料流程相反，其資料流程會以無法預測的方式傳輸;間隙表示這些猝發間的延遲。</span><span class="sxs-lookup"><span data-stu-id="2652f-295">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="2652f-296">此度量單位會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-296">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="2652f-297">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-299">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="2652f-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-300">視頻封包遺失的速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="2652f-301">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-303">int</span><span class="sxs-lookup"><span data-stu-id="2652f-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-304">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="2652f-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="2652f-305">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-307">Smallint</span><span class="sxs-lookup"><span data-stu-id="2652f-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="2652f-308">Foreign</span><span class="sxs-lookup"><span data-stu-id="2652f-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2652f-309">寄件者使用的影片編解碼器類型。</span><span class="sxs-lookup"><span data-stu-id="2652f-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="2652f-310">如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2652f-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2652f-311">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-313">int</span><span class="sxs-lookup"><span data-stu-id="2652f-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-314">寄件者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="2652f-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="2652f-315">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-317">int</span><span class="sxs-lookup"><span data-stu-id="2652f-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-318">寄件者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="2652f-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="2652f-319">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-321">float</span><span class="sxs-lookup"><span data-stu-id="2652f-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-322">寄件者使用的平均視頻畫面播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="2652f-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="2652f-323">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-325">int</span><span class="sxs-lookup"><span data-stu-id="2652f-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-326">寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="2652f-327">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-329">int</span><span class="sxs-lookup"><span data-stu-id="2652f-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-330">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-332">int</span><span class="sxs-lookup"><span data-stu-id="2652f-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-333">寄件者使用的影片資料流程數目上限。</span><span class="sxs-lookup"><span data-stu-id="2652f-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="2652f-334">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-336">Smallint</span><span class="sxs-lookup"><span data-stu-id="2652f-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="2652f-337">Foreign</span><span class="sxs-lookup"><span data-stu-id="2652f-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="2652f-338">接收器使用的影片代碼。</span><span class="sxs-lookup"><span data-stu-id="2652f-338">Video codes used by the receiver.</span></span> <span data-ttu-id="2652f-339">如需詳細資訊，請參閱 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2652f-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="2652f-340">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-342">int</span><span class="sxs-lookup"><span data-stu-id="2652f-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-343">接收器使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="2652f-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="2652f-344">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-346">int</span><span class="sxs-lookup"><span data-stu-id="2652f-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-347">接收器使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="2652f-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="2652f-348">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-350">float</span><span class="sxs-lookup"><span data-stu-id="2652f-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-351">接收器所用的平均影片速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="2652f-352">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-354">int</span><span class="sxs-lookup"><span data-stu-id="2652f-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-355">接收器的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="2652f-356">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-358">int</span><span class="sxs-lookup"><span data-stu-id="2652f-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-359">接收器的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="2652f-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="2652f-360">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-362">int</span><span class="sxs-lookup"><span data-stu-id="2652f-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-363">接收器的影片流量上限。</span><span class="sxs-lookup"><span data-stu-id="2652f-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="2652f-364">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-366">int</span><span class="sxs-lookup"><span data-stu-id="2652f-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-367">接收器的最小影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="2652f-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="2652f-368">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-370">int</span><span class="sxs-lookup"><span data-stu-id="2652f-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-371">影片模式 (例如，收件者的畫廊或單一 stream) 。</span><span class="sxs-lookup"><span data-stu-id="2652f-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="2652f-372">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-374">float</span><span class="sxs-lookup"><span data-stu-id="2652f-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-375">套用轉寄錯誤修正後的封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="2652f-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="2652f-376">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-378">float</span><span class="sxs-lookup"><span data-stu-id="2652f-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-379">動態功能旗標使用中的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="2652f-380">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-382">char (9) </span><span class="sxs-lookup"><span data-stu-id="2652f-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-383">通話期間測量的最小解析度。</span><span class="sxs-lookup"><span data-stu-id="2652f-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="2652f-384">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-386">float</span><span class="sxs-lookup"><span data-stu-id="2652f-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-387">低於低位元速率閾值的通話百分比 (70 千位/秒) 。</span><span class="sxs-lookup"><span data-stu-id="2652f-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="2652f-388">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-390">float</span><span class="sxs-lookup"><span data-stu-id="2652f-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-391">低於低機架速率閾值的通話百分比 (7.5 每秒，輸入) 的框架。</span><span class="sxs-lookup"><span data-stu-id="2652f-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="2652f-392">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-394">float</span><span class="sxs-lookup"><span data-stu-id="2652f-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-395">最低解析度發生之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="2652f-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="2652f-396">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="2652f-397">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2652f-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-399">float</span><span class="sxs-lookup"><span data-stu-id="2652f-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-400">通話的長度（秒）。</span><span class="sxs-lookup"><span data-stu-id="2652f-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="2652f-401">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2652f-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="2652f-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="2652f-403">位</span><span class="sxs-lookup"><span data-stu-id="2652f-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2652f-404">會指出資料是否已從多個呼叫匯總。</span><span class="sxs-lookup"><span data-stu-id="2652f-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="2652f-405">此欄是在 Microsoft Lync Server 2013 中引進。</span><span class="sxs-lookup"><span data-stu-id="2652f-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

