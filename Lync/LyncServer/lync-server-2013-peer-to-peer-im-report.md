---
title: Lync Server 2013： 對等 IM 報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e2cf987c40279a4854b9fe776c1585247d24e55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a><span data-ttu-id="80367-102">Lync Server 2013 中的對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="80367-102">Peer-to-Peer IM Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80367-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="80367-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="80367-p101">對等 IM 報告會提供對等立即訊息 (IM) 工作階段的趨勢資訊 (依集區和驗證類型細分)。此報告可以顯示指定時段內 (例如，每天或每小時) 主控的工作階段總數，或者可以顯示該時段內傳送的立即訊息總數。</span><span class="sxs-lookup"><span data-stu-id="80367-p101">The Peer-to-Peer IM Report provides trend information about peer-to-peer instant messaging (IM) sessions, broken down by pool and by authentication type. The report can show either the total number of sessions held during the specified time period (for example, day-by-day or hour-by-hour), or it can show the total number of instant messages sent during that time period.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a><span data-ttu-id="80367-106">存取對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="80367-106">Accessing the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="80367-107">您可以存取對等 IM 報告只能透過開啟[對等活動摘要報告在 Lync Server 2013 中](lync-server-2013-peer-to-peer-activity-summary-report.md)，再按一下下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="80367-107">You can access the Peer-to-Peer IM Report only by opening the [Peer-to-Peer Activity Summary Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) and then clicking either of the following metrics:</span></span>

  - <span data-ttu-id="80367-108">對等 IM 工作階段總數</span><span class="sxs-lookup"><span data-stu-id="80367-108">Total peer-to-peer IM sessions</span></span>

  - <span data-ttu-id="80367-109">對等 IM 訊息總數</span><span class="sxs-lookup"><span data-stu-id="80367-109">Total peer-to-peer IM messages</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a><span data-ttu-id="80367-110">善加利用對等 IM 報告</span><span class="sxs-lookup"><span data-stu-id="80367-110">Making the Best Use of the Peer-to-Peer IM Report</span></span>

<span data-ttu-id="80367-p102">依預設，對等 IM 報告會顯示每小時 (或每天，視您的設定而定) 的訊息計數。不過，您也可以選擇依每小時的工作階段來檢視那一天。若要執行這項作業，請按一下報告視窗右上角的 [隱藏/顯示參數]\*\*\*\*，然後從 [報告者]\*\*\*\* 清單按一下 [工作階段計數]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="80367-p102">By default, the Peer-to-Peer IM Report shows you the message count per-hour (or day, depending on your settings). However, you can also choose to view the day by sessions per hour. To do that, click **Hide/Show Parameters** in the upper-right corner of the Reports window, and then click **Session Count** from the **Report by** list.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="80367-114">篩選</span><span class="sxs-lookup"><span data-stu-id="80367-114">Filters</span></span>

<span data-ttu-id="80367-p103">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。下表列出您可以搭配對等 IM 報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="80367-p103">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Peer-to-Peer IM Report.</span></span>

