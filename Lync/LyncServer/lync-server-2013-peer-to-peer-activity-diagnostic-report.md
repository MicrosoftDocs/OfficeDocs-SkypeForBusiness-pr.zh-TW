---
title: Lync Server 2013：對等活動診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc98f1c81f79605da2de2b06397d8a23d8086861
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="0720f-102">Lync Server 2013 中的對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="0720f-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0720f-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0720f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0720f-104">對等活動診斷報告可提供對等通訊會話成功與失敗的資訊。</span><span class="sxs-lookup"><span data-stu-id="0720f-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="0720f-105">請注意，Microsoft Lync Server 2013 會區分不同類型的失敗：</span><span class="sxs-lookup"><span data-stu-id="0720f-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="0720f-106">**預期失敗**。</span><span class="sxs-lookup"><span data-stu-id="0720f-106">**Expected failure**.</span></span> <span data-ttu-id="0720f-107">預期的失敗通常是最有技術意義的失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="0720f-108">例如，假設您撥打電話給某人，但他/她不在辦公室，而且無法接聽電話。</span><span class="sxs-lookup"><span data-stu-id="0720f-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="0720f-109">因為通話沒有回應，所以從技術角度來看，該通話是失敗的。</span><span class="sxs-lookup"><span data-stu-id="0720f-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="0720f-110">另一方面，這是預期的失敗：如果您不能接聽電話，Microsoft Lync Server 2013 不會預期您接聽電話。</span><span class="sxs-lookup"><span data-stu-id="0720f-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="0720f-111">同樣地，如果您嘗試將即時消息傳送給離線的使用者，或只登入不支援立即訊息的電話，就會發生預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="0720f-112">未**預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="0720f-112">**Unexpected failure**.</span></span> <span data-ttu-id="0720f-113">不正確的錯誤就是名稱所暗示的錯誤：根據情況而定的錯誤，您不會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="0720f-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="0720f-114">例如，假設您撥打電話給某人，而該人員可接聽來電;不過，當 Lync Server 2013 嘗試將來電傳送到語音信箱時，通話失敗的原因是連線到 Exchange 整合通訊已遺失。</span><span class="sxs-lookup"><span data-stu-id="0720f-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="0720f-115">這是一個意外的錯誤：您預計通話永遠會傳送給語音信箱。</span><span class="sxs-lookup"><span data-stu-id="0720f-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="0720f-116">一般來說，非預期的失敗就是真正的失敗：它們是可能無法透過使用者教育或類似的措施修正的問題。</span><span class="sxs-lookup"><span data-stu-id="0720f-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="0720f-117">請注意，成功、預期的失敗及意外的失敗指標可能不會新增到 [總會話] 度量。</span><span class="sxs-lookup"><span data-stu-id="0720f-117">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="0720f-118">例如，在前面的圖例中，我們有下列值：</span><span class="sxs-lookup"><span data-stu-id="0720f-118">For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0720f-119">成功</span><span class="sxs-lookup"><span data-stu-id="0720f-119">Successes</span></span></th>
<th><span data-ttu-id="0720f-120">預期失敗</span><span class="sxs-lookup"><span data-stu-id="0720f-120">Expected failures</span></span></th>
<th><span data-ttu-id="0720f-121">意外的失敗</span><span class="sxs-lookup"><span data-stu-id="0720f-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="0720f-122">總會話數</span><span class="sxs-lookup"><span data-stu-id="0720f-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0720f-123">2024</span><span class="sxs-lookup"><span data-stu-id="0720f-123">2024</span></span></p></td>
<td><p><span data-ttu-id="0720f-124">469</span><span class="sxs-lookup"><span data-stu-id="0720f-124">469</span></span></p></td>
<td><p><span data-ttu-id="0720f-125">位</span><span class="sxs-lookup"><span data-stu-id="0720f-125">16</span></span></p></td>
<td><p><span data-ttu-id="0720f-126">2521</span><span class="sxs-lookup"><span data-stu-id="0720f-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0720f-127">如果您新增 2024 + 469 + 16，您總共會得到2509個會話，而 [總會話] 資料行則會顯示2521會話總數。</span><span class="sxs-lookup"><span data-stu-id="0720f-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="0720f-128">"遺失" 的12個會話是系統無法分類成成功或失敗的會話。</span><span class="sxs-lookup"><span data-stu-id="0720f-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="0720f-129">當協力廠商產品引入 Lync Server 不熟悉的新診斷程式代碼時，有時候會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="0720f-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="0720f-130">當發生這種情況時，使用該產品進行的通話，並報告該診斷程式代碼，不一定會成為成功、預期的失敗或意外的失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="0720f-131">存取對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="0720f-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="0720f-132">從 [監控報告] 首頁存取對等診斷報告。</span><span class="sxs-lookup"><span data-stu-id="0720f-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0720f-133">您可以按一下下列其中一個度量，[以存取 Lync Server 2013 中的失敗發佈報告](lync-server-2013-failure-distribution-report.md)：</span><span class="sxs-lookup"><span data-stu-id="0720f-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0720f-134">意外的失敗量</span><span class="sxs-lookup"><span data-stu-id="0720f-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="0720f-135">預期失敗的音量</span><span class="sxs-lookup"><span data-stu-id="0720f-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="0720f-136">充分運用對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="0720f-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="0720f-137">有幾種方式可以篩選對等的活動診斷報告，但根據預設，這些篩選選項會在視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="0720f-137">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view.</span></span> <span data-ttu-id="0720f-138">若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [顯示/隱藏參數] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="0720f-138">To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window.</span></span> <span data-ttu-id="0720f-139">一旦您這麼做，就可以使用篩選選項。</span><span class="sxs-lookup"><span data-stu-id="0720f-139">Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0720f-140">濾鏡</span><span class="sxs-lookup"><span data-stu-id="0720f-140">Filters</span></span>

