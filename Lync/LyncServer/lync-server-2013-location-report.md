---
title: Lync Server 2013：位置報告
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
ms.openlocfilehash: 4bb42f32313acd3609b21180ddaef90c53c27564
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="a1a6e-102">Lync Server 2013 中的位置報告</span><span class="sxs-lookup"><span data-stu-id="a1a6e-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1a6e-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a1a6e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a1a6e-104">位置報告會提供通話品質指標的相關資訊，依網路位置（也就是網路子網）分組。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-104">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="a1a6e-105">如果您的使用者遇到通話問題，此報告可協助您判斷這些問題是否已廣泛分佈，或是主要限制在指定的網路區段中。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-105">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="a1a6e-106">存取位置報告</span><span class="sxs-lookup"><span data-stu-id="a1a6e-106">Accessing the Location Report</span></span>

<span data-ttu-id="a1a6e-107">位置報告是從 [監控報告] 首頁存取。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-107">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="a1a6e-108">您可以按一下下列其中一個度量，向下切入 [通話清單] 報告：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-108">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="a1a6e-109">通話量</span><span class="sxs-lookup"><span data-stu-id="a1a6e-109">Call volume</span></span>

  - <span data-ttu-id="a1a6e-110">通話百分比太差</span><span class="sxs-lookup"><span data-stu-id="a1a6e-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="a1a6e-111">濾鏡</span><span class="sxs-lookup"><span data-stu-id="a1a6e-111">Filters</span></span>

<span data-ttu-id="a1a6e-112">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a1a6e-113">例如，[位置] 報告可讓您篩選諸如通話來源的位置，或是通話是在無線或有線連線中進行。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="a1a6e-114">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="a1a6e-115">在這種情況下，通話會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="a1a6e-116">下表列出可與位置報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="a1a6e-117">位置報表篩選</span><span class="sxs-lookup"><span data-stu-id="a1a6e-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1a6e-118">名稱</span><span class="sxs-lookup"><span data-stu-id="a1a6e-118">Name</span></span></th>
<th><span data-ttu-id="a1a6e-119">說明</span><span class="sxs-lookup"><span data-stu-id="a1a6e-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-120"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-121">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-121">Start date/time for the time range.</span></span> <span data-ttu-id="a1a6e-122">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-122">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a1a6e-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a1a6e-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a1a6e-124">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-124">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a1a6e-125">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-125">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a1a6e-126">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a1a6e-126">7/7/2012</span></span></p>
<p><span data-ttu-id="a1a6e-127">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a1a6e-128">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a1a6e-128">7/3/2012</span></span></p>
<p><span data-ttu-id="a1a6e-129">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-130"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-131">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-131">End date/time for the time range.</span></span> <span data-ttu-id="a1a6e-132">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-132">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a1a6e-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a1a6e-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a1a6e-134">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-134">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a1a6e-135">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-135">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a1a6e-136">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a1a6e-136">7/7/2012</span></span></p>
<p><span data-ttu-id="a1a6e-137">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a1a6e-138">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a1a6e-138">7/3/2012</span></span></p>
<p><span data-ttu-id="a1a6e-139">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-140"><strong>來電者位置</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-141">發出呼叫之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="a1a6e-142">您只可以選取<strong>[全部]</strong>來指示所有子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-143"><strong>被呼叫者位置</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-144">接收通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="a1a6e-145">您只可以選取<strong>[全部]</strong>來指示所有子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-146"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-147">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-147">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="a1a6e-148">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-148">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a1a6e-149">同時</span><span class="sxs-lookup"><span data-stu-id="a1a6e-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="a1a6e-150">有線</span><span class="sxs-lookup"><span data-stu-id="a1a6e-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="a1a6e-151">無線</span><span class="sxs-lookup"><span data-stu-id="a1a6e-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-152"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-153">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-153">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="a1a6e-154">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="a1a6e-154">Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="a1a6e-155">同時</span><span class="sxs-lookup"><span data-stu-id="a1a6e-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="a1a6e-156">點對點</span><span class="sxs-lookup"><span data-stu-id="a1a6e-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="a1a6e-157">非 VPN</span><span class="sxs-lookup"><span data-stu-id="a1a6e-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a1a6e-158">指標</span><span class="sxs-lookup"><span data-stu-id="a1a6e-158">Metrics</span></span>

