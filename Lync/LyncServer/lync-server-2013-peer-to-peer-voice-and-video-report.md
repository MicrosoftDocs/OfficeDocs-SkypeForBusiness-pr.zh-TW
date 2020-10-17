---
title: Lync Server 2013：語音和影片報告 Peer-to-Peer
description: Lync Server 2013：語音和影片報告 Peer-to-Peer。
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
ms.openlocfilehash: 43041926b3d6b57508b6ee4c53ca9cb055bcb348
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557269"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="bc9ff-103">在 Lync Server 2013 中 Peer-to-Peer 語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="bc9ff-103">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc9ff-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="bc9ff-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="bc9ff-105">Peer-to-Peer 的語音和影片報告可提供一段 (時間內的語音和影片通話的詳細資訊，例如每小時或每天通話數) 。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-105">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="bc9ff-106">該報告也可讓您查看所進行的所有語音和影片通話，或只查看成功或失敗的通話。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-106">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="bc9ff-107">報告顯示通話資訊分為下列群組：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-107">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="bc9ff-108">每個集區的通話</span><span class="sxs-lookup"><span data-stu-id="bc9ff-108">Calls per pool</span></span>

  - <span data-ttu-id="bc9ff-109">每個通話類型的通話 (例如，Lync to Lync 通話和對 PSTN 網路上的人員進行 lync 通話) </span><span class="sxs-lookup"><span data-stu-id="bc9ff-109">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="bc9ff-110">每一種存取類型 (使用者登入內部網路和使用者登入外部網路時的呼叫) </span><span class="sxs-lookup"><span data-stu-id="bc9ff-110">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="bc9ff-111">每個轉送伺服器的通話</span><span class="sxs-lookup"><span data-stu-id="bc9ff-111">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="bc9ff-112">存取對等語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="bc9ff-112">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="bc9ff-113">您可以只開啟 Peer-to-Peer 活動摘要報告，然後按一下下列其中一個計量，即可存取 Peer-to-Peer 語音和影片報告：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-113">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="bc9ff-114">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-114">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="bc9ff-115">對等音訊分鐘總數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-115">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="bc9ff-116">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-116">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="bc9ff-117">對等影片總分鐘數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-117">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="bc9ff-118">若要充分利用對等語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="bc9ff-118">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="bc9ff-119">您可以使用多種方式來篩選 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-119">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="bc9ff-120">不過，根據預設，這些篩選選項會從視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-120">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="bc9ff-121">若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [ **顯示/隱藏參數** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-121">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bc9ff-122">篩選</span><span class="sxs-lookup"><span data-stu-id="bc9ff-122">Filters</span></span>

