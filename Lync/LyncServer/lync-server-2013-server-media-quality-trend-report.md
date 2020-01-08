---
title: Lync Server 2013：伺服器媒體質量趨勢報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc60cd4c0d8d00fa67a5fe77ca70e61058191baa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="da23d-102">Lync Server 2013 中的 [伺服器媒體質量趨勢] 報告</span><span class="sxs-lookup"><span data-stu-id="da23d-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="da23d-103">_**主題上次修改日期：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="da23d-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="da23d-104">[伺服器媒體質量趨勢] 報告可讓您以圖形方式比較多達5台伺服器，包括通話量、通話百分比差、資料包遺失和抖動等品質統計資料。</span><span class="sxs-lookup"><span data-stu-id="da23d-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="da23d-105">這可讓您更容易地找出執行不佳的伺服器、找出未充分利用的伺服器，或找出過度操作的伺服器。</span><span class="sxs-lookup"><span data-stu-id="da23d-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="da23d-106">存取伺服器媒體質量趨勢報告</span><span class="sxs-lookup"><span data-stu-id="da23d-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="da23d-107">您可以透過下列其中一種報告來存取伺服器媒體質量趨勢報告：</span><span class="sxs-lookup"><span data-stu-id="da23d-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="da23d-108">[Lync server 2013 中的伺服器效能報告](lync-server-2013-server-performance-report.md)（按一下趨勢指標）</span><span class="sxs-lookup"><span data-stu-id="da23d-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="da23d-109">[在 Lync Server 2013 中呼叫詳細資料包告](lync-server-2013-call-detail-report.md)（按一下 A/V 邊緣伺服器規格）。</span><span class="sxs-lookup"><span data-stu-id="da23d-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="da23d-110">如果來電者或被叫方是伺服器，您也可以按一下端點名稱來取得 [伺服器品質] 媒體趨勢報告。</span><span class="sxs-lookup"><span data-stu-id="da23d-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="da23d-111">充分利用伺服器媒體質量趨勢報告</span><span class="sxs-lookup"><span data-stu-id="da23d-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="da23d-112">當您針對特定伺服器按一下[Lync server 2013 的 [伺服器效能] 報告中](lync-server-2013-server-performance-report.md)的趨勢度量時，系統就會開啟 [伺服器媒體質量] 趨勢報告。</span><span class="sxs-lookup"><span data-stu-id="da23d-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="da23d-113">不過，您只會看到該報表的空白實例;您在伺服器效能報告上選取的伺服器不會在螢幕上顯示。</span><span class="sxs-lookup"><span data-stu-id="da23d-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="da23d-114">相反地，您將需要從 [伺服器] 下拉式清單中選取該伺服器。</span><span class="sxs-lookup"><span data-stu-id="da23d-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="da23d-115">請注意，[伺服器] 下拉式清單也包含 [全選] 選項。</span><span class="sxs-lookup"><span data-stu-id="da23d-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="da23d-116">如果您的伺服器超過5個，此選項將無法運作;伺服器媒體質量趨勢報告一次最多隻能顯示5個伺服器的資料。</span><span class="sxs-lookup"><span data-stu-id="da23d-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="da23d-117">在 [伺服器媒體質量趨勢] 報告所顯示的圖形上，標示為 [通話音量] 和 [通話百分比不佳] 的端點是 hotlinks;按一下圖表上的點將會[在 Lync Server 2013 中開啟通話清單報告](lync-server-2013-call-list-report.md)的實例，顯示指定時段內的通話總次數（或通話較差）。</span><span class="sxs-lookup"><span data-stu-id="da23d-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="da23d-118">濾鏡</span><span class="sxs-lookup"><span data-stu-id="da23d-118">Filters</span></span>

