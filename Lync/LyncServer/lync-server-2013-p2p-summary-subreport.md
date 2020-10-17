---
title: Lync Server 2013： P2P 摘要子報表
description: Lync Server 2013： P2P 摘要子報表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eda51e76c4ed7b62535a2a2e4ab52982aa6381f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557379"
---
# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="15df6-103">Lync Server 2013 中的 P2P 摘要子報表</span><span class="sxs-lookup"><span data-stu-id="15df6-103">P2P Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15df6-104">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="15df6-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="15df6-105">P2P 摘要子報表可提供失敗的對等通訊會話的整體觀點。</span><span class="sxs-lookup"><span data-stu-id="15df6-105">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="15df6-106">篩選</span><span class="sxs-lookup"><span data-stu-id="15df6-106">Filters</span></span>

<span data-ttu-id="15df6-107">篩選器可以讓您傳回更精確的資料集，或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="15df6-107">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="15df6-108">下表列出您可以搭配 P2P 摘要子報表使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="15df6-108">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="15df6-109">P2P 摘要子報表篩選</span><span class="sxs-lookup"><span data-stu-id="15df6-109">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15df6-110">名稱</span><span class="sxs-lookup"><span data-stu-id="15df6-110">Name</span></span></th>
<th><span data-ttu-id="15df6-111">描述</span><span class="sxs-lookup"><span data-stu-id="15df6-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15df6-112"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-p102">時間範圍的開始日期和時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="15df6-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="15df6-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="15df6-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="15df6-p103">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="15df6-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15df6-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="15df6-118">7/7/2012</span></span></p>
<p><span data-ttu-id="15df6-119">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="15df6-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15df6-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="15df6-120">7/3/2012</span></span></p>
<p><span data-ttu-id="15df6-121">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="15df6-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15df6-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-p104">時間範圍的結束日期和時間。若要按照小時檢視資料，請輸入結束日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="15df6-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="15df6-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="15df6-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="15df6-p105">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="15df6-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="15df6-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="15df6-128">7/7/2012</span></span></p>
<p><span data-ttu-id="15df6-129">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="15df6-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="15df6-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="15df6-130">7/3/2012</span></span></p>
<p><span data-ttu-id="15df6-131">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="15df6-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15df6-132"><strong>集區</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-p106">登錄器集區或 Edge Server 的完整網域名稱 (FQDN)。您可以選取個別的集區，或是按一下 [全部]<strong></strong> 檢視所有集區的資料。此下拉式清單會自動將資料庫內的資料填入。</span><span class="sxs-lookup"><span data-stu-id="15df6-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="15df6-136">指標</span><span class="sxs-lookup"><span data-stu-id="15df6-136">Metrics</span></span>

<span data-ttu-id="15df6-137">下表列出 P2P 摘要子報表中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="15df6-137">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="15df6-138">P2P 摘要子報表度量</span><span class="sxs-lookup"><span data-stu-id="15df6-138">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15df6-139">姓名</span><span class="sxs-lookup"><span data-stu-id="15df6-139">Name</span></span></th>
<th><span data-ttu-id="15df6-140">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="15df6-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="15df6-141">描述</span><span class="sxs-lookup"><span data-stu-id="15df6-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15df6-142"><strong>工作階段總數</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-142"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-143">否</span><span class="sxs-lookup"><span data-stu-id="15df6-143">No</span></span></p></td>
<td><p><span data-ttu-id="15df6-144">工作階段的總數，包括成功的工作階段、失敗的工作階段 (預期失敗與未預期失敗) 以及未分類的工作階段。</span><span class="sxs-lookup"><span data-stu-id="15df6-144">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15df6-145"><strong>失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-145"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-146">否</span><span class="sxs-lookup"><span data-stu-id="15df6-146">No</span></span></p></td>
<td><p><span data-ttu-id="15df6-147">失敗的點對點工作階段百分比。</span><span class="sxs-lookup"><span data-stu-id="15df6-147">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15df6-148"><strong>依模態的會話</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-148"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-149">否</span><span class="sxs-lookup"><span data-stu-id="15df6-149">No</span></span></p></td>
<td><p><span data-ttu-id="15df6-150">依模態模式分組的會話總數 (例如立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="15df6-150">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15df6-151"><strong>依形式區分的失敗率</strong></span><span class="sxs-lookup"><span data-stu-id="15df6-151"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="15df6-152">否</span><span class="sxs-lookup"><span data-stu-id="15df6-152">No</span></span></p></td>
<td><p><span data-ttu-id="15df6-153">依形式分類 (所群組的失敗會話總數，例如立即訊息) 。</span><span class="sxs-lookup"><span data-stu-id="15df6-153">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

