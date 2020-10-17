---
title: Lync Server 2013：位置報告
description: Lync Server 2013：位置報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Report
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615035(v=OCS.15)
ms:contentKeyID: 48185641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b819bcffeee0795cd39d3dde3e38fbd9e4a1b7c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569469"
---
# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="e02dc-103">Lync Server 2013 中的位置報告</span><span class="sxs-lookup"><span data-stu-id="e02dc-103">Location Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e02dc-104">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e02dc-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e02dc-105">位置報告提供依網路位置 (，也就是由網路子網) 分組之通話品質計量的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e02dc-105">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="e02dc-106">如果使用者遇到來電問題，此報告可協助您判斷這些問題是否受到廣泛使用，或是主要局限于指定的網段。</span><span class="sxs-lookup"><span data-stu-id="e02dc-106">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="e02dc-107">存取位置報告</span><span class="sxs-lookup"><span data-stu-id="e02dc-107">Accessing the Location Report</span></span>

<span data-ttu-id="e02dc-108">您可以從監控報告首頁存取位置報告。</span><span class="sxs-lookup"><span data-stu-id="e02dc-108">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e02dc-109">您可以按一下下列其中一項度量，向下流覽通話清單報告：</span><span class="sxs-lookup"><span data-stu-id="e02dc-109">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e02dc-110">通話數量</span><span class="sxs-lookup"><span data-stu-id="e02dc-110">Call volume</span></span>

  - <span data-ttu-id="e02dc-111">通話百分比不佳</span><span class="sxs-lookup"><span data-stu-id="e02dc-111">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e02dc-112">篩選</span><span class="sxs-lookup"><span data-stu-id="e02dc-112">Filters</span></span>

<span data-ttu-id="e02dc-113">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="e02dc-113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e02dc-114">例如，位置報告可讓您篩選出呼叫來源所在的位置，或是呼叫是否發生在無線或有線連線上。</span><span class="sxs-lookup"><span data-stu-id="e02dc-114">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="e02dc-115">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="e02dc-115">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e02dc-116">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="e02dc-116">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e02dc-117">下表列出您可以搭配位置報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="e02dc-117">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="e02dc-118">位置報表篩選</span><span class="sxs-lookup"><span data-stu-id="e02dc-118">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e02dc-119">名稱</span><span class="sxs-lookup"><span data-stu-id="e02dc-119">Name</span></span></th>
<th><span data-ttu-id="e02dc-120">描述</span><span class="sxs-lookup"><span data-stu-id="e02dc-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-121"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-121"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-p104">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e02dc-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e02dc-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e02dc-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e02dc-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e02dc-127">7/7/2012</span></span></p>
<p><span data-ttu-id="e02dc-128">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e02dc-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e02dc-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e02dc-129">7/3/2012</span></span></p>
<p><span data-ttu-id="e02dc-130">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e02dc-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-131"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-131"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e02dc-134">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e02dc-134">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e02dc-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e02dc-137">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="e02dc-137">7/7/2012</span></span></p>
<p><span data-ttu-id="e02dc-138">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e02dc-138">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e02dc-139">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="e02dc-139">7/3/2012</span></span></p>
<p><span data-ttu-id="e02dc-140">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e02dc-140">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-141"><strong>來電者位置</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-141"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-142">撥打通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-142">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="e02dc-143">您只可以選取 <strong>[全部]</strong> ，以表示所有子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-143">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-144"><strong>被呼叫者位置</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-144"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-145">接收通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-145">IP subnet of the user who received the call.</span></span> <span data-ttu-id="e02dc-146">您只可以選取 <strong>[全部]</strong> ，以表示所有子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-146">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-147"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-147"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-p110">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e02dc-150">一切</span><span class="sxs-lookup"><span data-stu-id="e02dc-150">[All]</span></span></p></li>
<li><p><span data-ttu-id="e02dc-151">有線</span><span class="sxs-lookup"><span data-stu-id="e02dc-151">Wired</span></span></p></li>
<li><p><span data-ttu-id="e02dc-152">無線</span><span class="sxs-lookup"><span data-stu-id="e02dc-152">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-153"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-153"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e02dc-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e02dc-156">一切</span><span class="sxs-lookup"><span data-stu-id="e02dc-156">[All]</span></span></p></li>
<li><p><span data-ttu-id="e02dc-157">VPN</span><span class="sxs-lookup"><span data-stu-id="e02dc-157">VPN</span></span></p></li>
<li><p><span data-ttu-id="e02dc-158">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e02dc-158">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e02dc-159">指標</span><span class="sxs-lookup"><span data-stu-id="e02dc-159">Metrics</span></span>

