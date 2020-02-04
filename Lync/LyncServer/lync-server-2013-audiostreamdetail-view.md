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
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="db5d0-102">Lync Server 2013 中的 [AudioStreamDetail] 視圖</span><span class="sxs-lookup"><span data-stu-id="db5d0-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db5d0-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="db5d0-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="db5d0-104">[AudioStreamDetail] 視圖會儲存資料庫中每個音訊資料流程的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="db5d0-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="db5d0-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db5d0-106">左欄</span><span class="sxs-lookup"><span data-stu-id="db5d0-106">Column</span></span></th>
<th><span data-ttu-id="db5d0-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="db5d0-107">Data Type</span></span></th>
<th><span data-ttu-id="db5d0-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="db5d0-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="db5d0-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-110">datetime</span><span class="sxs-lookup"><span data-stu-id="db5d0-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-111">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="db5d0-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="db5d0-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="db5d0-113">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-113">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-114">從<a href="lync-server-2013-medialine-table.md">Lync Server 2013 的 MediaLine 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="db5d0-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="db5d0-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="db5d0-116">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-116">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-117">媒體線中的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="db5d0-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-118">開始</span><span class="sxs-lookup"><span data-stu-id="db5d0-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-119">datetime</span><span class="sxs-lookup"><span data-stu-id="db5d0-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-120">會話的開始時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="db5d0-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-122">datetime</span><span class="sxs-lookup"><span data-stu-id="db5d0-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="db5d0-123">會話的結束時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="db5d0-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="db5d0-125">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-125">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-126">對話方塊類別：0是 Lync 伺服器以進行轉送伺服器腿;1是通向 PSTN 閘道腿的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="db5d0-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="db5d0-128">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-128">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-129">該旗標指出通話是否被略過。</span><span class="sxs-lookup"><span data-stu-id="db5d0-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="db5d0-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="db5d0-131">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-131">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-132">如果有的話，則指示即使繞過旁路 Id，也不會避開通話。</span><span class="sxs-lookup"><span data-stu-id="db5d0-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="db5d0-133">只定義一個值：</span><span class="sxs-lookup"><span data-stu-id="db5d0-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="db5d0-134">0x0001 –預設網路介面卡的旁路旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="db5d0-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="db5d0-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="db5d0-136">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-136">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-137">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="db5d0-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="db5d0-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="db5d0-139">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-140">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="db5d0-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="db5d0-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="db5d0-142">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-143">被呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="db5d0-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-144">呼叫</span><span class="sxs-lookup"><span data-stu-id="db5d0-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="db5d0-145">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="db5d0-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-146">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="db5d0-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-147">方</span><span class="sxs-lookup"><span data-stu-id="db5d0-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="db5d0-148">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="db5d0-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-149">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="db5d0-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="db5d0-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="db5d0-151">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-152">來電者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="db5d0-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="db5d0-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="db5d0-154">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-155">來電者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="db5d0-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="db5d0-156">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="db5d0-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="db5d0-158">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="db5d0-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-159">呼叫者使用者代理程式的類別。</span><span class="sxs-lookup"><span data-stu-id="db5d0-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="db5d0-160">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="db5d0-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="db5d0-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="db5d0-162">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-163">被呼叫者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="db5d0-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="db5d0-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="db5d0-165">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-166">被呼叫者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="db5d0-166">Type of callee’s user agent.</span></span> <span data-ttu-id="db5d0-167">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="db5d0-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="db5d0-169">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="db5d0-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-170">被呼叫者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="db5d0-170">Category of callee’s user agent.</span></span> <span data-ttu-id="db5d0-171">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="db5d0-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="db5d0-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-173">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-174">來電者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="db5d0-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-176">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-177">被呼叫者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-179">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-180">呼叫者終點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="db5d0-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-182">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-183">被呼叫者的端點的作業系統（OS）。</span><span class="sxs-lookup"><span data-stu-id="db5d0-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="db5d0-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="db5d0-185">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-186">呼叫者終點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="db5d0-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="db5d0-188">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-189">被呼叫者的端點的 CPU 名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="db5d0-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="db5d0-191">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-192">呼叫者終點中的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="db5d0-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="db5d0-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="db5d0-194">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-195">被呼叫者的端點中的 CPU 核心數。</span><span class="sxs-lookup"><span data-stu-id="db5d0-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="db5d0-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="db5d0-197">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-197">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-198">呼叫者終點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="db5d0-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="db5d0-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="db5d0-200">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-200">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-201">被呼叫者的端點的 CPU 處理器速度。</span><span class="sxs-lookup"><span data-stu-id="db5d0-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="db5d0-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="db5d0-203">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-204">指出呼叫者的系統在虛擬化環境中是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="db5d0-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="db5d0-205">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="db5d0-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="db5d0-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="db5d0-207">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-208">指出被呼叫者的系統是否正在虛擬化環境中執行。</span><span class="sxs-lookup"><span data-stu-id="db5d0-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="db5d0-209">如需詳細資訊，請參閱<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="db5d0-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="db5d0-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="db5d0-211">[關聯金鑰]。</span><span class="sxs-lookup"><span data-stu-id="db5d0-211">Correlation key.</span></span> <span data-ttu-id="db5d0-212">從<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="db5d0-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="db5d0-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="db5d0-214">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-215">媒體路徑（例如直接或中繼）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="db5d0-216">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="db5d0-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="db5d0-218">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-218">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-219">針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="db5d0-220">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="db5d0-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="db5d0-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="db5d0-222">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-222">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-223">針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="db5d0-224">如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。</span><span class="sxs-lookup"><span data-stu-id="db5d0-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-225">傳輸</span><span class="sxs-lookup"><span data-stu-id="db5d0-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="db5d0-226">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-227">傳輸類型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="db5d0-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="db5d0-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="db5d0-229">var （50）</span><span class="sxs-lookup"><span data-stu-id="db5d0-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-230">來電者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db5d0-230">IP address of the caller.</span></span> <span data-ttu-id="db5d0-231">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="db5d0-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="db5d0-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="db5d0-233">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-233">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-234">呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="db5d0-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="db5d0-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="db5d0-236">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-236">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-237">指出來電者是否在間隔網路內：1表示呼叫者是在商業網路內，0代表來電者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="db5d0-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="db5d0-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="db5d0-239">var （50）</span><span class="sxs-lookup"><span data-stu-id="db5d0-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-240">被呼叫者的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db5d0-240">IP address of the callee.</span></span> <span data-ttu-id="db5d0-241">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="db5d0-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="db5d0-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="db5d0-243">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-243">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-244">被呼叫者使用的埠。</span><span class="sxs-lookup"><span data-stu-id="db5d0-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="db5d0-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="db5d0-246">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-246">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-247">指出被呼叫者是否在間隔網路內：1代表被呼叫者是在商業網路內，0代表被呼叫者在網路以外。</span><span class="sxs-lookup"><span data-stu-id="db5d0-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="db5d0-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="db5d0-249">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-250">來電者的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="db5d0-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="db5d0-252">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-253">來電者網站之國家/地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="db5d0-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="db5d0-255">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-256">被呼叫者的網站名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="db5d0-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="db5d0-258">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="db5d0-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-259">被呼叫者網站之國家/地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="db5d0-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="db5d0-261">var （50）</span><span class="sxs-lookup"><span data-stu-id="db5d0-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-262">呼叫者所使用之 A/V 邊緣服務的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="db5d0-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="db5d0-263">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="db5d0-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="db5d0-265">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-265">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-266">呼叫者使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="db5d0-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="db5d0-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="db5d0-268">var （50）</span><span class="sxs-lookup"><span data-stu-id="db5d0-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-269">被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。</span><span class="sxs-lookup"><span data-stu-id="db5d0-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="db5d0-270">如需詳細資訊，請參閱<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 [IPAddress] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="db5d0-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="db5d0-272">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-272">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-273">在被呼叫者所使用的 A/V 邊緣服務上使用的埠。</span><span class="sxs-lookup"><span data-stu-id="db5d0-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="db5d0-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="db5d0-275">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-276">來電者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="db5d0-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="db5d0-278">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-279">來電者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="db5d0-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="db5d0-281">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-282">來電者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="db5d0-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="db5d0-284">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-285">來電者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="db5d0-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="db5d0-287">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-288">被呼叫者的擷取裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="db5d0-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="db5d0-290">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-291">被呼叫者的轉譯裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="db5d0-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="db5d0-293">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-294">被呼叫者的捕獲裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="db5d0-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="db5d0-296">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="db5d0-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-297">被呼叫者的轉譯裝置驅動程式名稱。</span><span class="sxs-lookup"><span data-stu-id="db5d0-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="db5d0-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="db5d0-299">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-300">來電者的網路連線類型：0是 [有線]，1是 [無線]。</span><span class="sxs-lookup"><span data-stu-id="db5d0-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="db5d0-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="db5d0-302">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-302">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-303">指出呼叫者是否已經由虛擬專用網路連接：1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="db5d0-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="db5d0-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="db5d0-305">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="db5d0-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-306">呼叫者端點的網路連結速度，以 bps 表示。</span><span class="sxs-lookup"><span data-stu-id="db5d0-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="db5d0-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="db5d0-308">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-309">被呼叫者的網路連線類型：0是 [有線]，1是 [無線]。</span><span class="sxs-lookup"><span data-stu-id="db5d0-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="db5d0-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="db5d0-311">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-311">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-312">指出呼叫者是否已經由虛擬專用網路連接：1是虛擬私人網路（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="db5d0-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="db5d0-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="db5d0-314">小數（18，0）</span><span class="sxs-lookup"><span data-stu-id="db5d0-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-315">被呼叫者的端點的網路連結速度，以 bps 表示。</span><span class="sxs-lookup"><span data-stu-id="db5d0-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-317">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-318">Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。</span><span class="sxs-lookup"><span data-stu-id="db5d0-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="db5d0-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-320">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-320">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-321">在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。</span><span class="sxs-lookup"><span data-stu-id="db5d0-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="db5d0-322">這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="db5d0-323">這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所強加的限制</span><span class="sxs-lookup"><span data-stu-id="db5d0-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="db5d0-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="db5d0-325">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-325">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-326">從即時控制通訊協定（RTCP）統計資料的平均網路抖動。</span><span class="sxs-lookup"><span data-stu-id="db5d0-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="db5d0-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="db5d0-328">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-328">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-329">通話期間網路抖動的最大值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-331">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="db5d0-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-332">通話期間的平均資料包遺失率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="db5d0-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="db5d0-334">十進位（5，4）</span><span class="sxs-lookup"><span data-stu-id="db5d0-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-335">通話期間觀察到的最大資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="db5d0-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="db5d0-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="db5d0-337">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="db5d0-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-338">通話期間猝發損失期間的平均資料包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="db5d0-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="db5d0-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="db5d0-340">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-340">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-341">通話期間猝發損失期間的平均資料包遺失時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="db5d0-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="db5d0-343">十進位（9，4）</span><span class="sxs-lookup"><span data-stu-id="db5d0-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-344">在突發資料包遺失之間的間隔期間的平均資料包遺失密度。</span><span class="sxs-lookup"><span data-stu-id="db5d0-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="db5d0-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="db5d0-346">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-346">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-347">猝發資料包遺失之間的平均持續時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="db5d0-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="db5d0-349">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-349">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-350">音訊資料流程的 [資料包計數]。</span><span class="sxs-lookup"><span data-stu-id="db5d0-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="db5d0-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="db5d0-352">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-352">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-353">音訊資料流程的頻寬估計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-355">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-356">整個通話的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="db5d0-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="db5d0-357">範圍是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="db5d0-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="db5d0-358">這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。</span><span class="sxs-lookup"><span data-stu-id="db5d0-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="db5d0-359">針對可接受的品質，它應該小於0.5。</span><span class="sxs-lookup"><span data-stu-id="db5d0-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="db5d0-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="db5d0-361">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-362">通話期間網路 MOS 的最大下降。</span><span class="sxs-lookup"><span data-stu-id="db5d0-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-364">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-365">抖動造成的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="db5d0-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-367">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-368">因數據包遺失而造成的網路 MOS 下降。</span><span class="sxs-lookup"><span data-stu-id="db5d0-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="db5d0-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="db5d0-370">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-370">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-371">在<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 的 PayloadDescription 資料表中</a>參考的音訊編解碼器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-373">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-373">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-374">音訊資料流程的採樣速率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-376">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-376">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-377">撥號後的類比增益控制呼叫者傳送之音訊的音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="db5d0-378">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-379">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="db5d0-380">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-382">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-382">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-383">來電者收到之音訊的音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="db5d0-384">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-385">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="db5d0-386">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-388">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-388">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-389">撥號後的類比增益控制來電者傳送之音訊的音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="db5d0-390">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-391">針對可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="db5d0-392">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-394">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-394">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-395">撥號後的類比增益控制來電者收到之音訊的音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="db5d0-396">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-397">針對可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="db5d0-398">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="db5d0-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="db5d0-400">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-400">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-401">來電者的迴響回報損失增強功能。</span><span class="sxs-lookup"><span data-stu-id="db5d0-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="db5d0-402">這個指標的單位是 dB。</span><span class="sxs-lookup"><span data-stu-id="db5d0-402">The unit for this metric is dB.</span></span> <span data-ttu-id="db5d0-403">較低的值代表較少的回音。</span><span class="sxs-lookup"><span data-stu-id="db5d0-403">Lower values represent less echo.</span></span> <span data-ttu-id="db5d0-404">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-406">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-406">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-407">呼叫者的喇叭前轉譯每五分鐘的平均問題。</span><span class="sxs-lookup"><span data-stu-id="db5d0-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="db5d0-408">若要獲得較高的品質，此頻率應該小於每五分鐘。</span><span class="sxs-lookup"><span data-stu-id="db5d0-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="db5d0-409">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="db5d0-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-411">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-411">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-412">呼叫者麥克風捕獲每五分鐘的平均問題。</span><span class="sxs-lookup"><span data-stu-id="db5d0-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="db5d0-413">若要獲得良好的品質，這應該少於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="db5d0-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="db5d0-414">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="db5d0-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="db5d0-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="db5d0-416">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-417">本機號碼相對於 CPU 時鐘的麥克風裝置時鐘偏移速度。</span><span class="sxs-lookup"><span data-stu-id="db5d0-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="db5d0-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="db5d0-419">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-420">來電者與 CPU 時鐘相關的喇叭裝置時鐘偏移率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="db5d0-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="db5d0-422">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-423">在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="db5d0-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="db5d0-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="db5d0-425">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-426">呼叫者最近20秒內，來電者的喇叭轉譯資料流程時間戳記錯誤的平均值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="db5d0-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="db5d0-428">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-429">Voice 開關是一種半雙工模式，可減少中斷能力。</span><span class="sxs-lookup"><span data-stu-id="db5d0-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="db5d0-430">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="db5d0-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="db5d0-432">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-433">呼叫者回顯事件的原因。</span><span class="sxs-lookup"><span data-stu-id="db5d0-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="db5d0-434">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="db5d0-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="db5d0-436">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-437">在呼叫者麥克風捕獲串流中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="db5d0-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="db5d0-438">如果使用耳機，該值應該較低。</span><span class="sxs-lookup"><span data-stu-id="db5d0-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="db5d0-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="db5d0-440">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-441">在來電者的傳送資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="db5d0-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="db5d0-442">傳送資料流程中的高迴響百分比表示回應洩漏。</span><span class="sxs-lookup"><span data-stu-id="db5d0-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-444">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-444">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-445">從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="db5d0-446">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="db5d0-447">若要獲得良好的品質，可接受的範圍應該是-30 到-18 的 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-449">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-449">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-450">從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="db5d0-451">這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="db5d0-452">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="db5d0-453">若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="db5d0-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="db5d0-455">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-455">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-456">將中繼伺服器端的自動增益控制（AGC）套用至呼叫者的音訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="db5d0-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-458">浮</span><span class="sxs-lookup"><span data-stu-id="db5d0-458">float</span></span></p></td>
<td><p><span data-ttu-id="db5d0-459">呼叫的撥入信號的根平均數（RMS），最多為來電者的前30秒。</span><span class="sxs-lookup"><span data-stu-id="db5d0-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-461">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-461">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-462">代表被呼叫者傳送之音訊的類比後增益控制音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="db5d0-463">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-464">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="db5d0-465">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-467">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-467">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-468">被呼叫者接收之音訊的音訊信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="db5d0-469">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-470">若要取得可接受的品質，至少要有 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="db5d0-471">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-473">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-473">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-474">防類比增益控制被呼叫者傳送之音訊的音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="db5d0-475">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-476">針對可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="db5d0-477">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-479">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-479">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-480">已被呼叫者接收之音訊的反類比增益控制音訊雜訊層級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="db5d0-481">這個指標的單位是 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="db5d0-482">針對可接受的品質，它應該小於 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="db5d0-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="db5d0-483">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="db5d0-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="db5d0-485">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-485">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-486">被呼叫者的迴響傳回損失增強功能。</span><span class="sxs-lookup"><span data-stu-id="db5d0-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="db5d0-487">這個指標的單位是 dB。</span><span class="sxs-lookup"><span data-stu-id="db5d0-487">The unit for this metric is dB.</span></span> <span data-ttu-id="db5d0-488">較低的值代表較少的回音。</span><span class="sxs-lookup"><span data-stu-id="db5d0-488">Lower values represent less echo.</span></span> <span data-ttu-id="db5d0-489">A/V 會議伺服器或 IP 電話不會報告此統計值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-491">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-491">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-492">被呼叫者的喇叭前轉譯每五分鐘的平均故障。</span><span class="sxs-lookup"><span data-stu-id="db5d0-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="db5d0-493">若要獲得較高的品質，此頻率應該小於每五分鐘。</span><span class="sxs-lookup"><span data-stu-id="db5d0-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="db5d0-494">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="db5d0-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="db5d0-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="db5d0-496">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-496">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-497">被呼叫者麥克風捕獲每五分鐘的平均問題。</span><span class="sxs-lookup"><span data-stu-id="db5d0-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="db5d0-498">若要獲得良好的品質，這應該少於每五分鐘一次。</span><span class="sxs-lookup"><span data-stu-id="db5d0-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="db5d0-499">無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。</span><span class="sxs-lookup"><span data-stu-id="db5d0-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="db5d0-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="db5d0-501">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-502">被呼叫者的麥克風裝置時鐘偏移率，相對於 CPU 時鐘。</span><span class="sxs-lookup"><span data-stu-id="db5d0-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="db5d0-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="db5d0-504">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-505">被呼叫者的喇叭裝置時鐘偏移率，相對於 CPU 時鐘。</span><span class="sxs-lookup"><span data-stu-id="db5d0-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="db5d0-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="db5d0-507">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-508">在呼叫的最後20秒內，麥克風捕獲串流的時間戳記錯誤（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="db5d0-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="db5d0-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="db5d0-510">decimal （9，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-511">呼叫者最近20秒內，被呼叫者的喇叭轉譯資料流程時間戳記錯誤的平均值。</span><span class="sxs-lookup"><span data-stu-id="db5d0-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="db5d0-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="db5d0-513">Smallint</span><span class="sxs-lookup"><span data-stu-id="db5d0-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-514">Voice 開關是一種半雙工模式，可減少中斷能力。</span><span class="sxs-lookup"><span data-stu-id="db5d0-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="db5d0-515">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="db5d0-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="db5d0-517">Tinyint</span><span class="sxs-lookup"><span data-stu-id="db5d0-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="db5d0-518">被呼叫者的 echo 事件原因。</span><span class="sxs-lookup"><span data-stu-id="db5d0-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="db5d0-519">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="db5d0-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="db5d0-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="db5d0-521">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-522">在被呼叫者的麥克風捕獲資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="db5d0-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="db5d0-523">如果使用耳機，該值應該較低。</span><span class="sxs-lookup"><span data-stu-id="db5d0-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="db5d0-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="db5d0-525">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-526">在被呼叫者的傳送資料流程中檢測到迴響的時間百分比。</span><span class="sxs-lookup"><span data-stu-id="db5d0-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="db5d0-527">傳送資料流程中的高迴響百分比表示回應洩漏。</span><span class="sxs-lookup"><span data-stu-id="db5d0-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-529">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-529">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-530">從被呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="db5d0-531">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="db5d0-532">若要獲得良好的品質，可接受的範圍應該是 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="db5d0-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="db5d0-534">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-534">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-535">從被呼叫者音訊的閘道，在中繼伺服器上接收到的信號等級。</span><span class="sxs-lookup"><span data-stu-id="db5d0-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="db5d0-536">這只適用于中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="db5d0-537">這個度量單位是 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="db5d0-538">若要獲得良好的品質，可接受的範圍應該小於-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="db5d0-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="db5d0-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="db5d0-540">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-540">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-541">將中繼伺服器端的自動增益控制（AGC）套用到被呼叫者的音訊。</span><span class="sxs-lookup"><span data-stu-id="db5d0-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="db5d0-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-543">浮</span><span class="sxs-lookup"><span data-stu-id="db5d0-543">float</span></span></p></td>
<td><p><span data-ttu-id="db5d0-544">呼叫的撥入信號的根平均數（RMS），最多為撥打電話的前30秒。</span><span class="sxs-lookup"><span data-stu-id="db5d0-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-546">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-547">從音訊康復產生的隱藏樣本到典型範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-549">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-550">從音訊康復產生的延伸樣本數與典型範例的平均比率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="db5d0-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="db5d0-552">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-553">從音訊修復到典型範例所產生之壓縮樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="db5d0-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-554">環路</span><span class="sxs-lookup"><span data-stu-id="db5d0-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="db5d0-555">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-555">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-556">從 RTCP 統計資料中往返的時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="db5d0-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="db5d0-558">int</span><span class="sxs-lookup"><span data-stu-id="db5d0-558">int</span></span></p></td>
<td><p><span data-ttu-id="db5d0-559">音訊資料流程的最大往返行程時間。</span><span class="sxs-lookup"><span data-stu-id="db5d0-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-561">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-562">通話的平均 wideband 網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="db5d0-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="db5d0-563">這個指標取決於所使用的資料包遺失、抖動和編解碼器。</span><span class="sxs-lookup"><span data-stu-id="db5d0-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="db5d0-564">範圍是1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="db5d0-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-566">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-567">通話的最小 wideband 網路 MOS。</span><span class="sxs-lookup"><span data-stu-id="db5d0-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-569">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-570">已傳送音訊的平均預計 wideband，包括語音等級、雜訊等級及捕捉裝置特徵。</span><span class="sxs-lookup"><span data-stu-id="db5d0-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="db5d0-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="db5d0-572">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-573">通話的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="db5d0-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="db5d0-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="db5d0-575">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-576">平均預計 wideband 從網路接收之音訊的 MOS 分數，包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置特徵。</span><span class="sxs-lookup"><span data-stu-id="db5d0-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="db5d0-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="db5d0-578">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="db5d0-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="db5d0-579">通話的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="db5d0-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db5d0-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="db5d0-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="db5d0-581">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-581">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-582">指出是否已使用音訊 FEC 進行通話。</span><span class="sxs-lookup"><span data-stu-id="db5d0-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db5d0-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="db5d0-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="db5d0-584">稍微</span><span class="sxs-lookup"><span data-stu-id="db5d0-584">bit</span></span></p></td>
<td><p><span data-ttu-id="db5d0-585">表示 p 斷言識別資訊的方向。1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。</span><span class="sxs-lookup"><span data-stu-id="db5d0-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

