---
title: Lync Server 2013：對等語音及視頻報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="4b540-102">Lync Server 2013 中的對等語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="4b540-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b540-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="4b540-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="4b540-104">對等語音及視頻報告提供在指定的一段時間內進行語音與視頻通話的詳細說明（例如，每小時通話數或每天通話數）。</span><span class="sxs-lookup"><span data-stu-id="4b540-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="4b540-105">報告也提供查看所進行的所有語音和視頻通話，或只查看成功或失敗的通話的選項。</span><span class="sxs-lookup"><span data-stu-id="4b540-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="4b540-106">報告顯示在下列群組中細分的通話資訊：</span><span class="sxs-lookup"><span data-stu-id="4b540-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="4b540-107">每個池的通話</span><span class="sxs-lookup"><span data-stu-id="4b540-107">Calls per pool</span></span>

  - <span data-ttu-id="4b540-108">每個通話類型的呼叫（例如，Lync to Lync 通話，以及在 PSTN 網路上將 Lync 呼叫給某個人）</span><span class="sxs-lookup"><span data-stu-id="4b540-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="4b540-109">每個存取類型的通話（已登入內部網路的使用者，與已登入外部網路的使用者）</span><span class="sxs-lookup"><span data-stu-id="4b540-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="4b540-110">每個轉送伺服器的通話</span><span class="sxs-lookup"><span data-stu-id="4b540-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4b540-111">存取對等語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="4b540-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4b540-112">您只能開啟對等活動摘要報告，然後按一下下列任何一個度量，即可存取對等語音及視頻報告：</span><span class="sxs-lookup"><span data-stu-id="4b540-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="4b540-113">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="4b540-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="4b540-114">對等音訊通話總時間</span><span class="sxs-lookup"><span data-stu-id="4b540-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="4b540-115">對等影片會話總數</span><span class="sxs-lookup"><span data-stu-id="4b540-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="4b540-116">對等影片總分鐘數</span><span class="sxs-lookup"><span data-stu-id="4b540-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="4b540-117">若要充分利用對等的語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="4b540-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="4b540-118">您可以透過多種方式來篩選對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="4b540-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="4b540-119">不過，預設不會顯示這些篩選選項。</span><span class="sxs-lookup"><span data-stu-id="4b540-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="4b540-120">若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [**顯示/隱藏參數**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b540-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4b540-121">濾鏡</span><span class="sxs-lookup"><span data-stu-id="4b540-121">Filters</span></span>

<span data-ttu-id="4b540-122">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="4b540-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="4b540-123">下表列出您可以搭配對等語音及視頻報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="4b540-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="4b540-124">對等語音及視頻報表篩選</span><span class="sxs-lookup"><span data-stu-id="4b540-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b540-125">名稱</span><span class="sxs-lookup"><span data-stu-id="4b540-125">Name</span></span></th>
<th><span data-ttu-id="4b540-126">描述</span><span class="sxs-lookup"><span data-stu-id="4b540-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b540-127"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-128">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="4b540-128">Start date and time for the time range.</span></span> <span data-ttu-id="4b540-129">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b540-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4b540-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4b540-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4b540-131">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="4b540-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4b540-132">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="4b540-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4b540-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4b540-133">7/7/2012</span></span></p>
<p><span data-ttu-id="4b540-134">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="4b540-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4b540-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4b540-135">7/3/2012</span></span></p>
<p><span data-ttu-id="4b540-136">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="4b540-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-137"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-138">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="4b540-138">End date/time for the time range.</span></span> <span data-ttu-id="4b540-139">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b540-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4b540-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4b540-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4b540-141">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="4b540-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4b540-142">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="4b540-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4b540-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4b540-143">7/7/2012</span></span></p>
<p><span data-ttu-id="4b540-144">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="4b540-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4b540-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4b540-145">7/3/2012</span></span></p>
<p><span data-ttu-id="4b540-146">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="4b540-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-148">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="4b540-148">Time interval.</span></span> <span data-ttu-id="4b540-149">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-150">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="4b540-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4b540-151">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="4b540-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4b540-152">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="4b540-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4b540-153">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="4b540-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4b540-154">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="4b540-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="4b540-155">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="4b540-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-156"><strong>媒體類型</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-157">指出會話中使用的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="4b540-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="4b540-158">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-159">同時</span><span class="sxs-lookup"><span data-stu-id="4b540-159">Both</span></span></p></li>
<li><p><span data-ttu-id="4b540-160">音訊</span><span class="sxs-lookup"><span data-stu-id="4b540-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="4b540-161">顯示器</span><span class="sxs-lookup"><span data-stu-id="4b540-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-162"><strong>通話處置</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-163">表示會話的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="4b540-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="4b540-164">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-165">同時</span><span class="sxs-lookup"><span data-stu-id="4b540-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="4b540-166">成功通話</span><span class="sxs-lookup"><span data-stu-id="4b540-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="4b540-167">失敗的通話</span><span class="sxs-lookup"><span data-stu-id="4b540-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-168"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-169">指出要在報表中使用的值。</span><span class="sxs-lookup"><span data-stu-id="4b540-169">Indicates the values to be used in the report.</span></span> <span data-ttu-id="4b540-170">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-171">會話計數</span><span class="sxs-lookup"><span data-stu-id="4b540-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="4b540-172">通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="4b540-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4b540-173">依泳池進行對等語音及影片活動的度量單位</span><span class="sxs-lookup"><span data-stu-id="4b540-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="4b540-174">下表列出每個池的對等語音及視頻報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b540-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="4b540-175">依泳池進行對等語音及影片活動的度量單位</span><span class="sxs-lookup"><span data-stu-id="4b540-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b540-176">名稱</span><span class="sxs-lookup"><span data-stu-id="4b540-176">Name</span></span></th>
<th><span data-ttu-id="4b540-177">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="4b540-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b540-178">描述</span><span class="sxs-lookup"><span data-stu-id="4b540-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b540-179"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-180">否</span><span class="sxs-lookup"><span data-stu-id="4b540-180">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-181">用於通話的註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b540-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-183">否</span><span class="sxs-lookup"><span data-stu-id="4b540-183">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-184">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="4b540-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-185"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-186">否</span><span class="sxs-lookup"><span data-stu-id="4b540-186">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-187">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="4b540-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4b540-188">對等語音及影片活動（依呼叫類型）的度量單位</span><span class="sxs-lookup"><span data-stu-id="4b540-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="4b540-189">下表列出針對每種通話類型進行對等語音及視頻報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b540-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="4b540-190">對等語音及影片活動（依呼叫類型）的度量單位</span><span class="sxs-lookup"><span data-stu-id="4b540-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b540-191">名稱</span><span class="sxs-lookup"><span data-stu-id="4b540-191">Name</span></span></th>
<th><span data-ttu-id="4b540-192">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="4b540-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b540-193">描述</span><span class="sxs-lookup"><span data-stu-id="4b540-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b540-194"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-195">否</span><span class="sxs-lookup"><span data-stu-id="4b540-195">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-196">指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="4b540-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="4b540-197">[值] 是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-198">UC 對 UC</span><span class="sxs-lookup"><span data-stu-id="4b540-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4b540-199">UC 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="4b540-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="4b540-200">PSTN 到 UC</span><span class="sxs-lookup"><span data-stu-id="4b540-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="4b540-201">PSTN 到 PSTN</span><span class="sxs-lookup"><span data-stu-id="4b540-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-202"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-203">否</span><span class="sxs-lookup"><span data-stu-id="4b540-203">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-204">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="4b540-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-205"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-206">否</span><span class="sxs-lookup"><span data-stu-id="4b540-206">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-207">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="4b540-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4b540-208">依存取類型的對等語音及影片活動指標</span><span class="sxs-lookup"><span data-stu-id="4b540-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="4b540-209">下表列出針對每種網路存取類型的對等語音及視頻報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b540-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="4b540-210">依存取類型的對等語音及影片活動指標</span><span class="sxs-lookup"><span data-stu-id="4b540-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b540-211">名稱</span><span class="sxs-lookup"><span data-stu-id="4b540-211">Name</span></span></th>
<th><span data-ttu-id="4b540-212">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="4b540-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b540-213">描述</span><span class="sxs-lookup"><span data-stu-id="4b540-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b540-214"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-215">否</span><span class="sxs-lookup"><span data-stu-id="4b540-215">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-216">指出在撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="4b540-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="4b540-217">值通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4b540-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4b540-218">內部</span><span class="sxs-lookup"><span data-stu-id="4b540-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="4b540-219">外來</span><span class="sxs-lookup"><span data-stu-id="4b540-219">External</span></span></p></li>
<li><p><span data-ttu-id="4b540-220">混淆</span><span class="sxs-lookup"><span data-stu-id="4b540-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-221"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-222">否</span><span class="sxs-lookup"><span data-stu-id="4b540-222">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-223">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="4b540-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-224"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-225">否</span><span class="sxs-lookup"><span data-stu-id="4b540-225">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-226">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="4b540-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4b540-227">透過中繼伺服器進行對等語音及影片活動的度量標準</span><span class="sxs-lookup"><span data-stu-id="4b540-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="4b540-228">下表列出每個中繼伺服器的對等語音及視頻報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4b540-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="4b540-229">透過中繼伺服器進行對等語音及影片活動的度量標準</span><span class="sxs-lookup"><span data-stu-id="4b540-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b540-230">名稱</span><span class="sxs-lookup"><span data-stu-id="4b540-230">Name</span></span></th>
<th><span data-ttu-id="4b540-231">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="4b540-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4b540-232">描述</span><span class="sxs-lookup"><span data-stu-id="4b540-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b540-233"><strong>中繼伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-234">否</span><span class="sxs-lookup"><span data-stu-id="4b540-234">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-235">中繼伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="4b540-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b540-236"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-237">否</span><span class="sxs-lookup"><span data-stu-id="4b540-237">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-238">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="4b540-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b540-239"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="4b540-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="4b540-240">否</span><span class="sxs-lookup"><span data-stu-id="4b540-240">No</span></span></p></td>
<td><p><span data-ttu-id="4b540-241">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="4b540-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

