---
title: Lync Server 2013：對等 IM 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f44d25ec36788e6964ea81bde71e82f3746c5aee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="fe880-102">Lync Server 2013 中的對等 IM 報表</span><span class="sxs-lookup"><span data-stu-id="fe880-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe880-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fe880-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fe880-104">對等 IM 報告提供對等立即訊息（IM）會話的趨勢資訊，依池和驗證類型細分。</span><span class="sxs-lookup"><span data-stu-id="fe880-104">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type.</span></span> <span data-ttu-id="fe880-105">報告可以顯示在指定時段內所保留的會話總數（例如，按天或按小時計算），也可以顯示在該期間內傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="fe880-105">The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="fe880-106">存取對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="fe880-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="fe880-107">您只能[在 Lync Server 2013 開啟對等 [活動摘要] 報告](lync-server-2013-peer-to-peer-activity-summary-report.md)，然後按一下下列其中一個度量，以存取對等 IM 報告：</span><span class="sxs-lookup"><span data-stu-id="fe880-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="fe880-108">對等 IM 會話總數</span><span class="sxs-lookup"><span data-stu-id="fe880-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="fe880-109">對等 IM 訊息總計</span><span class="sxs-lookup"><span data-stu-id="fe880-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="fe880-110">充分運用對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="fe880-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="fe880-111">根據預設，對等 IM 報表會顯示每小時郵件數（或一天，視您的設定而定）。</span><span class="sxs-lookup"><span data-stu-id="fe880-111">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings).</span></span> <span data-ttu-id="fe880-112">不過，您也可以選擇透過每小時的會話來查看一天。</span><span class="sxs-lookup"><span data-stu-id="fe880-112">However, you can also choose to view the day by sessions per hour.</span></span> <span data-ttu-id="fe880-113">若要這樣做，請按一下 [報表] 視窗右上角的 [**隱藏/顯示參數**]，然後按一下 [**報表依據**] 清單中的 [**會話計數**]。</span><span class="sxs-lookup"><span data-stu-id="fe880-113">To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="fe880-114">濾鏡</span><span class="sxs-lookup"><span data-stu-id="fe880-114">Filters</span></span>

<span data-ttu-id="fe880-115">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="fe880-115">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="fe880-116">下表列出可與對等 IM 報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="fe880-116">The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="fe880-117">對等 IM 報表篩選</span><span class="sxs-lookup"><span data-stu-id="fe880-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe880-118">名稱</span><span class="sxs-lookup"><span data-stu-id="fe880-118">Name</span></span></th>
<th><span data-ttu-id="fe880-119">描述</span><span class="sxs-lookup"><span data-stu-id="fe880-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe880-120"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-121">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fe880-121">Start date and time for the time range.</span></span> <span data-ttu-id="fe880-122">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe880-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="fe880-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fe880-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fe880-124">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="fe880-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="fe880-125">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="fe880-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fe880-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fe880-126">7/7/2012</span></span></p>
<p><span data-ttu-id="fe880-127">若要按周或按月查看，請輸入一周或一月內任何位置的日期（您不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="fe880-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fe880-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fe880-128">7/3/2012</span></span></p>
<p><span data-ttu-id="fe880-129">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="fe880-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe880-130"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-131">時間範圍的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fe880-131">End date and time for the time range.</span></span> <span data-ttu-id="fe880-132">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fe880-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="fe880-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="fe880-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="fe880-134">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="fe880-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="fe880-135">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="fe880-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="fe880-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="fe880-136">7/7/2012</span></span></p>
<p><span data-ttu-id="fe880-137">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="fe880-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="fe880-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="fe880-138">7/3/2012</span></span></p>
<p><span data-ttu-id="fe880-139">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="fe880-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe880-140"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-141">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="fe880-141">Time interval.</span></span> <span data-ttu-id="fe880-142">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe880-142">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fe880-143">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="fe880-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fe880-144">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="fe880-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fe880-145">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="fe880-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="fe880-146">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="fe880-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="fe880-147">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="fe880-147">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="fe880-148">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="fe880-148">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe880-149"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-150">指出要在報表中使用的值。</span><span class="sxs-lookup"><span data-stu-id="fe880-150">Indicates the values to be used in the report.</span></span> <span data-ttu-id="fe880-151">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe880-151">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fe880-152">會話計數</span><span class="sxs-lookup"><span data-stu-id="fe880-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="fe880-153">郵件計數</span><span class="sxs-lookup"><span data-stu-id="fe880-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="fe880-154">依池進行對等 IM 會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="fe880-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="fe880-155">下表列出對等 IM 報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe880-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="fe880-156">依池進行對等 IM 會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="fe880-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe880-157">名稱</span><span class="sxs-lookup"><span data-stu-id="fe880-157">Name</span></span></th>
<th><span data-ttu-id="fe880-158">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="fe880-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fe880-159">描述</span><span class="sxs-lookup"><span data-stu-id="fe880-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe880-160"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-161">否</span><span class="sxs-lookup"><span data-stu-id="fe880-161">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-162">註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="fe880-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe880-163"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-164">否</span><span class="sxs-lookup"><span data-stu-id="fe880-164">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-165">會話發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fe880-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe880-166"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-167">否</span><span class="sxs-lookup"><span data-stu-id="fe880-167">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-168">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="fe880-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="fe880-169">依驗證類型的對等 IM 會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="fe880-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="fe880-170">下表列出點對點工作階段中參與者所使用的每一種驗證類型的對等 IM 報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="fe880-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="fe880-171">依驗證類型的對等 IM 會話的度量單位</span><span class="sxs-lookup"><span data-stu-id="fe880-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe880-172">名稱</span><span class="sxs-lookup"><span data-stu-id="fe880-172">Name</span></span></th>
<th><span data-ttu-id="fe880-173">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="fe880-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="fe880-174">描述</span><span class="sxs-lookup"><span data-stu-id="fe880-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe880-175"><strong>驗證類型</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-176">否</span><span class="sxs-lookup"><span data-stu-id="fe880-176">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-177">會話參與者所使用的驗證類型。</span><span class="sxs-lookup"><span data-stu-id="fe880-177">Type of authentication used by the session participants.</span></span> <span data-ttu-id="fe880-178">值通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fe880-178">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="fe880-179">級</span><span class="sxs-lookup"><span data-stu-id="fe880-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="fe880-180">建立</span><span class="sxs-lookup"><span data-stu-id="fe880-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="fe880-181">PIC</span><span class="sxs-lookup"><span data-stu-id="fe880-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe880-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-183">否</span><span class="sxs-lookup"><span data-stu-id="fe880-183">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-184">會話發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="fe880-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe880-185"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="fe880-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="fe880-186">否</span><span class="sxs-lookup"><span data-stu-id="fe880-186">No</span></span></p></td>
<td><p><span data-ttu-id="fe880-187">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="fe880-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

