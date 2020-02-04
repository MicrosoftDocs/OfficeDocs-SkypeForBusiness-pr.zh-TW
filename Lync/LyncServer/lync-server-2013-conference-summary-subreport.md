---
title: Lync Server 2013：會議摘要子報表
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
ms.openlocfilehash: 2537cbe959639baee6f0f986b3faea1ebd79b5a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756987"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="aa0e2-102">Lync Server 2013 中的會議摘要子報表</span><span class="sxs-lookup"><span data-stu-id="aa0e2-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa0e2-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="aa0e2-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="aa0e2-104">[會議摘要] 子報表提供失敗會議會話的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-104">The Conference Summary Subreport provides an overall view of failed conference sessions.</span></span> <span data-ttu-id="aa0e2-105">這些失敗的會話會透過會話類型進一步細分：焦點會話與 MCU 會話。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-105">These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="aa0e2-106">濾鏡</span><span class="sxs-lookup"><span data-stu-id="aa0e2-106">Filters</span></span>

<span data-ttu-id="aa0e2-107">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="aa0e2-108">下表列出可與會議摘要子報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-108">The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="aa0e2-109">會議摘要子報表篩選</span><span class="sxs-lookup"><span data-stu-id="aa0e2-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0e2-110">名稱</span><span class="sxs-lookup"><span data-stu-id="aa0e2-110">Name</span></span></th>
<th><span data-ttu-id="aa0e2-111">說明</span><span class="sxs-lookup"><span data-stu-id="aa0e2-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-112"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-113">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-113">Start date/time for the time range.</span></span> <span data-ttu-id="aa0e2-114">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-114">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="aa0e2-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="aa0e2-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aa0e2-116">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="aa0e2-117">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-117">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aa0e2-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aa0e2-118">7/7/2012</span></span></p>
<p><span data-ttu-id="aa0e2-119">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aa0e2-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aa0e2-120">7/3/2012</span></span></p>
<p><span data-ttu-id="aa0e2-121">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0e2-122"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-123">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-123">End date/time for the time range.</span></span> <span data-ttu-id="aa0e2-124">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-124">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="aa0e2-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="aa0e2-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="aa0e2-126">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-126">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="aa0e2-127">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-127">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="aa0e2-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="aa0e2-128">7/7/2012</span></span></p>
<p><span data-ttu-id="aa0e2-129">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="aa0e2-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="aa0e2-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="aa0e2-130">7/3/2012</span></span></p>
<p><span data-ttu-id="aa0e2-131">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-132"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-133">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-133">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="aa0e2-134">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-134">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="aa0e2-135">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-135">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="aa0e2-136">指標</span><span class="sxs-lookup"><span data-stu-id="aa0e2-136">Metrics</span></span>

<span data-ttu-id="aa0e2-137">下表列出會議摘要子報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="aa0e2-138">會議摘要子報表度量單位</span><span class="sxs-lookup"><span data-stu-id="aa0e2-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa0e2-139">名稱</span><span class="sxs-lookup"><span data-stu-id="aa0e2-139">Name</span></span></th>
<th><span data-ttu-id="aa0e2-140">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="aa0e2-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="aa0e2-141">說明</span><span class="sxs-lookup"><span data-stu-id="aa0e2-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-142"><strong>會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-143">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-143">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-144">已舉行的會議總數。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0e2-145"><strong>會議會話總數</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-146">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-146">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-147">會議會話總數。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-147">Total number of conference sessions.</span></span> <span data-ttu-id="aa0e2-148">單一會議可以有多個會話;例如，會議可能同時包含焦點會話和 MCU 會話。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-148">A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-149"><strong>總體會話失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-150">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-150">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-151">所有失敗的會議所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0e2-152"><strong>焦點會話</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-153">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-153">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-154">焦點會話總數。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-155"><strong>焦點失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-156">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-156">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-157">失敗的焦點會話百分比。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0e2-158">MCU 會話</span><span class="sxs-lookup"><span data-stu-id="aa0e2-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-159">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-159">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-160">MCU 會話總數。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-161"><strong>MCU 失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-162">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-162">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-163">失敗的 MCU 會話百分比。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa0e2-164"><strong>使用模態的 MCU 會話</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-165">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-165">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-166">MCU 會話總數，依模態分組（例如 IM 會議）。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa0e2-167"><strong>依模態的失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="aa0e2-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="aa0e2-168">否</span><span class="sxs-lookup"><span data-stu-id="aa0e2-168">No</span></span></p></td>
<td><p><span data-ttu-id="aa0e2-169">失敗的 MCU 會話百分比，依模態分組（例如 IM 會議）。</span><span class="sxs-lookup"><span data-stu-id="aa0e2-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

