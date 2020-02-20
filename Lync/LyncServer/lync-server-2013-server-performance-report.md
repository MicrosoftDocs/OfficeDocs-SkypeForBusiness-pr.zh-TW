---
title: Lync Server 2013： 伺服器效能報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05c1e366c797eb0c626d00744ef6f0088d28e465
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="686a4-102">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="686a4-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="686a4-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="686a4-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="686a4-104">伺服器效能報告提供經歷最高-收訊不良通話百分比的 Microsoft Lync Server 2013 伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="686a4-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="686a4-105">報表會分解伺服器的伺服器類型，報告下列類型的不同統計資料：</span><span class="sxs-lookup"><span data-stu-id="686a4-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="686a4-106">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="686a4-106">Mediation Server</span></span>

  - <span data-ttu-id="686a4-107">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="686a4-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="686a4-108">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="686a4-108">A/V Edge Server</span></span>

  - <span data-ttu-id="686a4-109">閘道 （中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="686a4-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="686a4-110">閘道 （中繼伺服器旁路）</span><span class="sxs-lookup"><span data-stu-id="686a4-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="686a4-111">視訊 (包括視訊計量 a / V 會議伺服器和 A / V Edge server)</span><span class="sxs-lookup"><span data-stu-id="686a4-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="686a4-112">應用程式共用 (包括應用程式共用計量 a / V 會議伺服器和 A / V Edge server)</span><span class="sxs-lookup"><span data-stu-id="686a4-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="686a4-113">請務必注意，在此報告中顯示成相對排名排名。</span><span class="sxs-lookup"><span data-stu-id="686a4-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="686a4-114">例如，假設您最壞打算執行的伺服器有其 1000 撥電話之間的一個收訊不良通話。</span><span class="sxs-lookup"><span data-stu-id="686a4-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="686a4-115">這是更多比接受百分比。 1%。</span><span class="sxs-lookup"><span data-stu-id="686a4-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="686a4-116">不過，如果這是最壞打算執行伺服器必須 (亦即，如果所有其他伺服器有即使低於收訊不良通話百分比。 1%)，然後該伺服器仍會出現在 [伺服器效能報告。</span><span class="sxs-lookup"><span data-stu-id="686a4-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="686a4-117">存取伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="686a4-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="686a4-118">伺服器效能報告是從監視報告首頁存取。</span><span class="sxs-lookup"><span data-stu-id="686a4-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="686a4-119">您可以按一下向下切入[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)的下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="686a4-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="686a4-120">[通話數</span><span class="sxs-lookup"><span data-stu-id="686a4-120">Call volume</span></span>

  - <span data-ttu-id="686a4-121">通話不良百分比</span><span class="sxs-lookup"><span data-stu-id="686a4-121">Poor call percentage</span></span>

<span data-ttu-id="686a4-122">此外，您可以按一下向下切入伺服器媒體品質趨勢報告下列計量：</span><span class="sxs-lookup"><span data-stu-id="686a4-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="686a4-123">Trend</span><span class="sxs-lookup"><span data-stu-id="686a4-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="686a4-124">伺服器效能報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="686a4-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="686a4-125">伺服器效能報告提供了數種方式來篩選資料;例如，您可以篩選網路類型 （從有線連線與從無線連線的呼叫進行的通話） 和存取類型 （內部防火牆與撥打從防火牆外部進行的通話）。</span><span class="sxs-lookup"><span data-stu-id="686a4-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="686a4-126">它是不錯的選項檢視伺服器效能報告進行時使用這些篩選器。</span><span class="sxs-lookup"><span data-stu-id="686a4-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="686a4-127">例如，假設您有中繼伺服器已 3.24%收訊不良通話百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="686a4-128">如果您查看察覺無線通話，該相同的伺服器可能達到 20%收訊不良通話百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="686a4-129">這表示，在伺服器已困難無線通話，因為伺服器已不會察覺有線來電的問題部分遮蔽問題。</span><span class="sxs-lookup"><span data-stu-id="686a4-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="686a4-130">篩選</span><span class="sxs-lookup"><span data-stu-id="686a4-130">Filters</span></span>