<span data-ttu-id="0720f-141">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0720f-141">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0720f-142">例如，對等活動診斷報告可讓您篩選諸如會話形式（例如立即訊息、檔案傳輸或應用程式共用）等內容。</span><span class="sxs-lookup"><span data-stu-id="0720f-142">For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing).</span></span> <span data-ttu-id="0720f-143">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="0720f-143">You can also choose how data should be grouped.</span></span> <span data-ttu-id="0720f-144">在這種情況下，通話會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="0720f-144">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0720f-145">下表列出您可以搭配對等活動診斷報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="0720f-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="0720f-146">對等活動診斷報表篩選</span><span class="sxs-lookup"><span data-stu-id="0720f-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0720f-147">名稱</span><span class="sxs-lookup"><span data-stu-id="0720f-147">Name</span></span></th>
<th><span data-ttu-id="0720f-148">說明</span><span class="sxs-lookup"><span data-stu-id="0720f-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0720f-149"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-150">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="0720f-150">Start date/time for the time range.</span></span> <span data-ttu-id="0720f-151">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0720f-151">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0720f-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0720f-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0720f-153">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="0720f-153">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0720f-154">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="0720f-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0720f-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0720f-155">7/7/2012</span></span></p>
<p><span data-ttu-id="0720f-156">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0720f-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0720f-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0720f-157">7/3/2012</span></span></p>
<p><span data-ttu-id="0720f-158">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="0720f-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0720f-159"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-160">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="0720f-160">End date/time for the time range.</span></span> <span data-ttu-id="0720f-161">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0720f-161">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0720f-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0720f-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0720f-163">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="0720f-163">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="0720f-164">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="0720f-164">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0720f-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="0720f-165">7/7/2012</span></span></p>
<p><span data-ttu-id="0720f-166">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="0720f-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0720f-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="0720f-167">7/3/2012</span></span></p>
<p><span data-ttu-id="0720f-168">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="0720f-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0720f-169"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-170">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="0720f-170">Time interval.</span></span> <span data-ttu-id="0720f-171">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0720f-171">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0720f-172">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="0720f-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0720f-173">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="0720f-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0720f-174">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="0720f-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0720f-175">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="0720f-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0720f-176">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="0720f-176">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="0720f-177">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="0720f-177">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0720f-178"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-179">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="0720f-179">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="0720f-180">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="0720f-180">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="0720f-181">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="0720f-181">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0720f-182"><strong>模態</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-183">指出發生的溝通活動類型。</span><span class="sxs-lookup"><span data-stu-id="0720f-183">Indicates the type of communication activity that took place.</span></span> <span data-ttu-id="0720f-184">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0720f-184">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0720f-185">同時</span><span class="sxs-lookup"><span data-stu-id="0720f-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="0720f-186">立即訊息</span><span class="sxs-lookup"><span data-stu-id="0720f-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="0720f-187">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="0720f-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="0720f-188">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="0720f-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="0720f-189">音訊</span><span class="sxs-lookup"><span data-stu-id="0720f-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="0720f-190">顯示器</span><span class="sxs-lookup"><span data-stu-id="0720f-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="0720f-191">度量單位（依模態）</span><span class="sxs-lookup"><span data-stu-id="0720f-191">Metrics (per modality)</span></span>

