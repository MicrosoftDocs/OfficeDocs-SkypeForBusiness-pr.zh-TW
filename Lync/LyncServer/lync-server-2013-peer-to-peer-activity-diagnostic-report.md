---
title: Lync Server 2013：活動診斷報告 Peer-to-Peer
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
ms.openlocfilehash: 53e47232a6345749f78f6136929209722a83621e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524390"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="46577-102">Lync Server 2013 中的 Peer-to-Peer 活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="46577-102">Peer-to-Peer Activity Diagnostic Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46577-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="46577-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="46577-104">對等活動診斷報告提供對等通訊工作階段成功與失敗的資訊。</span><span class="sxs-lookup"><span data-stu-id="46577-104">The Peer-to-Peer Activity Diagnostic Report provides information about the success and failure of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="46577-105">請注意，Microsoft Lync Server 2013 會區別不同類型的失敗：</span><span class="sxs-lookup"><span data-stu-id="46577-105">Note that Microsoft Lync Server 2013 distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="46577-106">**預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="46577-106">**Expected failure**.</span></span> <span data-ttu-id="46577-107">預期的失敗通常是指技術上預期會有的失敗。</span><span class="sxs-lookup"><span data-stu-id="46577-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="46577-108">例如，假設您撥打電話給某人，但是該名人員不在辦公室，而無法接聽電話。</span><span class="sxs-lookup"><span data-stu-id="46577-108">For example, suppose you call someone, but he or she is away from the office and is unable to answer the phone.</span></span> <span data-ttu-id="46577-109">由於無人接聽電話，該通話在技術上會視為失敗。</span><span class="sxs-lookup"><span data-stu-id="46577-109">Because the call was not answered, the call is technically considered a failure.</span></span> <span data-ttu-id="46577-110">另一方面，這是預期的失敗： Microsoft Lync Server 2013 不會期望您在無法接聽電話的情況下接聽電話。</span><span class="sxs-lookup"><span data-stu-id="46577-110">On the other hand, this was an expected failure: Microsoft Lync Server 2013 does not expect you to answer the phone if you're not available to answer the phone.</span></span> <span data-ttu-id="46577-111">同樣地，如果您嘗試將立即訊息傳送給離線的使用者，或傳送給只登入到不支援立即訊息之電話的使用者，則會發生預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="46577-111">Likewise, an expected failure will occur if you attempt to send an instant message to a user who is offline, or is logged on only to a phone that does not support instant messaging.</span></span>

  - <span data-ttu-id="46577-112">**未預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="46577-112">**Unexpected failure**.</span></span> <span data-ttu-id="46577-113">未預期的錯誤正如其名稱所指：在不同的情況下，所發生的未預期錯誤。</span><span class="sxs-lookup"><span data-stu-id="46577-113">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="46577-114">例如，假設您撥打某人，該人員可以接聽來電;不過，當 Lync Server 2013 嘗試將來電路由傳送至語音信箱時，呼叫失敗，因為 Exchange 整合通訊已遺失。</span><span class="sxs-lookup"><span data-stu-id="46577-114">For example, suppose you call someone and that person is available to answer the call; however, when Lync Server 2013 tries to route your call to voicemail the call fails because connectivity to Exchange Unified Messaging has been lost.</span></span> <span data-ttu-id="46577-115">此即為未預期的錯誤：您預期通話一律會轉接到語音信箱。</span><span class="sxs-lookup"><span data-stu-id="46577-115">That's an unexpected error: you would expect that calls could always be routed to voicemail.</span></span> <span data-ttu-id="46577-116">一般而言，未預期的失敗是真正的失敗：這些失敗可能是無法透過教育使用者或類似措施加以補救的問題。</span><span class="sxs-lookup"><span data-stu-id="46577-116">As a general rule, unexpected failures are true failures: they are problems that likely cannot be remedied through user education or similar measures.</span></span>

