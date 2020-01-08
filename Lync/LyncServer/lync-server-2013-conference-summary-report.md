---
title: Lync Server 2013：會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977254"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="4e35c-102">Lync Server 2013 中的 [會議摘要] 報告</span><span class="sxs-lookup"><span data-stu-id="4e35c-102">Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e35c-103">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="4e35c-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="4e35c-104">[會議摘要] 報告提供您的線上會議會話的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="4e35c-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="4e35c-105">會議通常會涉及超過2個使用者，且需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="4e35c-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="4e35c-106">相比之下，點對點工作階段通常只涉及2個使用者，不需要使用 Lync Server 的會議服務。</span><span class="sxs-lookup"><span data-stu-id="4e35c-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="4e35c-107">對等活動會報告在[Lync Server 2013 的對等活動摘要報告](lync-server-2013-peer-to-peer-activity-summary-report.md)上。</span><span class="sxs-lookup"><span data-stu-id="4e35c-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="4e35c-108">[會議摘要報告] 不僅告訴您在指定時間內所舉行的會議數量（每小時、每天、每週、每月），也會告知您參與這些會議的人員總數，以及唯一會議的總人數組織.</span><span class="sxs-lookup"><span data-stu-id="4e35c-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="4e35c-109">「唯一」召集人是指至少安排一個會議的人。</span><span class="sxs-lookup"><span data-stu-id="4e35c-109">A "unique” organizer is anyone who schedules at least one conference.</span></span> <span data-ttu-id="4e35c-110">例如，如果 Pilar 方排程一個會議，她將其計算為一個唯一的召集人。</span><span class="sxs-lookup"><span data-stu-id="4e35c-110">For example, if Pilar Ackerman schedules one conference she counts as one unique organizer.</span></span> <span data-ttu-id="4e35c-111">如果 Ken Myer 排程148會議給他，太多是一個唯一的召集人。</span><span class="sxs-lookup"><span data-stu-id="4e35c-111">If Ken Myer schedules 148 conferences he, too counts as one unique organizer.</span></span> <span data-ttu-id="4e35c-112">例如，下表顯示已排程8個會議，但只有三個唯一的召集人（Ken Myer、Pilar 方和 David Ahs）。</span><span class="sxs-lookup"><span data-stu-id="4e35c-112">For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e35c-113">會議召集人</span><span class="sxs-lookup"><span data-stu-id="4e35c-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="4e35c-114">會議日期</span><span class="sxs-lookup"><span data-stu-id="4e35c-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="4e35c-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="4e35c-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-121">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-125">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-129">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e35c-131">[會議摘要] 報告也會指出包括音訊和/或影片在內的會議數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="4e35c-132">存取會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="4e35c-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="4e35c-133">[會議摘要] 報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="4e35c-133">The Conference Summary Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="4e35c-134">您可以按一下下列其中一個度量來向下切入會議活動報告：</span><span class="sxs-lookup"><span data-stu-id="4e35c-134">You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="4e35c-135">會議總數</span><span class="sxs-lookup"><span data-stu-id="4e35c-135">Total conferences</span></span>

  - <span data-ttu-id="4e35c-136">參與者總數</span><span class="sxs-lookup"><span data-stu-id="4e35c-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="4e35c-137">充分利用會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="4e35c-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="4e35c-138">[會議摘要] 報告中所使用之大部分標準的總值，可以在報表底部找到;向下滾動以查看值，例如在指定的時段內所保留的會議總數，以及參與這些會議的人員總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-138">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences.</span></span> <span data-ttu-id="4e35c-139">在報表底部沒有匯總的一個度量單位是唯一的會議召集人總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-139">One metric that is not totaled at the bottom of the report is Total unique conference organizers.</span></span> <span data-ttu-id="4e35c-140">為什麼不呢？</span><span class="sxs-lookup"><span data-stu-id="4e35c-140">Why not?</span></span> <span data-ttu-id="4e35c-141">以下是其中一個原因。</span><span class="sxs-lookup"><span data-stu-id="4e35c-141">Here’s one reason.</span></span> <span data-ttu-id="4e35c-142">假設您要查看一個月的資料。</span><span class="sxs-lookup"><span data-stu-id="4e35c-142">Suppose you are looking at a month's worth of data.</span></span> <span data-ttu-id="4e35c-143">在第1天，您有34唯一的會議召集人;在第2天，您有27個唯一的會議召集人。</span><span class="sxs-lookup"><span data-stu-id="4e35c-143">On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers.</span></span> <span data-ttu-id="4e35c-144">這是否表示您有61唯一的會議召集人來執行這兩天？</span><span class="sxs-lookup"><span data-stu-id="4e35c-144">Does that mean you had 61 unique conference organizers for those two days?</span></span> <span data-ttu-id="4e35c-145">不一定。</span><span class="sxs-lookup"><span data-stu-id="4e35c-145">Not necessarily.</span></span> <span data-ttu-id="4e35c-146">畢竟，在第2天組織會議的所有27人，都可能是在第1天共同進行會議的34人員。</span><span class="sxs-lookup"><span data-stu-id="4e35c-146">After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1.</span></span> <span data-ttu-id="4e35c-147">例如，在這份簡單的報表中，請注意，在7/7/2012 和7/2/2012 上，Ken Myer 與 Pilar 方排程的會議：</span><span class="sxs-lookup"><span data-stu-id="4e35c-147">For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e35c-148">會議召集人</span><span class="sxs-lookup"><span data-stu-id="4e35c-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="4e35c-149">會議日期</span><span class="sxs-lookup"><span data-stu-id="4e35c-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="4e35c-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="4e35c-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-156">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-160">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="4e35c-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="4e35c-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-164">Pilar 方</span><span class="sxs-lookup"><span data-stu-id="4e35c-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="4e35c-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="4e35c-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4e35c-166">若要進一步瞭解組織會議的唯一使用者總數，請變更您的時間間隔;例如，依月份查看資料，而不是依日期查看。</span><span class="sxs-lookup"><span data-stu-id="4e35c-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="4e35c-167">濾鏡</span><span class="sxs-lookup"><span data-stu-id="4e35c-167">Filters</span></span>