<span data-ttu-id="a1a6e-159">下表列出位置報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="a1a6e-160">位置報告度量單位</span><span class="sxs-lookup"><span data-stu-id="a1a6e-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1a6e-161">名稱</span><span class="sxs-lookup"><span data-stu-id="a1a6e-161">Name</span></span></th>
<th><span data-ttu-id="a1a6e-162">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="a1a6e-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a1a6e-163">說明</span><span class="sxs-lookup"><span data-stu-id="a1a6e-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-164"><strong>來電者子網上</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-165">否</span><span class="sxs-lookup"><span data-stu-id="a1a6e-165">No</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-166">發出呼叫之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-167"><strong>被呼叫者子網上</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-168">否</span><span class="sxs-lookup"><span data-stu-id="a1a6e-168">No</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-169">接收通話之使用者的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-170"><strong>通話量</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-171">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-172">已發出的通話總次數。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-173"><strong>通話百分比太差</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-174">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-175">分類為不良通話的通話百分比。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="a1a6e-176">較差的通話是指至少其中一個測量的指標超過允許值（例如，遇到過度抖動的呼叫）的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-177"><strong>往返行程（毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-178">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-179">即時傳輸通訊協定（RTP）資料包移至另一個端點後再移回所需的平均（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-179">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="a1a6e-180">100毫秒或較低的往返行程時間會視為可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-180">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="a1a6e-181">高往返值可能是由國際呼叫路由、路由配置錯誤或超載媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-181">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="a1a6e-182">較高的往返行程時間會造成使用雙向即時音訊交談的困難。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-182">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-183"><strong>下降（MOS）</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-184">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-185">通話期間平均觀念得分（MOS）的平均數量下降。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="a1a6e-186">降級值的範圍可從低0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="a1a6e-187">0.5 或較低的值代表可接受的下降。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="a1a6e-188">過去，平均選項分數是由使用者以1到5的比例來評定通話品質的結果。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="a1a6e-189">在 Lync Server 中，Lync Server 會使用一組演算法來預測使用者對通話進行評分的方式。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="a1a6e-190">高降級值可能是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載的媒體伺服器或端點所造成。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-190">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="a1a6e-191">高品質的結果會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-191">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-192"><strong>資料包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-193">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-194">RTP 資料包遺失的平均速率。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-194">Average rate of RTP packet loss.</span></span> <span data-ttu-id="a1a6e-195">（當 RTP 資料包（這是一種用來透過網際網路傳送音訊和影片的通訊協定）無法送達目的地時，會發生資料包遺失。高遺失率通常是由於擁塞、缺乏頻寬、無線擁塞或干擾或超載媒體伺服器而造成。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-195">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="a1a6e-196">[資料包遺失] 通常會導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-196">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-197"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-198">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-199">在 RTP 資料包抵達之間檢測到的平均抖動。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="a1a6e-200">（抖動是通話&quot;shakiness&quot;的量度。）高抖動值通常是由擁塞或超載的媒體伺服器所造成，而且會造成失真或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-201"><strong>Healer 隱藏比例</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-202">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-203">隱藏的音訊樣本與總樣本數的平均比率。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-203">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="a1a6e-204">（隱藏的音訊範例是一種技術，用來平滑可能由網路資料包所造成的突然轉換。）[高值] 表示由於資料包遺失或抖動所造成的大量 concealment 損失，並導致聲音失真或遺失。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-204">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1a6e-205"><strong>Healer 延伸比率</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-206">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-207">延伸音訊樣本的平均比例與總樣本數的總和。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-207">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="a1a6e-208">（已延伸的音訊是已展開的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表由抖動所造成的大量樣本拉伸層級，並導致音訊聲音不在機器人或失真中。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-208">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1a6e-209"><strong>Healer 壓縮比率</strong></span><span class="sxs-lookup"><span data-stu-id="a1a6e-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="a1a6e-210">是</span><span class="sxs-lookup"><span data-stu-id="a1a6e-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="a1a6e-211">壓縮之音訊樣本的平均比率為樣本總數。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-211">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="a1a6e-212">（壓縮的音訊是已壓縮的音訊，可協助您在偵測到網路資料包時維持通話品質。）高值代表抖動所造成的大量樣本壓縮層級，而導致音訊聲音速度快或失真。</span><span class="sxs-lookup"><span data-stu-id="a1a6e-212">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

