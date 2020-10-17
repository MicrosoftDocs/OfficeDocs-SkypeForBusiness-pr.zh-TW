---
title: Lync Server 2013：會話視圖
description: Lync Server 2013：會話視圖。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545009"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="2b09e-103">Lync Server 2013 中的會話視圖</span><span class="sxs-lookup"><span data-stu-id="2b09e-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b09e-104">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2b09e-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2b09e-105">「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="2b09e-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="2b09e-106">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="2b09e-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b09e-107">欄</span><span class="sxs-lookup"><span data-stu-id="2b09e-107">Column</span></span></th>
<th><span data-ttu-id="2b09e-108">資料類型</span><span class="sxs-lookup"><span data-stu-id="2b09e-108">Data Type</span></span></th>
<th><span data-ttu-id="2b09e-109">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2b09e-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="2b09e-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-111">datetime</span><span class="sxs-lookup"><span data-stu-id="2b09e-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-112">參考來源為 MediaLine 表格。</span><span class="sxs-lookup"><span data-stu-id="2b09e-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="2b09e-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="2b09e-114">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2b09e-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-115">如果是會議則為會議 URI，如果是對等工作階段則為 DialogID。</span><span class="sxs-lookup"><span data-stu-id="2b09e-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-116">Correlation</span><span class="sxs-lookup"><span data-stu-id="2b09e-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="2b09e-117">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="2b09e-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-118">工作階段的關聯 ID。</span><span class="sxs-lookup"><span data-stu-id="2b09e-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="2b09e-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="2b09e-120">位</span><span class="sxs-lookup"><span data-stu-id="2b09e-120">bit</span></span></p></td>
<td><p><span data-ttu-id="2b09e-121">對話方塊類別;0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="2b09e-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="2b09e-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="2b09e-123">位</span><span class="sxs-lookup"><span data-stu-id="2b09e-123">bit</span></span></p></td>
<td><p><span data-ttu-id="2b09e-124">指出通話是否經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="2b09e-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="2b09e-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="2b09e-126">int</span><span class="sxs-lookup"><span data-stu-id="2b09e-126">int</span></span></p></td>
<td><p><span data-ttu-id="2b09e-127">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="2b09e-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="2b09e-128">對於 Lync Server，只會定義一個值：</span><span class="sxs-lookup"><span data-stu-id="2b09e-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="2b09e-129">0x0001 – 預設網路介面卡未知的旁路識別碼</span><span class="sxs-lookup"><span data-stu-id="2b09e-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="2b09e-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-131">datetime</span><span class="sxs-lookup"><span data-stu-id="2b09e-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-132">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="2b09e-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="2b09e-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-134">datetime</span><span class="sxs-lookup"><span data-stu-id="2b09e-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b09e-135">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="2b09e-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="2b09e-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="2b09e-137">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-138">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b09e-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="2b09e-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="2b09e-140">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-141">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="2b09e-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="2b09e-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="2b09e-143">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2b09e-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-144">發話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="2b09e-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="2b09e-146">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2b09e-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-147">受話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b09e-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="2b09e-149">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-150">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="2b09e-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="2b09e-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="2b09e-152">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-153">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="2b09e-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="2b09e-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="2b09e-155">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-156">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="2b09e-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="2b09e-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="2b09e-158">Smallint</span><span class="sxs-lookup"><span data-stu-id="2b09e-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b09e-159">發話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="2b09e-159">Type of caller’s user agent.</span></span> <span data-ttu-id="2b09e-160">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="2b09e-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="2b09e-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b09e-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-163">發話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="2b09e-163">Category of caller’s user agent.</span></span> <span data-ttu-id="2b09e-164">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="2b09e-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="2b09e-166">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="2b09e-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-167">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="2b09e-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="2b09e-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="2b09e-169">Smallint</span><span class="sxs-lookup"><span data-stu-id="2b09e-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b09e-170">受話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="2b09e-170">Type of user agent for the callee.</span></span> <span data-ttu-id="2b09e-171">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="2b09e-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="2b09e-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b09e-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-174">受話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="2b09e-174">User agent category for the callee.</span></span> <span data-ttu-id="2b09e-175">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="2b09e-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="2b09e-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="2b09e-177">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2b09e-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-178">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="2b09e-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b09e-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="2b09e-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="2b09e-180">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="2b09e-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b09e-181">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="2b09e-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b09e-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="2b09e-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="2b09e-183">int</span><span class="sxs-lookup"><span data-stu-id="2b09e-183">int</span></span></p></td>
<td><p><span data-ttu-id="2b09e-184">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="2b09e-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

