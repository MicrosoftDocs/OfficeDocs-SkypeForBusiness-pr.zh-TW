---
title: Lync Server 2013： 失敗散佈報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1531b7b103e3df6f2d165a4fd6fcd3abf100132
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="afa66-102">Lync Server 2013 中的失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="afa66-102">Failure Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afa66-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="afa66-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="afa66-104">失敗散佈報告會在下列類別中為失敗的工作階段進行排名：</span><span class="sxs-lookup"><span data-stu-id="afa66-104">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="afa66-105">最常見診斷原因</span><span class="sxs-lookup"><span data-stu-id="afa66-105">Top diagnostic reasons</span></span>

  - <span data-ttu-id="afa66-106">最常見形式</span><span class="sxs-lookup"><span data-stu-id="afa66-106">Top modalities</span></span>

  - <span data-ttu-id="afa66-107">最常見集區</span><span class="sxs-lookup"><span data-stu-id="afa66-107">Top pools</span></span>

  - <span data-ttu-id="afa66-108">最常見來源</span><span class="sxs-lookup"><span data-stu-id="afa66-108">Top sources</span></span>

  - <span data-ttu-id="afa66-109">最常見元件</span><span class="sxs-lookup"><span data-stu-id="afa66-109">Top components</span></span>

  - <span data-ttu-id="afa66-110">最常見來源使用者</span><span class="sxs-lookup"><span data-stu-id="afa66-110">Top from users</span></span>

  - <span data-ttu-id="afa66-111">最常見目標使用者</span><span class="sxs-lookup"><span data-stu-id="afa66-111">Top to users</span></span>

  - <span data-ttu-id="afa66-112">最常見來源使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="afa66-112">Top from user agents</span></span>

<span data-ttu-id="afa66-p101">您可以使用這些類別來判斷確實發生問題的地方，並在某些情況下判斷發生問題的原因。例如，假設您在某一天記錄了 242 個失敗的音訊/視訊工作階段。如果您查看失敗散佈報告，其中可能會顯示有 237 個失敗的工作階段是發生在您的 Dublin 集區中。這讓您在追蹤和診斷這些失敗背後的原因時可以有一個良好的開端。如果您按一下 **[最常見集區]** 類別下方的 Dublin 集區，就只會看見該集區的失敗散佈報告。接著，您可以開始分析為什麼 Dublin 集區會遇到這麼多問題。</span><span class="sxs-lookup"><span data-stu-id="afa66-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="afa66-119">檢視失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="afa66-119">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="afa66-120">您可以按一下 **[預期失敗次數]** 或 **[未預期失敗次數]** 計量，從下列任一個報告存取失敗散佈報告：</span><span class="sxs-lookup"><span data-stu-id="afa66-120">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="afa66-121">Lync Server 2013 中的最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="afa66-121">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="afa66-122">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="afa66-122">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="afa66-123">Lync Server 2013 中的對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="afa66-123">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="afa66-124">從失敗散佈報告中，您可以按一下下列計量，以檢視[Failure List Report Lync Server 2013 中](lync-server-2013-failure-list-report.md)的任何：</span><span class="sxs-lookup"><span data-stu-id="afa66-124">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="afa66-125">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-125">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="afa66-126">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-126">Top modalities (sessions)</span></span>

  - <span data-ttu-id="afa66-127">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-127">Top pools (sessions)</span></span>

  - <span data-ttu-id="afa66-128">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-128">Top sources (sessions)</span></span>

  - <span data-ttu-id="afa66-129">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-129">Top components (sessions)</span></span>

  - <span data-ttu-id="afa66-130">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-130">Top from users (sessions)</span></span>

  - <span data-ttu-id="afa66-131">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-131">Top to users (sessions)</span></span>

  - <span data-ttu-id="afa66-132">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="afa66-132">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="afa66-133">使用失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="afa66-133">Using the Failure Distribution Report</span></span>

