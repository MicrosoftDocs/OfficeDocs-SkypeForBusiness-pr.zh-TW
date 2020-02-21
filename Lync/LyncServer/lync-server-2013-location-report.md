---
title: Lync Server 2013： 位置報告
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
ms.openlocfilehash: 2035d66d9b690a351a9b286eeff378ec0a36c1f9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-report-in-lync-server-2013"></a><span data-ttu-id="e4b18-102">Lync Server 2013 中的位置報告</span><span class="sxs-lookup"><span data-stu-id="e4b18-102">Location Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4b18-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="e4b18-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e4b18-104">位置報告提供有關通話品質計量依據網路位置資訊 (也就是由網路子網路)。</span><span class="sxs-lookup"><span data-stu-id="e4b18-104">The Location Report provides information about call quality metrics grouped by network location (that is, by network subnet).</span></span> <span data-ttu-id="e4b18-105">如果您的使用者遇到其通話的問題，這份報告可以協助您判斷如果這些問題時遇到的普遍，或者主要限於特定的網路區段。</span><span class="sxs-lookup"><span data-stu-id="e4b18-105">If your users are experiencing problems with their calls, this report can help you determine if those problems are widespread or if they are largely confined to a given network segment.</span></span>

<div>

## <a name="accessing-the-location-report"></a><span data-ttu-id="e4b18-106">存取位置報告</span><span class="sxs-lookup"><span data-stu-id="e4b18-106">Accessing the Location Report</span></span>