<span data-ttu-id="4e35c-168">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="4e35c-168">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="4e35c-169">例如，[會議摘要] 報告可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="4e35c-169">For example, the Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="4e35c-170">在這種情況下，會議會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="4e35c-170">In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="4e35c-171">下表列出可與會議摘要報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="4e35c-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="4e35c-172">會議摘要報表篩選</span><span class="sxs-lookup"><span data-stu-id="4e35c-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e35c-173">名稱</span><span class="sxs-lookup"><span data-stu-id="4e35c-173">Name</span></span></th>
<th><span data-ttu-id="4e35c-174">描述</span><span class="sxs-lookup"><span data-stu-id="4e35c-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-175"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-176">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="4e35c-176">Start date/time for the time range.</span></span> <span data-ttu-id="4e35c-177">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e35c-177">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="4e35c-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4e35c-179">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="4e35c-179">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4e35c-180">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="4e35c-180">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4e35c-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4e35c-181">7/7/2012</span></span></p>
<p><span data-ttu-id="4e35c-182">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="4e35c-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4e35c-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4e35c-183">7/3/2012</span></span></p>
<p><span data-ttu-id="4e35c-184">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="4e35c-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-185"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-186">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="4e35c-186">End date/time for the time range.</span></span> <span data-ttu-id="4e35c-187">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e35c-187">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="4e35c-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="4e35c-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="4e35c-189">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="4e35c-189">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="4e35c-190">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="4e35c-190">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="4e35c-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="4e35c-191">7/7/2012</span></span></p>
<p><span data-ttu-id="4e35c-192">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="4e35c-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="4e35c-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="4e35c-193">7/3/2012</span></span></p>
<p><span data-ttu-id="4e35c-194">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="4e35c-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-195"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-196">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="4e35c-196">Time interval.</span></span> <span data-ttu-id="4e35c-197">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="4e35c-197">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4e35c-198">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="4e35c-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4e35c-199">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="4e35c-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4e35c-200">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="4e35c-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="4e35c-201">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="4e35c-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="4e35c-202">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數目，則只會顯示最大值數（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="4e35c-202">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed.</span></span> <span data-ttu-id="4e35c-203">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="4e35c-203">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="4e35c-204">指標</span><span class="sxs-lookup"><span data-stu-id="4e35c-204">Metrics</span></span>

