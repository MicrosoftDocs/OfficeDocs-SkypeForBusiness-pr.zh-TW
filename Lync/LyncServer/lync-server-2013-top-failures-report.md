---
title: Lync Server 2013：熱門失敗報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 094f5034951e20d48b05c8772698ae2983492509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="998be-102">Lync Server 2013 中的 [熱門失敗] 報告</span><span class="sxs-lookup"><span data-stu-id="998be-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="998be-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="998be-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="998be-104">[熱門失敗] 報告可讓您查看最常報告的失敗及其隨時間變化的趨勢。</span><span class="sxs-lookup"><span data-stu-id="998be-104">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time.</span></span> <span data-ttu-id="998be-105">失敗是以下列兩個度量的組合為基礎：</span><span class="sxs-lookup"><span data-stu-id="998be-105">Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="998be-106">**診斷 ID**。</span><span class="sxs-lookup"><span data-stu-id="998be-106">**Diagnostic ID**.</span></span> <span data-ttu-id="998be-107">附加至 SIP 訊息的唯一識別碼（以 ms diagnostics 標頭形式）。</span><span class="sxs-lookup"><span data-stu-id="998be-107">Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message.</span></span> <span data-ttu-id="998be-108">診斷識別碼可在疑難排解呼叫相關問題時提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="998be-108">Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="998be-109">**回應代碼**。</span><span class="sxs-lookup"><span data-stu-id="998be-109">**Response code**.</span></span> <span data-ttu-id="998be-110">在 SIP 通訊會話中使用回應代碼來回應 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="998be-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="998be-111">例如，如果 Ken 將邀請要求傳送給 Pilar 方（也就是，假設 Ken Myer 呼叫 Pilar 方）。</span><span class="sxs-lookup"><span data-stu-id="998be-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="998be-112">如果 Pilar 答案，她的手機會傳送回應碼200（確定），讓 Ken 手機知道 Pilar 已回答問題。</span><span class="sxs-lookup"><span data-stu-id="998be-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="998be-113">[熱門失敗] 報告只包含回應通話失敗時所傳送的回應碼;Lync Server 不會追蹤通話期間發出的所有回應碼。</span><span class="sxs-lookup"><span data-stu-id="998be-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="998be-114">資訊不只會報告發生失敗的會話總數，以及因失敗而受到影響的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="998be-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="998be-115">存取 [熱門失敗] 報告</span><span class="sxs-lookup"><span data-stu-id="998be-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="998be-116">[熱門失敗] 報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="998be-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="998be-117">按一下報告的會話指標會將您帶到[Lync Server 2013 的失敗發佈報告](lync-server-2013-failure-distribution-report.md)。</span><span class="sxs-lookup"><span data-stu-id="998be-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="998be-118">充分利用 [熱門失敗] 報告</span><span class="sxs-lookup"><span data-stu-id="998be-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="998be-119">[熱門失敗] 報告在某種情況下是不尋常的：它可讓您一次篩選多達5個診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="998be-119">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once.</span></span> <span data-ttu-id="998be-120">（通常您只能篩選一個專案，例如一個使用者 SIP 位址（一次）。若要篩選多個診斷識別碼，只要在 [診斷識別碼] 方塊中輸入每個識別碼，即可使用逗號分隔識別碼。</span><span class="sxs-lookup"><span data-stu-id="998be-120">(Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas.</span></span> <span data-ttu-id="998be-121">（如果您想要的話，您可以在每個逗號後留一個空格）。例如：</span><span class="sxs-lookup"><span data-stu-id="998be-121">(If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="998be-122">1011、2412、1033、52116、1008</span><span class="sxs-lookup"><span data-stu-id="998be-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="998be-123">請執行這項作業，而且只會顯示那些五個診斷識別碼中至少有一個報告的失敗通話。</span><span class="sxs-lookup"><span data-stu-id="998be-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="998be-124">如果您將滑鼠放在回應代碼上，您會看到工具提示，告訴您有問題的回應碼。</span><span class="sxs-lookup"><span data-stu-id="998be-124">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means.</span></span> <span data-ttu-id="998be-125">例如，如果您將滑鼠放在回應代碼486上，您會看到以下訊息：</span><span class="sxs-lookup"><span data-stu-id="998be-125">For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="998be-126">在這裡忙碌。</span><span class="sxs-lookup"><span data-stu-id="998be-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="998be-127">濾鏡</span><span class="sxs-lookup"><span data-stu-id="998be-127">Filters</span></span>

<span data-ttu-id="998be-128">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="998be-128">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="998be-129">例如，[熱門失敗] 報告可讓您根據活動類型（點對點工作階段或會議會話）或隨附失敗會話的 SIP 回應程式碼，來篩選傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="998be-129">For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session.</span></span> <span data-ttu-id="998be-130">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="998be-130">You can also choose how data should be grouped.</span></span> <span data-ttu-id="998be-131">在這種情況下，使用方式會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="998be-131">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="998be-132">下表列出可用於 [熱門失敗] 報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="998be-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="998be-133">[熱門失敗] 報表篩選</span><span class="sxs-lookup"><span data-stu-id="998be-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="998be-134">名稱</span><span class="sxs-lookup"><span data-stu-id="998be-134">Name</span></span></th>
<th><span data-ttu-id="998be-135">描述</span><span class="sxs-lookup"><span data-stu-id="998be-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="998be-136"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="998be-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-137">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="998be-137">Start date/time for the time range.</span></span> <span data-ttu-id="998be-138">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="998be-138">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="998be-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="998be-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="998be-140">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="998be-140">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="998be-141">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="998be-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="998be-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="998be-142">7/7/2012</span></span></p>
<p><span data-ttu-id="998be-143">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="998be-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="998be-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="998be-144">7/3/2012</span></span></p>
<p><span data-ttu-id="998be-145">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="998be-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-146"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="998be-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-147">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="998be-147">End date/time for the time range.</span></span> <span data-ttu-id="998be-148">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="998be-148">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="998be-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="998be-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="998be-150">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="998be-150">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="998be-151">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="998be-151">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="998be-152">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="998be-152">7/7/2012</span></span></p>
<p><span data-ttu-id="998be-153">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="998be-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="998be-154">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="998be-154">7/3/2012</span></span></p>
<p><span data-ttu-id="998be-155">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="998be-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998be-156"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="998be-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-157">活動類型。</span><span class="sxs-lookup"><span data-stu-id="998be-157">Type of activity.</span></span> <span data-ttu-id="998be-158">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="998be-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="998be-159">同時</span><span class="sxs-lookup"><span data-stu-id="998be-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="998be-160">對等</span><span class="sxs-lookup"><span data-stu-id="998be-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="998be-161">會議</span><span class="sxs-lookup"><span data-stu-id="998be-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-162"><strong>模態</strong></span><span class="sxs-lookup"><span data-stu-id="998be-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-163">目前唯一可用的選項是<strong>[全部]</strong>。</span><span class="sxs-lookup"><span data-stu-id="998be-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998be-164"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="998be-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-165">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="998be-165">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="998be-166">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="998be-166">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="998be-167">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="998be-167">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-168"><strong>類別</strong></span><span class="sxs-lookup"><span data-stu-id="998be-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-169">遇到的失敗類型。</span><span class="sxs-lookup"><span data-stu-id="998be-169">Type of failure experienced.</span></span> <span data-ttu-id="998be-170">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="998be-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="998be-171">預期與意外失敗</span><span class="sxs-lookup"><span data-stu-id="998be-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="998be-172">意外失敗</span><span class="sxs-lookup"><span data-stu-id="998be-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="998be-173">&quot;預期的失敗&quot;是預期發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="998be-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="998be-174">例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="998be-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="998be-175">發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。</span><span class="sxs-lookup"><span data-stu-id="998be-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="998be-176">例如，如果來電者停留在 [保留] 上，就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="998be-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="998be-177">如果發生這種情況，就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="998be-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998be-178"><strong>回應代碼</strong></span><span class="sxs-lookup"><span data-stu-id="998be-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-179">在會議失敗時傳送 SIP 回應代碼。</span><span class="sxs-lookup"><span data-stu-id="998be-179">SIP response code sent when the conference failed.</span></span> <span data-ttu-id="998be-180">輸入整個回應代碼（例如：</span><span class="sxs-lookup"><span data-stu-id="998be-180">Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="998be-181">400</span><span class="sxs-lookup"><span data-stu-id="998be-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-182"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="998be-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-183">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="998be-183">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="998be-184">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="998be-184">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="998be-185">指標</span><span class="sxs-lookup"><span data-stu-id="998be-185">Metrics</span></span>

<span data-ttu-id="998be-186">下表列出 [熱門失敗] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="998be-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="998be-187">熱門失敗報告度量單位</span><span class="sxs-lookup"><span data-stu-id="998be-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="998be-188">名稱</span><span class="sxs-lookup"><span data-stu-id="998be-188">Name</span></span></th>
<th><span data-ttu-id="998be-189">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="998be-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="998be-190">描述</span><span class="sxs-lookup"><span data-stu-id="998be-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="998be-191"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="998be-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-192">是</span><span class="sxs-lookup"><span data-stu-id="998be-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="998be-193">根據所報告的會話數進行相對等級。</span><span class="sxs-lookup"><span data-stu-id="998be-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-194"><strong>報告的會話</strong></span><span class="sxs-lookup"><span data-stu-id="998be-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-195">是</span><span class="sxs-lookup"><span data-stu-id="998be-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="998be-196">根據診斷識別碼和 SIP 回應代碼，失敗的會話總數。</span><span class="sxs-lookup"><span data-stu-id="998be-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998be-197"><strong>受影響的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="998be-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-198">是</span><span class="sxs-lookup"><span data-stu-id="998be-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="998be-199">受失敗會話影響的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="998be-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="998be-200"><strong>失敗資訊</strong></span><span class="sxs-lookup"><span data-stu-id="998be-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-201">否</span><span class="sxs-lookup"><span data-stu-id="998be-201">No</span></span></p></td>
<td><p><span data-ttu-id="998be-202">失敗的詳細資訊，包括診斷識別碼、SIP 回應代碼，以及會話失敗原因的描述。</span><span class="sxs-lookup"><span data-stu-id="998be-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="998be-203"><strong>過去的趨勢</strong></span><span class="sxs-lookup"><span data-stu-id="998be-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="998be-204">否</span><span class="sxs-lookup"><span data-stu-id="998be-204">No</span></span></p></td>
<td><p><span data-ttu-id="998be-205">圖形在一段時間內失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="998be-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