<span data-ttu-id="afa66-p102">根據您的監視器大小和螢幕解析度而定，當您在螢幕上檢視失敗散佈報告時，該報告中顯示的部分資料可能被截斷。這種情況特別會出現在像是使用者代理程式的計量中，因為這類計量含有非常長的標籤。例如，名稱像是 "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" 的使用者代理程式可能只會在螢幕上顯示部分名稱：</span><span class="sxs-lookup"><span data-stu-id="afa66-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="afa66-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="afa66-137">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="afa66-138">幸運地是，您只需在截斷的值上按住滑鼠，就可以看見完整的標籤。</span><span class="sxs-lookup"><span data-stu-id="afa66-138">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="afa66-p103">有一個您可以使用失敗散佈報告來篩選的特別計量是診斷識別碼。如果您在其他報告中看見經過剪裁的相同診斷識別碼，就可以在失敗散佈報告中使用該識別碼來篩選，並取得在失敗工作階段執行期間該識別碼確實出現在何處以及出現的頻率等非常詳盡的內容。</span><span class="sxs-lookup"><span data-stu-id="afa66-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="afa66-141">篩選</span><span class="sxs-lookup"><span data-stu-id="afa66-141">Filters</span></span>

<span data-ttu-id="afa66-p104">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，失敗散佈報告可讓您依活動類型 (對等工作階段或會議工作階段) 之類的項目，或是依每個失敗工作階段隨附的診斷識別碼篩選。</span><span class="sxs-lookup"><span data-stu-id="afa66-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="afa66-144">下表列出您可以用於失敗散佈報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="afa66-144">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="afa66-145">失敗散佈報告篩選</span><span class="sxs-lookup"><span data-stu-id="afa66-145">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-146">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-146">Name</span></span></th>
<th><span data-ttu-id="afa66-147">描述</span><span class="sxs-lookup"><span data-stu-id="afa66-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-148"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-148"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="afa66-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="afa66-151">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="afa66-151">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="afa66-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="afa66-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="afa66-154">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="afa66-154">7/7/2012</span></span></p>
<p><span data-ttu-id="afa66-155">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="afa66-155">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="afa66-156">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="afa66-156">7/3/2012</span></span></p>
<p><span data-ttu-id="afa66-157">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="afa66-157">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-158"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-158"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="afa66-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="afa66-161">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="afa66-161">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="afa66-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="afa66-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="afa66-164">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="afa66-164">7/7/2012</span></span></p>
<p><span data-ttu-id="afa66-165">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="afa66-165">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="afa66-166">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="afa66-166">7/3/2012</span></span></p>
<p><span data-ttu-id="afa66-167">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="afa66-167">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-168"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-168"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p109">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="afa66-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-172"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-172"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p110">篩選的活動類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="afa66-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="afa66-175">[全部]</span><span class="sxs-lookup"><span data-stu-id="afa66-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="afa66-176">端對端</span><span class="sxs-lookup"><span data-stu-id="afa66-176">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="afa66-177">會議</span><span class="sxs-lookup"><span data-stu-id="afa66-177">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-178"><strong>工作階段類別</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-178"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p111">指出有疑問的活動為成功或失敗。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="afa66-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="afa66-181">[全部]</span><span class="sxs-lookup"><span data-stu-id="afa66-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="afa66-182">成功</span><span class="sxs-lookup"><span data-stu-id="afa66-182">Success</span></span></p></li>
<li><p><span data-ttu-id="afa66-183">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="afa66-183">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="afa66-184">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="afa66-184">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="afa66-185">&quot;預期失敗&quot;是預期會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="afa66-185">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="afa66-186">例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="afa66-186">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="afa66-187">&quot;未預期的失敗&quot;是在項目會顯示為否則狀況良好的系統，就會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="afa66-187">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="afa66-188">例如，當發話者處於保留狀態時，不應掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="afa66-188">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="afa66-189">當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="afa66-189">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-190"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-190"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="afa66-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="afa66-193">前幾名診斷原因的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-193">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="afa66-194">下表依據最常報告的診斷識別碼，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-194">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="afa66-195">前幾名診斷原因的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-195">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-196">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-196">Name</span></span></th>
<th><span data-ttu-id="afa66-197">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-197">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-198">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-198">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-199"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-199"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-200">否</span><span class="sxs-lookup"><span data-stu-id="afa66-200">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-p114">依據診斷識別碼的失敗工作階段相對排名。診斷識別碼是附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-203"><strong>前幾名診斷原因</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-203"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-204">否</span><span class="sxs-lookup"><span data-stu-id="afa66-204">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-205">在工作階段產生的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="afa66-205">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-206"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-206"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-207">否</span><span class="sxs-lookup"><span data-stu-id="afa66-207">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-208">產生所指定之診斷識別碼的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-208">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="afa66-209">前幾名形式的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-209">Metrics for Top Modalities</span></span>

