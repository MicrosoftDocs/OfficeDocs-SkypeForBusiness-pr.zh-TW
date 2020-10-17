---
title: Lync Server 2013： VideoStreamDetail view
description: Lync Server 2013： VideoStreamDetail view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567969"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="c001f-103">Lync Server 2013 中的 VideoStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="c001f-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c001f-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c001f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c001f-105">VideoStreamDetail View 儲存資料庫中每個影片資料流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="c001f-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="c001f-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="c001f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c001f-107">欄</span><span class="sxs-lookup"><span data-stu-id="c001f-107">Column</span></span></th>
<th><span data-ttu-id="c001f-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="c001f-108">Data Type</span></span></th>
<th><span data-ttu-id="c001f-109">描述</span><span class="sxs-lookup"><span data-stu-id="c001f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c001f-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="c001f-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="c001f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c001f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c001f-112">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c001f-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="c001f-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="c001f-114">int</span><span class="sxs-lookup"><span data-stu-id="c001f-114">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-115">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c001f-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="c001f-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="c001f-117">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-118">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c001f-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="c001f-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="c001f-120">int</span><span class="sxs-lookup"><span data-stu-id="c001f-120">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-121">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="c001f-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="c001f-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="c001f-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c001f-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="c001f-124">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="c001f-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="c001f-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="c001f-126">datetime</span><span class="sxs-lookup"><span data-stu-id="c001f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="c001f-127">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="c001f-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="c001f-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="c001f-129">int</span><span class="sxs-lookup"><span data-stu-id="c001f-129">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-130">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="c001f-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="c001f-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="c001f-132">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-133">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c001f-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="c001f-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="c001f-135">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-136">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c001f-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-137">Caller</span><span class="sxs-lookup"><span data-stu-id="c001f-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="c001f-138">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c001f-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c001f-139">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="c001f-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-140">方</span><span class="sxs-lookup"><span data-stu-id="c001f-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="c001f-141">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c001f-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c001f-142">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="c001f-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="c001f-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c001f-144">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-145">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="c001f-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c001f-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c001f-147">Smallint</span><span class="sxs-lookup"><span data-stu-id="c001f-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="c001f-148">發話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="c001f-148">Type of caller’s user agent.</span></span> <span data-ttu-id="c001f-149">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c001f-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c001f-151">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="c001f-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c001f-152">發話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="c001f-152">Category of caller’s user agent.</span></span> <span data-ttu-id="c001f-153">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="c001f-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c001f-155">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-156">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="c001f-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c001f-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c001f-158">Smallint</span><span class="sxs-lookup"><span data-stu-id="c001f-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="c001f-159">被呼叫者之使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="c001f-159">Type of callee’s user agent.</span></span> <span data-ttu-id="c001f-160">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c001f-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c001f-162">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="c001f-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c001f-163">被呼叫者之使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="c001f-163">Category of callee’s user agent.</span></span> <span data-ttu-id="c001f-164">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) 中的 Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c001f-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c001f-166">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-167">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="c001f-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c001f-169">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-170">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="c001f-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="c001f-172">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-173">呼叫者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="c001f-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="c001f-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="c001f-175">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-176">受話者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="c001f-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="c001f-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="c001f-178">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-179">來電者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="c001f-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="c001f-181">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-182">受話者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c001f-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c001f-184">Smallint</span><span class="sxs-lookup"><span data-stu-id="c001f-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="c001f-185">來電者端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="c001f-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c001f-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c001f-187">Smallint</span><span class="sxs-lookup"><span data-stu-id="c001f-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="c001f-188">受話者端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="c001f-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c001f-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c001f-190">int</span><span class="sxs-lookup"><span data-stu-id="c001f-190">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-191">來電者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="c001f-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c001f-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c001f-193">int</span><span class="sxs-lookup"><span data-stu-id="c001f-193">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-194">受話者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="c001f-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c001f-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c001f-196">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-197">會指出來電者的系統是否在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="c001f-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c001f-198">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c001f-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c001f-200">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-201">會指出受話者的系統是否正在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="c001f-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c001f-202">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="c001f-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="c001f-204">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-205">媒體路徑的相關資訊，例如 direct 或中繼。</span><span class="sxs-lookup"><span data-stu-id="c001f-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="c001f-206">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c001f-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c001f-208">int</span><span class="sxs-lookup"><span data-stu-id="c001f-208">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-p109">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="c001f-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c001f-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c001f-212">int</span><span class="sxs-lookup"><span data-stu-id="c001f-212">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-p110">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="c001f-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-215">傳輸</span><span class="sxs-lookup"><span data-stu-id="c001f-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="c001f-216">int</span><span class="sxs-lookup"><span data-stu-id="c001f-216">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-217">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="c001f-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="c001f-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c001f-219">var (50) </span><span class="sxs-lookup"><span data-stu-id="c001f-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c001f-220">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c001f-220">IP address of the caller.</span></span> <span data-ttu-id="c001f-221">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c001f-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="c001f-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="c001f-223">int</span><span class="sxs-lookup"><span data-stu-id="c001f-223">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-224">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="c001f-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="c001f-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="c001f-226">位</span><span class="sxs-lookup"><span data-stu-id="c001f-226">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-227">會指出來電者是否在組織網路內。</span><span class="sxs-lookup"><span data-stu-id="c001f-227">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="c001f-228">1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="c001f-228">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="c001f-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c001f-230">var (50) </span><span class="sxs-lookup"><span data-stu-id="c001f-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c001f-231">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c001f-231">IP address of the callee.</span></span> <span data-ttu-id="c001f-232">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="c001f-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="c001f-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="c001f-234">int</span><span class="sxs-lookup"><span data-stu-id="c001f-234">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-235">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="c001f-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="c001f-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="c001f-237">位</span><span class="sxs-lookup"><span data-stu-id="c001f-237">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-238">會指出來電者是否在組織網路內。1表示受話者位於商業網路內，0表示受話者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="c001f-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="c001f-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="c001f-240">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-241">來電者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="c001f-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="c001f-243">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-244">來電者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="c001f-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="c001f-246">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-247">被呼叫者之網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="c001f-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="c001f-249">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c001f-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c001f-250">被呼叫者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c001f-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c001f-252">var (50) </span><span class="sxs-lookup"><span data-stu-id="c001f-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c001f-253">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c001f-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="c001f-254">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="c001f-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c001f-256">int</span><span class="sxs-lookup"><span data-stu-id="c001f-256">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-257">呼叫者所使用 A/V Edge service 上的埠。</span><span class="sxs-lookup"><span data-stu-id="c001f-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c001f-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c001f-259">var (50) </span><span class="sxs-lookup"><span data-stu-id="c001f-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c001f-260">被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="c001f-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="c001f-261">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="c001f-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c001f-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c001f-263">int</span><span class="sxs-lookup"><span data-stu-id="c001f-263">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-264">被呼叫者所使用 A/V Edge service 上的埠。</span><span class="sxs-lookup"><span data-stu-id="c001f-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c001f-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c001f-266">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-267">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="c001f-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c001f-269">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-270">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c001f-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c001f-272">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-273">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c001f-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c001f-275">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-276">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c001f-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c001f-278">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-279">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="c001f-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c001f-281">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-282">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c001f-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c001f-284">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-285">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c001f-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c001f-287">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c001f-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c001f-288">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="c001f-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c001f-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c001f-290">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-291">來電者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="c001f-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="c001f-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="c001f-293">位</span><span class="sxs-lookup"><span data-stu-id="c001f-293">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-294">會指出呼叫者是否透過虛擬專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="c001f-294">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="c001f-295">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="c001f-295">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c001f-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c001f-297">十進位 (18，) </span><span class="sxs-lookup"><span data-stu-id="c001f-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="c001f-298">呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="c001f-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c001f-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c001f-300">Tinyint</span><span class="sxs-lookup"><span data-stu-id="c001f-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c001f-301">被呼叫者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="c001f-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="c001f-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="c001f-303">位</span><span class="sxs-lookup"><span data-stu-id="c001f-303">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-304">會指出是否已透過虛擬專用網路連接被呼叫者。</span><span class="sxs-lookup"><span data-stu-id="c001f-304">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="c001f-305">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="c001f-305">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c001f-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c001f-307">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="c001f-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c001f-308">受話者端點的網路連結速度 (以 bps) 為單位）。</span><span class="sxs-lookup"><span data-stu-id="c001f-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="c001f-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="c001f-310">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="c001f-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c001f-311">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="c001f-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="c001f-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="c001f-313">int</span><span class="sxs-lookup"><span data-stu-id="c001f-313">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-314">針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="c001f-314">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="c001f-315">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="c001f-315">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="c001f-316">基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="c001f-316">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="c001f-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="c001f-318">int</span><span class="sxs-lookup"><span data-stu-id="c001f-318">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-319">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="c001f-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="c001f-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="c001f-321">int</span><span class="sxs-lookup"><span data-stu-id="c001f-321">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-322">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="c001f-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-323">往返</span><span class="sxs-lookup"><span data-stu-id="c001f-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="c001f-324">int</span><span class="sxs-lookup"><span data-stu-id="c001f-324">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-325">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="c001f-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="c001f-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="c001f-327">int</span><span class="sxs-lookup"><span data-stu-id="c001f-327">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-328">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="c001f-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c001f-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c001f-330">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="c001f-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-331">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="c001f-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="c001f-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="c001f-333">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="c001f-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-334">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="c001f-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="c001f-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="c001f-336">int</span><span class="sxs-lookup"><span data-stu-id="c001f-336">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-337">影片的封包計數 (即時傳輸通訊協定，RTP) 。</span><span class="sxs-lookup"><span data-stu-id="c001f-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-338">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="c001f-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="c001f-339">int</span><span class="sxs-lookup"><span data-stu-id="c001f-339">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-340">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="c001f-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="c001f-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="c001f-342">int</span><span class="sxs-lookup"><span data-stu-id="c001f-342">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-343">用於通話的音訊編解碼器，從 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="c001f-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="c001f-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="c001f-345">char (9) </span><span class="sxs-lookup"><span data-stu-id="c001f-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="c001f-346">影片解析度（圖元寬度乘以圖元高度）。</span><span class="sxs-lookup"><span data-stu-id="c001f-346">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="c001f-347">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="c001f-347">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="c001f-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c001f-349">int</span><span class="sxs-lookup"><span data-stu-id="c001f-349">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-350">視頻資料流程的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="c001f-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="c001f-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c001f-352">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="c001f-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-353">收到的影片的畫面速率。</span><span class="sxs-lookup"><span data-stu-id="c001f-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="c001f-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c001f-355">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="c001f-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-356">傳送影片的畫面速率。</span><span class="sxs-lookup"><span data-stu-id="c001f-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="c001f-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="c001f-358">int</span><span class="sxs-lookup"><span data-stu-id="c001f-358">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-359">影片中的最大視頻位元速率。</span><span class="sxs-lookup"><span data-stu-id="c001f-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c001f-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c001f-361">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="c001f-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-362">視頻封包遺失的速率。</span><span class="sxs-lookup"><span data-stu-id="c001f-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="c001f-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="c001f-364">十進位 (9.4) </span><span class="sxs-lookup"><span data-stu-id="c001f-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-365">丟失之總影片框的百分比。</span><span class="sxs-lookup"><span data-stu-id="c001f-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="c001f-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="c001f-367">位</span><span class="sxs-lookup"><span data-stu-id="c001f-367">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-368">不會使用。</span><span class="sxs-lookup"><span data-stu-id="c001f-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="c001f-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="c001f-370">int</span><span class="sxs-lookup"><span data-stu-id="c001f-370">int</span></span></p></td>
<td><p><span data-ttu-id="c001f-371">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="c001f-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c001f-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="c001f-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="c001f-373">十進位 (9.4) </span><span class="sxs-lookup"><span data-stu-id="c001f-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="c001f-374">已遺失之總影片框的百分比。</span><span class="sxs-lookup"><span data-stu-id="c001f-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c001f-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="c001f-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="c001f-376">位</span><span class="sxs-lookup"><span data-stu-id="c001f-376">bit</span></span></p></td>
<td><p><span data-ttu-id="c001f-377">P-宣稱身分識別資訊的資料流程方向。</span><span class="sxs-lookup"><span data-stu-id="c001f-377">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="c001f-378">1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="c001f-378">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

