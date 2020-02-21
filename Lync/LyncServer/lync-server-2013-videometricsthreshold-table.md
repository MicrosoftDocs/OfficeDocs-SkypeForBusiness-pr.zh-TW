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
ms.openlocfilehash: 58a054ba58ff7e1e839b0aeca88d0e61164e30b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="ec53c-102">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="ec53c-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec53c-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="ec53c-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ec53c-104">VideoMetricsThreshold 資料表包含了最佳且可接受的值，供經驗品質搭配視訊通話使用。</span><span class="sxs-lookup"><span data-stu-id="ec53c-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec53c-105"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ec53c-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ec53c-107"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ec53c-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-110">int</span><span class="sxs-lookup"><span data-stu-id="ec53c-110">int</span></span></p></td>
<td><p><span data-ttu-id="ec53c-111">主要</span><span class="sxs-lookup"><span data-stu-id="ec53c-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="ec53c-112">被指定的電話類型。</span><span class="sxs-lookup"><span data-stu-id="ec53c-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-114">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-115">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="ec53c-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-117">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-118">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="ec53c-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-120">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-121">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="ec53c-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-123">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-124">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="ec53c-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-126">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="ec53c-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-127">預設值為 12.0000。</span><span class="sxs-lookup"><span data-stu-id="ec53c-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-129">decimal(9,4)</span><span class="sxs-lookup"><span data-stu-id="ec53c-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-130">預設值為 7.0000。</span><span class="sxs-lookup"><span data-stu-id="ec53c-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-132">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-133">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="ec53c-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-135">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-136">預設值為 10.0/。</span><span class="sxs-lookup"><span data-stu-id="ec53c-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-138">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-139">預設值為 5.0。</span><span class="sxs-lookup"><span data-stu-id="ec53c-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-141">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-142">預設值為 10.0。</span><span class="sxs-lookup"><span data-stu-id="ec53c-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-144">foat</span><span class="sxs-lookup"><span data-stu-id="ec53c-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-145">預設值為 0.05。</span><span class="sxs-lookup"><span data-stu-id="ec53c-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-147">float</span><span class="sxs-lookup"><span data-stu-id="ec53c-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-148">預設值為 0.10。</span><span class="sxs-lookup"><span data-stu-id="ec53c-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-150">float</span><span class="sxs-lookup"><span data-stu-id="ec53c-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-151">預設值為 12。</span><span class="sxs-lookup"><span data-stu-id="ec53c-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-153">float</span><span class="sxs-lookup"><span data-stu-id="ec53c-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-154">預設值為 7。</span><span class="sxs-lookup"><span data-stu-id="ec53c-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec53c-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-156">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-157">預設值為 5.00。</span><span class="sxs-lookup"><span data-stu-id="ec53c-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec53c-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="ec53c-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="ec53c-159">decimal(5,2)</span><span class="sxs-lookup"><span data-stu-id="ec53c-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ec53c-160">預設值為 10.00。</span><span class="sxs-lookup"><span data-stu-id="ec53c-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

