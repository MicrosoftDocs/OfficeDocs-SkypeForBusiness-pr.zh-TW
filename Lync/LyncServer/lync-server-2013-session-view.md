---
title: Lync Server 2013：會話視圖
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
ms.openlocfilehash: 30183ffde7380b5029ac458f102eaf81ecee914b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510090"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b4c9b-102">Lync Server 2013 中的會話視圖</span><span class="sxs-lookup"><span data-stu-id="b4c9b-102">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4c9b-103">_**主題上次修改日期：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b4c9b-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b4c9b-104">「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b4c9b-105">此視圖已引進于 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4c9b-106">欄</span><span class="sxs-lookup"><span data-stu-id="b4c9b-106">Column</span></span></th>
<th><span data-ttu-id="b4c9b-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="b4c9b-107">Data Type</span></span></th>
<th><span data-ttu-id="b4c9b-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="b4c9b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-111">參考來源為 MediaLine 表格。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b4c9b-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-113">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-114">如果是會議則為會議 URI，如果是對等工作階段則為 DialogID。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="b4c9b-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-116">Varchar (max) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-117">工作階段的關聯 ID。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b4c9b-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-119">位</span><span class="sxs-lookup"><span data-stu-id="b4c9b-119">bit</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-120">對話方塊類別;0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b4c9b-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-122">位</span><span class="sxs-lookup"><span data-stu-id="b4c9b-122">bit</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-123">指出通話是否經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b4c9b-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-125">int</span><span class="sxs-lookup"><span data-stu-id="b4c9b-125">int</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-126">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b4c9b-127">對於 Lync Server，只會定義一個值：</span><span class="sxs-lookup"><span data-stu-id="b4c9b-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b4c9b-128">0x0001 – 預設網路介面卡未知的旁路識別碼</span><span class="sxs-lookup"><span data-stu-id="b4c9b-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-130">datetime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-131">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-133">datetime</span><span class="sxs-lookup"><span data-stu-id="b4c9b-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-134">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b4c9b-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-136">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-137">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b4c9b-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-139">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-140">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b4c9b-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-142">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-143">發話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b4c9b-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-145">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-146">受話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b4c9b-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-148">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-149">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b4c9b-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-151">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-152">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b4c9b-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-154">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-155">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b4c9b-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-157">Smallint</span><span class="sxs-lookup"><span data-stu-id="b4c9b-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-158">發話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-158">Type of caller’s user agent.</span></span> <span data-ttu-id="b4c9b-159">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b4c9b-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b4c9b-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-162">發話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-162">Category of caller’s user agent.</span></span> <span data-ttu-id="b4c9b-163">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b4c9b-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-165">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-166">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b4c9b-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-168">Smallint</span><span class="sxs-lookup"><span data-stu-id="b4c9b-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-169">受話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-169">Type of user agent for the callee.</span></span> <span data-ttu-id="b4c9b-170">如需詳細資訊，請參閱 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b4c9b-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b4c9b-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-173">受話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-173">User agent category for the callee.</span></span> <span data-ttu-id="b4c9b-174">如需詳細資訊，請參閱 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表格 (Lync Server 2013 中的 QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b4c9b-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-176">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-177">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4c9b-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b4c9b-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-179">Nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b4c9b-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-180">被呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4c9b-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="b4c9b-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-182">int</span><span class="sxs-lookup"><span data-stu-id="b4c9b-182">int</span></span></p></td>
<td><p><span data-ttu-id="b4c9b-183">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b4c9b-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

