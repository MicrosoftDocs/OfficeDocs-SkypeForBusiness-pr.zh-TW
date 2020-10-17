---
title: Lync Server 2013： VideoMetricsThreshold 表格
description: Lync Server 2013： VideoMetricsThreshold 表格。
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
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567999"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="aea8b-103">Lync Server 2013 中的 VideoMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="aea8b-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aea8b-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="aea8b-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="aea8b-105">VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。</span><span class="sxs-lookup"><span data-stu-id="aea8b-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aea8b-106"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="aea8b-107"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="aea8b-108"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="aea8b-109"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-111">int</span><span class="sxs-lookup"><span data-stu-id="aea8b-111">int</span></span></p></td>
<td><p><span data-ttu-id="aea8b-112">主要</span><span class="sxs-lookup"><span data-stu-id="aea8b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="aea8b-113">被指定的電話類型。</span><span class="sxs-lookup"><span data-stu-id="aea8b-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-115">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-116">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="aea8b-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-118">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-119">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="aea8b-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-121">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-122">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="aea8b-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-124">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-125">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="aea8b-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-127">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="aea8b-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-128">預設值為 12.0000。</span><span class="sxs-lookup"><span data-stu-id="aea8b-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-130">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="aea8b-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-131">預設值為 7.0000。</span><span class="sxs-lookup"><span data-stu-id="aea8b-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-133">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-134">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="aea8b-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-136">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-137">預設值為 10.0/。</span><span class="sxs-lookup"><span data-stu-id="aea8b-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-139">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-140">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="aea8b-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-142">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-143">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="aea8b-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-145">foat</span><span class="sxs-lookup"><span data-stu-id="aea8b-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-146">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="aea8b-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-148">float</span><span class="sxs-lookup"><span data-stu-id="aea8b-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-149">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="aea8b-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-151">float</span><span class="sxs-lookup"><span data-stu-id="aea8b-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-152">預設值為 12。</span><span class="sxs-lookup"><span data-stu-id="aea8b-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-154">float</span><span class="sxs-lookup"><span data-stu-id="aea8b-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-155">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="aea8b-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aea8b-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-157">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-158">預設值為 5.00。</span><span class="sxs-lookup"><span data-stu-id="aea8b-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aea8b-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="aea8b-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="aea8b-160">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="aea8b-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aea8b-161">預設值為 10.00。</span><span class="sxs-lookup"><span data-stu-id="aea8b-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

