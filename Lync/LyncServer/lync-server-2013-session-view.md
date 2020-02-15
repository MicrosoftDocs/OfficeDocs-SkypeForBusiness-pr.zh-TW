---
title: 'Lync Server 2013: Session 檢視'
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
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="9f5b1-102">Lync Server 2013 中的工作階段檢視</span><span class="sxs-lookup"><span data-stu-id="9f5b1-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f5b1-103">_**主題上次修改日期：** 2012年-10-03_</span><span class="sxs-lookup"><span data-stu-id="9f5b1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="9f5b1-104">「工作階段檢視」會儲存在資料庫中有記錄的工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="9f5b1-105">Microsoft Lync Server 2013 中已採用此檢視。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f5b1-106">欄</span><span class="sxs-lookup"><span data-stu-id="9f5b1-106">Column</span></span></th>
<th><span data-ttu-id="9f5b1-107">資料類型</span><span class="sxs-lookup"><span data-stu-id="9f5b1-107">Data Type</span></span></th>
<th><span data-ttu-id="9f5b1-108">詳細資料</span><span class="sxs-lookup"><span data-stu-id="9f5b1-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-111">參考來源為 MediaLine 表格。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="9f5b1-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-113">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-114">如果是會議則為會議 URI，如果是對等工作階段則為 DialogID。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-115">Correlation</span><span class="sxs-lookup"><span data-stu-id="9f5b1-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-116">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-117">工作階段的關聯 ID。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="9f5b1-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-119">位元</span><span class="sxs-lookup"><span data-stu-id="9f5b1-119">bit</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-120">對話類別;0 是 Lync Server 中繼伺服器 leg;1 是中繼伺服器到 PSTN 閘道計量。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="9f5b1-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-122">位元</span><span class="sxs-lookup"><span data-stu-id="9f5b1-122">bit</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-123">指出通話是否經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="9f5b1-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-125">int</span><span class="sxs-lookup"><span data-stu-id="9f5b1-125">int</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-126">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="9f5b1-127">Lync Server 的定義只能有一個值：</span><span class="sxs-lookup"><span data-stu-id="9f5b1-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="9f5b1-128">0x0001 – 預設網路介面卡未知的旁路識別碼</span><span class="sxs-lookup"><span data-stu-id="9f5b1-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-130">datetime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-131">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-133">datetime</span><span class="sxs-lookup"><span data-stu-id="9f5b1-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-134">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="9f5b1-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-137">發話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="9f5b1-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-140">受話者集區 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="9f5b1-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-142">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-143">發話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="9f5b1-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-145">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-146">受話者的 P 聲稱的識別 URI 。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9f5b1-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-149">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="9f5b1-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-152">發話者的端點名稱。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="9f5b1-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-155">發話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9f5b1-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-157">smallint</span><span class="sxs-lookup"><span data-stu-id="9f5b1-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-158">發話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-158">Type of caller’s user agent.</span></span> <span data-ttu-id="9f5b1-159">請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9f5b1-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-162">發話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-162">Category of caller’s user agent.</span></span> <span data-ttu-id="9f5b1-163">請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表 (QoE)</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="9f5b1-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-166">受話者的使用者代理程式字串。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="9f5b1-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-168">smallint</span><span class="sxs-lookup"><span data-stu-id="9f5b1-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-169">受話者的使用者代理程式類型。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-169">Type of user agent for the callee.</span></span> <span data-ttu-id="9f5b1-170">請參閱<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="9f5b1-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-173">受話者的使用者代理程式類別。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-173">User agent category for the callee.</span></span> <span data-ttu-id="9f5b1-174">請參閱<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 資料表 (QoE)</a>如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="9f5b1-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-176">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-177">發話者的 URI。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f5b1-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="9f5b1-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-179">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="9f5b1-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-180">受話者的 URI。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f5b1-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="9f5b1-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-182">int</span><span class="sxs-lookup"><span data-stu-id="9f5b1-182">int</span></span></p></td>
<td><p><span data-ttu-id="9f5b1-183">通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="9f5b1-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

