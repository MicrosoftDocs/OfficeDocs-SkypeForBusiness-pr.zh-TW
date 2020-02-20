---
title: Lync Server 2013： 對等活動摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03a3015f24bae2595ac845c351c32ccb5d36c5f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="c4638-102">Lync Server 2013 中的對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="c4638-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4638-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="c4638-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="c4638-104">對等活動摘要報告提供您對等通訊工作階段的整體] 檢視。</span><span class="sxs-lookup"><span data-stu-id="c4638-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="c4638-105">端對端工作階段通常涉及僅由兩個使用者，且不需要使用 Lync Server 會議服務。</span><span class="sxs-lookup"><span data-stu-id="c4638-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="c4638-106">相較之下，會議通常包括兩個以上的使用者，以及需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="c4638-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="c4638-107">會議活動報告在 Conference Summary Report。</span><span class="sxs-lookup"><span data-stu-id="c4638-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="c4638-108">對等活動摘要報告可協助您回答下列問題：</span><span class="sxs-lookup"><span data-stu-id="c4638-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="c4638-109">我的使用者傳送多少對等立即訊息平日？</span><span class="sxs-lookup"><span data-stu-id="c4638-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="c4638-110">是否有任何我的使用者實際運用的 Lync Server 應用程式共用和檔案傳輸功能？</span><span class="sxs-lookup"><span data-stu-id="c4638-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="c4638-111">使用者有抱怨，網路似乎速度很慢在特定一天的時間。</span><span class="sxs-lookup"><span data-stu-id="c4638-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="c4638-112">幾分鐘的時間是在專供端對端音訊和視訊工作階段期間的時段？</span><span class="sxs-lookup"><span data-stu-id="c4638-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="c4638-113">存取對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="c4638-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="c4638-114">您從監視報告首頁存取對等活動摘要報告。</span><span class="sxs-lookup"><span data-stu-id="c4638-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="c4638-115">您可以按一下下列計量之一，以開啟[Lync Server 2013 中的對等 IM 報告](lync-server-2013-peer-to-peer-im-report.md)：</span><span class="sxs-lookup"><span data-stu-id="c4638-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="c4638-116">對等 IM 工作階段總數</span><span class="sxs-lookup"><span data-stu-id="c4638-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="c4638-117">對等 IM 訊息總數</span><span class="sxs-lookup"><span data-stu-id="c4638-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="c4638-118">同樣地，您可以按一下下列其中一個指標開啟對等語音和視訊報告：</span><span class="sxs-lookup"><span data-stu-id="c4638-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="c4638-119">對等音訊工作階段總數</span><span class="sxs-lookup"><span data-stu-id="c4638-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c4638-120">對等音訊工作階段分鐘總數</span><span class="sxs-lookup"><span data-stu-id="c4638-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="c4638-121">對等音訊工作階段總數</span><span class="sxs-lookup"><span data-stu-id="c4638-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="c4638-122">對等音訊工作階段分鐘總數</span><span class="sxs-lookup"><span data-stu-id="c4638-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="c4638-123">對等活動摘要報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="c4638-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="c4638-124">底部的對等活動摘要報告中，您會發現總計的對等 IM 工作階段總數和對等 IM 訊息總數等量值。</span><span class="sxs-lookup"><span data-stu-id="c4638-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="c4638-125">這會提供報表的內文中找到的詳細資訊的快速摘要。</span><span class="sxs-lookup"><span data-stu-id="c4638-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c4638-126">篩選</span><span class="sxs-lookup"><span data-stu-id="c4638-126">Filters</span></span>

<span data-ttu-id="c4638-127">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="c4638-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c4638-128">例如，對等活動摘要報告可讓您選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="c4638-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="c4638-129">在此情況下，活動依據小時、 日、 週或月。</span><span class="sxs-lookup"><span data-stu-id="c4638-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="c4638-130">下表列出您可以使用對等活動摘要報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="c4638-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="c4638-131">對等活動摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="c4638-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4638-132">名稱</span><span class="sxs-lookup"><span data-stu-id="c4638-132">Name</span></span></th>
<th><span data-ttu-id="c4638-133">描述</span><span class="sxs-lookup"><span data-stu-id="c4638-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4638-134"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-p106">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4638-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c4638-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c4638-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4638-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="c4638-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4638-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c4638-140">7/17/12012</span></span></p>
<p><span data-ttu-id="c4638-141">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="c4638-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4638-142">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="c4638-142">7/13/2012</span></span></p>
<p><span data-ttu-id="c4638-143">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="c4638-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-144"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-p108">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c4638-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c4638-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c4638-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="c4638-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="c4638-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c4638-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="c4638-150">7/17/12012</span></span></p>
<p><span data-ttu-id="c4638-151">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="c4638-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c4638-152">2012/7/13</span><span class="sxs-lookup"><span data-stu-id="c4638-152">7/13/2012</span></span></p>
<p><span data-ttu-id="c4638-153">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="c4638-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-154"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-p110">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c4638-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c4638-157">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="c4638-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c4638-158">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="c4638-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c4638-159">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="c4638-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c4638-160">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="c4638-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c4638-161">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。</span><span class="sxs-lookup"><span data-stu-id="c4638-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="c4638-162">例如，如果您選取 [每日的間隔時間與開始日期是 7/17/12012 和結束日期的 2/28/2012年，資料會顯示天 8/7/12012 上午 12:00 到 9/7/12012 12:00 AM （也就是 31 天的資料總數）。</span><span class="sxs-lookup"><span data-stu-id="c4638-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c4638-163">計量</span><span class="sxs-lookup"><span data-stu-id="c4638-163">Metrics</span></span>