<span data-ttu-id="0720f-192">下表列出針對每個模態的對等活動診斷報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0720f-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="0720f-193">度量單位（依模態）</span><span class="sxs-lookup"><span data-stu-id="0720f-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0720f-194">名稱</span><span class="sxs-lookup"><span data-stu-id="0720f-194">Name</span></span></th>
<th><span data-ttu-id="0720f-195">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="0720f-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0720f-196">說明</span><span class="sxs-lookup"><span data-stu-id="0720f-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0720f-197"><strong>成功的音量</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-198">否</span><span class="sxs-lookup"><span data-stu-id="0720f-198">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-199">成功的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="0720f-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0720f-200"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-201">否</span><span class="sxs-lookup"><span data-stu-id="0720f-201">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-202">已完成且重要問題的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="0720f-202">Percentage of peer-to-peer sessions that completed with significant problems.</span></span> <span data-ttu-id="0720f-203">將成功率除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="0720f-203">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0720f-204"><strong>預期失敗的音量</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-205">否</span><span class="sxs-lookup"><span data-stu-id="0720f-205">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-206">&quot;預期失敗&quot;發生的會話總數。</span><span class="sxs-lookup"><span data-stu-id="0720f-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0720f-207">預期的失敗是預期發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-207">An expected failure is a failure that is expected to happen.</span></span> <span data-ttu-id="0720f-208">例如，如果使用者將自己的狀態設為 [請勿打擾]，您預期該使用者的任何呼叫都會失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-208">For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0720f-209"><strong>預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-210">否</span><span class="sxs-lookup"><span data-stu-id="0720f-210">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-211">遇到預期錯誤的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="0720f-211">Percentage of peer-to-peer sessions that experienced an expected error.</span></span> <span data-ttu-id="0720f-212">將預期的失敗量除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="0720f-212">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0720f-213"><strong>意外的失敗量</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-214">否</span><span class="sxs-lookup"><span data-stu-id="0720f-214">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-215">發生&quot;意外失敗&quot;的會話總數。</span><span class="sxs-lookup"><span data-stu-id="0720f-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0720f-216">發生意外的失敗，就是看起來像是其他健康的系統。</span><span class="sxs-lookup"><span data-stu-id="0720f-216">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="0720f-217">例如，如果來電者停留在 [保留] 上，就不應該終止通話。</span><span class="sxs-lookup"><span data-stu-id="0720f-217">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="0720f-218">如果發生這種情況，就會將它標記為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="0720f-218">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0720f-219"><strong>意外的失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-220">否</span><span class="sxs-lookup"><span data-stu-id="0720f-220">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-221">遇到意外錯誤的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="0720f-221">Percentage of peer-to-peer sessions that experienced an unexpected error.</span></span> <span data-ttu-id="0720f-222">將非預期的失敗量除以總會話數來計算。</span><span class="sxs-lookup"><span data-stu-id="0720f-222">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0720f-223"><strong>總會話數</strong></span><span class="sxs-lookup"><span data-stu-id="0720f-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0720f-224">否</span><span class="sxs-lookup"><span data-stu-id="0720f-224">No</span></span></p></td>
<td><p><span data-ttu-id="0720f-225">會話總數，包括成功的會話、失敗的會話（預期的失敗與意外的失敗），以及未分類的會話。</span><span class="sxs-lookup"><span data-stu-id="0720f-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