<span data-ttu-id="4e35c-205">下表是會議摘要報告所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="4e35c-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="4e35c-206">會議摘要報表度量單位</span><span class="sxs-lookup"><span data-stu-id="4e35c-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e35c-207">名稱</span><span class="sxs-lookup"><span data-stu-id="4e35c-207">Name</span></span></th>
<th><span data-ttu-id="4e35c-208">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="4e35c-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="4e35c-209">描述</span><span class="sxs-lookup"><span data-stu-id="4e35c-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-210"><strong>工資</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="4e35c-211"><strong>日常</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="4e35c-212"><strong>周更新</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="4e35c-213"><strong>次</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-214">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-214">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-215">指出您在 [篩選] 工具列上選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="4e35c-215">Indicates the time interval that you selected on the filter toolbar.</span></span> <span data-ttu-id="4e35c-216">在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4e35c-216">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="4e35c-217">例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="4e35c-217">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-218"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-219">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-219">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-220">已保留的會議總數（無論會議類型為何）。</span><span class="sxs-lookup"><span data-stu-id="4e35c-220">Total number of conferences (regardless of conference type) that were held.</span></span> <span data-ttu-id="4e35c-221">當您按一下此專案時，報告會顯示所選時段的會議活動報告。</span><span class="sxs-lookup"><span data-stu-id="4e35c-221">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-222"><strong>參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-223">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-223">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-224">參與會議的人員總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-224">Total number of people who took part in the conferences.</span></span> <span data-ttu-id="4e35c-225">當您按一下此專案時，報告會顯示所選時段的會議活動報告。</span><span class="sxs-lookup"><span data-stu-id="4e35c-225">When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-226"><strong>每個會議的平均參與者</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-227">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-227">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-228">參與特定會議的平均人數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-228">Average number of people who took part in a given conference.</span></span> <span data-ttu-id="4e35c-229">由由總參與者數除會議數來決定。</span><span class="sxs-lookup"><span data-stu-id="4e35c-229">Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-230"><strong>A/V 會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-231">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-231">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-232">包含音訊或影片的會議總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-233"><strong>A/V 會議紀要總計</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-234">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-234">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-235">專用於音訊/視訊會議的總分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="4e35c-236">總計 A/V 會議分鐘數的度量會總結所有音訊/視覺會議類型，包括： A/V 會議;IM 會議;app 共用會議;資料會議;和 PSTN 會議。</span><span class="sxs-lookup"><span data-stu-id="4e35c-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-237"><strong>A/V 會議參與者紀要總計</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-238">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-238">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-239">專用於音訊/視訊會議的參與者總分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-239">Total number of participant minutes devoted to audio/video conferencing.</span></span> <span data-ttu-id="4e35c-240">例如，假設一個使用者在音訊/視訊會議中花費5分鐘，而另一個使用者在該會議中花3分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="4e35c-240">For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference.</span></span> <span data-ttu-id="4e35c-241">這會產生總共8個參與者的分鐘數：5分鐘再加上3分鐘。</span><span class="sxs-lookup"><span data-stu-id="4e35c-241">That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-242"><strong>平均/V 會議分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-243">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-243">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-244">每個音訊/視訊會議的平均分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e35c-245"><strong>會議唯一召集人總數</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-246">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-246">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-247">至少組織一次會議的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-247">Total number of users who organized at least one conference.</span></span> <span data-ttu-id="4e35c-248">組織多個會議的使用者會算作一個唯一的召集人，就像只組織單一會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="4e35c-248">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e35c-249"><strong>會議訊息總計</strong></span><span class="sxs-lookup"><span data-stu-id="4e35c-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="4e35c-250">否</span><span class="sxs-lookup"><span data-stu-id="4e35c-250">No</span></span></p></td>
<td><p><span data-ttu-id="4e35c-251">在會議期間傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="4e35c-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