<span data-ttu-id="c4638-164">下表列出對等活動摘要報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c4638-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="c4638-165">對等活動摘要報告計量</span><span class="sxs-lookup"><span data-stu-id="c4638-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4638-166">名稱</span><span class="sxs-lookup"><span data-stu-id="c4638-166">Name</span></span></th>
<th><span data-ttu-id="c4638-167">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="c4638-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c4638-168">描述</span><span class="sxs-lookup"><span data-stu-id="c4638-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4638-169"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="c4638-170"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="c4638-171"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="c4638-172"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-173">否</span><span class="sxs-lookup"><span data-stu-id="c4638-173">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-174">指出在篩選工具列上所選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="c4638-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="c4638-175">在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c4638-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="c4638-176">例如，如果您正在使用的每日時間間隔，因此您按一下 [7/17/12012，您看到使用者註冊活動每小時分解該日期。</span><span class="sxs-lookup"><span data-stu-id="c4638-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-177"><strong>端對端工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-178">否</span><span class="sxs-lookup"><span data-stu-id="c4638-178">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-179">端對端工作階段總數，不論工作階段類型。</span><span class="sxs-lookup"><span data-stu-id="c4638-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-180"><strong>對等 IM 工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-181">否</span><span class="sxs-lookup"><span data-stu-id="c4638-181">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-182">對等立即訊息 (IM) 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="c4638-183">當您按一下此項目時，報告會顯示您對等 IM 報告針對選取的時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-184"><strong>對等 IM 訊息總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-185">否</span><span class="sxs-lookup"><span data-stu-id="c4638-185">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-186">傳送端對端工作階段中的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="c4638-187">當您按一下此項目時，報告會顯示您對等 IM 報告針對選取的時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-188"><strong>對等音訊工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-189">否</span><span class="sxs-lookup"><span data-stu-id="c4638-189">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-190">對等音訊通話總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="c4638-191">當您按一下此欄位中，報告會顯示 「 對等語音和視訊報告所選時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-192"><strong>對等音訊工作階段分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-193">否</span><span class="sxs-lookup"><span data-stu-id="c4638-193">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-194">對等音訊工作階段中所花費的時間總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="c4638-195">當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-196"><strong>平均對等音訊工作階段分鐘</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-197">否</span><span class="sxs-lookup"><span data-stu-id="c4638-197">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-198">對等音訊工作階段中所花費的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="c4638-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="c4638-199">計算除以總計音訊工作階段時間依音訊工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-200"><strong>對等視訊工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-201">否</span><span class="sxs-lookup"><span data-stu-id="c4638-201">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-202">端對端視訊通話總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="c4638-203">請注意視訊工作階段也視為音訊工作階段： 每個視訊工作階段視為一個視訊工作階段和一個音訊工作階段。</span><span class="sxs-lookup"><span data-stu-id="c4638-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="c4638-204">當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-205"><strong>對等視訊工作階段分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-206">否</span><span class="sxs-lookup"><span data-stu-id="c4638-206">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-207">對等視訊工作階段中所花費的時間總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="c4638-208">當您按一下此項目時，報告即顯示 「 對等語音和視訊報告所選時段。</span><span class="sxs-lookup"><span data-stu-id="c4638-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-209"><strong>平均對等視訊工作階段分鐘</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-210">否</span><span class="sxs-lookup"><span data-stu-id="c4638-210">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-211">對等視訊工作階段中所花費的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="c4638-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="c4638-212">計算除以總計視訊工作階段時間依視訊工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4638-213"><strong>總數的端對端檔案傳輸工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-214">否</span><span class="sxs-lookup"><span data-stu-id="c4638-214">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-215">包含檔案傳輸之對等工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4638-216"><strong>總端對端應用程式共用工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="c4638-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="c4638-217">否</span><span class="sxs-lookup"><span data-stu-id="c4638-217">No</span></span></p></td>
<td><p><span data-ttu-id="c4638-218">包含應用程式共用之對等工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="c4638-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

