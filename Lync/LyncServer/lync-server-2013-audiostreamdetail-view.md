---
title: Lync Server 2013： AudioStreamDetail view
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
ms.openlocfilehash: fe995d08bf334308603512b4812b02c672d400f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="23f52-102">Lync Server 2013 中的 AudioStreamDetail 視圖</span><span class="sxs-lookup"><span data-stu-id="23f52-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="23f52-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="23f52-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="23f52-104">AudioStreamDetail View 儲存資料庫中每個音訊資料流程的資訊。</span><span class="sxs-lookup"><span data-stu-id="23f52-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="23f52-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="23f52-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23f52-106">欄</span><span class="sxs-lookup"><span data-stu-id="23f52-106">Column</span></span></th>
<th><span data-ttu-id="23f52-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="23f52-107">Data Type</span></span></th>
<th><span data-ttu-id="23f52-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="23f52-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23f52-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="23f52-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="23f52-110">datetime</span><span class="sxs-lookup"><span data-stu-id="23f52-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="23f52-111">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="23f52-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="23f52-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="23f52-113">int</span><span class="sxs-lookup"><span data-stu-id="23f52-113">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-114">從 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="23f52-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="23f52-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="23f52-116">int</span><span class="sxs-lookup"><span data-stu-id="23f52-116">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-117">媒體行中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="23f52-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="23f52-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="23f52-119">datetime</span><span class="sxs-lookup"><span data-stu-id="23f52-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="23f52-120">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="23f52-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="23f52-122">datetime</span><span class="sxs-lookup"><span data-stu-id="23f52-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="23f52-123">工作階段結束時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="23f52-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="23f52-125">位</span><span class="sxs-lookup"><span data-stu-id="23f52-125">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-126">對話方塊類別：0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="23f52-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="23f52-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="23f52-128">位</span><span class="sxs-lookup"><span data-stu-id="23f52-128">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-129">指示是否略過呼叫的旗標。</span><span class="sxs-lookup"><span data-stu-id="23f52-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="23f52-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="23f52-131">int</span><span class="sxs-lookup"><span data-stu-id="23f52-131">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-132">如果有的話，則表示即使旁路 IDs 相符也不會略過通話的原因。</span><span class="sxs-lookup"><span data-stu-id="23f52-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="23f52-133">只定義了一個值：</span><span class="sxs-lookup"><span data-stu-id="23f52-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="23f52-134">0x0001 –預設網路介面卡的未知旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="23f52-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="23f52-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="23f52-136">int</span><span class="sxs-lookup"><span data-stu-id="23f52-136">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-137">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="23f52-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="23f52-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="23f52-139">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-140">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23f52-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="23f52-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="23f52-142">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-143">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23f52-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-144">Caller</span><span class="sxs-lookup"><span data-stu-id="23f52-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="23f52-145">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="23f52-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="23f52-146">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="23f52-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-147">方</span><span class="sxs-lookup"><span data-stu-id="23f52-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="23f52-148">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="23f52-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="23f52-149">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="23f52-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="23f52-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="23f52-151">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-152">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="23f52-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="23f52-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="23f52-154">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-155">來電者使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="23f52-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="23f52-156">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="23f52-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="23f52-158">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="23f52-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="23f52-159">來電者使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="23f52-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="23f52-160">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="23f52-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="23f52-162">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-163">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="23f52-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="23f52-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="23f52-165">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-166">被呼叫者之使用者代理程式的類型。</span><span class="sxs-lookup"><span data-stu-id="23f52-166">Type of callee’s user agent.</span></span> <span data-ttu-id="23f52-167">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="23f52-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="23f52-169">Nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="23f52-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="23f52-170">被呼叫者之使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="23f52-170">Category of callee’s user agent.</span></span> <span data-ttu-id="23f52-171">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) 中的 Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="23f52-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="23f52-173">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-174">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="23f52-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="23f52-176">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-177">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="23f52-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-179">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-180">呼叫者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="23f52-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="23f52-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-182">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-183">受話者端點的作業系統 (OS) 。</span><span class="sxs-lookup"><span data-stu-id="23f52-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="23f52-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="23f52-185">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-186">來電者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="23f52-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="23f52-188">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-189">受話者端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="23f52-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="23f52-191">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-192">來電者端點中的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="23f52-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="23f52-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="23f52-194">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-195">受話者端點中的 CPU 核心數目。</span><span class="sxs-lookup"><span data-stu-id="23f52-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="23f52-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="23f52-197">int</span><span class="sxs-lookup"><span data-stu-id="23f52-197">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-198">來電者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="23f52-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="23f52-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="23f52-200">int</span><span class="sxs-lookup"><span data-stu-id="23f52-200">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-201">受話者端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="23f52-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="23f52-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="23f52-203">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-204">會指出來電者的系統是否在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="23f52-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="23f52-205">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="23f52-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="23f52-207">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-208">會指出受話者的系統是否正在虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="23f52-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="23f52-209">如需詳細資訊，請參閱 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="23f52-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="23f52-211">相關機碼。</span><span class="sxs-lookup"><span data-stu-id="23f52-211">Correlation key.</span></span> <span data-ttu-id="23f52-212">從 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="23f52-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="23f52-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="23f52-214">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-215">媒體路徑的相關資訊，例如 direct 或中繼。</span><span class="sxs-lookup"><span data-stu-id="23f52-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="23f52-216">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="23f52-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="23f52-218">int</span><span class="sxs-lookup"><span data-stu-id="23f52-218">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-p111">發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="23f52-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="23f52-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="23f52-222">int</span><span class="sxs-lookup"><span data-stu-id="23f52-222">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-p112">受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。</span><span class="sxs-lookup"><span data-stu-id="23f52-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-225">傳輸</span><span class="sxs-lookup"><span data-stu-id="23f52-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="23f52-226">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-227">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="23f52-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="23f52-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="23f52-229">var (50) </span><span class="sxs-lookup"><span data-stu-id="23f52-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="23f52-230">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23f52-230">IP address of the caller.</span></span> <span data-ttu-id="23f52-231">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="23f52-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="23f52-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="23f52-233">int</span><span class="sxs-lookup"><span data-stu-id="23f52-233">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-234">發話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="23f52-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="23f52-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="23f52-236">位</span><span class="sxs-lookup"><span data-stu-id="23f52-236">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-237">會指出來電者是否在間隔網路內：1表示來電者位於商業網路內，0表示來電者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="23f52-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="23f52-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="23f52-239">var (50) </span><span class="sxs-lookup"><span data-stu-id="23f52-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="23f52-240">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23f52-240">IP address of the callee.</span></span> <span data-ttu-id="23f52-241">這可以是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="23f52-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="23f52-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="23f52-243">int</span><span class="sxs-lookup"><span data-stu-id="23f52-243">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-244">受話者使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="23f52-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="23f52-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="23f52-246">位</span><span class="sxs-lookup"><span data-stu-id="23f52-246">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-247">會指出受話者是否在間隔網路內：1表示受話者位於商業網路內，0表示受話者位於網路外。</span><span class="sxs-lookup"><span data-stu-id="23f52-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="23f52-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="23f52-249">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-250">來電者網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="23f52-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="23f52-252">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-253">來電者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="23f52-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="23f52-255">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-256">被呼叫者之網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="23f52-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="23f52-258">Nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="23f52-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="23f52-259">被呼叫者網站的國家/地區名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="23f52-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="23f52-261">var (50) </span><span class="sxs-lookup"><span data-stu-id="23f52-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="23f52-262">發話者使用之 A/V Edge Service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="23f52-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="23f52-263">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="23f52-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="23f52-265">int</span><span class="sxs-lookup"><span data-stu-id="23f52-265">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-266">發話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="23f52-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="23f52-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="23f52-268">var (50) </span><span class="sxs-lookup"><span data-stu-id="23f52-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="23f52-269">被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="23f52-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="23f52-270">如需詳細資訊，請參閱 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="23f52-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="23f52-272">int</span><span class="sxs-lookup"><span data-stu-id="23f52-272">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-273">受話者在 A/V Edge Service 上使用的連接埠。</span><span class="sxs-lookup"><span data-stu-id="23f52-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="23f52-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="23f52-275">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-276">發話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="23f52-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="23f52-278">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-279">發話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="23f52-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="23f52-281">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-282">發話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="23f52-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="23f52-284">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-285">發話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="23f52-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="23f52-287">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-288">受話者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="23f52-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="23f52-290">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-291">受話者的轉換裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="23f52-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="23f52-293">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-294">受話者的擷取裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="23f52-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="23f52-296">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="23f52-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="23f52-297">受話者的轉換裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="23f52-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="23f52-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="23f52-299">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-300">來電者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="23f52-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="23f52-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="23f52-302">位</span><span class="sxs-lookup"><span data-stu-id="23f52-302">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-303">會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="23f52-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="23f52-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="23f52-305">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="23f52-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="23f52-306">呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="23f52-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="23f52-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="23f52-308">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-309">被呼叫者的網路連線類型：0是有線的，1是無線。</span><span class="sxs-lookup"><span data-stu-id="23f52-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="23f52-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="23f52-311">位</span><span class="sxs-lookup"><span data-stu-id="23f52-311">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-312">會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="23f52-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="23f52-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="23f52-314">十進位 (18，0) </span><span class="sxs-lookup"><span data-stu-id="23f52-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="23f52-315">被呼叫者端點的網路連結速度（bps）。</span><span class="sxs-lookup"><span data-stu-id="23f52-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="23f52-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-317">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-318">音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。</span><span class="sxs-lookup"><span data-stu-id="23f52-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="23f52-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="23f52-320">int</span><span class="sxs-lookup"><span data-stu-id="23f52-320">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-321">針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。</span><span class="sxs-lookup"><span data-stu-id="23f52-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="23f52-322">這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。</span><span class="sxs-lookup"><span data-stu-id="23f52-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="23f52-323">這基本上是傳送資料流程可以採用限制頻寬估計所強加限制的最大頻寬</span><span class="sxs-lookup"><span data-stu-id="23f52-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="23f52-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="23f52-325">int</span><span class="sxs-lookup"><span data-stu-id="23f52-325">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-326">從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="23f52-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="23f52-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="23f52-328">int</span><span class="sxs-lookup"><span data-stu-id="23f52-328">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-329">通話期間的最大網路抖動。</span><span class="sxs-lookup"><span data-stu-id="23f52-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="23f52-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-331">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="23f52-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="23f52-332">通話期間的平均封包遺失率。</span><span class="sxs-lookup"><span data-stu-id="23f52-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="23f52-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="23f52-334">十進位 (5，4) </span><span class="sxs-lookup"><span data-stu-id="23f52-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="23f52-335">通話期間觀察到的封包遺失上限。</span><span class="sxs-lookup"><span data-stu-id="23f52-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="23f52-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="23f52-337">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="23f52-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="23f52-338">通話期間的猝量遺失期間的封包遺失平均密度。</span><span class="sxs-lookup"><span data-stu-id="23f52-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="23f52-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="23f52-340">int</span><span class="sxs-lookup"><span data-stu-id="23f52-340">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-341">通話期間的猝量遺失期間的封包遺失平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="23f52-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="23f52-343">十進位 (9，4) </span><span class="sxs-lookup"><span data-stu-id="23f52-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="23f52-344">封包遺失失敗之間的平均封包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="23f52-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="23f52-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="23f52-346">int</span><span class="sxs-lookup"><span data-stu-id="23f52-346">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-347">封包遺失的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="23f52-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="23f52-349">int</span><span class="sxs-lookup"><span data-stu-id="23f52-349">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-350">音訊資料流程的封包計數。</span><span class="sxs-lookup"><span data-stu-id="23f52-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="23f52-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="23f52-352">int</span><span class="sxs-lookup"><span data-stu-id="23f52-352">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-353">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="23f52-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-355">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-356">整個通話的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="23f52-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="23f52-357">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="23f52-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="23f52-358">此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。</span><span class="sxs-lookup"><span data-stu-id="23f52-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="23f52-359">可接受的品質應小於0.5。</span><span class="sxs-lookup"><span data-stu-id="23f52-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="23f52-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="23f52-361">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-362">通話期間的最大網路 MOS 降級。</span><span class="sxs-lookup"><span data-stu-id="23f52-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-364">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-365">抖動導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="23f52-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-367">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-368">封包遺失導致的網路 MOS 降低。</span><span class="sxs-lookup"><span data-stu-id="23f52-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="23f52-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="23f52-370">int</span><span class="sxs-lookup"><span data-stu-id="23f52-370">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-371">用於通話的音訊編解碼器，從 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="23f52-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="23f52-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-373">int</span><span class="sxs-lookup"><span data-stu-id="23f52-373">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-374">音訊資料流程的取樣速率。</span><span class="sxs-lookup"><span data-stu-id="23f52-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-376">int</span><span class="sxs-lookup"><span data-stu-id="23f52-376">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-377">來電者所傳送之音訊的後續類比增益控制音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="23f52-378">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-379">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="23f52-380">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-382">int</span><span class="sxs-lookup"><span data-stu-id="23f52-382">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-383">來電者接收之音訊的音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="23f52-384">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-385">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="23f52-386">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-388">int</span><span class="sxs-lookup"><span data-stu-id="23f52-388">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-389">來電者所傳送之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="23f52-390">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-391">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="23f52-392">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-394">int</span><span class="sxs-lookup"><span data-stu-id="23f52-394">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-395">來電者接收之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="23f52-396">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-397">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="23f52-398">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="23f52-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="23f52-400">int</span><span class="sxs-lookup"><span data-stu-id="23f52-400">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-401">呼叫來電者的回顯回復功能增強功能。</span><span class="sxs-lookup"><span data-stu-id="23f52-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="23f52-402">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="23f52-402">The unit for this metric is dB.</span></span> <span data-ttu-id="23f52-403">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="23f52-403">Lower values represent less echo.</span></span> <span data-ttu-id="23f52-404">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="23f52-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-406">int</span><span class="sxs-lookup"><span data-stu-id="23f52-406">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-407">呼叫者的喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="23f52-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="23f52-408">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="23f52-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="23f52-409">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="23f52-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="23f52-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-411">int</span><span class="sxs-lookup"><span data-stu-id="23f52-411">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-412">來電者的擴音器 capture 每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="23f52-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="23f52-413">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="23f52-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="23f52-414">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="23f52-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="23f52-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="23f52-416">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-417">來電者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="23f52-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="23f52-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="23f52-419">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-420">來電者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="23f52-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="23f52-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="23f52-422">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-423">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="23f52-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="23f52-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="23f52-425">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-426">呼叫者的最後20秒內，平均來電者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="23f52-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="23f52-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="23f52-428">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-429">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="23f52-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="23f52-430">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="23f52-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="23f52-432">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-433">來電者的 echo 事件原因。</span><span class="sxs-lookup"><span data-stu-id="23f52-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="23f52-434">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="23f52-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="23f52-436">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-437">在來電者的麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="23f52-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="23f52-438">如果使用的是耳機，則值應該很低。</span><span class="sxs-lookup"><span data-stu-id="23f52-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="23f52-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="23f52-440">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-441">在來電者的傳送資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="23f52-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="23f52-442">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="23f52-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-444">int</span><span class="sxs-lookup"><span data-stu-id="23f52-444">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-445">從來電者音訊的閘道，在轉送伺服器上接收信號等級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="23f52-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="23f52-446">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="23f52-447">為了獲得良好的品質，可接受的範圍應為-30 到-18 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-449">int</span><span class="sxs-lookup"><span data-stu-id="23f52-449">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-450">從來電者的音訊的閘道處接收轉送伺服器上的信號等級。</span><span class="sxs-lookup"><span data-stu-id="23f52-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="23f52-451">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="23f52-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="23f52-452">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="23f52-453">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="23f52-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="23f52-455">int</span><span class="sxs-lookup"><span data-stu-id="23f52-455">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-456">在套用至來電者音訊的轉送伺服器端 (AGC) 自動取得控制權。</span><span class="sxs-lookup"><span data-stu-id="23f52-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="23f52-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="23f52-458">float</span><span class="sxs-lookup"><span data-stu-id="23f52-458">float</span></span></p></td>
<td><p><span data-ttu-id="23f52-459">對來電者傳入的信號的根平均方 (RMS) ，最多可達前30秒的呼叫。</span><span class="sxs-lookup"><span data-stu-id="23f52-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-461">int</span><span class="sxs-lookup"><span data-stu-id="23f52-461">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-462">代表被呼叫者所傳送之音訊的後續類比增益控制音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="23f52-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="23f52-463">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-464">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="23f52-465">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-467">int</span><span class="sxs-lookup"><span data-stu-id="23f52-467">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-468">被呼叫者所接收之音訊的音訊信號層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="23f52-469">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-470">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="23f52-471">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-473">int</span><span class="sxs-lookup"><span data-stu-id="23f52-473">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-474">受話者所傳送之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="23f52-475">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-476">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="23f52-477">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-479">int</span><span class="sxs-lookup"><span data-stu-id="23f52-479">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-480">受話者接收之音訊的後續類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="23f52-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="23f52-481">此度量單位的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="23f52-482">針對可接受的品質，它應小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="23f52-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="23f52-483">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="23f52-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="23f52-485">int</span><span class="sxs-lookup"><span data-stu-id="23f52-485">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-486">被呼叫者的回顯傳回遺失增強功能。</span><span class="sxs-lookup"><span data-stu-id="23f52-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="23f52-487">此度量單位的單位為 dB。</span><span class="sxs-lookup"><span data-stu-id="23f52-487">The unit for this metric is dB.</span></span> <span data-ttu-id="23f52-488">較低的值表示較少的回聲。</span><span class="sxs-lookup"><span data-stu-id="23f52-488">Lower values represent less echo.</span></span> <span data-ttu-id="23f52-489">A/V 的會議服務器或 IP 電話不會報告此度量。</span><span class="sxs-lookup"><span data-stu-id="23f52-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="23f52-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-491">int</span><span class="sxs-lookup"><span data-stu-id="23f52-491">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-492">被呼叫者的喇叭轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="23f52-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="23f52-493">為了獲得良好的品質，應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="23f52-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="23f52-494">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="23f52-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="23f52-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="23f52-496">int</span><span class="sxs-lookup"><span data-stu-id="23f52-496">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-497">受話者麥克風捕獲每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="23f52-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="23f52-498">若為良好的品質，這應小於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="23f52-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="23f52-499">不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。</span><span class="sxs-lookup"><span data-stu-id="23f52-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="23f52-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="23f52-501">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-502">受話者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="23f52-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="23f52-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="23f52-504">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-505">受話者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。</span><span class="sxs-lookup"><span data-stu-id="23f52-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="23f52-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="23f52-507">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-508">通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="23f52-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="23f52-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="23f52-510">十進位 (9，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-511">通話的最後20秒內，被呼叫者的發言人轉譯資料流程時間戳記錯誤（毫秒）。</span><span class="sxs-lookup"><span data-stu-id="23f52-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="23f52-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="23f52-513">Smallint</span><span class="sxs-lookup"><span data-stu-id="23f52-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="23f52-514">語音開關是一種具有低中斷能力的半雙工模式。</span><span class="sxs-lookup"><span data-stu-id="23f52-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="23f52-515">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="23f52-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="23f52-517">Tinyint</span><span class="sxs-lookup"><span data-stu-id="23f52-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="23f52-518">被呼叫者的 echo 事件原因。</span><span class="sxs-lookup"><span data-stu-id="23f52-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="23f52-519">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="23f52-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="23f52-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="23f52-521">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-522">被呼叫者的麥克風捕獲資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="23f52-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="23f52-523">如果使用的是耳機，則值應該很低。</span><span class="sxs-lookup"><span data-stu-id="23f52-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="23f52-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="23f52-525">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-526">在被呼叫者的已傳送資料流程中偵測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="23f52-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="23f52-527">傳送資料流程中的高回音百分比會傳回回聲洩漏。</span><span class="sxs-lookup"><span data-stu-id="23f52-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-529">int</span><span class="sxs-lookup"><span data-stu-id="23f52-529">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-530">從受話者的音訊的閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="23f52-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="23f52-531">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="23f52-532">為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="23f52-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="23f52-534">int</span><span class="sxs-lookup"><span data-stu-id="23f52-534">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-535">從所呼叫者音訊的閘道，在轉送伺服器上收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="23f52-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="23f52-536">這只適用于轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="23f52-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="23f52-537">此度量單位為 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="23f52-538">為了獲得良好的品質，可接受的範圍應小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="23f52-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="23f52-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="23f52-540">int</span><span class="sxs-lookup"><span data-stu-id="23f52-540">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-541">在套用至受話者音訊的轉送伺服器端 (AGC) 自動取得控制權。</span><span class="sxs-lookup"><span data-stu-id="23f52-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="23f52-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="23f52-543">float</span><span class="sxs-lookup"><span data-stu-id="23f52-543">float</span></span></p></td>
<td><p><span data-ttu-id="23f52-544">從來電者傳入的信號的根平均平方 (RMS) ，最多可達前30秒的呼叫。</span><span class="sxs-lookup"><span data-stu-id="23f52-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-546">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-547">音訊修復所產生之隱藏樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="23f52-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-549">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-550">音訊修復所產生之延伸樣本的平均比率為典型範例。</span><span class="sxs-lookup"><span data-stu-id="23f52-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="23f52-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="23f52-552">十進位 (5，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-553">音訊修復所產生之壓縮樣本與一般範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="23f52-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-554">往返</span><span class="sxs-lookup"><span data-stu-id="23f52-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="23f52-555">int</span><span class="sxs-lookup"><span data-stu-id="23f52-555">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-556">從 RTCP 統計資料來回的時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="23f52-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="23f52-558">int</span><span class="sxs-lookup"><span data-stu-id="23f52-558">int</span></span></p></td>
<td><p><span data-ttu-id="23f52-559">音訊資料流程的最大來回時間。</span><span class="sxs-lookup"><span data-stu-id="23f52-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="23f52-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-561">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-562">通話的平均寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="23f52-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="23f52-563">此度量取決於所用的封包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="23f52-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="23f52-564">範圍是1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="23f52-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="23f52-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-566">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-567">通話的最小寬頻網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="23f52-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="23f52-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-569">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-570">已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="23f52-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="23f52-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="23f52-572">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-573">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="23f52-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="23f52-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="23f52-575">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-576">從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。</span><span class="sxs-lookup"><span data-stu-id="23f52-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="23f52-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="23f52-578">十進位 (3，2) </span><span class="sxs-lookup"><span data-stu-id="23f52-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="23f52-579">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="23f52-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23f52-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="23f52-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="23f52-581">位</span><span class="sxs-lookup"><span data-stu-id="23f52-581">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-582">會指出是否使用音訊 FEC 進行通話。</span><span class="sxs-lookup"><span data-stu-id="23f52-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23f52-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="23f52-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="23f52-584">位</span><span class="sxs-lookup"><span data-stu-id="23f52-584">bit</span></span></p></td>
<td><p><span data-ttu-id="23f52-585">表示 p 宣稱識別資訊的方向;1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。</span><span class="sxs-lookup"><span data-stu-id="23f52-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