### <a name="peer-to-peer-im-report-filters"></a><span data-ttu-id="80367-117">對等 IM 報告篩選器</span><span class="sxs-lookup"><span data-stu-id="80367-117">Peer-to-Peer IM Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80367-118">名稱</span><span class="sxs-lookup"><span data-stu-id="80367-118">Name</span></span></th>
<th><span data-ttu-id="80367-119">描述</span><span class="sxs-lookup"><span data-stu-id="80367-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80367-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="80367-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-p104">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="80367-p104">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="80367-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="80367-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="80367-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="80367-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="80367-126">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="80367-126">7/7/2012</span></span></p>
<p><span data-ttu-id="80367-127">若要按星期或月份查看，請輸入當週或該月內的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="80367-127">To view by week or by month, enter a date that falls anywhere within the week or month (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="80367-128">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="80367-128">7/3/2012</span></span></p>
<p><span data-ttu-id="80367-129">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="80367-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80367-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="80367-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-p106">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="80367-p106">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="80367-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="80367-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="80367-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="80367-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="80367-136">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="80367-136">7/7/2012</span></span></p>
<p><span data-ttu-id="80367-137">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="80367-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="80367-138">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="80367-138">7/3/2012</span></span></p>
<p><span data-ttu-id="80367-139">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="80367-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80367-140"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="80367-140"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="80367-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="80367-143">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="80367-143">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="80367-144">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="80367-144">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="80367-145">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="80367-145">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="80367-146">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="80367-146">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="80367-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="80367-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval then only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80367-149"><strong>報告依據</strong></span><span class="sxs-lookup"><span data-stu-id="80367-149"><strong>Report by</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-p110">指定報告中所要使用的值。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="80367-p110">Indicates the values to be used in the report. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="80367-152">工作階段計數</span><span class="sxs-lookup"><span data-stu-id="80367-152">Session count</span></span></p></li>
<li><p><span data-ttu-id="80367-153">訊息計數</span><span class="sxs-lookup"><span data-stu-id="80367-153">Message count</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="80367-154">對等 IM 工作階段計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="80367-154">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<span data-ttu-id="80367-155">下表列出對等 IM 報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="80367-155">The following table lists the information provided in the Peer-to-Peer IM Report.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a><span data-ttu-id="80367-156">對等 IM 工作階段計量 (依集區)</span><span class="sxs-lookup"><span data-stu-id="80367-156">Metrics for Peer-to-Peer IM Session by Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80367-157">名稱</span><span class="sxs-lookup"><span data-stu-id="80367-157">Name</span></span></th>
<th><span data-ttu-id="80367-158">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="80367-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="80367-159">描述</span><span class="sxs-lookup"><span data-stu-id="80367-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80367-160"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="80367-160"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-161">否</span><span class="sxs-lookup"><span data-stu-id="80367-161">No</span></span></p></td>
<td><p><span data-ttu-id="80367-162">登錄器集區或 Edge Server 的名稱。</span><span class="sxs-lookup"><span data-stu-id="80367-162">Name of the Registrar pool or Edge Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80367-163"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="80367-163"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-164">否</span><span class="sxs-lookup"><span data-stu-id="80367-164">No</span></span></p></td>
<td><p><span data-ttu-id="80367-165">工作階段的執行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="80367-165">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80367-166"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="80367-166"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-167">否</span><span class="sxs-lookup"><span data-stu-id="80367-167">No</span></span></p></td>
<td><p><span data-ttu-id="80367-168">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="80367-168">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="80367-169">對等 IM 工作階段計量 (依驗證類型)</span><span class="sxs-lookup"><span data-stu-id="80367-169">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<span data-ttu-id="80367-170">下表列出對等 IM 報告針對參與者在對等工作階段中使用之每項驗證類型所提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="80367-170">The following table lists the information provided in the Peer-to-Peer IM Report for each type of authentication used by the participants in a peer-to-peer session.</span></span>

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a><span data-ttu-id="80367-171">對等 IM 工作階段計量 (依驗證類型)</span><span class="sxs-lookup"><span data-stu-id="80367-171">Metrics for Peer-to-Peer IM Session by Authentication Type</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80367-172">名稱</span><span class="sxs-lookup"><span data-stu-id="80367-172">Name</span></span></th>
<th><span data-ttu-id="80367-173">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="80367-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="80367-174">描述</span><span class="sxs-lookup"><span data-stu-id="80367-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80367-175"><strong>驗證類型</strong></span><span class="sxs-lookup"><span data-stu-id="80367-175"><strong>Authentication type</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-176">否</span><span class="sxs-lookup"><span data-stu-id="80367-176">No</span></span></p></td>
<td><p><span data-ttu-id="80367-p111">工作階段參與者所使用的驗證類型。一般來說，值都是下列其中之一：</span><span class="sxs-lookup"><span data-stu-id="80367-p111">Type of authentication used by the session participants. Values are typically one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="80367-179">企業</span><span class="sxs-lookup"><span data-stu-id="80367-179">Enterprise</span></span></p></li>
<li><p><span data-ttu-id="80367-180">同盟</span><span class="sxs-lookup"><span data-stu-id="80367-180">Federated</span></span></p></li>
<li><p><span data-ttu-id="80367-181">PIC</span><span class="sxs-lookup"><span data-stu-id="80367-181">PIC</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80367-182"><strong>日期/時間</strong></span><span class="sxs-lookup"><span data-stu-id="80367-182"><strong>Date/Time</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-183">否</span><span class="sxs-lookup"><span data-stu-id="80367-183">No</span></span></p></td>
<td><p><span data-ttu-id="80367-184">工作階段的執行日期與時間。</span><span class="sxs-lookup"><span data-stu-id="80367-184">Date and time that the sessions took place.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80367-185"><strong>Total</strong></span><span class="sxs-lookup"><span data-stu-id="80367-185"><strong>Total</strong></span></span></p></td>
<td><p><span data-ttu-id="80367-186">否</span><span class="sxs-lookup"><span data-stu-id="80367-186">No</span></span></p></td>
<td><p><span data-ttu-id="80367-187">工作階段總數或訊息總數。</span><span class="sxs-lookup"><span data-stu-id="80367-187">Total number of sessions or total message count.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

