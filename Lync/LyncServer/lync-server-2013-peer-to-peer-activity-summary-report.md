---
title: Lync Server 2013： Peer-to-Peer 活動摘要報告
description: Lync Server 2013： Peer-to-Peer 活動摘要報告。
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
ms.openlocfilehash: 2f081f542a5063ed83be470d3e991c58e458b487
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557299"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="8b570-103">Lync Server 2013 中的 Peer-to-Peer 活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="8b570-103">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b570-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="8b570-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="8b570-105">Peer-to-Peer 活動摘要報告可提供對等通訊會話的整體觀點。</span><span class="sxs-lookup"><span data-stu-id="8b570-105">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="8b570-106">點對點工作階段通常只會包含兩位使用者，不需要使用 Lync Server 會議服務。</span><span class="sxs-lookup"><span data-stu-id="8b570-106">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="8b570-107">相比之下，會議通常包含兩個以上的使用者，且需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="8b570-107">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="8b570-108">會議活動會在會議摘要報告上報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-108">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="8b570-109">Peer-to-Peer 活動摘要報告可協助您回答如下問題：</span><span class="sxs-lookup"><span data-stu-id="8b570-109">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="8b570-110">我的使用者在一般的一天會傳送多少對等立即訊息？</span><span class="sxs-lookup"><span data-stu-id="8b570-110">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="8b570-111">是否有任何使用者真的利用 Lync Server 應用程式共用和檔案傳輸功能？</span><span class="sxs-lookup"><span data-stu-id="8b570-111">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="8b570-112">使用者抱怨，網路在一天中的特定時間似乎很慢。</span><span class="sxs-lookup"><span data-stu-id="8b570-112">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="8b570-113">對等音訊和影片在這些時段內專門占多少分鐘？</span><span class="sxs-lookup"><span data-stu-id="8b570-113">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="8b570-114">存取 Peer-to-Peer 活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="8b570-114">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="8b570-115">您可以從監控報告的首頁存取 Peer-to-Peer 活動摘要報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-115">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="8b570-116">您可以按一下下列其中一個計量， [以在 Lync Server 2013 中開啟 PEER-TO-PEER IM 報告](lync-server-2013-peer-to-peer-im-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="8b570-116">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="8b570-117">對等 IM 工作階段總數</span><span class="sxs-lookup"><span data-stu-id="8b570-117">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="8b570-118">對等 IM 訊息總數</span><span class="sxs-lookup"><span data-stu-id="8b570-118">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="8b570-119">同樣的，您也可以按一下下列其中一項度量，開啟 Peer-to-Peer 的語音和影片報告：</span><span class="sxs-lookup"><span data-stu-id="8b570-119">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="8b570-120">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="8b570-120">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="8b570-121">對等音訊會話分鐘總數</span><span class="sxs-lookup"><span data-stu-id="8b570-121">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="8b570-122">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="8b570-122">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="8b570-123">對等音訊會話分鐘總數</span><span class="sxs-lookup"><span data-stu-id="8b570-123">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="8b570-124">Peer-to-Peer 活動摘要報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="8b570-124">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="8b570-125">在 Peer-to-Peer 活動摘要報告的底部，您會找到計量（如對等 IM 會話總數和對等 IM 訊息總數）的總和。</span><span class="sxs-lookup"><span data-stu-id="8b570-125">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="8b570-126">這會提供報表內文中所發現詳細資訊的摘要。</span><span class="sxs-lookup"><span data-stu-id="8b570-126">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8b570-127">篩選</span><span class="sxs-lookup"><span data-stu-id="8b570-127">Filters</span></span>

<span data-ttu-id="8b570-128">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="8b570-128">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8b570-129">例如，Peer-to-Peer 活動摘要報表可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="8b570-129">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="8b570-130">在此情況下，活動會依小時、天、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="8b570-130">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="8b570-131">下表列出您可以搭配 Peer-to-Peer 活動摘要報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="8b570-131">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="8b570-132">活動摘要報表篩選 Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="8b570-132">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b570-133">名稱</span><span class="sxs-lookup"><span data-stu-id="8b570-133">Name</span></span></th>
<th><span data-ttu-id="8b570-134">描述</span><span class="sxs-lookup"><span data-stu-id="8b570-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b570-135"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-135"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-p106">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b570-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8b570-138">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b570-138">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b570-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="8b570-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b570-141">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8b570-141">7/17/12012</span></span></p>
<p><span data-ttu-id="8b570-142">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="8b570-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b570-143">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8b570-143">7/13/2012</span></span></p>
<p><span data-ttu-id="8b570-144">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="8b570-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-145"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-145"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-p108">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b570-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8b570-148">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="8b570-148">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="8b570-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="8b570-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8b570-151">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="8b570-151">7/17/12012</span></span></p>
<p><span data-ttu-id="8b570-152">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="8b570-152">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8b570-153">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="8b570-153">7/13/2012</span></span></p>
<p><span data-ttu-id="8b570-154">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="8b570-154">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-155"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-155"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-p110">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="8b570-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b570-158">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="8b570-158">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8b570-159">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="8b570-159">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8b570-160">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="8b570-160">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="8b570-161">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="8b570-161">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="8b570-162">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。</span><span class="sxs-lookup"><span data-stu-id="8b570-162">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="8b570-163">例如，如果您選取 [開始日期 7/17/12012] 和 [結束2/28/2012 日期] 的 [每日間隔]，將會顯示 8/7/12012 12:00 AM 到 9/7/12012 12:00 AM (的資料，也就是有31天的資料) 總計。</span><span class="sxs-lookup"><span data-stu-id="8b570-163">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8b570-164">指標</span><span class="sxs-lookup"><span data-stu-id="8b570-164">Metrics</span></span>

<span data-ttu-id="8b570-165">下表列出 Peer-to-Peer 活動摘要報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="8b570-165">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="8b570-166">活動摘要報表度量 Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="8b570-166">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b570-167">姓名</span><span class="sxs-lookup"><span data-stu-id="8b570-167">Name</span></span></th>
<th><span data-ttu-id="8b570-168">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="8b570-168">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8b570-169">描述</span><span class="sxs-lookup"><span data-stu-id="8b570-169">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b570-170"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-170"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="8b570-171"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-171"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="8b570-172"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-172"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="8b570-173"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-173"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-174">否</span><span class="sxs-lookup"><span data-stu-id="8b570-174">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-175">指出在篩選工具列上所選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="8b570-175">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="8b570-176">在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8b570-176">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="8b570-177">例如，如果您使用的是每日間隔，而您按一下 [7/17/12012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="8b570-177">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-178"><strong>點對點工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-178"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-179">否</span><span class="sxs-lookup"><span data-stu-id="8b570-179">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-180">進行中的點對點工作階段總數（不論會話類型為何）。</span><span class="sxs-lookup"><span data-stu-id="8b570-180">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-181"><strong>對等 IM 工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-181"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-182">否</span><span class="sxs-lookup"><span data-stu-id="8b570-182">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-183">對等立即訊息 (IM) 會話的總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-183">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="8b570-184">當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-184">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-185"><strong>對等 IM 訊息總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-185"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-186">否</span><span class="sxs-lookup"><span data-stu-id="8b570-186">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-187">在點對點工作階段中傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-187">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="8b570-188">當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-188">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-189"><strong>對等音訊會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-189"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-190">否</span><span class="sxs-lookup"><span data-stu-id="8b570-190">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-191">對等音訊通話總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-191">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="8b570-192">當您按一下此欄位時，報表會顯示所選時段的 Peer-to-Peer 語音及影片報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-192">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-193"><strong>對等音訊會話分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-193"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-194">否</span><span class="sxs-lookup"><span data-stu-id="8b570-194">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-195">對等音訊會話所用的總時間量。</span><span class="sxs-lookup"><span data-stu-id="8b570-195">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="8b570-196">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-196">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-197"><strong>平均對等音訊會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-197"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-198">否</span><span class="sxs-lookup"><span data-stu-id="8b570-198">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-199">對等音訊會話所用的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="8b570-199">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="8b570-200">由音訊會話總數除以音訊會話總數所計算。</span><span class="sxs-lookup"><span data-stu-id="8b570-200">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-201"><strong>對等音訊會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-201"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-202">否</span><span class="sxs-lookup"><span data-stu-id="8b570-202">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-203">對等視頻通話總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-203">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="8b570-204">請注意，影片也會算作音訊會話：每個影片都會計算為一個影片會話和一個音訊會話。</span><span class="sxs-lookup"><span data-stu-id="8b570-204">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="8b570-205">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-205">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-206"><strong>對等視頻會話分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-206"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-207">否</span><span class="sxs-lookup"><span data-stu-id="8b570-207">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-208">對等視頻會話所用的總時間。</span><span class="sxs-lookup"><span data-stu-id="8b570-208">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="8b570-209">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="8b570-209">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-210"><strong>平均對等視頻會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-210"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-211">否</span><span class="sxs-lookup"><span data-stu-id="8b570-211">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-212">對等視頻會話所用的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="8b570-212">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="8b570-213">透過影片總數除以影片總數來計算。</span><span class="sxs-lookup"><span data-stu-id="8b570-213">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b570-214"><strong>對等檔案傳輸會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-214"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-215">否</span><span class="sxs-lookup"><span data-stu-id="8b570-215">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-216">包含檔案傳輸的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-216">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b570-217"><strong>對等應用程式共用會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="8b570-217"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="8b570-218">否</span><span class="sxs-lookup"><span data-stu-id="8b570-218">No</span></span></p></td>
<td><p><span data-ttu-id="8b570-219">包含應用程式共用的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="8b570-219">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

