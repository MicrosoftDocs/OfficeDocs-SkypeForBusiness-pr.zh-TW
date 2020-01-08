---
title: Lync Server 2013：會議活動報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="fff3a-102">Lync Server 2013 中的會議活動報告</span><span class="sxs-lookup"><span data-stu-id="fff3a-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fff3a-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fff3a-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fff3a-104">會議活動報告可讓您輕鬆回答下列問題：每天舉行多少筆會議，以及何時舉行這些會議？</span><span class="sxs-lookup"><span data-stu-id="fff3a-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="fff3a-105">這類資訊不僅是本身所有用的，也適用于疑難排解工具。</span><span class="sxs-lookup"><span data-stu-id="fff3a-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="fff3a-106">例如，假設使用者抱怨，在一天中間網路看起來很慢。</span><span class="sxs-lookup"><span data-stu-id="fff3a-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="fff3a-107">您可以快速流覽會議活動報告，可能會建議一種可能的原因：目前為止，有更多的會議是在 10:00 AM 和 2:00 PM 之間排程，然後在其他時間進行排程。</span><span class="sxs-lookup"><span data-stu-id="fff3a-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="fff3a-108">如果慢速網路造成問題，您可以鼓勵使用者在一天較低的 trafficked 時間期間重新排程其中一些會議。</span><span class="sxs-lookup"><span data-stu-id="fff3a-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="fff3a-109">存取會議活動報告</span><span class="sxs-lookup"><span data-stu-id="fff3a-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="fff3a-110">在[Lync Server 2013 的 [會議摘要] 報告中](lync-server-2013-conference-summary-report.md)，按一下下列其中一個度量，即可存取會議活動報告：</span><span class="sxs-lookup"><span data-stu-id="fff3a-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="fff3a-111">會議總數</span><span class="sxs-lookup"><span data-stu-id="fff3a-111">Total conferences</span></span>

  - <span data-ttu-id="fff3a-112">參與者總數</span><span class="sxs-lookup"><span data-stu-id="fff3a-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="fff3a-113">充分利用會議活動報告</span><span class="sxs-lookup"><span data-stu-id="fff3a-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="fff3a-114">根據預設，會議活動報告會會顯示指定時段內的會議總數（例如，每日會議總數，或一天中每小時會議的總數）。</span><span class="sxs-lookup"><span data-stu-id="fff3a-114">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day).</span></span> <span data-ttu-id="fff3a-115">不過，您也可以選擇顯示該時段的參與者總數或參與者分鐘數的總數。</span><span class="sxs-lookup"><span data-stu-id="fff3a-115">However, you can also choose to display the total number of participants for that time period or the total number of participant minutes.</span></span> <span data-ttu-id="fff3a-116">若要這樣做，請按一下 [顯示/隱藏參數] 按鈕以顯示篩選選項，然後從 [報告依據] 下拉式清單中選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fff3a-116">To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="fff3a-117">參與者計數</span><span class="sxs-lookup"><span data-stu-id="fff3a-117">Participant count</span></span>

  - <span data-ttu-id="fff3a-118">參與者通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="fff3a-118">Participant minutes</span></span>

  - <span data-ttu-id="fff3a-119">會議計數</span><span class="sxs-lookup"><span data-stu-id="fff3a-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fff3a-120">濾鏡</span><span class="sxs-lookup"><span data-stu-id="fff3a-120">Filters</span></span>