<span data-ttu-id="46577-p104">請注意，「成功」、「預期的失敗」及「未預期的失敗」計量的總和不一定等於「工作階段總數」計量。例如，在以上說明中，我們有下列值：</span><span class="sxs-lookup"><span data-stu-id="46577-p104">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric. For example, in the preceding illustration, we have the following values:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46577-119">成功</span><span class="sxs-lookup"><span data-stu-id="46577-119">Successes</span></span></th>
<th><span data-ttu-id="46577-120">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="46577-120">Expected failures</span></span></th>
<th><span data-ttu-id="46577-121">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="46577-121">Unexpected failures</span></span></th>
<th><span data-ttu-id="46577-122">工作階段總數</span><span class="sxs-lookup"><span data-stu-id="46577-122">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46577-123">2024</span><span class="sxs-lookup"><span data-stu-id="46577-123">2024</span></span></p></td>
<td><p><span data-ttu-id="46577-124">469</span><span class="sxs-lookup"><span data-stu-id="46577-124">469</span></span></p></td>
<td><p><span data-ttu-id="46577-125">16 </span><span class="sxs-lookup"><span data-stu-id="46577-125">16</span></span></p></td>
<td><p><span data-ttu-id="46577-126">2521</span><span class="sxs-lookup"><span data-stu-id="46577-126">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46577-127">如果將 2024 + 469 + 16，則會得到工作階段總數 2,509，但是 [工作階段總數] 欄顯示工作階段總數為 2,521。</span><span class="sxs-lookup"><span data-stu-id="46577-127">If you add 2024 + 469 + 16 you get a total of 2,509 sessions, yet the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="46577-128">「遺失的」12 個工作階段是系統無法分類為成功或失敗的工作階段。</span><span class="sxs-lookup"><span data-stu-id="46577-128">The "missing" 12 sessions are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="46577-129">在協力廠商產品引進 Lync Server 不熟悉的新診斷碼時，有時候會出現這種情況。</span><span class="sxs-lookup"><span data-stu-id="46577-129">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Lync Server.</span></span> <span data-ttu-id="46577-130">若發生此情況，使用該產品撥打電話後回報該診斷碼，可能無法歸類為「成功」、「預期的失敗」或「未預期的失敗」。</span><span class="sxs-lookup"><span data-stu-id="46577-130">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="46577-131">存取對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="46577-131">Accessing the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="46577-132">對等診斷報告是透過監視報告首頁來存取。</span><span class="sxs-lookup"><span data-stu-id="46577-132">The Peer-to-Peer Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="46577-133">您可以按一下下列其中一個計量， [以在 Lync Server 2013 中存取失敗散佈報告](lync-server-2013-failure-distribution-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="46577-133">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="46577-134">未預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="46577-134">Unexpected failure volume</span></span>

  - <span data-ttu-id="46577-135">預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="46577-135">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a><span data-ttu-id="46577-136">充分運用對等活動診斷報告</span><span class="sxs-lookup"><span data-stu-id="46577-136">Making the Best Use of the Peer-to-Peer Activity Diagnostic Report</span></span>

<span data-ttu-id="46577-p107">您可以透過一些方式來篩選對等活動診斷報告，但是預設無法檢視這些篩選選項。若要檢視可用的篩選選項，請按一下報告視窗右上角的 [顯示/隱藏參數] 按鈕。如此一來，即可使用篩選選項。</span><span class="sxs-lookup"><span data-stu-id="46577-p107">There are a number of ways you can filter the Peer-to-Peer Activity Diagnostic Report but, by default, those filtering options are hidden from view. To view the filtering options available to you, click the Show/Hide Parameters button in the upper right-hand corner of the report window. Once you do that the filtering options will be available for use.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="46577-140">篩選</span><span class="sxs-lookup"><span data-stu-id="46577-140">Filters</span></span>

<span data-ttu-id="46577-p108">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，對等活動診斷報告可以讓您依據工作階段形式等項目 (例如立即訊息、檔案傳輸或應用程式共用) 進行篩選。您也可以選擇資料的分組方式。在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="46577-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Peer-to-Peer Activity Diagnostic Report enables you to filter on such things as the session modality (for example, instant messaging, file transfer, or application sharing). You can also choose how data should be grouped. In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="46577-145">下表列出您可以搭配對等活動診斷報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="46577-145">The following table lists the filters that you can use with the Peer-to-Peer Activity Diagnostic Report.</span></span>

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a><span data-ttu-id="46577-146">對等活動診斷報告篩選器</span><span class="sxs-lookup"><span data-stu-id="46577-146">Peer-to-Peer Activity Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46577-147">名稱</span><span class="sxs-lookup"><span data-stu-id="46577-147">Name</span></span></th>
<th><span data-ttu-id="46577-148">描述</span><span class="sxs-lookup"><span data-stu-id="46577-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46577-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="46577-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-p109">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="46577-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="46577-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="46577-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="46577-p110">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="46577-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="46577-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="46577-155">7/7/2012</span></span></p>
<p><span data-ttu-id="46577-156">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="46577-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="46577-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="46577-157">7/3/2012</span></span></p>
<p><span data-ttu-id="46577-158">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="46577-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46577-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="46577-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-p111">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="46577-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="46577-162">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="46577-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="46577-p112">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="46577-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="46577-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="46577-165">7/7/2012</span></span></p>
<p><span data-ttu-id="46577-166">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="46577-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="46577-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="46577-167">7/3/2012</span></span></p>
<p><span data-ttu-id="46577-168">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="46577-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46577-169"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="46577-169"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-p113">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="46577-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46577-172">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="46577-172">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="46577-173">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="46577-173">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="46577-174">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="46577-174">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="46577-175">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="46577-175">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="46577-p114">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="46577-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46577-178"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="46577-178"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-p115">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="46577-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46577-182"><strong>形態</strong></span><span class="sxs-lookup"><span data-stu-id="46577-182"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-p116">指出發生之通訊活動的類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="46577-p116">Indicates the type of communication activity that took place. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="46577-185">一切</span><span class="sxs-lookup"><span data-stu-id="46577-185">[All]</span></span></p></li>
<li><p><span data-ttu-id="46577-186">立即訊息</span><span class="sxs-lookup"><span data-stu-id="46577-186">Instant messaging</span></span></p></li>
<li><p><span data-ttu-id="46577-187">檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="46577-187">File transfer</span></span></p></li>
<li><p><span data-ttu-id="46577-188">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="46577-188">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="46577-189">音訊</span><span class="sxs-lookup"><span data-stu-id="46577-189">Audio</span></span></p></li>
<li><p><span data-ttu-id="46577-190">影片</span><span class="sxs-lookup"><span data-stu-id="46577-190">Video</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a><span data-ttu-id="46577-191">計量 (每種形式)</span><span class="sxs-lookup"><span data-stu-id="46577-191">Metrics (per modality)</span></span>

