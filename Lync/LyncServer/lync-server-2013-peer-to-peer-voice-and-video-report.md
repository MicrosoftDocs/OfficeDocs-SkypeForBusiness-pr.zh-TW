---
title: Lync Server 2013：語音和影片報告 Peer-to-Peer
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
ms.openlocfilehash: dc5d3905df971cf5ce09bfb026acc4838974ff18
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536800"
---
# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="ea3fe-102">在 Lync Server 2013 中 Peer-to-Peer 語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="ea3fe-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea3fe-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="ea3fe-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="ea3fe-104">Peer-to-Peer 的語音和影片報告可提供一段 (時間內的語音和影片通話的詳細資訊，例如每小時或每天通話數) 。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="ea3fe-105">該報告也可讓您查看所進行的所有語音和影片通話，或只查看成功或失敗的通話。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="ea3fe-106">報告顯示通話資訊分為下列群組：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="ea3fe-107">每個集區的通話</span><span class="sxs-lookup"><span data-stu-id="ea3fe-107">Calls per pool</span></span>

  - <span data-ttu-id="ea3fe-108">每個通話類型的通話 (例如，Lync to Lync 通話和對 PSTN 網路上的人員進行 lync 通話) </span><span class="sxs-lookup"><span data-stu-id="ea3fe-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="ea3fe-109">每一種存取類型 (使用者登入內部網路和使用者登入外部網路時的呼叫) </span><span class="sxs-lookup"><span data-stu-id="ea3fe-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="ea3fe-110">每個轉送伺服器的通話</span><span class="sxs-lookup"><span data-stu-id="ea3fe-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="ea3fe-111">存取對等語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="ea3fe-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="ea3fe-112">您可以只開啟 Peer-to-Peer 活動摘要報告，然後按一下下列其中一個計量，即可存取 Peer-to-Peer 語音和影片報告：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="ea3fe-113">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="ea3fe-114">對等音訊分鐘總數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="ea3fe-115">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="ea3fe-116">對等影片總分鐘數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="ea3fe-117">若要充分利用對等語音和影片報告</span><span class="sxs-lookup"><span data-stu-id="ea3fe-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="ea3fe-118">您可以使用多種方式來篩選 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="ea3fe-119">不過，根據預設，這些篩選選項會從視圖中隱藏。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="ea3fe-120">若要查看您可以使用的篩選選項，請按一下報表視窗右上角的 [ **顯示/隱藏參數** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ea3fe-121">篩選</span><span class="sxs-lookup"><span data-stu-id="ea3fe-121">Filters</span></span>

