---
title: Lync Server 2013： 最大失敗報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Top Failures Report
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558640(v=OCS.15)
ms:contentKeyID: 48184021
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972c9e97015f5a39ace3cf1fc68051cc0afcc988
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193636"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="top-failures-report-in-lync-server-2013"></a><span data-ttu-id="13d6b-102">Lync Server 2013 中的最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="13d6b-102">Top Failures Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13d6b-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="13d6b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="13d6b-p101">Top Failures 報告列出最常發生的失敗及其在一段時間後的趨勢。</span><span class="sxs-lookup"><span data-stu-id="13d6b-p101">The Top Failures Report provides a look at the most-commonly reported failures and their trends over time. Failures are based on a combination of the following two metrics:</span></span>

  - <span data-ttu-id="13d6b-p102">**診斷 ID**。附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)。診斷 ID 可以在疑難排解通話相關錯誤時提供實用的資訊。</span><span class="sxs-lookup"><span data-stu-id="13d6b-p102">**Diagnostic ID**. Unique identifier (in the form of an ms-diagnostics header) that is attached to a SIP message. Diagnostic IDs provide information useful in troubleshooting call-related problems.</span></span>

  - <span data-ttu-id="13d6b-109">**回應碼**。</span><span class="sxs-lookup"><span data-stu-id="13d6b-109">**Response code**.</span></span> <span data-ttu-id="13d6b-110">回應碼適用於 SIP 通訊工作階段來回應 SIP 要求。</span><span class="sxs-lookup"><span data-stu-id="13d6b-110">Response codes are used in SIP communication sessions to respond to SIP requests.</span></span> <span data-ttu-id="13d6b-111">例如，假設 Ken 邀請將要求傳送至為 Pilar Ackerman （也就是假設 Ken Myer 呼叫為 Pilar Ackerman）。</span><span class="sxs-lookup"><span data-stu-id="13d6b-111">For example, suppose Ken sends the INVITE request to Pilar Ackerman (that is, suppose Ken Myer calls Pilar Ackerman).</span></span> <span data-ttu-id="13d6b-112">如果 Pilar 接聽，其電話將傳送給您知道有回答 Pilar Ken 的電話，讓回應碼 200 (OK)。</span><span class="sxs-lookup"><span data-stu-id="13d6b-112">If Pilar answers, her phone will send the response code 200 (OK), letting Ken's phone know that Pilar has answered.</span></span> <span data-ttu-id="13d6b-113">最大失敗報告只包含已傳送回應通話失敗; 回應碼Lync Server 不會不追蹤的發出的通話過程中的所有回應碼。</span><span class="sxs-lookup"><span data-stu-id="13d6b-113">The Top Failures Report only includes response codes that were sent in response to a call failure; Lync Server does not keep track of all the response codes issued during the course of a call.</span></span>

<span data-ttu-id="13d6b-114">資訊回報內容不僅有發生失敗的工作階段總數，還有因失敗受到影響的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="13d6b-114">Information is reported not only for the total number of sessions where a failure occurred but also for the total number of users who were impacted by the failure.</span></span>

<div>

## <a name="accessing-the-top-failures-report"></a><span data-ttu-id="13d6b-115">存取最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="13d6b-115">Accessing the Top Failures Report</span></span>

