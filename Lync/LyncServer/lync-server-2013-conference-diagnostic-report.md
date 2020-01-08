---
title: Lync Server 2013：會議診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279d844a4c67d3b09b35fff92f6868cae8971059
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="443f1-102">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="443f1-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="443f1-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="443f1-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="443f1-104">會議診斷報告提供所有會議會話成功和失敗的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="443f1-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="443f1-105">請注意，Microsoft Lync Server 會區分不同類型的失敗：</span><span class="sxs-lookup"><span data-stu-id="443f1-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="443f1-106">**預期失敗**。</span><span class="sxs-lookup"><span data-stu-id="443f1-106">**Expected failure**.</span></span> <span data-ttu-id="443f1-107">預期的失敗通常是最有技術意義的失敗。</span><span class="sxs-lookup"><span data-stu-id="443f1-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="443f1-108">例如，假設有人開始會議，但在任何人都可以加入之前掛斷。</span><span class="sxs-lookup"><span data-stu-id="443f1-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="443f1-109">技術上的故障：會議已啟動，但尚未完成。</span><span class="sxs-lookup"><span data-stu-id="443f1-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="443f1-110">不過，這不是您預期會發生的問題：如果召集人在任何人都可以加入之前就取消會議，您就不會預期會議已完成。</span><span class="sxs-lookup"><span data-stu-id="443f1-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="443f1-111">未**預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="443f1-111">**Unexpected failure**.</span></span> <span data-ttu-id="443f1-112">不正確的錯誤就是名稱所暗示的錯誤：根據情況而定的錯誤，您不會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="443f1-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="443f1-113">例如，假設無法控制會議，因為無法檢索召集人的會議原則。</span><span class="sxs-lookup"><span data-stu-id="443f1-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="443f1-114">這是一個意外的錯誤：畢竟，您應該總是能夠取得使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="443f1-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="443f1-115">請注意，成功、預期的失敗及意外的失敗指標可能不會新增到 [總會話] 度量。</span><span class="sxs-lookup"><span data-stu-id="443f1-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="443f1-116">例如，您可能會在報表中看到下列值：</span><span class="sxs-lookup"><span data-stu-id="443f1-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="443f1-117">成功</span><span class="sxs-lookup"><span data-stu-id="443f1-117">Successes</span></span></th>
<th><span data-ttu-id="443f1-118">預期失敗</span><span class="sxs-lookup"><span data-stu-id="443f1-118">Expected failures</span></span></th>
<th><span data-ttu-id="443f1-119">意外的失敗</span><span class="sxs-lookup"><span data-stu-id="443f1-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="443f1-120">總會話數</span><span class="sxs-lookup"><span data-stu-id="443f1-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="443f1-121">2024</span><span class="sxs-lookup"><span data-stu-id="443f1-121">2024</span></span></p></td>
<td><p><span data-ttu-id="443f1-122">469</span><span class="sxs-lookup"><span data-stu-id="443f1-122">469</span></span></p></td>
<td><p><span data-ttu-id="443f1-123">位</span><span class="sxs-lookup"><span data-stu-id="443f1-123">16</span></span></p></td>
<td><p><span data-ttu-id="443f1-124">2521</span><span class="sxs-lookup"><span data-stu-id="443f1-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="443f1-125">如果您新增 2024 + 469 + 16，您總共會得到2509個會話，而且 [總會話] 資料列會顯示2521會話總數。</span><span class="sxs-lookup"><span data-stu-id="443f1-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="443f1-126">"遺失" 的12個會話是系統無法分類為成功或失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="443f1-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="443f1-127">當協力廠商產品引入了不熟悉的監視伺服器的新診斷程式代碼時，有時候會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="443f1-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="443f1-128">當發生這種情況時，使用該產品進行的通話，並報告該診斷程式代碼，不一定會成為成功、預期的失敗或意外的失敗。</span><span class="sxs-lookup"><span data-stu-id="443f1-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="443f1-129">存取會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="443f1-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="443f1-130">您可從 [監控報告] 首頁存取會議診斷報告。</span><span class="sxs-lookup"><span data-stu-id="443f1-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="443f1-131">您可以按一下下列其中一個度量，[以存取 Lync Server 2013 中的失敗發佈報告](lync-server-2013-failure-distribution-report.md)：</span><span class="sxs-lookup"><span data-stu-id="443f1-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="443f1-132">意外的失敗量</span><span class="sxs-lookup"><span data-stu-id="443f1-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="443f1-133">預期失敗的音量</span><span class="sxs-lookup"><span data-stu-id="443f1-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="443f1-134">充分利用會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="443f1-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="443f1-135">會議診斷報告包含一系列的圖形。</span><span class="sxs-lookup"><span data-stu-id="443f1-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="443f1-136">圖表中顯示的每一欄實際上都是超連結。</span><span class="sxs-lookup"><span data-stu-id="443f1-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="443f1-137">如果您按一下某個欄，就會向下切入[Lync Server 2013 的 [失敗發佈] 報告](lync-server-2013-failure-distribution-report.md)，以瞭解該時段以及該會議類型。</span><span class="sxs-lookup"><span data-stu-id="443f1-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="443f1-138">濾鏡</span><span class="sxs-lookup"><span data-stu-id="443f1-138">Filters</span></span>

