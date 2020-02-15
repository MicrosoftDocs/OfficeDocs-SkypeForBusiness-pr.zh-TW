---
title: Lync Server 2013： 工作階段表格
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
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="043e8-102">Lync Server 2013 中的工作階段表格</span><span class="sxs-lookup"><span data-stu-id="043e8-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="043e8-103">_**上次修改主題：** 2013年-09-09_</span><span class="sxs-lookup"><span data-stu-id="043e8-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="043e8-104">每筆記錄代表一個包括音訊或音訊和視訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="043e8-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="043e8-105">它包含整體工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="043e8-105">It contains overall information about the session.</span></span> <span data-ttu-id="043e8-106">工作階段被指兩個端點之間的音訊或視訊工作階段初始通訊協定 (SIP) 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="043e8-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="043e8-107"><strong>欄</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="043e8-108"><strong>資料類型</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="043e8-109"><strong>主索引鍵 /</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="043e8-110"><strong>詳細資料</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="043e8-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="043e8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="043e8-113">主要</span><span class="sxs-lookup"><span data-stu-id="043e8-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="043e8-114">參考來源： <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-116">int</span><span class="sxs-lookup"><span data-stu-id="043e8-116">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-117">主要</span><span class="sxs-lookup"><span data-stu-id="043e8-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="043e8-118">參考來源： <a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-120">int</span><span class="sxs-lookup"><span data-stu-id="043e8-120">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-121">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-122">會議索引鍵。</span><span class="sxs-lookup"><span data-stu-id="043e8-122">Conference key.</span></span> <span data-ttu-id="043e8-123">參考來源： <a href="lync-server-2013-conference-table.md">Lync Server 2013 中的會議表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-125">int</span><span class="sxs-lookup"><span data-stu-id="043e8-125">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-126">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-127">相互關聯索引鍵。</span><span class="sxs-lookup"><span data-stu-id="043e8-127">Correlation key.</span></span> <span data-ttu-id="043e8-128">參考來源： <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-130">位元</span><span class="sxs-lookup"><span data-stu-id="043e8-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="043e8-131">對話類別;0 是 Lync Server 中繼伺服器 leg;1 是中繼伺服器到 PSTN 閘道計量。</span><span class="sxs-lookup"><span data-stu-id="043e8-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-133">位元</span><span class="sxs-lookup"><span data-stu-id="043e8-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="043e8-134">指出通話略過如果旗標。</span><span class="sxs-lookup"><span data-stu-id="043e8-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-136">int</span><span class="sxs-lookup"><span data-stu-id="043e8-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="043e8-137">此欄位 (若有) 指出即使旁路識別碼相符，通話為何未經旁路處理。</span><span class="sxs-lookup"><span data-stu-id="043e8-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="043e8-138">Lync Server 的定義只能有一個值。</span><span class="sxs-lookup"><span data-stu-id="043e8-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="043e8-139">0x0001 – 預設網路介面卡未知的旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="043e8-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-141">datetime</span><span class="sxs-lookup"><span data-stu-id="043e8-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="043e8-142">通話開始時間。</span><span class="sxs-lookup"><span data-stu-id="043e8-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-144">datetime</span><span class="sxs-lookup"><span data-stu-id="043e8-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="043e8-145">通話結束時間。</span><span class="sxs-lookup"><span data-stu-id="043e8-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-147">int</span><span class="sxs-lookup"><span data-stu-id="043e8-147">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-148">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-149">發話者的集區。</span><span class="sxs-lookup"><span data-stu-id="043e8-149">The pool of the caller.</span></span> <span data-ttu-id="043e8-150">參考來源： <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-152">int</span><span class="sxs-lookup"><span data-stu-id="043e8-152">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-153">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-154">受話者集區。</span><span class="sxs-lookup"><span data-stu-id="043e8-154">The pool of the call receiver.</span></span> <span data-ttu-id="043e8-155">參考來源： <a href="lync-server-2013-pool-table.md">Lync Server 2013 中的集區資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-157">int</span><span class="sxs-lookup"><span data-stu-id="043e8-157">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-158">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-159">在 [SIP p 聲稱的身分識別 (PAI) 接收方端點的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="043e8-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="043e8-160">參考來源：<a href="lync-server-2013-user-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-162">int</span><span class="sxs-lookup"><span data-stu-id="043e8-162">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-163">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-164">發話者的 URI。</span><span class="sxs-lookup"><span data-stu-id="043e8-164">Caller’s URI.</span></span> <span data-ttu-id="043e8-165">參考來源：<a href="lync-server-2013-user-table.md">使用者在 Lync Server 2013 中的表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-167">int</span><span class="sxs-lookup"><span data-stu-id="043e8-167">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-168">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-169">發話者端點。</span><span class="sxs-lookup"><span data-stu-id="043e8-169">Caller’s endpoint.</span></span> <span data-ttu-id="043e8-170">參考來源： <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的端點資料表</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-172">位元</span><span class="sxs-lookup"><span data-stu-id="043e8-172">bit</span></span></p></td>
<td><p><span data-ttu-id="043e8-173">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-174">發話者的使用者代理程式。</span><span class="sxs-lookup"><span data-stu-id="043e8-174">Caller’s user agent.</span></span> <span data-ttu-id="043e8-175">參考來源： <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表格</a>。</span><span class="sxs-lookup"><span data-stu-id="043e8-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-177">smallint</span><span class="sxs-lookup"><span data-stu-id="043e8-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="043e8-178">此通話的優先順序。</span><span class="sxs-lookup"><span data-stu-id="043e8-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-180">位元</span><span class="sxs-lookup"><span data-stu-id="043e8-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="043e8-181">此資料行已經被取代，並不適用於 Microsoft Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="043e8-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="043e8-182">相反地，這項資訊會報告上的每個媒體行基底。</span><span class="sxs-lookup"><span data-stu-id="043e8-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="043e8-183">請參閱<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的來源： MediaLine table</a> ，如需詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="043e8-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-185">int</span><span class="sxs-lookup"><span data-stu-id="043e8-185">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-186">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-187">P-聲稱的身分識別打電話的使用者。</span><span class="sxs-lookup"><span data-stu-id="043e8-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="043e8-188">P 聲稱的識別 (PAI) 用來傳達使用者打電話，則為 true 身分識別。</span><span class="sxs-lookup"><span data-stu-id="043e8-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-190">int</span><span class="sxs-lookup"><span data-stu-id="043e8-190">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-191">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-192">接到電話的端點。</span><span class="sxs-lookup"><span data-stu-id="043e8-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="043e8-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-194">int</span><span class="sxs-lookup"><span data-stu-id="043e8-194">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-195">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-196">使用者代理程式採用使用者已收到通話。</span><span class="sxs-lookup"><span data-stu-id="043e8-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="043e8-197">使用者代理程式代表的用戶端端點裝置。</span><span class="sxs-lookup"><span data-stu-id="043e8-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="043e8-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="043e8-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="043e8-199">int</span><span class="sxs-lookup"><span data-stu-id="043e8-199">int</span></span></p></td>
<td><p><span data-ttu-id="043e8-200">Foreign</span><span class="sxs-lookup"><span data-stu-id="043e8-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="043e8-201">接到電話之使用者的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="043e8-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

