---
title: Lync Server 2013：會議摘要子報告
description: Lync Server 2013：會議摘要子報表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550689"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="11688-103">Lync Server 2013 中的會議摘要子報告</span><span class="sxs-lookup"><span data-stu-id="11688-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11688-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="11688-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="11688-p101">會議摘要子報告提供了失敗會議工作階段的整體檢視。這些失敗的工作階段可藉由工作階段類型加以細分為：焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="11688-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="11688-107">篩選</span><span class="sxs-lookup"><span data-stu-id="11688-107">Filters</span></span>

<span data-ttu-id="11688-p102">篩選器可供您用於傳回更加精確的一組資料，或是使用其他方式檢視傳回的資料。下表列出可搭配會議摘要子報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="11688-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="11688-110">會議摘要子報告篩選器</span><span class="sxs-lookup"><span data-stu-id="11688-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11688-111">名稱</span><span class="sxs-lookup"><span data-stu-id="11688-111">Name</span></span></th>
<th><span data-ttu-id="11688-112">描述</span><span class="sxs-lookup"><span data-stu-id="11688-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11688-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="11688-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-p103">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="11688-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="11688-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="11688-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="11688-p104">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="11688-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="11688-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="11688-119">7/7/2012</span></span></p>
<p><span data-ttu-id="11688-120">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="11688-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="11688-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="11688-121">7/3/2012</span></span></p>
<p><span data-ttu-id="11688-122">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="11688-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11688-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="11688-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-p105">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="11688-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="11688-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="11688-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="11688-p106">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="11688-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="11688-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="11688-129">7/7/2012</span></span></p>
<p><span data-ttu-id="11688-130">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="11688-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="11688-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="11688-131">7/3/2012</span></span></p>
<p><span data-ttu-id="11688-132">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="11688-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11688-133"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="11688-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-p107">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="11688-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="11688-137">指標</span><span class="sxs-lookup"><span data-stu-id="11688-137">Metrics</span></span>

<span data-ttu-id="11688-138">下表列出會議摘要子報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="11688-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="11688-139">會議摘要子報告計量</span><span class="sxs-lookup"><span data-stu-id="11688-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11688-140">姓名</span><span class="sxs-lookup"><span data-stu-id="11688-140">Name</span></span></th>
<th><span data-ttu-id="11688-141">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="11688-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="11688-142">描述</span><span class="sxs-lookup"><span data-stu-id="11688-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11688-143"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="11688-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-144">否</span><span class="sxs-lookup"><span data-stu-id="11688-144">No</span></span></p></td>
<td><p><span data-ttu-id="11688-145">保留的會議總數。</span><span class="sxs-lookup"><span data-stu-id="11688-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11688-146"><strong>會議工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="11688-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-147">否</span><span class="sxs-lookup"><span data-stu-id="11688-147">No</span></span></p></td>
<td><p><span data-ttu-id="11688-p108">會議工作階段總數。單一會議可能會有多個工作階段；例如，會議可能包含焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="11688-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11688-150"><strong>整體工作階段失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="11688-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-151">否</span><span class="sxs-lookup"><span data-stu-id="11688-151">No</span></span></p></td>
<td><p><span data-ttu-id="11688-152">所有失敗工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="11688-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11688-153"><strong>焦點工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="11688-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-154">否</span><span class="sxs-lookup"><span data-stu-id="11688-154">No</span></span></p></td>
<td><p><span data-ttu-id="11688-155">焦點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="11688-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11688-156"><strong>焦點失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="11688-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-157">否</span><span class="sxs-lookup"><span data-stu-id="11688-157">No</span></span></p></td>
<td><p><span data-ttu-id="11688-158">失敗之焦點工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="11688-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11688-159">MCU 工作階段</span><span class="sxs-lookup"><span data-stu-id="11688-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="11688-160">否</span><span class="sxs-lookup"><span data-stu-id="11688-160">No</span></span></p></td>
<td><p><span data-ttu-id="11688-161">MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="11688-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11688-162"><strong>MCU 失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="11688-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-163">否</span><span class="sxs-lookup"><span data-stu-id="11688-163">No</span></span></p></td>
<td><p><span data-ttu-id="11688-164">失敗之 MCU 工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="11688-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="11688-165"><strong>依形式區分的 MCU 工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="11688-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-166">否</span><span class="sxs-lookup"><span data-stu-id="11688-166">No</span></span></p></td>
<td><p><span data-ttu-id="11688-167">依形式分組 (例如，IM 會議) 的 MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="11688-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="11688-168"><strong>依形式區分的失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="11688-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="11688-169">否</span><span class="sxs-lookup"><span data-stu-id="11688-169">No</span></span></p></td>
<td><p><span data-ttu-id="11688-170">依形式分組 (例如，IM 會議) 的 MCU 工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="11688-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

