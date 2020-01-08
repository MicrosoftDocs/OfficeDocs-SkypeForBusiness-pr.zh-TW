---
title: Lync Server 2013：Session 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="f9211-102">Lync Server 2013 中的 Session 表格</span><span class="sxs-lookup"><span data-stu-id="f9211-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9211-103">_**主題上次修改日期：** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="f9211-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="f9211-104">每個記錄代表一個涉及音訊或音訊與影片的會話。</span><span class="sxs-lookup"><span data-stu-id="f9211-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="f9211-105">它包含有關會話的整體資訊。</span><span class="sxs-lookup"><span data-stu-id="f9211-105">It contains overall information about the session.</span></span> <span data-ttu-id="f9211-106">會話是在兩個端點之間定義為音訊或視頻會話初始通訊協定（SIP）對話方塊。</span><span class="sxs-lookup"><span data-stu-id="f9211-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9211-107"><strong>左欄</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f9211-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f9211-109"><strong>索引鍵/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f9211-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9211-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-112">datetime</span><span class="sxs-lookup"><span data-stu-id="f9211-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="f9211-113">首選</span><span class="sxs-lookup"><span data-stu-id="f9211-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9211-114">從<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-116">int</span><span class="sxs-lookup"><span data-stu-id="f9211-116">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-117">首選</span><span class="sxs-lookup"><span data-stu-id="f9211-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="f9211-118">從<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的對話方塊表格中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-120">int</span><span class="sxs-lookup"><span data-stu-id="f9211-120">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-121">外</span><span class="sxs-lookup"><span data-stu-id="f9211-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-122">[會議金鑰]。</span><span class="sxs-lookup"><span data-stu-id="f9211-122">Conference key.</span></span> <span data-ttu-id="f9211-123"><a href="lync-server-2013-conference-table.md">在 Lync Server 2013 的 [會議] 表格中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-125">int</span><span class="sxs-lookup"><span data-stu-id="f9211-125">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-126">外</span><span class="sxs-lookup"><span data-stu-id="f9211-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-127">[關聯金鑰]。</span><span class="sxs-lookup"><span data-stu-id="f9211-127">Correlation key.</span></span> <span data-ttu-id="f9211-128">從<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 的 SessionCorrelation 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-130">稍微</span><span class="sxs-lookup"><span data-stu-id="f9211-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9211-131">對話方塊類別;0是 Lync Server 以進行轉送伺服器腿;1是將伺服器轉送到 PSTN 閘道腿。</span><span class="sxs-lookup"><span data-stu-id="f9211-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-133">稍微</span><span class="sxs-lookup"><span data-stu-id="f9211-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9211-134">該旗標指出通話是否被略過。</span><span class="sxs-lookup"><span data-stu-id="f9211-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-136">int</span><span class="sxs-lookup"><span data-stu-id="f9211-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9211-137">此欄位（如果有的話）會指出即使繞過的旁路 Id，也不會避開通話。</span><span class="sxs-lookup"><span data-stu-id="f9211-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="f9211-138">對於 Lync Server，只會定義一個值。</span><span class="sxs-lookup"><span data-stu-id="f9211-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="f9211-139">0x0001 –預設網路介面卡的旁路旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="f9211-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-140"><strong>開始</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-141">datetime</span><span class="sxs-lookup"><span data-stu-id="f9211-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9211-142">呼叫開始時間。</span><span class="sxs-lookup"><span data-stu-id="f9211-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-144">datetime</span><span class="sxs-lookup"><span data-stu-id="f9211-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f9211-145">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="f9211-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-147">int</span><span class="sxs-lookup"><span data-stu-id="f9211-147">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-148">外</span><span class="sxs-lookup"><span data-stu-id="f9211-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-149">來電者的池子。</span><span class="sxs-lookup"><span data-stu-id="f9211-149">The pool of the caller.</span></span> <span data-ttu-id="f9211-150">從<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 [Pool] 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-152">int</span><span class="sxs-lookup"><span data-stu-id="f9211-152">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-153">外</span><span class="sxs-lookup"><span data-stu-id="f9211-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-154">呼叫接收器的池子。</span><span class="sxs-lookup"><span data-stu-id="f9211-154">The pool of the call receiver.</span></span> <span data-ttu-id="f9211-155">從<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 [Pool] 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-157">int</span><span class="sxs-lookup"><span data-stu-id="f9211-157">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-158">外</span><span class="sxs-lookup"><span data-stu-id="f9211-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-159">接收端點的 SIP p 斷言身分識別（PAI）中的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f9211-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="f9211-160">從<a href="lync-server-2013-user-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f9211-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-162">int</span><span class="sxs-lookup"><span data-stu-id="f9211-162">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-163">外</span><span class="sxs-lookup"><span data-stu-id="f9211-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-164">來電者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f9211-164">Caller’s URI.</span></span> <span data-ttu-id="f9211-165">從<a href="lync-server-2013-user-table.md">Lync Server 2013 的 [使用者] 資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f9211-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-167">int</span><span class="sxs-lookup"><span data-stu-id="f9211-167">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-168">外</span><span class="sxs-lookup"><span data-stu-id="f9211-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-169">來電者的端點。</span><span class="sxs-lookup"><span data-stu-id="f9211-169">Caller’s endpoint.</span></span> <span data-ttu-id="f9211-170">從<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 的端點資料表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f9211-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-172">稍微</span><span class="sxs-lookup"><span data-stu-id="f9211-172">bit</span></span></p></td>
<td><p><span data-ttu-id="f9211-173">外</span><span class="sxs-lookup"><span data-stu-id="f9211-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-174">來電者的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="f9211-174">Caller’s user agent.</span></span> <span data-ttu-id="f9211-175">從<a href="lync-server-2013-useragent-table.md">Lync Server 2013 的 UserAgent 資料表中</a>參考。</span><span class="sxs-lookup"><span data-stu-id="f9211-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-177">Smallint</span><span class="sxs-lookup"><span data-stu-id="f9211-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9211-178">此通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="f9211-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-180">稍微</span><span class="sxs-lookup"><span data-stu-id="f9211-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f9211-181">此欄已棄用，且未在 Microsoft Lync Server 2013 中使用。</span><span class="sxs-lookup"><span data-stu-id="f9211-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f9211-182">相反地，此資訊是在每個媒體的行基底報告。</span><span class="sxs-lookup"><span data-stu-id="f9211-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="f9211-183">如需詳細資訊，請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中</a>的 [MediaLine] 資料表。</span><span class="sxs-lookup"><span data-stu-id="f9211-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-185">int</span><span class="sxs-lookup"><span data-stu-id="f9211-185">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-186">外</span><span class="sxs-lookup"><span data-stu-id="f9211-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-187">P-已斷言-撥打電話之使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="f9211-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="f9211-188">P 斷言身分識別（PAI）是用來傳達撥打電話之使用者的真實身分識別。</span><span class="sxs-lookup"><span data-stu-id="f9211-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-190">int</span><span class="sxs-lookup"><span data-stu-id="f9211-190">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-191">外</span><span class="sxs-lookup"><span data-stu-id="f9211-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-192">接收通話的端點。</span><span class="sxs-lookup"><span data-stu-id="f9211-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9211-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-194">int</span><span class="sxs-lookup"><span data-stu-id="f9211-194">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-195">外</span><span class="sxs-lookup"><span data-stu-id="f9211-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-196">由接收通話的使用者所使用的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="f9211-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="f9211-197">使用者代理代表用戶端端點裝置。</span><span class="sxs-lookup"><span data-stu-id="f9211-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9211-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="f9211-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f9211-199">int</span><span class="sxs-lookup"><span data-stu-id="f9211-199">int</span></span></p></td>
<td><p><span data-ttu-id="f9211-200">外</span><span class="sxs-lookup"><span data-stu-id="f9211-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f9211-201">接收通話之使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="f9211-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

