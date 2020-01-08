---
title: Lync Server 2013：VideoStream 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="a986f-102">Lync Server 2013 中的 VideoStream 表格</span><span class="sxs-lookup"><span data-stu-id="a986f-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a986f-103">_**主題上次修改日期：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="a986f-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="a986f-104">每個記錄代表一個影片資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-104">Each record represents one video stream.</span></span> <span data-ttu-id="a986f-105">一個影片媒體線通常包含兩個影片串流。</span><span class="sxs-lookup"><span data-stu-id="a986f-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a986f-106"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="a986f-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="a986f-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="a986f-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a986f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a986f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a986f-112">首選</span><span class="sxs-lookup"><span data-stu-id="a986f-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="a986f-113">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a986f-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-115">int</span><span class="sxs-lookup"><span data-stu-id="a986f-115">int</span></span></p></td>
<td><p><span data-ttu-id="a986f-116">首選</span><span class="sxs-lookup"><span data-stu-id="a986f-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="a986f-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 的 MediaLine 資料表中</a>參照 R。</span><span class="sxs-lookup"><span data-stu-id="a986f-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-119">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a986f-120">首選</span><span class="sxs-lookup"><span data-stu-id="a986f-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="a986f-121">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a986f-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-123">int</span><span class="sxs-lookup"><span data-stu-id="a986f-123">int</span></span></p></td>
<td><p><span data-ttu-id="a986f-124">首選</span><span class="sxs-lookup"><span data-stu-id="a986f-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="a986f-125">媒體線中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a986f-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-127">Smallint</span><span class="sxs-lookup"><span data-stu-id="a986f-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="a986f-128">外、主要</span><span class="sxs-lookup"><span data-stu-id="a986f-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="a986f-129">[負載描述]。</span><span class="sxs-lookup"><span data-stu-id="a986f-129">Payload description.</span></span> <span data-ttu-id="a986f-130">如需詳細資訊，請參閱<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中</a>的 [PayloadDescription] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a986f-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-132">int</span><span class="sxs-lookup"><span data-stu-id="a986f-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-133">從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="a986f-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-135">int</span><span class="sxs-lookup"><span data-stu-id="a986f-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-136">在視頻會話期間網路抖動的上限。</span><span class="sxs-lookup"><span data-stu-id="a986f-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-137"><strong>環路</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-138">int</span><span class="sxs-lookup"><span data-stu-id="a986f-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-139">從 RTCP 統計資料中往返的時間。</span><span class="sxs-lookup"><span data-stu-id="a986f-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-141">int</span><span class="sxs-lookup"><span data-stu-id="a986f-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-142">影片串流的最大往返行程時間。</span><span class="sxs-lookup"><span data-stu-id="a986f-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-144">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-145">通話期間的平均資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="a986f-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-147">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-148">通話期間觀察到的最大資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="a986f-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-150">int</span><span class="sxs-lookup"><span data-stu-id="a986f-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-151">影片串流的資料包計數（即時傳輸通訊協定、RTP）。</span><span class="sxs-lookup"><span data-stu-id="a986f-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-153">int</span><span class="sxs-lookup"><span data-stu-id="a986f-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-154">影片串流的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="a986f-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-156">char （9）</span><span class="sxs-lookup"><span data-stu-id="a986f-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-157">以圖元為單位的影片解析度，以圖元為單位的寬度乘以圖元高度。</span><span class="sxs-lookup"><span data-stu-id="a986f-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="a986f-158">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="a986f-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-160">int</span><span class="sxs-lookup"><span data-stu-id="a986f-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-161">影片串流的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-163">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-164">收到的影片畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-166">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-167">已傳送的影片畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-169">int</span><span class="sxs-lookup"><span data-stu-id="a986f-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-170">影片會話期間的最大視頻位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-172">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-173">遺失的視頻畫面總百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-175">稍微</span><span class="sxs-lookup"><span data-stu-id="a986f-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-176">無法使用。</span><span class="sxs-lookup"><span data-stu-id="a986f-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-178">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-179">遺失的視頻畫面總百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-181">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-182">常見交換格式（CIF）解析度的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-184">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-185">以 VGA 解析度表示的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-187">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-188">HD720 解析度的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-190">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-191">沒有框架拖放的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-193">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-194">B 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-196">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-197">含 BP 框架下沉之通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-199">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-200">BPSP 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-202">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a986f-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-203">BPSPI 框架下沉的通話持續時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-204"><strong>進貨</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-205">稍微</span><span class="sxs-lookup"><span data-stu-id="a986f-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-206">收到接收器端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="a986f-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-207"><strong>發</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-208">稍微</span><span class="sxs-lookup"><span data-stu-id="a986f-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-209">收到寄件者端的資料流程資料。</span><span class="sxs-lookup"><span data-stu-id="a986f-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-211">稍微</span><span class="sxs-lookup"><span data-stu-id="a986f-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a986f-212">1表示資料流程方向從來電者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="a986f-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="a986f-213">0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="a986f-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-215">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-216">表示通話處於遺失擁塞狀態的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="a986f-217">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-219">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-220">指出因網路資料包損損，導致堵塞的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="a986f-221">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-223">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-224">表示通話爭用網路資源的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="a986f-225">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-227">int</span><span class="sxs-lookup"><span data-stu-id="a986f-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-228">呼叫期間測量的最小頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="a986f-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a986f-229">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-231">int</span><span class="sxs-lookup"><span data-stu-id="a986f-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-232">呼叫期間測量的最大頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="a986f-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a986f-233">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-235">int</span><span class="sxs-lookup"><span data-stu-id="a986f-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-236">在通話期間測量之頻寬估計的標準差。</span><span class="sxs-lookup"><span data-stu-id="a986f-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a986f-237">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-239">int</span><span class="sxs-lookup"><span data-stu-id="a986f-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-240">通話期間平均測量的頻寬估計量。</span><span class="sxs-lookup"><span data-stu-id="a986f-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="a986f-241">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-243">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-244">端點判斷網路連接無法支援多種顯示的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="a986f-245">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-247">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-248">單向延遲的總金額。</span><span class="sxs-lookup"><span data-stu-id="a986f-248">Total amount of one-way latency.</span></span> <span data-ttu-id="a986f-249">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-250">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-252">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-253">單向延隔時間的平均量。</span><span class="sxs-lookup"><span data-stu-id="a986f-253">Average amount of one-way latency.</span></span> <span data-ttu-id="a986f-254">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-255">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-257">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-258">單向延隔時間的最大值。</span><span class="sxs-lookup"><span data-stu-id="a986f-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="a986f-259">相對單向延遲會測量用戶端與伺服器之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-260">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-262">int</span><span class="sxs-lookup"><span data-stu-id="a986f-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-263">單向突發發生次數總計。</span><span class="sxs-lookup"><span data-stu-id="a986f-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="a986f-264">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="a986f-265">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-266">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-268">int</span><span class="sxs-lookup"><span data-stu-id="a986f-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-269">總計單向突發密度。</span><span class="sxs-lookup"><span data-stu-id="a986f-269">Total one-way burst density.</span></span> <span data-ttu-id="a986f-270">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="a986f-271">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-272">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-274">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-275">總計單向突發持續時間。</span><span class="sxs-lookup"><span data-stu-id="a986f-275">Total one-way burst duration.</span></span> <span data-ttu-id="a986f-276">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="a986f-277">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-278">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-280">int</span><span class="sxs-lookup"><span data-stu-id="a986f-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-281">總的單向間距發生情況。</span><span class="sxs-lookup"><span data-stu-id="a986f-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="a986f-282">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="a986f-283">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-284">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-286">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-287">總單向間距密度。</span><span class="sxs-lookup"><span data-stu-id="a986f-287">Total one-way gap density.</span></span> <span data-ttu-id="a986f-288">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="a986f-289">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-290">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-292">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-293">總共一個單向間距時間。</span><span class="sxs-lookup"><span data-stu-id="a986f-293">Total one-way gap duration.</span></span> <span data-ttu-id="a986f-294">"Bursty" 傳輸是一種傳輸，其中的資料流程過無法預料的猝發，而不是穩定的資料流程;[空隙] 表示這些猝發之間的延遲。</span><span class="sxs-lookup"><span data-stu-id="a986f-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="a986f-295">此量度會測量用戶端與伺服器之間的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a986f-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="a986f-296">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-298">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a986f-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-299">視頻資料包遺失的頻率。</span><span class="sxs-lookup"><span data-stu-id="a986f-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="a986f-300">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-302">int</span><span class="sxs-lookup"><span data-stu-id="a986f-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-303">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="a986f-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="a986f-304">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-306">Smallint</span><span class="sxs-lookup"><span data-stu-id="a986f-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="a986f-307">外</span><span class="sxs-lookup"><span data-stu-id="a986f-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a986f-308">寄件者所用的視頻編解碼器類型。</span><span class="sxs-lookup"><span data-stu-id="a986f-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="a986f-309">如需詳細資訊，請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中</a>的 [CodecDescription] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a986f-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a986f-310">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-312">int</span><span class="sxs-lookup"><span data-stu-id="a986f-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-313">寄件者使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="a986f-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="a986f-314">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-316">int</span><span class="sxs-lookup"><span data-stu-id="a986f-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-317">寄件者使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="a986f-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="a986f-318">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-320">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-321">寄件者使用的平均視頻畫面播放速率傳輸。</span><span class="sxs-lookup"><span data-stu-id="a986f-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="a986f-322">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-324">int</span><span class="sxs-lookup"><span data-stu-id="a986f-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-325">該寄件者的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="a986f-326">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-328">int</span><span class="sxs-lookup"><span data-stu-id="a986f-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-329">寄件者的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-331">int</span><span class="sxs-lookup"><span data-stu-id="a986f-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-332">寄件者使用的最大視頻串流數。</span><span class="sxs-lookup"><span data-stu-id="a986f-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="a986f-333">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-335">Smallint</span><span class="sxs-lookup"><span data-stu-id="a986f-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="a986f-336">外</span><span class="sxs-lookup"><span data-stu-id="a986f-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="a986f-337">接收器所使用的影片代碼。</span><span class="sxs-lookup"><span data-stu-id="a986f-337">Video codes used by the receiver.</span></span> <span data-ttu-id="a986f-338">如需詳細資訊，請參閱<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中</a>的 [CodecDescription] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a986f-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="a986f-339">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-341">int</span><span class="sxs-lookup"><span data-stu-id="a986f-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-342">接收器所使用的解析度寬度。</span><span class="sxs-lookup"><span data-stu-id="a986f-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="a986f-343">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-345">int</span><span class="sxs-lookup"><span data-stu-id="a986f-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-346">接收器所使用的解析度高度。</span><span class="sxs-lookup"><span data-stu-id="a986f-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="a986f-347">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-349">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-350">接收器所使用的平均視頻畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="a986f-351">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-353">int</span><span class="sxs-lookup"><span data-stu-id="a986f-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-354">接收器的最大位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a986f-355">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-357">int</span><span class="sxs-lookup"><span data-stu-id="a986f-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-358">接收器的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="a986f-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="a986f-359">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-361">int</span><span class="sxs-lookup"><span data-stu-id="a986f-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-362">接收器的最大影片流量。</span><span class="sxs-lookup"><span data-stu-id="a986f-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a986f-363">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-365">int</span><span class="sxs-lookup"><span data-stu-id="a986f-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-366">接收器的最小視頻流量。</span><span class="sxs-lookup"><span data-stu-id="a986f-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="a986f-367">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-369">int</span><span class="sxs-lookup"><span data-stu-id="a986f-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-370">接收器的影片模式（例如圖庫或單一資料流程）。</span><span class="sxs-lookup"><span data-stu-id="a986f-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="a986f-371">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-373">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-374">已套用轉寄錯誤修正之後的資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="a986f-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="a986f-375">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-377">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-378">動態功能標誌作用中的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="a986f-379">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-381">char （9）</span><span class="sxs-lookup"><span data-stu-id="a986f-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-382">通話期間測量的最小解析度。</span><span class="sxs-lookup"><span data-stu-id="a986f-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="a986f-383">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-385">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-386">通話百分比低於低位率閾值（70 kb/秒）。</span><span class="sxs-lookup"><span data-stu-id="a986f-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="a986f-387">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-389">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-390">通話百分比低於低畫面播放速率閾值（7.5 幀/秒、入站）。</span><span class="sxs-lookup"><span data-stu-id="a986f-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="a986f-391">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-393">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-394">最低解析度所發生通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="a986f-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="a986f-395">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="a986f-396">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a986f-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-398">浮</span><span class="sxs-lookup"><span data-stu-id="a986f-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-399">通話長度（以秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="a986f-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="a986f-400">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a986f-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="a986f-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="a986f-402">稍微</span><span class="sxs-lookup"><span data-stu-id="a986f-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a986f-403">指示資料是否已從多個通話匯總。</span><span class="sxs-lookup"><span data-stu-id="a986f-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="a986f-404">此欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a986f-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

