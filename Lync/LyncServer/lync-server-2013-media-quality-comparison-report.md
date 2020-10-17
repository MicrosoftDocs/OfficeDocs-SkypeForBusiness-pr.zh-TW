---
title: Lync Server 2013：媒體質量比較報告
description: Lync Server 2013：媒體質量比較報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2c4c5c948d167ce5210f9814c4e0625ffaa9152
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548229"
---
# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="2bd17-103">Lync Server 2013 中的媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="2bd17-103">Media Quality Comparison Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2bd17-104">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="2bd17-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="2bd17-105">媒體質量比較報告可讓您比較不同音訊通話類型的通話品質值 (例如，透過無線網路撥打的通話，以及透過有線連線進行的通話) 。</span><span class="sxs-lookup"><span data-stu-id="2bd17-105">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="2bd17-106">存取媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="2bd17-106">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="2bd17-107">媒體質量比較報告可從監控報告的首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="2bd17-107">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="2bd17-108">篩選</span><span class="sxs-lookup"><span data-stu-id="2bd17-108">Filters</span></span>

<span data-ttu-id="2bd17-109">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="2bd17-109">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="2bd17-110">下表列出您可以搭配媒體質量比較報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="2bd17-110">The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="2bd17-111">媒體質量比較報表篩選</span><span class="sxs-lookup"><span data-stu-id="2bd17-111">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bd17-112">名稱</span><span class="sxs-lookup"><span data-stu-id="2bd17-112">Name</span></span></th>
<th><span data-ttu-id="2bd17-113">描述</span><span class="sxs-lookup"><span data-stu-id="2bd17-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-114"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-p102">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bd17-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="2bd17-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2bd17-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2bd17-p103">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="2bd17-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2bd17-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2bd17-120">7/7/2012</span></span></p>
<p><span data-ttu-id="2bd17-121">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="2bd17-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2bd17-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2bd17-122">7/3/2012</span></span></p>
<p><span data-ttu-id="2bd17-123">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="2bd17-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-p104">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2bd17-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="2bd17-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="2bd17-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="2bd17-p105">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="2bd17-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="2bd17-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="2bd17-130">7/7/2012</span></span></p>
<p><span data-ttu-id="2bd17-131">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="2bd17-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="2bd17-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="2bd17-132">7/3/2012</span></span></p>
<p><span data-ttu-id="2bd17-133">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="2bd17-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-134"><strong>調用</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-134"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-135">要用來做為主要比較專案的呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="2bd17-135">Type of call to be used as the main comparison item.</span></span> <span data-ttu-id="2bd17-136">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="2bd17-136">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2bd17-137">一切</span><span class="sxs-lookup"><span data-stu-id="2bd17-137">[All]</span></span></p></li>
<li><p><span data-ttu-id="2bd17-138">外部</span><span class="sxs-lookup"><span data-stu-id="2bd17-138">External</span></span></p></li>
<li><p><span data-ttu-id="2bd17-139">內部</span><span class="sxs-lookup"><span data-stu-id="2bd17-139">Internal</span></span></p></li>
<li><p><span data-ttu-id="2bd17-140">VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-140">VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-141">非 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-141">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-142">有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-142">Wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-143">無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-143">Wireless</span></span></p></li>
<li><p><span data-ttu-id="2bd17-144">外部和有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-144">External and wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-145">外部和無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-145">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="2bd17-146">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-146">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-147">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-147">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-148">內部和有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-148">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-149">內部和無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-149">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-150"><strong>與通話比較</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-150"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-151">要用來做為次要比較專案的呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="2bd17-151">Type of call to be used as the secondary comparison item.</span></span> <span data-ttu-id="2bd17-152">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="2bd17-152">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="2bd17-153">一切</span><span class="sxs-lookup"><span data-stu-id="2bd17-153">[All]</span></span></p></li>
<li><p><span data-ttu-id="2bd17-154">外部</span><span class="sxs-lookup"><span data-stu-id="2bd17-154">External</span></span></p></li>
<li><p><span data-ttu-id="2bd17-155">內部</span><span class="sxs-lookup"><span data-stu-id="2bd17-155">Internal</span></span></p></li>
<li><p><span data-ttu-id="2bd17-156">VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-157">非 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-157">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-158">有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-158">Wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-159">無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-159">Wireless</span></span></p></li>
<li><p><span data-ttu-id="2bd17-160">外部和有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-160">External and wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-161">外部和無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-161">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="2bd17-162">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-162">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-163">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="2bd17-163">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="2bd17-164">內部和有線</span><span class="sxs-lookup"><span data-stu-id="2bd17-164">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="2bd17-165">內部和無線</span><span class="sxs-lookup"><span data-stu-id="2bd17-165">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-166"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-166"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="2bd17-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="2bd17-169">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="2bd17-169">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2bd17-170">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="2bd17-170">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="2bd17-171">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="2bd17-171">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="2bd17-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="2bd17-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="2bd17-174">指標</span><span class="sxs-lookup"><span data-stu-id="2bd17-174">Metrics</span></span>

