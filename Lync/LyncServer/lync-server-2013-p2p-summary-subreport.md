---
title: Lync Server 2013： P2P 摘要子報表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7199d9571adfb90b6f848f8f46474fd14813bc76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="558e0-102">Lync Server 2013 中的 P2P 摘要子報表</span><span class="sxs-lookup"><span data-stu-id="558e0-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="558e0-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="558e0-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="558e0-104">P2P 摘要子報表提供失敗的對等通訊會話的整體視圖。</span><span class="sxs-lookup"><span data-stu-id="558e0-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="558e0-105">濾鏡</span><span class="sxs-lookup"><span data-stu-id="558e0-105">Filters</span></span>

<span data-ttu-id="558e0-106">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同的方式來查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="558e0-106">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="558e0-107">下表列出可與 P2P 摘要子報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="558e0-107">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="558e0-108">P2P 摘要子報表篩選</span><span class="sxs-lookup"><span data-stu-id="558e0-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="558e0-109">名稱</span><span class="sxs-lookup"><span data-stu-id="558e0-109">Name</span></span></th>
<th><span data-ttu-id="558e0-110">描述</span><span class="sxs-lookup"><span data-stu-id="558e0-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="558e0-111"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-112">時間範圍的開始日期和時間。</span><span class="sxs-lookup"><span data-stu-id="558e0-112">Start date and time for the time range.</span></span> <span data-ttu-id="558e0-113">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="558e0-113">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="558e0-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="558e0-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="558e0-115">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="558e0-115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="558e0-116">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="558e0-116">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="558e0-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="558e0-117">7/7/2012</span></span></p>
<p><span data-ttu-id="558e0-118">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="558e0-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="558e0-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="558e0-119">7/3/2012</span></span></p>
<p><span data-ttu-id="558e0-120">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="558e0-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558e0-121"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-122">時間範圍的結束日期和時間。</span><span class="sxs-lookup"><span data-stu-id="558e0-122">End date and time for the time range.</span></span> <span data-ttu-id="558e0-123">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="558e0-123">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="558e0-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="558e0-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="558e0-125">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="558e0-125">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="558e0-126">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="558e0-126">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="558e0-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="558e0-127">7/7/2012</span></span></p>
<p><span data-ttu-id="558e0-128">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="558e0-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="558e0-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="558e0-129">7/3/2012</span></span></p>
<p><span data-ttu-id="558e0-130">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="558e0-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558e0-131"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-132">註冊機構池或邊緣伺服器的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="558e0-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="558e0-133">您可以選取個別的池中，或按一下<strong>[全部]</strong>來查看所有資源庫的資料。</span><span class="sxs-lookup"><span data-stu-id="558e0-133">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="558e0-134">這個下拉式清單會根據資料庫中的記錄，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="558e0-134">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="558e0-135">指標</span><span class="sxs-lookup"><span data-stu-id="558e0-135">Metrics</span></span>

<span data-ttu-id="558e0-136">下表列出 P2P 摘要子報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="558e0-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="558e0-137">P2P 摘要子報表度量單位</span><span class="sxs-lookup"><span data-stu-id="558e0-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="558e0-138">名稱</span><span class="sxs-lookup"><span data-stu-id="558e0-138">Name</span></span></th>
<th><span data-ttu-id="558e0-139">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="558e0-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="558e0-140">描述</span><span class="sxs-lookup"><span data-stu-id="558e0-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="558e0-141"><strong>總會話數</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-142">否</span><span class="sxs-lookup"><span data-stu-id="558e0-142">No</span></span></p></td>
<td><p><span data-ttu-id="558e0-143">會話總數，包括成功的會話、失敗的會話（預期的失敗與意外的失敗），以及未分類的會話。</span><span class="sxs-lookup"><span data-stu-id="558e0-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558e0-144"><strong>失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-145">否</span><span class="sxs-lookup"><span data-stu-id="558e0-145">No</span></span></p></td>
<td><p><span data-ttu-id="558e0-146">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="558e0-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="558e0-147"><strong>依模態的課時</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-148">否</span><span class="sxs-lookup"><span data-stu-id="558e0-148">No</span></span></p></td>
<td><p><span data-ttu-id="558e0-149">依模態分組的會話總數（例如，立即訊息）。</span><span class="sxs-lookup"><span data-stu-id="558e0-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="558e0-150"><strong>依模態的失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="558e0-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="558e0-151">否</span><span class="sxs-lookup"><span data-stu-id="558e0-151">No</span></span></p></td>
<td><p><span data-ttu-id="558e0-152">依模態分組的失敗會話總數（例如立即訊息）。</span><span class="sxs-lookup"><span data-stu-id="558e0-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

