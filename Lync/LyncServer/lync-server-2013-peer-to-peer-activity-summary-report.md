---
title: Lync Server 2013： Peer-to-Peer 活動摘要報告
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
ms.openlocfilehash: e232d6ffee5e49d52eef68c9668d7d8b6325f13d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520800"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="91fe4-102">Lync Server 2013 中的 Peer-to-Peer 活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="91fe4-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91fe4-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="91fe4-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="91fe4-104">Peer-to-Peer 活動摘要報告可提供對等通訊會話的整體觀點。</span><span class="sxs-lookup"><span data-stu-id="91fe4-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="91fe4-105">點對點工作階段通常只會包含兩位使用者，不需要使用 Lync Server 會議服務。</span><span class="sxs-lookup"><span data-stu-id="91fe4-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="91fe4-106">相比之下，會議通常包含兩個以上的使用者，且需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="91fe4-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="91fe4-107">會議活動會在會議摘要報告上報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="91fe4-108">Peer-to-Peer 活動摘要報告可協助您回答如下問題：</span><span class="sxs-lookup"><span data-stu-id="91fe4-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="91fe4-109">我的使用者在一般的一天會傳送多少對等立即訊息？</span><span class="sxs-lookup"><span data-stu-id="91fe4-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="91fe4-110">是否有任何使用者真的利用 Lync Server 應用程式共用和檔案傳輸功能？</span><span class="sxs-lookup"><span data-stu-id="91fe4-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="91fe4-111">使用者抱怨，網路在一天中的特定時間似乎很慢。</span><span class="sxs-lookup"><span data-stu-id="91fe4-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="91fe4-112">對等音訊和影片在這些時段內專門占多少分鐘？</span><span class="sxs-lookup"><span data-stu-id="91fe4-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="91fe4-113">存取 Peer-to-Peer 活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="91fe4-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="91fe4-114">您可以從監控報告的首頁存取 Peer-to-Peer 活動摘要報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="91fe4-115">您可以按一下下列其中一個計量， [以在 Lync Server 2013 中開啟 PEER-TO-PEER IM 報告](lync-server-2013-peer-to-peer-im-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="91fe4-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="91fe4-116">對等 IM 工作階段總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="91fe4-117">對等 IM 訊息總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="91fe4-118">同樣的，您也可以按一下下列其中一項度量，開啟 Peer-to-Peer 的語音和影片報告：</span><span class="sxs-lookup"><span data-stu-id="91fe4-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="91fe4-119">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="91fe4-120">對等音訊會話分鐘總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="91fe4-121">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="91fe4-122">對等音訊會話分鐘總數</span><span class="sxs-lookup"><span data-stu-id="91fe4-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="91fe4-123">Peer-to-Peer 活動摘要報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="91fe4-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="91fe4-124">在 Peer-to-Peer 活動摘要報告的底部，您會找到計量（如對等 IM 會話總數和對等 IM 訊息總數）的總和。</span><span class="sxs-lookup"><span data-stu-id="91fe4-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="91fe4-125">這會提供報表內文中所發現詳細資訊的摘要。</span><span class="sxs-lookup"><span data-stu-id="91fe4-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="91fe4-126">篩選</span><span class="sxs-lookup"><span data-stu-id="91fe4-126">Filters</span></span>

<span data-ttu-id="91fe4-127">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="91fe4-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="91fe4-128">例如，Peer-to-Peer 活動摘要報表可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="91fe4-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="91fe4-129">在此情況下，活動會依小時、天、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="91fe4-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="91fe4-130">下表列出您可以搭配 Peer-to-Peer 活動摘要報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="91fe4-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="91fe4-131">活動摘要報表篩選 Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="91fe4-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91fe4-132">名稱</span><span class="sxs-lookup"><span data-stu-id="91fe4-132">Name</span></span></th>
<th><span data-ttu-id="91fe4-133">描述</span><span class="sxs-lookup"><span data-stu-id="91fe4-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-134"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-p106">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="91fe4-p106">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="91fe4-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="91fe4-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="91fe4-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="91fe4-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91fe4-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="91fe4-140">7/17/12012</span></span></p>
<p><span data-ttu-id="91fe4-141">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="91fe4-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91fe4-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="91fe4-142">7/13/2012</span></span></p>
<p><span data-ttu-id="91fe4-143">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="91fe4-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-144"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-p108">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="91fe4-p108">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="91fe4-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="91fe4-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="91fe4-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="91fe4-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="91fe4-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="91fe4-150">7/17/12012</span></span></p>
<p><span data-ttu-id="91fe4-151">若要按星期或月份查看，請輸入當週或該月您想查看的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="91fe4-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="91fe4-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="91fe4-152">7/13/2012</span></span></p>
<p><span data-ttu-id="91fe4-153">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="91fe4-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-154"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-p110">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="91fe4-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="91fe4-157">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="91fe4-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="91fe4-158">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="91fe4-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="91fe4-159">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="91fe4-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="91fe4-160">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="91fe4-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="91fe4-161">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。</span><span class="sxs-lookup"><span data-stu-id="91fe4-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="91fe4-162">例如，如果您選取 [開始日期 7/17/12012] 和 [結束2/28/2012 日期] 的 [每日間隔]，將會顯示 8/7/12012 12:00 AM 到 9/7/12012 12:00 AM (的資料，也就是有31天的資料) 總計。</span><span class="sxs-lookup"><span data-stu-id="91fe4-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="91fe4-163">指標</span><span class="sxs-lookup"><span data-stu-id="91fe4-163">Metrics</span></span>

<span data-ttu-id="91fe4-164">下表列出 Peer-to-Peer 活動摘要報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="91fe4-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="91fe4-165">活動摘要報表度量 Peer-to-Peer</span><span class="sxs-lookup"><span data-stu-id="91fe4-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="91fe4-166">姓名</span><span class="sxs-lookup"><span data-stu-id="91fe4-166">Name</span></span></th>
<th><span data-ttu-id="91fe4-167">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="91fe4-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="91fe4-168">描述</span><span class="sxs-lookup"><span data-stu-id="91fe4-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-169"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="91fe4-170"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="91fe4-171"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="91fe4-172"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-173">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-173">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-174">指出在篩選工具列上所選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="91fe4-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="91fe4-175">在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="91fe4-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="91fe4-176">例如，如果您使用的是每日間隔，而您按一下 [7/17/12012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="91fe4-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-177"><strong>點對點工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-178">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-178">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-179">進行中的點對點工作階段總數（不論會話類型為何）。</span><span class="sxs-lookup"><span data-stu-id="91fe4-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-180"><strong>對等 IM 工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-181">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-181">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-182">對等立即訊息 (IM) 會話的總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="91fe4-183">當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-184"><strong>對等 IM 訊息總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-185">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-185">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-186">在點對點工作階段中傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="91fe4-187">當您按一下此專案時，報表會顯示所選取時段的 Peer-to-Peer IM 報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-188"><strong>對等音訊會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-189">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-189">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-190">對等音訊通話總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="91fe4-191">當您按一下此欄位時，報表會顯示所選時段的 Peer-to-Peer 語音及影片報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-192"><strong>對等音訊會話分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-193">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-193">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-194">對等音訊會話所用的總時間量。</span><span class="sxs-lookup"><span data-stu-id="91fe4-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="91fe4-195">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-196"><strong>平均對等音訊會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-197">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-197">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-198">對等音訊會話所用的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="91fe4-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="91fe4-199">由音訊會話總數除以音訊會話總數所計算。</span><span class="sxs-lookup"><span data-stu-id="91fe4-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-200"><strong>對等音訊會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-201">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-201">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-202">對等視頻通話總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="91fe4-203">請注意，影片也會算作音訊會話：每個影片都會計算為一個影片會話和一個音訊會話。</span><span class="sxs-lookup"><span data-stu-id="91fe4-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="91fe4-204">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-205"><strong>對等視頻會話分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-206">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-206">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-207">對等視頻會話所用的總時間。</span><span class="sxs-lookup"><span data-stu-id="91fe4-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="91fe4-208">當您按一下此專案時，報告會顯示所選取時段的 Peer-to-Peer 語音和影片報告。</span><span class="sxs-lookup"><span data-stu-id="91fe4-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-209"><strong>平均對等視頻會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-210">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-210">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-211">對等視頻會話所用的平均時間量。</span><span class="sxs-lookup"><span data-stu-id="91fe4-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="91fe4-212">透過影片總數除以影片總數來計算。</span><span class="sxs-lookup"><span data-stu-id="91fe4-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="91fe4-213"><strong>對等檔案傳輸會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-214">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-214">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-215">包含檔案傳輸的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="91fe4-216"><strong>對等應用程式共用會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="91fe4-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="91fe4-217">否</span><span class="sxs-lookup"><span data-stu-id="91fe4-217">No</span></span></p></td>
<td><p><span data-ttu-id="91fe4-218">包含應用程式共用的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="91fe4-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

