---
title: Lync Server 2013： 會議活動報告
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
ms.openlocfilehash: 93113f3167cf16733f5c7ab51247dcb57f1a118c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a><span data-ttu-id="618cc-102">Lync Server 2013 中的會議活動報告</span><span class="sxs-lookup"><span data-stu-id="618cc-102">Conference Activity Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="618cc-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="618cc-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="618cc-104">「會議活動報告」可讓您輕鬆回答下列問題：每天舉行了幾場會議？</span><span class="sxs-lookup"><span data-stu-id="618cc-104">The Conference Activity Report makes it easy for you to answer questions like these: how many conferences are being held each day, and when are those conferences being held?</span></span> <span data-ttu-id="618cc-105">這些會議的舉行時間為何？</span><span class="sxs-lookup"><span data-stu-id="618cc-105">Information like this is useful not only in its own right, but also as a troubleshooting tool.</span></span> <span data-ttu-id="618cc-106">這類資訊不只具備本質的意義，也是非常實用的疑難排解工具。</span><span class="sxs-lookup"><span data-stu-id="618cc-106">For example, suppose users are complaining that the network seems particularly slow in the middle of the day.</span></span> <span data-ttu-id="618cc-107">快速檢視會議活動報告可能建議可能的原因之一： 遠會議排定之間的上午 10:00 的時間，然後在任何其他階段 2:00 PM。</span><span class="sxs-lookup"><span data-stu-id="618cc-107">A quick glance at the Conference Activity reports might suggest one possible reason: far more conferences are being scheduled between the hours of 10:00 AM and 2:00 PM then at any other time.</span></span>

<span data-ttu-id="618cc-108">若網路太慢導致了問題，您就可以鼓勵使用者將部分會議重新排程在較為離峰流量的時段。</span><span class="sxs-lookup"><span data-stu-id="618cc-108">If the slow network is causing problems, you can encourage users to reschedule some of their conferences during the less-heavily trafficked times of the day.</span></span>

<div>

## <a name="accessing-the-conference-activity-report"></a><span data-ttu-id="618cc-109">存取會議活動報告</span><span class="sxs-lookup"><span data-stu-id="618cc-109">Accessing the Conference Activity Report</span></span>

<span data-ttu-id="618cc-110">從[Lync Server 2013 中的會議摘要報告](lync-server-2013-conference-summary-report.md)存取會議活動報告按一下下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="618cc-110">The Conference Activity Report is accessed from the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md) by clicking either one of the following metrics:</span></span>

  - <span data-ttu-id="618cc-111">會議總數</span><span class="sxs-lookup"><span data-stu-id="618cc-111">Total conferences</span></span>

  - <span data-ttu-id="618cc-112">參與者總數</span><span class="sxs-lookup"><span data-stu-id="618cc-112">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a><span data-ttu-id="618cc-113">善加利用會議活動報告</span><span class="sxs-lookup"><span data-stu-id="618cc-113">Making the Best Use of the Conference Activity Report</span></span>

<span data-ttu-id="618cc-p102">會議活動報告預設會顯示特定時間範圍內的會議總數 (例如，每天的會議總數，或當天某一小時的會議總數)。不過，您也可以選擇要顯示該時段的參與者總數或參與者總分鐘數。要進行這項作業，您可按一下 [顯示/隱藏參數] 按鈕，以顯示篩選選項，然後從下拉式清單的報告中選取其中一個項目：</span><span class="sxs-lookup"><span data-stu-id="618cc-p102">By default the Conference Activity Report shows you the total number of conferences for the specified time period (for example, the total number of conferences per day, or the total number of conferences per hour of the day). However, you can also choose to display the total number of participants for that time period or the total number of participant minutes. To do that, click the Show/Hide Parameters button to display the filtering options, and then select one of the following from the Report by dropdown list:</span></span>

  - <span data-ttu-id="618cc-117">參與者計數</span><span class="sxs-lookup"><span data-stu-id="618cc-117">Participant count</span></span>

  - <span data-ttu-id="618cc-118">參與者分鐘數</span><span class="sxs-lookup"><span data-stu-id="618cc-118">Participant minutes</span></span>

  - <span data-ttu-id="618cc-119">會議計數</span><span class="sxs-lookup"><span data-stu-id="618cc-119">Conference count</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="618cc-120">篩選</span><span class="sxs-lookup"><span data-stu-id="618cc-120">Filters</span></span>

<span data-ttu-id="618cc-p103">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。下表列出您可以搭配會議活動報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="618cc-p103">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Activity Report.</span></span>

