---
title: Lync Server 2013：對等活動摘要報告
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
ms.openlocfilehash: d55c3d84fe48158490473c31e9782dc63e298310
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a><span data-ttu-id="d7017-102">Lync Server 2013 中的對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="d7017-102">Peer-to-Peer Activity Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7017-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="d7017-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="d7017-104">對等活動摘要報告可提供對等通訊會話的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="d7017-104">The Peer-to-Peer Activity Summary Report provides an overall view of your peer-to-peer communication sessions.</span></span> <span data-ttu-id="d7017-105">點對點工作階段通常只涉及兩個使用者，不需要使用 Lync Server 會議服務。</span><span class="sxs-lookup"><span data-stu-id="d7017-105">A peer-to-peer session typically involves just two users, and does not require the use of the Lync Server conferencing services.</span></span> <span data-ttu-id="d7017-106">依比較，會議通常會涉及超過兩個使用者，且需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="d7017-106">By comparison, a conference typically involves more than two users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="d7017-107">會議活動會報告在會議摘要報告上。</span><span class="sxs-lookup"><span data-stu-id="d7017-107">Conference activity is reported on the Conference Summary Report.</span></span>

<span data-ttu-id="d7017-108">對等活動摘要報告可協助您回答如下所示的問題：</span><span class="sxs-lookup"><span data-stu-id="d7017-108">The Peer-to-Peer Activity Summary Report helps you answer questions like the following:</span></span>

  - <span data-ttu-id="d7017-109">我的使用者在一般日期傳送多少對等立即訊息？</span><span class="sxs-lookup"><span data-stu-id="d7017-109">How many peer-to-peer instant messages do my users send on a typical day?</span></span>

  - <span data-ttu-id="d7017-110">我是否有任何使用者確實充分利用 Lync Server 應用程式的共用和檔案傳輸功能？</span><span class="sxs-lookup"><span data-stu-id="d7017-110">Are any of my users actually taking advantage of the Lync Server application sharing and file transfer capabilities?</span></span>

  - <span data-ttu-id="d7017-111">使用者抱怨，網路在一天的特定時間看起來很慢。</span><span class="sxs-lookup"><span data-stu-id="d7017-111">Users have been complaining that the network seems slow at certain times of the day.</span></span> <span data-ttu-id="d7017-112">在這些時段內，專門針對對等音訊和影片會議所用的分鐘數為何？</span><span class="sxs-lookup"><span data-stu-id="d7017-112">How many minutes are devoted to peer-to-peer audio and video sessions during those time periods?</span></span>

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d7017-113">存取對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="d7017-113">Accessing the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d7017-114">您可以從 [監控報告] 首頁存取對等活動摘要報告。</span><span class="sxs-lookup"><span data-stu-id="d7017-114">You access the Peer-to-Peer Activity Summary Report from the Monitoring Reports home page.</span></span> <span data-ttu-id="d7017-115">在 Lync Server 2013 中，按一下下列其中一個度量，即可開啟[對等 IM 報告](lync-server-2013-peer-to-peer-im-report.md)：</span><span class="sxs-lookup"><span data-stu-id="d7017-115">You open the [Peer-to-Peer IM Report in Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d7017-116">對等 IM 會話總數</span><span class="sxs-lookup"><span data-stu-id="d7017-116">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="d7017-117">對等 IM 訊息總計</span><span class="sxs-lookup"><span data-stu-id="d7017-117">Total peer-to-peer IM messages</span></span>

<span data-ttu-id="d7017-118">同樣地，您也可以按一下下列任何一個度量來開啟對等語音及視頻報告：</span><span class="sxs-lookup"><span data-stu-id="d7017-118">Likewise, you can open the Peer-to-Peer Voice and Video Report by clicking any of these metrics:</span></span>

  - <span data-ttu-id="d7017-119">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="d7017-119">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d7017-120">對等音訊會話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="d7017-120">Total peer-to-peer audio session minutes</span></span>

  - <span data-ttu-id="d7017-121">對等音訊會話總數</span><span class="sxs-lookup"><span data-stu-id="d7017-121">Total peer-to-peer audio sessions</span></span>

  - <span data-ttu-id="d7017-122">對等音訊會話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="d7017-122">Total peer-to-peer audio session minutes</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a><span data-ttu-id="d7017-123">充分運用對等活動摘要報告</span><span class="sxs-lookup"><span data-stu-id="d7017-123">Making the Best Use of the Peer-to-Peer Activity Summary Report</span></span>

<span data-ttu-id="d7017-124">在對等活動摘要報告的底部，您會發現指標（例如對等與對等 IM 會話以及對等與對等 IM 訊息總計）的合計。</span><span class="sxs-lookup"><span data-stu-id="d7017-124">At the bottom of the Peer-to-Peer Activity Summary Report you'll find totals for metrics such as Total peer-to-peer IM sessions and Total peer-to-peer IM messages.</span></span> <span data-ttu-id="d7017-125">這可讓您快速摘要顯示在報表本文中找到的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d7017-125">This provides a quick summary of the detailed information found in the body of the report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d7017-126">濾鏡</span><span class="sxs-lookup"><span data-stu-id="d7017-126">Filters</span></span>

<span data-ttu-id="d7017-127">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="d7017-127">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d7017-128">例如，對等活動摘要報告可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="d7017-128">For example, the Peer-to-Peer Activity Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="d7017-129">在這種情況下，活動會依小時、日、周或月分組。</span><span class="sxs-lookup"><span data-stu-id="d7017-129">In this case, activity grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d7017-130">下表列出您可以搭配對等活動摘要報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="d7017-130">The following table lists the filters that you can use with the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-filters"></a><span data-ttu-id="d7017-131">對等活動摘要報表篩選</span><span class="sxs-lookup"><span data-stu-id="d7017-131">Peer-to-Peer Activity Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7017-132">名稱</span><span class="sxs-lookup"><span data-stu-id="d7017-132">Name</span></span></th>
<th><span data-ttu-id="d7017-133">說明</span><span class="sxs-lookup"><span data-stu-id="d7017-133">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7017-134"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-134"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-135">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d7017-135">Start date and time for the time range.</span></span> <span data-ttu-id="d7017-136">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7017-136">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d7017-137">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d7017-137">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d7017-138">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="d7017-138">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d7017-139">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d7017-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d7017-140">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d7017-140">7/17/12012</span></span></p>
<p><span data-ttu-id="d7017-141">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d7017-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d7017-142">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d7017-142">7/13/2012</span></span></p>
<p><span data-ttu-id="d7017-143">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d7017-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-144"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-144"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-145">時間範圍的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="d7017-145">End date and time for the time range.</span></span> <span data-ttu-id="d7017-146">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d7017-146">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d7017-147">7/17/12012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d7017-147">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="d7017-148">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="d7017-148">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d7017-149">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d7017-149">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d7017-150">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="d7017-150">7/17/12012</span></span></p>
<p><span data-ttu-id="d7017-151">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d7017-151">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d7017-152">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="d7017-152">7/13/2012</span></span></p>
<p><span data-ttu-id="d7017-153">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d7017-153">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-154"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-154"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-155">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="d7017-155">Time interval.</span></span> <span data-ttu-id="d7017-156">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d7017-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d7017-157">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="d7017-157">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d7017-158">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="d7017-158">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d7017-159">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="d7017-159">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d7017-160">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="d7017-160">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d7017-161">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="d7017-161">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d7017-162">例如，如果您選取 [開始日期 7/17/12012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/12012 12:00 AM 至 9/7/12012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="d7017-162">For example, if you select the Daily interval with a start date of 7/17/12012 and an end date of 2/28/2012, data is displayed for the days 8/7/12012 12:00 AM to 9/7/12012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d7017-163">指標</span><span class="sxs-lookup"><span data-stu-id="d7017-163">Metrics</span></span>

<span data-ttu-id="d7017-164">下表列出對等活動摘要報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d7017-164">The following table lists the information provided in the Peer-to-Peer Activity Summary Report.</span></span>

### <a name="peer-to-peer-activity-summary-report-metrics"></a><span data-ttu-id="d7017-165">對等活動摘要報表度量單位</span><span class="sxs-lookup"><span data-stu-id="d7017-165">Peer-to-Peer Activity Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7017-166">名稱</span><span class="sxs-lookup"><span data-stu-id="d7017-166">Name</span></span></th>
<th><span data-ttu-id="d7017-167">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d7017-167">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d7017-168">說明</span><span class="sxs-lookup"><span data-stu-id="d7017-168">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7017-169"><strong>工資</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-169"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="d7017-170"><strong>日常</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-170"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="d7017-171"><strong>周更新</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-171"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="d7017-172"><strong>次</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-172"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-173">否</span><span class="sxs-lookup"><span data-stu-id="d7017-173">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-174">指出您在 [篩選] 工具列上選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="d7017-174">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="d7017-175">在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d7017-175">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="d7017-176">例如，如果您使用的是每日間隔，而您按一下 [7/17/12012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="d7017-176">For example, if you are using the Daily interval and you click 7/17/12012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-177"><strong>點對點工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-177"><strong>Total peer-to-peer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-178">否</span><span class="sxs-lookup"><span data-stu-id="d7017-178">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-179">所進行的點對點工作階段總數（無論會話類型為何）。</span><span class="sxs-lookup"><span data-stu-id="d7017-179">Total number of peer-to-peer sessions conducted, regardless of session type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-180"><strong>對等 IM 會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-180"><strong>Total peer-to-peer IM sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-181">否</span><span class="sxs-lookup"><span data-stu-id="d7017-181">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-182">對等立即訊息（IM）會話的總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-182">Total number of peer-to-peer instant messaging (IM) sessions.</span></span> <span data-ttu-id="d7017-183">當您按一下此專案時，報告會顯示所選時段的對等 IM 報表。</span><span class="sxs-lookup"><span data-stu-id="d7017-183">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-184"><strong>對等 IM 訊息總計</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-184"><strong>Total peer-to-peer IM messages</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-185">否</span><span class="sxs-lookup"><span data-stu-id="d7017-185">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-186">在點對點工作階段中傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-186">Total number of instant messages sent in peer-to-peer sessions.</span></span> <span data-ttu-id="d7017-187">當您按一下此專案時，報告會顯示所選時段的對等 IM 報表。</span><span class="sxs-lookup"><span data-stu-id="d7017-187">When you click this item, the report shows you the Peer-to-Peer IM Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-188"><strong>對等音訊會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-188"><strong>Total peer-to-peer audio sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-189">否</span><span class="sxs-lookup"><span data-stu-id="d7017-189">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-190">對等音訊通話的總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-190">Total number of peer-to-peer audio calls.</span></span> <span data-ttu-id="d7017-191">當您按一下這個欄位時，報告會顯示所選時間範圍內的對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="d7017-191">When you click this field, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-192"><strong>對等音訊會話總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-192"><strong>Total peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-193">否</span><span class="sxs-lookup"><span data-stu-id="d7017-193">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-194">對等音訊會話所花費的總時間量。</span><span class="sxs-lookup"><span data-stu-id="d7017-194">Total amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="d7017-195">當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="d7017-195">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-196"><strong>平均對等音訊會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-196"><strong>Average peer-to-peer audio session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-197">否</span><span class="sxs-lookup"><span data-stu-id="d7017-197">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-198">對等音訊會話所花費的平均時間長度。</span><span class="sxs-lookup"><span data-stu-id="d7017-198">Average amount of time spent in peer-to-peer audio sessions.</span></span> <span data-ttu-id="d7017-199">將音訊會話總時間除以音訊會話總數來計算。</span><span class="sxs-lookup"><span data-stu-id="d7017-199">Calculated by dividing the total audio session time by the total number of audio sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-200"><strong>對等影片會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-200"><strong>Total peer-to-peer video sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-201">否</span><span class="sxs-lookup"><span data-stu-id="d7017-201">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-202">對等視頻通話的總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-202">Total number of peer-to-peer video calls.</span></span> <span data-ttu-id="d7017-203">請注意，視頻會話也會計算為音訊會話：每個視頻會話都會計算為一個影片會話和一個音訊會話。</span><span class="sxs-lookup"><span data-stu-id="d7017-203">Note that video sessions are also counted as audio sessions: each video session is counted as one video session and one audio session.</span></span> <span data-ttu-id="d7017-204">當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="d7017-204">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-205"><strong>對等影片會話總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-205"><strong>Total peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-206">否</span><span class="sxs-lookup"><span data-stu-id="d7017-206">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-207">對等視頻會話所花費的總時間量。</span><span class="sxs-lookup"><span data-stu-id="d7017-207">Total amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="d7017-208">當您按一下此專案時，報告會顯示所選時段內的對等語音及視頻報告。</span><span class="sxs-lookup"><span data-stu-id="d7017-208">When you click this item, the report shows you the Peer-to-Peer Voice and Video Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-209"><strong>平均對等影片會話分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-209"><strong>Average peer-to-peer video session minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-210">否</span><span class="sxs-lookup"><span data-stu-id="d7017-210">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-211">對等視頻會話所花費的平均時間長度。</span><span class="sxs-lookup"><span data-stu-id="d7017-211">Average amount of time spent in peer-to-peer video sessions.</span></span> <span data-ttu-id="d7017-212">透過將影片總時間除以視頻會話總數來計算。</span><span class="sxs-lookup"><span data-stu-id="d7017-212">Calculated by dividing the total video session time by the total number of video sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7017-213"><strong>對等檔案傳輸會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-213"><strong>Total peer-to-peer file transfer sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-214">否</span><span class="sxs-lookup"><span data-stu-id="d7017-214">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-215">包含檔案傳輸的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-215">Total number of peer-to-peer sessions that included file transfers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7017-216"><strong>對等應用程式共用會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="d7017-216"><strong>Total peer-to-peer application sharing sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="d7017-217">否</span><span class="sxs-lookup"><span data-stu-id="d7017-217">No</span></span></p></td>
<td><p><span data-ttu-id="d7017-218">包含應用程式共用的點對點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="d7017-218">Total number of peer-to-peer sessions that included application sharing.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

