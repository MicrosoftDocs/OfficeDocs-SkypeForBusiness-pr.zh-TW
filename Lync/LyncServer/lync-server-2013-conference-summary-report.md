---
title: Lync Server 2013：會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4390c2f3aa18820668415543496dfdcfd5aa79e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502350"
---
# <a name="conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="a3bbe-102">Lync Server 2013 中的會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="a3bbe-102">Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3bbe-103">_**主題上次修改日期：** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="a3bbe-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="a3bbe-104">會議摘要報告提供線上會議工作階段的整體檢視。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-104">The Conference Summary Report provides an overall view of your online conferencing sessions.</span></span> <span data-ttu-id="a3bbe-105">會議通常會包含超過2個使用者，且需要使用 Microsoft Lync Server 2013 會議服務。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-105">A conference typically involves more than 2 users and requires the use of Microsoft Lync Server 2013 conferencing services.</span></span> <span data-ttu-id="a3bbe-106">相較之下，對等工作階段通常只涉及兩位使用者，而且不需要使用 Lync Server 的會議服務。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-106">By comparison, a peer-to-peer session typically involves just 2 users and does not require the use of Lync Server's conferencing services.</span></span> <span data-ttu-id="a3bbe-107">對等活動會在 [Lync Server 2013 的「Peer-to-Peer 活動摘要」報告](lync-server-2013-peer-to-peer-activity-summary-report.md)上報告。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-107">Peer-to-peer activities are reported on the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).</span></span>

