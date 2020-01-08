---
title: Lync Server 2013： VideoStreamDetail view
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="a77b7-102">Lync Server 2013 中的 [VideoStreamDetail] 視圖</span><span class="sxs-lookup"><span data-stu-id="a77b7-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a77b7-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a77b7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a77b7-104">[VideoStreamDetail] 視圖會儲存資料庫中每個影片資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b7-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="a77b7-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a77b7-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a77b7-106">左欄</span><span class="sxs-lookup"><span data-stu-id="a77b7-106">Column</span></span></th>
<th><span data-ttu-id="a77b7-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="a77b7-107">Data Type</span></span></th>
<th><span data-ttu-id="a77b7-108">描述</span><span class="sxs-lookup"><span data-stu-id="a77b7-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="a77b7-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a77b7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-111">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a77b7-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="a77b7-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="a77b7-113">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-113">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-114">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a77b7-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="a77b7-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="a77b7-116">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a77b7-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="a77b7-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="a77b7-119">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-119">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-120">媒體線中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="a77b7-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-121">開始</span><span class="sxs-lookup"><span data-stu-id="a77b7-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="a77b7-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-123">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="a77b7-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="a77b7-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a77b7-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="a77b7-126">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="a77b7-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="a77b7-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="a77b7-128">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-128">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-129">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="a77b7-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="a77b7-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="a77b7-131">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-132">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a77b7-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="a77b7-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="a77b7-134">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-135">被呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a77b7-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-136">呼叫</span><span class="sxs-lookup"><span data-stu-id="a77b7-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="a77b7-137">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="a77b7-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-138">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="a77b7-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-139">方</span><span class="sxs-lookup"><span data-stu-id="a77b7-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="a77b7-140">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="a77b7-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-141">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="a77b7-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="a77b7-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a77b7-143">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-144">來電者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="a77b7-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a77b7-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a77b7-146">Smallint</span><span class="sxs-lookup"><span data-stu-id="a77b7-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-147">呼叫者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="a77b7-147">Type of caller’s user agent.</span></span> <span data-ttu-id="a77b7-148">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a77b7-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a77b7-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a77b7-150">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="a77b7-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-151">呼叫者的使用者代理類別。</span><span class="sxs-lookup"><span data-stu-id="a77b7-151">Category of caller’s user agent.</span></span> <span data-ttu-id="a77b7-152">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="a77b7-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="a77b7-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a77b7-154">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-155">被呼叫者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="a77b7-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a77b7-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a77b7-157">Smallint</span><span class="sxs-lookup"><span data-stu-id="a77b7-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-158">被呼叫者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="a77b7-158">Type of callee’s user agent.</span></span> <span data-ttu-id="a77b7-159">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a77b7-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a77b7-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a77b7-161">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="a77b7-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-162">被呼叫者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="a77b7-162">Category of callee’s user agent.</span></span> <span data-ttu-id="a77b7-163">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="a77b7-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="a77b7-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-165">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-166">來電者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="a77b7-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-168">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-169">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="a77b7-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="a77b7-171">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-172">呼叫者終點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="a77b7-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="a77b7-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="a77b7-174">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-175">被呼叫者的端點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="a77b7-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="a77b7-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="a77b7-177">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-178">呼叫者終點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="a77b7-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="a77b7-180">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-181">被呼叫者的端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="a77b7-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="a77b7-183">Smallint</span><span class="sxs-lookup"><span data-stu-id="a77b7-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-184">呼叫者終點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="a77b7-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="a77b7-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="a77b7-186">Smallint</span><span class="sxs-lookup"><span data-stu-id="a77b7-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-187">被呼叫者的端點的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="a77b7-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="a77b7-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="a77b7-189">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-189">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-190">呼叫者終點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="a77b7-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="a77b7-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="a77b7-192">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-192">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-193">被呼叫者的端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="a77b7-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="a77b7-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="a77b7-195">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-196">指出呼叫者的系統在虛擬化環境中是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="a77b7-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="a77b7-197">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="a77b7-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="a77b7-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="a77b7-199">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-200">指出被呼叫者的系統是否正在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="a77b7-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="a77b7-201">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="a77b7-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="a77b7-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="a77b7-203">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-204">媒體路徑（例如直接或中繼）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b7-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="a77b7-205">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a77b7-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a77b7-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a77b7-207">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-207">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-208">針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b7-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="a77b7-209">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="a77b7-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="a77b7-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="a77b7-211">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-211">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-212">針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a77b7-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="a77b7-213">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="a77b7-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-214">傳輸</span><span class="sxs-lookup"><span data-stu-id="a77b7-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="a77b7-215">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-215">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-216">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="a77b7-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="a77b7-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a77b7-218">var （50）</span><span class="sxs-lookup"><span data-stu-id="a77b7-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-219">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a77b7-219">IP address of the caller.</span></span> <span data-ttu-id="a77b7-220">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="a77b7-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="a77b7-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="a77b7-222">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-222">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-223">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="a77b7-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="a77b7-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="a77b7-225">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-225">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-226">指出來電者是否在組織網路內。</span><span class="sxs-lookup"><span data-stu-id="a77b7-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="a77b7-227">1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="a77b7-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="a77b7-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a77b7-229">var （50）</span><span class="sxs-lookup"><span data-stu-id="a77b7-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-230">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a77b7-230">IP address of the callee.</span></span> <span data-ttu-id="a77b7-231">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="a77b7-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="a77b7-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="a77b7-233">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-233">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-234">被呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="a77b7-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="a77b7-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="a77b7-236">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-236">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-237">指出來電者是否在組織網路內。1代表被叫方是在商業網路內，0代表被叫方在網路以外。</span><span class="sxs-lookup"><span data-stu-id="a77b7-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="a77b7-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="a77b7-239">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-240">來電者的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="a77b7-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="a77b7-242">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-243">來電者網站之國家/地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="a77b7-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="a77b7-245">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-246">被呼叫者的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="a77b7-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="a77b7-248">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="a77b7-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-249">被呼叫者網站之國家/地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a77b7-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a77b7-251">var （50）</span><span class="sxs-lookup"><span data-stu-id="a77b7-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-252">呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a77b7-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="a77b7-253">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a77b7-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="a77b7-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a77b7-255">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-255">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-256">呼叫者使用的 A/V 邊緣服務上的埠。</span><span class="sxs-lookup"><span data-stu-id="a77b7-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="a77b7-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="a77b7-258">var （50）</span><span class="sxs-lookup"><span data-stu-id="a77b7-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-259">被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="a77b7-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="a77b7-260">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="a77b7-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="a77b7-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="a77b7-262">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-262">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-263">被呼叫者使用的 A/V 邊緣服務上的埠。</span><span class="sxs-lookup"><span data-stu-id="a77b7-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a77b7-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a77b7-265">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-266">來電者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="a77b7-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a77b7-268">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-269">來電者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a77b7-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a77b7-271">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-272">來電者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="a77b7-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a77b7-274">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-275">來電者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="a77b7-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="a77b7-277">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-278">被呼叫者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="a77b7-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="a77b7-280">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-281">被呼叫者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="a77b7-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a77b7-283">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-284">被呼叫者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="a77b7-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="a77b7-286">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="a77b7-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-287">被呼叫者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="a77b7-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="a77b7-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="a77b7-289">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-290">來電者的網路連線類型：0是 [有線]，1是 [無線]。</span><span class="sxs-lookup"><span data-stu-id="a77b7-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="a77b7-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="a77b7-292">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-292">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-293">指出呼叫者是否已經由虛擬專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="a77b7-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="a77b7-294">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a77b7-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="a77b7-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="a77b7-296">小數（18，）</span><span class="sxs-lookup"><span data-stu-id="a77b7-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-297">呼叫者端點的網路連結速度，以 bps 表示。</span><span class="sxs-lookup"><span data-stu-id="a77b7-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="a77b7-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="a77b7-299">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a77b7-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="a77b7-300">被呼叫者的網路連線類型：0是 [有線]，1是 [無線]。</span><span class="sxs-lookup"><span data-stu-id="a77b7-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="a77b7-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="a77b7-302">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-302">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-303">指出被呼叫者是否已經由虛擬私人網路絡進行連線。</span><span class="sxs-lookup"><span data-stu-id="a77b7-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="a77b7-304">1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="a77b7-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="a77b7-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="a77b7-306">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="a77b7-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-307">被呼叫者的端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="a77b7-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="a77b7-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="a77b7-309">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="a77b7-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-310">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="a77b7-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="a77b7-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-312">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-312">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-313">在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="a77b7-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="a77b7-314">這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="a77b7-315">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。</span><span class="sxs-lookup"><span data-stu-id="a77b7-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="a77b7-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="a77b7-317">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-317">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-318">從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="a77b7-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="a77b7-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="a77b7-320">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-320">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-321">通話期間網路抖動的最大值。</span><span class="sxs-lookup"><span data-stu-id="a77b7-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-322">環路</span><span class="sxs-lookup"><span data-stu-id="a77b7-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="a77b7-323">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-323">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-324">從 RTCP 統計資料中往返的時間。</span><span class="sxs-lookup"><span data-stu-id="a77b7-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="a77b7-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="a77b7-326">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-326">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-327">音訊資料流程的最大往返行程時間。</span><span class="sxs-lookup"><span data-stu-id="a77b7-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="a77b7-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="a77b7-329">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-330">通話期間的平均資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="a77b7-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="a77b7-332">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-333">通話期間觀察到的最大資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="a77b7-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="a77b7-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="a77b7-335">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-335">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-336">影片串流的資料包計數（即時傳輸通訊協定、RTP）。</span><span class="sxs-lookup"><span data-stu-id="a77b7-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="a77b7-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="a77b7-338">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-338">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-339">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="a77b7-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="a77b7-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="a77b7-341">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-341">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-342">用於通話的音訊編解碼器，<a href="lync-server-2013-payloaddescription-table.md">在 Lync Server 2013 的 PayloadDescription 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="a77b7-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="a77b7-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="a77b7-344">char （9）</span><span class="sxs-lookup"><span data-stu-id="a77b7-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-345">以圖元為單位的影片解析度，以圖元為單位的寬度乘以圖元高度。</span><span class="sxs-lookup"><span data-stu-id="a77b7-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="a77b7-346">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="a77b7-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="a77b7-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="a77b7-348">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-348">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-349">影片串流的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="a77b7-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="a77b7-351">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-352">收到的視頻畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="a77b7-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="a77b7-354">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-355">已傳送的視頻畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="a77b7-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="a77b7-357">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-357">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-358">影片會話期間的最大視頻位元速率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="a77b7-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="a77b7-360">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-361">視頻資料包遺失的頻率。</span><span class="sxs-lookup"><span data-stu-id="a77b7-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="a77b7-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="a77b7-363">decimal （9.4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-364">遺失的視頻畫面總百分比。</span><span class="sxs-lookup"><span data-stu-id="a77b7-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="a77b7-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="a77b7-366">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-366">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-367">不使用。</span><span class="sxs-lookup"><span data-stu-id="a77b7-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="a77b7-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="a77b7-369">int</span><span class="sxs-lookup"><span data-stu-id="a77b7-369">int</span></span></p></td>
<td><p><span data-ttu-id="a77b7-370">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="a77b7-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a77b7-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="a77b7-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="a77b7-372">decimal （9.4）</span><span class="sxs-lookup"><span data-stu-id="a77b7-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="a77b7-373">遺失的視頻畫面總百分比。</span><span class="sxs-lookup"><span data-stu-id="a77b7-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a77b7-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="a77b7-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="a77b7-375">稍微</span><span class="sxs-lookup"><span data-stu-id="a77b7-375">bit</span></span></p></td>
<td><p><span data-ttu-id="a77b7-376">P 斷言身分識別資訊的資料流程方向。</span><span class="sxs-lookup"><span data-stu-id="a77b7-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="a77b7-377">1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="a77b7-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