<span data-ttu-id="443f1-139">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="443f1-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="443f1-140">例如，會議診斷報告可讓您篩選出所進行的會議類型（例如焦點會議），或由會議中使用的邊緣伺服器進行。</span><span class="sxs-lookup"><span data-stu-id="443f1-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="443f1-141">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="443f1-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="443f1-142">在這種情況下，會議會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="443f1-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="443f1-143">下表列出可與會議診斷報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="443f1-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="443f1-144">會議診斷報表篩選</span><span class="sxs-lookup"><span data-stu-id="443f1-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="443f1-145">名稱</span><span class="sxs-lookup"><span data-stu-id="443f1-145">Name</span></span></th>
<th><span data-ttu-id="443f1-146">描述</span><span class="sxs-lookup"><span data-stu-id="443f1-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="443f1-147"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-148">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="443f1-148">Start date/time for the time range.</span></span> <span data-ttu-id="443f1-149">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="443f1-149">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="443f1-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="443f1-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="443f1-151">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="443f1-151">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="443f1-152">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="443f1-152">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="443f1-153">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="443f1-153">7/7/2012</span></span></p>
<p><span data-ttu-id="443f1-154">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="443f1-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="443f1-155">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="443f1-155">7/3/2012</span></span></p>
<p><span data-ttu-id="443f1-156">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="443f1-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443f1-157"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-158">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="443f1-158">End date/time for the time range.</span></span> <span data-ttu-id="443f1-159">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="443f1-159">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="443f1-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="443f1-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="443f1-161">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="443f1-161">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="443f1-162">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="443f1-162">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="443f1-163">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="443f1-163">7/7/2012</span></span></p>
<p><span data-ttu-id="443f1-164">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="443f1-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="443f1-165">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="443f1-165">7/3/2012</span></span></p>
<p><span data-ttu-id="443f1-166">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="443f1-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443f1-167"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-168">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="443f1-168">Time interval.</span></span> <span data-ttu-id="443f1-169">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="443f1-169">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="443f1-170">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="443f1-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="443f1-171">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="443f1-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="443f1-172">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="443f1-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="443f1-173">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="443f1-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="443f1-174">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="443f1-174">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="443f1-175">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="443f1-175">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443f1-176"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-177">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="443f1-177">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="443f1-178">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="443f1-178">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="443f1-179">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="443f1-179">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443f1-180"><strong>會議會話</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-181">表示會議會話的類型。</span><span class="sxs-lookup"><span data-stu-id="443f1-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="443f1-182">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="443f1-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="443f1-183">同時</span><span class="sxs-lookup"><span data-stu-id="443f1-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="443f1-184">焦點會話</span><span class="sxs-lookup"><span data-stu-id="443f1-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="443f1-185">所有 MCU 會話</span><span class="sxs-lookup"><span data-stu-id="443f1-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="443f1-186">IM 會議</span><span class="sxs-lookup"><span data-stu-id="443f1-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="443f1-187">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="443f1-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="443f1-188">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="443f1-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="443f1-189">指標</span><span class="sxs-lookup"><span data-stu-id="443f1-189">Metrics</span></span>

<span data-ttu-id="443f1-190">下表列出每個會議會話類型的會議診斷報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="443f1-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="443f1-191">會議診斷報告度量單位</span><span class="sxs-lookup"><span data-stu-id="443f1-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="443f1-192">名稱</span><span class="sxs-lookup"><span data-stu-id="443f1-192">Name</span></span></th>
<th><span data-ttu-id="443f1-193">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="443f1-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="443f1-194">描述</span><span class="sxs-lookup"><span data-stu-id="443f1-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="443f1-195"><strong>成功的音量</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-196">否</span><span class="sxs-lookup"><span data-stu-id="443f1-196">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-197">成功的會議總數。</span><span class="sxs-lookup"><span data-stu-id="443f1-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443f1-198"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-199">否</span><span class="sxs-lookup"><span data-stu-id="443f1-199">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-200">已完成且重要問題的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="443f1-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="443f1-201">將成功率除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="443f1-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443f1-202"><strong>預期失敗的音量</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-203">否</span><span class="sxs-lookup"><span data-stu-id="443f1-203">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-204">&quot;預期發生失敗&quot;的會議總數。</span><span class="sxs-lookup"><span data-stu-id="443f1-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="443f1-205">預期的失敗是預期發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="443f1-205">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="443f1-206">例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="443f1-206">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443f1-207"><strong>預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-208">否</span><span class="sxs-lookup"><span data-stu-id="443f1-208">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-209">遇到預期錯誤的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="443f1-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="443f1-210">將預期的失敗量除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="443f1-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443f1-211"><strong>意外的失敗量</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-212">否</span><span class="sxs-lookup"><span data-stu-id="443f1-212">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-213">發生&quot;意外失敗&quot;的會議總數。</span><span class="sxs-lookup"><span data-stu-id="443f1-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="443f1-214">發生意外的失敗，就是看起來像是其他健康的系統。</span><span class="sxs-lookup"><span data-stu-id="443f1-214">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="443f1-215">例如，如果來電者停留在 [保留] 上，就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="443f1-215">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="443f1-216">如果發生這種情況，就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="443f1-216">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="443f1-217"><strong>意外的失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-218">否</span><span class="sxs-lookup"><span data-stu-id="443f1-218">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-219">遇到意外錯誤的會議百分比。</span><span class="sxs-lookup"><span data-stu-id="443f1-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="443f1-220">將非預期的失敗量除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="443f1-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="443f1-221"><strong>總會話數</strong></span><span class="sxs-lookup"><span data-stu-id="443f1-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="443f1-222">否</span><span class="sxs-lookup"><span data-stu-id="443f1-222">No</span></span></p></td>
<td><p><span data-ttu-id="443f1-223">會議總數，包括成功的會議、失敗的會議（預期的失敗與意外的失敗），以及未分類的會議。</span><span class="sxs-lookup"><span data-stu-id="443f1-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

