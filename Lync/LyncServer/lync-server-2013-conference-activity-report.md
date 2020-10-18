---
title: Lync Server 2013：會議活動報告
description: Lync Server 2013：會議活動報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7a2b23a08970defaec62b98d075ad1167527fd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577649"
---
# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="133e5-103">Lync Server 2013 中的會議活動報告</span><span class="sxs-lookup"><span data-stu-id="133e5-103">Conference Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="133e5-104">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="133e5-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="133e5-105">「會議活動報告」可讓您輕鬆回答下列問題：每天舉行了幾場會議？</span><span class="sxs-lookup"><span data-stu-id="133e5-105">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="133e5-106">這些會議的舉行時間為何？</span><span class="sxs-lookup"><span data-stu-id="133e5-106">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="133e5-107">這類資訊不只具備本質的意義，也是非常實用的疑難排解工具。</span><span class="sxs-lookup"><span data-stu-id="133e5-107">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="133e5-108">在會議活動報告中，您可能會建議一個可能的原因：目前在 10:00 AM 和 2:00 PM 的下班時間之間排程的會議，在任何其他時間。</span><span class="sxs-lookup"><span data-stu-id="133e5-108">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="133e5-109">若網路太慢導致了問題，您就可以鼓勵使用者將部分會議重新排程在較為離峰流量的時段。</span><span class="sxs-lookup"><span data-stu-id="133e5-109">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="133e5-110">存取會議活動報告</span><span class="sxs-lookup"><span data-stu-id="133e5-110">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="133e5-111">您可以按一下下列其中一個計量， [以在 Lync Server 2013 中的會議摘要報告中](lync-server-2013-conference-summary-report.md) 存取會議活動報告：</span><span class="sxs-lookup"><span data-stu-id="133e5-111">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="133e5-112">會議總數</span><span class="sxs-lookup"><span data-stu-id="133e5-112">Total conferences</span></span>

  - <span data-ttu-id="133e5-113">參與者總數</span><span class="sxs-lookup"><span data-stu-id="133e5-113">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="133e5-114">善加利用會議活動報告</span><span class="sxs-lookup"><span data-stu-id="133e5-114">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="133e5-p102">會議活動報告預設會顯示特定時間範圍內的會議總數 (例如，每天的會議總數，或當天某一小時的會議總數)。不過，您也可以選擇要顯示該時段的參與者總數或參與者總分鐘數。要進行這項作業，您可按一下 [顯示/隱藏參數] 按鈕，以顯示篩選選項，然後從下拉式清單的報告中選取其中一個項目：</span><span class="sxs-lookup"><span data-stu-id="133e5-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="133e5-118">參與者計數</span><span class="sxs-lookup"><span data-stu-id="133e5-118">Participant count</span></span>

  - <span data-ttu-id="133e5-119">參與者分鐘數</span><span class="sxs-lookup"><span data-stu-id="133e5-119">Participant minutes</span></span>

  - <span data-ttu-id="133e5-120">會議計數</span><span class="sxs-lookup"><span data-stu-id="133e5-120">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="133e5-121">篩選</span><span class="sxs-lookup"><span data-stu-id="133e5-121">Filters</span></span>

<span data-ttu-id="133e5-p103">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。下表列出您可以搭配會議活動報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="133e5-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="133e5-124">會議活動報告篩選</span><span class="sxs-lookup"><span data-stu-id="133e5-124">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133e5-125">名稱</span><span class="sxs-lookup"><span data-stu-id="133e5-125">Name</span></span></th>
<th><span data-ttu-id="133e5-126">描述</span><span class="sxs-lookup"><span data-stu-id="133e5-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133e5-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-p104">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="133e5-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="133e5-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="133e5-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="133e5-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="133e5-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="133e5-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="133e5-133">7/7/2012</span></span></p>
<p><span data-ttu-id="133e5-134">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="133e5-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="133e5-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="133e5-135">7/3/2012</span></span></p>
<p><span data-ttu-id="133e5-136">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="133e5-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133e5-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="133e5-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="133e5-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="133e5-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="133e5-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="133e5-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="133e5-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="133e5-143">7/7/2012</span></span></p>
<p><span data-ttu-id="133e5-144">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="133e5-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="133e5-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="133e5-145">7/3/2012</span></span></p>
<p><span data-ttu-id="133e5-146">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="133e5-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133e5-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-p108">時間間隔。請選取下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="133e5-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133e5-150">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="133e5-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="133e5-151">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="133e5-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="133e5-152">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="133e5-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="133e5-153">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="133e5-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="133e5-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="133e5-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133e5-156"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-156"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-p110">指定報告中所要使用的值。您可選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="133e5-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133e5-159">參與者計數</span><span class="sxs-lookup"><span data-stu-id="133e5-159">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="133e5-160">參與者分鐘數</span><span class="sxs-lookup"><span data-stu-id="133e5-160">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="133e5-161">會議計數</span><span class="sxs-lookup"><span data-stu-id="133e5-161">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="133e5-162">會議計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="133e5-162">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="133e5-163">下表列出會議活動報告針對每個集區提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="133e5-163">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="133e5-164">會議計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="133e5-164">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133e5-165">姓名</span><span class="sxs-lookup"><span data-stu-id="133e5-165">Name</span></span></th>
<th><span data-ttu-id="133e5-166">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="133e5-166">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="133e5-167">描述</span><span class="sxs-lookup"><span data-stu-id="133e5-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133e5-168"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-169">否</span><span class="sxs-lookup"><span data-stu-id="133e5-169">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-170">會議中所使用的登錄器集區或 Edge Server 名稱。</span><span class="sxs-lookup"><span data-stu-id="133e5-170">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133e5-171"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-171"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-172">否</span><span class="sxs-lookup"><span data-stu-id="133e5-172">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-173">會議的舉行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="133e5-173">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133e5-174"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-174"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-175">否</span><span class="sxs-lookup"><span data-stu-id="133e5-175">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-176">參與者總數、參與者的總分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="133e5-176">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="133e5-177">會議計量 (依伺服器類型)</span><span class="sxs-lookup"><span data-stu-id="133e5-177">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="133e5-178">下表列出會議活動報告針對每種伺服器類型提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="133e5-178">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="133e5-179">會議計量 (依伺服器類型)</span><span class="sxs-lookup"><span data-stu-id="133e5-179">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="133e5-180">姓名</span><span class="sxs-lookup"><span data-stu-id="133e5-180">Name</span></span></th>
<th><span data-ttu-id="133e5-181">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="133e5-181">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="133e5-182">描述</span><span class="sxs-lookup"><span data-stu-id="133e5-182">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="133e5-183"><strong>會議伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-183"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-184">否</span><span class="sxs-lookup"><span data-stu-id="133e5-184">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-185">會議中所使用的伺服器類型一般為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="133e5-185">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="133e5-186">Web 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="133e5-186">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="133e5-187">IM 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="133e5-187">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="133e5-188">電話會議伺服器</span><span class="sxs-lookup"><span data-stu-id="133e5-188">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="133e5-189">音訊/視訊會議伺服器</span><span class="sxs-lookup"><span data-stu-id="133e5-189">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="133e5-190">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="133e5-190">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="133e5-191"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-191"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-192">否</span><span class="sxs-lookup"><span data-stu-id="133e5-192">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-193">會議的舉行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="133e5-193">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="133e5-194"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="133e5-194"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="133e5-195">否</span><span class="sxs-lookup"><span data-stu-id="133e5-195">No</span></span></p></td>
<td><p><span data-ttu-id="133e5-196">參與者總數、參與者的總分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="133e5-196">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