<span data-ttu-id="686a4-131">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="686a4-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="686a4-132">例如，伺服器效能報告可讓您進行當作篩選傳回的資料的伺服器類型或網路型別 （也就是有線或無線） 等項目。</span><span class="sxs-lookup"><span data-stu-id="686a4-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="686a4-133">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="686a4-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="686a4-134">在此情況下，是由小時、 日、 週或月群組資料。</span><span class="sxs-lookup"><span data-stu-id="686a4-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="686a4-135">下表列出您可以搭配伺服器效能報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="686a4-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="686a4-136">伺服器效能報告篩選器</span><span class="sxs-lookup"><span data-stu-id="686a4-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686a4-137">名稱</span><span class="sxs-lookup"><span data-stu-id="686a4-137">Name</span></span></th>
<th><span data-ttu-id="686a4-138">描述</span><span class="sxs-lookup"><span data-stu-id="686a4-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686a4-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="686a4-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="686a4-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="686a4-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="686a4-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="686a4-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="686a4-145">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="686a4-145">7/7/2012</span></span></p>
<p><span data-ttu-id="686a4-146">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="686a4-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="686a4-147">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="686a4-147">7/3/2012</span></span></p>
<p><span data-ttu-id="686a4-148">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="686a4-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="686a4-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="686a4-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="686a4-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="686a4-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="686a4-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="686a4-155">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="686a4-155">7/7/2012</span></span></p>
<p><span data-ttu-id="686a4-156">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="686a4-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="686a4-157">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="686a4-157">7/3/2012</span></span></p>
<p><span data-ttu-id="686a4-158">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="686a4-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-159"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-160">會指出應該報告其效能的伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="686a4-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="686a4-161">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="686a4-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="686a4-162">[全部]</span><span class="sxs-lookup"><span data-stu-id="686a4-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="686a4-163">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="686a4-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="686a4-164">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="686a4-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="686a4-165">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="686a4-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-166"><strong>榜尾數量</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-167">若要顯示在每個類別會指出伺服器 （根據其通話不良百分比） 的數目。</span><span class="sxs-lookup"><span data-stu-id="686a4-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="686a4-168">例如，如果您選取<strong>5</strong>然後五個執行效能最差的伺服器會顯示。</span><span class="sxs-lookup"><span data-stu-id="686a4-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="686a4-169">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="686a4-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="686a4-170">[全部]</span><span class="sxs-lookup"><span data-stu-id="686a4-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="686a4-171">5</span><span class="sxs-lookup"><span data-stu-id="686a4-171">5</span></span></p></li>
<li><p><span data-ttu-id="686a4-172">10 </span><span class="sxs-lookup"><span data-stu-id="686a4-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-173"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-p112">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="686a4-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="686a4-176">[全部]</span><span class="sxs-lookup"><span data-stu-id="686a4-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="686a4-177">內部</span><span class="sxs-lookup"><span data-stu-id="686a4-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="686a4-178">External</span><span class="sxs-lookup"><span data-stu-id="686a4-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-179"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-p113">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="686a4-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="686a4-182">[全部]</span><span class="sxs-lookup"><span data-stu-id="686a4-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="686a4-183">有線</span><span class="sxs-lookup"><span data-stu-id="686a4-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="686a4-184">無線</span><span class="sxs-lookup"><span data-stu-id="686a4-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-p114">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="686a4-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="686a4-188">[全部]</span><span class="sxs-lookup"><span data-stu-id="686a4-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="686a4-189">VPN</span><span class="sxs-lookup"><span data-stu-id="686a4-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="686a4-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="686a4-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="686a4-191">計量</span><span class="sxs-lookup"><span data-stu-id="686a4-191">Metrics</span></span>