<span data-ttu-id="da23d-119">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="da23d-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="da23d-120">下表列出您可搭配 [伺服器媒體質量趨勢] 報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="da23d-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="da23d-121">伺服器媒體質量趨勢報表篩選</span><span class="sxs-lookup"><span data-stu-id="da23d-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da23d-122">名稱</span><span class="sxs-lookup"><span data-stu-id="da23d-122">Name</span></span></th>
<th><span data-ttu-id="da23d-123">描述</span><span class="sxs-lookup"><span data-stu-id="da23d-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da23d-124"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-125">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="da23d-125">Start date/time for the time range.</span></span> <span data-ttu-id="da23d-126">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da23d-126">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="da23d-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da23d-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da23d-128">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="da23d-128">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="da23d-129">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="da23d-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da23d-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da23d-130">7/7/2012</span></span></p>
<p><span data-ttu-id="da23d-131">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="da23d-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da23d-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da23d-132">7/3/2012</span></span></p>
<p><span data-ttu-id="da23d-133">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="da23d-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-134"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-135">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="da23d-135">End date/time for the time range.</span></span> <span data-ttu-id="da23d-136">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="da23d-136">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="da23d-137">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="da23d-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="da23d-138">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="da23d-138">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="da23d-139">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="da23d-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="da23d-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="da23d-140">7/7/2012</span></span></p>
<p><span data-ttu-id="da23d-141">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="da23d-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="da23d-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="da23d-142">7/3/2012</span></span></p>
<p><span data-ttu-id="da23d-143">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="da23d-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-144"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-145">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="da23d-145">Time interval.</span></span> <span data-ttu-id="da23d-146">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="da23d-146">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="da23d-147">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="da23d-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da23d-148">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="da23d-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="da23d-149">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="da23d-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="da23d-150">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="da23d-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="da23d-151">例如，如果您選取 [開始日期 8/7/2012] 和 [結束日期] 9/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="da23d-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-152"><strong>伺服器類型</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-153">通話中所涉及的伺服器類型。</span><span class="sxs-lookup"><span data-stu-id="da23d-153">Type of server involved in the call.</span></span> <span data-ttu-id="da23d-154">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="da23d-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="da23d-155">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="da23d-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="da23d-156">A/V 會議伺服器</span><span class="sxs-lookup"><span data-stu-id="da23d-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="da23d-157">A/V 邊緣伺服器</span><span class="sxs-lookup"><span data-stu-id="da23d-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="da23d-158">閘道（中繼伺服器）</span><span class="sxs-lookup"><span data-stu-id="da23d-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="da23d-159">閘道（中繼伺服器旁路）</span><span class="sxs-lookup"><span data-stu-id="da23d-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="da23d-160">AS 會議服務器</span><span class="sxs-lookup"><span data-stu-id="da23d-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-161"><strong>伺服器</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-162">會話中所涉及的伺服器名稱;這個下拉式清單會根據 [伺服器類型] 篩選器的值，自動填入給您。</span><span class="sxs-lookup"><span data-stu-id="da23d-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="da23d-163">編譯報表時，最多可以選取5個不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="da23d-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-164"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-165">指出參與者是否已登入內部網路或來自外部網路。</span><span class="sxs-lookup"><span data-stu-id="da23d-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="da23d-166">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="da23d-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="da23d-167">同時</span><span class="sxs-lookup"><span data-stu-id="da23d-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="da23d-168">內部</span><span class="sxs-lookup"><span data-stu-id="da23d-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="da23d-169">外來</span><span class="sxs-lookup"><span data-stu-id="da23d-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-170"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-171">指出參與者已連接的網路類型。</span><span class="sxs-lookup"><span data-stu-id="da23d-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="da23d-172">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="da23d-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="da23d-173">同時</span><span class="sxs-lookup"><span data-stu-id="da23d-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="da23d-174">有線</span><span class="sxs-lookup"><span data-stu-id="da23d-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="da23d-175">無線</span><span class="sxs-lookup"><span data-stu-id="da23d-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-176"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-177">表示外部參與者是否在會話期間使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="da23d-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="da23d-178">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="da23d-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="da23d-179">同時</span><span class="sxs-lookup"><span data-stu-id="da23d-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="da23d-180">點對點</span><span class="sxs-lookup"><span data-stu-id="da23d-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="da23d-181">非 VPN</span><span class="sxs-lookup"><span data-stu-id="da23d-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="da23d-182">指標</span><span class="sxs-lookup"><span data-stu-id="da23d-182">Metrics</span></span>

<span data-ttu-id="da23d-183">下表列出 [伺服器媒體質量趨勢] 報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="da23d-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="da23d-184">伺服器媒體質量趨勢報告度量單位</span><span class="sxs-lookup"><span data-stu-id="da23d-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="da23d-185">名稱</span><span class="sxs-lookup"><span data-stu-id="da23d-185">Name</span></span></th>
<th><span data-ttu-id="da23d-186">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="da23d-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="da23d-187">描述</span><span class="sxs-lookup"><span data-stu-id="da23d-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="da23d-188"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-189">否</span><span class="sxs-lookup"><span data-stu-id="da23d-189">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-190">通話總次數。</span><span class="sxs-lookup"><span data-stu-id="da23d-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-191"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-192">否</span><span class="sxs-lookup"><span data-stu-id="da23d-192">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-193">通話期間的平均 MOS （平均選項分數）下降。</span><span class="sxs-lookup"><span data-stu-id="da23d-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="da23d-194">降級值的範圍可從低0.0 到 5.0;0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="da23d-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="da23d-195">過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。</span><span class="sxs-lookup"><span data-stu-id="da23d-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="da23d-196">Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="da23d-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="da23d-197">擁塞可能會造成高降級值。缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="da23d-197">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="da23d-198">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="da23d-198">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-199"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-200">否</span><span class="sxs-lookup"><span data-stu-id="da23d-200">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-201">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="da23d-201">The total number of calls classified as poor.</span></span> <span data-ttu-id="da23d-202">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="da23d-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-203"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-204">否</span><span class="sxs-lookup"><span data-stu-id="da23d-204">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-205">即時傳輸通訊協定資料包傳送到一個端點，然後返回該時間所需的平均時間（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="da23d-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="da23d-206">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="da23d-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="da23d-207">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="da23d-207">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="da23d-208">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="da23d-208">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-209"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-210">否</span><span class="sxs-lookup"><span data-stu-id="da23d-210">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-211">即時傳輸通訊協定（RTP）資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="da23d-211">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="da23d-212">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="da23d-212">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="da23d-213">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="da23d-213">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-214"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-215">否</span><span class="sxs-lookup"><span data-stu-id="da23d-215">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-216">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="da23d-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="da23d-217">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="da23d-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-218"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-219">否</span><span class="sxs-lookup"><span data-stu-id="da23d-219">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-220">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="da23d-220">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="da23d-221">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="da23d-221">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="da23d-222"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-223">否</span><span class="sxs-lookup"><span data-stu-id="da23d-223">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-224">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="da23d-224">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="da23d-225">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="da23d-225">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="da23d-226"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="da23d-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="da23d-227">否</span><span class="sxs-lookup"><span data-stu-id="da23d-227">No</span></span></p></td>
<td><p><span data-ttu-id="da23d-228">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="da23d-228">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="da23d-229">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="da23d-229">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

