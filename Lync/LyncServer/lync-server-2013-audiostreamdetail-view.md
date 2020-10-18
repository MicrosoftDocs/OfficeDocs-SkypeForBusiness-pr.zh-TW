---
title: Lync Server 2013： AudioStreamDetail view
description: Lync Server 2013： AudioStreamDetail view。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573049"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="4428b-103">Lync Server 2013 中的 AudioStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="4428b-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4428b-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="4428b-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="4428b-105">AudioStreamDetail View 儲存資料庫中每個音訊資料流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="4428b-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="4428b-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4428b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4428b-107">欄</span><span class="sxs-lookup"><span data-stu-id="4428b-107">Column</span></span></th>
<th><span data-ttu-id="4428b-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="4428b-108">Data Type</span></span></th>
<th><span data-ttu-id="4428b-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="4428b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4428b-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="4428b-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="4428b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="4428b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="4428b-112">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="4428b-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="4428b-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="4428b-114">int</span><span class="sxs-lookup"><span data-stu-id="4428b-114">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-115">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="4428b-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="4428b-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="4428b-117">int</span><span class="sxs-lookup"><span data-stu-id="4428b-117">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-118">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="4428b-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="4428b-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="4428b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="4428b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="4428b-121">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="4428b-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="4428b-123">datetime</span><span class="sxs-lookup"><span data-stu-id="4428b-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="4428b-124">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="4428b-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="4428b-126">位</span><span class="sxs-lookup"><span data-stu-id="4428b-126">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-127">對話方塊類別：0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="4428b-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="4428b-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="4428b-129">位</span><span class="sxs-lookup"><span data-stu-id="4428b-129">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-130">指示是否略過呼叫的旗標。</span><span class="sxs-lookup"><span data-stu-id="4428b-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="4428b-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="4428b-132">int</span><span class="sxs-lookup"><span data-stu-id="4428b-132">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-133">如果有的話，則表示即使旁路 IDs 相符也不會略過通話的原因。</span><span class="sxs-lookup"><span data-stu-id="4428b-133">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="4428b-134">只定義了一個值：</span><span class="sxs-lookup"><span data-stu-id="4428b-134">Only one value is defined:</span></span></p>
<p><span data-ttu-id="4428b-135">0x0001 –預設網路介面卡的未知旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="4428b-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="4428b-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="4428b-137">int</span><span class="sxs-lookup"><span data-stu-id="4428b-137">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-138">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="4428b-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="4428b-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="4428b-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-141">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4428b-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="4428b-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="4428b-143">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-144">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4428b-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-145">Caller</span><span class="sxs-lookup"><span data-stu-id="4428b-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="4428b-146">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="4428b-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4428b-147">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="4428b-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-148">方</span><span class="sxs-lookup"><span data-stu-id="4428b-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="4428b-149">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="4428b-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="4428b-150">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="4428b-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="4428b-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4428b-152">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-153">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="4428b-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4428b-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4428b-155">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-156">來電者使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="4428b-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="4428b-157">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4428b-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4428b-159">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="4428b-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4428b-160">來電者使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="4428b-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="4428b-161">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="4428b-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="4428b-163">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-164">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="4428b-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="4428b-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="4428b-166">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-167">被呼叫者之使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="4428b-167">Type of callee’s user agent.</span></span> <span data-ttu-id="4428b-168">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="4428b-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="4428b-170">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="4428b-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="4428b-171">被呼叫者之使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="4428b-171">Category of callee’s user agent.</span></span> <span data-ttu-id="4428b-172">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) 中的 Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="4428b-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4428b-174">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-175">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="4428b-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="4428b-177">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-178">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="4428b-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-180">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-181">呼叫者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="4428b-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="4428b-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-183">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-184">受話者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="4428b-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="4428b-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="4428b-186">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-187">來電者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="4428b-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="4428b-189">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-190">受話者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4428b-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4428b-192">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-193">來電者端點中的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="4428b-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="4428b-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="4428b-195">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-196">受話者端點中的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="4428b-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="4428b-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4428b-198">int</span><span class="sxs-lookup"><span data-stu-id="4428b-198">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-199">來電者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="4428b-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="4428b-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="4428b-201">int</span><span class="sxs-lookup"><span data-stu-id="4428b-201">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-202">受話者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="4428b-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4428b-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4428b-204">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-205">會指出來電者的系統是否在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="4428b-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4428b-206">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="4428b-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="4428b-208">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-209">會指出受話者的系統是否正在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="4428b-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="4428b-210">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="4428b-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4428b-212">相關機碼。</span><span class="sxs-lookup"><span data-stu-id="4428b-212">Correlation key.</span></span> <span data-ttu-id="4428b-213">從 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="4428b-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="4428b-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="4428b-215">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-216">媒體路徑的相關資訊，例如 direct 或中繼。</span><span class="sxs-lookup"><span data-stu-id="4428b-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="4428b-217">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4428b-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4428b-219">int</span><span class="sxs-lookup"><span data-stu-id="4428b-219">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-p111">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="4428b-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="4428b-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="4428b-223">int</span><span class="sxs-lookup"><span data-stu-id="4428b-223">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-p112">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="4428b-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-226">傳輸</span><span class="sxs-lookup"><span data-stu-id="4428b-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="4428b-227">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-228">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="4428b-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="4428b-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4428b-230">var (50) </span><span class="sxs-lookup"><span data-stu-id="4428b-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4428b-231">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4428b-231">IP address of the caller.</span></span> <span data-ttu-id="4428b-232">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="4428b-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="4428b-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="4428b-234">int</span><span class="sxs-lookup"><span data-stu-id="4428b-234">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-235">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="4428b-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="4428b-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="4428b-237">位</span><span class="sxs-lookup"><span data-stu-id="4428b-237">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-238">會指出來電者是否在間隔網路內：1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="4428b-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="4428b-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4428b-240">var (50) </span><span class="sxs-lookup"><span data-stu-id="4428b-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4428b-241">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4428b-241">IP address of the callee.</span></span> <span data-ttu-id="4428b-242">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="4428b-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="4428b-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="4428b-244">int</span><span class="sxs-lookup"><span data-stu-id="4428b-244">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-245">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="4428b-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="4428b-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="4428b-247">位</span><span class="sxs-lookup"><span data-stu-id="4428b-247">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-248">會指出受話者是否在間隔網路內：1表示受話者位於商業網路內，0表示受話者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="4428b-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="4428b-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="4428b-250">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-251">來電者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="4428b-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="4428b-253">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-254">來電者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="4428b-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="4428b-256">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-257">被呼叫者之網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="4428b-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="4428b-259">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="4428b-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="4428b-260">被呼叫者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4428b-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4428b-262">var (50) </span><span class="sxs-lookup"><span data-stu-id="4428b-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4428b-263">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4428b-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="4428b-264">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="4428b-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4428b-266">int</span><span class="sxs-lookup"><span data-stu-id="4428b-266">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-267">發話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="4428b-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="4428b-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="4428b-269">var (50) </span><span class="sxs-lookup"><span data-stu-id="4428b-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="4428b-270">被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="4428b-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="4428b-271">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="4428b-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="4428b-273">int</span><span class="sxs-lookup"><span data-stu-id="4428b-273">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-274">受話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="4428b-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4428b-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4428b-276">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-277">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="4428b-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4428b-279">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-280">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4428b-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4428b-282">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-283">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="4428b-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="4428b-285">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-286">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="4428b-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="4428b-288">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-289">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="4428b-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="4428b-291">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-292">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="4428b-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4428b-294">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-295">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="4428b-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="4428b-297">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="4428b-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="4428b-298">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4428b-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4428b-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4428b-300">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-301">來電者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="4428b-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="4428b-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="4428b-303">位</span><span class="sxs-lookup"><span data-stu-id="4428b-303">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-304">會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="4428b-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4428b-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4428b-306">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="4428b-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4428b-307">呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="4428b-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="4428b-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="4428b-309">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-310">被呼叫者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="4428b-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="4428b-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="4428b-312">位</span><span class="sxs-lookup"><span data-stu-id="4428b-312">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-313">會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="4428b-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="4428b-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="4428b-315">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="4428b-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="4428b-316">被呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="4428b-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="4428b-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-318">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-319">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="4428b-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="4428b-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="4428b-321">int</span><span class="sxs-lookup"><span data-stu-id="4428b-321">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-322">針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="4428b-322">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="4428b-323">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="4428b-323">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="4428b-324">這基本上是傳送資料流程可以採用限制頻寬估計所強加限制的最大頻寬</span><span class="sxs-lookup"><span data-stu-id="4428b-324">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="4428b-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="4428b-326">int</span><span class="sxs-lookup"><span data-stu-id="4428b-326">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-327">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="4428b-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="4428b-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="4428b-329">int</span><span class="sxs-lookup"><span data-stu-id="4428b-329">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-330">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="4428b-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="4428b-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-332">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="4428b-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4428b-333">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="4428b-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="4428b-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="4428b-335">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="4428b-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="4428b-336">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="4428b-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="4428b-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="4428b-338">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="4428b-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4428b-339">通話期間的猝量遺失期間的封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="4428b-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="4428b-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="4428b-341">int</span><span class="sxs-lookup"><span data-stu-id="4428b-341">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-342">通話期間的猝量遺失期間的封包遺失平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="4428b-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="4428b-344">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="4428b-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="4428b-345">封包遺失失敗之間的平均封包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="4428b-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="4428b-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="4428b-347">int</span><span class="sxs-lookup"><span data-stu-id="4428b-347">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-348">封包遺失的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="4428b-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="4428b-350">int</span><span class="sxs-lookup"><span data-stu-id="4428b-350">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-351">音訊資料流程的封包計數。</span><span class="sxs-lookup"><span data-stu-id="4428b-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-352">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="4428b-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="4428b-353">int</span><span class="sxs-lookup"><span data-stu-id="4428b-353">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-354">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="4428b-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-356">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-357">整個通話的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="4428b-357">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="4428b-358">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="4428b-358">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="4428b-359">此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。</span><span class="sxs-lookup"><span data-stu-id="4428b-359">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="4428b-360">可接受的品質應小於0.5。</span><span class="sxs-lookup"><span data-stu-id="4428b-360">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="4428b-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="4428b-362">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-363">通話期間的最大網路 MOS 降級。</span><span class="sxs-lookup"><span data-stu-id="4428b-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-365">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-366">抖動導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="4428b-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-368">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-369">封包遺失導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="4428b-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="4428b-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="4428b-371">int</span><span class="sxs-lookup"><span data-stu-id="4428b-371">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-372">用於通話的音訊編解碼器，從 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="4428b-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="4428b-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-374">int</span><span class="sxs-lookup"><span data-stu-id="4428b-374">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-375">音訊資料流程的取樣速率。</span><span class="sxs-lookup"><span data-stu-id="4428b-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-377">int</span><span class="sxs-lookup"><span data-stu-id="4428b-377">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-378">來電者所傳送之音訊的後續類比增益控制音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-378">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="4428b-379">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-379">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-380">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-380">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="4428b-381">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-381">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-383">int</span><span class="sxs-lookup"><span data-stu-id="4428b-383">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-384">來電者接收之音訊的音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-384">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="4428b-385">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-385">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-386">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-386">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="4428b-387">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-387">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-389">int</span><span class="sxs-lookup"><span data-stu-id="4428b-389">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-390">來電者所傳送之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-390">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="4428b-391">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-391">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-392">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-392">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="4428b-393">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-393">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-395">int</span><span class="sxs-lookup"><span data-stu-id="4428b-395">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-396">來電者接收之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-396">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="4428b-397">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-397">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-398">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-398">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="4428b-399">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-399">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="4428b-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="4428b-401">int</span><span class="sxs-lookup"><span data-stu-id="4428b-401">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-402">呼叫來電者的回顯回復功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="4428b-402">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="4428b-403">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="4428b-403">The unit for this metric is dB.</span></span> <span data-ttu-id="4428b-404">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="4428b-404">Lower values represent less echo.</span></span> <span data-ttu-id="4428b-405">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-405">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4428b-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-407">int</span><span class="sxs-lookup"><span data-stu-id="4428b-407">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-408">呼叫者的喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="4428b-408">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="4428b-409">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="4428b-409">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="4428b-410">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="4428b-410">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4428b-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-412">int</span><span class="sxs-lookup"><span data-stu-id="4428b-412">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-413">來電者的擴音器 capture 每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="4428b-413">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="4428b-414">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="4428b-414">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="4428b-415">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="4428b-415">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="4428b-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="4428b-417">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-418">來電者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="4428b-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="4428b-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="4428b-420">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-421">來電者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="4428b-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="4428b-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="4428b-423">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-424">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="4428b-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="4428b-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="4428b-426">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-427">呼叫者的最後20秒內，平均來電者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="4428b-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="4428b-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="4428b-429">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-430">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="4428b-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="4428b-431">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="4428b-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="4428b-433">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-434">來電者的 echo 事件原因。</span><span class="sxs-lookup"><span data-stu-id="4428b-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="4428b-435">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="4428b-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="4428b-437">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-438">在來電者的麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="4428b-438">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="4428b-439">如果使用的是耳機，則值應該很低。</span><span class="sxs-lookup"><span data-stu-id="4428b-439">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="4428b-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="4428b-441">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-442">在來電者的傳送資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="4428b-442">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="4428b-443">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="4428b-443">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-445">int</span><span class="sxs-lookup"><span data-stu-id="4428b-445">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-446">從來電者音訊的閘道，在轉送伺服器上接收信號等級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4428b-446">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="4428b-447">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-447">The unit of this metric is dBoV.</span></span> <span data-ttu-id="4428b-448">為了獲得良好的品質，可接受的範圍應為-30 到-18 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-448">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-450">int</span><span class="sxs-lookup"><span data-stu-id="4428b-450">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-451">從來電者的音訊的閘道處接收轉送伺服器上的信號等級。</span><span class="sxs-lookup"><span data-stu-id="4428b-451">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="4428b-452">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4428b-452">This applies only to the Mediation Server.</span></span> <span data-ttu-id="4428b-453">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-453">The unit of this metric is dBoV.</span></span> <span data-ttu-id="4428b-454">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-454">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="4428b-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="4428b-456">int</span><span class="sxs-lookup"><span data-stu-id="4428b-456">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-457">在套用至來電者音訊的轉送伺服器端 (AGC) 自動取得控制權。</span><span class="sxs-lookup"><span data-stu-id="4428b-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="4428b-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="4428b-459">float</span><span class="sxs-lookup"><span data-stu-id="4428b-459">float</span></span></p></td>
<td><p><span data-ttu-id="4428b-460">對來電者傳入的信號的根平均方 (RMS) ，最多可達前30秒的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4428b-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-462">int</span><span class="sxs-lookup"><span data-stu-id="4428b-462">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-463">代表被呼叫者所傳送之音訊的後續類比增益控制音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="4428b-463">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="4428b-464">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-464">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-465">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-465">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="4428b-466">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-466">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-468">int</span><span class="sxs-lookup"><span data-stu-id="4428b-468">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-469">被呼叫者所接收之音訊的音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-469">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="4428b-470">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-470">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-471">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-471">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="4428b-472">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-472">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-474">int</span><span class="sxs-lookup"><span data-stu-id="4428b-474">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-475">受話者所傳送之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-475">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="4428b-476">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-476">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-477">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-477">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="4428b-478">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-478">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-480">int</span><span class="sxs-lookup"><span data-stu-id="4428b-480">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-481">受話者接收之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="4428b-481">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="4428b-482">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-482">The unit for this metric is dBmo.</span></span> <span data-ttu-id="4428b-483">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="4428b-483">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="4428b-484">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-484">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="4428b-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="4428b-486">int</span><span class="sxs-lookup"><span data-stu-id="4428b-486">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-487">被呼叫者的回顯傳回遺失增強功能。</span><span class="sxs-lookup"><span data-stu-id="4428b-487">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="4428b-488">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="4428b-488">The unit for this metric is dB.</span></span> <span data-ttu-id="4428b-489">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="4428b-489">Lower values represent less echo.</span></span> <span data-ttu-id="4428b-490">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="4428b-490">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4428b-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-492">int</span><span class="sxs-lookup"><span data-stu-id="4428b-492">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-493">被呼叫者的喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="4428b-493">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="4428b-494">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="4428b-494">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="4428b-495">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="4428b-495">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="4428b-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="4428b-497">int</span><span class="sxs-lookup"><span data-stu-id="4428b-497">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-498">受話者麥克風捕獲每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="4428b-498">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="4428b-499">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="4428b-499">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="4428b-500">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="4428b-500">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="4428b-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="4428b-502">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-503">受話者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="4428b-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="4428b-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="4428b-505">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-506">受話者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="4428b-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="4428b-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="4428b-508">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-509">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="4428b-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="4428b-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="4428b-511">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-512">通話的最後20秒內，被呼叫者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="4428b-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="4428b-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="4428b-514">Smallint</span><span class="sxs-lookup"><span data-stu-id="4428b-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="4428b-515">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="4428b-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="4428b-516">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="4428b-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="4428b-518">Tinyint</span><span class="sxs-lookup"><span data-stu-id="4428b-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="4428b-519">被呼叫者的 echo 事件原因。</span><span class="sxs-lookup"><span data-stu-id="4428b-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="4428b-520">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="4428b-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="4428b-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="4428b-522">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-523">被呼叫者的麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="4428b-523">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="4428b-524">如果使用的是耳機，則值應該很低。</span><span class="sxs-lookup"><span data-stu-id="4428b-524">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="4428b-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="4428b-526">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-527">在被呼叫者的已傳送資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="4428b-527">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="4428b-528">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="4428b-528">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-530">int</span><span class="sxs-lookup"><span data-stu-id="4428b-530">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-531">從受話者的音訊的閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4428b-531">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="4428b-532">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-532">The unit of this metric is dBoV.</span></span> <span data-ttu-id="4428b-533">為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-533">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="4428b-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="4428b-535">int</span><span class="sxs-lookup"><span data-stu-id="4428b-535">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-536">從所呼叫者音訊的閘道，在轉送伺服器上收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="4428b-536">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="4428b-537">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="4428b-537">This applies only to the Mediation Server.</span></span> <span data-ttu-id="4428b-538">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-538">The unit of this metric is dBoV.</span></span> <span data-ttu-id="4428b-539">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="4428b-539">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="4428b-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="4428b-541">int</span><span class="sxs-lookup"><span data-stu-id="4428b-541">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-542">在套用至受話者音訊的轉送伺服器端 (AGC) 自動取得控制權。</span><span class="sxs-lookup"><span data-stu-id="4428b-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="4428b-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="4428b-544">float</span><span class="sxs-lookup"><span data-stu-id="4428b-544">float</span></span></p></td>
<td><p><span data-ttu-id="4428b-545">從來電者傳入的信號的根平均平方 (RMS) ，最多可達前30秒的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4428b-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-547">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-548">音訊修復所產生之隱藏樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="4428b-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-550">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-551">音訊修復所產生之延伸樣本的平均比率為典型範例。</span><span class="sxs-lookup"><span data-stu-id="4428b-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="4428b-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="4428b-553">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-554">音訊修復所產生之壓縮樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="4428b-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-555">往返</span><span class="sxs-lookup"><span data-stu-id="4428b-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="4428b-556">int</span><span class="sxs-lookup"><span data-stu-id="4428b-556">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-557">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="4428b-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="4428b-559">int</span><span class="sxs-lookup"><span data-stu-id="4428b-559">int</span></span></p></td>
<td><p><span data-ttu-id="4428b-560">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="4428b-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="4428b-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-562">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-563">通話的平均寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="4428b-563">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="4428b-564">此度量取決於所用的封包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="4428b-564">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="4428b-565">範圍是1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="4428b-565">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="4428b-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-567">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-568">通話的最小寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="4428b-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="4428b-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-570">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-571">已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="4428b-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="4428b-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="4428b-573">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-574">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="4428b-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="4428b-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="4428b-576">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-577">從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="4428b-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="4428b-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="4428b-579">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="4428b-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="4428b-580">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="4428b-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4428b-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="4428b-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="4428b-582">位</span><span class="sxs-lookup"><span data-stu-id="4428b-582">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-583">會指出是否使用音訊 FEC 進行通話。</span><span class="sxs-lookup"><span data-stu-id="4428b-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4428b-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="4428b-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="4428b-585">位</span><span class="sxs-lookup"><span data-stu-id="4428b-585">bit</span></span></p></td>
<td><p><span data-ttu-id="4428b-586">表示 p 宣稱識別資訊的方向;1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="4428b-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

