---
title: Lync Server 2013：會議加入時間報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fac854b9e296d744473593562f32430c6e21fc87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975730"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a><span data-ttu-id="44b4e-102">Lync Server 2013 中的會議加入時間報告</span><span class="sxs-lookup"><span data-stu-id="44b4e-102">Conference Join Time Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44b4e-103">_**主題上次修改日期：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="44b4e-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="44b4e-104">[會議加入時間摘要] 可讓您判斷使用者加入會議所需的時間。</span><span class="sxs-lookup"><span data-stu-id="44b4e-104">The Conference Join Time Summary enables you to determine how long it takes your users to join a conference.</span></span> <span data-ttu-id="44b4e-105">報告會顯示平均的連線時間（以毫秒為單位），同時也會提供一種細目，讓您知道有多少使用者可以在2秒或更短的時間內加入會議，還有多少使用者需要2到5秒的時間加入會議等。</span><span class="sxs-lookup"><span data-stu-id="44b4e-105">The report shows the average join time (in milliseconds), and also provides a breakdown that lets you know how many users were able to join a conference in 2 seconds or less, how many users required between 2 and 5 seconds to join the conference, and so on.</span></span>

<div>

## <a name="accessing-the-conference-join-time-report"></a><span data-ttu-id="44b4e-106">存取會議加入時間報告</span><span class="sxs-lookup"><span data-stu-id="44b4e-106">Accessing the Conference Join Time Report</span></span>

<span data-ttu-id="44b4e-107">[會議加入時間] 報告可從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="44b4e-107">The Conference Join Time Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="44b4e-108">濾鏡</span><span class="sxs-lookup"><span data-stu-id="44b4e-108">Filters</span></span>

<span data-ttu-id="44b4e-109">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="44b4e-109">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="44b4e-110">下表列出可與會議加入時間報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="44b4e-110">The following table lists the filters that you can use with the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-filters"></a><span data-ttu-id="44b4e-111">會議加入時間報表篩選</span><span class="sxs-lookup"><span data-stu-id="44b4e-111">Conference Join Time Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44b4e-112">名稱</span><span class="sxs-lookup"><span data-stu-id="44b4e-112">Name</span></span></th>
<th><span data-ttu-id="44b4e-113">描述</span><span class="sxs-lookup"><span data-stu-id="44b4e-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-114"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-115">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="44b4e-115">Start date/time for the time range.</span></span> <span data-ttu-id="44b4e-116">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="44b4e-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="44b4e-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="44b4e-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44b4e-118">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="44b4e-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="44b4e-119">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="44b4e-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44b4e-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44b4e-120">7/7/2012</span></span></p>
<p><span data-ttu-id="44b4e-121">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="44b4e-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44b4e-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44b4e-122">7/3/2012</span></span></p>
<p><span data-ttu-id="44b4e-123">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="44b4e-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-124"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-125">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="44b4e-125">End date/time for the time range.</span></span> <span data-ttu-id="44b4e-126">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="44b4e-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="44b4e-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="44b4e-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="44b4e-128">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="44b4e-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="44b4e-129">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="44b4e-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="44b4e-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="44b4e-130">7/7/2012</span></span></p>
<p><span data-ttu-id="44b4e-131">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="44b4e-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="44b4e-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="44b4e-132">7/3/2012</span></span></p>
<p><span data-ttu-id="44b4e-133">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="44b4e-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-134"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-135">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="44b4e-135">Time interval.</span></span> <span data-ttu-id="44b4e-136">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="44b4e-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b4e-137">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="44b4e-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44b4e-138">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="44b4e-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44b4e-139">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="44b4e-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="44b4e-140">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="44b4e-140">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="44b4e-141">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="44b4e-141">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="44b4e-142">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="44b4e-142">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-143"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-143"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-144">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="44b4e-144">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="44b4e-145">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="44b4e-145">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="44b4e-146">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="44b4e-146">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-147"><strong>會議會話</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-147"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-148">會話類型。</span><span class="sxs-lookup"><span data-stu-id="44b4e-148">Type of session.</span></span> <span data-ttu-id="44b4e-149">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="44b4e-149">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="44b4e-150">同時</span><span class="sxs-lookup"><span data-stu-id="44b4e-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="44b4e-151">焦點會話（焦點是線上會議的中心原則和狀態管理員，並協調會議的所有方面</span><span class="sxs-lookup"><span data-stu-id="44b4e-151">Focus sessions (the Focus is the central policy and state manager for online meetings and coordinates all aspects of A conference</span></span></p></li>
<li><p><span data-ttu-id="44b4e-152">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="44b4e-152">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="44b4e-153">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="44b4e-153">A/V conferencing</span></span></p></li>
</ul>
<p><span data-ttu-id="44b4e-154">如果您選取 [全部]，會議加入時間總將會顯示在報表頂端。</span><span class="sxs-lookup"><span data-stu-id="44b4e-154">If you select [All], the total conference join time will be displayed at the top of the report.</span></span> <span data-ttu-id="44b4e-155">請注意，這些總和只適用于使用 Microsoft Exchange 或 Microsoft Outlook 排程的會議。</span><span class="sxs-lookup"><span data-stu-id="44b4e-155">Note that these totals are only for conferences which were scheduled by using Microsoft Exchange or Microsoft Outlook.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="44b4e-156">指標</span><span class="sxs-lookup"><span data-stu-id="44b4e-156">Metrics</span></span>