<span data-ttu-id="13d6b-116">可以從監視報告首頁存取最大失敗報告。</span><span class="sxs-lookup"><span data-stu-id="13d6b-116">The Top Failures Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="13d6b-117">按一下 [Reported 工作階段計量，將帶您前往[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)。</span><span class="sxs-lookup"><span data-stu-id="13d6b-117">Clicking the Reported sessions metric will take you to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-top-failures-report"></a><span data-ttu-id="13d6b-118">善用最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="13d6b-118">Making the Best Use of the Top Failures Report</span></span>

<span data-ttu-id="13d6b-p105">在某方面而言，最大失敗報告顯得十分特別：此報告最多能讓您一次篩選 5 個診斷 ID (通常一次只能篩選一個項目，例如一個使用者 SIP 位址)。若要篩選多個診斷 ID，只要在「診斷 ID」方塊中輸入各個 ID，並以逗號區隔即可 (也可以在每個逗號後面留下空格)。例如：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p105">The Top Failures Report is unusual in one regard: it allows you to filter on as many as 5 diagnostic IDs at once. (Typically you can only filter on one item – such as one user SIP address – at a time.) To filter on multiple diagnostic IDs, simply enter each ID in the Diagnostic IDs box, separating the IDs by using commas. (If you want to, you can leave a blank space after each comma.) For example:</span></span>

<span data-ttu-id="13d6b-122">1011, 2412, 1033, 52116, 1008</span><span class="sxs-lookup"><span data-stu-id="13d6b-122">1011, 2412, 1033, 52116, 1008</span></span>

<span data-ttu-id="13d6b-123">完成後，只會顯示回報五個診斷 ID 中至少有一個 ID 的失敗通話。</span><span class="sxs-lookup"><span data-stu-id="13d6b-123">Do that, and only failed calls that reported at least one of those five diagnostic IDs will be displayed.</span></span>

<span data-ttu-id="13d6b-p106">如果您將滑鼠移到回應碼時會看到工具提示，說明有問題的回應代碼所代表的涵義。例如將滑鼠移到回應碼 486，會看到此訊息：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p106">If you hold your mouse over a Response code you'll see a tooltip that tells you what the Response code in question means. For example, if you hold the mouse over the Response code 486 you'll see this message:</span></span>

<span data-ttu-id="13d6b-126">此處非常忙碌。</span><span class="sxs-lookup"><span data-stu-id="13d6b-126">Busy Here.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="13d6b-127">篩選</span><span class="sxs-lookup"><span data-stu-id="13d6b-127">Filters</span></span>

<span data-ttu-id="13d6b-p107">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，「最大失敗報告」可讓您依據活動類型之類的項目 (對等工作階段或會議工作階段)，或是依失敗工作階段隨附的 SIP 回應碼，篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，使用量會按照小時、日、星期或月加以分組。</span><span class="sxs-lookup"><span data-stu-id="13d6b-p107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Top Failures Report enables you to filter the returned data based on such things as the activity type (peer-to-peer session or conferencing session) or by the SIP response code that accompanied the failed session. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="13d6b-132">下表列出您可以用於最大失敗報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="13d6b-132">The following table lists the filters that you can use with the Top Failures Report.</span></span>

### <a name="top-failures-report-filters"></a><span data-ttu-id="13d6b-133">最大失敗報告篩選器</span><span class="sxs-lookup"><span data-stu-id="13d6b-133">Top Failures Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13d6b-134">名稱</span><span class="sxs-lookup"><span data-stu-id="13d6b-134">Name</span></span></th>
<th><span data-ttu-id="13d6b-135">描述</span><span class="sxs-lookup"><span data-stu-id="13d6b-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-136"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-136"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p108">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p108">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="13d6b-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="13d6b-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="13d6b-p109">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p109">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="13d6b-142">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="13d6b-142">7/7/2012</span></span></p>
<p><span data-ttu-id="13d6b-143">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="13d6b-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="13d6b-144">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="13d6b-144">7/3/2012</span></span></p>
<p><span data-ttu-id="13d6b-145">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="13d6b-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-146"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-146"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p110">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p110">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="13d6b-149">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="13d6b-149">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="13d6b-p111">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p111">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="13d6b-152">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="13d6b-152">7/7/2012</span></span></p>
<p><span data-ttu-id="13d6b-153">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="13d6b-153">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="13d6b-154">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="13d6b-154">7/3/2012</span></span></p>
<p><span data-ttu-id="13d6b-155">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="13d6b-155">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-156"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-156"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p112">活動的類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p112">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="13d6b-159">[全部]</span><span class="sxs-lookup"><span data-stu-id="13d6b-159">[All]</span></span></p></li>
<li><p><span data-ttu-id="13d6b-160">端對端</span><span class="sxs-lookup"><span data-stu-id="13d6b-160">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="13d6b-161">會議</span><span class="sxs-lookup"><span data-stu-id="13d6b-161">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-162"><strong>形式</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-162"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-163">目前唯一可用的選項是 [全部]<strong></strong>。</span><span class="sxs-lookup"><span data-stu-id="13d6b-163">At this time the only option available is <strong>[All]</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-164"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-164"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p113">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="13d6b-p113">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-168"><strong>類別</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-168"><strong>Category</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p114">遇到的失敗類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p114">Type of failure experienced. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="13d6b-171">預期及未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="13d6b-171">Both expected and unexpected failure</span></span></p></li>
<li><p><span data-ttu-id="13d6b-172">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="13d6b-172">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="13d6b-173">&quot;預期失敗&quot;是預期會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="13d6b-173">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="13d6b-174">例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="13d6b-174">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="13d6b-175">&quot;未預期的失敗&quot;是在項目會顯示為否則狀況良好的系統，就會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="13d6b-175">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="13d6b-176">例如，當發話者處於保留狀態時，不應掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="13d6b-176">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="13d6b-177">當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="13d6b-177">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-178"><strong>回應碼</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-178"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p116">會議失敗時所傳送的 SIP 回應碼。請輸入完整的回應碼，例如：</span><span class="sxs-lookup"><span data-stu-id="13d6b-p116">SIP response code sent when the conference failed. Enter the entire response code For example:</span></span></p>
<p><span data-ttu-id="13d6b-181">400</span><span class="sxs-lookup"><span data-stu-id="13d6b-181">400</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-182"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-182"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-p117">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="13d6b-p117">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="13d6b-185">計量</span><span class="sxs-lookup"><span data-stu-id="13d6b-185">Metrics</span></span>

<span data-ttu-id="13d6b-186">下表列出前幾名失敗報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="13d6b-186">The following table lists the information provided in the Top Failures Report.</span></span>

### <a name="top-failures-report-metrics"></a><span data-ttu-id="13d6b-187">最大失敗報告計量</span><span class="sxs-lookup"><span data-stu-id="13d6b-187">Top Failures Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="13d6b-188">名稱</span><span class="sxs-lookup"><span data-stu-id="13d6b-188">Name</span></span></th>
<th><span data-ttu-id="13d6b-189">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="13d6b-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="13d6b-190">說明</span><span class="sxs-lookup"><span data-stu-id="13d6b-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-191"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-191"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-192">是</span><span class="sxs-lookup"><span data-stu-id="13d6b-192">Yes</span></span></p></td>
<td><p><span data-ttu-id="13d6b-193">依據所報告之工作階段數的相對排名。</span><span class="sxs-lookup"><span data-stu-id="13d6b-193">Relative rank based on the number of reported sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-194"><strong>報告的工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-194"><strong>Reported sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-195">是</span><span class="sxs-lookup"><span data-stu-id="13d6b-195">Yes</span></span></p></td>
<td><p><span data-ttu-id="13d6b-196">依據診斷識別碼及 SIP 回應碼的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="13d6b-196">Total number of failed sessions based on diagnostic ID and SIP response code.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-197"><strong>受影響的使用者</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-197"><strong>Users impacted</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-198">是</span><span class="sxs-lookup"><span data-stu-id="13d6b-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="13d6b-199">受失敗工作階段影響的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="13d6b-199">Total number of users affected by the failed session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="13d6b-200"><strong>失敗資訊</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-200"><strong>Failure information</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-201">否</span><span class="sxs-lookup"><span data-stu-id="13d6b-201">No</span></span></p></td>
<td><p><span data-ttu-id="13d6b-202">失敗的詳細資訊，包括診斷識別碼、SIP 回應碼，以及工作階段為什麼失敗的說明。</span><span class="sxs-lookup"><span data-stu-id="13d6b-202">Detailed information about the failure, including diagnostic ID, SIP response code, and description of why the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="13d6b-203"><strong>過去的趨勢</strong></span><span class="sxs-lookup"><span data-stu-id="13d6b-203"><strong>Trend in the past</strong></span></span></p></td>
<td><p><span data-ttu-id="13d6b-204">否</span><span class="sxs-lookup"><span data-stu-id="13d6b-204">No</span></span></p></td>
<td><p><span data-ttu-id="13d6b-205">一段時間的失敗工作階段圖表。</span><span class="sxs-lookup"><span data-stu-id="13d6b-205">Graphs failed sessions over time.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

