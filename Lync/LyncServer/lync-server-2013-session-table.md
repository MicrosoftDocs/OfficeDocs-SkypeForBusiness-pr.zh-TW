---
title: Lync Server 2013：會話表格
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
ms.openlocfilehash: d74d2732d2f8ad293450f4945eef00bccb9a572d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510080"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="b033f-102">Lync Server 2013 中的會話表格</span><span class="sxs-lookup"><span data-stu-id="b033f-102">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b033f-103">_**主題上次修改日期：** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="b033f-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="b033f-104">每筆記錄代表一個包含音訊或音訊和影片的會話。</span><span class="sxs-lookup"><span data-stu-id="b033f-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="b033f-105">包含有關會話的整體資訊。</span><span class="sxs-lookup"><span data-stu-id="b033f-105">It contains overall information about the session.</span></span> <span data-ttu-id="b033f-106">會話是在兩個端點之間的 (SIP) ] 對話方塊中定義為音訊或視頻會話初始通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b033f-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b033f-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="b033f-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="b033f-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="b033f-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b033f-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b033f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b033f-113">主要</span><span class="sxs-lookup"><span data-stu-id="b033f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b033f-114">從 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-116">int</span><span class="sxs-lookup"><span data-stu-id="b033f-116">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-117">主要</span><span class="sxs-lookup"><span data-stu-id="b033f-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="b033f-118">從 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-120">int</span><span class="sxs-lookup"><span data-stu-id="b033f-120">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-122">會議金鑰。</span><span class="sxs-lookup"><span data-stu-id="b033f-122">Conference key.</span></span> <span data-ttu-id="b033f-123"><a href="lync-server-2013-conference-table.md">在 Lync Server 2013 中從會議表格</a>參考。</span><span class="sxs-lookup"><span data-stu-id="b033f-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-125">int</span><span class="sxs-lookup"><span data-stu-id="b033f-125">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-126">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-127">相關機碼。</span><span class="sxs-lookup"><span data-stu-id="b033f-127">Correlation key.</span></span> <span data-ttu-id="b033f-128">從 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-130">位</span><span class="sxs-lookup"><span data-stu-id="b033f-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b033f-131">對話方塊類別;0是 Lync Server 的轉送伺服器腿;1是轉送伺服器到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="b033f-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-133">位</span><span class="sxs-lookup"><span data-stu-id="b033f-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b033f-134">指示是否略過呼叫的旗標。</span><span class="sxs-lookup"><span data-stu-id="b033f-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-136">int</span><span class="sxs-lookup"><span data-stu-id="b033f-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b033f-137">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="b033f-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b033f-138">對於 Lync Server，只會定義一個值。</span><span class="sxs-lookup"><span data-stu-id="b033f-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="b033f-139">0x0001 –預設網路介面卡的未知旁路識別碼。</span><span class="sxs-lookup"><span data-stu-id="b033f-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-141">datetime</span><span class="sxs-lookup"><span data-stu-id="b033f-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b033f-142">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="b033f-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-144">datetime</span><span class="sxs-lookup"><span data-stu-id="b033f-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b033f-145">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="b033f-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-147">int</span><span class="sxs-lookup"><span data-stu-id="b033f-147">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-148">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-149">來電者的集區。</span><span class="sxs-lookup"><span data-stu-id="b033f-149">The pool of the caller.</span></span> <span data-ttu-id="b033f-150">從 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的集區資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-152">int</span><span class="sxs-lookup"><span data-stu-id="b033f-152">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-153">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-154">呼叫接收器的集區。</span><span class="sxs-lookup"><span data-stu-id="b033f-154">The pool of the call receiver.</span></span> <span data-ttu-id="b033f-155">從 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的集區資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-157">int</span><span class="sxs-lookup"><span data-stu-id="b033f-157">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-158">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-159">SIP p-宣稱身分識別 (PAI) 接收方端點的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="b033f-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="b033f-160"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的使用者資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-162">int</span><span class="sxs-lookup"><span data-stu-id="b033f-162">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-163">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-164">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b033f-164">Caller’s URI.</span></span> <span data-ttu-id="b033f-165"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的使用者資料表中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-167">int</span><span class="sxs-lookup"><span data-stu-id="b033f-167">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-168">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-169">來電者的端點。</span><span class="sxs-lookup"><span data-stu-id="b033f-169">Caller’s endpoint.</span></span> <span data-ttu-id="b033f-170">從 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點表</a>參考。</span><span class="sxs-lookup"><span data-stu-id="b033f-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-172">位</span><span class="sxs-lookup"><span data-stu-id="b033f-172">bit</span></span></p></td>
<td><p><span data-ttu-id="b033f-173">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-174">來電者的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="b033f-174">Caller’s user agent.</span></span> <span data-ttu-id="b033f-175">從 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 的 UserAgent 表格中</a>參照。</span><span class="sxs-lookup"><span data-stu-id="b033f-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-177">Smallint</span><span class="sxs-lookup"><span data-stu-id="b033f-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b033f-178">此通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b033f-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-180">位</span><span class="sxs-lookup"><span data-stu-id="b033f-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b033f-181">此欄已被取代，而且不會用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b033f-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="b033f-182">相反地，會在每個媒體行基礎上報告此資訊。</span><span class="sxs-lookup"><span data-stu-id="b033f-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="b033f-183">如需詳細資訊，請參閱 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表格</a> 。</span><span class="sxs-lookup"><span data-stu-id="b033f-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-185">int</span><span class="sxs-lookup"><span data-stu-id="b033f-185">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-186">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-187">撥打通話之使用者的 P-Asserted-Identity。</span><span class="sxs-lookup"><span data-stu-id="b033f-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="b033f-188">P-Asserted-Identity (PAI) 是用來傳達撥打通話之使用者的真實身分識別。</span><span class="sxs-lookup"><span data-stu-id="b033f-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-190">int</span><span class="sxs-lookup"><span data-stu-id="b033f-190">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-191">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-192">接收通話的端點。</span><span class="sxs-lookup"><span data-stu-id="b033f-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b033f-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-194">int</span><span class="sxs-lookup"><span data-stu-id="b033f-194">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-195">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-196">接收通話之使用者所採用的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="b033f-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="b033f-197">使用者代理程式代表用戶端端點裝置。</span><span class="sxs-lookup"><span data-stu-id="b033f-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b033f-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="b033f-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b033f-199">int</span><span class="sxs-lookup"><span data-stu-id="b033f-199">int</span></span></p></td>
<td><p><span data-ttu-id="b033f-200">Foreign</span><span class="sxs-lookup"><span data-stu-id="b033f-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="b033f-201">接收通話之使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="b033f-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

