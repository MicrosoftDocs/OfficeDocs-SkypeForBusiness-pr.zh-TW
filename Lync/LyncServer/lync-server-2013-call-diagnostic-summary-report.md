---
title: Lync Server 2013：呼叫診斷摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0228af8690fe7170fc4fd77e72f67f6cb3adc08c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="2ca68-102">在 Lync Server 2013 中呼叫診斷摘要報告</span><span class="sxs-lookup"><span data-stu-id="2ca68-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ca68-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="2ca68-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="2ca68-104">[通話診斷摘要] 報告可全面瞭解對等與會議會話失敗的情況。</span><span class="sxs-lookup"><span data-stu-id="2ca68-104">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="2ca68-105">報告會顯示這兩種類型的會話的整體失敗率，然後依會話模態類型進一步打破失敗資訊：</span><span class="sxs-lookup"><span data-stu-id="2ca68-105">The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="2ca68-106">立即訊息</span><span class="sxs-lookup"><span data-stu-id="2ca68-106">Instant messaging</span></span>

  - <span data-ttu-id="2ca68-107">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="2ca68-107">Application sharing</span></span>

  - <span data-ttu-id="2ca68-108">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="2ca68-108">File transfer</span></span>

  - <span data-ttu-id="2ca68-109">音訊</span><span class="sxs-lookup"><span data-stu-id="2ca68-109">Audio</span></span>

  - <span data-ttu-id="2ca68-110">顯示器</span><span class="sxs-lookup"><span data-stu-id="2ca68-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="2ca68-111">存取呼叫診斷摘要報告</span><span class="sxs-lookup"><span data-stu-id="2ca68-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="2ca68-112">[呼叫診斷摘要] 報告可從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="2ca68-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="2ca68-113">在 [呼叫診斷摘要] 報告中，您可以在 [Lync Server 2013] 中按一下 [對等] 的 [點對點工作階段摘要] 區段下的 [失敗率] 度量，以存取該報告的[對等活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)。</span><span class="sxs-lookup"><span data-stu-id="2ca68-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="2ca68-114">您也可以按一下下列任何一種會議度量，[在 Lync Server 2013 中存取會議診斷報告](lync-server-2013-conference-diagnostic-report.md)：</span><span class="sxs-lookup"><span data-stu-id="2ca68-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="2ca68-115">總體會話失敗率</span><span class="sxs-lookup"><span data-stu-id="2ca68-115">Overall session failure rate</span></span>

  - <span data-ttu-id="2ca68-116">焦點失敗率</span><span class="sxs-lookup"><span data-stu-id="2ca68-116">Focus failure rate</span></span>

  - <span data-ttu-id="2ca68-117">MCU 失敗率</span><span class="sxs-lookup"><span data-stu-id="2ca68-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="2ca68-118">充分利用 [呼叫診斷摘要] 報告</span><span class="sxs-lookup"><span data-stu-id="2ca68-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="2ca68-119">[通話診斷摘要] 報告包含的圖形會針對 Microsoft Lync Server 2013 中使用的各種形式，比較失敗率。</span><span class="sxs-lookup"><span data-stu-id="2ca68-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="2ca68-120">這些圖形中的欄實際上是 hotlinks;例如，如果您按一下點對點工作階段的 [立即訊息] 資料行，您會[在 Lync Server 2013 中](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)向下切入對等活動診斷報告的實例，此報告提供有關 [呼叫說明摘要] 報告中所包含的所有立即訊息會話的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2ca68-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2ca68-121">濾鏡</span><span class="sxs-lookup"><span data-stu-id="2ca68-121">Filters</span></span>

