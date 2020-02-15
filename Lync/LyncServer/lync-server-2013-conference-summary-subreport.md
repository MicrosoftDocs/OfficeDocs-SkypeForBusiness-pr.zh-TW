---
title: Lync Server 2013： 會議摘要子報表
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
ms.openlocfilehash: d2c31c614298112b91874882df1e4945845b74bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046316"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="cde22-102">Lync Server 2013 中的會議摘要子報表</span><span class="sxs-lookup"><span data-stu-id="cde22-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cde22-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="cde22-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="cde22-p101">會議摘要子報告提供了失敗會議工作階段的整體檢視。這些失敗的工作階段可藉由工作階段類型加以細分為：焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="cde22-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="cde22-106">篩選</span><span class="sxs-lookup"><span data-stu-id="cde22-106">Filters</span></span>

<span data-ttu-id="cde22-p102">篩選器可供您用於傳回更加精確的一組資料，或是使用其他方式檢視傳回的資料。下表列出可搭配會議摘要子報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="cde22-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="cde22-109">會議摘要子報告篩選器</span><span class="sxs-lookup"><span data-stu-id="cde22-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cde22-110">名稱</span><span class="sxs-lookup"><span data-stu-id="cde22-110">Name</span></span></th>
<th><span data-ttu-id="cde22-111">描述</span><span class="sxs-lookup"><span data-stu-id="cde22-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cde22-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-p103">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cde22-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cde22-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cde22-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cde22-p104">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="cde22-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cde22-118">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="cde22-118">7/7/2012</span></span></p>
<p><span data-ttu-id="cde22-119">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="cde22-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cde22-120">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="cde22-120">7/3/2012</span></span></p>
<p><span data-ttu-id="cde22-121">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="cde22-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde22-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-p105">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cde22-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cde22-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cde22-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cde22-p106">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="cde22-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cde22-128">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="cde22-128">7/7/2012</span></span></p>
<p><span data-ttu-id="cde22-129">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="cde22-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cde22-130">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="cde22-130">7/3/2012</span></span></p>
<p><span data-ttu-id="cde22-131">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="cde22-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cde22-132"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-p107">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="cde22-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cde22-136">計量</span><span class="sxs-lookup"><span data-stu-id="cde22-136">Metrics</span></span>

<span data-ttu-id="cde22-137">下表列出會議摘要子報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="cde22-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="cde22-138">會議摘要子報告計量</span><span class="sxs-lookup"><span data-stu-id="cde22-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cde22-139">姓名</span><span class="sxs-lookup"><span data-stu-id="cde22-139">Name</span></span></th>
<th><span data-ttu-id="cde22-140">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="cde22-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cde22-141">描述</span><span class="sxs-lookup"><span data-stu-id="cde22-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cde22-142"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-143">否</span><span class="sxs-lookup"><span data-stu-id="cde22-143">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-144">保留的會議總數。</span><span class="sxs-lookup"><span data-stu-id="cde22-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde22-145"><strong>會議工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-146">否</span><span class="sxs-lookup"><span data-stu-id="cde22-146">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-p108">會議工作階段總數。單一會議可能會有多個工作階段；例如，會議可能包含焦點工作階段及 MCU 工作階段。</span><span class="sxs-lookup"><span data-stu-id="cde22-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cde22-149"><strong>整體工作階段失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-150">否</span><span class="sxs-lookup"><span data-stu-id="cde22-150">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-151">所有失敗工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="cde22-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde22-152"><strong>焦點工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-153">否</span><span class="sxs-lookup"><span data-stu-id="cde22-153">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-154">焦點工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="cde22-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cde22-155"><strong>焦點失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-156">否</span><span class="sxs-lookup"><span data-stu-id="cde22-156">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-157">失敗之焦點工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="cde22-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde22-158">MCU 工作階段</span><span class="sxs-lookup"><span data-stu-id="cde22-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="cde22-159">否</span><span class="sxs-lookup"><span data-stu-id="cde22-159">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-160">MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="cde22-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cde22-161"><strong>MCU 失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-162">否</span><span class="sxs-lookup"><span data-stu-id="cde22-162">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-163">失敗之 MCU 工作階段的百分比。</span><span class="sxs-lookup"><span data-stu-id="cde22-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cde22-164"><strong>依形式區分的 MCU 工作階段</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-165">否</span><span class="sxs-lookup"><span data-stu-id="cde22-165">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-166">依形式分組 (例如，IM 會議) 的 MCU 工作階段總數。</span><span class="sxs-lookup"><span data-stu-id="cde22-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cde22-167"><strong>依形式區分的失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="cde22-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cde22-168">否</span><span class="sxs-lookup"><span data-stu-id="cde22-168">No</span></span></p></td>
<td><p><span data-ttu-id="cde22-169">依形式分組 (例如，IM 會議) 的 MCU 工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="cde22-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