<span data-ttu-id="afa66-210">下表依據最常發生失敗的工作階段形式，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-210">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="afa66-211">前幾名形式的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-211">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-212">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-212">Name</span></span></th>
<th><span data-ttu-id="afa66-213">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-214">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-215"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-215"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-216">否</span><span class="sxs-lookup"><span data-stu-id="afa66-216">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-217">依據工作階段類型 (例如，音訊/視訊會議或對等檔案傳輸工作階段) 的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-217">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-218"><strong>前幾名形式</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-218"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-219">否</span><span class="sxs-lookup"><span data-stu-id="afa66-219">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-220">工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="afa66-220">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-221"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-221"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-222">否</span><span class="sxs-lookup"><span data-stu-id="afa66-222">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-223">與指定形式有關的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-223">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="afa66-224">前幾名集區的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-224">Metrics for Top Pools</span></span>

<span data-ttu-id="afa66-225">下表依據最常發生失敗的集區，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-225">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="afa66-226">前幾名集區的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-226">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-227">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-227">Name</span></span></th>
<th><span data-ttu-id="afa66-228">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-228">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-229">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-229">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-230"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-230"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-231">否</span><span class="sxs-lookup"><span data-stu-id="afa66-231">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-232">登錄器集區或 Edge Server 已在單獨執行的工作階段為基礎的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-232">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-233"><strong>前幾名集區</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-233"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-234">否</span><span class="sxs-lookup"><span data-stu-id="afa66-234">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-235">登錄器集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="afa66-235">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-236"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-236"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-237">否</span><span class="sxs-lookup"><span data-stu-id="afa66-237">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-238">每個登錄器集區或 Edge Server 的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-238">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="afa66-239">前幾名來源的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-239">Metrics for Top Sources</span></span>

<span data-ttu-id="afa66-240">下表依據最常發生失敗的電腦，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-240">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="afa66-241">前幾名來源的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-241">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-242">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-242">Name</span></span></th>
<th><span data-ttu-id="afa66-243">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-243">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-244">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-244">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-245"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-245"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-246">否</span><span class="sxs-lookup"><span data-stu-id="afa66-246">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-247">每部電腦的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-247">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-248"><strong>前幾名來源</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-248"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-249">否</span><span class="sxs-lookup"><span data-stu-id="afa66-249">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-250">與失敗工作階段相關的電腦名稱。</span><span class="sxs-lookup"><span data-stu-id="afa66-250">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-251"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-251"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-252">否</span><span class="sxs-lookup"><span data-stu-id="afa66-252">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-253">每部電腦的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-253">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="afa66-254">前幾名元件的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-254">Metrics for Top Components</span></span>

