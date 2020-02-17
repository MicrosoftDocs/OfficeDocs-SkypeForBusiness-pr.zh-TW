---
title: Lync Server 2013： 媒體品質比較報告
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
ms.openlocfilehash: c45f2d238d2ffd8df058e31bfa50a51f26c1caf5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a><span data-ttu-id="b01e2-102">Lync Server 2013 中的媒體品質比較報告</span><span class="sxs-lookup"><span data-stu-id="b01e2-102">Media Quality Comparison Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b01e2-103">_**上次修改主題：** 2014年-04-22_</span><span class="sxs-lookup"><span data-stu-id="b01e2-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="b01e2-104">媒體品質比較報告可讓您比較不同類型的音訊通話 （例如，透過無線網路與有線連線之間進行的呼叫進行的通話） 的通話品質值。</span><span class="sxs-lookup"><span data-stu-id="b01e2-104">The Media Quality Comparison Report enables you to compare call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

<div>

## <a name="accessing-the-media-quality-comparison-report"></a><span data-ttu-id="b01e2-105">存取媒體品質比較報告</span><span class="sxs-lookup"><span data-stu-id="b01e2-105">Accessing the Media Quality Comparison Report</span></span>

<span data-ttu-id="b01e2-106">從監視報告首頁存取媒體品質比較報告。</span><span class="sxs-lookup"><span data-stu-id="b01e2-106">The Media Quality Comparison Report is accessed from the Monitoring Reports home page.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="b01e2-107">篩選</span><span class="sxs-lookup"><span data-stu-id="b01e2-107">Filters</span></span>

<span data-ttu-id="b01e2-108">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="b01e2-108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b01e2-109">下表列出您可以搭配媒體品質比較報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="b01e2-109">The following table lists the filters that you can use with the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-filters"></a><span data-ttu-id="b01e2-110">媒體品質比較報告篩選器</span><span class="sxs-lookup"><span data-stu-id="b01e2-110">Media Quality Comparison Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b01e2-111">名稱</span><span class="sxs-lookup"><span data-stu-id="b01e2-111">Name</span></span></th>
<th><span data-ttu-id="b01e2-112">描述</span><span class="sxs-lookup"><span data-stu-id="b01e2-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-113"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-p102">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b01e2-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b01e2-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b01e2-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b01e2-p103">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="b01e2-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b01e2-119">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="b01e2-119">7/7/2012</span></span></p>
<p><span data-ttu-id="b01e2-120">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="b01e2-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b01e2-121">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="b01e2-121">7/3/2012</span></span></p>
<p><span data-ttu-id="b01e2-122">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="b01e2-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-p104">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b01e2-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b01e2-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b01e2-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b01e2-p105">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="b01e2-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b01e2-129">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="b01e2-129">7/7/2012</span></span></p>
<p><span data-ttu-id="b01e2-130">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="b01e2-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b01e2-131">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="b01e2-131">7/3/2012</span></span></p>
<p><span data-ttu-id="b01e2-132">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="b01e2-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-133"><strong>通話</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-133"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-134">呼叫，以做為主要比較項目類型。</span><span class="sxs-lookup"><span data-stu-id="b01e2-134">Type of call to be used as the main comparison item.</span></span> <span data-ttu-id="b01e2-135">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b01e2-135">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b01e2-136">[全部]</span><span class="sxs-lookup"><span data-stu-id="b01e2-136">[All]</span></span></p></li>
<li><p><span data-ttu-id="b01e2-137">External</span><span class="sxs-lookup"><span data-stu-id="b01e2-137">External</span></span></p></li>
<li><p><span data-ttu-id="b01e2-138">內部</span><span class="sxs-lookup"><span data-stu-id="b01e2-138">Internal</span></span></p></li>
<li><p><span data-ttu-id="b01e2-139">VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-139">VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-140">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-140">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-141">有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-141">Wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-142">無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-142">Wireless</span></span></p></li>
<li><p><span data-ttu-id="b01e2-143">外部和有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-143">External and wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-144">外部和無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-144">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="b01e2-145">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-145">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-146">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-146">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-147">內部和有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-147">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-148">內部和無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-148">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-149"><strong>比較通話</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-149"><strong>Compare with calls</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-150">呼叫，以做為次要比較項目類型。</span><span class="sxs-lookup"><span data-stu-id="b01e2-150">Type of call to be used as the secondary comparison item.</span></span> <span data-ttu-id="b01e2-151">允許的值為：</span><span class="sxs-lookup"><span data-stu-id="b01e2-151">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="b01e2-152">[全部]</span><span class="sxs-lookup"><span data-stu-id="b01e2-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="b01e2-153">External</span><span class="sxs-lookup"><span data-stu-id="b01e2-153">External</span></span></p></li>
<li><p><span data-ttu-id="b01e2-154">內部</span><span class="sxs-lookup"><span data-stu-id="b01e2-154">Internal</span></span></p></li>
<li><p><span data-ttu-id="b01e2-155">VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-155">VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-156">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-156">Non-VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-157">有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-157">Wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-158">無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-158">Wireless</span></span></p></li>
<li><p><span data-ttu-id="b01e2-159">外部和有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-159">External and wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-160">外部和無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-160">External and wireless</span></span></p></li>
<li><p><span data-ttu-id="b01e2-161">外部和 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-161">External and VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-162">外部和非 VPN</span><span class="sxs-lookup"><span data-stu-id="b01e2-162">External and non-VPN</span></span></p></li>
<li><p><span data-ttu-id="b01e2-163">內部和有線</span><span class="sxs-lookup"><span data-stu-id="b01e2-163">Internal and wired</span></span></p></li>
<li><p><span data-ttu-id="b01e2-164">內部和無線</span><span class="sxs-lookup"><span data-stu-id="b01e2-164">Internal and wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-165"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-165"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-p108">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b01e2-p108">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b01e2-168">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="b01e2-168">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b01e2-169">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="b01e2-169">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="b01e2-170">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="b01e2-170">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="b01e2-p109">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="b01e2-p109">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="b01e2-173">計量</span><span class="sxs-lookup"><span data-stu-id="b01e2-173">Metrics</span></span>

