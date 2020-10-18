---
title: Lync Server 2013：會議診斷報告
description: Lync Server 2013：會議診斷報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d3ef3c78bc2145d907d5a40e1aed95a2f4cb4c4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577639"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="e12ef-103">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="e12ef-103">Conference Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e12ef-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e12ef-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e12ef-105">會議診斷報告可提供所有會議會話成功和失敗的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e12ef-105">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="e12ef-106">請注意，Microsoft Lync Server 會區別不同的失敗類型：</span><span class="sxs-lookup"><span data-stu-id="e12ef-106">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="e12ef-107">**預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="e12ef-107">**Expected failure**.</span></span> <span data-ttu-id="e12ef-108">預期的失敗通常是指技術上預期會有的失敗。</span><span class="sxs-lookup"><span data-stu-id="e12ef-108">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="e12ef-109">例如，假設某人開始參加會議，但在任何人都可以加入之前便會掛斷。</span><span class="sxs-lookup"><span data-stu-id="e12ef-109">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="e12ef-110">技術上的失敗：會議已啟動，但尚未完成。</span><span class="sxs-lookup"><span data-stu-id="e12ef-110">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="e12ef-111">不過，這是您預期會發生的失敗：如果召集人在使用者可以加入之前取消會議，您就不會期望會議順利完成。</span><span class="sxs-lookup"><span data-stu-id="e12ef-111">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="e12ef-112">**未預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="e12ef-112">**Unexpected failure**.</span></span> <span data-ttu-id="e12ef-113">未預期的錯誤正如其名稱所指：在不同的情況下，所發生的未預期錯誤。</span><span class="sxs-lookup"><span data-stu-id="e12ef-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="e12ef-114">例如，假設無法保留會議，因為無法取得召集人的會議原則。</span><span class="sxs-lookup"><span data-stu-id="e12ef-114">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="e12ef-115">這是未預期的錯誤：畢竟，您應該永遠能夠取回使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="e12ef-115">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="e12ef-116">請注意，「成功」、「預期的失敗」及「未預期的失敗」計量的總和不一定等於「工作階段總數」計量。</span><span class="sxs-lookup"><span data-stu-id="e12ef-116">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="e12ef-117">例如，您可能會在報告中看到下列值：</span><span class="sxs-lookup"><span data-stu-id="e12ef-117">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e12ef-118">成功</span><span class="sxs-lookup"><span data-stu-id="e12ef-118">Successes</span></span></th>
<th><span data-ttu-id="e12ef-119">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="e12ef-119">Expected failures</span></span></th>
<th><span data-ttu-id="e12ef-120">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="e12ef-120">Unexpected failures</span></span></th>
<th><span data-ttu-id="e12ef-121">工作階段總數</span><span class="sxs-lookup"><span data-stu-id="e12ef-121">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-122">2024</span><span class="sxs-lookup"><span data-stu-id="e12ef-122">2024</span></span></p></td>
<td><p><span data-ttu-id="e12ef-123">469</span><span class="sxs-lookup"><span data-stu-id="e12ef-123">469</span></span></p></td>
<td><p><span data-ttu-id="e12ef-124">16 </span><span class="sxs-lookup"><span data-stu-id="e12ef-124">16</span></span></p></td>
<td><p><span data-ttu-id="e12ef-125">2521</span><span class="sxs-lookup"><span data-stu-id="e12ef-125">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e12ef-126">如果您新增 2024 + 469 + 16，您會收到全部的2509個會話，但是 [總會話] 欄會顯示總的2521會話。</span><span class="sxs-lookup"><span data-stu-id="e12ef-126">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="e12ef-127">「丟失」的12個會話是系統無法分類為成功或失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="e12ef-127">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="e12ef-128">在協力廠商產品引進監控伺服器不熟悉的新診斷程式代碼時，有時候會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="e12ef-128">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="e12ef-129">若發生此情況，使用該產品撥打電話後回報該診斷碼，可能無法歸類為「成功」、「預期的失敗」或「未預期的失敗」。</span><span class="sxs-lookup"><span data-stu-id="e12ef-129">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="e12ef-130">存取會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="e12ef-130">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="e12ef-131">您可以從監控報告首頁存取會議診斷報告。</span><span class="sxs-lookup"><span data-stu-id="e12ef-131">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e12ef-132">您可以按一下下列其中一個計量， [以在 Lync Server 2013 中存取失敗散佈報告](lync-server-2013-failure-distribution-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="e12ef-132">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e12ef-133">未預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="e12ef-133">Unexpected failure volume</span></span>

  - <span data-ttu-id="e12ef-134">預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="e12ef-134">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="e12ef-135">會議診斷報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="e12ef-135">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="e12ef-136">會議診斷報告包含一系列的圖表。</span><span class="sxs-lookup"><span data-stu-id="e12ef-136">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="e12ef-137">圖表中所顯示的每一欄實際上都是超連結。</span><span class="sxs-lookup"><span data-stu-id="e12ef-137">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="e12ef-138">如果您按一下某欄，您會 [在 Lync Server 2013 中深入查看 [失敗散佈報告](lync-server-2013-failure-distribution-report.md) ]，以取得該時段及該會議類型。</span><span class="sxs-lookup"><span data-stu-id="e12ef-138">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e12ef-139">篩選</span><span class="sxs-lookup"><span data-stu-id="e12ef-139">Filters</span></span>

<span data-ttu-id="e12ef-140">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="e12ef-140">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e12ef-141">例如，會議診斷報告可讓您篩選出正在進行的會議類型 (例如，以焦點為基礎的會議) 或是會議中所使用的 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="e12ef-141">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="e12ef-142">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="e12ef-142">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e12ef-143">在此情況下，會依小時、天、周或月群組會議。</span><span class="sxs-lookup"><span data-stu-id="e12ef-143">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e12ef-144">下表列出您可以搭配會議診斷報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="e12ef-144">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="e12ef-145">會議診斷報告篩選器</span><span class="sxs-lookup"><span data-stu-id="e12ef-145">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e12ef-146">名稱</span><span class="sxs-lookup"><span data-stu-id="e12ef-146">Name</span></span></th>
<th><span data-ttu-id="e12ef-147">描述</span><span class="sxs-lookup"><span data-stu-id="e12ef-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-p109">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e12ef-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e12ef-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e12ef-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e12ef-p110">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e12ef-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e12ef-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e12ef-154">7/7/2012</span></span></p>
<p><span data-ttu-id="e12ef-155">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e12ef-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e12ef-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e12ef-156">7/3/2012</span></span></p>
<p><span data-ttu-id="e12ef-157">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e12ef-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e12ef-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-p111">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e12ef-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e12ef-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e12ef-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e12ef-p112">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e12ef-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e12ef-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e12ef-164">7/7/2012</span></span></p>
<p><span data-ttu-id="e12ef-165">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e12ef-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e12ef-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e12ef-166">7/3/2012</span></span></p>
<p><span data-ttu-id="e12ef-167">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e12ef-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-168"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-168"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-p113">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e12ef-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e12ef-171">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="e12ef-171">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e12ef-172">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="e12ef-172">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e12ef-173">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="e12ef-173">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="e12ef-174">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="e12ef-174">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="e12ef-p114">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="e12ef-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e12ef-177"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-177"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-p115">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="e12ef-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-181"><strong>會議會話</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-181"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-182">會指出會議會話的類型。</span><span class="sxs-lookup"><span data-stu-id="e12ef-182">Indicates the type of conferencing session.</span></span> <span data-ttu-id="e12ef-183">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e12ef-183">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="e12ef-184">一切</span><span class="sxs-lookup"><span data-stu-id="e12ef-184">[All]</span></span></p></li>
<li><p><span data-ttu-id="e12ef-185">焦點工作階段</span><span class="sxs-lookup"><span data-stu-id="e12ef-185">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="e12ef-186">所有 MCU 會話</span><span class="sxs-lookup"><span data-stu-id="e12ef-186">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="e12ef-187">IM 會議</span><span class="sxs-lookup"><span data-stu-id="e12ef-187">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="e12ef-188">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="e12ef-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="e12ef-189">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="e12ef-189">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e12ef-190">指標</span><span class="sxs-lookup"><span data-stu-id="e12ef-190">Metrics</span></span>

<span data-ttu-id="e12ef-191">下表列出會議診斷報告中針對每種會議會話類型所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="e12ef-191">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="e12ef-192">會議診斷報告計量</span><span class="sxs-lookup"><span data-stu-id="e12ef-192">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e12ef-193">姓名</span><span class="sxs-lookup"><span data-stu-id="e12ef-193">Name</span></span></th>
<th><span data-ttu-id="e12ef-194">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="e12ef-194">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e12ef-195">描述</span><span class="sxs-lookup"><span data-stu-id="e12ef-195">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-196"><strong>成功次數</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-196"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-197">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-197">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-198">成功的會議總數。</span><span class="sxs-lookup"><span data-stu-id="e12ef-198">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e12ef-199"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-199"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-200">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-200">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-201">已完成且發生重大問題的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="e12ef-201">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="e12ef-202">計算方式是將成功次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="e12ef-202">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-203"><strong>預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-203"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-204">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-204">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-205">預期發生失敗之會議的總數 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e12ef-205">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e12ef-p118">預期的失敗是指預期會發生的失敗。例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="e12ef-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e12ef-208"><strong>預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-208"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-209">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-209">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-210">發生預期錯誤之會議所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="e12ef-210">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="e12ef-211">計算方式是將預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="e12ef-211">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-212"><strong>未預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-212"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-213">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-213">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-214">發生未預期失敗之會議的總數 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="e12ef-214">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="e12ef-p120">未預期的失敗是指起因於系統不健全的失敗。例如，當發話者處於保留狀態時，不應掛斷通話。當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="e12ef-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e12ef-218"><strong>未預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-218"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-219">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-219">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-220">發生未預期錯誤之會議所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="e12ef-220">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="e12ef-221">計算方式是將未預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="e12ef-221">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e12ef-222"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="e12ef-222"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="e12ef-223">否</span><span class="sxs-lookup"><span data-stu-id="e12ef-223">No</span></span></p></td>
<td><p><span data-ttu-id="e12ef-224">會議總數，包括成功的會議、失敗的會議 (預期的失敗及未預期的失敗) 及未分類的會議。</span><span class="sxs-lookup"><span data-stu-id="e12ef-224">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