<span data-ttu-id="afa66-255">下表列出根據最常發生失敗的 Microsoft Lync Server 2010 元件失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-255">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="afa66-256">前幾名元件的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-256">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-257">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-257">Name</span></span></th>
<th><span data-ttu-id="afa66-258">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-258">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-259">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-259">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-260"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-260"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-261">否</span><span class="sxs-lookup"><span data-stu-id="afa66-261">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-262">Lync Server 2010 元件 （例如 ExumRouting、 GroupChat 或 MediationServer） 為基礎的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-262">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-263"><strong>前幾名元件</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-263"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-264">否</span><span class="sxs-lookup"><span data-stu-id="afa66-264">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-265">與失敗工作階段相關的元件名稱。</span><span class="sxs-lookup"><span data-stu-id="afa66-265">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-266"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-266"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-267">否</span><span class="sxs-lookup"><span data-stu-id="afa66-267">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-268">每個元件的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-268">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="afa66-269">前幾名發話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-269">Metrics for Top From Users</span></span>

<span data-ttu-id="afa66-270">下表依據最常在嘗試呼叫他人時發生失敗的使用者 (即所謂的「發話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-270">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="afa66-271">前幾名發話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-271">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-272">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-272">Name</span></span></th>
<th><span data-ttu-id="afa66-273">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-273">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-274">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-274">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-275"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-275"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-276">否</span><span class="sxs-lookup"><span data-stu-id="afa66-276">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-277">依據受邀參加工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-277">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-278"><strong>前幾名發話使用者</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-278"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-279">否</span><span class="sxs-lookup"><span data-stu-id="afa66-279">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-280">受邀參加工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="afa66-280">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-281"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-281"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-282">否</span><span class="sxs-lookup"><span data-stu-id="afa66-282">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-283">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-283">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="afa66-284">前幾名受話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-284">Metrics for Top To Users</span></span>

<span data-ttu-id="afa66-285">下表依據最常在其他使用者呼叫他們時發生失敗的使用者 (即所謂的「受話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-285">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-286">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-286">Name</span></span></th>
<th><span data-ttu-id="afa66-287">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-287">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-288">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-288">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-289"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-289"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-290">否</span><span class="sxs-lookup"><span data-stu-id="afa66-290">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-291">依據啟動工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="afa66-291">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-292"><strong>前幾名受話使用者</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-292"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-293">否</span><span class="sxs-lookup"><span data-stu-id="afa66-293">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-294">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="afa66-294">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-295"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-295"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-296">否</span><span class="sxs-lookup"><span data-stu-id="afa66-296">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-297">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-297">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="afa66-298">前幾名使用者代理程式的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-298">Metrics for Top User Agents</span></span>

<span data-ttu-id="afa66-299">下表依據最常發生失敗的端點軟體，列出失敗通訊報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="afa66-299">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="afa66-300">前幾名使用者代理程式的計量</span><span class="sxs-lookup"><span data-stu-id="afa66-300">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="afa66-301">名稱</span><span class="sxs-lookup"><span data-stu-id="afa66-301">Name</span></span></th>
<th><span data-ttu-id="afa66-302">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="afa66-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="afa66-303">說明</span><span class="sxs-lookup"><span data-stu-id="afa66-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="afa66-304"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-304"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-305">否</span><span class="sxs-lookup"><span data-stu-id="afa66-305">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-p115">依據與工作階段相關之使用者代理程式 (軟體) 的失敗工作階段相對排名。例如：RTCC/4.0.0.0 輸入路由/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="afa66-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="afa66-308"><strong>前幾名使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-308"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-309">否</span><span class="sxs-lookup"><span data-stu-id="afa66-309">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-310">與失敗工作階段相關的使用者代理程式名稱。</span><span class="sxs-lookup"><span data-stu-id="afa66-310">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="afa66-311"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="afa66-311"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="afa66-312">否</span><span class="sxs-lookup"><span data-stu-id="afa66-312">No</span></span></p></td>
<td><p><span data-ttu-id="afa66-313">每個使用者代理程式的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="afa66-313">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

