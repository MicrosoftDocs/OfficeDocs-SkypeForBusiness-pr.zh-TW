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
ms.openlocfilehash: 6e7a2d73f09a3cb48b1d50f06aa530c91d779b28
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529550"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="1c69a-102">Lync Server 2013 中的 AppSharingMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="1c69a-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c69a-103">_**主題上次修改日期：** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="1c69a-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="1c69a-p101">AppSharingMetricsThreshold 表格包含可與應用程式共用搭配使用之經驗品質計量適用的最佳值與可接受值。這些閾值可用來判斷應用程式共用經驗是否應該分類為不良。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="1c69a-106">此表格已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1c69a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1c69a-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1c69a-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1c69a-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1c69a-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-112">int</span><span class="sxs-lookup"><span data-stu-id="1c69a-112">int</span></span></p></td>
<td><p><span data-ttu-id="1c69a-113">主要</span><span class="sxs-lookup"><span data-stu-id="1c69a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1c69a-114">撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="1c69a-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-116">int</span><span class="sxs-lookup"><span data-stu-id="1c69a-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p102">適用於應用程式共用的最佳頻寬限制。預設值為 1000000。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-120">int</span><span class="sxs-lookup"><span data-stu-id="1c69a-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p103">適用於應用程式共用且可接受的頻寬限制。預設值為 500000。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-124">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="1c69a-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p104">對於可用於分類應用程式共用品質之「已毀損」並排顯示的最佳百分比率。此值是來自未送達檢視者之共用者的內容百分比。當共用者從圖表來源中捨棄並排顯示或 ASMCU 並排顯示個別捨棄來自共用者的並排顯示時，內容可能會被捨棄 (或毀損)。預設值為 11 個百分比。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-130">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="1c69a-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p105">對於可用於分類應用程式共用品質之「已毀損」並排顯示的可接受百分比率。此值是來自未送達檢視者之共用者的內容百分比。當共用者從圖表來源中捨棄並排顯示或 ASMCU 並排顯示個別捨棄來自共用者的並排顯示時，內容可能會被捨棄 (或毀損)。預設值為 36 個百分比。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-136">int</span><span class="sxs-lookup"><span data-stu-id="1c69a-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-137">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-139">int</span><span class="sxs-lookup"><span data-stu-id="1c69a-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-140">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-142">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-143">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-145">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-146">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-148">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-149">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-151">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-152">Microsoft Lync Server 2013 中不會使用此欄。</span><span class="sxs-lookup"><span data-stu-id="1c69a-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-154">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p106">應用程式共用中所含之兩個媒體端點間適用於相對單向延遲的最佳值。此為單一躍點延遲措施。預設值為 1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="1c69a-158">欄已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1c69a-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-160">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-p107">應用程式共用中所含之兩個媒體端點間適用於相對單向延遲的最佳值。此為單一躍點延遲措施。預設值為 1.75 秒。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="1c69a-164">欄已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1c69a-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1c69a-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-166">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-167">在檢視工作階段期間，AS 會議伺服器中平均 RDP 並排顯示處理延遲的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1c69a-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1c69a-168">延遲是指當伺服器 (共用或 MCU 上的開始幀進行編碼時，取決於案例) 和在檢視器中解碼相同開始幀的時間差。</span><span class="sxs-lookup"><span data-stu-id="1c69a-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1c69a-p109">高平均會反映檢視經驗中較長的延遲。負載過重的會議伺服器可能會發生較高的平均延遲。預設值為 200ms。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1c69a-172">欄已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1c69a-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1c69a-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1c69a-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1c69a-174">float</span><span class="sxs-lookup"><span data-stu-id="1c69a-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1c69a-175">在檢視工作階段期間，AS 會議伺服器中平均 RDP 並排顯示處理延遲的可接受值。</span><span class="sxs-lookup"><span data-stu-id="1c69a-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1c69a-176">延遲是指當伺服器 (共用或 MCU 上的開始幀進行編碼時，取決於案例) 和在檢視器中解碼相同開始幀的時間差。</span><span class="sxs-lookup"><span data-stu-id="1c69a-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1c69a-p111">高平均會反映檢視經驗中較長的延遲。負載過重的會議伺服器可能會發生較高的平均延遲。預設值為 200ms。</span><span class="sxs-lookup"><span data-stu-id="1c69a-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1c69a-180">欄已引進 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="1c69a-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