<span data-ttu-id="2bd17-175">下表列出媒體質量比較報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="2bd17-175">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="2bd17-176">媒體質量比較報告度量</span><span class="sxs-lookup"><span data-stu-id="2bd17-176">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2bd17-177">姓名</span><span class="sxs-lookup"><span data-stu-id="2bd17-177">Name</span></span></th>
<th><span data-ttu-id="2bd17-178">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="2bd17-178">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="2bd17-179">描述</span><span class="sxs-lookup"><span data-stu-id="2bd17-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-180"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-180"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-181">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-181">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-182">通話總數。</span><span class="sxs-lookup"><span data-stu-id="2bd17-182">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-183"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-184">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-184">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-185">平均 MOS 金額 (平均平均觀點) 通話期間的效能。</span><span class="sxs-lookup"><span data-stu-id="2bd17-185">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="2bd17-186">降級值的範圍從低0.0 到高 5.0;值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="2bd17-186">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="2bd17-187">從過去開始，平均觀點是透過讓使用者以1到5的比例來評分呼叫的品質來計算。</span><span class="sxs-lookup"><span data-stu-id="2bd17-187">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="2bd17-188">Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="2bd17-188">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="2bd17-189">嚴重降級值可能是由於擁塞所造成;缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="2bd17-189">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="2bd17-190">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="2bd17-190">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-191"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-191"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-192">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-192">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-193">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="2bd17-193">The total number of calls classified as poor.</span></span> <span data-ttu-id="2bd17-194">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="2bd17-194">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-195"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-195"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-196">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-196">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-197">Real-Time 傳輸通訊協定封包傳送到另一個端點後再回的平均 (量（毫秒）) 所需。</span><span class="sxs-lookup"><span data-stu-id="2bd17-197">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="2bd17-198">在200毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="2bd17-198">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="2bd17-199">高來回行程值可能是由國際通話路由所造成;路由傳送錯誤;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="2bd17-199">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="2bd17-200">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="2bd17-200">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-201"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-201"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-202">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-202">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-203"> (RTP) 封包遺失 Real-Time 傳輸通訊協定的平均速率。</span><span class="sxs-lookup"><span data-stu-id="2bd17-203">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="2bd17-204">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或重載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="2bd17-204">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="2bd17-205">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="2bd17-205">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-206"><strong>抖動 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-206"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-207">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-207">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-208">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="2bd17-208">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="2bd17-209"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="2bd17-209">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-210"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-210"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-211">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-211">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-212">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="2bd17-212">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="2bd17-213"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="2bd17-213">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2bd17-214"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-214"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-215">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-215">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-216">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="2bd17-216">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="2bd17-217"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="2bd17-217">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2bd17-218"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="2bd17-218"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="2bd17-219">否</span><span class="sxs-lookup"><span data-stu-id="2bd17-219">No</span></span></p></td>
<td><p><span data-ttu-id="2bd17-220">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="2bd17-220">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="2bd17-221"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="2bd17-221">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

