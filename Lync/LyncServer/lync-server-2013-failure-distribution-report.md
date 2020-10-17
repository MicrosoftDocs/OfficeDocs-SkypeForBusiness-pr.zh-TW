---
title: Lync Server 2013：失敗散佈報告
description: Lync Server 2013：失敗散佈報告。
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
ms.openlocfilehash: f5a87f779f87d6b7002fa108f1969c33739eed9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564729"
---
# <a name="failure-distribution-report-in-lync-server-2013"></a><span data-ttu-id="8f5c2-103">Lync Server 2013 的失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-103">Failure Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f5c2-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8f5c2-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8f5c2-105">失敗散佈報告會在下列類別中為失敗的工作階段進行排名：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-105">The Failure Distribution Report ranks failed sessions in the following categories:</span></span>

  - <span data-ttu-id="8f5c2-106">最常見診斷原因</span><span class="sxs-lookup"><span data-stu-id="8f5c2-106">Top diagnostic reasons</span></span>

  - <span data-ttu-id="8f5c2-107">最常見形式</span><span class="sxs-lookup"><span data-stu-id="8f5c2-107">Top modalities</span></span>

  - <span data-ttu-id="8f5c2-108">最常見集區</span><span class="sxs-lookup"><span data-stu-id="8f5c2-108">Top pools</span></span>

  - <span data-ttu-id="8f5c2-109">最常見來源</span><span class="sxs-lookup"><span data-stu-id="8f5c2-109">Top sources</span></span>

  - <span data-ttu-id="8f5c2-110">最常見元件</span><span class="sxs-lookup"><span data-stu-id="8f5c2-110">Top components</span></span>

  - <span data-ttu-id="8f5c2-111">最常見來源使用者</span><span class="sxs-lookup"><span data-stu-id="8f5c2-111">Top from users</span></span>

  - <span data-ttu-id="8f5c2-112">最常見目標使用者</span><span class="sxs-lookup"><span data-stu-id="8f5c2-112">Top to users</span></span>

  - <span data-ttu-id="8f5c2-113">最常見來源使用者代理程式</span><span class="sxs-lookup"><span data-stu-id="8f5c2-113">Top from user agents</span></span>

<span data-ttu-id="8f5c2-p101">您可以使用這些類別來判斷確實發生問題的地方，並在某些情況下判斷發生問題的原因。例如，假設您在某一天記錄了 242 個失敗的音訊/視訊工作階段。如果您查看失敗散佈報告，其中可能會顯示有 237 個失敗的工作階段是發生在您的 Dublin 集區中。這讓您在追蹤和診斷這些失敗背後的原因時可以有一個良好的開端。如果您按一下 **[最常見集區]** 類別下方的 Dublin 集區，就只會看見該集區的失敗散佈報告。接著，您可以開始分析為什麼 Dublin 集區會遇到這麼多問題。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p101">You can use these categories to determine exactly where a problem is occurring and, in some cases, why the problem is occurring. For example, suppose you recorded 242 failed audio/video sessions during a given day. If you look at the Failure Distribution Report, it might show that 237 of those failed sessions took place in your Dublin pool. That gives you a good place to start when it comes to tracking down and diagnosing the causes behind those failures. If you click on the Dublin pool under the **Top pools** category, you will see a Failure Distribution Report just for that pool. You can then begin analyzing why the Dublin pool was experiencing so many difficulties.</span></span>

<div>

## <a name="viewing-the-failure-distribution-report"></a><span data-ttu-id="8f5c2-120">檢視失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-120">Viewing the Failure Distribution Report</span></span>

