---
title: Lync Server 2013： VideoStreamDetail view
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
ms.openlocfilehash: e9b6cc13721ff249d9f8bd8bc0c38260c4ca7f55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="7337c-102">Lync Server 2013 中的 VideoStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="7337c-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7337c-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="7337c-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="7337c-104">VideoStreamDetail View 儲存資料庫中每個影片資料流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="7337c-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="7337c-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="7337c-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7337c-106">欄</span><span class="sxs-lookup"><span data-stu-id="7337c-106">Column</span></span></th>
<th><span data-ttu-id="7337c-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="7337c-107">Data Type</span></span></th>
<th><span data-ttu-id="7337c-108">描述</span><span class="sxs-lookup"><span data-stu-id="7337c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7337c-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="7337c-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="7337c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="7337c-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="7337c-111">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="7337c-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="7337c-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="7337c-113">int</span><span class="sxs-lookup"><span data-stu-id="7337c-113">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-114">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="7337c-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="7337c-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="7337c-116">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-117">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="7337c-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="7337c-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="7337c-119">int</span><span class="sxs-lookup"><span data-stu-id="7337c-119">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-120">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="7337c-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="7337c-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="7337c-122">datetime</span><span class="sxs-lookup"><span data-stu-id="7337c-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="7337c-123">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="7337c-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="7337c-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="7337c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="7337c-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="7337c-126">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="7337c-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="7337c-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="7337c-128">int</span><span class="sxs-lookup"><span data-stu-id="7337c-128">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-129">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="7337c-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="7337c-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="7337c-131">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-132">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7337c-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="7337c-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="7337c-134">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-135">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7337c-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-136">Caller</span><span class="sxs-lookup"><span data-stu-id="7337c-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="7337c-137">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="7337c-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7337c-138">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="7337c-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-139">方</span><span class="sxs-lookup"><span data-stu-id="7337c-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="7337c-140">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="7337c-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="7337c-141">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="7337c-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="7337c-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="7337c-143">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-144">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="7337c-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="7337c-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="7337c-146">Smallint</span><span class="sxs-lookup"><span data-stu-id="7337c-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="7337c-147">發話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="7337c-147">Type of caller’s user agent.</span></span> <span data-ttu-id="7337c-148">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="7337c-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="7337c-150">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="7337c-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7337c-151">發話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="7337c-151">Category of caller’s user agent.</span></span> <span data-ttu-id="7337c-152">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="7337c-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="7337c-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="7337c-154">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-155">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="7337c-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="7337c-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="7337c-157">Smallint</span><span class="sxs-lookup"><span data-stu-id="7337c-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="7337c-158">被呼叫者之使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="7337c-158">Type of callee’s user agent.</span></span> <span data-ttu-id="7337c-159">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="7337c-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="7337c-161">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="7337c-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="7337c-162">被呼叫者之使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="7337c-162">Category of callee’s user agent.</span></span> <span data-ttu-id="7337c-163">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) 中的 Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="7337c-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="7337c-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="7337c-165">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-166">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="7337c-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="7337c-168">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-169">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="7337c-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="7337c-171">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-172">呼叫者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="7337c-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="7337c-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="7337c-174">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-175">受話者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="7337c-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="7337c-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="7337c-177">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-178">來電者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="7337c-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="7337c-180">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-181">受話者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="7337c-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="7337c-183">Smallint</span><span class="sxs-lookup"><span data-stu-id="7337c-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="7337c-184">來電者端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="7337c-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="7337c-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="7337c-186">Smallint</span><span class="sxs-lookup"><span data-stu-id="7337c-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="7337c-187">受話者端點的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="7337c-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="7337c-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="7337c-189">int</span><span class="sxs-lookup"><span data-stu-id="7337c-189">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-190">來電者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="7337c-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="7337c-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="7337c-192">int</span><span class="sxs-lookup"><span data-stu-id="7337c-192">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-193">受話者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="7337c-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="7337c-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="7337c-195">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-196">會指出來電者的系統是否在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="7337c-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="7337c-197">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="7337c-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="7337c-199">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-200">會指出受話者的系統是否正在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="7337c-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="7337c-201">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="7337c-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="7337c-203">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-204">媒體路徑的相關資訊，例如 direct 或中繼。</span><span class="sxs-lookup"><span data-stu-id="7337c-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="7337c-205">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="7337c-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="7337c-207">int</span><span class="sxs-lookup"><span data-stu-id="7337c-207">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-p109">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="7337c-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="7337c-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="7337c-211">int</span><span class="sxs-lookup"><span data-stu-id="7337c-211">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-p110">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="7337c-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-214">傳輸</span><span class="sxs-lookup"><span data-stu-id="7337c-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="7337c-215">int</span><span class="sxs-lookup"><span data-stu-id="7337c-215">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-216">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="7337c-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="7337c-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7337c-218">var (50) </span><span class="sxs-lookup"><span data-stu-id="7337c-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7337c-219">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7337c-219">IP address of the caller.</span></span> <span data-ttu-id="7337c-220">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="7337c-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="7337c-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="7337c-222">int</span><span class="sxs-lookup"><span data-stu-id="7337c-222">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-223">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="7337c-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="7337c-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="7337c-225">位</span><span class="sxs-lookup"><span data-stu-id="7337c-225">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-226">會指出來電者是否在組織網路內。</span><span class="sxs-lookup"><span data-stu-id="7337c-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="7337c-227">1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="7337c-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="7337c-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7337c-229">var (50) </span><span class="sxs-lookup"><span data-stu-id="7337c-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7337c-230">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7337c-230">IP address of the callee.</span></span> <span data-ttu-id="7337c-231">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="7337c-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="7337c-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="7337c-233">int</span><span class="sxs-lookup"><span data-stu-id="7337c-233">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-234">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="7337c-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="7337c-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="7337c-236">位</span><span class="sxs-lookup"><span data-stu-id="7337c-236">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-237">會指出來電者是否在組織網路內。1表示受話者位於商業網路內，0表示受話者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="7337c-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="7337c-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="7337c-239">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-240">來電者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="7337c-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="7337c-242">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-243">來電者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="7337c-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="7337c-245">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-246">被呼叫者之網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="7337c-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="7337c-248">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="7337c-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="7337c-249">被呼叫者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="7337c-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7337c-251">var (50) </span><span class="sxs-lookup"><span data-stu-id="7337c-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7337c-252">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7337c-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="7337c-253">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="7337c-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="7337c-255">int</span><span class="sxs-lookup"><span data-stu-id="7337c-255">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-256">呼叫者所使用 A/V Edge service 上的埠。</span><span class="sxs-lookup"><span data-stu-id="7337c-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="7337c-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="7337c-258">var (50) </span><span class="sxs-lookup"><span data-stu-id="7337c-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="7337c-259">被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="7337c-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="7337c-260">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="7337c-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="7337c-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="7337c-262">int</span><span class="sxs-lookup"><span data-stu-id="7337c-262">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-263">被呼叫者所使用 A/V Edge service 上的埠。</span><span class="sxs-lookup"><span data-stu-id="7337c-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="7337c-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="7337c-265">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-266">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="7337c-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="7337c-268">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-269">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="7337c-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7337c-271">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-272">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="7337c-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7337c-274">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-275">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="7337c-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="7337c-277">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-278">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="7337c-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="7337c-280">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-281">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="7337c-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7337c-283">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-284">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="7337c-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="7337c-286">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="7337c-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="7337c-287">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="7337c-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="7337c-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="7337c-289">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-290">來電者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="7337c-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="7337c-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="7337c-292">位</span><span class="sxs-lookup"><span data-stu-id="7337c-292">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-293">會指出呼叫者是否透過虛擬專用網路連接。</span><span class="sxs-lookup"><span data-stu-id="7337c-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="7337c-294">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="7337c-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="7337c-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="7337c-296">十進位 (18，) </span><span class="sxs-lookup"><span data-stu-id="7337c-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="7337c-297">呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="7337c-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="7337c-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="7337c-299">Tinyint</span><span class="sxs-lookup"><span data-stu-id="7337c-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7337c-300">被呼叫者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="7337c-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="7337c-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="7337c-302">位</span><span class="sxs-lookup"><span data-stu-id="7337c-302">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-303">會指出是否已透過虛擬專用網路連接被呼叫者。</span><span class="sxs-lookup"><span data-stu-id="7337c-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="7337c-304">1 是虛擬私人網路 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="7337c-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="7337c-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="7337c-306">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="7337c-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="7337c-307">受話者端點的網路連結速度 (以 bps) 為單位）。</span><span class="sxs-lookup"><span data-stu-id="7337c-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="7337c-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="7337c-309">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="7337c-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="7337c-310">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="7337c-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="7337c-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="7337c-312">int</span><span class="sxs-lookup"><span data-stu-id="7337c-312">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-313">針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="7337c-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="7337c-314">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="7337c-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="7337c-315">基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。</span><span class="sxs-lookup"><span data-stu-id="7337c-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="7337c-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="7337c-317">int</span><span class="sxs-lookup"><span data-stu-id="7337c-317">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-318">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="7337c-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="7337c-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="7337c-320">int</span><span class="sxs-lookup"><span data-stu-id="7337c-320">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-321">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="7337c-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-322">往返</span><span class="sxs-lookup"><span data-stu-id="7337c-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="7337c-323">int</span><span class="sxs-lookup"><span data-stu-id="7337c-323">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-324">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="7337c-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="7337c-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="7337c-326">int</span><span class="sxs-lookup"><span data-stu-id="7337c-326">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-327">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="7337c-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="7337c-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="7337c-329">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="7337c-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-330">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="7337c-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="7337c-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="7337c-332">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="7337c-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-333">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="7337c-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="7337c-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="7337c-335">int</span><span class="sxs-lookup"><span data-stu-id="7337c-335">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-336">影片的封包計數 (即時傳輸通訊協定，RTP) 。</span><span class="sxs-lookup"><span data-stu-id="7337c-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="7337c-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="7337c-338">int</span><span class="sxs-lookup"><span data-stu-id="7337c-338">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-339">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="7337c-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="7337c-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="7337c-341">int</span><span class="sxs-lookup"><span data-stu-id="7337c-341">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-342">用於通話的音訊編解碼器，從<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="7337c-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="7337c-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="7337c-344">char (9) </span><span class="sxs-lookup"><span data-stu-id="7337c-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="7337c-345">影片解析度（圖元寬度乘以圖元高度）。</span><span class="sxs-lookup"><span data-stu-id="7337c-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="7337c-346">報告為字串。</span><span class="sxs-lookup"><span data-stu-id="7337c-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="7337c-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7337c-348">int</span><span class="sxs-lookup"><span data-stu-id="7337c-348">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-349">視頻資料流程的平均位元速率。</span><span class="sxs-lookup"><span data-stu-id="7337c-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="7337c-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7337c-351">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="7337c-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-352">收到的影片的畫面速率。</span><span class="sxs-lookup"><span data-stu-id="7337c-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="7337c-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="7337c-354">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="7337c-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-355">傳送影片的畫面速率。</span><span class="sxs-lookup"><span data-stu-id="7337c-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="7337c-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="7337c-357">int</span><span class="sxs-lookup"><span data-stu-id="7337c-357">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-358">影片中的最大視頻位元速率。</span><span class="sxs-lookup"><span data-stu-id="7337c-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="7337c-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="7337c-360">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="7337c-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-361">視頻封包遺失的速率。</span><span class="sxs-lookup"><span data-stu-id="7337c-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="7337c-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="7337c-363">十進位 (9.4) </span><span class="sxs-lookup"><span data-stu-id="7337c-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-364">丟失之總影片框的百分比。</span><span class="sxs-lookup"><span data-stu-id="7337c-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="7337c-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="7337c-366">位</span><span class="sxs-lookup"><span data-stu-id="7337c-366">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-367">不會使用。</span><span class="sxs-lookup"><span data-stu-id="7337c-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="7337c-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="7337c-369">int</span><span class="sxs-lookup"><span data-stu-id="7337c-369">int</span></span></p></td>
<td><p><span data-ttu-id="7337c-370">為影片所分配的平均頻寬量。</span><span class="sxs-lookup"><span data-stu-id="7337c-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7337c-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="7337c-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="7337c-372">十進位 (9.4) </span><span class="sxs-lookup"><span data-stu-id="7337c-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="7337c-373">已遺失之總影片框的百分比。</span><span class="sxs-lookup"><span data-stu-id="7337c-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7337c-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="7337c-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="7337c-375">位</span><span class="sxs-lookup"><span data-stu-id="7337c-375">bit</span></span></p></td>
<td><p><span data-ttu-id="7337c-376">P-宣稱身分識別資訊的資料流程方向。</span><span class="sxs-lookup"><span data-stu-id="7337c-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="7337c-377">1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="7337c-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

