---
title: Lync Server 2013：對等語音及視頻報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68cddb8296a94ff5d5b084895024d7379a42022c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="d483f-102">Lync Server 2013 中的對等語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="d483f-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d483f-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d483f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d483f-104">對等語音及視頻報告提供在指定的一段時間內進行語音與視頻通話的詳細說明（例如，每小時通話數或每天通話數）。</span><span class="sxs-lookup"><span data-stu-id="d483f-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="d483f-105">報告也提供查看所進行的所有語音和視頻通話，或只查看成功或失敗的通話的選項。</span><span class="sxs-lookup"><span data-stu-id="d483f-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="d483f-106">報告顯示在下列群組中細分的通話資訊：</span><span class="sxs-lookup"><span data-stu-id="d483f-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="d483f-107">每個池的通話</span><span class="sxs-lookup"><span data-stu-id="d483f-107">Calls per pool</span></span>

  - <span data-ttu-id="d483f-108">每個通話類型的呼叫（例如，Lync to Lync 通話，以及在 PSTN 網路上將 Lync 呼叫給某個人）</span><span class="sxs-lookup"><span data-stu-id="d483f-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="d483f-109">每個存取類型的通話（已登入內部網路的使用者，與已登入外部網路的使用者）</span><span class="sxs-lookup"><span data-stu-id="d483f-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="d483f-110">每個轉送伺服器的通話</span><span class="sxs-lookup"><span data-stu-id="d483f-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="d483f-111">存取對等語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="d483f-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="d483f-112">您只能開啟對等活動摘要報告，然後按一下下列任何一個度量，即可存取對等語音及視頻報告：</span><span class="sxs-lookup"><span data-stu-id="d483f-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="d483f-113">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="d483f-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d483f-114">對等音訊通話總時間</span><span class="sxs-lookup"><span data-stu-id="d483f-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="d483f-115">對等影片會話總數</span><span class="sxs-lookup"><span data-stu-id="d483f-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="d483f-116">對等影片總分鐘數</span><span class="sxs-lookup"><span data-stu-id="d483f-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="d483f-117">若要充分利用對等的語音及視頻報告</span><span class="sxs-lookup"><span data-stu-id="d483f-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="d483f-118">您可以透過多種方式來篩選對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="d483f-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="d483f-119">不過，預設不會顯示這些篩選選項。</span><span class="sxs-lookup"><span data-stu-id="d483f-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="d483f-120">若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [**顯示/隱藏參數**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d483f-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d483f-121">濾鏡</span><span class="sxs-lookup"><span data-stu-id="d483f-121">Filters</span></span>