<span data-ttu-id="8f5c2-121">您可以按一下 **[預期失敗次數]** 或 **[未預期失敗次數]** 計量，從下列任一個報告存取失敗散佈報告：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-121">You can access the Failure Distribution Report from any of the following reports by clicking either the **Expected failure volume** or the **Unexpected failure volume** metric:</span></span>

  - [<span data-ttu-id="8f5c2-122">Lync Server 2013 的最大失敗報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-122">Top Failures Report in Lync Server 2013</span></span>](lync-server-2013-top-failures-report.md)

  - [<span data-ttu-id="8f5c2-123">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-123">Conference Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-conference-diagnostic-report.md)

  - [<span data-ttu-id="8f5c2-124">Lync Server 2013 中的 Peer-to-Peer 活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-124">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

<span data-ttu-id="8f5c2-125">在 [失敗散佈報告] 中，您可以按一下下列任何度量，以 [在 Lync Server 2013 中查看失敗清單報告](lync-server-2013-failure-list-report.md)：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-125">From the Failure Distribution Report, you can click any of the following metrics to view the [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md):</span></span>

  - <span data-ttu-id="8f5c2-126">前幾名診斷原因 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-126">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="8f5c2-127">最常見形式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-127">Top modalities (sessions)</span></span>

  - <span data-ttu-id="8f5c2-128">最常見集區 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-128">Top pools (sessions)</span></span>

  - <span data-ttu-id="8f5c2-129">最常見來源 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-129">Top sources (sessions)</span></span>

  - <span data-ttu-id="8f5c2-130">最常見元件 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-130">Top components (sessions)</span></span>

  - <span data-ttu-id="8f5c2-131">最常見來源使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-131">Top from users (sessions)</span></span>

  - <span data-ttu-id="8f5c2-132">最常見目標使用者 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-132">Top to users (sessions)</span></span>

  - <span data-ttu-id="8f5c2-133">最常見來源使用者代理程式 (工作階段)</span><span class="sxs-lookup"><span data-stu-id="8f5c2-133">Top from user agents (sessions)</span></span>

</div>

<div>

## <a name="using-the-failure-distribution-report"></a><span data-ttu-id="8f5c2-134">使用失敗散佈報告</span><span class="sxs-lookup"><span data-stu-id="8f5c2-134">Using the Failure Distribution Report</span></span>

<span data-ttu-id="8f5c2-p102">根據您的監視器大小和螢幕解析度而定，當您在螢幕上檢視失敗散佈報告時，該報告中顯示的部分資料可能被截斷。這種情況特別會出現在像是使用者代理程式的計量中，因為這類計量含有非常長的標籤。例如，名稱像是 "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" 的使用者代理程式可能只會在螢幕上顯示部分名稱：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p102">Depending on your monitor size and screen resolution, it's possible that some of the data shown in the Failure Distribution Report might be truncated when you view it onscreen. This is especially true for metrics such as user agents, which can have very long labels. For example, a user agent with a name like "UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)" might only partially appear onscreen:</span></span>

<span data-ttu-id="8f5c2-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span><span class="sxs-lookup"><span data-stu-id="8f5c2-138">UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...</span></span>

<span data-ttu-id="8f5c2-139">幸運地是，您只需在截斷的值上按住滑鼠，就可以看見完整的標籤。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-139">Fortunately, you can see the entire label simply by holding your mouse over the truncated value.</span></span>

<span data-ttu-id="8f5c2-p103">有一個您可以使用失敗散佈報告來篩選的特別計量是診斷識別碼。如果您在其他報告中看見經過剪裁的相同診斷識別碼，就可以在失敗散佈報告中使用該識別碼來篩選，並取得在失敗工作階段執行期間該識別碼確實出現在何處以及出現的頻率等非常詳盡的內容。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p103">One interesting metric that you can filter on by using the Failure Distribution Report is Diagnostic ID. If you see the same Diagnostic ID cropping up in other reports you can filter on that ID in the Failure Distribution Report and get a very detailed look at exactly where, and how often, that ID has been reported during a failed session.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8f5c2-142">篩選</span><span class="sxs-lookup"><span data-stu-id="8f5c2-142">Filters</span></span>

<span data-ttu-id="8f5c2-p104">篩選可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，失敗散佈報告可讓您依活動類型 (對等工作階段或會議工作階段) 之類的項目，或是依每個失敗工作階段隨附的診斷識別碼篩選。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Failed Distribution Report enables you to filter on such things as the activity type (peer-to-peer session or conferencing session) or by the diagnostic ID that accompanied each failed session.</span></span>

<span data-ttu-id="8f5c2-145">下表列出您可以用於失敗散佈報告的篩選。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-145">The following table lists the filters that you can use with the Failure Distribution Report.</span></span>

### <a name="failure-distribution-report-filters"></a><span data-ttu-id="8f5c2-146">失敗散佈報告篩選</span><span class="sxs-lookup"><span data-stu-id="8f5c2-146">Failure Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-147">名稱</span><span class="sxs-lookup"><span data-stu-id="8f5c2-147">Name</span></span></th>
<th><span data-ttu-id="8f5c2-148">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8f5c2-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8f5c2-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8f5c2-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8f5c2-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8f5c2-155">7/7/2012</span></span></p>
<p><span data-ttu-id="8f5c2-156">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8f5c2-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8f5c2-157">7/3/2012</span></span></p>
<p><span data-ttu-id="8f5c2-158">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8f5c2-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8f5c2-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8f5c2-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8f5c2-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8f5c2-165">7/7/2012</span></span></p>
<p><span data-ttu-id="8f5c2-166">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8f5c2-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8f5c2-167">7/3/2012</span></span></p>
<p><span data-ttu-id="8f5c2-168">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-169"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-169"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p109">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p109">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-173"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-173"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p110">篩選的活動類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p110">Type of activity to filter on. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f5c2-176">一切</span><span class="sxs-lookup"><span data-stu-id="8f5c2-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="8f5c2-177">對等</span><span class="sxs-lookup"><span data-stu-id="8f5c2-177">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="8f5c2-178">會議</span><span class="sxs-lookup"><span data-stu-id="8f5c2-178">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-179"><strong>工作階段類別</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-179"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p111">指出有疑問的活動為成功或失敗。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p111">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f5c2-182">一切</span><span class="sxs-lookup"><span data-stu-id="8f5c2-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="8f5c2-183">成功</span><span class="sxs-lookup"><span data-stu-id="8f5c2-183">Success</span></span></p></li>
<li><p><span data-ttu-id="8f5c2-184">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="8f5c2-184">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="8f5c2-185">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="8f5c2-185">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="8f5c2-186">&quot;預期的失敗 &quot; 是預期會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-186">An &quot;expected failure&quot; is a failure that is expected to happen.</span></span> <span data-ttu-id="8f5c2-187">例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-187">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="8f5c2-188">未 &quot; 預期的失敗 &quot; 是指出現在其他狀況良好之系統上的失敗。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-188">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="8f5c2-189">例如，當發話者處於保留狀態時，不應掛斷通話。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-189">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="8f5c2-190">當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-190">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-191"><strong>診斷識別碼</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-191"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p113">附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。診斷標頭為選用 (也可能有 SIP 工作階段不包含這些標頭)。只有發生特定問題的工作階段才會回報診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p113">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="8f5c2-194">前幾名診斷原因的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-194">Metrics for Top Diagnostic Reasons</span></span>

<span data-ttu-id="8f5c2-195">下表依據最常報告的診斷識別碼，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-195">The following table lists the information provided in the Failure Distribution Report based on the most frequently reported diagnostic ID.</span></span>

### <a name="metrics-for-top-diagnostic-reasons"></a><span data-ttu-id="8f5c2-196">前幾名診斷原因的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-196">Metrics for Top Diagnostic Reasons</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-197">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-197">Name</span></span></th>
<th><span data-ttu-id="8f5c2-198">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-198">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-199">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-199">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-200"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-200"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-201">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-201">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p114">依據診斷識別碼的失敗工作階段相對排名。診斷識別碼是附加在 SIP 訊息中的唯一識別碼 (採用 ms-diagnostics 標頭的格式)，常可以在疑難排解錯誤時提供實用的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p114">Relative ranking of failed sessions based on diagnostic IDs. The diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-204"><strong>前幾名診斷原因</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-204"><strong>Top diagnostic reasons</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-205">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-205">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-206">在工作階段產生的診斷識別碼。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-206">Diagnostic ID generated in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-207"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-207"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-208">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-208">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-209">產生所指定之診斷識別碼的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-209">Total number of failed sessions where the specified diagnostic ID was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-modalities"></a><span data-ttu-id="8f5c2-210">前幾名形式的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-210">Metrics for Top Modalities</span></span>

<span data-ttu-id="8f5c2-211">下表依據最常發生失敗的工作階段形式，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-211">The following table lists the information provided in the Failure Distribution Report based on the session modalities that experienced the most failures.</span></span>

### <a name="metrics-for-top-modalities"></a><span data-ttu-id="8f5c2-212">前幾名形式的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-212">Metrics for Top Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-213">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-213">Name</span></span></th>
<th><span data-ttu-id="8f5c2-214">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-214">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-215">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-216"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-216"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-217">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-217">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-218">依據工作階段類型 (例如，音訊/視訊會議或對等檔案傳輸工作階段) 的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-218">Relative ranking based of failed session based on session type (for example, an audio/video conference or a peer-to-peer file transfer session).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-219"><strong>前幾名形式</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-219"><strong>Top modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-220">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-220">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-221">工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-221">Session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-222"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-222"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-223">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-223">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-224">與指定形式有關的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-224">Total number of failed sessions involving the specified modality.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-pools"></a><span data-ttu-id="8f5c2-225">前幾名集區的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-225">Metrics for Top Pools</span></span>

<span data-ttu-id="8f5c2-226">下表依據最常發生失敗的集區，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-226">The following table lists the information provided in the Failure Distribution Report based on the pools that experienced the most failures.</span></span>

### <a name="metrics-for-top-pools"></a><span data-ttu-id="8f5c2-227">前幾名集區的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-227">Metrics for Top Pools</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-228">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-228">Name</span></span></th>
<th><span data-ttu-id="8f5c2-229">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-229">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-230">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-230">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-231"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-231"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-232">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-232">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-233">根據執行會話之註冊集區或 Edge Server 之失敗會話的相對排名。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-233">Relative ranking of failed sessions based on the Registrar pool or Edge Server where the session was conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-234"><strong>前幾名集區</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-234"><strong>Top pools</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-235">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-235">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-236">註冊機構集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-236">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-237"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-237"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-238">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-238">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-239">每個註冊集區或 Edge Server 的失敗會話總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-239">Total number of failed sessions per Registrar pool or Edge Server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a><span data-ttu-id="8f5c2-240">前幾名來源的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-240">Metrics for Top Sources</span></span>

<span data-ttu-id="8f5c2-241">下表依據最常發生失敗的電腦，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-241">The following table lists the information provided in the Failure Distribution Report based on the computers that experienced the most failures.</span></span>

### <a name="metrics-for-top-sources"></a><span data-ttu-id="8f5c2-242">前幾名來源的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-242">Metrics for Top Sources</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-243">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-243">Name</span></span></th>
<th><span data-ttu-id="8f5c2-244">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-244">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-245">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-245">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-246"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-246"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-247">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-247">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-248">每部電腦的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-248">Relative ranking failed sessions per computer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-249"><strong>前幾名來源</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-249"><strong>Top sources</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-250">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-250">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-251">與失敗工作階段相關的電腦名稱。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-251">Name of the computer involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-252"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-252"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-253">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-253">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-254">每部電腦的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-254">Total number of failed sessions per computer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-components"></a><span data-ttu-id="8f5c2-255">前幾名元件的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-255">Metrics for Top Components</span></span>

<span data-ttu-id="8f5c2-256">下表根據最近失敗的 Microsoft Lync Server 2010 元件，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-256">The following table lists the information provided in the Failure Distribution Report based on the Microsoft Lync Server 2010 components that experienced the most failures.</span></span>

### <a name="metrics-for-top-components"></a><span data-ttu-id="8f5c2-257">前幾名元件的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-257">Metrics for Top Components</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-258">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-258">Name</span></span></th>
<th><span data-ttu-id="8f5c2-259">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-259">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-260">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-260">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-261"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-261"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-262">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-262">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-263">根據 Lync Server 2010 元件的失敗會話的相對排名 (例如，ExumRouting、GroupChat 或 MediationServer) 。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-263">Relative ranking of failed sessions based on Lync Server 2010 component (for example, ExumRouting, GroupChat, or MediationServer).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-264"><strong>前幾名元件</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-264"><strong>Top components</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-265">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-265">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-266">與失敗工作階段相關的元件名稱。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-266">Name of the component involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-267"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-267"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-268">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-268">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-269">每個元件的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-269">Total number of failed sessions per component.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-from-users"></a><span data-ttu-id="8f5c2-270">前幾名發話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-270">Metrics for Top From Users</span></span>

<span data-ttu-id="8f5c2-271">下表依據最常在嘗試呼叫他人時發生失敗的使用者 (即所謂的「發話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-271">The following table lists the information provided in the Failure Distribution Report based on users who experienced the most failures when they tried to call someone else (known as "From" users).</span></span>

### <a name="metrics-for-top-from-users"></a><span data-ttu-id="8f5c2-272">前幾名發話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-272">Metrics for Top From Users</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-273">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-273">Name</span></span></th>
<th><span data-ttu-id="8f5c2-274">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-274">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-275">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-275">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-276"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-276"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-277">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-277">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-278">依據受邀參加工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-278">Relative ranking of failed sessions based on the user who was invited to join the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-279"><strong>前幾名發話使用者</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-279"><strong>Top from users</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-280">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-280">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-281">受邀參加工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-281">SIP address of the user invited to join the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-282"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-282"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-283">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-283">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-284">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-284">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a><span data-ttu-id="8f5c2-285">前幾名受話使用者的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-285">Metrics for Top To Users</span></span>

<span data-ttu-id="8f5c2-286">下表依據最常在其他使用者呼叫他們時發生失敗的使用者 (即所謂的「受話」使用者)，列出失敗散佈報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-286">The following table lists the information provided in the Failure Distribution Report based on the users who experienced the most failures when another user tried to call them (known as "To" users).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-287">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-287">Name</span></span></th>
<th><span data-ttu-id="8f5c2-288">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-288">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-289">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-289">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-290"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-290"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-291">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-291">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-292">依據啟動工作階段之使用者的失敗工作階段相對排名。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-292">Relative ranking of failed sessions based on the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-293"><strong>前幾名受話使用者</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-293"><strong>Top to users</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-294">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-294">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-295">啟動工作階段之使用者的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-295">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-296"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-296"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-297">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-297">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-298">每位使用者的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-298">Total number of failed sessions per user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-user-agents"></a><span data-ttu-id="8f5c2-299">前幾名使用者代理程式的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-299">Metrics for Top User Agents</span></span>

<span data-ttu-id="8f5c2-300">下表依據最常發生失敗的端點軟體，列出失敗通訊報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-300">The following table lists the information provided in the Failure Distribution Report based on the endpoint software that experienced the most failures.</span></span>

### <a name="metrics-for-top-user-agents"></a><span data-ttu-id="8f5c2-301">前幾名使用者代理程式的計量</span><span class="sxs-lookup"><span data-stu-id="8f5c2-301">Metrics for Top User Agents</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f5c2-302">姓名</span><span class="sxs-lookup"><span data-stu-id="8f5c2-302">Name</span></span></th>
<th><span data-ttu-id="8f5c2-303">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8f5c2-303">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f5c2-304">描述</span><span class="sxs-lookup"><span data-stu-id="8f5c2-304">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-305"><strong>Rank</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-305"><strong>Rank</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-306">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-306">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-p115">依據與工作階段相關之使用者代理程式 (軟體) 的失敗工作階段相對排名。例如：RTCC/4.0.0.0 輸入路由/4.0.0.0。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-p115">Relative ranking of failed sessions based on the user agent (software) involved in the session. For example: RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f5c2-309"><strong>前幾名使用者代理程式</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-309"><strong>Top user agents</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-310">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-310">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-311">與失敗工作階段相關的使用者代理程式名稱。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-311">Name of the user agent involved in the failed session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f5c2-312"><strong>工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="8f5c2-312"><strong>Sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8f5c2-313">否</span><span class="sxs-lookup"><span data-stu-id="8f5c2-313">No</span></span></p></td>
<td><p><span data-ttu-id="8f5c2-314">每個使用者代理程式的失敗工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8f5c2-314">Total number of failed sessions per user agent.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