<span data-ttu-id="fff3a-121">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="fff3a-121">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="fff3a-122">下表列出您可與會議活動報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="fff3a-122">The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="fff3a-123">會議活動報表篩選</span><span class="sxs-lookup"><span data-stu-id="fff3a-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff3a-124">名稱</span><span class="sxs-lookup"><span data-stu-id="fff3a-124">Name</span></span></th>
<th><span data-ttu-id="fff3a-125">描述</span><span class="sxs-lookup"><span data-stu-id="fff3a-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-126"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-127">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="fff3a-127">Start date/time for the time range.</span></span> <span data-ttu-id="fff3a-128">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fff3a-128">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fff3a-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fff3a-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fff3a-130">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="fff3a-130">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="fff3a-131">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="fff3a-131">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fff3a-132">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fff3a-132">7/7/2012</span></span></p>
<p><span data-ttu-id="fff3a-133">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="fff3a-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fff3a-134">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fff3a-134">7/3/2012</span></span></p>
<p><span data-ttu-id="fff3a-135">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="fff3a-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff3a-136"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-137">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="fff3a-137">End date/time for the time range.</span></span> <span data-ttu-id="fff3a-138">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fff3a-138">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fff3a-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fff3a-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fff3a-140">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="fff3a-140">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="fff3a-141">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="fff3a-141">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fff3a-142">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fff3a-142">7/7/2012</span></span></p>
<p><span data-ttu-id="fff3a-143">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="fff3a-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fff3a-144">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fff3a-144">7/3/2012</span></span></p>
<p><span data-ttu-id="fff3a-145">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="fff3a-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-146"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-147">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="fff3a-147">Time interval.</span></span> <span data-ttu-id="fff3a-148">選取下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="fff3a-148">Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fff3a-149">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="fff3a-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fff3a-150">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="fff3a-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fff3a-151">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="fff3a-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fff3a-152">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="fff3a-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="fff3a-153">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="fff3a-153">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="fff3a-154">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="fff3a-154">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff3a-155"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-156">指出要在報表中使用的值。</span><span class="sxs-lookup"><span data-stu-id="fff3a-156">Indicates the values to be used in the report.</span></span> <span data-ttu-id="fff3a-157">您可以選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fff3a-157">You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fff3a-158">參與者計數</span><span class="sxs-lookup"><span data-stu-id="fff3a-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="fff3a-159">參與者通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="fff3a-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="fff3a-160">會議計數</span><span class="sxs-lookup"><span data-stu-id="fff3a-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="fff3a-161">依泳池進行的會議度量單位</span><span class="sxs-lookup"><span data-stu-id="fff3a-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="fff3a-162">下表列出每個池之會議活動報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="fff3a-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="fff3a-163">依泳池進行的會議度量單位</span><span class="sxs-lookup"><span data-stu-id="fff3a-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff3a-164">名稱</span><span class="sxs-lookup"><span data-stu-id="fff3a-164">Name</span></span></th>
<th><span data-ttu-id="fff3a-165">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="fff3a-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fff3a-166">描述</span><span class="sxs-lookup"><span data-stu-id="fff3a-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-167"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-168">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-168">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-169">在會議中使用的註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="fff3a-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff3a-170"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-171">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-171">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-172">舉行會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fff3a-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-173"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-174">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-174">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-175">參與者總數、總參與者分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="fff3a-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="fff3a-176">依伺服器類型的會議標準</span><span class="sxs-lookup"><span data-stu-id="fff3a-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="fff3a-177">下表列出每個伺服器類型之會議活動報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="fff3a-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="fff3a-178">依伺服器類型的會議標準</span><span class="sxs-lookup"><span data-stu-id="fff3a-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fff3a-179">名稱</span><span class="sxs-lookup"><span data-stu-id="fff3a-179">Name</span></span></th>
<th><span data-ttu-id="fff3a-180">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="fff3a-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fff3a-181">描述</span><span class="sxs-lookup"><span data-stu-id="fff3a-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-182"><strong>會議服務器類型</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-183">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-183">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-184">在會議中使用的伺服器類型，通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fff3a-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fff3a-185">網路會議服務器</span><span class="sxs-lookup"><span data-stu-id="fff3a-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="fff3a-186">IM 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="fff3a-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="fff3a-187">電話會議伺服器</span><span class="sxs-lookup"><span data-stu-id="fff3a-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="fff3a-188">防病毒會議服務器</span><span class="sxs-lookup"><span data-stu-id="fff3a-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="fff3a-189">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="fff3a-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fff3a-190"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-191">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-191">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-192">舉行會議的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fff3a-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fff3a-193"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="fff3a-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fff3a-194">否</span><span class="sxs-lookup"><span data-stu-id="fff3a-194">No</span></span></p></td>
<td><p><span data-ttu-id="fff3a-195">參與者總數、總參與者分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="fff3a-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

