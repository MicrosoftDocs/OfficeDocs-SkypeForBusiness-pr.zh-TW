---
title: Lync Server 2013： 會議診斷報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6061f04875d15f163bfb91d8803c488467cadb6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="0f4e7-102">Lync Server 2013 中的會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="0f4e7-102">Conference Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f4e7-103">_**主題上次修改日期：** 2012年-10-22_</span><span class="sxs-lookup"><span data-stu-id="0f4e7-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="0f4e7-104">會議診斷報告提供的成功和失敗的所有會議工作階段的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-104">The Conference Diagnostic Report provides information about the success and failure of all conferencing sessions.</span></span> <span data-ttu-id="0f4e7-105">請注意，Microsoft Lync Server 區別不同種類的失敗：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-105">Note that Microsoft Lync Server distinguishes between different kinds of failure:</span></span>

  - <span data-ttu-id="0f4e7-106">**預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-106">**Expected failure**.</span></span> <span data-ttu-id="0f4e7-107">預期的失敗通常是指技術上預期會有的失敗。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-107">An expected failure is typically a failure only in the most technical sense.</span></span> <span data-ttu-id="0f4e7-108">例如，假設有人啟動會議，但是任何人都可以加入之前掛斷。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-108">For example, suppose someone starts a conference but hangs up before anyone can join.</span></span> <span data-ttu-id="0f4e7-109">技術上而言，是失敗： 會議已啟動，但不是會完成。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-109">Technically that's a failure: the conference was initiated, but not completed.</span></span> <span data-ttu-id="0f4e7-110">不過，這是您預期會發生失敗： 如果召集人取消會議，任何人都可以加入接著您應該不會完成該會議之前。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-110">However, that's a failure that you would expect to happen: if the organizer cancels the conference before anyone can join then you would not expect that conference to be completed.</span></span>

  - <span data-ttu-id="0f4e7-111">**未預期的失敗**。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-111">**Unexpected failure**.</span></span> <span data-ttu-id="0f4e7-112">未預期的錯誤正如其名稱所指：在不同的情況下，所發生的未預期錯誤。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-112">An unexpected error is exactly what the name implies: an error that, based on the circumstances, you would not expect to occur.</span></span> <span data-ttu-id="0f4e7-113">例如，假設會議可能不會佔用，因為無法擷取召集人的會議原則。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-113">For example, suppose a conference could not be held because the organizer's meeting policy could not be retrieved.</span></span> <span data-ttu-id="0f4e7-114">這是未預期的錯誤： 所有之後，您應該一律能夠擷取使用者的會議原則。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-114">That's an unexpected error: after all, you should always be able to retrieve a user's meeting policy.</span></span>

<span data-ttu-id="0f4e7-115">請注意，「成功」、「預期的失敗」及「未預期的失敗」計量的總和不一定等於「工作階段總數」計量。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-115">Note that the Success, Expected failure, and Unexpected failure metrics might not add up to the Total sessions metric.</span></span> <span data-ttu-id="0f4e7-116">例如，您可能會看到在報表中的下列值：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-116">For example, you might see the following values in the Report:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f4e7-117">成功</span><span class="sxs-lookup"><span data-stu-id="0f4e7-117">Successes</span></span></th>
<th><span data-ttu-id="0f4e7-118">預期的失敗</span><span class="sxs-lookup"><span data-stu-id="0f4e7-118">Expected failures</span></span></th>
<th><span data-ttu-id="0f4e7-119">未預期的失敗</span><span class="sxs-lookup"><span data-stu-id="0f4e7-119">Unexpected failures</span></span></th>
<th><span data-ttu-id="0f4e7-120">工作階段總數</span><span class="sxs-lookup"><span data-stu-id="0f4e7-120">Total sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-121">2024</span><span class="sxs-lookup"><span data-stu-id="0f4e7-121">2024</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-122">469</span><span class="sxs-lookup"><span data-stu-id="0f4e7-122">469</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-123">16 </span><span class="sxs-lookup"><span data-stu-id="0f4e7-123">16</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-124">2521</span><span class="sxs-lookup"><span data-stu-id="0f4e7-124">2521</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0f4e7-125">如果您新增 2024 + 469 + 16 您收到 2,509 工作階段總計和尚未，工作階段總數] 欄位會顯示 2,521 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-125">If you add 2024 + 469 + 16 you get a total of 2,509 sessions and yet, the Total sessions column shows a total of 2,521 sessions.</span></span> <span data-ttu-id="0f4e7-126">「 缺少 」 12 工作階段是系統找不到分類為成功或失敗的工作階段。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-126">The "missing" 12 sessions for are sessions that the system was unable to categorize as successful or unsuccessful.</span></span> <span data-ttu-id="0f4e7-127">有時會這種情況時的協力廠商產品引進新的診斷程式碼是不太熟悉監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-127">That will sometimes be the case when a third-party product introduces a new diagnostic code that is unfamiliar to Monitoring Server.</span></span> <span data-ttu-id="0f4e7-128">若發生此情況，使用該產品撥打電話後回報該診斷碼，可能無法歸類為「成功」、「預期的失敗」或「未預期的失敗」。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-128">When that happens, calls made using that product, and reporting that diagnostic code, cannot always be categorized as being a Success, an Expected failure, or an Unexpected failure.</span></span>

