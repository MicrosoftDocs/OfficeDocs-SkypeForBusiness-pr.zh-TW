---
title: Lync Server 2013：媒體質量比較報告
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
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="943aa-102">Lync Server 2013 中的媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="943aa-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="943aa-103">_**主題上次修改日期：** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="943aa-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="943aa-104">媒體質量比較報告可讓您比較不同類型音訊通話的通話品質值（例如，透過無線網路撥打，以及透過有線連線進行通話）。</span><span class="sxs-lookup"><span data-stu-id="943aa-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="943aa-105">存取媒體質量比較報告</span><span class="sxs-lookup"><span data-stu-id="943aa-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="943aa-106">您可從 [監控報告] 首頁存取媒體質量比較報告。</span><span class="sxs-lookup"><span data-stu-id="943aa-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="943aa-107">濾鏡</span><span class="sxs-lookup"><span data-stu-id="943aa-107">Filters</span></span>

<span data-ttu-id="943aa-108">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="943aa-108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="943aa-109">下表列出您可搭配媒體質量比較報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="943aa-109">The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="943aa-110">媒體質量比較報表篩選</span><span class="sxs-lookup"><span data-stu-id="943aa-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="943aa-111">名稱</span><span class="sxs-lookup"><span data-stu-id="943aa-111">Name</span></span></th>
<th><span data-ttu-id="943aa-112">說明</span><span class="sxs-lookup"><span data-stu-id="943aa-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="943aa-113"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-114">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="943aa-114">Start date/time for the time range.</span></span> <span data-ttu-id="943aa-115">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="943aa-115">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="943aa-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="943aa-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="943aa-117">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="943aa-117">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="943aa-118">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="943aa-118">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="943aa-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="943aa-119">7/7/2012</span></span></p>
<p><span data-ttu-id="943aa-120">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="943aa-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="943aa-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="943aa-121">7/3/2012</span></span></p>
<p><span data-ttu-id="943aa-122">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="943aa-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-123"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-124">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="943aa-124">End date/time for the time range.</span></span> <span data-ttu-id="943aa-125">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="943aa-125">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="943aa-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="943aa-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="943aa-127">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="943aa-127">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="943aa-128">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="943aa-128">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="943aa-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="943aa-129">7/7/2012</span></span></p>
<p><span data-ttu-id="943aa-130">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="943aa-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="943aa-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="943aa-131">7/3/2012</span></span></p>
<p><span data-ttu-id="943aa-132">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="943aa-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-133"><strong>撥</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-134">要用來做為主要比較專案的呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="943aa-134">Type of call to be used as the main comparison item.</span></span> <span data-ttu-id="943aa-135">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="943aa-135">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="943aa-136">同時</span><span class="sxs-lookup"><span data-stu-id="943aa-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="943aa-137">外來</span><span class="sxs-lookup"><span data-stu-id="943aa-137">External</span></span></p></li>
<li><p><span data-ttu-id="943aa-138">內部</span><span class="sxs-lookup"><span data-stu-id="943aa-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="943aa-139">點對點</span><span class="sxs-lookup"><span data-stu-id="943aa-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-140">非 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-141">有線</span><span class="sxs-lookup"><span data-stu-id="943aa-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-142">無線</span><span class="sxs-lookup"><span data-stu-id="943aa-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="943aa-143">外部和有線</span><span class="sxs-lookup"><span data-stu-id="943aa-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-144">外部和無線</span><span class="sxs-lookup"><span data-stu-id="943aa-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="943aa-145">外部與 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-146">外部與非 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-147">內部和有線</span><span class="sxs-lookup"><span data-stu-id="943aa-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-148">內部和無線</span><span class="sxs-lookup"><span data-stu-id="943aa-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-149"><strong>與通話比較</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-150">要用來做為次要比較專案的呼叫類型。</span><span class="sxs-lookup"><span data-stu-id="943aa-150">Type of call to be used as the secondary comparison item.</span></span> <span data-ttu-id="943aa-151">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="943aa-151">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="943aa-152">同時</span><span class="sxs-lookup"><span data-stu-id="943aa-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="943aa-153">外來</span><span class="sxs-lookup"><span data-stu-id="943aa-153">External</span></span></p></li>
<li><p><span data-ttu-id="943aa-154">內部</span><span class="sxs-lookup"><span data-stu-id="943aa-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="943aa-155">點對點</span><span class="sxs-lookup"><span data-stu-id="943aa-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-156">非 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-157">有線</span><span class="sxs-lookup"><span data-stu-id="943aa-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-158">無線</span><span class="sxs-lookup"><span data-stu-id="943aa-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="943aa-159">外部和有線</span><span class="sxs-lookup"><span data-stu-id="943aa-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-160">外部和無線</span><span class="sxs-lookup"><span data-stu-id="943aa-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="943aa-161">外部與 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-162">外部與非 VPN</span><span class="sxs-lookup"><span data-stu-id="943aa-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="943aa-163">內部和有線</span><span class="sxs-lookup"><span data-stu-id="943aa-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="943aa-164">內部和無線</span><span class="sxs-lookup"><span data-stu-id="943aa-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-165"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-166">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="943aa-166">Time interval.</span></span> <span data-ttu-id="943aa-167">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="943aa-167">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="943aa-168">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="943aa-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="943aa-169">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="943aa-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="943aa-170">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="943aa-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="943aa-171">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="943aa-171">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="943aa-172">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="943aa-172">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="943aa-173">指標</span><span class="sxs-lookup"><span data-stu-id="943aa-173">Metrics</span></span>