### <a name="conference-activity-report-filters"></a><span data-ttu-id="618cc-123">會議活動報告篩選</span><span class="sxs-lookup"><span data-stu-id="618cc-123">Conference Activity Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="618cc-124">名稱</span><span class="sxs-lookup"><span data-stu-id="618cc-124">Name</span></span></th>
<th><span data-ttu-id="618cc-125">描述</span><span class="sxs-lookup"><span data-stu-id="618cc-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="618cc-126"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-126"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-p104">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="618cc-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="618cc-129">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="618cc-129">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="618cc-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="618cc-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="618cc-132">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="618cc-132">7/7/2012</span></span></p>
<p><span data-ttu-id="618cc-133">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="618cc-133">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="618cc-134">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="618cc-134">7/3/2012</span></span></p>
<p><span data-ttu-id="618cc-135">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="618cc-135">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="618cc-136"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-136"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="618cc-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="618cc-139">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="618cc-139">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="618cc-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="618cc-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="618cc-142">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="618cc-142">7/7/2012</span></span></p>
<p><span data-ttu-id="618cc-143">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="618cc-143">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="618cc-144">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="618cc-144">7/3/2012</span></span></p>
<p><span data-ttu-id="618cc-145">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="618cc-145">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="618cc-146"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-146"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-p108">時間間隔。請選取下列任何一項：</span><span class="sxs-lookup"><span data-stu-id="618cc-p108">Time interval. Select any of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="618cc-149">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="618cc-149">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="618cc-150">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="618cc-150">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="618cc-151">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="618cc-151">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="618cc-152">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="618cc-152">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="618cc-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="618cc-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="618cc-155"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-155"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-p110">指定報告中所要使用的值。您可選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="618cc-p110">Indicates the values to be used in the report. You can select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="618cc-158">參與者計數</span><span class="sxs-lookup"><span data-stu-id="618cc-158">Participant Count</span></span></p></li>
<li><p><span data-ttu-id="618cc-159">參與者分鐘數</span><span class="sxs-lookup"><span data-stu-id="618cc-159">Participant Minutes</span></span></p></li>
<li><p><span data-ttu-id="618cc-160">會議計數</span><span class="sxs-lookup"><span data-stu-id="618cc-160">Conference Count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="618cc-161">會議計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="618cc-161">Metrics for Conferences by Pool</span></span>

<span data-ttu-id="618cc-162">下表列出會議活動報告針對每個集區提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="618cc-162">The following table lists the information in the Conference Activity Report for each pool.</span></span>

### <a name="metrics-for-conferences-by-pool"></a><span data-ttu-id="618cc-163">會議計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="618cc-163">Metrics for Conferences by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="618cc-164">名稱</span><span class="sxs-lookup"><span data-stu-id="618cc-164">Name</span></span></th>
<th><span data-ttu-id="618cc-165">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="618cc-165">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="618cc-166">描述</span><span class="sxs-lookup"><span data-stu-id="618cc-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="618cc-167"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-167"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-168">否</span><span class="sxs-lookup"><span data-stu-id="618cc-168">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-169">會議中所使用的登錄器集區或 Edge Server 名稱。</span><span class="sxs-lookup"><span data-stu-id="618cc-169">Name of the Registrar pool or Edge Server used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="618cc-170"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-170"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-171">否</span><span class="sxs-lookup"><span data-stu-id="618cc-171">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-172">會議的舉行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="618cc-172">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="618cc-173"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-173"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-174">否</span><span class="sxs-lookup"><span data-stu-id="618cc-174">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-175">參與者總數、參與者的總分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="618cc-175">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="618cc-176">會議計量 (依伺服器類型)</span><span class="sxs-lookup"><span data-stu-id="618cc-176">Metrics for Conferences by Server Type</span></span>

<span data-ttu-id="618cc-177">下表列出會議活動報告針對每種伺服器類型提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="618cc-177">The following table lists the information in the Conference Activity Report for each type of server.</span></span>

### <a name="metrics-for-conferences-by-server-type"></a><span data-ttu-id="618cc-178">會議計量 (依伺服器類型)</span><span class="sxs-lookup"><span data-stu-id="618cc-178">Metrics for Conferences by Server Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="618cc-179">名稱</span><span class="sxs-lookup"><span data-stu-id="618cc-179">Name</span></span></th>
<th><span data-ttu-id="618cc-180">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="618cc-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="618cc-181">描述</span><span class="sxs-lookup"><span data-stu-id="618cc-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="618cc-182"><strong>會議伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-182"><strong>Conferencing server type</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-183">否</span><span class="sxs-lookup"><span data-stu-id="618cc-183">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-184">會議中所使用的伺服器類型一般為下列其中一種：</span><span class="sxs-lookup"><span data-stu-id="618cc-184">Type of server used in the conference, typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="618cc-185">Web 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="618cc-185">Web Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="618cc-186">IM 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="618cc-186">IM Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="618cc-187">電話會議伺服器</span><span class="sxs-lookup"><span data-stu-id="618cc-187">Telephony Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="618cc-188">音訊/視訊會議伺服器</span><span class="sxs-lookup"><span data-stu-id="618cc-188">AV Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="618cc-189">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="618cc-189">Application Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="618cc-190"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-190"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-191">否</span><span class="sxs-lookup"><span data-stu-id="618cc-191">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-192">會議的舉行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="618cc-192">Date and time when the conference was held.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="618cc-193"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="618cc-193"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="618cc-194">否</span><span class="sxs-lookup"><span data-stu-id="618cc-194">No</span></span></p></td>
<td><p><span data-ttu-id="618cc-195">參與者總數、參與者的總分鐘數或會議總數。</span><span class="sxs-lookup"><span data-stu-id="618cc-195">Total participant count, total participant minutes, or total conference count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