<span data-ttu-id="a3bbe-108">會議摘要報告不僅會告訴您每小時、每日、每週、) 每月都有多少會議已在指定期間內舉行 (，但也會告訴您在這些會議中進行部分工作的人數，以及唯一會議召集人的總數。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-108">The Conference Summary Report not only tells you how many conferences were held during a given time period (hourly, daily, weekly, monthly) but also tells you the total number of people who took part in those conferences, and the total number of unique conference organizers.</span></span>

<span data-ttu-id="a3bbe-p102">「專屬」召集人是任何至少排程一場會議的人。例如，如果 Pilar Ackerman 排程一場會議，她就算是一位專屬召集人。如果 Ken Myer 排程 148 場會議，他也算是一位專屬召集人。 例如，下表顯示排程 8 場會議，但只有 3 位專屬召集人 (Ken Myer、Pilar Ackerman 及 David Ahs)。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p102">A "unique” organizer is anyone who schedules at least one conference. For example, if Pilar Ackerman schedules one conference she counts as one unique organizer. If Ken Myer schedules 148 conferences he, too counts as one unique organizer. For example, the table below shows 8 conferences scheduled, but just three unique organizers (Ken Myer, Pilar Ackerman, and David Ahs).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3bbe-113">會議召集人</span><span class="sxs-lookup"><span data-stu-id="a3bbe-113">Conference Organizer</span></span></th>
<th><span data-ttu-id="a3bbe-114">會議日期</span><span class="sxs-lookup"><span data-stu-id="a3bbe-114">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-115">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-115">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-116">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-116">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-117">David Ahs</span><span class="sxs-lookup"><span data-stu-id="a3bbe-117">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-118">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-118">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-119">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-119">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-120">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-120">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-121">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-121">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-122">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-122">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-123">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-123">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-124">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-125">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-125">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-126">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-126">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-127">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-127">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-128">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-128">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-129">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-129">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-130">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-130">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3bbe-131">會議摘要報告還會指出多少場會議包含音訊和/或視訊。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-131">The Conference Summary Report also indicates how many conferences included audio and/or video.</span></span>

<div>

## <a name="accessing-the-conference-summary-report"></a><span data-ttu-id="a3bbe-132">存取會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="a3bbe-132">Accessing the Conference Summary Report</span></span>

<span data-ttu-id="a3bbe-p103">從 [監控報告] 首頁可存取會議摘要報告。按下列計量，即可向下切入至會議活動報告：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p103">The Conference Summary Report is accessed from the Monitoring Reports home page. You can drill down to the Conference Activity report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a3bbe-135">會議總數</span><span class="sxs-lookup"><span data-stu-id="a3bbe-135">Total conferences</span></span>

  - <span data-ttu-id="a3bbe-136">參與者總數</span><span class="sxs-lookup"><span data-stu-id="a3bbe-136">Total participants</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a><span data-ttu-id="a3bbe-137">發揮會議摘要報告的最大效用</span><span class="sxs-lookup"><span data-stu-id="a3bbe-137">Making the Best Use of the Conference Summary Report</span></span>

<span data-ttu-id="a3bbe-p104">會議摘要報告上大多數所用計量的總數值可見於報告下方；向下捲動即可見到這些值，例如指定期間內舉行的會議總數，以及參與這些會議的總人數。報告下方未總計的一個計量是專屬會議召集人總數。理由何在？原因之一是，假設您在檢視一個月的資料，第一天有 34 位專屬會議召集人，第二天有 27 位專屬會議召集人。這表示兩天總共有 61 位專屬會議召集人嗎？這可不一定。畢竟在第二天召集會議的所有 27 位人員有有可能就在第一天召集會議的 34 位人員之中。例如，在下列簡單報告中，注意到 Ken Myer 與 Pilar Ackerman 在 7/7/2012 和 7/2/2012 兩天都有排程會議：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p104">Total values for most of the metrics used on the Conference Summary Report can be found at the bottom of the report; scroll down to see values such as the total number of conferences held during the specified time period, and the total number of people who participated in those conferences. One metric that is not totaled at the bottom of the report is Total unique conference organizers. Why not? Here’s one reason. Suppose you are looking at a month's worth of data. On day 1 you had 34 unique conference organizers; on day 2 you had 27 unique conference organizers. Does that mean you had 61 unique conference organizers for those two days? Not necessarily. After all, all 27 people who organized conferences on day 2 might be among the 34 people who organized conferences on day 1. For example, in this simple report, note that Ken Myer and Pilar Ackerman scheduled conferences both on 7/7/2012 and on 7/2/2012:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3bbe-148">會議召集人</span><span class="sxs-lookup"><span data-stu-id="a3bbe-148">Conference Organizer</span></span></th>
<th><span data-ttu-id="a3bbe-149">會議日期</span><span class="sxs-lookup"><span data-stu-id="a3bbe-149">Conference Date</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-150">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-150">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-151">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-151">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-152">David Ahs</span><span class="sxs-lookup"><span data-stu-id="a3bbe-152">David Ahs</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-153">7/7/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-153">7/7/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-154">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-154">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-155">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-155">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-156">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-156">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-157">7/7/2012 11:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-157">7/7/2012 11:00 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-158">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-158">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-159">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-159">7/7/2012 1:00 PM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-160">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-160">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-161">7/7/2012 2:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-161">7/7/2012 2:00 PM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-162">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="a3bbe-162">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-163">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-163">7/2/2012 10:00 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-164">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="a3bbe-164">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-165">7/2/2012 10:00 AM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-165">7/2/2012 10:00 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3bbe-166">若要更清楚了解召集會議之專屬使用者的總數，請變更時間間隔；例如，按月而不是按日來檢視資料。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-166">To get a better idea of the total number of unique users who organized conferences, change your time interval; for example, look at the data by month instead of by day.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a3bbe-167">篩選</span><span class="sxs-lookup"><span data-stu-id="a3bbe-167">Filters</span></span>

<span data-ttu-id="a3bbe-p105">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，會議摘要報告可讓您選擇如何將資料分組。在這種情況下，會議會按照小時、日、星期或月加以分組。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p105">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Conference Summary Report enables you to choose how data should be grouped. In this case, conferences grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a3bbe-171">下表列出您可以用於會議摘要報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-171">The following table lists the filters that you can use with the Conference Summary Report.</span></span>

### <a name="conference-summary-report-filters"></a><span data-ttu-id="a3bbe-172">會議摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="a3bbe-172">Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3bbe-173">名稱</span><span class="sxs-lookup"><span data-stu-id="a3bbe-173">Name</span></span></th>
<th><span data-ttu-id="a3bbe-174">描述</span><span class="sxs-lookup"><span data-stu-id="a3bbe-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-175"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-175"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a3bbe-178">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-178">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a3bbe-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a3bbe-181">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a3bbe-181">7/7/2012</span></span></p>
<p><span data-ttu-id="a3bbe-182">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-182">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a3bbe-183">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a3bbe-183">7/3/2012</span></span></p>
<p><span data-ttu-id="a3bbe-184">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-184">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-185"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-185"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a3bbe-188">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a3bbe-188">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a3bbe-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a3bbe-191">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a3bbe-191">7/7/2012</span></span></p>
<p><span data-ttu-id="a3bbe-192">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-192">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a3bbe-193">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a3bbe-193">7/3/2012</span></span></p>
<p><span data-ttu-id="a3bbe-194">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-194">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-195"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-195"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p110">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="a3bbe-198">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="a3bbe-198">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a3bbe-199">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="a3bbe-199">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a3bbe-200">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="a3bbe-200">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="a3bbe-201">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="a3bbe-201">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="a3bbe-p111">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 8/7/2012 及 2/28/2012，將只會顯示 8/7/2012 上午 12:00 至 9/7/2012 上午 12:00 這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a3bbe-204">指標</span><span class="sxs-lookup"><span data-stu-id="a3bbe-204">Metrics</span></span>

<span data-ttu-id="a3bbe-205">下表列出會議摘要報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-205">The following table the information provided by the Conferences Summary Report.</span></span>

### <a name="conference-summary-report-metrics"></a><span data-ttu-id="a3bbe-206">會議摘要報告計量</span><span class="sxs-lookup"><span data-stu-id="a3bbe-206">Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3bbe-207">姓名</span><span class="sxs-lookup"><span data-stu-id="a3bbe-207">Name</span></span></th>
<th><span data-ttu-id="a3bbe-208">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="a3bbe-208">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a3bbe-209">描述</span><span class="sxs-lookup"><span data-stu-id="a3bbe-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-210"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-210"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="a3bbe-211"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-211"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="a3bbe-212"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-212"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="a3bbe-213"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-213"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-214">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-214">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p112">指出在篩選工具列上所選取的時間間隔。在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。例如，若是使用 [每日] 間隔，而按一下 7/7/2012，將可檢視當天按小時顯示的使用者註冊活動。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p112">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-218"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-218"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-219">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-219">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p113">已舉辦的會議總數 (無論會議類型為何)。當您按一下此項目，報告即顯示所選定時段的會議活動報告。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p113">Total number of conferences (regardless of conference type) that were held. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-222"><strong>參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-222"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-223">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-223">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p114">參加會議的總人數。當您按一下此項目，報告即顯示所選定時段的會議活動報告。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p114">Total number of people who took part in the conferences. When you click this item, the report shows you the Conference Activity Report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-226"><strong>每次會議的平均參加人數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-226"><strong>Average participants per conference</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-227">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-227">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p115">參加給定會議的平均人數。將會議總數除以參與者總數得之。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p115">Average number of people who took part in a given conference. Determined by dividing the total conferences by the total participants.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-230"><strong>A/V 會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-230"><strong>Total A/V conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-231">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-231">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-232">包含音訊或視訊的會議總數。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-232">Total number of conferences that included audio or video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-233"><strong>A/V 會議總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-233"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-234">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-234">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-235">用於音訊/視訊會議的總分鐘數。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-235">Total number of minutes devoted to audio/video conferencing.</span></span></p>
<p><span data-ttu-id="a3bbe-236">A/V 會議紀要度量總數摘要會摘要所有音訊/視訊會議類型，包括： A/V 會議;IM 會議;應用程式共用會議;資料會議;和 PSTN 會議。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-236">The Total A/V conference minutes metric summarizes all the audio/visual conference types, including: A/V conferences; IM conferences; app sharing conferences; data conferences; and PSTN conferences.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-237"><strong>A/V 會議參與者總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-237"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-238">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-238">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p116">用於音訊/視訊會議的參與者總分鐘數。例如，假設一位使用者花 5 分鐘參加音訊/視訊會議，而另一位使用者花 3 分鐘參加相同的會議。所以參與者總分鐘數為 8 分鐘：5 分鐘加 3 分鐘。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p116">Total number of participant minutes devoted to audio/video conferencing. For example, suppose one user spends 5 minutes in an audio/video conference and a second user spends 3 minutes in that same conference. That makes a total of 8 participant minutes: 5 minutes plus 3 minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-242"><strong>A/V 會議平均分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-242"><strong>Average A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-243">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-243">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-244">每次音訊/視訊會議的平均分鐘數。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-244">Average number of minutes per audio/video conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3bbe-245"><strong>會議專屬召集人總數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-245"><strong>Total number of unique organizers of conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-246">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-246">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-p117">至少召集過一次會議的使用者總數。召集過多次會議的使用者計為一個專屬召集人，就像只召集過一次會議的使用者一樣。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-p117">Total number of users who organized at least one conference. Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3bbe-249"><strong>會議訊息總數</strong></span><span class="sxs-lookup"><span data-stu-id="a3bbe-249"><strong>Total conference messages</strong></span></span></p></td>
<td><p><span data-ttu-id="a3bbe-250">否</span><span class="sxs-lookup"><span data-stu-id="a3bbe-250">No</span></span></p></td>
<td><p><span data-ttu-id="a3bbe-251">會議期間傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="a3bbe-251">Total number of instant messages sent during the conferences.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