<span data-ttu-id="943aa-174">下表列出媒體質量比較報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="943aa-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="943aa-175">媒體質量比較報告度量單位</span><span class="sxs-lookup"><span data-stu-id="943aa-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="943aa-176">名稱</span><span class="sxs-lookup"><span data-stu-id="943aa-176">Name</span></span></th>
<th><span data-ttu-id="943aa-177">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="943aa-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="943aa-178">說明</span><span class="sxs-lookup"><span data-stu-id="943aa-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="943aa-179"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-180">否</span><span class="sxs-lookup"><span data-stu-id="943aa-180">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-181">通話總次數。</span><span class="sxs-lookup"><span data-stu-id="943aa-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-182"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-183">否</span><span class="sxs-lookup"><span data-stu-id="943aa-183">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-184">通話期間的平均 MOS （平均意見分數）會下降。</span><span class="sxs-lookup"><span data-stu-id="943aa-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="943aa-185">降級值的範圍可從低0.0 到 5.0;0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="943aa-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="943aa-186">在過去，平均值觀點的計算方式是讓使用者以1到5的比例來評分通話品質。</span><span class="sxs-lookup"><span data-stu-id="943aa-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="943aa-187">Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="943aa-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="943aa-188">擁塞可能會造成高降級值。缺乏頻寬;無線擁塞或干擾，或超載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="943aa-188">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="943aa-189">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="943aa-189">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-190"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-191">否</span><span class="sxs-lookup"><span data-stu-id="943aa-191">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-192">分類為不良的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="943aa-192">The total number of calls classified as poor.</span></span> <span data-ttu-id="943aa-193">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="943aa-193">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-194"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-195">否</span><span class="sxs-lookup"><span data-stu-id="943aa-195">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-196">即時傳輸通訊協定資料包移動到另一個端點之後，再返回的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="943aa-196">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="943aa-197">200毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="943aa-197">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="943aa-198">國際呼叫路由可能會造成高往返值。路由無法正確配置;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="943aa-198">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="943aa-199">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="943aa-199">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-200"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-201">否</span><span class="sxs-lookup"><span data-stu-id="943aa-201">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-202">即時傳輸通訊協定（RTP）資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="943aa-202">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="943aa-203">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由擁塞所造成;缺乏頻寬;無線擁塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="943aa-203">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="943aa-204">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="943aa-204">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-205"><strong>抖動（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-206">否</span><span class="sxs-lookup"><span data-stu-id="943aa-206">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-207">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="943aa-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="943aa-208">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="943aa-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-209"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-210">否</span><span class="sxs-lookup"><span data-stu-id="943aa-210">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-211">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="943aa-211">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="943aa-212">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="943aa-212">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="943aa-213"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-214">否</span><span class="sxs-lookup"><span data-stu-id="943aa-214">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-215">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="943aa-215">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="943aa-216">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="943aa-216">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="943aa-217"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="943aa-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="943aa-218">否</span><span class="sxs-lookup"><span data-stu-id="943aa-218">No</span></span></p></td>
<td><p><span data-ttu-id="943aa-219">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="943aa-219">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="943aa-220">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="943aa-220">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

