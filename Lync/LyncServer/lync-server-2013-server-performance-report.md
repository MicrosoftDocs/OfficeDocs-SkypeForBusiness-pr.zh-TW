---
title: Lync Server 2013：伺服器效能報告
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
ms.openlocfilehash: f8e348882ffa07d1784e62a458455a1ad32a5bbd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510290"
---
# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="95f7a-102">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="95f7a-102">Server Performance Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f7a-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="95f7a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="95f7a-104">「伺服器性能報告」會提供 Microsoft Lync Server 2013 伺服器的清單，該清單已經歷最高百分比的低通話量。</span><span class="sxs-lookup"><span data-stu-id="95f7a-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="95f7a-105">報告依伺服器類型分解伺服器，報告下列類型的個別統計資料：</span><span class="sxs-lookup"><span data-stu-id="95f7a-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="95f7a-106">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="95f7a-106">Mediation Server</span></span>

  - <span data-ttu-id="95f7a-107">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="95f7a-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="95f7a-108">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="95f7a-108">A/V Edge Server</span></span>

  - <span data-ttu-id="95f7a-109">閘道 (轉送伺服器) </span><span class="sxs-lookup"><span data-stu-id="95f7a-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="95f7a-110">閘道 (轉送伺服器旁路) </span><span class="sxs-lookup"><span data-stu-id="95f7a-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="95f7a-111">影片 (包含 A/V 會議伺服器及 A/V Edge server 的影片度量) </span><span class="sxs-lookup"><span data-stu-id="95f7a-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="95f7a-112">應用程式共用 (包括 A/V 會議伺服器和 A/V Edge server 的應用程式共用計量，) </span><span class="sxs-lookup"><span data-stu-id="95f7a-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="95f7a-113">請務必注意，此報告中顯示的排名為相對排名。</span><span class="sxs-lookup"><span data-stu-id="95f7a-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="95f7a-114">例如，假設您的最壞執行伺服器在其1000的來電中有一個不佳的呼叫。</span><span class="sxs-lookup"><span data-stu-id="95f7a-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="95f7a-115">這是1% 的可接受百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="95f7a-116">不過，如果這是執行最壞的伺服器，也就是 (也就是說，如果其他所有伺服器的呼叫百分比不佳，甚至低於 0.1% ) ，則該伺服器仍會出現在伺服器效能報告上。</span><span class="sxs-lookup"><span data-stu-id="95f7a-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="95f7a-117">存取伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="95f7a-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="95f7a-118">伺服器效能報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="95f7a-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="95f7a-119">您可以按一下下列其中一個計量，以深入瞭解 [Lync Server 2013 中的通話清單報告](lync-server-2013-call-list-report.md) ：</span><span class="sxs-lookup"><span data-stu-id="95f7a-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="95f7a-120">通話數量</span><span class="sxs-lookup"><span data-stu-id="95f7a-120">Call volume</span></span>

  - <span data-ttu-id="95f7a-121">通話百分比不佳</span><span class="sxs-lookup"><span data-stu-id="95f7a-121">Poor call percentage</span></span>

<span data-ttu-id="95f7a-122">此外，您可以按一下下列度量，向下流覽至 [伺服器媒體質量趨勢] 報告：</span><span class="sxs-lookup"><span data-stu-id="95f7a-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="95f7a-123">Trend</span><span class="sxs-lookup"><span data-stu-id="95f7a-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="95f7a-124">伺服器效能報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="95f7a-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="95f7a-125">伺服器效能報告提供了多種篩選資料的方式;例如，您可以篩選網路類型 (來自有線連線的呼叫，以及從防火牆內部撥打的撥號類型) 和 access 類型 (呼叫從防火牆內部所撥打的呼叫，而不是來自防火牆) 以外的呼叫。</span><span class="sxs-lookup"><span data-stu-id="95f7a-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="95f7a-126">在查看伺服器效能報告以利用這些篩選器時，是一個不錯的主意。</span><span class="sxs-lookup"><span data-stu-id="95f7a-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="95f7a-127">例如，假設您的轉送伺服器的呼叫百分比不佳，3.24%。</span><span class="sxs-lookup"><span data-stu-id="95f7a-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="95f7a-128">如果您只是在無線通話時查看，則相同的伺服器可能會有接近20% 的低通話百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="95f7a-129">這表示伺服器在無線通話時發生困難，因為伺服器沒有有線通話的問題，所以發生部分掩蓋問題。</span><span class="sxs-lookup"><span data-stu-id="95f7a-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="95f7a-130">篩選</span><span class="sxs-lookup"><span data-stu-id="95f7a-130">Filters</span></span>

