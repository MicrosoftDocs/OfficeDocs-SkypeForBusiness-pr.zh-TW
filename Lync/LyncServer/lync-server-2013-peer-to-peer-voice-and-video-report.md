---
title: Lync Server 2013： 對等語音和視訊報告
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
ms.openlocfilehash: 880104d0809b0135c74c72a80eefb7d4bb0ed709
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a><span data-ttu-id="bfe60-102">對等語音和視訊報告在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfe60-102">Peer-to-Peer Voice and Video Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfe60-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="bfe60-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="bfe60-104">對等語音和視訊報告提供詳細的外觀在一段指定的時間 （例如，每小時的通話） 或每日的電話語音和視訊通話的通訊。</span><span class="sxs-lookup"><span data-stu-id="bfe60-104">The Peer-to-Peer Voice and Video Report provides a detailed look at the distribution of voice and video calls over a specified period of time (for example, calls per hour or calls per day).</span></span> <span data-ttu-id="bfe60-105">報告也會提供您檢視所有語音和視訊通話進行，或都檢視僅成功或失敗通話的選項。</span><span class="sxs-lookup"><span data-stu-id="bfe60-105">The report also gives you the option of viewing all the voice and video calls that were made, or of viewing only the successful or failed calls.</span></span> <span data-ttu-id="bfe60-106">報告顯示通話的資訊分為下列群組：</span><span class="sxs-lookup"><span data-stu-id="bfe60-106">The reports shows call information broken down into the following groupings:</span></span>

  - <span data-ttu-id="bfe60-107">每個集區的通話</span><span class="sxs-lookup"><span data-stu-id="bfe60-107">Calls per pool</span></span>

  - <span data-ttu-id="bfe60-108">每一種通話類型 (例如，要撥打至 PSTN 網路內的人員的 Lync 電話與 Lync 通話 Lync) 的通話</span><span class="sxs-lookup"><span data-stu-id="bfe60-108">Calls per call type (for example, a Lync to Lync call vs. a Lync call to a person on the PSTN network)</span></span>

  - <span data-ttu-id="bfe60-109">每個存取類型 （內部網路與外部網路登入的使用者登入的使用者） 的通話</span><span class="sxs-lookup"><span data-stu-id="bfe60-109">Calls per access type (users logged on to the internal network vs. users logged on to the external network)</span></span>

  - <span data-ttu-id="bfe60-110">每個中繼伺服器的呼叫</span><span class="sxs-lookup"><span data-stu-id="bfe60-110">Calls per Mediation Server</span></span>

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="bfe60-111">若要存取對等語音和視訊報告</span><span class="sxs-lookup"><span data-stu-id="bfe60-111">To access the peer-to-peer voice and video report</span></span>

<span data-ttu-id="bfe60-112">您可以存取對等語音和視訊報告只能透過開啟對等活動摘要報告，然後按一下下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="bfe60-112">You can access the Peer-to-Peer Voice and Video Report only by opening the Peer-to-Peer Activity Summary Report and then clicking any of the following metrics:</span></span>

  - <span data-ttu-id="bfe60-113">對等音訊工作階段總數</span><span class="sxs-lookup"><span data-stu-id="bfe60-113">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="bfe60-114">對等音訊分鐘總數</span><span class="sxs-lookup"><span data-stu-id="bfe60-114">Total peer-to-peer audio minutes</span></span>

  - <span data-ttu-id="bfe60-115">對等視訊工作階段總數</span><span class="sxs-lookup"><span data-stu-id="bfe60-115">Total peer-to-peer video sessions</span></span>

  - <span data-ttu-id="bfe60-116">端對端視訊分鐘總數</span><span class="sxs-lookup"><span data-stu-id="bfe60-116">Total peer-to-peer video minutes</span></span>

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a><span data-ttu-id="bfe60-117">若要充分運用對等語音和視訊報告</span><span class="sxs-lookup"><span data-stu-id="bfe60-117">To make the best use of the peer-to-peer voice and video report</span></span>