<span data-ttu-id="2ca68-122">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="2ca68-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2ca68-123">例如，[呼叫診斷摘要] 報告可讓您篩選出會話中使用的註冊機構池或邊緣伺服器等專案。</span><span class="sxs-lookup"><span data-stu-id="2ca68-123">For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session.</span></span> <span data-ttu-id="2ca68-124">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="2ca68-124">You can also choose how data should be grouped.</span></span> <span data-ttu-id="2ca68-125">在這種情況下，通話會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="2ca68-125">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="2ca68-126">下表列出可與 [呼叫診斷摘要] 報告搭配使用的篩選準則。</span><span class="sxs-lookup"><span data-stu-id="2ca68-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="2ca68-127">呼叫診斷摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="2ca68-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca68-128">名稱</span><span class="sxs-lookup"><span data-stu-id="2ca68-128">Name</span></span></th>
<th><span data-ttu-id="2ca68-129">說明</span><span class="sxs-lookup"><span data-stu-id="2ca68-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-130"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-131">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2ca68-131">Start date/time for the time range.</span></span> <span data-ttu-id="2ca68-132">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ca68-132">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2ca68-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ca68-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ca68-134">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="2ca68-134">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2ca68-135">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="2ca68-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ca68-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ca68-136">7/7/2012</span></span></p>
<p><span data-ttu-id="2ca68-137">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2ca68-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ca68-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ca68-138">7/3/2012</span></span></p>
<p><span data-ttu-id="2ca68-139">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="2ca68-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-140"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-141">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="2ca68-141">End date/time for the time range.</span></span> <span data-ttu-id="2ca68-142">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2ca68-142">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2ca68-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2ca68-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2ca68-144">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="2ca68-144">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="2ca68-145">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="2ca68-145">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2ca68-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2ca68-146">7/7/2012</span></span></p>
<p><span data-ttu-id="2ca68-147">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="2ca68-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2ca68-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2ca68-148">7/3/2012</span></span></p>
<p><span data-ttu-id="2ca68-149">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="2ca68-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-150"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-151">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="2ca68-151">Time interval.</span></span> <span data-ttu-id="2ca68-152">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2ca68-152">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2ca68-153">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="2ca68-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2ca68-154">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="2ca68-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2ca68-155">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="2ca68-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2ca68-156">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="2ca68-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2ca68-157">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="2ca68-157">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="2ca68-158">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="2ca68-158">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-159"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-160">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="2ca68-160">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="2ca68-161">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="2ca68-161">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="2ca68-162">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="2ca68-162">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2ca68-163">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="2ca68-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="2ca68-164">下表列出點對點工作階段的呼叫診斷摘要報告中所提供的資訊（也就是只涉及兩個參與者的會話）。</span><span class="sxs-lookup"><span data-stu-id="2ca68-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="2ca68-165">點對點工作階段的度量單位</span><span class="sxs-lookup"><span data-stu-id="2ca68-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca68-166">名稱</span><span class="sxs-lookup"><span data-stu-id="2ca68-166">Name</span></span></th>
<th><span data-ttu-id="2ca68-167">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="2ca68-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ca68-168">說明</span><span class="sxs-lookup"><span data-stu-id="2ca68-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-169"><strong>總會話數</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-170">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-170">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-171">所執行的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="2ca68-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-172"><strong>失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-173">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-173">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-174">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="2ca68-174">Percentage of peer-to-peer sessions that failed.</span></span> <span data-ttu-id="2ca68-175">當您按一下此專案時，報告會顯示對等活動診斷報告，其中會顯示關於失敗的點對點工作階段的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2ca68-175">When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2ca68-176">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="2ca68-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="2ca68-177">下表列出會議會話的通話診斷報告中所提供的資訊（也就是有三個或更多參與者的會議）。</span><span class="sxs-lookup"><span data-stu-id="2ca68-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="2ca68-178">會議會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="2ca68-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ca68-179">名稱</span><span class="sxs-lookup"><span data-stu-id="2ca68-179">Name</span></span></th>
<th><span data-ttu-id="2ca68-180">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="2ca68-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2ca68-181">說明</span><span class="sxs-lookup"><span data-stu-id="2ca68-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-182"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-183">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-183">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-184">召開的會議總數。</span><span class="sxs-lookup"><span data-stu-id="2ca68-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-185"><strong>會議會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-186">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-186">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-187">已執行的會議會話總數。</span><span class="sxs-lookup"><span data-stu-id="2ca68-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-188"><strong>總體會話失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-189">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-189">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-190">失敗之會議會話總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="2ca68-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-191"><strong>焦點會話</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-192">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-192">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-193">失敗的焦點會議會話總數。</span><span class="sxs-lookup"><span data-stu-id="2ca68-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-194"><strong>焦點失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-195">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-195">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-196">失敗的專注于會議會話所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="2ca68-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ca68-197"><strong>MCU 會話</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-198">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-198">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-199">已失敗的會議服務器（先前稱為 Multipoint 控制項單元或 MCU）會議的總數。</span><span class="sxs-lookup"><span data-stu-id="2ca68-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ca68-200"><strong>MCU 失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="2ca68-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="2ca68-201">否</span><span class="sxs-lookup"><span data-stu-id="2ca68-201">No</span></span></p></td>
<td><p><span data-ttu-id="2ca68-202">已失敗的會議服務器（先前稱為 Multipoint 控制項單元或 MCU）會議所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="2ca68-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

