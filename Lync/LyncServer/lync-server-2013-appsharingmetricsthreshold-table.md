---
title: Lync Server 2013： AppSharingMetricsThreshold 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="50337-102">Lync Server 2013 中的 AppSharingMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="50337-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50337-103">_**主題上次修改日期：** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="50337-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="50337-104">AppSharingMetricsThreshold 表格包含與應用程式共用搭配使用之經驗統計之品質最佳且可接受的值。</span><span class="sxs-lookup"><span data-stu-id="50337-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="50337-105">這些閾值是用來判斷應用程式共用體驗是否應該歸類為較差。</span><span class="sxs-lookup"><span data-stu-id="50337-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="50337-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="50337-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50337-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="50337-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="50337-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="50337-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="50337-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="50337-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="50337-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="50337-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50337-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="50337-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-112">int</span><span class="sxs-lookup"><span data-stu-id="50337-112">int</span></span></p></td>
<td><p><span data-ttu-id="50337-113">首選</span><span class="sxs-lookup"><span data-stu-id="50337-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="50337-114">所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="50337-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-116">int</span><span class="sxs-lookup"><span data-stu-id="50337-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-117">應用程式共用的最佳頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="50337-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="50337-118">預設值為1000000。</span><span class="sxs-lookup"><span data-stu-id="50337-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-120">int</span><span class="sxs-lookup"><span data-stu-id="50337-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-121">應用程式共用的可接受頻寬限制。</span><span class="sxs-lookup"><span data-stu-id="50337-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="50337-122">預設值為500000。</span><span class="sxs-lookup"><span data-stu-id="50337-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-124">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="50337-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-125">針對應用程式共用品質分類的「spoiled」磚最佳百分比率。</span><span class="sxs-lookup"><span data-stu-id="50337-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="50337-126">此值是來自共用資源且未到達檢視器的內容百分比。</span><span class="sxs-lookup"><span data-stu-id="50337-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="50337-127">在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。</span><span class="sxs-lookup"><span data-stu-id="50337-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="50337-128">預設值為11%。</span><span class="sxs-lookup"><span data-stu-id="50337-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-130">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="50337-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-131">針對應用程式共用品質分類的 "spoiled" 磚的 cceptable 百分比率。</span><span class="sxs-lookup"><span data-stu-id="50337-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="50337-132">此值是來自共用資源且未到達檢視器的內容百分比。</span><span class="sxs-lookup"><span data-stu-id="50337-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="50337-133">在共用物件捨棄來自圖形來源或 ASMCU 磚的磚時，內容可能會被捨棄（或 spoiled）。</span><span class="sxs-lookup"><span data-stu-id="50337-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="50337-134">預設值為36%。</span><span class="sxs-lookup"><span data-stu-id="50337-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-136">int</span><span class="sxs-lookup"><span data-stu-id="50337-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-137">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-139">int</span><span class="sxs-lookup"><span data-stu-id="50337-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-140">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-142">浮</span><span class="sxs-lookup"><span data-stu-id="50337-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-143">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-145">浮</span><span class="sxs-lookup"><span data-stu-id="50337-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-146">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-148">浮</span><span class="sxs-lookup"><span data-stu-id="50337-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-149">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-151">浮</span><span class="sxs-lookup"><span data-stu-id="50337-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-152">此欄未用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="50337-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-154">浮</span><span class="sxs-lookup"><span data-stu-id="50337-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-155">應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。</span><span class="sxs-lookup"><span data-stu-id="50337-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="50337-156">這是一個單跳躍延遲測量。</span><span class="sxs-lookup"><span data-stu-id="50337-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="50337-157">預設值為1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="50337-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="50337-158">欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="50337-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-160">浮</span><span class="sxs-lookup"><span data-stu-id="50337-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-161">應用程式共用所涉及之兩個媒體端點之間相對單向延遲的最佳值。</span><span class="sxs-lookup"><span data-stu-id="50337-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="50337-162">這是一個單跳躍延遲測量。</span><span class="sxs-lookup"><span data-stu-id="50337-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="50337-163">預設值為1.75 秒。</span><span class="sxs-lookup"><span data-stu-id="50337-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="50337-164">欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="50337-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50337-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="50337-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-166">浮</span><span class="sxs-lookup"><span data-stu-id="50337-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-167">在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲時間最佳值。</span><span class="sxs-lookup"><span data-stu-id="50337-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="50337-168">延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。</span><span class="sxs-lookup"><span data-stu-id="50337-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="50337-169">高平均值會在觀賞體驗中反映較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="50337-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="50337-170">超負荷的會議服務器可能會遇到較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="50337-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="50337-171">預設值為200ms。</span><span class="sxs-lookup"><span data-stu-id="50337-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="50337-172">欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="50337-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50337-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="50337-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="50337-174">浮</span><span class="sxs-lookup"><span data-stu-id="50337-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50337-175">在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲值。</span><span class="sxs-lookup"><span data-stu-id="50337-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="50337-176">延隔時間是在伺服器上（根據案例），在伺服器（共用或 MCU）上對開始幀進行編碼的時間差，且在檢視器上解碼相同的開始畫面。</span><span class="sxs-lookup"><span data-stu-id="50337-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="50337-177">高平均值會在觀賞體驗中反映較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="50337-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="50337-178">超負荷的會議服務器可能會遇到較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="50337-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="50337-179">預設值為200ms。</span><span class="sxs-lookup"><span data-stu-id="50337-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="50337-180">欄是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="50337-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