<span data-ttu-id="e02dc-160">下表列出位置報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="e02dc-160">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="e02dc-161">位置報告度量</span><span class="sxs-lookup"><span data-stu-id="e02dc-161">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e02dc-162">姓名</span><span class="sxs-lookup"><span data-stu-id="e02dc-162">Name</span></span></th>
<th><span data-ttu-id="e02dc-163">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="e02dc-163">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e02dc-164">描述</span><span class="sxs-lookup"><span data-stu-id="e02dc-164">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-165"><strong>來電者子網</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-165"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-166">否</span><span class="sxs-lookup"><span data-stu-id="e02dc-166">No</span></span></p></td>
<td><p><span data-ttu-id="e02dc-167">撥打通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-167">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-168"><strong>被呼叫者子網</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-168"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-169">否</span><span class="sxs-lookup"><span data-stu-id="e02dc-169">No</span></span></p></td>
<td><p><span data-ttu-id="e02dc-170">接收通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="e02dc-170">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-171"><strong>通話數量</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-171"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-172">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-172">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-173">發出的呼叫總數。</span><span class="sxs-lookup"><span data-stu-id="e02dc-173">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-174"><strong>通話百分比不佳</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-174"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-175">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-175">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-176">分類為不良通話的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="e02dc-176">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="e02dc-177">不佳的來電是指至少有一個衡量的衡量值超出允許的值 (例如，來電已有過高的抖動) 。</span><span class="sxs-lookup"><span data-stu-id="e02dc-177">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-178"><strong>來回行程 (毫秒) </strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-178"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-179">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-179">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-180">即時傳輸通訊協定 (RTP) 封包移至另一個端點後再進行的平均 (量（毫秒）) 所需）。</span><span class="sxs-lookup"><span data-stu-id="e02dc-180">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="e02dc-181">在100毫秒或更少的來回行程時間，會考慮可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="e02dc-181">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e02dc-182">高來回行程值可能是由國際通話路由、路由配置錯誤或超載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="e02dc-182">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="e02dc-183">較高的往返時間會導致使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="e02dc-183">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-184"><strong>MOS) 降級 (</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-184"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-185">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-185">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-186">通話期間 (MOS) 效能的平均平均觀點量。</span><span class="sxs-lookup"><span data-stu-id="e02dc-186">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="e02dc-187">降級值的範圍從低0.0 到高5.0。</span><span class="sxs-lookup"><span data-stu-id="e02dc-187">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="e02dc-188">值0.5 或更少代表可接受的降級。</span><span class="sxs-lookup"><span data-stu-id="e02dc-188">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="e02dc-189">在過去，平均選項分數的計算方式是讓使用者以1到5的比例來評分通話的品質。</span><span class="sxs-lookup"><span data-stu-id="e02dc-189">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="e02dc-190">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話的評分方式。</span><span class="sxs-lookup"><span data-stu-id="e02dc-190">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="e02dc-191">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="e02dc-191">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="e02dc-192">高降級導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="e02dc-192">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-193"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-193"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-194">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-194">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-195">RTP 封包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="e02dc-195">Average rate of RTP packet loss.</span></span> <span data-ttu-id="e02dc-196">當 RTP 封包（用於透過網際網路傳送音訊和影片的通訊協定）無法抵達目的地時，就會發生 (封包遺失。 ) 高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="e02dc-196">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="e02dc-197">封包遺失通常會導致音訊失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="e02dc-197">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-198"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-198"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-199">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-199">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-200">在 RTP 封包抵達之間偵測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="e02dc-200">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e02dc-201"> (抖動是指 &quot; 通話的 shakiness 量 &quot; 。 ) 高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="e02dc-201">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-202"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-202"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-203">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-204">隱藏音訊樣本的平均比率與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="e02dc-204">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e02dc-205"> (隱藏的音訊範例是一種技術，它通常是因丟棄網路資料包而造成的強烈轉換。 ) 高值表示因封包遺失或抖動所造成的 concealment 損毀，並產生失真或遺失的音訊。</span><span class="sxs-lookup"><span data-stu-id="e02dc-205">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e02dc-206"><strong>修復延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-206"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-207">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-208">延伸音訊樣本的平均比例與樣本總數總數。</span><span class="sxs-lookup"><span data-stu-id="e02dc-208">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e02dc-209"> (延伸的音訊是已展開的音訊，可在偵測到網路封包時，維持通話品質。 ) 高值會指出抖動所造成的大量樣本拉伸層級，並導致音訊的自動或失真。</span><span class="sxs-lookup"><span data-stu-id="e02dc-209">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e02dc-210"><strong>修復壓縮比例</strong></span><span class="sxs-lookup"><span data-stu-id="e02dc-210"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e02dc-211">是</span><span class="sxs-lookup"><span data-stu-id="e02dc-211">Yes</span></span></p></td>
<td><p><span data-ttu-id="e02dc-212">壓縮音訊樣本的平均比率與樣本總數。</span><span class="sxs-lookup"><span data-stu-id="e02dc-212">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="e02dc-213"> (壓縮音訊是一種已壓縮的音訊，可在偵測到網路資料包時，維持通話品質。 ) 高值表示減少抖動所造成的範例壓縮層級，並導致音訊的快向或失真。</span><span class="sxs-lookup"><span data-stu-id="e02dc-213">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