<span data-ttu-id="686a4-192">下表列出伺服器效能報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="686a4-193">伺服器效能報告計量： 音訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="686a4-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686a4-194">名稱</span><span class="sxs-lookup"><span data-stu-id="686a4-194">Name</span></span></th>
<th><span data-ttu-id="686a4-195">可以排序</span><span class="sxs-lookup"><span data-stu-id="686a4-195">Can Sort On</span></span></th>
<th><span data-ttu-id="686a4-196">描述</span><span class="sxs-lookup"><span data-stu-id="686a4-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686a4-197"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-198">否</span><span class="sxs-lookup"><span data-stu-id="686a4-198">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-199">伺服器名稱] / [IP 位址。</span><span class="sxs-lookup"><span data-stu-id="686a4-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-200"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-201">否</span><span class="sxs-lookup"><span data-stu-id="686a4-201">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-202">撥打的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-203"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-204">否</span><span class="sxs-lookup"><span data-stu-id="686a4-204">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-205">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-205">Total number of calls classified as poor.</span></span> <span data-ttu-id="686a4-206">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="686a4-206">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-207"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-208">是</span><span class="sxs-lookup"><span data-stu-id="686a4-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-209">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="686a4-209">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="686a4-210">100 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="686a4-210">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="686a4-211">高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="686a4-211">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="686a4-212">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="686a4-212">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-213"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-214">是</span><span class="sxs-lookup"><span data-stu-id="686a4-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-215">平均量平均意見分數 (MOS) 降低在通話期間發生。</span><span class="sxs-lookup"><span data-stu-id="686a4-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="686a4-216">為 [高] 的 5.0，降低值可介於 0.0 的低。</span><span class="sxs-lookup"><span data-stu-id="686a4-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="686a4-217">為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="686a4-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="686a4-218">在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="686a4-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="686a4-219">在 Lync Server 中，監控伺服器會使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="686a4-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="686a4-220">高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="686a4-220">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="686a4-221">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-221">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-222"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-223">是</span><span class="sxs-lookup"><span data-stu-id="686a4-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-224">即時傳輸通訊協定 (RTP) 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="686a4-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="686a4-225">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="686a4-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="686a4-226">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-227"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-228">是</span><span class="sxs-lookup"><span data-stu-id="686a4-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-229">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="686a4-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="686a4-230">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-231"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-232">是</span><span class="sxs-lookup"><span data-stu-id="686a4-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-233">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="686a4-233">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="686a4-234">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-234">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-235"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-236">是</span><span class="sxs-lookup"><span data-stu-id="686a4-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-237">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="686a4-237">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="686a4-238">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="686a4-238">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-239"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-240">是</span><span class="sxs-lookup"><span data-stu-id="686a4-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="686a4-241">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="686a4-241">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="686a4-242">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="686a4-242">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="686a4-243">伺服器效能報告計量： 視訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="686a4-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686a4-244">名稱</span><span class="sxs-lookup"><span data-stu-id="686a4-244">Name</span></span></th>
<th><span data-ttu-id="686a4-245">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="686a4-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="686a4-246">描述</span><span class="sxs-lookup"><span data-stu-id="686a4-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686a4-247"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-248">否</span><span class="sxs-lookup"><span data-stu-id="686a4-248">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-249">當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-249">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="686a4-250">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="686a4-250">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="686a4-251">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="686a4-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="686a4-252">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="686a4-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="686a4-253">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="686a4-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="686a4-254">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="686a4-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="686a4-255">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="686a4-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="686a4-256">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="686a4-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="686a4-257">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="686a4-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-258"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-259">否</span><span class="sxs-lookup"><span data-stu-id="686a4-259">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-260">每一種通話類型通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-261"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-262">否</span><span class="sxs-lookup"><span data-stu-id="686a4-262">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-263">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-263">Total number of calls classified as poor.</span></span> <span data-ttu-id="686a4-264">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="686a4-264">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-265"><strong>通話數 （無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-266">否</span><span class="sxs-lookup"><span data-stu-id="686a4-266">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-267">使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-268"><strong>通話數 （VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-269">否</span><span class="sxs-lookup"><span data-stu-id="686a4-269">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-270">使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-271"><strong>通話數 （外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-272">否</span><span class="sxs-lookup"><span data-stu-id="686a4-272">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-273">使用外部連線 （亦即內部網路外部連接） 的通話數。</span><span class="sxs-lookup"><span data-stu-id="686a4-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-274"><strong>平均位元速率 （Kb/秒）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-275">否</span><span class="sxs-lookup"><span data-stu-id="686a4-275">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-276">平均視訊位元速率 （每秒的 kb）。</span><span class="sxs-lookup"><span data-stu-id="686a4-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-277"><strong>低位元速率 %]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-278">否</span><span class="sxs-lookup"><span data-stu-id="686a4-278">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-279">其中的位元速率較低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-280"><strong>輸出封包遺漏</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-281">否</span><span class="sxs-lookup"><span data-stu-id="686a4-281">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-282">輸出封包的即時傳輸通訊協定 (RTP) 封包遺失。</span><span class="sxs-lookup"><span data-stu-id="686a4-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="686a4-283">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="686a4-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="686a4-284">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-285"><strong>[凍結的畫面 %]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-286">否</span><span class="sxs-lookup"><span data-stu-id="686a4-286">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-287">「 凍結 」 畫面的百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-287">Percentage of “frozen” frames.</span></span> <span data-ttu-id="686a4-288">在 [凍結的畫面，影片會停止前進時通話的音訊部分會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="686a4-288">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-289"><strong>輸出平均播放速率]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-290">否</span><span class="sxs-lookup"><span data-stu-id="686a4-290">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-291">通話期間輸出傳輸的平均播放速率。</span><span class="sxs-lookup"><span data-stu-id="686a4-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-292"><strong>輸入的平均播放速率]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-293">否</span><span class="sxs-lookup"><span data-stu-id="686a4-293">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-294">通話期間輸入傳輸的平均播放速率。</span><span class="sxs-lookup"><span data-stu-id="686a4-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-295"><strong>輸入低播放速率 %]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-296">否</span><span class="sxs-lookup"><span data-stu-id="686a4-296">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-297">其中傳入的視訊的位元速率較低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-298"><strong>用戶端健康情況 %]</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="686a4-299">通話期間會指出用戶端裝置的相關健康情況。</span><span class="sxs-lookup"><span data-stu-id="686a4-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="686a4-300">伺服器效能報告計量： 應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="686a4-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="686a4-301">名稱</span><span class="sxs-lookup"><span data-stu-id="686a4-301">Name</span></span></th>
<th><span data-ttu-id="686a4-302">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="686a4-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="686a4-303">描述</span><span class="sxs-lookup"><span data-stu-id="686a4-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="686a4-304"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-305">否</span><span class="sxs-lookup"><span data-stu-id="686a4-305">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-306">當您按一下此項目時，報告就會顯示該類型為基礎的通話的詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-306">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="686a4-307">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="686a4-307">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="686a4-308">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="686a4-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="686a4-309">UC 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="686a4-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="686a4-310">PSTN 會議工作階段</span><span class="sxs-lookup"><span data-stu-id="686a4-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="686a4-311">PSTN 通話： 媒體旁路</span><span class="sxs-lookup"><span data-stu-id="686a4-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="686a4-312">PSTN 通話 （非旁路）： UC Leg</span><span class="sxs-lookup"><span data-stu-id="686a4-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="686a4-313">PSTN 通話 （非旁路）： 閘道 Leg</span><span class="sxs-lookup"><span data-stu-id="686a4-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="686a4-314">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="686a4-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-315"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-316">否</span><span class="sxs-lookup"><span data-stu-id="686a4-316">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-317">每一種通話類型通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-318"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-319">否</span><span class="sxs-lookup"><span data-stu-id="686a4-319">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-320">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-320">Total number of calls classified as poor.</span></span> <span data-ttu-id="686a4-321">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="686a4-321">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-322"><strong>通話數 （無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-323">否</span><span class="sxs-lookup"><span data-stu-id="686a4-323">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-324">使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-325"><strong>通話數 （VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-326">否</span><span class="sxs-lookup"><span data-stu-id="686a4-326">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-327">使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="686a4-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-328"><strong>通話數 （外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-329">否</span><span class="sxs-lookup"><span data-stu-id="686a4-329">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-330">使用外部連線 （亦即內部網路外部連接） 的通話數。</span><span class="sxs-lookup"><span data-stu-id="686a4-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-331"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-332">否</span><span class="sxs-lookup"><span data-stu-id="686a4-332">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-333">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="686a4-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="686a4-334">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="686a4-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-335"><strong>平均相對的其中一種方式</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-336">否</span><span class="sxs-lookup"><span data-stu-id="686a4-336">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-337">平均相對單向之間的延遲兩個媒體端點。</span><span class="sxs-lookup"><span data-stu-id="686a4-337">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="686a4-338">此為單一躍點延遲措施。</span><span class="sxs-lookup"><span data-stu-id="686a4-338">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="686a4-339"><strong>平均 RDP 並排顯示處理延遲</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-340">否</span><span class="sxs-lookup"><span data-stu-id="686a4-340">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-341">平均 RDP 並排檢視工作階段的持續時間內 AS 會議伺服器的處理延遲。</span><span class="sxs-lookup"><span data-stu-id="686a4-341">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="686a4-342">此計量並未涵蓋網路延遲。</span><span class="sxs-lookup"><span data-stu-id="686a4-342">This metric does not cover network latency.</span></span> <span data-ttu-id="686a4-343">高平均會反映檢視經驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="686a4-343">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="686a4-344">負載過重的會議伺服器可能會發生較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="686a4-344">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="686a4-345"><strong>總毀損之並排顯示 %</strong></span><span class="sxs-lookup"><span data-stu-id="686a4-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="686a4-346">否</span><span class="sxs-lookup"><span data-stu-id="686a4-346">No</span></span></p></td>
<td><p><span data-ttu-id="686a4-347">毀損之 RDP 並排顯示的總百分比。</span><span class="sxs-lookup"><span data-stu-id="686a4-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

