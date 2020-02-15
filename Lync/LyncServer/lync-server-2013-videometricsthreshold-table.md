---
title: 'Lync Server 2013: VideoMetricsThreshold 表'
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
ms.openlocfilehash: 9ffd2c289917c5ccf0ec3a484284fecca3323810
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="23f7e-102">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="23f7e-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f7e-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="23f7e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="23f7e-104">VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。</span><span class="sxs-lookup"><span data-stu-id="23f7e-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23f7e-105"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="23f7e-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="23f7e-107"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="23f7e-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-110">int</span><span class="sxs-lookup"><span data-stu-id="23f7e-110">int</span></span></p></td>
<td><p><span data-ttu-id="23f7e-111">主要</span><span class="sxs-lookup"><span data-stu-id="23f7e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="23f7e-112">被指定的電話類型。</span><span class="sxs-lookup"><span data-stu-id="23f7e-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-114">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-115">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="23f7e-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-117">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-118">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="23f7e-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-120">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-121">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="23f7e-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-123">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-124">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="23f7e-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-126">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="23f7e-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-127">預設值為 12.0000。</span><span class="sxs-lookup"><span data-stu-id="23f7e-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-129">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="23f7e-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-130">預設值為 7.0000。</span><span class="sxs-lookup"><span data-stu-id="23f7e-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-132">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-133">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="23f7e-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-135">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-136">預設值為 10.0/。</span><span class="sxs-lookup"><span data-stu-id="23f7e-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-138">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-139">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="23f7e-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-141">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-142">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="23f7e-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-144">foat</span><span class="sxs-lookup"><span data-stu-id="23f7e-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-145">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="23f7e-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-147">float</span><span class="sxs-lookup"><span data-stu-id="23f7e-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-148">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="23f7e-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-150">float</span><span class="sxs-lookup"><span data-stu-id="23f7e-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-151">預設值為 12。</span><span class="sxs-lookup"><span data-stu-id="23f7e-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-153">float</span><span class="sxs-lookup"><span data-stu-id="23f7e-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-154">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="23f7e-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f7e-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-156">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-157">預設值為 5.00。</span><span class="sxs-lookup"><span data-stu-id="23f7e-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f7e-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="23f7e-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="23f7e-159">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="23f7e-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f7e-160">預設值為 10.00。</span><span class="sxs-lookup"><span data-stu-id="23f7e-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