<span data-ttu-id="95f7a-131">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="95f7a-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="95f7a-132">例如，伺服器效能報告可讓您執行下列作業：依伺服器類型篩選傳回的資料，或透過網路類型 (（即有線或無線) ）。</span><span class="sxs-lookup"><span data-stu-id="95f7a-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="95f7a-133">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="95f7a-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="95f7a-134">在此情況下，資料會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="95f7a-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="95f7a-135">下表列出您可以搭配伺服器效能報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="95f7a-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="95f7a-136">伺服器效能報告篩選器</span><span class="sxs-lookup"><span data-stu-id="95f7a-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f7a-137">名稱</span><span class="sxs-lookup"><span data-stu-id="95f7a-137">Name</span></span></th>
<th><span data-ttu-id="95f7a-138">描述</span><span class="sxs-lookup"><span data-stu-id="95f7a-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-139"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="95f7a-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="95f7a-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="95f7a-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="95f7a-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="95f7a-145">7/7/2012</span></span></p>
<p><span data-ttu-id="95f7a-146">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="95f7a-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="95f7a-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="95f7a-147">7/3/2012</span></span></p>
<p><span data-ttu-id="95f7a-148">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="95f7a-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-149"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="95f7a-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="95f7a-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="95f7a-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="95f7a-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="95f7a-155">7/7/2012</span></span></p>
<p><span data-ttu-id="95f7a-156">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="95f7a-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="95f7a-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="95f7a-157">7/3/2012</span></span></p>
<p><span data-ttu-id="95f7a-158">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="95f7a-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-159"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-160">會指出應報告其效能的伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="95f7a-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="95f7a-161">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95f7a-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="95f7a-162">一切</span><span class="sxs-lookup"><span data-stu-id="95f7a-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="95f7a-163">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="95f7a-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="95f7a-164">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="95f7a-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="95f7a-165">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="95f7a-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-166"><strong>前 N 個</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-167">根據每個類別中所要顯示的低通話百分比) 指出 (的伺服器數目。</span><span class="sxs-lookup"><span data-stu-id="95f7a-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="95f7a-168">例如，如果您選取 [ <strong>5</strong> ]，則會顯示五個 poorest 執行中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="95f7a-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="95f7a-169">請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95f7a-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="95f7a-170">一切</span><span class="sxs-lookup"><span data-stu-id="95f7a-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="95f7a-171">5 </span><span class="sxs-lookup"><span data-stu-id="95f7a-171">5</span></span></p></li>
<li><p><span data-ttu-id="95f7a-172">10 </span><span class="sxs-lookup"><span data-stu-id="95f7a-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-173"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-p112">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p112">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="95f7a-176">一切</span><span class="sxs-lookup"><span data-stu-id="95f7a-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="95f7a-177">內部</span><span class="sxs-lookup"><span data-stu-id="95f7a-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="95f7a-178">外部</span><span class="sxs-lookup"><span data-stu-id="95f7a-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-179"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-p113">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p113">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="95f7a-182">一切</span><span class="sxs-lookup"><span data-stu-id="95f7a-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="95f7a-183">有線</span><span class="sxs-lookup"><span data-stu-id="95f7a-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="95f7a-184">無線</span><span class="sxs-lookup"><span data-stu-id="95f7a-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-185"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-p114">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="95f7a-p114">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="95f7a-188">一切</span><span class="sxs-lookup"><span data-stu-id="95f7a-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="95f7a-189">VPN</span><span class="sxs-lookup"><span data-stu-id="95f7a-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="95f7a-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="95f7a-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="95f7a-191">指標</span><span class="sxs-lookup"><span data-stu-id="95f7a-191">Metrics</span></span>

<span data-ttu-id="95f7a-192">下表列出伺服器效能報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="95f7a-193">伺服器效能報告計量：音訊通話摘要</span><span class="sxs-lookup"><span data-stu-id="95f7a-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f7a-194">姓名</span><span class="sxs-lookup"><span data-stu-id="95f7a-194">Name</span></span></th>
<th><span data-ttu-id="95f7a-195">可以排序</span><span class="sxs-lookup"><span data-stu-id="95f7a-195">Can Sort On</span></span></th>
<th><span data-ttu-id="95f7a-196">描述</span><span class="sxs-lookup"><span data-stu-id="95f7a-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-197"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-198">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-198">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-199">伺服器的名稱/IP 位址。</span><span class="sxs-lookup"><span data-stu-id="95f7a-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-200"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-201">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-201">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-202">撥打的通話總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-203"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-204">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-204">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-205">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-205">Total number of calls classified as poor.</span></span> <span data-ttu-id="95f7a-206">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="95f7a-206">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-207"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-208">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-209">即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。</span><span class="sxs-lookup"><span data-stu-id="95f7a-209">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="95f7a-210">在100毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="95f7a-210">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="95f7a-211">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="95f7a-211">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="95f7a-212">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="95f7a-212">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-213"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-214">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-215">通話期間 (MOS) 效能的平均平均觀點量。</span><span class="sxs-lookup"><span data-stu-id="95f7a-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="95f7a-216">降級值的範圍從低0.0 到高5.0。</span><span class="sxs-lookup"><span data-stu-id="95f7a-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="95f7a-217">值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="95f7a-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="95f7a-218">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="95f7a-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="95f7a-219">在 Lync Server 中，監控伺服器會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="95f7a-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="95f7a-220">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="95f7a-220">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="95f7a-221">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="95f7a-221">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-222"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-223">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-224">即時傳輸通訊協定 (RTP) 封包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="95f7a-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="95f7a-225">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="95f7a-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="95f7a-226">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="95f7a-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-227"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-228">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-229">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="95f7a-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="95f7a-230"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-231"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-232">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-233">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-233">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="95f7a-234"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-234">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-235"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-236">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-237">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-237">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="95f7a-238"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="95f7a-238">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-239"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-240">是</span><span class="sxs-lookup"><span data-stu-id="95f7a-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f7a-241">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-241">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="95f7a-242"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="95f7a-242">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="95f7a-243">伺服器效能報告計量：影片通話摘要</span><span class="sxs-lookup"><span data-stu-id="95f7a-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f7a-244">姓名</span><span class="sxs-lookup"><span data-stu-id="95f7a-244">Name</span></span></th>
<th><span data-ttu-id="95f7a-245">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="95f7a-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="95f7a-246">描述</span><span class="sxs-lookup"><span data-stu-id="95f7a-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-247"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-248">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-248">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-249">當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-249">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="95f7a-250">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="95f7a-250">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="95f7a-251">UC Peer-to-Peer 通話</span><span class="sxs-lookup"><span data-stu-id="95f7a-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="95f7a-252">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="95f7a-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="95f7a-253">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="95f7a-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="95f7a-254">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="95f7a-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="95f7a-255">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="95f7a-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="95f7a-256">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="95f7a-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="95f7a-257">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="95f7a-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-258"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-259">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-259">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-260">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-261"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-262">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-262">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-263">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-263">Total number of calls classified as poor.</span></span> <span data-ttu-id="95f7a-264">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="95f7a-264">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-265"><strong> (無線通話的電話量) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-266">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-266">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-267">使用無線連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-268"><strong> (VPN 呼叫的通話量) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-269">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-269">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-270">使用 VPN 連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-271"><strong>通話量 (外部呼叫) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-272">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-272">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-273">使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</span><span class="sxs-lookup"><span data-stu-id="95f7a-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-274"><strong>平均位元速率 (Kb/s) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-275">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-275">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-276">平均影片位元速率 (以每秒千位數) 。</span><span class="sxs-lookup"><span data-stu-id="95f7a-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-277"><strong>低位率%</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-278">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-278">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-279">位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-280"><strong>輸出封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-281">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-281">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-282">Real-Time 傳輸通訊協定 (RTP) 輸出封包遺失。</span><span class="sxs-lookup"><span data-stu-id="95f7a-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="95f7a-283">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="95f7a-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="95f7a-284">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="95f7a-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-285"><strong>凍結的圖文框%</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-286">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-286">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-287">「凍結」框架的百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-287">Percentage of “frozen” frames.</span></span> <span data-ttu-id="95f7a-288">在凍結的框架中，當繼續通話的音訊部分時，影片會停止向前。</span><span class="sxs-lookup"><span data-stu-id="95f7a-288">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-289"><strong>輸出平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-290">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-290">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-291">通話期間輸出傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="95f7a-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-292"><strong>輸入平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-293">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-293">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-294">通話期間傳入傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="95f7a-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-295"><strong>輸入低框架速率%</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-296">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-296">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-297">傳入影片的位元速率很低之通話的百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-298"><strong>用戶端狀況%</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="95f7a-299">會指出通話期間用戶端裝置的相對健康情況。</span><span class="sxs-lookup"><span data-stu-id="95f7a-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="95f7a-300">伺服器效能報告計量：應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="95f7a-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f7a-301">姓名</span><span class="sxs-lookup"><span data-stu-id="95f7a-301">Name</span></span></th>
<th><span data-ttu-id="95f7a-302">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="95f7a-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="95f7a-303">描述</span><span class="sxs-lookup"><span data-stu-id="95f7a-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-304"><strong>通話類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-305">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-305">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-306">當您按一下此專案時，報告會顯示以該類型為基礎之通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-306">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="95f7a-307">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="95f7a-307">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="95f7a-308">UC Peer-to-Peer 通話</span><span class="sxs-lookup"><span data-stu-id="95f7a-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="95f7a-309">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="95f7a-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="95f7a-310">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="95f7a-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="95f7a-311">PSTN 通話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="95f7a-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="95f7a-312">PSTN 通話 (Non-Bypass) ： UC 腿</span><span class="sxs-lookup"><span data-stu-id="95f7a-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="95f7a-313">PSTN 通話 (Non-Bypass) ：閘道腿</span><span class="sxs-lookup"><span data-stu-id="95f7a-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="95f7a-314">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="95f7a-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-315"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-316">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-316">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-317">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-318"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-319">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-319">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-320">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-320">Total number of calls classified as poor.</span></span> <span data-ttu-id="95f7a-321">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="95f7a-321">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-322"><strong> (無線通話的電話量) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-323">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-323">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-324">使用無線連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-325"><strong> (VPN 呼叫的通話量) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-326">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-326">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-327">使用 VPN 連線的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="95f7a-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-328"><strong>通話量 (外部呼叫) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-329">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-329">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-330">使用外部連線 (的呼叫數目，也就是內部網路) 以外的連線。</span><span class="sxs-lookup"><span data-stu-id="95f7a-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-331"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-332">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-332">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-333">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="95f7a-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="95f7a-334"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="95f7a-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-335"><strong>平均相對單向方式</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-336">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-336">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-337">兩個媒體端點之間的平均相對單向延遲。</span><span class="sxs-lookup"><span data-stu-id="95f7a-337">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="95f7a-338">此為單一躍點延遲措施。</span><span class="sxs-lookup"><span data-stu-id="95f7a-338">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f7a-339"><strong>平均 .RDP 磚處理延遲</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-340">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-340">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-341">在查看會話期間，AS 會議服務器中的平均 RDP 磚處理延遲。</span><span class="sxs-lookup"><span data-stu-id="95f7a-341">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="95f7a-342">此計量並未涵蓋網路延遲。</span><span class="sxs-lookup"><span data-stu-id="95f7a-342">This metric does not cover network latency.</span></span> <span data-ttu-id="95f7a-343">高平均會反映檢視經驗中較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="95f7a-343">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="95f7a-344">負載過重的會議伺服器可能會發生較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="95f7a-344">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f7a-345"><strong>Spoiled 磚的總數%</strong></span><span class="sxs-lookup"><span data-stu-id="95f7a-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="95f7a-346">否</span><span class="sxs-lookup"><span data-stu-id="95f7a-346">No</span></span></p></td>
<td><p><span data-ttu-id="95f7a-347">Spoiled RDP 磚的總百分比。</span><span class="sxs-lookup"><span data-stu-id="95f7a-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

