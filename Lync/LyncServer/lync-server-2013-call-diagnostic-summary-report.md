---
title: Lync Server 2013：通話診斷摘要報告
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
ms.openlocfilehash: f70c4fc0987b75cc8c5a8831eb8ad76493fea9b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526320"
---
# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a><span data-ttu-id="f000e-102">Lync Server 2013 中的通話診斷摘要報告</span><span class="sxs-lookup"><span data-stu-id="f000e-102">Call Diagnostic Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f000e-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="f000e-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="f000e-104">通話診斷摘要報告提供失敗的對等和會議會話的整體外觀。</span><span class="sxs-lookup"><span data-stu-id="f000e-104">The Call Diagnostic Summary Report provides an overall look at failed peer-to-peer and conferencing sessions.</span></span> <span data-ttu-id="f000e-105">報告顯示這兩種類型的會話的整體失敗率，並以會話形式的形式進一步打破失敗資訊：</span><span class="sxs-lookup"><span data-stu-id="f000e-105">The report shows the overall failure rate for both types of sessions, and further breaks the failure information down by session modality type:</span></span>

  - <span data-ttu-id="f000e-106">立即訊息</span><span class="sxs-lookup"><span data-stu-id="f000e-106">Instant messaging</span></span>

  - <span data-ttu-id="f000e-107">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="f000e-107">Application sharing</span></span>

  - <span data-ttu-id="f000e-108">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="f000e-108">File transfer</span></span>

  - <span data-ttu-id="f000e-109">音訊</span><span class="sxs-lookup"><span data-stu-id="f000e-109">Audio</span></span>

  - <span data-ttu-id="f000e-110">影片</span><span class="sxs-lookup"><span data-stu-id="f000e-110">Video</span></span>

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a><span data-ttu-id="f000e-111">存取通話診斷摘要報告</span><span class="sxs-lookup"><span data-stu-id="f000e-111">Accessing the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="f000e-112">通話診斷摘要報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="f000e-112">The Call Diagnostic Summary Report is accessed from the Monitoring Reports Home page.</span></span> <span data-ttu-id="f000e-113">在 [通話診斷摘要報告] 中，您可以按一下報告的 [Peer-to-Peer 會話摘要] 區段下的 [失敗率]，即可 [在 [Lync Server 2013] 中存取 Peer-to-Peer 活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) 。</span><span class="sxs-lookup"><span data-stu-id="f000e-113">From the Call Diagnostic Summary Report you can access the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) by clicking the Failure rate metric under the Peer-to-Peer Session Summary section of the report.</span></span> <span data-ttu-id="f000e-114">您也可以按一下下列任一會議計量， [以在 Lync Server 2013 中存取會議診斷報告](lync-server-2013-conference-diagnostic-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="f000e-114">You can also access the [Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) by clicking any of the following conference metrics:</span></span>

  - <span data-ttu-id="f000e-115">整體工作階段失敗率</span><span class="sxs-lookup"><span data-stu-id="f000e-115">Overall session failure rate</span></span>

  - <span data-ttu-id="f000e-116">焦點失敗率</span><span class="sxs-lookup"><span data-stu-id="f000e-116">Focus failure rate</span></span>

  - <span data-ttu-id="f000e-117">MCU 失敗率</span><span class="sxs-lookup"><span data-stu-id="f000e-117">MCU failure rate</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a><span data-ttu-id="f000e-118">通話診斷摘要報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="f000e-118">Making the Best Use of the Call Diagnostic Summary Report</span></span>

<span data-ttu-id="f000e-119">通話診斷摘要報告包含的圖形會比較 Microsoft Lync Server 2013 中使用的各種形式的失敗率。</span><span class="sxs-lookup"><span data-stu-id="f000e-119">The Call Diagnostic Summary Report includes graphs that compare failure rates for the various modalities used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="f000e-120">這些圖形中的資料行實際上是 hotlinks 的;例如，如果按一下點對點工作階段的 [立即訊息] 欄，您會向下流覽 [Lync Server 2013 中 Peer-to-Peer 活動診斷報告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)的實例，該報告提供 [通話診斷摘要報告] 中所包含之所有立即訊息會話的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="f000e-120">The columns in these graphs are actually hotlinks; for example, if you click the Instant messaging column for peer-to-peer sessions, you'll drill down to an instance of the [Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), a report that provides additional details about all the instant messaging sessions included in the Call Diagnostic Summary Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="f000e-121">篩選</span><span class="sxs-lookup"><span data-stu-id="f000e-121">Filters</span></span>

<span data-ttu-id="f000e-122">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="f000e-122">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="f000e-123">例如，[通話診斷摘要] 報告可讓您篩選諸如會話中所使用的註冊區集區或 Edge Server 等事項。</span><span class="sxs-lookup"><span data-stu-id="f000e-123">For example, the Call Diagnostic Summary Report enables you to filter on such things as the Registrar pool or Edge Server used in the session.</span></span> <span data-ttu-id="f000e-124">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="f000e-124">You can also choose how data should be grouped.</span></span> <span data-ttu-id="f000e-125">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="f000e-125">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="f000e-126">下表列出您可以搭配通話診斷摘要報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="f000e-126">The following table lists the filters that you can use with the Call Diagnostic Summary Report.</span></span>

### <a name="call-diagnostic-summary-report-filters"></a><span data-ttu-id="f000e-127">通話診斷摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="f000e-127">Call Diagnostic Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f000e-128">名稱</span><span class="sxs-lookup"><span data-stu-id="f000e-128">Name</span></span></th>
<th><span data-ttu-id="f000e-129">描述</span><span class="sxs-lookup"><span data-stu-id="f000e-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f000e-130"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-130"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f000e-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="f000e-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f000e-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f000e-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="f000e-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f000e-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f000e-136">7/7/2012</span></span></p>
<p><span data-ttu-id="f000e-137">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="f000e-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f000e-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f000e-138">7/3/2012</span></span></p>
<p><span data-ttu-id="f000e-139">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="f000e-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-140"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-140"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f000e-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="f000e-143">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="f000e-143">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="f000e-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="f000e-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="f000e-146">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="f000e-146">7/7/2012</span></span></p>
<p><span data-ttu-id="f000e-147">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="f000e-147">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="f000e-148">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="f000e-148">7/3/2012</span></span></p>
<p><span data-ttu-id="f000e-149">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="f000e-149">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f000e-150"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-150"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-p109">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="f000e-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="f000e-153">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="f000e-153">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f000e-154">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="f000e-154">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f000e-155">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="f000e-155">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="f000e-156">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="f000e-156">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="f000e-p110">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="f000e-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-159"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-159"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-p111">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="f000e-p111">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f000e-163">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="f000e-163">Metrics for Peer-to-Peer Sessions</span></span>

<span data-ttu-id="f000e-164">下表列出點對點工作階段的通話診斷摘要報告所提供的資訊 (也就是說，只涉及兩位參與者) 。</span><span class="sxs-lookup"><span data-stu-id="f000e-164">The following table lists the information provided in the Call Diagnostic Summary Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="f000e-165">Peer-to-Peer 會話的計量</span><span class="sxs-lookup"><span data-stu-id="f000e-165">Metrics for Peer-to-Peer Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f000e-166">姓名</span><span class="sxs-lookup"><span data-stu-id="f000e-166">Name</span></span></th>
<th><span data-ttu-id="f000e-167">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="f000e-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f000e-168">描述</span><span class="sxs-lookup"><span data-stu-id="f000e-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f000e-169"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-169"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-170">否</span><span class="sxs-lookup"><span data-stu-id="f000e-170">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-171">進行中的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="f000e-171">Total number of peer-to-peer sessions conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-172"><strong>失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-172"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-173">否</span><span class="sxs-lookup"><span data-stu-id="f000e-173">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-174">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="f000e-174">Percentage of peer-to-peer sessions that failed.</span></span> <span data-ttu-id="f000e-175">當您按一下此專案時，報告會顯示 Peer-to-Peer 活動診斷報告，其中會顯示失敗的點對點工作階段詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f000e-175">When you click this item, the report shows the Peer-to-Peer Activity Diagnostic report, which displays more detailed information about the failed peer-to-peer sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f000e-176">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="f000e-176">Metrics for Conferencing Sessions</span></span>

<span data-ttu-id="f000e-177">下表列出會議會話的通話診斷報告中所提供的資訊 (也就是說，涉及三個或更多參與者) 的會話。</span><span class="sxs-lookup"><span data-stu-id="f000e-177">The following table lists the information provided in the Call Diagnostic Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="f000e-178">會議會話的計量</span><span class="sxs-lookup"><span data-stu-id="f000e-178">Metrics for Conferencing Sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f000e-179">姓名</span><span class="sxs-lookup"><span data-stu-id="f000e-179">Name</span></span></th>
<th><span data-ttu-id="f000e-180">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="f000e-180">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="f000e-181">描述</span><span class="sxs-lookup"><span data-stu-id="f000e-181">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f000e-182"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-182"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-183">否</span><span class="sxs-lookup"><span data-stu-id="f000e-183">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-184">已執行的會議總數。</span><span class="sxs-lookup"><span data-stu-id="f000e-184">Total number of conferences conducted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-185"><strong>會議工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-185"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-186">否</span><span class="sxs-lookup"><span data-stu-id="f000e-186">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-187">已執行的會議會話總數。</span><span class="sxs-lookup"><span data-stu-id="f000e-187">Total number of conferencing sessions conducted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f000e-188"><strong>整體工作階段失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-188"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-189">否</span><span class="sxs-lookup"><span data-stu-id="f000e-189">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-190">失敗之會議會話總數所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="f000e-190">Percentage of the total conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-191"><strong>焦點工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-191"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-192">否</span><span class="sxs-lookup"><span data-stu-id="f000e-192">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-193">失敗的專注型會議會話總數。</span><span class="sxs-lookup"><span data-stu-id="f000e-193">Total number of Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f000e-194"><strong>焦點失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-194"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-195">否</span><span class="sxs-lookup"><span data-stu-id="f000e-195">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-196">失敗之專注于會議會話的百分比。</span><span class="sxs-lookup"><span data-stu-id="f000e-196">Percentage of the Focus-based conferencing sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f000e-197"><strong>MCU 會話</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-197"><strong>MCU sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-198">否</span><span class="sxs-lookup"><span data-stu-id="f000e-198">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-199">會議服務器型 (的總數（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）。</span><span class="sxs-lookup"><span data-stu-id="f000e-199">Total number of conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f000e-200"><strong>MCU 失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="f000e-200"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="f000e-201">否</span><span class="sxs-lookup"><span data-stu-id="f000e-201">No</span></span></p></td>
<td><p><span data-ttu-id="f000e-202">會議服務器型 (（以前稱為 Multipoint Control Unit 或 MCU) 會議失敗）的百分比。</span><span class="sxs-lookup"><span data-stu-id="f000e-202">Percentage of the conferencing server-based (formerly known as Multipoint Control Unit or MCU) conferences that failed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

