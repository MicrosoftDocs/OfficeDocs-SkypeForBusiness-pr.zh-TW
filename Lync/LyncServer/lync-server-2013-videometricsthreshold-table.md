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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="56a3f-102">Lync Server 2013 中的 VideoMetricsThreshold 表格</span><span class="sxs-lookup"><span data-stu-id="56a3f-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56a3f-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="56a3f-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="56a3f-104">VideoMetricsThreshold 表格包含與視頻通話搭配使用之經驗統計之品質的最佳和可接受的值。</span><span class="sxs-lookup"><span data-stu-id="56a3f-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56a3f-105"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="56a3f-106"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="56a3f-107"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="56a3f-108"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-110">int</span><span class="sxs-lookup"><span data-stu-id="56a3f-110">int</span></span></p></td>
<td><p><span data-ttu-id="56a3f-111">首選</span><span class="sxs-lookup"><span data-stu-id="56a3f-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="56a3f-112">所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="56a3f-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-114">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-115">預設值為0.05。</span><span class="sxs-lookup"><span data-stu-id="56a3f-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-117">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-118">預設值為0.10。</span><span class="sxs-lookup"><span data-stu-id="56a3f-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-120">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-121">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="56a3f-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-123">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-124">預設值為10.0。</span><span class="sxs-lookup"><span data-stu-id="56a3f-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-126">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="56a3f-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-127">預設值為12.0000。</span><span class="sxs-lookup"><span data-stu-id="56a3f-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-129">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="56a3f-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-130">預設值為7.0000。</span><span class="sxs-lookup"><span data-stu-id="56a3f-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-132">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-133">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="56a3f-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-135">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-136">預設值為 10.0/</span><span class="sxs-lookup"><span data-stu-id="56a3f-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-138">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-139">預設值為5.0。</span><span class="sxs-lookup"><span data-stu-id="56a3f-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-141">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-142">預設值為10.0。</span><span class="sxs-lookup"><span data-stu-id="56a3f-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-144">foat</span><span class="sxs-lookup"><span data-stu-id="56a3f-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-145">預設值為0.05。</span><span class="sxs-lookup"><span data-stu-id="56a3f-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-147">浮</span><span class="sxs-lookup"><span data-stu-id="56a3f-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-148">預設值為0.10。</span><span class="sxs-lookup"><span data-stu-id="56a3f-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-150">浮</span><span class="sxs-lookup"><span data-stu-id="56a3f-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-151">預設值為12。</span><span class="sxs-lookup"><span data-stu-id="56a3f-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-153">浮</span><span class="sxs-lookup"><span data-stu-id="56a3f-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-154">預設值為7。</span><span class="sxs-lookup"><span data-stu-id="56a3f-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56a3f-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-156">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-157">預設值為5.00。</span><span class="sxs-lookup"><span data-stu-id="56a3f-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56a3f-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="56a3f-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="56a3f-159">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="56a3f-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="56a3f-160">預設值為10.00。</span><span class="sxs-lookup"><span data-stu-id="56a3f-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

