---
title: Lync Server 2013：失敗的發佈報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06481be824f6c51975431aeea2efe27e41eadabc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="c3722-102">Lync Server 2013 中的發佈報告失敗</span><span class="sxs-lookup"><span data-stu-id="c3722-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3722-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="c3722-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c3722-104">失敗的發佈報告在下列類別中排名失敗的會話：</span><span class="sxs-lookup"><span data-stu-id="c3722-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="c3722-105">常見的診斷原因</span><span class="sxs-lookup"><span data-stu-id="c3722-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="c3722-106">上方形式</span><span class="sxs-lookup"><span data-stu-id="c3722-106">Top modalities</span></span>

  - <span data-ttu-id="c3722-107">頂層池</span><span class="sxs-lookup"><span data-stu-id="c3722-107">Top pools</span></span>

  - <span data-ttu-id="c3722-108">熱門來源</span><span class="sxs-lookup"><span data-stu-id="c3722-108">Top sources</span></span>

  - <span data-ttu-id="c3722-109">上方元件</span><span class="sxs-lookup"><span data-stu-id="c3722-109">Top components</span></span>

  - <span data-ttu-id="c3722-110">使用者頂端</span><span class="sxs-lookup"><span data-stu-id="c3722-110">Top from users</span></span>

  - <span data-ttu-id="c3722-111">使用者頂端</span><span class="sxs-lookup"><span data-stu-id="c3722-111">Top to users</span></span>

  - <span data-ttu-id="c3722-112">從使用者代理程式頂端</span><span class="sxs-lookup"><span data-stu-id="c3722-112">Top from user agents</span></span>

