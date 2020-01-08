---
title: Lync Server 2013：伺服器效能報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5a08104f33fc07d6a0ec1c3241a7f14fa1227a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976840"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a><span data-ttu-id="d49be-102">Lync Server 2013 中的伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="d49be-102">Server Performance Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d49be-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d49be-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d49be-104">伺服器效能報告會提供 Microsoft Lync Server 2013 伺服器的清單，這些伺服器已經歷最高百分比的不佳通話。</span><span class="sxs-lookup"><span data-stu-id="d49be-104">The Server Performance Report provides a list of Microsoft Lync Server 2013 servers that have experienced the highest-percentage of poor calls.</span></span> <span data-ttu-id="d49be-105">報告會依據伺服器類型來細分伺服器，並報告個別的統計資料，以進行下列類型：</span><span class="sxs-lookup"><span data-stu-id="d49be-105">The report breaks down servers by server type, reporting separate statistics for the following types:</span></span>

  - <span data-ttu-id="d49be-106">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-106">Mediation Server</span></span>

  - <span data-ttu-id="d49be-107">A/V 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-107">A/V Conferencing Server</span></span>

  - <span data-ttu-id="d49be-108">A/V 邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-108">A/V Edge Server</span></span>

  - <span data-ttu-id="d49be-109">閘道（中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="d49be-109">Gateway (Mediation Server)</span></span>

  - <span data-ttu-id="d49be-110">閘道（中繼伺服器旁路）</span><span class="sxs-lookup"><span data-stu-id="d49be-110">Gateway (Mediation Server bypass)</span></span>

  - <span data-ttu-id="d49be-111">影片（包括 A/V 會議伺服器與 A/V 邊緣伺服器的視頻指標）</span><span class="sxs-lookup"><span data-stu-id="d49be-111">Video (including video metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

  - <span data-ttu-id="d49be-112">應用程式共用（包括 A/V 會議伺服器與 A/V 邊緣伺服器的應用程式共用指標）</span><span class="sxs-lookup"><span data-stu-id="d49be-112">Application Sharing (including application sharing metrics for A/V Conferencing servers and A/V Edge servers)</span></span>

<span data-ttu-id="d49be-113">請務必注意，此報告中顯示的排名是相對排名。</span><span class="sxs-lookup"><span data-stu-id="d49be-113">It’s important to note that the ranking shown in this report as relative rankings.</span></span> <span data-ttu-id="d49be-114">例如，假設您最糟糕的伺服器在其1000的撥入呼叫中有一個不佳的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d49be-114">For example, suppose your worst-performing server had one poor call among its 1,000 placed calls.</span></span> <span data-ttu-id="d49be-115">這是一個大於-可接受的百分比。1%。</span><span class="sxs-lookup"><span data-stu-id="d49be-115">That's a more-than-acceptable percentage of .1%.</span></span> <span data-ttu-id="d49be-116">不過，如果這是您所擁有的最差執行伺服器（也就是如果所有其他伺服器的通話百分比都不是0.1%），則該伺服器仍會出現在 [伺服器效能] 報告中。</span><span class="sxs-lookup"><span data-stu-id="d49be-116">However, if that's the worst-performing server you have (that is, if all your other servers have a poor call percentage even lower than .1%), then that server will still appear on the Server Performance Report.</span></span>

<div>

## <a name="accessing-the-server-performance-report"></a><span data-ttu-id="d49be-117">存取伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="d49be-117">Accessing the Server Performance Report</span></span>

<span data-ttu-id="d49be-118">伺服器效能報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="d49be-118">The Server Performance Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="d49be-119">您可以按一下下列其中一個度量，[在 Lync Server 2013 中](lync-server-2013-call-list-report.md)向下切入至 [通話清單] 報告：</span><span class="sxs-lookup"><span data-stu-id="d49be-119">You can drill down to the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="d49be-120">通話量</span><span class="sxs-lookup"><span data-stu-id="d49be-120">Call volume</span></span>

  - <span data-ttu-id="d49be-121">通話百分比太差</span><span class="sxs-lookup"><span data-stu-id="d49be-121">Poor call percentage</span></span>

<span data-ttu-id="d49be-122">此外，您可以按一下以下度量，向下切入 [伺服器媒體質量趨勢] 報告：</span><span class="sxs-lookup"><span data-stu-id="d49be-122">In addition, you can drill down to the Server Media Quality Trend Report by clicking the following metric:</span></span>

  - <span data-ttu-id="d49be-123">傾向</span><span class="sxs-lookup"><span data-stu-id="d49be-123">Trend</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a><span data-ttu-id="d49be-124">充分利用伺服器效能報告</span><span class="sxs-lookup"><span data-stu-id="d49be-124">Making the Best Use of the Server Performance Report</span></span>

<span data-ttu-id="d49be-125">伺服器效能報告提供了多種篩選資料的方式;例如，您可以篩選網路類型（從有線連線所撥打的通話，以及從無線連線撥打的通話），以及存取類型（從防火牆外的呼叫撥打到防火牆以外的通話）。</span><span class="sxs-lookup"><span data-stu-id="d49be-125">The Server Performance Report provides a number of ways to filter data; for example, you can filter on network type (calls made from a wired connection vs. calls made from a wireless connection) and access type (calls made from inside the firewall vs. calls made from outside the firewall).</span></span> <span data-ttu-id="d49be-126">當您查看伺服器效能報告以使用這些篩選器時，這是個不錯的做法。</span><span class="sxs-lookup"><span data-stu-id="d49be-126">It's a good idea when viewing the server performance report to make use of these filters.</span></span> <span data-ttu-id="d49be-127">例如，假設您的中繼伺服器的通話百分比較差3.24%。</span><span class="sxs-lookup"><span data-stu-id="d49be-127">For example, suppose you have a Mediation Server that has a poor call percentage of 3.24%.</span></span> <span data-ttu-id="d49be-128">如果您只查看無線通話，那台伺服器可能會有接近20% 的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="d49be-128">If you look solely at wireless calls, that same server might have a poor call percentage approaching 20%.</span></span> <span data-ttu-id="d49be-129">這表示伺服器難以進行無線通話，因為伺服器沒有有線通話的問題，所以這個問題遭到了一部分遮住。</span><span class="sxs-lookup"><span data-stu-id="d49be-129">That means that the server was having difficulty with wireless calls, a problem that is partially obscured because the server was not having problems with wired calls.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d49be-130">濾鏡</span><span class="sxs-lookup"><span data-stu-id="d49be-130">Filters</span></span>

<span data-ttu-id="d49be-131">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="d49be-131">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d49be-132">例如，伺服器效能報告可讓您執行下列動作：依伺服器類型或網路類型（也就是有線或無線）篩選傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="d49be-132">For example, the Server Performance Report enables you to do such things as filter the returned data by server type or by network type (that is, wired or wireless).</span></span> <span data-ttu-id="d49be-133">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="d49be-133">You can also choose how data should be grouped.</span></span> <span data-ttu-id="d49be-134">在這種情況下，資料會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="d49be-134">In this case, data is grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="d49be-135">下表列出您可與 [伺服器效能] 報告搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="d49be-135">The following table lists the filters that you can use with the Server Performance Report.</span></span>

### <a name="server-performance-report-filters"></a><span data-ttu-id="d49be-136">伺服器效能報告篩選器</span><span class="sxs-lookup"><span data-stu-id="d49be-136">Server Performance Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49be-137">名稱</span><span class="sxs-lookup"><span data-stu-id="d49be-137">Name</span></span></th>
<th><span data-ttu-id="d49be-138">描述</span><span class="sxs-lookup"><span data-stu-id="d49be-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49be-139"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-139"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-140">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="d49be-140">Start date/time for the time range.</span></span> <span data-ttu-id="d49be-141">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d49be-141">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d49be-142">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d49be-142">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d49be-143">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="d49be-143">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d49be-144">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d49be-144">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d49be-145">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d49be-145">7/7/2012</span></span></p>
<p><span data-ttu-id="d49be-146">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d49be-146">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d49be-147">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d49be-147">7/3/2012</span></span></p>
<p><span data-ttu-id="d49be-148">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d49be-148">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-149"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-149"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-150">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="d49be-150">End date/time for the time range.</span></span> <span data-ttu-id="d49be-151">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d49be-151">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d49be-152">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="d49be-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d49be-153">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="d49be-153">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d49be-154">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="d49be-154">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d49be-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d49be-155">7/7/2012</span></span></p>
<p><span data-ttu-id="d49be-156">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="d49be-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d49be-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d49be-157">7/3/2012</span></span></p>
<p><span data-ttu-id="d49be-158">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="d49be-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-159"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-159"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-160">指示應報告其效能的伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="d49be-160">Indicates the type of server whose performance should be reported.</span></span> <span data-ttu-id="d49be-161">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d49be-161">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d49be-162">同時</span><span class="sxs-lookup"><span data-stu-id="d49be-162">[All]</span></span></p></li>
<li><p><span data-ttu-id="d49be-163">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-163">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="d49be-164">A/V 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-164">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="d49be-165">A/V 邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="d49be-165">A/V Edge Server</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-166"><strong>前 N 個</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-166"><strong>Top N</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-167">指出每個類別中要顯示的伺服器數量（根據其不佳的通話百分比）。</span><span class="sxs-lookup"><span data-stu-id="d49be-167">Indicates the number of servers (based on their poor call percentage) to be displayed in each category.</span></span> <span data-ttu-id="d49be-168">例如，如果您選取 [ <strong>5</strong> ]，則會顯示五個 poorest 執行中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d49be-168">For example, if you select <strong>5</strong> then the five poorest-performing servers are displayed.</span></span> <span data-ttu-id="d49be-169">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d49be-169">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d49be-170">同時</span><span class="sxs-lookup"><span data-stu-id="d49be-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="d49be-171">500</span><span class="sxs-lookup"><span data-stu-id="d49be-171">5</span></span></p></li>
<li><p><span data-ttu-id="d49be-172">第</span><span class="sxs-lookup"><span data-stu-id="d49be-172">10</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-173"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-173"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-174">指出撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="d49be-174">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="d49be-175">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d49be-175">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d49be-176">同時</span><span class="sxs-lookup"><span data-stu-id="d49be-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="d49be-177">內部</span><span class="sxs-lookup"><span data-stu-id="d49be-177">Internal</span></span></p></li>
<li><p><span data-ttu-id="d49be-178">外來</span><span class="sxs-lookup"><span data-stu-id="d49be-178">External</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-179"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-180">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="d49be-180">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="d49be-181">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d49be-181">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d49be-182">同時</span><span class="sxs-lookup"><span data-stu-id="d49be-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="d49be-183">有線</span><span class="sxs-lookup"><span data-stu-id="d49be-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="d49be-184">無線</span><span class="sxs-lookup"><span data-stu-id="d49be-184">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-185"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-185"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-186">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="d49be-186">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="d49be-187">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d49be-187">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="d49be-188">同時</span><span class="sxs-lookup"><span data-stu-id="d49be-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="d49be-189">點對點</span><span class="sxs-lookup"><span data-stu-id="d49be-189">VPN</span></span></p></li>
<li><p><span data-ttu-id="d49be-190">非 VPN</span><span class="sxs-lookup"><span data-stu-id="d49be-190">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d49be-191">指標</span><span class="sxs-lookup"><span data-stu-id="d49be-191">Metrics</span></span>

<span data-ttu-id="d49be-192">下表列出 [伺服器效能] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-192">The following table lists the information provided in the Server Performance Report.</span></span>

### <a name="server-performance-report-metrics-audio-call-summary"></a><span data-ttu-id="d49be-193">伺服器效能報告度量值：語音通話摘要</span><span class="sxs-lookup"><span data-stu-id="d49be-193">Server Performance Report Metrics: Audio Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49be-194">名稱</span><span class="sxs-lookup"><span data-stu-id="d49be-194">Name</span></span></th>
<th><span data-ttu-id="d49be-195">可以排序</span><span class="sxs-lookup"><span data-stu-id="d49be-195">Can Sort On</span></span></th>
<th><span data-ttu-id="d49be-196">描述</span><span class="sxs-lookup"><span data-stu-id="d49be-196">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49be-197"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-197"><strong>Server</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-198">否</span><span class="sxs-lookup"><span data-stu-id="d49be-198">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-199">伺服器的名稱/IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d49be-199">Name/IP address of the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-200"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-200"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-201">否</span><span class="sxs-lookup"><span data-stu-id="d49be-201">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-202">撥打的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-202">Total number of calls made.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-203"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-203"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-204">否</span><span class="sxs-lookup"><span data-stu-id="d49be-204">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-205">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-205">Total number of calls classified as poor.</span></span> <span data-ttu-id="d49be-206">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d49be-206">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-207"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-207"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-208">是</span><span class="sxs-lookup"><span data-stu-id="d49be-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-209">即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="d49be-209">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="d49be-210">100毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="d49be-210">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d49be-211">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="d49be-211">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="d49be-212">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="d49be-212">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-213"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-213"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-214">是</span><span class="sxs-lookup"><span data-stu-id="d49be-214">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-215">通話期間平均觀念得分（MOS）的平均數量下降。</span><span class="sxs-lookup"><span data-stu-id="d49be-215">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="d49be-216">降級值的範圍可從低0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="d49be-216">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="d49be-217">0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="d49be-217">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="d49be-218">過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。</span><span class="sxs-lookup"><span data-stu-id="d49be-218">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="d49be-219">在 Lync Server 中，監視伺服器會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="d49be-219">In Lync Server, the Monitoring Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="d49be-220">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="d49be-220">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="d49be-221">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-221">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-222"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-222"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-223">是</span><span class="sxs-lookup"><span data-stu-id="d49be-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-224">即時傳輸通訊協定（RTP）資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="d49be-224">Average rate of real-time transport protocol (RTP) packet loss.</span></span> <span data-ttu-id="d49be-225">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="d49be-225">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="d49be-226">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="d49be-226">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-227"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-227"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-228">是</span><span class="sxs-lookup"><span data-stu-id="d49be-228">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-229">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="d49be-229">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d49be-230">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-230">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-231"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-231"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-232">是</span><span class="sxs-lookup"><span data-stu-id="d49be-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-233">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="d49be-233">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="d49be-234">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="d49be-234">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-235"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-235"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-236">是</span><span class="sxs-lookup"><span data-stu-id="d49be-236">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-237">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="d49be-237">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="d49be-238">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="d49be-238">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-239"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-239"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-240">是</span><span class="sxs-lookup"><span data-stu-id="d49be-240">Yes</span></span></p></td>
<td><p><span data-ttu-id="d49be-241">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-241">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="d49be-242">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="d49be-242">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a><span data-ttu-id="d49be-243">伺服器效能報告度量值：影片通話摘要</span><span class="sxs-lookup"><span data-stu-id="d49be-243">Server Performance Report Metrics: Video Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49be-244">名稱</span><span class="sxs-lookup"><span data-stu-id="d49be-244">Name</span></span></th>
<th><span data-ttu-id="d49be-245">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d49be-245">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d49be-246">描述</span><span class="sxs-lookup"><span data-stu-id="d49be-246">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49be-247"><strong>呼叫類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-247"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-248">否</span><span class="sxs-lookup"><span data-stu-id="d49be-248">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-249">當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-249">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="d49be-250">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="d49be-250">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="d49be-251">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="d49be-251">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="d49be-252">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="d49be-252">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="d49be-253">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="d49be-253">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="d49be-254">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="d49be-254">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="d49be-255">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="d49be-255">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="d49be-256">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="d49be-256">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="d49be-257">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="d49be-257">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-258"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-258"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-259">否</span><span class="sxs-lookup"><span data-stu-id="d49be-259">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-260">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-260">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-261"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-261"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-262">否</span><span class="sxs-lookup"><span data-stu-id="d49be-262">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-263">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-263">Total number of calls classified as poor.</span></span> <span data-ttu-id="d49be-264">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d49be-264">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-265"><strong>通話音量（無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-265"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-266">否</span><span class="sxs-lookup"><span data-stu-id="d49be-266">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-267">已使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-267">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-268"><strong>通話量（VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-268"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-269">否</span><span class="sxs-lookup"><span data-stu-id="d49be-269">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-270">已使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-270">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-271"><strong>通話音量（外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-271"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-272">否</span><span class="sxs-lookup"><span data-stu-id="d49be-272">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-273">使用外部連線的呼叫數量（也就是內部網路以外的連線）。</span><span class="sxs-lookup"><span data-stu-id="d49be-273">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-274"><strong>平均比對率（Kbits/s）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-274"><strong>Avg bit-rate (Kbits/s)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-275">否</span><span class="sxs-lookup"><span data-stu-id="d49be-275">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-276">平均視頻位元速率（以千位數/秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="d49be-276">Average video bit rate (in kilobits per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-277"><strong>低位比率%</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-277"><strong>Low bit-rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-278">否</span><span class="sxs-lookup"><span data-stu-id="d49be-278">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-279">位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="d49be-279">Percentage of the call where the bit rate was low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-280"><strong>輸出資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-280"><strong>Outbound packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-281">否</span><span class="sxs-lookup"><span data-stu-id="d49be-281">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-282">輸出資料包的即時傳輸通訊協定（RTP）資料包遺失。</span><span class="sxs-lookup"><span data-stu-id="d49be-282">Real-Time Transport Protocol (RTP) packet loss for outbound packets.</span></span> <span data-ttu-id="d49be-283">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="d49be-283">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="d49be-284">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="d49be-284">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-285"><strong>凍結的畫面%</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-285"><strong>Frozen frame %</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-286">否</span><span class="sxs-lookup"><span data-stu-id="d49be-286">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-287">「凍結」畫面的百分比。</span><span class="sxs-lookup"><span data-stu-id="d49be-287">Percentage of “frozen” frames.</span></span> <span data-ttu-id="d49be-288">在凍結的畫面中，當通話的音訊部分繼續時，影片會停止向前進行。</span><span class="sxs-lookup"><span data-stu-id="d49be-288">In a frozen frame, the video stops advancing while the audio portion of the call continues.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-289"><strong>輸出平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-289"><strong>Outbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-290">否</span><span class="sxs-lookup"><span data-stu-id="d49be-290">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-291">通話期間輸出傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="d49be-291">Average frame rate for outbound transmissions during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-292"><strong>輸入平均畫面播放速率</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-292"><strong>Inbound avg frame rate</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-293">否</span><span class="sxs-lookup"><span data-stu-id="d49be-293">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-294">通話期間內送傳輸的平均畫面播放速率。</span><span class="sxs-lookup"><span data-stu-id="d49be-294">Average frame rate for incoming transmissions during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-295"><strong>輸入低畫面播放速率%</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-295"><strong>Inbound low frame rate %</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-296">否</span><span class="sxs-lookup"><span data-stu-id="d49be-296">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-297">傳入影片的位元速率低的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="d49be-297">Percentage of the call where the bit rate for incoming video was low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-298"><strong>用戶端健康情況%</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-298"><strong>Client health %</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d49be-299">表示通話期間用戶端裝置的相對健康情況。</span><span class="sxs-lookup"><span data-stu-id="d49be-299">Indicates the relative health of the client device during the call.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a><span data-ttu-id="d49be-300">伺服器效能報告規格：應用程式共用通話摘要</span><span class="sxs-lookup"><span data-stu-id="d49be-300">Server Performance Report Metrics: Application Sharing Call Summary</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d49be-301">名稱</span><span class="sxs-lookup"><span data-stu-id="d49be-301">Name</span></span></th>
<th><span data-ttu-id="d49be-302">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="d49be-302">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d49be-303">描述</span><span class="sxs-lookup"><span data-stu-id="d49be-303">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d49be-304"><strong>呼叫類型/端點類型</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-304"><strong>Call type/Endpoint type</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-305">否</span><span class="sxs-lookup"><span data-stu-id="d49be-305">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-306">當您按一下此專案時，報告會根據該類型顯示通話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-306">When you click this item, the report shows detailed information about calls based on that type.</span></span> <span data-ttu-id="d49be-307">通話類型包括：</span><span class="sxs-lookup"><span data-stu-id="d49be-307">Call types include:</span></span></p>
<ul>
<li><p><span data-ttu-id="d49be-308">UC 對等通話</span><span class="sxs-lookup"><span data-stu-id="d49be-308">UC Peer-to-Peer Calls</span></span></p></li>
<li><p><span data-ttu-id="d49be-309">UC 會議會話</span><span class="sxs-lookup"><span data-stu-id="d49be-309">UC Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="d49be-310">PSTN 會議會話</span><span class="sxs-lookup"><span data-stu-id="d49be-310">PSTN Conference Sessions</span></span></p></li>
<li><p><span data-ttu-id="d49be-311">PSTN 電話：媒體旁路</span><span class="sxs-lookup"><span data-stu-id="d49be-311">PSTN Calls: Media Bypass</span></span></p></li>
<li><p><span data-ttu-id="d49be-312">PSTN 通話（非旁路）： UC 腿</span><span class="sxs-lookup"><span data-stu-id="d49be-312">PSTN Calls (Non-Bypass): UC Leg</span></span></p></li>
<li><p><span data-ttu-id="d49be-313">PSTN 通話（非旁路）：閘道腿</span><span class="sxs-lookup"><span data-stu-id="d49be-313">PSTN Calls (Non-Bypass): Gateway Leg</span></span></p></li>
<li><p><span data-ttu-id="d49be-314">其他通話類型</span><span class="sxs-lookup"><span data-stu-id="d49be-314">Other Call Types</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-315"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-315"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-316">否</span><span class="sxs-lookup"><span data-stu-id="d49be-316">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-317">每個通話類型的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-317">Total number of calls per call type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-318"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-318"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-319">否</span><span class="sxs-lookup"><span data-stu-id="d49be-319">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-320">分類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-320">Total number of calls classified as poor.</span></span> <span data-ttu-id="d49be-321">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="d49be-321">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-322"><strong>通話音量（無線通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-322"><strong>Call volume (wireless call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-323">否</span><span class="sxs-lookup"><span data-stu-id="d49be-323">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-324">已使用無線連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-324">Total number of calls that used a wireless connection.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-325"><strong>通話量（VPN 通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-325"><strong>Call volume (VPN call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-326">否</span><span class="sxs-lookup"><span data-stu-id="d49be-326">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-327">已使用 VPN 連線的通話總數。</span><span class="sxs-lookup"><span data-stu-id="d49be-327">Total number of calls that used a VPN connection.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-328"><strong>通話音量（外部通話）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-328"><strong>Call volume (external call)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-329">否</span><span class="sxs-lookup"><span data-stu-id="d49be-329">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-330">使用外部連線的呼叫數量（也就是內部網路以外的連線）。</span><span class="sxs-lookup"><span data-stu-id="d49be-330">Number of calls that used an external connection (that is, a connection outside the internal network).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-331"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-331"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-332">否</span><span class="sxs-lookup"><span data-stu-id="d49be-332">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-333">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="d49be-333">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d49be-334">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="d49be-334">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-335"><strong>平均相對單向</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-335"><strong>Avg. relative one way</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-336">否</span><span class="sxs-lookup"><span data-stu-id="d49be-336">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-337">兩個媒體端點之間的平均相對單向延遲。</span><span class="sxs-lookup"><span data-stu-id="d49be-337">Average relative one-way delay between two media endpoints.</span></span> <span data-ttu-id="d49be-338">這是一個單跳躍延遲測量。</span><span class="sxs-lookup"><span data-stu-id="d49be-338">This is a single-hop latency measure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d49be-339"><strong>平均 .RDP 磚處理延遲時間</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-339"><strong>Avg. RDP tile processing latency</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-340">否</span><span class="sxs-lookup"><span data-stu-id="d49be-340">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-341">在查看會話期間，AS 會議服務器中的 [作為會議中的平均 RDP 磚處理延遲]。</span><span class="sxs-lookup"><span data-stu-id="d49be-341">The average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="d49be-342">此統計不會涵蓋網路延遲。</span><span class="sxs-lookup"><span data-stu-id="d49be-342">This metric does not cover network latency.</span></span> <span data-ttu-id="d49be-343">高平均值會在觀賞體驗中反映較長的延遲。</span><span class="sxs-lookup"><span data-stu-id="d49be-343">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="d49be-344">超負荷的會議服務器可能會遇到較高的平均延遲。</span><span class="sxs-lookup"><span data-stu-id="d49be-344">An overloaded conferencing server may experience higher average delays.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d49be-345"><strong>總 spoiled 磚%</strong></span><span class="sxs-lookup"><span data-stu-id="d49be-345"><strong>Total spoiled tile %</strong></span></span></p></td>
<td><p><span data-ttu-id="d49be-346">否</span><span class="sxs-lookup"><span data-stu-id="d49be-346">No</span></span></p></td>
<td><p><span data-ttu-id="d49be-347">Spoiled RDP 磚的總百分比。</span><span class="sxs-lookup"><span data-stu-id="d49be-347">Total percentage of spoiled RDP tiles.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