<span data-ttu-id="44b4e-157">下表列出會議加入時間報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="44b4e-157">The following table lists the information provided in the Conference Join Time Report.</span></span>

### <a name="conference-join-time-report-metrics"></a><span data-ttu-id="44b4e-158">會議加入時間報表度量單位</span><span class="sxs-lookup"><span data-stu-id="44b4e-158">Conference Join Time Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="44b4e-159">名稱</span><span class="sxs-lookup"><span data-stu-id="44b4e-159">Name</span></span></th>
<th><span data-ttu-id="44b4e-160">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="44b4e-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="44b4e-161">描述</span><span class="sxs-lookup"><span data-stu-id="44b4e-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-162"><strong>為止</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-162"><strong>Date</strong></span></span></p>
<p><span data-ttu-id="44b4e-163">這個指標的實際標題會根據所選的間隔而有所不同。</span><span class="sxs-lookup"><span data-stu-id="44b4e-163">The actual title for this metric will vary depending on the Interval that was selected.</span></span></p></td>
<td><p><span data-ttu-id="44b4e-164">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-164">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-165">會議發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="44b4e-165">Date and time that the conference took place.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-166"><strong>總會話數</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-166"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-167">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-167">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-168">會話總數，包括成功的會話、失敗的會話（預期的失敗與意外的失敗），以及未分類的會話。</span><span class="sxs-lookup"><span data-stu-id="44b4e-168">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-169"><strong>Average （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-169"><strong>Average (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-170">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-170">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-171">參與者加入會議所需的平均時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="44b4e-171">Average amount of time (in milliseconds) that it took participants to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-172"><strong>會話&lt; 2 秒，大量</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-172"><strong>Sessions &lt; 2 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-173">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-173">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-174">可在不超過2秒內加入會議的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="44b4e-174">Number of participants who were able to join the conference in less than 2 seconds.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-175"><strong>會話&lt; 2 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-175"><strong>Sessions &lt; 2 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-176">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-176">No</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-177"><strong>會話2-5 秒、成交量</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-177"><strong>Sessions 2-5 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-178">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-178">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-179">在2秒到5秒之間加入會議所需的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="44b4e-179">Number of participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-180"><strong>會話2-5 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-180"><strong>Sessions 2-5 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-181">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-181">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-182">在2秒到5秒之間加入會議所需的呼叫參與者總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="44b4e-182">Percentage of the total call participants who took between 2 seconds and 5 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-183"><strong>會話5-10 秒、成交量</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-183"><strong>Sessions 5-10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-184">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-184">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-185">在5秒到10秒之間加入會議所需的參與者人數。</span><span class="sxs-lookup"><span data-stu-id="44b4e-185">Number of participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-186"><strong>會話5-10 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-186"><strong>Sessions 5-10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-187">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-187">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-188">在5秒和10秒之間加入會議所需的呼叫參與者總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="44b4e-188">Percentage of the total call participants who took between 5 seconds and 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="44b4e-189"><strong>會話&gt; 10 秒、成交量</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-189"><strong>Sessions &gt; 10 seconds, Volume</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-190">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-190">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-191">需要10秒以上的參與者加入會議的人數。</span><span class="sxs-lookup"><span data-stu-id="44b4e-191">Number of participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="44b4e-192"><strong>會話&gt; 10 秒、百分比</strong></span><span class="sxs-lookup"><span data-stu-id="44b4e-192"><strong>Sessions &gt; 10 seconds, Percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="44b4e-193">否</span><span class="sxs-lookup"><span data-stu-id="44b4e-193">No</span></span></p></td>
<td><p><span data-ttu-id="44b4e-194">需要10秒以上的時間來加入會議的呼叫參與者總數的百分比。</span><span class="sxs-lookup"><span data-stu-id="44b4e-194">Percentage of the total call participants who required more than 10 seconds to join the conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