<span data-ttu-id="b01e2-174">下表列出媒體品質比較報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-174">The following table lists the information provided in the Media Quality Comparison Report.</span></span>

### <a name="media-quality-comparison-report-metrics"></a><span data-ttu-id="b01e2-175">媒體品質比較報告計量</span><span class="sxs-lookup"><span data-stu-id="b01e2-175">Media Quality Comparison Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b01e2-176">名稱</span><span class="sxs-lookup"><span data-stu-id="b01e2-176">Name</span></span></th>
<th><span data-ttu-id="b01e2-177">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="b01e2-177">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="b01e2-178">描述</span><span class="sxs-lookup"><span data-stu-id="b01e2-178">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-179"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-179"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-180">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-180">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-181">通話總數。</span><span class="sxs-lookup"><span data-stu-id="b01e2-181">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-182"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-182"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-183">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-183">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-184">平均量 MOS （平均意見分數） 降低在通話期間發生的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-184">Average amount of MOS (mean opinion score) degradation experienced during a call.</span></span> <span data-ttu-id="b01e2-185">降低值可介於 0.0 的低到高的 5.0;為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="b01e2-185">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="b01e2-186">在過去，平均意見分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="b01e2-186">Historically, mean opinion scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="b01e2-187">Lync Server 使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="b01e2-187">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="b01e2-188">高的效能下降值會造成壅塞;缺少的頻寬;無線壅塞干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="b01e2-188">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="b01e2-189">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-189">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-190"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-190"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-191">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-191">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-192">歸類為不良的通話總數。</span><span class="sxs-lookup"><span data-stu-id="b01e2-192">The total number of calls classified as poor.</span></span> <span data-ttu-id="b01e2-193">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="b01e2-193">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-194"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-194"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-195">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-195">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-196">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="b01e2-196">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="b01e2-197">200 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="b01e2-197">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="b01e2-198">高的來回行程值可能被因國際電話路由;路由設定錯誤;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="b01e2-198">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="b01e2-199">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="b01e2-199">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-200"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-200"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-201">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-201">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-202">即時傳輸通訊協定 (RTP) 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="b01e2-202">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="b01e2-203">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率是通常會因壅塞;缺少的頻寬;無線壅塞或干擾;或超載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="b01e2-203">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="b01e2-204">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-204">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-205"><strong>抖動 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-205"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-206">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-206">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-207">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="b01e2-207">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="b01e2-208">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-208">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-209"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-209"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-210">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-210">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-211">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="b01e2-211">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="b01e2-212">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="b01e2-212">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b01e2-213"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-213"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-214">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-214">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-215">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="b01e2-215">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="b01e2-216">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="b01e2-216">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b01e2-217"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="b01e2-217"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="b01e2-218">否</span><span class="sxs-lookup"><span data-stu-id="b01e2-218">No</span></span></p></td>
<td><p><span data-ttu-id="b01e2-219">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="b01e2-219">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="b01e2-220">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="b01e2-220">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

