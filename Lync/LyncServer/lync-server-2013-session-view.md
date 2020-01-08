---
title: Lync Server 2013： [會話] 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="1edec-102">Lync Server 2013 中的 [會話] 視圖</span><span class="sxs-lookup"><span data-stu-id="1edec-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1edec-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1edec-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1edec-104">[會話] 視圖儲存在資料庫中有記錄之會話的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1edec-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="1edec-105">此視圖已在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="1edec-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1edec-106">左欄</span><span class="sxs-lookup"><span data-stu-id="1edec-106">Column</span></span></th>
<th><span data-ttu-id="1edec-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="1edec-107">Data Type</span></span></th>
<th><span data-ttu-id="1edec-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="1edec-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1edec-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="1edec-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="1edec-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1edec-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1edec-111">從 MediaLine 資料表中參照。</span><span class="sxs-lookup"><span data-stu-id="1edec-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="1edec-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="1edec-113">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1edec-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1edec-114">會議 URI （如果這是會議），或 DialogID （如果這是點對點工作階段的話）。</span><span class="sxs-lookup"><span data-stu-id="1edec-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-115">相關</span><span class="sxs-lookup"><span data-stu-id="1edec-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="1edec-116">Varchar （max）</span><span class="sxs-lookup"><span data-stu-id="1edec-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1edec-117">會話的相關識別碼。</span><span class="sxs-lookup"><span data-stu-id="1edec-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="1edec-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="1edec-119">稍微</span><span class="sxs-lookup"><span data-stu-id="1edec-119">bit</span></span></p></td>
<td><p><span data-ttu-id="1edec-120">對話方塊類別;0是 Lync Server 以進行轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="1edec-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="1edec-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="1edec-122">稍微</span><span class="sxs-lookup"><span data-stu-id="1edec-122">bit</span></span></p></td>
<td><p><span data-ttu-id="1edec-123">指出是否已略過通話。</span><span class="sxs-lookup"><span data-stu-id="1edec-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="1edec-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="1edec-125">int</span><span class="sxs-lookup"><span data-stu-id="1edec-125">int</span></span></p></td>
<td><p><span data-ttu-id="1edec-126">此欄位（如果有的話）會指出即使繞過的旁路 Id，也不會避開通話。</span><span class="sxs-lookup"><span data-stu-id="1edec-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="1edec-127">對於 Lync Server，只會定義一個值：</span><span class="sxs-lookup"><span data-stu-id="1edec-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="1edec-128">0x0001 –預設網路介面卡的旁路旁路 ID</span><span class="sxs-lookup"><span data-stu-id="1edec-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-129">開始</span><span class="sxs-lookup"><span data-stu-id="1edec-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="1edec-130">datetime</span><span class="sxs-lookup"><span data-stu-id="1edec-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="1edec-131">呼叫開始時間。</span><span class="sxs-lookup"><span data-stu-id="1edec-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="1edec-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="1edec-133">datetime</span><span class="sxs-lookup"><span data-stu-id="1edec-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="1edec-134">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="1edec-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="1edec-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="1edec-136">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-137">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1edec-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="1edec-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="1edec-139">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-140">被呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1edec-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="1edec-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="1edec-142">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1edec-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1edec-143">來電者 p 斷言身分識別 URI。</span><span class="sxs-lookup"><span data-stu-id="1edec-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="1edec-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="1edec-145">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1edec-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1edec-146">被呼叫者的 p 聲明身分識別 URI。</span><span class="sxs-lookup"><span data-stu-id="1edec-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="1edec-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1edec-148">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-149">來電者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="1edec-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="1edec-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="1edec-151">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-152">來電者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="1edec-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="1edec-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1edec-154">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-155">來電者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="1edec-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1edec-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1edec-157">Smallint</span><span class="sxs-lookup"><span data-stu-id="1edec-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="1edec-158">呼叫者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="1edec-158">Type of caller’s user agent.</span></span> <span data-ttu-id="1edec-159">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="1edec-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1edec-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1edec-161">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="1edec-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="1edec-162">呼叫者的使用者代理類別。</span><span class="sxs-lookup"><span data-stu-id="1edec-162">Category of caller’s user agent.</span></span> <span data-ttu-id="1edec-163">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="1edec-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="1edec-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="1edec-165">Nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1edec-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1edec-166">被呼叫者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="1edec-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="1edec-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="1edec-168">Smallint</span><span class="sxs-lookup"><span data-stu-id="1edec-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="1edec-169">被呼叫者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="1edec-169">Type of user agent for the callee.</span></span> <span data-ttu-id="1edec-170">如需詳細資訊，請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中</a>的 [UserAgent] 資料表。</span><span class="sxs-lookup"><span data-stu-id="1edec-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="1edec-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="1edec-172">Nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="1edec-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="1edec-173">被呼叫者的使用者代理類別。</span><span class="sxs-lookup"><span data-stu-id="1edec-173">User agent category for the callee.</span></span> <span data-ttu-id="1edec-174">如需詳細資訊，請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="1edec-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="1edec-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="1edec-176">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1edec-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1edec-177">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="1edec-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1edec-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="1edec-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="1edec-179">Nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1edec-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1edec-180">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="1edec-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1edec-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="1edec-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="1edec-182">int</span><span class="sxs-lookup"><span data-stu-id="1edec-182">int</span></span></p></td>
<td><p><span data-ttu-id="1edec-183">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="1edec-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

