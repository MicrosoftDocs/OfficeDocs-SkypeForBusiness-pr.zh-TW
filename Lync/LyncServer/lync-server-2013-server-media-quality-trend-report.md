---
title: Lync Server 2013：伺服器媒體質量趨勢報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b40f2c316216b01415b3e58d5d59c97421439d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510300"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="01964-102">Lync Server 2013 中的伺服器媒體質量趨勢報告</span><span class="sxs-lookup"><span data-stu-id="01964-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01964-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="01964-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="01964-104">伺服器媒體質量趨勢報告為您提供一種方式，可讓您以圖形方式比較最多5台伺服器的經驗品質計量，例如通話量、通話百分比、封包遺失及抖動。</span><span class="sxs-lookup"><span data-stu-id="01964-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="01964-105">這可讓您更容易進行這樣的工作，例如識別執行品質欠佳的伺服器、找出未充分利用的伺服器，或找出正在濫用的伺服器。</span><span class="sxs-lookup"><span data-stu-id="01964-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="01964-106">存取伺服器媒體質量趨勢報告</span><span class="sxs-lookup"><span data-stu-id="01964-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="01964-107">您可以從下列任一報告中存取伺服器媒體質量趨勢報告：</span><span class="sxs-lookup"><span data-stu-id="01964-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="01964-108">[在 Lync server 2013 (中](lync-server-2013-server-performance-report.md) ，按一下 [趨勢] 度量，以執行伺服器效能報告) </span><span class="sxs-lookup"><span data-stu-id="01964-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="01964-109">[在 Lync server 2013 (中](lync-server-2013-call-detail-report.md) ，按一下 [A/V edge Server 度量] 中的 [通話詳細資料包告]。</span><span class="sxs-lookup"><span data-stu-id="01964-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="01964-110">如果來電者或被叫方是伺服器，您也可以按一下端點名稱，以到達伺服器品質媒體趨勢報告。 ) </span><span class="sxs-lookup"><span data-stu-id="01964-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="01964-111">伺服器媒體質量趨勢報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="01964-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="01964-112">當您在特定伺服器的 [Lync server 2013 中，按一下 [伺服器效能報告](lync-server-2013-server-performance-report.md) ] 上的趨勢度量時，將會開啟 [伺服器媒體質量趨勢] 報告。</span><span class="sxs-lookup"><span data-stu-id="01964-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="01964-113">不過，您只會看到該報表的空白實例;您在伺服器效能報告上選取的伺服器不會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="01964-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="01964-114">相反地，您將需要從 [伺服器] 下拉式清單中選取該伺服器。</span><span class="sxs-lookup"><span data-stu-id="01964-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="01964-115">請注意，[伺服器] 下拉式清單中包含 [全選] 選項。</span><span class="sxs-lookup"><span data-stu-id="01964-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="01964-116">如果您有超過5部伺服器，此選項將無法運作;伺服器媒體質量趨勢報告一次只能顯示最多5個伺服器的資料。</span><span class="sxs-lookup"><span data-stu-id="01964-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="01964-117">在伺服器媒體質量趨勢報告所顯示的圖形上，會 hotlinks 標示為「呼叫數量」和「通話百分比不良」的點數。按一下圖形上的點會 [在 [Lync Server 2013] 中開啟通話清單報告](lync-server-2013-call-list-report.md) 的實例，顯示指定期間內 (或) 通話的總數。</span><span class="sxs-lookup"><span data-stu-id="01964-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="01964-118">篩選</span><span class="sxs-lookup"><span data-stu-id="01964-118">Filters</span></span>

<span data-ttu-id="01964-119">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="01964-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="01964-120">下表列出您可以搭配伺服器媒體質量趨勢報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="01964-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="01964-121">伺服器媒體質量趨勢報告篩選器</span><span class="sxs-lookup"><span data-stu-id="01964-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01964-122">名稱</span><span class="sxs-lookup"><span data-stu-id="01964-122">Name</span></span></th>
<th><span data-ttu-id="01964-123">描述</span><span class="sxs-lookup"><span data-stu-id="01964-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01964-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="01964-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01964-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="01964-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="01964-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01964-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="01964-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01964-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01964-130">7/7/2012</span></span></p>
<p><span data-ttu-id="01964-131">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="01964-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01964-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01964-132">7/3/2012</span></span></p>
<p><span data-ttu-id="01964-133">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="01964-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="01964-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="01964-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="01964-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="01964-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="01964-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="01964-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="01964-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="01964-140">7/7/2012</span></span></p>
<p><span data-ttu-id="01964-141">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="01964-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="01964-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="01964-142">7/3/2012</span></span></p>
<p><span data-ttu-id="01964-143">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="01964-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-144"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="01964-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-p109">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="01964-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="01964-147">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="01964-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01964-148">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="01964-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="01964-149">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="01964-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="01964-p110">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 8 月 7 日及 2012 年 9 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="01964-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-152"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="01964-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-153">通話中相關的伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="01964-153">Type of server involved in the call.</span></span> <span data-ttu-id="01964-154">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="01964-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="01964-155">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="01964-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="01964-156">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="01964-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="01964-157">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="01964-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="01964-158">閘道 (轉送伺服器) </span><span class="sxs-lookup"><span data-stu-id="01964-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="01964-159">閘道 (轉送伺服器旁路) </span><span class="sxs-lookup"><span data-stu-id="01964-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="01964-160">做為會議服務器</span><span class="sxs-lookup"><span data-stu-id="01964-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-161"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="01964-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-162">會話中相關的伺服器名稱;此下拉式清單會根據伺服器類型篩選器的值，自動為您填入。</span><span class="sxs-lookup"><span data-stu-id="01964-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="01964-163">在編譯報告時，最多可以選擇5個不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="01964-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-164"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="01964-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-165">會指出參與者是登入內部網路還是從外部網路登入。</span><span class="sxs-lookup"><span data-stu-id="01964-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="01964-166">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="01964-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="01964-167">一切</span><span class="sxs-lookup"><span data-stu-id="01964-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="01964-168">內部</span><span class="sxs-lookup"><span data-stu-id="01964-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="01964-169">外部</span><span class="sxs-lookup"><span data-stu-id="01964-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-170"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="01964-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-171">會指出參與者所連線的網路類型。</span><span class="sxs-lookup"><span data-stu-id="01964-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="01964-172">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="01964-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="01964-173">一切</span><span class="sxs-lookup"><span data-stu-id="01964-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="01964-174">有線</span><span class="sxs-lookup"><span data-stu-id="01964-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="01964-175">無線</span><span class="sxs-lookup"><span data-stu-id="01964-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="01964-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-177">會指出外部參與者是否在會話期間使用虛擬私人網路 (VPN) 連接。</span><span class="sxs-lookup"><span data-stu-id="01964-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="01964-178">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="01964-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="01964-179">一切</span><span class="sxs-lookup"><span data-stu-id="01964-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="01964-180">VPN</span><span class="sxs-lookup"><span data-stu-id="01964-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="01964-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="01964-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="01964-182">指標</span><span class="sxs-lookup"><span data-stu-id="01964-182">Metrics</span></span>

<span data-ttu-id="01964-183">下表列出伺服器媒體質量趨勢報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="01964-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="01964-184">伺服器媒體質量趨勢報告度量</span><span class="sxs-lookup"><span data-stu-id="01964-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01964-185">姓名</span><span class="sxs-lookup"><span data-stu-id="01964-185">Name</span></span></th>
<th><span data-ttu-id="01964-186">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="01964-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="01964-187">描述</span><span class="sxs-lookup"><span data-stu-id="01964-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01964-188"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="01964-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-189">否</span><span class="sxs-lookup"><span data-stu-id="01964-189">No</span></span></p></td>
<td><p><span data-ttu-id="01964-190">通話總數。</span><span class="sxs-lookup"><span data-stu-id="01964-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-191"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="01964-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-192">否</span><span class="sxs-lookup"><span data-stu-id="01964-192">No</span></span></p></td>
<td><p><span data-ttu-id="01964-193">通話的平均 MOS 量 (平均平均) </span><span class="sxs-lookup"><span data-stu-id="01964-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="01964-194">降級值的範圍從低0.0 到高 5.0;值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="01964-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="01964-195">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="01964-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="01964-196">Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="01964-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="01964-197">嚴重降級值可能是由於擁塞所造成;缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="01964-197">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="01964-198">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="01964-198">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-199"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="01964-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-200">否</span><span class="sxs-lookup"><span data-stu-id="01964-200">No</span></span></p></td>
<td><p><span data-ttu-id="01964-201">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="01964-201">The total number of calls classified as poor.</span></span> <span data-ttu-id="01964-202">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="01964-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-203"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="01964-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-204">否</span><span class="sxs-lookup"><span data-stu-id="01964-204">No</span></span></p></td>
<td><p><span data-ttu-id="01964-205">將 Real-Time 傳輸通訊協定封包傳送至一個端點後再進行的平均時間（毫秒）) 所需的 (毫秒量。</span><span class="sxs-lookup"><span data-stu-id="01964-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="01964-206">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="01964-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="01964-207">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="01964-207">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="01964-208">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="01964-208">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-209"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="01964-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-210">否</span><span class="sxs-lookup"><span data-stu-id="01964-210">No</span></span></p></td>
<td><p><span data-ttu-id="01964-211"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。</span><span class="sxs-lookup"><span data-stu-id="01964-211">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="01964-212">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="01964-212">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="01964-213">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="01964-213">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-214"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="01964-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-215">否</span><span class="sxs-lookup"><span data-stu-id="01964-215">No</span></span></p></td>
<td><p><span data-ttu-id="01964-216">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="01964-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="01964-217"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="01964-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-218"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="01964-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-219">否</span><span class="sxs-lookup"><span data-stu-id="01964-219">No</span></span></p></td>
<td><p><span data-ttu-id="01964-220">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="01964-220">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="01964-221"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="01964-221">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01964-222"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="01964-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-223">否</span><span class="sxs-lookup"><span data-stu-id="01964-223">No</span></span></p></td>
<td><p><span data-ttu-id="01964-224">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="01964-224">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="01964-225"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="01964-225">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01964-226"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="01964-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="01964-227">否</span><span class="sxs-lookup"><span data-stu-id="01964-227">No</span></span></p></td>
<td><p><span data-ttu-id="01964-228">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="01964-228">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="01964-229"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="01964-229">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