<span data-ttu-id="e4b18-107">從監視報告首頁存取位置報告。</span><span class="sxs-lookup"><span data-stu-id="e4b18-107">The Location Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="e4b18-108">您可以按一下向下切入 Call List Report 下列計量之一：</span><span class="sxs-lookup"><span data-stu-id="e4b18-108">You can drill down to the Call List Report by clicking either of the following metrics:</span></span>

  - <span data-ttu-id="e4b18-109">[通話數</span><span class="sxs-lookup"><span data-stu-id="e4b18-109">Call volume</span></span>

  - <span data-ttu-id="e4b18-110">通話不良百分比</span><span class="sxs-lookup"><span data-stu-id="e4b18-110">Poor call percentage</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e4b18-111">篩選</span><span class="sxs-lookup"><span data-stu-id="e4b18-111">Filters</span></span>

<span data-ttu-id="e4b18-112">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="e4b18-112">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="e4b18-113">例如，位置報告可讓您篩選上為呼叫起源的所在位置，或是否通話中發生了在無線或有線的連線等項目。</span><span class="sxs-lookup"><span data-stu-id="e4b18-113">For example, the Location Report enables you to filter on such things as the location where a call was originated or whether the call took place on a wireless or a wired connection.</span></span> <span data-ttu-id="e4b18-114">您也可以選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="e4b18-114">You can also choose how data should be grouped.</span></span> <span data-ttu-id="e4b18-115">在這種情況下，通話會按照小時、日、星期或月而加以分組。</span><span class="sxs-lookup"><span data-stu-id="e4b18-115">In this case, calls are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="e4b18-116">下表列出您可以搭配位置報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="e4b18-116">The following table lists the filters that you can use with the Location Report.</span></span>

### <a name="location-report-filters"></a><span data-ttu-id="e4b18-117">位置報告篩選器</span><span class="sxs-lookup"><span data-stu-id="e4b18-117">Location Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4b18-118">名稱</span><span class="sxs-lookup"><span data-stu-id="e4b18-118">Name</span></span></th>
<th><span data-ttu-id="e4b18-119">描述</span><span class="sxs-lookup"><span data-stu-id="e4b18-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-120"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-120"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-p104">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p104">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="e4b18-123">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e4b18-123">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e4b18-p105">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p105">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e4b18-126">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="e4b18-126">7/7/2012</span></span></p>
<p><span data-ttu-id="e4b18-127">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e4b18-127">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e4b18-128">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="e4b18-128">7/3/2012</span></span></p>
<p><span data-ttu-id="e4b18-129">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e4b18-129">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-130"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-130"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-p106">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p106">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="e4b18-133">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="e4b18-133">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="e4b18-p107">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p107">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="e4b18-136">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="e4b18-136">7/7/2012</span></span></p>
<p><span data-ttu-id="e4b18-137">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="e4b18-137">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="e4b18-138">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="e4b18-138">7/3/2012</span></span></p>
<p><span data-ttu-id="e4b18-139">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="e4b18-139">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-140"><strong>來電者位置</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-140"><strong>Caller location</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-141">撥打通話之使用者的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-141">IP subnet of the user who placed the call.</span></span> <span data-ttu-id="e4b18-142">您只能選取<strong>[全部]</strong>表示所有子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-142">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-143"><strong>被呼叫者位置</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-143"><strong>Callee location</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-144">接到電話之使用者的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-144">IP subnet of the user who received the call.</span></span> <span data-ttu-id="e4b18-145">您只能選取<strong>[全部]</strong>表示所有子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-145">You can only select <strong>[All]</strong> to indicate all subnets.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-146"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-146"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-p110">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p110">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e4b18-149">[全部]</span><span class="sxs-lookup"><span data-stu-id="e4b18-149">[All]</span></span></p></li>
<li><p><span data-ttu-id="e4b18-150">有線</span><span class="sxs-lookup"><span data-stu-id="e4b18-150">Wired</span></span></p></li>
<li><p><span data-ttu-id="e4b18-151">無線</span><span class="sxs-lookup"><span data-stu-id="e4b18-151">Wireless</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-152"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-152"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e4b18-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ol>
<li><p><span data-ttu-id="e4b18-155">[全部]</span><span class="sxs-lookup"><span data-stu-id="e4b18-155">[All]</span></span></p></li>
<li><p><span data-ttu-id="e4b18-156">VPN</span><span class="sxs-lookup"><span data-stu-id="e4b18-156">VPN</span></span></p></li>
<li><p><span data-ttu-id="e4b18-157">非 VPN</span><span class="sxs-lookup"><span data-stu-id="e4b18-157">Non-VPN</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="e4b18-158">計量</span><span class="sxs-lookup"><span data-stu-id="e4b18-158">Metrics</span></span>

<span data-ttu-id="e4b18-159">下表列出位置報告中提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="e4b18-159">The following table lists the information provided in the Location Report.</span></span>

### <a name="location-report-metrics"></a><span data-ttu-id="e4b18-160">位置報告計量</span><span class="sxs-lookup"><span data-stu-id="e4b18-160">Location Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e4b18-161">名稱</span><span class="sxs-lookup"><span data-stu-id="e4b18-161">Name</span></span></th>
<th><span data-ttu-id="e4b18-162">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="e4b18-162">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e4b18-163">說明</span><span class="sxs-lookup"><span data-stu-id="e4b18-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-164"><strong>呼叫者子網路</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-164"><strong>Caller subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-165">否</span><span class="sxs-lookup"><span data-stu-id="e4b18-165">No</span></span></p></td>
<td><p><span data-ttu-id="e4b18-166">撥打通話之使用者的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-166">IP subnet of the user who placed the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-167"><strong>被呼叫者子網路</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-167"><strong>Callee subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-168">否</span><span class="sxs-lookup"><span data-stu-id="e4b18-168">No</span></span></p></td>
<td><p><span data-ttu-id="e4b18-169">接到電話之使用者的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="e4b18-169">IP subnet of the user who received the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-170"><strong>[通話數</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-170"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-171">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-171">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-172">撥打的通話總數。</span><span class="sxs-lookup"><span data-stu-id="e4b18-172">Total number of calls placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-173"><strong>通話不良百分比</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-173"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-174">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-174">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-175">通話歸類為不良通話百分比。</span><span class="sxs-lookup"><span data-stu-id="e4b18-175">Percentage of calls classified as poor calls.</span></span> <span data-ttu-id="e4b18-176">通話不良是指至少一項計算超出允許的值 （例如，通話過多的抖動） 任何來電。</span><span class="sxs-lookup"><span data-stu-id="e4b18-176">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-177"><strong>往返時間 （毫秒）</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-177"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-178">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-178">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-179">平均量 （以毫秒為單位） 所需的即時傳輸通訊協定 (RTP) 封包傳輸至另一個端點，再重新。</span><span class="sxs-lookup"><span data-stu-id="e4b18-179">Average amount of (in milliseconds) required for a real-time transport protocol (RTP) packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="e4b18-180">100 毫秒或更低的來回行程時間會被視為的可接受的品質。</span><span class="sxs-lookup"><span data-stu-id="e4b18-180">Round-trip times of 100 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="e4b18-181">高的來回行程值可以是國際電話路由，路由設定錯誤或已多載的媒體伺服器所造成。</span><span class="sxs-lookup"><span data-stu-id="e4b18-181">High round-trip values can be caused by international call routing, a routing misconfiguration, or an overloaded media server.</span></span> <span data-ttu-id="e4b18-182">高的來回行程時間會導致雙向、 即時音訊交談的問題。</span><span class="sxs-lookup"><span data-stu-id="e4b18-182">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-183"><strong>降低 (MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-183"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-184">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-184">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-185">平均量平均意見分數 (MOS) 降低在通話期間發生。</span><span class="sxs-lookup"><span data-stu-id="e4b18-185">Average amount of mean opinion score (MOS) degradation experienced during a call.</span></span> <span data-ttu-id="e4b18-186">為 [高] 的 5.0，降低值可介於 0.0 的低。</span><span class="sxs-lookup"><span data-stu-id="e4b18-186">Degradation values can range from a low of 0.0 to a high of 5.0.</span></span> <span data-ttu-id="e4b18-187">為 0.5 或更低的值代表可接受的效能下降。</span><span class="sxs-lookup"><span data-stu-id="e4b18-187">A value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="e4b18-188">在過去，mean 選項分數已計算方式是讓使用者在 1 到 5 的小數位數率通話品質。</span><span class="sxs-lookup"><span data-stu-id="e4b18-188">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="e4b18-189">在 Lync Server 中，Lync Server 會使用一組演算法來預測如何使用者會有分級通話。</span><span class="sxs-lookup"><span data-stu-id="e4b18-189">In Lync Server, Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="e4b18-190">高的效能下降值會造成壅塞，缺少的頻寬、 無線壅塞或干擾，或已多載的媒體伺服器或端點。</span><span class="sxs-lookup"><span data-stu-id="e4b18-190">High degradation values can be caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="e4b18-191">高降低的情形會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="e4b18-191">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-192"><strong>封包遺失</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-192"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-193">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-193">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-194">RTP 封包遺失平均速率。</span><span class="sxs-lookup"><span data-stu-id="e4b18-194">Average rate of RTP packet loss.</span></span> <span data-ttu-id="e4b18-195">（封包遺失發生於 RTP 封包，用於傳輸音訊和視訊在網際網路上的通訊協定無法到達其目的地）。高遺失率通常會因擁塞、 缺乏頻寬、 無線壅塞或干擾，或已多載的媒體伺服器。</span><span class="sxs-lookup"><span data-stu-id="e4b18-195">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion, lack of bandwidth, wireless congestion or interference, or an overloaded media server.</span></span> <span data-ttu-id="e4b18-196">封包遺失通常會導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="e4b18-196">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-197"><strong>抖動</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-197"><strong>Jitter</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-198">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-198">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-199">偵測到之間 RTP 封包抵達的平均抖動值。</span><span class="sxs-lookup"><span data-stu-id="e4b18-199">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="e4b18-200">(抖動是評量&quot;shakiness&quot;的呼叫。)高抖動值通常是造成壅塞或超載的媒體伺服器，並導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="e4b18-200">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-201"><strong>修復隱藏比率</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-201"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-202">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-202">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-203">之隱藏樣本總數總計的音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e4b18-203">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e4b18-204">（隱藏的音訊取樣是用來平滑出通常會因首的網路封包突然轉換技術）。高的值可指出重大的層級套用的遺失隱藏聲音因封包遺失及抖動，導致扭曲或遺失音訊。</span><span class="sxs-lookup"><span data-stu-id="e4b18-204">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e4b18-205"><strong>修復延伸的比率</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-205"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-206">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-206">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-207">範例總數總計的延伸音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e4b18-207">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="e4b18-208">（延伸的音訊是已擴充為維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例拉長因抖動，而導致音訊發音機械或扭曲。</span><span class="sxs-lookup"><span data-stu-id="e4b18-208">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e4b18-209"><strong>修復壓縮的比率</strong></span><span class="sxs-lookup"><span data-stu-id="e4b18-209"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="e4b18-210">是</span><span class="sxs-lookup"><span data-stu-id="e4b18-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="e4b18-211">範例總數的壓縮音訊樣本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e4b18-211">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="e4b18-212">（壓縮的音訊是已壓縮，並維持已偵測到的繞邊的網路封包時通話品質的音訊）。高的值可指出重大的層級的範例壓縮因抖動，而導致音訊發音加速或失真。</span><span class="sxs-lookup"><span data-stu-id="e4b18-212">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

