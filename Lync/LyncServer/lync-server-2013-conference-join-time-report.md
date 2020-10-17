---
title: Lync Server 2013：會議加入時間報告
description: Lync Server 2013：會議加入時間報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd4aa5d21a8109a323bb953c7196f43715d51413
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542789"
---
# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="59992-103">Lync Server 2013 中的會議加入時間報告</span><span class="sxs-lookup"><span data-stu-id="59992-103">Conference Join Time Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59992-104">_**主題上次修改日期：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="59992-104">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="59992-105">會議加入時間摘要可讓您判斷使用者加入會議所需的時間。</span><span class="sxs-lookup"><span data-stu-id="59992-105">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="59992-106">報告會以毫秒) 顯示平均加入時間 (，也可讓您知道有多少使用者可以在2秒內加入會議，以及在2到5秒的時間內加入會議，等等。</span><span class="sxs-lookup"><span data-stu-id="59992-106">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="59992-107">存取會議加入時間報告</span><span class="sxs-lookup"><span data-stu-id="59992-107">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="59992-108">會議加入時間報告可以從監控報告首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="59992-108">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="59992-109">篩選</span><span class="sxs-lookup"><span data-stu-id="59992-109">Filters</span></span>

<span data-ttu-id="59992-110">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="59992-110">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="59992-111">下表列出您可以搭配會議加入時間報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="59992-111">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="59992-112">會議加入時間報表篩選</span><span class="sxs-lookup"><span data-stu-id="59992-112">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59992-113">名稱</span><span class="sxs-lookup"><span data-stu-id="59992-113">Name</span></span></th>
<th><span data-ttu-id="59992-114">描述</span><span class="sxs-lookup"><span data-stu-id="59992-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59992-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="59992-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-p103">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59992-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="59992-118">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="59992-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="59992-p104">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="59992-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="59992-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="59992-121">7/7/2012</span></span></p>
<p><span data-ttu-id="59992-122">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="59992-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="59992-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="59992-123">7/3/2012</span></span></p>
<p><span data-ttu-id="59992-124">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="59992-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="59992-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-p105">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="59992-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="59992-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="59992-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="59992-p106">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="59992-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="59992-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="59992-131">7/7/2012</span></span></p>
<p><span data-ttu-id="59992-132">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="59992-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="59992-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="59992-133">7/3/2012</span></span></p>
<p><span data-ttu-id="59992-134">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="59992-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-135"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="59992-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-p107">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="59992-p107">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="59992-138">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="59992-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="59992-139">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="59992-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="59992-140">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="59992-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="59992-141">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="59992-141">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="59992-p108">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="59992-p108">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-144"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="59992-144"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-p109">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="59992-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-148"><strong>會議會話</strong></span><span class="sxs-lookup"><span data-stu-id="59992-148"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-149">會話類型。</span><span class="sxs-lookup"><span data-stu-id="59992-149">Type of session.</span></span> <span data-ttu-id="59992-150">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="59992-150">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="59992-151">一切</span><span class="sxs-lookup"><span data-stu-id="59992-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="59992-152">焦點會話 (焦點是線上會議的中央原則和狀態管理員，並協調會議的各個方面</span><span class="sxs-lookup"><span data-stu-id="59992-152">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="59992-153">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="59992-153">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="59992-154">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="59992-154">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="59992-155">如果您選取 [全部]，會議加入時間的總數將會顯示在報告的頂端。</span><span class="sxs-lookup"><span data-stu-id="59992-155">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="59992-156">請注意，這些總和只適用于使用 Microsoft Exchange 或 Microsoft Outlook 排程的會議。</span><span class="sxs-lookup"><span data-stu-id="59992-156">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="59992-157">指標</span><span class="sxs-lookup"><span data-stu-id="59992-157">Metrics</span></span>

