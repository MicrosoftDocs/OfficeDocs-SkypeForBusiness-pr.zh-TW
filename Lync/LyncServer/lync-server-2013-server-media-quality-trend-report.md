---
title: Lync Server 2013： 伺服器媒體品質趨勢報告
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
ms.openlocfilehash: 0c36add301665c2e6b689bd1343cc09efeec5b3e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="c0e0d-102">在 Lync Server 2013 伺服器媒體品質趨勢報告</span><span class="sxs-lookup"><span data-stu-id="c0e0d-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0e0d-103">_**主題上次修改日期：** 2012年-11-12_</span><span class="sxs-lookup"><span data-stu-id="c0e0d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="c0e0d-104">伺服器媒體品質趨勢報告可讓您以圖形方式比較最多 5 個伺服器上的經驗品質計量，例如通話數量、 收訊不良通話百分比、 封包遺失及抖動。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="c0e0d-105">這樣做為識別執行效能不佳的伺服器、 識別伺服器，都未得到充分利用，或識別所要使用過度的伺服器此類事情更容易。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="c0e0d-106">存取伺服器媒體品質趨勢報告</span><span class="sxs-lookup"><span data-stu-id="c0e0d-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="c0e0d-107">伺服器媒體品質趨勢報告可從下列報告的其中一個：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="c0e0d-108">[Lync Server 2013 中的 server Performance Report](lync-server-2013-server-performance-report.md) (按一下趨勢計量）</span><span class="sxs-lookup"><span data-stu-id="c0e0d-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="c0e0d-109">[Lync Server 2013 中的通話詳細資料報告](lync-server-2013-call-detail-report.md)(按一下 [A / V edge server] 計量。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="c0e0d-110">如果來電者或受話者位於伺服器，您可能也會達到伺服器品質媒體趨勢報告的端點名稱，即可。）</span><span class="sxs-lookup"><span data-stu-id="c0e0d-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="c0e0d-111">伺服器媒體品質趨勢報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="c0e0d-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="c0e0d-112">當您按一下趨勢計量[Lync Server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)的特定伺服器上時，將會開啟伺服器媒體品質趨勢報告。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="c0e0d-113">不過，您會看到該報表; 中的空白執行個體在伺服器效能報告選取的伺服器不會顯示在螢幕上。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="c0e0d-114">相反地，您必須從 [伺服器] 下拉式清單中選取該伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="c0e0d-115">請注意，[伺服器] 下拉式清單中包含的所有選取的選項。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="c0e0d-116">如果您有超過 5 伺服器; 此選項將無法運作伺服器媒體品質趨勢報告可以只會顯示一次最多 5 部伺服器的資料。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="c0e0d-117">在 [伺服器媒體品質趨勢報告顯示的圖形，資料點標記為呼叫磁碟區，且收訊不良通話百分比不良率;按一下圖上的點將開啟[Call List Report Lync Server 2013 中](lync-server-2013-call-list-report.md)顯示的來電總數 （或不良通話數） 指定的時間期間內的執行個體。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="c0e0d-118">篩選</span><span class="sxs-lookup"><span data-stu-id="c0e0d-118">Filters</span></span>

<span data-ttu-id="c0e0d-119">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="c0e0d-120">下表列出您可以使用伺服器媒體品質趨勢報告篩選器。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="c0e0d-121">伺服器媒體品質趨勢報告篩選器</span><span class="sxs-lookup"><span data-stu-id="c0e0d-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0e0d-122">名稱</span><span class="sxs-lookup"><span data-stu-id="c0e0d-122">Name</span></span></th>
<th><span data-ttu-id="c0e0d-123">描述</span><span class="sxs-lookup"><span data-stu-id="c0e0d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-124"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-p105">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="c0e0d-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c0e0d-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0e0d-p106">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0e0d-130">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="c0e0d-130">7/7/2012</span></span></p>
<p><span data-ttu-id="c0e0d-131">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0e0d-132">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="c0e0d-132">7/3/2012</span></span></p>
<p><span data-ttu-id="c0e0d-133">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-134"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-p107">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="c0e0d-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="c0e0d-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="c0e0d-p108">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="c0e0d-140">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="c0e0d-140">7/7/2012</span></span></p>
<p><span data-ttu-id="c0e0d-141">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="c0e0d-142">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="c0e0d-142">7/3/2012</span></span></p>
<p><span data-ttu-id="c0e0d-143">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-144"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-p109">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0e0d-147">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="c0e0d-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-148">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="c0e0d-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-149">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="c0e0d-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="c0e0d-p110">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 8 月 7 日及 2012 年 9 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-152"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-153">伺服器參與通話類型。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-153">Type of server involved in the call.</span></span> <span data-ttu-id="c0e0d-154">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0e0d-155">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="c0e0d-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-156">A/V Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="c0e0d-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-157">A/V Edge Server</span><span class="sxs-lookup"><span data-stu-id="c0e0d-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-158">閘道 （中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="c0e0d-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-159">閘道 （中繼伺服器旁路）</span><span class="sxs-lookup"><span data-stu-id="c0e0d-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-160">AS 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="c0e0d-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-161"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-162">參與工作階段; 的伺服器名稱為您的伺服器類型篩選條件的值為基礎，會自動填入此下拉式清單。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="c0e0d-163">編譯報表時，您可以選取最多 5 個不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-164"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-165">會指出是否參與者登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="c0e0d-166">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0e0d-167">[全部]</span><span class="sxs-lookup"><span data-stu-id="c0e0d-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-168">內部</span><span class="sxs-lookup"><span data-stu-id="c0e0d-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-169">External</span><span class="sxs-lookup"><span data-stu-id="c0e0d-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-170"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-171">會指出參與者已連線至網路的類型。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="c0e0d-172">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0e0d-173">[全部]</span><span class="sxs-lookup"><span data-stu-id="c0e0d-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-174">有線</span><span class="sxs-lookup"><span data-stu-id="c0e0d-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-175">無線</span><span class="sxs-lookup"><span data-stu-id="c0e0d-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-177">會指出外部參與者是否已使用工作階段期間的虛擬私人網路 (VPN) 連線。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="c0e0d-178">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="c0e0d-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="c0e0d-179">[全部]</span><span class="sxs-lookup"><span data-stu-id="c0e0d-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-180">VPN</span><span class="sxs-lookup"><span data-stu-id="c0e0d-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="c0e0d-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="c0e0d-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="c0e0d-182">計量</span><span class="sxs-lookup"><span data-stu-id="c0e0d-182">Metrics</span></span>

<span data-ttu-id="c0e0d-183">下表列出伺服器媒體品質趨勢報告提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="c0e0d-184">伺服器媒體品質趨勢報告計量</span><span class="sxs-lookup"><span data-stu-id="c0e0d-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0e0d-185">姓名</span><span class="sxs-lookup"><span data-stu-id="c0e0d-185">Name</span></span></th>
<th><span data-ttu-id="c0e0d-186">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="c0e0d-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="c0e0d-187">描述</span><span class="sxs-lookup"><span data-stu-id="c0e0d-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-188"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-189">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-189">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-190">通話總數。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-191"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-192">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-192">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-193">平均量 MOS （mean 選項分數） 降低在通話期間發生的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="c0e0d-194">降低值可介於 0.0 的低到高的 5.0;為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="c0e0d-195">在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="c0e0d-196">Lync Server 使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="c0e0d-197">高的效能下降值會造成壅塞;缺少的頻寬;無線壅塞干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-197">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="c0e0d-198">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-198">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-199"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-200">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-200">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-201">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-201">The total number of calls classified as poor.</span></span> <span data-ttu-id="c0e0d-202">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-203"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-204">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-204">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-205">平均時間 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳送到一個端點，再重新量。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="c0e0d-206">200 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="c0e0d-207">高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-207">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="c0e0d-208">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-208">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-209"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-210">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-210">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-211">即時傳輸通訊協定 (RTP) 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-211">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="c0e0d-212">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-212">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="c0e0d-213">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-213">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-214"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-215">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-215">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-216">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="c0e0d-217">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-218"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-219">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-219">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-220">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-220">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="c0e0d-221">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-221">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0e0d-222"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-223">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-223">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-224">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-224">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="c0e0d-225">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-225">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0e0d-226"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="c0e0d-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="c0e0d-227">否</span><span class="sxs-lookup"><span data-stu-id="c0e0d-227">No</span></span></p></td>
<td><p><span data-ttu-id="c0e0d-228">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-228">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="c0e0d-229">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="c0e0d-229">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