<span data-ttu-id="bfe60-118">有多種方式對等語音和視訊報告，您可以篩選。</span><span class="sxs-lookup"><span data-stu-id="bfe60-118">There are a number of ways you can filter the Peer-to-Peer Voice and Video Report.</span></span> <span data-ttu-id="bfe60-119">不過，這些篩選選項預設為隱藏從檢視。</span><span class="sxs-lookup"><span data-stu-id="bfe60-119">However, those filtering options are hidden from view by default.</span></span> <span data-ttu-id="bfe60-120">若要檢視您可以使用的篩選選項，請按一下 [報表] 視窗右上角的 [**顯示/隱藏參數**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="bfe60-120">To view the filtering options available to you, click **Show/Hide Parameters** button in the upper-right corner of the Report window.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="bfe60-121">篩選</span><span class="sxs-lookup"><span data-stu-id="bfe60-121">Filters</span></span>

<span data-ttu-id="bfe60-122">篩選提供方法，讓您傳回更準確地目標的資料集，或以不同方式檢視資料。</span><span class="sxs-lookup"><span data-stu-id="bfe60-122">Filters provide a way for you to return a more finely targeted set of data or to view the data in different ways.</span></span> <span data-ttu-id="bfe60-123">下表列出您可以使用 「 對等語音和視訊報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="bfe60-123">The following table lists the filters that you can use with the Peer-to-Peer Voice and Video Report.</span></span>

### <a name="peer-to-peer-voice-and-video-report-filters"></a><span data-ttu-id="bfe60-124">對等語音和視訊報告篩選器</span><span class="sxs-lookup"><span data-stu-id="bfe60-124">Peer-to-peer voice and video report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfe60-125">名稱</span><span class="sxs-lookup"><span data-stu-id="bfe60-125">Name</span></span></th>
<th><span data-ttu-id="bfe60-126">描述</span><span class="sxs-lookup"><span data-stu-id="bfe60-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-p104">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="bfe60-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="bfe60-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bfe60-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bfe60-133">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="bfe60-133">7/7/2012</span></span></p>
<p><span data-ttu-id="bfe60-134">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bfe60-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bfe60-135">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="bfe60-135">7/3/2012</span></span></p>
<p><span data-ttu-id="bfe60-136">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bfe60-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="bfe60-140">7/7/2012 下午 1:00</span><span class="sxs-lookup"><span data-stu-id="bfe60-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="bfe60-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="bfe60-143">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="bfe60-143">7/7/2012</span></span></p>
<p><span data-ttu-id="bfe60-144">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="bfe60-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="bfe60-145">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="bfe60-145">7/3/2012</span></span></p>
<p><span data-ttu-id="bfe60-146">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="bfe60-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-150">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="bfe60-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bfe60-151">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="bfe60-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bfe60-152">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="bfe60-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="bfe60-153">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="bfe60-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="bfe60-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="bfe60-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-156"><strong>媒體類型</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-156"><strong>Media type</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-157">會指出媒體工作階段中所使用的類型。</span><span class="sxs-lookup"><span data-stu-id="bfe60-157">Indicates the type of media used in the session.</span></span> <span data-ttu-id="bfe60-158">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe60-158">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-159">兩者都要</span><span class="sxs-lookup"><span data-stu-id="bfe60-159">Both</span></span></p></li>
<li><p><span data-ttu-id="bfe60-160">音訊</span><span class="sxs-lookup"><span data-stu-id="bfe60-160">Audio</span></span></p></li>
<li><p><span data-ttu-id="bfe60-161">影片</span><span class="sxs-lookup"><span data-stu-id="bfe60-161">Video</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-162"><strong>通話處理</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-162"><strong>Call disposition</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-163">會指出成功或失敗的工作階段。</span><span class="sxs-lookup"><span data-stu-id="bfe60-163">Indicates the success or failure of the session.</span></span> <span data-ttu-id="bfe60-164">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe60-164">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-165">[全部]</span><span class="sxs-lookup"><span data-stu-id="bfe60-165">[All]</span></span></p></li>
<li><p><span data-ttu-id="bfe60-166">通話成功</span><span class="sxs-lookup"><span data-stu-id="bfe60-166">Success Calls</span></span></p></li>
<li><p><span data-ttu-id="bfe60-167">失敗的通話</span><span class="sxs-lookup"><span data-stu-id="bfe60-167">Failed Calls</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-168"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-168"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-p112">指定報告中所要使用的值。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe60-p112">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-171">工作階段計數</span><span class="sxs-lookup"><span data-stu-id="bfe60-171">Session count</span></span></p></li>
<li><p><span data-ttu-id="bfe60-172">通話分鐘數</span><span class="sxs-lookup"><span data-stu-id="bfe60-172">Call minutes</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="bfe60-173">對等語音及視訊活動的集區的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-173">Metrics for peer-to-peer voice and video activity by Pool</span></span>

<span data-ttu-id="bfe60-174">下表列出對等語音和視訊報告 」 中每個集區所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bfe60-174">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each pool.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a><span data-ttu-id="bfe60-175">對等語音及視訊活動的集區的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-175">Metrics for peer-to-peer voice and video activity by pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfe60-176">名稱</span><span class="sxs-lookup"><span data-stu-id="bfe60-176">Name</span></span></th>
<th><span data-ttu-id="bfe60-177">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bfe60-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bfe60-178">描述</span><span class="sxs-lookup"><span data-stu-id="bfe60-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-179"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-179"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-180">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-180">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-181">登錄器集區或 Edge Server 用於通話的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfe60-181">Name of the Registrar pool or Edge Server used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-183">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-183">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-184">在呼叫發生日期和時間期間。</span><span class="sxs-lookup"><span data-stu-id="bfe60-184">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-186">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-186">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-187">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bfe60-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="bfe60-188">對等語音及視訊活動依通話類型的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-188">Metrics for peer-to-peer voice and video activity by call type</span></span>

<span data-ttu-id="bfe60-189">下表列出對等語音和視訊報告 」 中每一種所進行之通話所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bfe60-189">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each type of call that was made.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a><span data-ttu-id="bfe60-190">對等語音及視訊活動依通話類型的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-190">Metrics for peer-to-peer voice and video activity by call type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfe60-191">名稱</span><span class="sxs-lookup"><span data-stu-id="bfe60-191">Name</span></span></th>
<th><span data-ttu-id="bfe60-192">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bfe60-192">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bfe60-193">描述</span><span class="sxs-lookup"><span data-stu-id="bfe60-193">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-194"><strong>通話類型</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-194"><strong>Call type</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-195">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-195">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-196">會指出所進行之通話的類型。</span><span class="sxs-lookup"><span data-stu-id="bfe60-196">Indicates the type of call that was made.</span></span> <span data-ttu-id="bfe60-197">值可以是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bfe60-197">Values are one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-198">UC 對 UC</span><span class="sxs-lookup"><span data-stu-id="bfe60-198">UC-to-UC</span></span></p></li>
<li><p><span data-ttu-id="bfe60-199">UC 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="bfe60-199">UC-to-PSTN</span></span></p></li>
<li><p><span data-ttu-id="bfe60-200">PSTN-UC</span><span class="sxs-lookup"><span data-stu-id="bfe60-200">PSTN-to-UC</span></span></p></li>
<li><p><span data-ttu-id="bfe60-201">PSTN 對 PSTN</span><span class="sxs-lookup"><span data-stu-id="bfe60-201">PSTN-to-PSTN</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-202"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-202"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-203">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-203">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-204">在呼叫發生日期和時間期間。</span><span class="sxs-lookup"><span data-stu-id="bfe60-204">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-205"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-205"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-206">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-206">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-207">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bfe60-207">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="bfe60-208">對等語音及視訊活動依存取類型的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-208">Metrics for peer-to-peer voice and video activity by access type</span></span>

<span data-ttu-id="bfe60-209">下表列出每個網路存取類型對等語音和視訊報告 」 中所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bfe60-209">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each network access type.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a><span data-ttu-id="bfe60-210">對等語音及視訊活動依存取類型的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-210">Metrics for peer-to-peer voice and video activity by access type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfe60-211">名稱</span><span class="sxs-lookup"><span data-stu-id="bfe60-211">Name</span></span></th>
<th><span data-ttu-id="bfe60-212">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bfe60-212">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bfe60-213">描述</span><span class="sxs-lookup"><span data-stu-id="bfe60-213">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-214"><strong>活動類型</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-214"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-215">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-215">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-216">會指出是否在用戶端已登入內部網路或外部網路時撥打電話。</span><span class="sxs-lookup"><span data-stu-id="bfe60-216">Indicates whether the clients were logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="bfe60-217">一般來說，值都是下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="bfe60-217">Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="bfe60-218">內部</span><span class="sxs-lookup"><span data-stu-id="bfe60-218">Internal</span></span></p></li>
<li><p><span data-ttu-id="bfe60-219">External</span><span class="sxs-lookup"><span data-stu-id="bfe60-219">External</span></span></p></li>
<li><p><span data-ttu-id="bfe60-220">混合</span><span class="sxs-lookup"><span data-stu-id="bfe60-220">Mixed</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-221"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-221"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-222">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-222">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-223">在呼叫發生日期和時間期間。</span><span class="sxs-lookup"><span data-stu-id="bfe60-223">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-224"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-224"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-225">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-225">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-226">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bfe60-226">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="bfe60-227">對等語音及視訊活動由中繼伺服器的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-227">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<span data-ttu-id="bfe60-228">下表列出對等語音和視訊報告 」 中每一部中繼伺服器所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="bfe60-228">The following table lists the information provided in the Peer-to-Peer Voice and Video Report for each Mediation Server.</span></span>

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a><span data-ttu-id="bfe60-229">對等語音及視訊活動由中繼伺服器的計量</span><span class="sxs-lookup"><span data-stu-id="bfe60-229">Metrics for peer-to-peer voice and video activity by mediation server</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bfe60-230">名稱</span><span class="sxs-lookup"><span data-stu-id="bfe60-230">Name</span></span></th>
<th><span data-ttu-id="bfe60-231">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="bfe60-231">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="bfe60-232">描述</span><span class="sxs-lookup"><span data-stu-id="bfe60-232">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-233"><strong>中繼伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-233"><strong>Mediation Server</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-234">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-234">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-235">中繼伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="bfe60-235">Name of the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bfe60-236"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-236"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-237">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-237">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-238">在呼叫發生日期和時間期間。</span><span class="sxs-lookup"><span data-stu-id="bfe60-238">Date and time period in which the call took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bfe60-239"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="bfe60-239"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="bfe60-240">否</span><span class="sxs-lookup"><span data-stu-id="bfe60-240">No</span></span></p></td>
<td><p><span data-ttu-id="bfe60-241">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="bfe60-241">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