<span data-ttu-id="46577-192">下表列出對等活動診斷報告中針對每種形式所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="46577-192">The following table lists the information provided in the Peer-to-Peer Activity Diagnostic Report for each modality.</span></span>

### <a name="metrics-per-modality"></a><span data-ttu-id="46577-193">計量 (每種形式)</span><span class="sxs-lookup"><span data-stu-id="46577-193">Metrics (per modality)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46577-194">姓名</span><span class="sxs-lookup"><span data-stu-id="46577-194">Name</span></span></th>
<th><span data-ttu-id="46577-195">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="46577-195">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="46577-196">描述</span><span class="sxs-lookup"><span data-stu-id="46577-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46577-197"><strong>成功次數</strong></span><span class="sxs-lookup"><span data-stu-id="46577-197"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-198">否</span><span class="sxs-lookup"><span data-stu-id="46577-198">No</span></span></p></td>
<td><p><span data-ttu-id="46577-199">成功的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="46577-199">Total number of successful peer-to-peer sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46577-200"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="46577-200"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-201">否</span><span class="sxs-lookup"><span data-stu-id="46577-201">No</span></span></p></td>
<td><p><span data-ttu-id="46577-p117">完成時具有重大問題的點對點工作階段百分比。計算方式是將成功次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="46577-p117">Percentage of peer-to-peer sessions that completed with significant problems. Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46577-204"><strong>預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="46577-204"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-205">否</span><span class="sxs-lookup"><span data-stu-id="46577-205">No</span></span></p></td>
<td><p><span data-ttu-id="46577-206">預期失敗發生的會話總數 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="46577-206">Total number of sessions where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="46577-p118">預期的失敗是指預期會發生的失敗。例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="46577-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46577-209"><strong>預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="46577-209"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-210">否</span><span class="sxs-lookup"><span data-stu-id="46577-210">No</span></span></p></td>
<td><p><span data-ttu-id="46577-p119">發生預期失敗的點對點工作階段百分比。計算方式是將預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="46577-p119">Percentage of peer-to-peer sessions that experienced an expected error. Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46577-213"><strong>未預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="46577-213"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-214">否</span><span class="sxs-lookup"><span data-stu-id="46577-214">No</span></span></p></td>
<td><p><span data-ttu-id="46577-215">發生未預期失敗之會話的總數 &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="46577-215">Total number of sessions where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="46577-p120">未預期的失敗是指起因於系統不健全的失敗。例如，當發話者處於保留狀態時，不應掛斷通話。當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="46577-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46577-219"><strong>未預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="46577-219"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-220">否</span><span class="sxs-lookup"><span data-stu-id="46577-220">No</span></span></p></td>
<td><p><span data-ttu-id="46577-p121">發生未預期失敗的點對點工作階段百分比。計算方式是將未預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="46577-p121">Percentage of peer-to-peer sessions that experienced an unexpected error. Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46577-223"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="46577-223"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="46577-224">否</span><span class="sxs-lookup"><span data-stu-id="46577-224">No</span></span></p></td>
<td><p><span data-ttu-id="46577-225">工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</span><span class="sxs-lookup"><span data-stu-id="46577-225">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