<span data-ttu-id="59992-158">下表列出會議加入時間報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="59992-158">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="59992-159">會議加入時間報表計量</span><span class="sxs-lookup"><span data-stu-id="59992-159">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59992-160">姓名</span><span class="sxs-lookup"><span data-stu-id="59992-160">Name</span></span></th>
<th><span data-ttu-id="59992-161">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="59992-161">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="59992-162">描述</span><span class="sxs-lookup"><span data-stu-id="59992-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59992-163"><strong>Date</strong></span><span class="sxs-lookup"><span data-stu-id="59992-163"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="59992-164">此度量值的實際標題會因所選取的間隔而異。</span><span class="sxs-lookup"><span data-stu-id="59992-164">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="59992-165">否</span><span class="sxs-lookup"><span data-stu-id="59992-165">No</span></span></p></td>
<td><p><span data-ttu-id="59992-166">召開會議的日期與時間。</span><span class="sxs-lookup"><span data-stu-id="59992-166">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-167"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="59992-167"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-168">否</span><span class="sxs-lookup"><span data-stu-id="59992-168">No</span></span></p></td>
<td><p><span data-ttu-id="59992-169">工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</span><span class="sxs-lookup"><span data-stu-id="59992-169">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-170"><strong>平均 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="59992-170"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-171">否</span><span class="sxs-lookup"><span data-stu-id="59992-171">No</span></span></p></td>
<td><p><span data-ttu-id="59992-172"> (以毫秒為單位) 參與者加入會議所需的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="59992-172">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-173"><strong>會話 &lt; 2 秒，大量</strong></span><span class="sxs-lookup"><span data-stu-id="59992-173"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-174">否</span><span class="sxs-lookup"><span data-stu-id="59992-174">No</span></span></p></td>
<td><p><span data-ttu-id="59992-175">可在2秒內加入會議的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="59992-175">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-176"><strong>會話 &lt; 2 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="59992-176"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-177">否</span><span class="sxs-lookup"><span data-stu-id="59992-177">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-178"><strong>會話2-5 秒、磁片區</strong></span><span class="sxs-lookup"><span data-stu-id="59992-178"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-179">否</span><span class="sxs-lookup"><span data-stu-id="59992-179">No</span></span></p></td>
<td><p><span data-ttu-id="59992-180">需要2秒到5秒才能加入會議的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="59992-180">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-181"><strong>會話2-5 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="59992-181"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-182">否</span><span class="sxs-lookup"><span data-stu-id="59992-182">No</span></span></p></td>
<td><p><span data-ttu-id="59992-183">在2秒到5秒內加入會議的總通話參與者百分比。</span><span class="sxs-lookup"><span data-stu-id="59992-183">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-184"><strong>會話5-10 秒、磁片區</strong></span><span class="sxs-lookup"><span data-stu-id="59992-184"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-185">否</span><span class="sxs-lookup"><span data-stu-id="59992-185">No</span></span></p></td>
<td><p><span data-ttu-id="59992-186">需要5秒和10秒才能加入會議的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="59992-186">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-187"><strong>會話5-10 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="59992-187"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-188">否</span><span class="sxs-lookup"><span data-stu-id="59992-188">No</span></span></p></td>
<td><p><span data-ttu-id="59992-189">在5秒及10秒內加入會議的總通話參與者百分比。</span><span class="sxs-lookup"><span data-stu-id="59992-189">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59992-190"><strong>會話 &gt; 10 秒、磁片區</strong></span><span class="sxs-lookup"><span data-stu-id="59992-190"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-191">否</span><span class="sxs-lookup"><span data-stu-id="59992-191">No</span></span></p></td>
<td><p><span data-ttu-id="59992-192">需要超過10秒才能加入會議的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="59992-192">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59992-193"><strong>會話 &gt; 10 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="59992-193"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="59992-194">否</span><span class="sxs-lookup"><span data-stu-id="59992-194">No</span></span></p></td>
<td><p><span data-ttu-id="59992-195">需要超過10秒才能加入會議的通話總人數百分比。</span><span class="sxs-lookup"><span data-stu-id="59992-195">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