<span data-ttu-id="bc9ff-123">篩選為您提供一種方法，讓您可以傳回更精細的目標資料集，或以不同方式查看資料。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-123">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="bc9ff-124">下表列出您可以搭配 Peer-to-Peer 語音和影片報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-124">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="bc9ff-125">對等語音和影片報告篩選器</span><span class="sxs-lookup"><span data-stu-id="bc9ff-125">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9ff-126">名稱</span><span class="sxs-lookup"><span data-stu-id="bc9ff-126">Name</span></span></th>
<th><span data-ttu-id="bc9ff-127">描述</span><span class="sxs-lookup"><span data-stu-id="bc9ff-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-128"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-128"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-p104">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="bc9ff-131">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bc9ff-131">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bc9ff-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bc9ff-134">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bc9ff-134">7/7/2012</span></span></p>
<p><span data-ttu-id="bc9ff-135">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-135">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bc9ff-136">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bc9ff-136">7/3/2012</span></span></p>
<p><span data-ttu-id="bc9ff-137">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-137">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-138"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-138"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="bc9ff-141">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bc9ff-141">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bc9ff-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bc9ff-144">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="bc9ff-144">7/7/2012</span></span></p>
<p><span data-ttu-id="bc9ff-145">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-145">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bc9ff-146">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="bc9ff-146">7/3/2012</span></span></p>
<p><span data-ttu-id="bc9ff-147">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-147">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-148"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-148"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-151">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="bc9ff-151">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-152">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="bc9ff-152">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-153">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="bc9ff-153">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-154">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="bc9ff-154">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="bc9ff-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-157"><strong>媒體類型</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-157"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-158">會指出會話中所用的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-158">Indicates the type of media used in the session.</span></span> <span data-ttu-id="bc9ff-159">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-159">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-160">兩者都要</span><span class="sxs-lookup"><span data-stu-id="bc9ff-160">Both</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-161">音訊</span><span class="sxs-lookup"><span data-stu-id="bc9ff-161">Audio</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-162">影片</span><span class="sxs-lookup"><span data-stu-id="bc9ff-162">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-163"><strong>呼叫處置</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-163"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-164">表示會話成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-164">Indicates the success or failure of the session.</span></span> <span data-ttu-id="bc9ff-165">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-165">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-166">一切</span><span class="sxs-lookup"><span data-stu-id="bc9ff-166">[All]</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-167">成功通話</span><span class="sxs-lookup"><span data-stu-id="bc9ff-167">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-168">通話失敗</span><span class="sxs-lookup"><span data-stu-id="bc9ff-168">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-169"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-169"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-p112">指定報告中所要使用的值。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-172">工作階段計數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-172">Session count</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-173">通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="bc9ff-173">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="bc9ff-174">對等語音和影片活動的計量（依集區）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-174">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="bc9ff-175">下表列出每個集區 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-175">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="bc9ff-176">對等語音和影片活動的計量（依集區）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-176">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9ff-177">姓名</span><span class="sxs-lookup"><span data-stu-id="bc9ff-177">Name</span></span></th>
<th><span data-ttu-id="bc9ff-178">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bc9ff-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc9ff-179">描述</span><span class="sxs-lookup"><span data-stu-id="bc9ff-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-180"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-180"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-181">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-181">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-182">用於通話的註冊區集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-182">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-183"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-183"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-184">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-184">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-185">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-185">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-186"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-186"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-187">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-187">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-188">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-188">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="bc9ff-189">對等語音和影片活動的計量（依通話類型）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-189">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="bc9ff-190">下表列出每個所撥打的通話類型的 Peer-to-Peer 語音和影片報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-190">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="bc9ff-191">對等語音和影片活動的計量（依通話類型）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-191">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9ff-192">姓名</span><span class="sxs-lookup"><span data-stu-id="bc9ff-192">Name</span></span></th>
<th><span data-ttu-id="bc9ff-193">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bc9ff-193">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc9ff-194">描述</span><span class="sxs-lookup"><span data-stu-id="bc9ff-194">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-195"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-195"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-196">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-196">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-197">會指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-197">Indicates the type of call that was made.</span></span> <span data-ttu-id="bc9ff-198">值為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-198">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-199">UC 對 UC</span><span class="sxs-lookup"><span data-stu-id="bc9ff-199">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-200">UC 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="bc9ff-200">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-201">PSTN 對 UC</span><span class="sxs-lookup"><span data-stu-id="bc9ff-201">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-202">PSTN 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="bc9ff-202">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-203"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-203"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-204">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-204">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-205">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-205">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-206"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-206"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-207">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-207">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-208">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-208">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="bc9ff-209">對等語音和影片活動的計量（依存取類型）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-209">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="bc9ff-210">下表列出每個網路訪問類型的 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-210">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="bc9ff-211">對等語音和影片活動的計量（依存取類型）</span><span class="sxs-lookup"><span data-stu-id="bc9ff-211">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9ff-212">姓名</span><span class="sxs-lookup"><span data-stu-id="bc9ff-212">Name</span></span></th>
<th><span data-ttu-id="bc9ff-213">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bc9ff-213">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc9ff-214">描述</span><span class="sxs-lookup"><span data-stu-id="bc9ff-214">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-215"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-215"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-216">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-216">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-217">會指出撥打通話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-217">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="bc9ff-218">一般來說，值都是下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="bc9ff-218">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc9ff-219">內部</span><span class="sxs-lookup"><span data-stu-id="bc9ff-219">Internal</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-220">外部</span><span class="sxs-lookup"><span data-stu-id="bc9ff-220">External</span></span></p></li>
<li><p><span data-ttu-id="bc9ff-221">混合</span><span class="sxs-lookup"><span data-stu-id="bc9ff-221">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-222"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-222"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-223">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-223">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-224">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-224">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-225"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-225"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-226">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-226">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-227">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-227">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="bc9ff-228">依轉送伺服器的對等語音和影片活動計量</span><span class="sxs-lookup"><span data-stu-id="bc9ff-228">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="bc9ff-229">下表列出每個轉送伺服器的 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-229">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="bc9ff-230">依轉送伺服器的對等語音和影片活動計量</span><span class="sxs-lookup"><span data-stu-id="bc9ff-230">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc9ff-231">姓名</span><span class="sxs-lookup"><span data-stu-id="bc9ff-231">Name</span></span></th>
<th><span data-ttu-id="bc9ff-232">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bc9ff-232">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bc9ff-233">描述</span><span class="sxs-lookup"><span data-stu-id="bc9ff-233">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-234"><strong>中繼伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-234"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-235">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-235">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-236">轉送伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-236">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc9ff-237"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-237"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-238">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-238">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-239">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-239">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc9ff-240"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bc9ff-240"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bc9ff-241">否</span><span class="sxs-lookup"><span data-stu-id="bc9ff-241">No</span></span></p></td>
<td><p><span data-ttu-id="bc9ff-242">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bc9ff-242">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

