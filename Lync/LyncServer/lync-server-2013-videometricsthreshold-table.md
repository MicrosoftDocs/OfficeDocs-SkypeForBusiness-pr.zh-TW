---
title: Lync Server 2013： VideoMetricsThreshold 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="dcfae-102">Lync Server 2013 中的 VideoMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="dcfae-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcfae-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dcfae-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dcfae-104">VideoMetricsThreshold 表格包含與視頻通話搭配使用之經驗統計之品質的最佳和可接受的值。</span><span class="sxs-lookup"><span data-stu-id="dcfae-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dcfae-105"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dcfae-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dcfae-107"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dcfae-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-110">int</span><span class="sxs-lookup"><span data-stu-id="dcfae-110">int</span></span></p></td>
<td><p><span data-ttu-id="dcfae-111">首選</span><span class="sxs-lookup"><span data-stu-id="dcfae-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="dcfae-112">所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="dcfae-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-114">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-115">預設值為0.05。</span><span class="sxs-lookup"><span data-stu-id="dcfae-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-117">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-118">預設值為0.10。</span><span class="sxs-lookup"><span data-stu-id="dcfae-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-120">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-121">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="dcfae-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-123">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-124">預設值為10.0。</span><span class="sxs-lookup"><span data-stu-id="dcfae-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-126">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="dcfae-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-127">預設值為12.0000。</span><span class="sxs-lookup"><span data-stu-id="dcfae-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-129">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="dcfae-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-130">預設值為7.0000。</span><span class="sxs-lookup"><span data-stu-id="dcfae-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-132">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-133">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="dcfae-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-135">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-136">預設值為 10.0/</span><span class="sxs-lookup"><span data-stu-id="dcfae-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-138">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-139">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="dcfae-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-141">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-142">預設值為10.0。</span><span class="sxs-lookup"><span data-stu-id="dcfae-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-144">foat</span><span class="sxs-lookup"><span data-stu-id="dcfae-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-145">預設值為0.05。</span><span class="sxs-lookup"><span data-stu-id="dcfae-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-147">浮</span><span class="sxs-lookup"><span data-stu-id="dcfae-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-148">預設值為0.10。</span><span class="sxs-lookup"><span data-stu-id="dcfae-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-150">浮</span><span class="sxs-lookup"><span data-stu-id="dcfae-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-151">預設值為12。</span><span class="sxs-lookup"><span data-stu-id="dcfae-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-153">浮</span><span class="sxs-lookup"><span data-stu-id="dcfae-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-154">預設值為7。</span><span class="sxs-lookup"><span data-stu-id="dcfae-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dcfae-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-156">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-157">預設值為5.00。</span><span class="sxs-lookup"><span data-stu-id="dcfae-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dcfae-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="dcfae-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="dcfae-159">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="dcfae-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dcfae-160">預設值為10.00。</span><span class="sxs-lookup"><span data-stu-id="dcfae-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

