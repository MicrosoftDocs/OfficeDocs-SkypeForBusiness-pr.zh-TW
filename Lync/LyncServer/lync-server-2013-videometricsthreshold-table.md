---
title: Lync Server 2013： VideoMetricsThreshold 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508510"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="59652-102">Lync Server 2013 中的 VideoMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="59652-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59652-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="59652-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="59652-104">VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。</span><span class="sxs-lookup"><span data-stu-id="59652-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59652-105"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="59652-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="59652-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="59652-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="59652-107"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="59652-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="59652-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="59652-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59652-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="59652-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-110">int</span><span class="sxs-lookup"><span data-stu-id="59652-110">int</span></span></p></td>
<td><p><span data-ttu-id="59652-111">主要</span><span class="sxs-lookup"><span data-stu-id="59652-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="59652-112">被指定的電話類型。</span><span class="sxs-lookup"><span data-stu-id="59652-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-114">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-115">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="59652-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-117">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-118">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="59652-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-120">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-121">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="59652-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-123">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-124">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="59652-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-126">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="59652-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-127">預設值為 12.0000。</span><span class="sxs-lookup"><span data-stu-id="59652-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-129">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="59652-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-130">預設值為 7.0000。</span><span class="sxs-lookup"><span data-stu-id="59652-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-132">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-133">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="59652-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-135">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-136">預設值為 10.0/。</span><span class="sxs-lookup"><span data-stu-id="59652-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-138">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-139">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="59652-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-141">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-142">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="59652-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-144">foat</span><span class="sxs-lookup"><span data-stu-id="59652-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-145">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="59652-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-147">float</span><span class="sxs-lookup"><span data-stu-id="59652-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-148">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="59652-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-150">float</span><span class="sxs-lookup"><span data-stu-id="59652-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-151">預設值為 12。</span><span class="sxs-lookup"><span data-stu-id="59652-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-153">float</span><span class="sxs-lookup"><span data-stu-id="59652-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-154">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="59652-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59652-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="59652-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-156">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-157">預設值為 5.00。</span><span class="sxs-lookup"><span data-stu-id="59652-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59652-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="59652-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="59652-159">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="59652-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="59652-160">預設值為 10.00。</span><span class="sxs-lookup"><span data-stu-id="59652-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

