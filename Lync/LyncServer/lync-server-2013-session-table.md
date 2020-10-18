---
title: Lync Server 2013：會話表格
description: Lync Server 2013：會話表格。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576449"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="f71f0-103">Lync Server 2013 中的會話表格</span><span class="sxs-lookup"><span data-stu-id="f71f0-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f71f0-104">_**主題上次修改日期：** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="f71f0-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="f71f0-105">每筆記錄代表一個包含音訊或音訊和影片的會話。</span><span class="sxs-lookup"><span data-stu-id="f71f0-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="f71f0-106">包含有關會話的整體資訊。</span><span class="sxs-lookup"><span data-stu-id="f71f0-106">It contains overall information about the session.</span></span> <span data-ttu-id="f71f0-107">會話是在兩個端點之間的 (SIP) ] 對話方塊中定義為音訊或視頻會話初始通訊協定。</span><span class="sxs-lookup"><span data-stu-id="f71f0-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f71f0-108"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f71f0-109"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f71f0-110"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f71f0-111"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-113">datetime</span><span class="sxs-lookup"><span data-stu-id="f71f0-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="f71f0-114">主要</span><span class="sxs-lookup"><span data-stu-id="f71f0-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="f71f0-115">從 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-117">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-117">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-118">主要</span><span class="sxs-lookup"><span data-stu-id="f71f0-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="f71f0-119">從 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-121">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-121">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-122">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-123">會議金鑰。</span><span class="sxs-lookup"><span data-stu-id="f71f0-123">Conference key.</span></span> <span data-ttu-id="f71f0-124"><a href="lync-server-2013-conference-table.md">在 Lync Server 2013 中從會議表格</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f71f0-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-126">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-126">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-127">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-128">相關機碼。</span><span class="sxs-lookup"><span data-stu-id="f71f0-128">Correlation key.</span></span> <span data-ttu-id="f71f0-129">從 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-131">位</span><span class="sxs-lookup"><span data-stu-id="f71f0-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f71f0-132">對話方塊類別;0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="f71f0-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-134">位</span><span class="sxs-lookup"><span data-stu-id="f71f0-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71f0-135">指示是否略過呼叫的旗標。</span><span class="sxs-lookup"><span data-stu-id="f71f0-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-137">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71f0-138">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="f71f0-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="f71f0-139">對於 Lync Server，只會定義一個值。</span><span class="sxs-lookup"><span data-stu-id="f71f0-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="f71f0-140">0x0001 –預設網路介面卡的未知旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="f71f0-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-142">datetime</span><span class="sxs-lookup"><span data-stu-id="f71f0-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f71f0-143">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="f71f0-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-145">datetime</span><span class="sxs-lookup"><span data-stu-id="f71f0-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f71f0-146">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="f71f0-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-148">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-148">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-149">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-150">來電者的集區。</span><span class="sxs-lookup"><span data-stu-id="f71f0-150">The pool of the caller.</span></span> <span data-ttu-id="f71f0-151">從 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的集區資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-153">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-153">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-154">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-155">呼叫接收器的集區。</span><span class="sxs-lookup"><span data-stu-id="f71f0-155">The pool of the call receiver.</span></span> <span data-ttu-id="f71f0-156">從 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的集區資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-158">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-158">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-159">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-160">SIP p-宣稱身分識別 (PAI) 接收方端點的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f71f0-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="f71f0-161"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的使用者資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-163">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-163">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-164">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-165">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f71f0-165">Caller’s URI.</span></span> <span data-ttu-id="f71f0-166"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的使用者資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-168">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-168">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-169">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-170">來電者的端點。</span><span class="sxs-lookup"><span data-stu-id="f71f0-170">Caller’s endpoint.</span></span> <span data-ttu-id="f71f0-171">從 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f71f0-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-173">位</span><span class="sxs-lookup"><span data-stu-id="f71f0-173">bit</span></span></p></td>
<td><p><span data-ttu-id="f71f0-174">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-175">來電者的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="f71f0-175">Caller’s user agent.</span></span> <span data-ttu-id="f71f0-176">從 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 的 UserAgent 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="f71f0-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-178">Smallint</span><span class="sxs-lookup"><span data-stu-id="f71f0-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71f0-179">此通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f71f0-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-181">位</span><span class="sxs-lookup"><span data-stu-id="f71f0-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f71f0-182">此欄已被取代，而且不會用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f71f0-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f71f0-183">相反地，會在每個媒體行基礎上報告此資訊。</span><span class="sxs-lookup"><span data-stu-id="f71f0-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="f71f0-184">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="f71f0-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-186">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-186">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-187">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-188">撥打通話之使用者的 P-Asserted-Identity。</span><span class="sxs-lookup"><span data-stu-id="f71f0-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="f71f0-189">P-Asserted-Identity (PAI) 是用來傳達撥打通話之使用者的真實身分識別。</span><span class="sxs-lookup"><span data-stu-id="f71f0-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-191">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-191">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-192">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-193">接收通話的端點。</span><span class="sxs-lookup"><span data-stu-id="f71f0-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f71f0-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-195">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-195">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-196">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-197">接收通話之使用者所採用的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="f71f0-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="f71f0-198">使用者代理程式代表用戶端端點裝置。</span><span class="sxs-lookup"><span data-stu-id="f71f0-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f71f0-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="f71f0-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f71f0-200">int</span><span class="sxs-lookup"><span data-stu-id="f71f0-200">int</span></span></p></td>
<td><p><span data-ttu-id="f71f0-201">Foreign</span><span class="sxs-lookup"><span data-stu-id="f71f0-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f71f0-202">接收通話之使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f71f0-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