<div>

## <a name="accessing-the-conference-diagnostic-report"></a><span data-ttu-id="0f4e7-129">存取會議診斷報告</span><span class="sxs-lookup"><span data-stu-id="0f4e7-129">Accessing the Conference Diagnostic Report</span></span>

<span data-ttu-id="0f4e7-130">從監視報告首頁存取會議診斷報告。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-130">The Conference Diagnostic Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0f4e7-131">您可以按一下下列計量之一來存取[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-131">You can access the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="0f4e7-132">未預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="0f4e7-132">Unexpected failure volume</span></span>

  - <span data-ttu-id="0f4e7-133">預期失敗次數</span><span class="sxs-lookup"><span data-stu-id="0f4e7-133">Expected failure volume</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a><span data-ttu-id="0f4e7-134">會議診斷報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="0f4e7-134">Making the Best Use of the Conference Diagnostic Report</span></span>

<span data-ttu-id="0f4e7-135">會議診斷報告包含一系列的圖形。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-135">The Conference Diagnostic Report includes a series of graphs.</span></span> <span data-ttu-id="0f4e7-136">每個圖所示的資料行是實際的超連結。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-136">Each of the columns shown in the graph is actually a hyperlink.</span></span> <span data-ttu-id="0f4e7-137">如果您按一下欄時，您將向下切入[Lync Server 2013 中的失敗散佈報告](lync-server-2013-failure-distribution-report.md)期間與該會議類型。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-137">If you click a column, you'll drill down to the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md) for that time period and that conference type.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0f4e7-138">篩選</span><span class="sxs-lookup"><span data-stu-id="0f4e7-138">Filters</span></span>

<span data-ttu-id="0f4e7-139">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-139">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="0f4e7-140">例如，會議診斷報告可讓您篩選上為正在進行的會議 （例如，基於 Focus 的會議） 或會議中使用的 Edge 伺服器類型等項目。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-140">For example, the Conference Diagnostic Report enables you to filter on such things as the type of conference being conducted (for example, a Focus-based conference) or by the Edge Server used in the conference.</span></span> <span data-ttu-id="0f4e7-141">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-141">You can also choose how data should be grouped.</span></span> <span data-ttu-id="0f4e7-142">在此情況下，會議分組小時、 日、 週或月。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-142">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0f4e7-143">下表列出您可以搭配會議診斷報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-143">The following table lists the filters that you can use with the Conference Diagnostic Report.</span></span>

### <a name="conference-diagnostic-report-filters"></a><span data-ttu-id="0f4e7-144">會議診斷報告篩選器</span><span class="sxs-lookup"><span data-stu-id="0f4e7-144">Conference Diagnostic Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f4e7-145">名稱</span><span class="sxs-lookup"><span data-stu-id="0f4e7-145">Name</span></span></th>
<th><span data-ttu-id="0f4e7-146">描述</span><span class="sxs-lookup"><span data-stu-id="0f4e7-146">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-147"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-147"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-p109">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0f4e7-150">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0f4e7-150">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0f4e7-p110">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0f4e7-153">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="0f4e7-153">7/7/2012</span></span></p>
<p><span data-ttu-id="0f4e7-154">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-154">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0f4e7-155">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="0f4e7-155">7/3/2012</span></span></p>
<p><span data-ttu-id="0f4e7-156">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-156">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4e7-157"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-157"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-p111">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0f4e7-160">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="0f4e7-160">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="0f4e7-p112">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0f4e7-163">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="0f4e7-163">7/7/2012</span></span></p>
<p><span data-ttu-id="0f4e7-164">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0f4e7-165">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="0f4e7-165">7/3/2012</span></span></p>
<p><span data-ttu-id="0f4e7-166">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-167"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-167"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-p113">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p113">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4e7-170">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="0f4e7-170">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-171">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="0f4e7-171">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-172">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="0f4e7-172">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-173">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="0f4e7-173">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="0f4e7-p114">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p114">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4e7-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-p115">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p115">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-180"><strong>會議工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-180"><strong>Conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-181">指出會議工作階段的類型。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-181">Indicates the type of conferencing session.</span></span> <span data-ttu-id="0f4e7-182">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="0f4e7-182">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0f4e7-183">[全部]</span><span class="sxs-lookup"><span data-stu-id="0f4e7-183">[All]</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-184">焦點工作階段</span><span class="sxs-lookup"><span data-stu-id="0f4e7-184">Focus sessions</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-185">所有 MCU 工作階段</span><span class="sxs-lookup"><span data-stu-id="0f4e7-185">All MCU sessions</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-186">IM 會議</span><span class="sxs-lookup"><span data-stu-id="0f4e7-186">IM conferencing</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-187">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="0f4e7-187">Application sharing</span></span></p></li>
<li><p><span data-ttu-id="0f4e7-188">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="0f4e7-188">A/V conferencing</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="0f4e7-189">計量</span><span class="sxs-lookup"><span data-stu-id="0f4e7-189">Metrics</span></span>

<span data-ttu-id="0f4e7-190">下表列出會議工作階段的每一種會議診斷報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-190">The following table lists the information provided in the Conference Diagnostic Report for each type of conferencing session.</span></span>

### <a name="conference-diagnostic-report-metrics"></a><span data-ttu-id="0f4e7-191">會議診斷報告計量</span><span class="sxs-lookup"><span data-stu-id="0f4e7-191">Conference Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f4e7-192">姓名</span><span class="sxs-lookup"><span data-stu-id="0f4e7-192">Name</span></span></th>
<th><span data-ttu-id="0f4e7-193">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="0f4e7-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0f4e7-194">描述</span><span class="sxs-lookup"><span data-stu-id="0f4e7-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-195"><strong>成功次數</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-195"><strong>Success volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-196">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-196">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-197">成功的會議總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-197">Total number of successful conferences.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4e7-198"><strong>成功百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-198"><strong>Success percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-199">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-199">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-200">完成但有重大問題的會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-200">Percentage of conferences that completed with significant problems.</span></span> <span data-ttu-id="0f4e7-201">計算方式是將成功次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-201">Calculated by dividing the Success volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-202"><strong>預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-202"><strong>Expected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-203">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-203">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-204">會議總數：&quot;預期失敗&quot;發生。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-204">Total number of conferences where an &quot;expected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0f4e7-p118">預期的失敗是指預期會發生的失敗。例如，當使用者將其狀態設為「勿打擾」時，即應預期所有撥話給該使用者的通話皆會失敗。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p118">An expected failure is a failure that is expected to happen. For example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4e7-207"><strong>預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-207"><strong>Expected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-208">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-208">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-209">發生預期的錯誤的會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-209">Percentage of conferences that experienced an expected error.</span></span> <span data-ttu-id="0f4e7-210">計算方式是將預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-210">Calculated by dividing the Expected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-211"><strong>未預期失敗次數</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-211"><strong>Unexpected failure volume</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-212">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-212">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-213">會議總數：&quot;未預期的失敗&quot;發生。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-213">Total number of conferences where an &quot;unexpected failure&quot; occurred.</span></span></p>
<p><span data-ttu-id="0f4e7-p120">未預期的失敗是指起因於系統不健全的失敗。例如，當發話者處於保留狀態時，不應掛斷通話。當發生此狀況時，會將其標幟為未預期的失敗。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-p120">An unexpected failure is a failure that occurs in what would appear to be an otherwise healthy system. For example, a call should not be terminated if the caller is placed on hold. If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f4e7-217"><strong>未預期失敗百分比</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-217"><strong>Unexpected failure percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-218">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-218">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-219">發生意外的錯誤的會議的百分比。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-219">Percentage of conferences that experienced an unexpected error.</span></span> <span data-ttu-id="0f4e7-220">計算方式是將未預期失敗次數除以工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-220">Calculated by dividing the Unexpected failure volume by the Total sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f4e7-221"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="0f4e7-221"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="0f4e7-222">否</span><span class="sxs-lookup"><span data-stu-id="0f4e7-222">No</span></span></p></td>
<td><p><span data-ttu-id="0f4e7-223">會議，包括成功的會議、 失敗的會議 （預期的失敗與未預期的失敗），以及未分類的會議總數。</span><span class="sxs-lookup"><span data-stu-id="0f4e7-223">Total number of conferences, including successful conferences, failed conferences (both expected failures and unexpected failures), and uncategorized conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