<span data-ttu-id="c3722-113">您可以使用這些類別來判斷問題發生的確切位置，在某些情況下，也會發生問題的原因。</span><span class="sxs-lookup"><span data-stu-id="c3722-113">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring.</span></span> <span data-ttu-id="c3722-114">例如，假設您在指定的一天期間記錄了242失敗的音訊/視頻會話。</span><span class="sxs-lookup"><span data-stu-id="c3722-114">For example, suppose you recorded 242 failed audio/video sessions during a given day.</span></span> <span data-ttu-id="c3722-115">如果您看到失敗的發佈報告，可能會顯示您的都柏林池中發生了這些失敗會話的237。</span><span class="sxs-lookup"><span data-stu-id="c3722-115">If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool.</span></span> <span data-ttu-id="c3722-116">這可讓您在追蹤及診斷這些失敗背後的原因時提供良好的開始位置。</span><span class="sxs-lookup"><span data-stu-id="c3722-116">That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures.</span></span> <span data-ttu-id="c3722-117">如果您在 [**頂層池**] 類別底下按一下 [都柏林]，就會看到該群組的 [分發報告] 只出現失敗。</span><span class="sxs-lookup"><span data-stu-id="c3722-117">If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool.</span></span> <span data-ttu-id="c3722-118">然後，您就可以開始分析都柏林池為什麼會遇到這麼多問題。</span><span class="sxs-lookup"><span data-stu-id="c3722-118">You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="c3722-119">查看失敗發佈報告</span><span class="sxs-lookup"><span data-stu-id="c3722-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="c3722-120">您可以按一下**預期的失敗量**或**意外的失敗體積**指標，從下列任何報告存取失敗的發佈報告：</span><span class="sxs-lookup"><span data-stu-id="c3722-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - <span data-ttu-id="c3722-121">[Lync Server 2013 中的 [熱門失敗] 報告](lync-server-2013-top-failures-report.md)</span><span class="sxs-lookup"><span data-stu-id="c3722-121">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)</span></span>

  - [<span data-ttu-id="c3722-122">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="c3722-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="c3722-123">Lync Server 2013 中的對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="c3722-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="c3722-124">從失敗的發佈報告中，您可以按一下下列任何一項測量，以[在 Lync Server 2013 中查看失敗清單報告](lync-server-2013-failure-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="c3722-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="c3722-125">常見的診斷原因（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="c3722-126">熱門形式（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="c3722-127">頂層池（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="c3722-128">熱門來源（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="c3722-129">Top 元件（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-129">Top components (sessions)</span></span>

  - <span data-ttu-id="c3722-130">使用者的最上層（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="c3722-131">使用者的最上層（會話）</span><span class="sxs-lookup"><span data-stu-id="c3722-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="c3722-132">使用者代理程式（會話）的頂端</span><span class="sxs-lookup"><span data-stu-id="c3722-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="c3722-133">使用失敗發佈報告</span><span class="sxs-lookup"><span data-stu-id="c3722-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="c3722-134">視您的監視器大小和螢幕解析度而定，當您在螢幕上查看失敗的發佈報告時，可能會有一些顯示的資料會被截斷。</span><span class="sxs-lookup"><span data-stu-id="c3722-134">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen.</span></span> <span data-ttu-id="c3722-135">特別是對於使用者代理程式（例如使用者代理程式）而言，可能會有非常長的標籤。</span><span class="sxs-lookup"><span data-stu-id="c3722-135">This is especially true for metrics such as user agents, which can have very long labels.</span></span> <span data-ttu-id="c3722-136">例如，名為「UCCAPI/4.0.7400.0 OC/4.0.7400.0 （Microsoft Lync 2013）」的使用者代理程式可能只會部分出現在螢幕上：</span><span class="sxs-lookup"><span data-stu-id="c3722-136">For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="c3722-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 （Microsoft Ly .。。</span><span class="sxs-lookup"><span data-stu-id="c3722-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="c3722-138">幸運的是，您只需將滑鼠放在截斷的值上，就能看到整張標籤。</span><span class="sxs-lookup"><span data-stu-id="c3722-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="c3722-139">您可以使用「失敗發佈」報告篩選的一個有趣的度量單位是 [診斷 ID]。</span><span class="sxs-lookup"><span data-stu-id="c3722-139">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID.</span></span> <span data-ttu-id="c3722-140">如果您在其他報告中看到相同的診斷識別碼，您可以在失敗的發佈報告中篩選該識別碼，並在失敗的會話期間，獲得非常詳細的資訊，以及該識別碼已報告的頻率。</span><span class="sxs-lookup"><span data-stu-id="c3722-140">If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c3722-141">濾鏡</span><span class="sxs-lookup"><span data-stu-id="c3722-141">Filters</span></span>

<span data-ttu-id="c3722-142">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="c3722-142">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c3722-143">例如，失敗的發佈報告可讓您篩選諸如活動類型（點對點工作階段或會議會話）或隨附每個失敗會話的診斷 ID 等專案。</span><span class="sxs-lookup"><span data-stu-id="c3722-143">For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="c3722-144">下表列出您可與失敗發佈報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="c3722-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="c3722-145">失敗的發佈報表篩選</span><span class="sxs-lookup"><span data-stu-id="c3722-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-146">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-146">Name</span></span></th>
<th><span data-ttu-id="c3722-147">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-148"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-149">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="c3722-149">Start date/time for the time range.</span></span> <span data-ttu-id="c3722-150">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3722-150">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c3722-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3722-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3722-152">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="c3722-152">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="c3722-153">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="c3722-153">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3722-154">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3722-154">7/7/2012</span></span></p>
<p><span data-ttu-id="c3722-155">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c3722-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3722-156">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3722-156">7/3/2012</span></span></p>
<p><span data-ttu-id="c3722-157">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="c3722-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-158"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-159">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="c3722-159">End date/time for the time range.</span></span> <span data-ttu-id="c3722-160">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c3722-160">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c3722-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c3722-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c3722-162">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="c3722-162">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="c3722-163">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="c3722-163">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c3722-164">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="c3722-164">7/7/2012</span></span></p>
<p><span data-ttu-id="c3722-165">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="c3722-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c3722-166">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="c3722-166">7/3/2012</span></span></p>
<p><span data-ttu-id="c3722-167">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="c3722-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-168"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-169">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c3722-169">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="c3722-170">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="c3722-170">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="c3722-171">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="c3722-171">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-172"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-173">要篩選的活動類型。</span><span class="sxs-lookup"><span data-stu-id="c3722-173">Type of activity to filter on.</span></span> <span data-ttu-id="c3722-174">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c3722-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3722-175">同時</span><span class="sxs-lookup"><span data-stu-id="c3722-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3722-176">對等</span><span class="sxs-lookup"><span data-stu-id="c3722-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="c3722-177">會議</span><span class="sxs-lookup"><span data-stu-id="c3722-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-178"><strong>會話類別</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-179">指出問題中的活動是否已成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="c3722-179">Indicates whether the activity in question succeeded or failed.</span></span> <span data-ttu-id="c3722-180">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c3722-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3722-181">同時</span><span class="sxs-lookup"><span data-stu-id="c3722-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="c3722-182">成功案例</span><span class="sxs-lookup"><span data-stu-id="c3722-182">Success</span></span></p></li>
<li><p><span data-ttu-id="c3722-183">預期失敗</span><span class="sxs-lookup"><span data-stu-id="c3722-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="c3722-184">意外失敗</span><span class="sxs-lookup"><span data-stu-id="c3722-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="c3722-185">&quot;預期的失敗&quot;是預期發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="c3722-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="c3722-186">例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="c3722-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="c3722-187">發生&quot;意外的&quot;失敗，就是看起來像是其他健康的系統。</span><span class="sxs-lookup"><span data-stu-id="c3722-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="c3722-188">例如，如果來電者停留在 [保留] 上，就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="c3722-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="c3722-189">如果發生這種情況，就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="c3722-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-190"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-191">附加至 SIP 訊息的唯一識別碼（ms diagnostics 標頭形式），通常可在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-191">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="c3722-192">診斷標頭是可選項（有可能是不包含這些標頭的 SIP 會話），而且只會針對遇到某種問題的會話報告診斷 Id。</span><span class="sxs-lookup"><span data-stu-id="c3722-192">Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c3722-193">常見診斷原因的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="c3722-194">下表列出以最常報告的診斷 ID 為基礎的失敗發佈報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="c3722-195">常見診斷原因的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-196">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-196">Name</span></span></th>
<th><span data-ttu-id="c3722-197">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-198">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-199"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-200">否</span><span class="sxs-lookup"><span data-stu-id="c3722-200">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-201">根據診斷識別碼，失敗會話的相對排名。</span><span class="sxs-lookup"><span data-stu-id="c3722-201">Relative ranking of failed sessions based on diagnostic IDs.</span></span> <span data-ttu-id="c3722-202">診斷識別碼是附加至 SIP 訊息的唯一識別碼（以 ms 診斷標頭形式），它通常會在疑難排解錯誤中提供有用的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-202">The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-203"><strong>常見的診斷原因</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-204">否</span><span class="sxs-lookup"><span data-stu-id="c3722-204">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-205">在會話中產生的診斷 ID。</span><span class="sxs-lookup"><span data-stu-id="c3722-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-206"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-207">否</span><span class="sxs-lookup"><span data-stu-id="c3722-207">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-208">產生指定診斷 ID 的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="c3722-209">Top 形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="c3722-210">下表列出根據遇到最多失敗的會話形式，在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="c3722-211">Top 形式的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-212">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-212">Name</span></span></th>
<th><span data-ttu-id="c3722-213">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-214">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-215"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-216">否</span><span class="sxs-lookup"><span data-stu-id="c3722-216">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-217">根據會話類型（例如音訊/視訊會議或對等檔案傳輸會話），以失敗的會話為基礎的相對排名。</span><span class="sxs-lookup"><span data-stu-id="c3722-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-218"><strong>上方形式</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-219">否</span><span class="sxs-lookup"><span data-stu-id="c3722-219">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-220">會話類型。</span><span class="sxs-lookup"><span data-stu-id="c3722-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-221"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-222">否</span><span class="sxs-lookup"><span data-stu-id="c3722-222">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-223">涉及指定模態的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="c3722-224">頂層池的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-224">Metrics for Top Pools</span></span>

<span data-ttu-id="c3722-225">下表列出根據遇到最多失敗的池，在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="c3722-226">頂層池的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-227">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-227">Name</span></span></th>
<th><span data-ttu-id="c3722-228">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-229">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-230"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-231">否</span><span class="sxs-lookup"><span data-stu-id="c3722-231">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-232">根據執行會話的註冊機構池或邊緣伺服器來找出失敗會話的相對等級。</span><span class="sxs-lookup"><span data-stu-id="c3722-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-233"><strong>頂層池</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-234">否</span><span class="sxs-lookup"><span data-stu-id="c3722-234">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-235">註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3722-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-236"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-237">否</span><span class="sxs-lookup"><span data-stu-id="c3722-237">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-238">每個註冊機構池或邊緣伺服器的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="c3722-239">熱門來源的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-239">Metrics for Top Sources</span></span>

<span data-ttu-id="c3722-240">下表列出根據遇到最多失敗的電腦，在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="c3722-241">熱門來源的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-242">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-242">Name</span></span></th>
<th><span data-ttu-id="c3722-243">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-244">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-245"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-246">否</span><span class="sxs-lookup"><span data-stu-id="c3722-246">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-247">每個電腦的相對排名失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="c3722-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-248"><strong>熱門來源</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-249">否</span><span class="sxs-lookup"><span data-stu-id="c3722-249">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-250">失敗會話中所涉及的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c3722-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-251"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-252">否</span><span class="sxs-lookup"><span data-stu-id="c3722-252">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-253">每個電腦的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="c3722-254">Top 元件的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-254">Metrics for Top Components</span></span>

<span data-ttu-id="c3722-255">下表列出根據遇到最多失敗的 Microsoft Lync Server 2010 元件，在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="c3722-256">Top 元件的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-257">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-257">Name</span></span></th>
<th><span data-ttu-id="c3722-258">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-259">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-260"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-261">否</span><span class="sxs-lookup"><span data-stu-id="c3722-261">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-262">根據 Lync Server 2010 元件（例如 ExumRouting、GroupChat 或 MediationServer）而失敗的會話相對排名。</span><span class="sxs-lookup"><span data-stu-id="c3722-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-263"><strong>上方元件</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-264">否</span><span class="sxs-lookup"><span data-stu-id="c3722-264">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-265">失敗會話中所涉及元件的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3722-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-266"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-267">否</span><span class="sxs-lookup"><span data-stu-id="c3722-267">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-268">每個元件的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="c3722-269">使用者的最高指標</span><span class="sxs-lookup"><span data-stu-id="c3722-269">Metrics for Top From Users</span></span>

<span data-ttu-id="c3722-270">下表列出失敗發佈報告中提供的資訊，這些資訊是根據在嘗試呼叫其他人（稱為「寄件者」使用者）時遇到最多失敗的使用者。</span><span class="sxs-lookup"><span data-stu-id="c3722-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="c3722-271">使用者的最高指標</span><span class="sxs-lookup"><span data-stu-id="c3722-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-272">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-272">Name</span></span></th>
<th><span data-ttu-id="c3722-273">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-274">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-275"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-276">否</span><span class="sxs-lookup"><span data-stu-id="c3722-276">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-277">根據受邀加入會話的使用者，對失敗的會話進行相對等級。</span><span class="sxs-lookup"><span data-stu-id="c3722-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-278"><strong>使用者頂端</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-279">否</span><span class="sxs-lookup"><span data-stu-id="c3722-279">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-280">受邀加入會話的使用者 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3722-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-281"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-282">否</span><span class="sxs-lookup"><span data-stu-id="c3722-282">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-283">每個使用者的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="c3722-284">最上層使用者的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-284">Metrics for Top To Users</span></span>

<span data-ttu-id="c3722-285">下表列出失敗發佈報告所提供的資訊，這些資訊是根據在其他使用者嘗試呼叫它們（稱為「收件者」使用者）時遇到最多失敗的使用者所提供。</span><span class="sxs-lookup"><span data-stu-id="c3722-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-286">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-286">Name</span></span></th>
<th><span data-ttu-id="c3722-287">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-288">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-289"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-290">否</span><span class="sxs-lookup"><span data-stu-id="c3722-290">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-291">根據啟動會話的使用者，失敗會話的相對等級。</span><span class="sxs-lookup"><span data-stu-id="c3722-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-292"><strong>使用者頂端</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-293">否</span><span class="sxs-lookup"><span data-stu-id="c3722-293">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-294">啟動會話之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c3722-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-295"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-296">否</span><span class="sxs-lookup"><span data-stu-id="c3722-296">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-297">每個使用者的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c3722-298">主要使用者代理程式的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="c3722-299">下表列出根據遇到最多失敗的端點軟體，在失敗發佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c3722-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="c3722-300">主要使用者代理程式的度量單位</span><span class="sxs-lookup"><span data-stu-id="c3722-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3722-301">名稱</span><span class="sxs-lookup"><span data-stu-id="c3722-301">Name</span></span></th>
<th><span data-ttu-id="c3722-302">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="c3722-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c3722-303">描述</span><span class="sxs-lookup"><span data-stu-id="c3722-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3722-304"><strong>排名</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-305">否</span><span class="sxs-lookup"><span data-stu-id="c3722-305">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-306">根據會話中所涉及的使用者代理程式（軟體），在失敗的會話中相對排名的依據。</span><span class="sxs-lookup"><span data-stu-id="c3722-306">Relative ranking of failed sessions based on the user agent (software) involved in the session.</span></span> <span data-ttu-id="c3722-307">例如： RTCC/4.0.0.0 入站路由/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="c3722-307">For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3722-308"><strong>最上層的使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-309">否</span><span class="sxs-lookup"><span data-stu-id="c3722-309">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-310">失敗會話中所涉及之使用者代理程式的名稱。</span><span class="sxs-lookup"><span data-stu-id="c3722-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3722-311"><strong>時段</strong></span><span class="sxs-lookup"><span data-stu-id="c3722-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c3722-312">否</span><span class="sxs-lookup"><span data-stu-id="c3722-312">No</span></span></p></td>
<td><p><span data-ttu-id="c3722-313">每個使用者代理程式失敗的會話總數。</span><span class="sxs-lookup"><span data-stu-id="c3722-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