<span data-ttu-id="d483f-122">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看資料。</span><span class="sxs-lookup"><span data-stu-id="d483f-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="d483f-123">下表列出您可以搭配對等語音及視頻報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="d483f-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="d483f-124">對等語音及視頻報表篩選</span><span class="sxs-lookup"><span data-stu-id="d483f-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d483f-125">名稱</span><span class="sxs-lookup"><span data-stu-id="d483f-125">Name</span></span></th>
<th><span data-ttu-id="d483f-126">說明</span><span class="sxs-lookup"><span data-stu-id="d483f-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d483f-127"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-128">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d483f-128">Start date and time for the time range.</span></span> <span data-ttu-id="d483f-129">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d483f-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d483f-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d483f-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d483f-131">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="d483f-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d483f-132">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d483f-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d483f-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d483f-133">7/7/2012</span></span></p>
<p><span data-ttu-id="d483f-134">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d483f-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d483f-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d483f-135">7/3/2012</span></span></p>
<p><span data-ttu-id="d483f-136">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d483f-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-137"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-138">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="d483f-138">End date/time for the time range.</span></span> <span data-ttu-id="d483f-139">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d483f-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d483f-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d483f-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d483f-141">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="d483f-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d483f-142">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d483f-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d483f-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d483f-143">7/7/2012</span></span></p>
<p><span data-ttu-id="d483f-144">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d483f-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d483f-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d483f-145">7/3/2012</span></span></p>
<p><span data-ttu-id="d483f-146">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d483f-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-148">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="d483f-148">Time interval.</span></span> <span data-ttu-id="d483f-149">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-150">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="d483f-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d483f-151">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="d483f-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d483f-152">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="d483f-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d483f-153">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="d483f-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d483f-154">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="d483f-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d483f-155">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="d483f-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-156"><strong>媒體類型</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-157">指出會話中使用的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="d483f-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="d483f-158">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-159">同時</span><span class="sxs-lookup"><span data-stu-id="d483f-159">Both</span></span></p></li>
<li><p><span data-ttu-id="d483f-160">音訊</span><span class="sxs-lookup"><span data-stu-id="d483f-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="d483f-161">顯示器</span><span class="sxs-lookup"><span data-stu-id="d483f-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-162"><strong>通話處置</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-163">表示會話的成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="d483f-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="d483f-164">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-165">同時</span><span class="sxs-lookup"><span data-stu-id="d483f-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="d483f-166">成功通話</span><span class="sxs-lookup"><span data-stu-id="d483f-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="d483f-167">失敗的通話</span><span class="sxs-lookup"><span data-stu-id="d483f-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-168"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-169">指出要在報表中使用的值。</span><span class="sxs-lookup"><span data-stu-id="d483f-169">Indicates the values to be used in the report.</span></span> <span data-ttu-id="d483f-170">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-170">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-171">會話計數</span><span class="sxs-lookup"><span data-stu-id="d483f-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="d483f-172">通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="d483f-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="d483f-173">依泳池進行對等語音及影片活動的度量單位</span><span class="sxs-lookup"><span data-stu-id="d483f-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="d483f-174">下表列出每個池的對等語音及視頻報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d483f-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="d483f-175">依泳池進行對等語音及影片活動的度量單位</span><span class="sxs-lookup"><span data-stu-id="d483f-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d483f-176">名稱</span><span class="sxs-lookup"><span data-stu-id="d483f-176">Name</span></span></th>
<th><span data-ttu-id="d483f-177">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d483f-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d483f-178">說明</span><span class="sxs-lookup"><span data-stu-id="d483f-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d483f-179"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-180">否</span><span class="sxs-lookup"><span data-stu-id="d483f-180">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-181">用於通話的註冊機構池或邊緣伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d483f-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-183">否</span><span class="sxs-lookup"><span data-stu-id="d483f-183">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-184">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="d483f-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-185"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-186">否</span><span class="sxs-lookup"><span data-stu-id="d483f-186">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-187">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="d483f-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="d483f-188">對等語音及影片活動（依呼叫類型）的度量單位</span><span class="sxs-lookup"><span data-stu-id="d483f-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="d483f-189">下表列出針對每種通話類型進行對等語音及視頻報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d483f-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="d483f-190">對等語音及影片活動（依呼叫類型）的度量單位</span><span class="sxs-lookup"><span data-stu-id="d483f-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d483f-191">名稱</span><span class="sxs-lookup"><span data-stu-id="d483f-191">Name</span></span></th>
<th><span data-ttu-id="d483f-192">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d483f-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d483f-193">說明</span><span class="sxs-lookup"><span data-stu-id="d483f-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d483f-194"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-195">否</span><span class="sxs-lookup"><span data-stu-id="d483f-195">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-196">指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="d483f-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="d483f-197">[值] 是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-198">UC 對 UC</span><span class="sxs-lookup"><span data-stu-id="d483f-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="d483f-199">UC 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="d483f-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="d483f-200">PSTN 到 UC</span><span class="sxs-lookup"><span data-stu-id="d483f-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="d483f-201">PSTN 到 PSTN</span><span class="sxs-lookup"><span data-stu-id="d483f-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-202"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-203">否</span><span class="sxs-lookup"><span data-stu-id="d483f-203">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-204">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="d483f-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-205"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-206">否</span><span class="sxs-lookup"><span data-stu-id="d483f-206">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-207">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="d483f-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="d483f-208">依存取類型的對等語音及影片活動指標</span><span class="sxs-lookup"><span data-stu-id="d483f-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="d483f-209">下表列出針對每種網路存取類型的對等語音及視頻報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d483f-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="d483f-210">依存取類型的對等語音及影片活動指標</span><span class="sxs-lookup"><span data-stu-id="d483f-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d483f-211">名稱</span><span class="sxs-lookup"><span data-stu-id="d483f-211">Name</span></span></th>
<th><span data-ttu-id="d483f-212">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d483f-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d483f-213">說明</span><span class="sxs-lookup"><span data-stu-id="d483f-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d483f-214"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-215">否</span><span class="sxs-lookup"><span data-stu-id="d483f-215">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-216">指出在撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="d483f-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="d483f-217">值通常是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d483f-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d483f-218">內部</span><span class="sxs-lookup"><span data-stu-id="d483f-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="d483f-219">外來</span><span class="sxs-lookup"><span data-stu-id="d483f-219">External</span></span></p></li>
<li><p><span data-ttu-id="d483f-220">混淆</span><span class="sxs-lookup"><span data-stu-id="d483f-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-221"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-222">否</span><span class="sxs-lookup"><span data-stu-id="d483f-222">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-223">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="d483f-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-224"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-225">否</span><span class="sxs-lookup"><span data-stu-id="d483f-225">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-226">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="d483f-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="d483f-227">透過中繼伺服器進行對等語音及影片活動的度量標準</span><span class="sxs-lookup"><span data-stu-id="d483f-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="d483f-228">下表列出每個中繼伺服器的對等語音及視頻報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d483f-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="d483f-229">透過中繼伺服器進行對等語音及影片活動的度量標準</span><span class="sxs-lookup"><span data-stu-id="d483f-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d483f-230">名稱</span><span class="sxs-lookup"><span data-stu-id="d483f-230">Name</span></span></th>
<th><span data-ttu-id="d483f-231">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d483f-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d483f-232">說明</span><span class="sxs-lookup"><span data-stu-id="d483f-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d483f-233"><strong>中繼伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-234">否</span><span class="sxs-lookup"><span data-stu-id="d483f-234">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-235">中繼伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d483f-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d483f-236"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-237">否</span><span class="sxs-lookup"><span data-stu-id="d483f-237">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-238">通話發生的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="d483f-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d483f-239"><strong>總額</strong></span><span class="sxs-lookup"><span data-stu-id="d483f-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="d483f-240">否</span><span class="sxs-lookup"><span data-stu-id="d483f-240">No</span></span></p></td>
<td><p><span data-ttu-id="d483f-241">[會話總數] 或 [總郵件數]。</span><span class="sxs-lookup"><span data-stu-id="d483f-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