<span data-ttu-id="ea3fe-122">篩選為您提供一種方法，讓您可以傳回更精細的目標資料集，或以不同方式查看資料。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="ea3fe-123">下表列出您可以搭配 Peer-to-Peer 語音和影片報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="ea3fe-124">對等語音和影片報告篩選器</span><span class="sxs-lookup"><span data-stu-id="ea3fe-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3fe-125">名稱</span><span class="sxs-lookup"><span data-stu-id="ea3fe-125">Name</span></span></th>
<th><span data-ttu-id="ea3fe-126">描述</span><span class="sxs-lookup"><span data-stu-id="ea3fe-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-p104">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ea3fe-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ea3fe-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ea3fe-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ea3fe-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ea3fe-133">7/7/2012</span></span></p>
<p><span data-ttu-id="ea3fe-134">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ea3fe-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ea3fe-135">7/3/2012</span></span></p>
<p><span data-ttu-id="ea3fe-136">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ea3fe-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ea3fe-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ea3fe-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ea3fe-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ea3fe-143">7/7/2012</span></span></p>
<p><span data-ttu-id="ea3fe-144">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ea3fe-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ea3fe-145">7/3/2012</span></span></p>
<p><span data-ttu-id="ea3fe-146">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-150">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="ea3fe-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-151">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="ea3fe-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-152">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="ea3fe-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-153">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="ea3fe-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="ea3fe-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-156"><strong>媒體類型</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-157">會指出會話中所用的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="ea3fe-158">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-159">兩者都要</span><span class="sxs-lookup"><span data-stu-id="ea3fe-159">Both</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-160">音訊</span><span class="sxs-lookup"><span data-stu-id="ea3fe-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-161">影片</span><span class="sxs-lookup"><span data-stu-id="ea3fe-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-162"><strong>呼叫處置</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-163">表示會話成功或失敗。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="ea3fe-164">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-165">一切</span><span class="sxs-lookup"><span data-stu-id="ea3fe-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-166">成功通話</span><span class="sxs-lookup"><span data-stu-id="ea3fe-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-167">通話失敗</span><span class="sxs-lookup"><span data-stu-id="ea3fe-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-168"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-p112">指定報告中所要使用的值。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-171">工作階段計數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-172">通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="ea3fe-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="ea3fe-173">對等語音和影片活動的計量（依集區）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="ea3fe-174">下表列出每個集區 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="ea3fe-175">對等語音和影片活動的計量（依集區）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3fe-176">姓名</span><span class="sxs-lookup"><span data-stu-id="ea3fe-176">Name</span></span></th>
<th><span data-ttu-id="ea3fe-177">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="ea3fe-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ea3fe-178">描述</span><span class="sxs-lookup"><span data-stu-id="ea3fe-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-179"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-180">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-180">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-181">用於通話的註冊區集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-183">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-183">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-184">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-186">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-186">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-187">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="ea3fe-188">對等語音和影片活動的計量（依通話類型）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="ea3fe-189">下表列出每個所撥打的通話類型的 Peer-to-Peer 語音和影片報告中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="ea3fe-190">對等語音和影片活動的計量（依通話類型）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3fe-191">姓名</span><span class="sxs-lookup"><span data-stu-id="ea3fe-191">Name</span></span></th>
<th><span data-ttu-id="ea3fe-192">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="ea3fe-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ea3fe-193">描述</span><span class="sxs-lookup"><span data-stu-id="ea3fe-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-194"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-195">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-195">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-196">會指出所撥打的通話類型。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="ea3fe-197">值為下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-198">UC 對 UC</span><span class="sxs-lookup"><span data-stu-id="ea3fe-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-199">UC 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="ea3fe-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-200">PSTN 對 UC</span><span class="sxs-lookup"><span data-stu-id="ea3fe-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-201">PSTN 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="ea3fe-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-202"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-203">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-203">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-204">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-206">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-206">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-207">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="ea3fe-208">對等語音和影片活動的計量（依存取類型）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="ea3fe-209">下表列出每個網路訪問類型的 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="ea3fe-210">對等語音和影片活動的計量（依存取類型）</span><span class="sxs-lookup"><span data-stu-id="ea3fe-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3fe-211">姓名</span><span class="sxs-lookup"><span data-stu-id="ea3fe-211">Name</span></span></th>
<th><span data-ttu-id="ea3fe-212">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="ea3fe-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ea3fe-213">描述</span><span class="sxs-lookup"><span data-stu-id="ea3fe-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-214"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-215">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-215">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-216">會指出撥打通話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="ea3fe-217">一般來說，值都是下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="ea3fe-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ea3fe-218">內部</span><span class="sxs-lookup"><span data-stu-id="ea3fe-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-219">外部</span><span class="sxs-lookup"><span data-stu-id="ea3fe-219">External</span></span></p></li>
<li><p><span data-ttu-id="ea3fe-220">混合</span><span class="sxs-lookup"><span data-stu-id="ea3fe-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-221"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-222">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-222">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-223">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-225">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-225">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-226">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="ea3fe-227">依轉送伺服器的對等語音和影片活動計量</span><span class="sxs-lookup"><span data-stu-id="ea3fe-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="ea3fe-228">下表列出每個轉送伺服器的 Peer-to-Peer 語音和影片報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="ea3fe-229">依轉送伺服器的對等語音和影片活動計量</span><span class="sxs-lookup"><span data-stu-id="ea3fe-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ea3fe-230">姓名</span><span class="sxs-lookup"><span data-stu-id="ea3fe-230">Name</span></span></th>
<th><span data-ttu-id="ea3fe-231">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="ea3fe-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ea3fe-232">描述</span><span class="sxs-lookup"><span data-stu-id="ea3fe-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-233"><strong>中繼伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-234">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-234">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-235">轉送伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea3fe-236"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-237">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-237">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-238">進行通話的日期和時間週期。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea3fe-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="ea3fe-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="ea3fe-240">否</span><span class="sxs-lookup"><span data-stu-id="ea3fe-240">No</span></span></p></td>
<td><p><span data-ttu-id="ea3fe-241">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="ea3fe-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

