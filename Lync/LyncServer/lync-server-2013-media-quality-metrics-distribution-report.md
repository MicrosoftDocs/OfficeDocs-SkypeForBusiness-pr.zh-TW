---
title: Lync Server 2013：媒體質量計量散佈報告
description: Lync Server 2013：媒體質量計量散佈報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: def56580477dadf989268e1fc24fcec7776c00d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548149"
---
# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="ba310-103">Lync Server 2013 中的媒體質量計量散佈報告</span><span class="sxs-lookup"><span data-stu-id="ba310-103">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba310-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="ba310-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="ba310-105">媒體質量計量散佈報告可讓您查看顯示品質狀況（如抖動或封包遺失）之分配值的圖形。</span><span class="sxs-lookup"><span data-stu-id="ba310-105">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="ba310-106">例如，假設您的使用者總共撥打了10次通話;這10個通話會報告下列往返時間：</span><span class="sxs-lookup"><span data-stu-id="ba310-106">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba310-107">通話號碼</span><span class="sxs-lookup"><span data-stu-id="ba310-107">Call Number</span></span></th>
<th><span data-ttu-id="ba310-108">往返時間 (毫秒) </span><span class="sxs-lookup"><span data-stu-id="ba310-108">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba310-109">1 </span><span class="sxs-lookup"><span data-stu-id="ba310-109">1</span></span></p></td>
<td><p><span data-ttu-id="ba310-110">50</span><span class="sxs-lookup"><span data-stu-id="ba310-110">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-111">第</span><span class="sxs-lookup"><span data-stu-id="ba310-111">2</span></span></p></td>
<td><p><span data-ttu-id="ba310-112">50</span><span class="sxs-lookup"><span data-stu-id="ba310-112">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-113">個</span><span class="sxs-lookup"><span data-stu-id="ba310-113">3</span></span></p></td>
<td><p><span data-ttu-id="ba310-114">50</span><span class="sxs-lookup"><span data-stu-id="ba310-114">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-115">4 </span><span class="sxs-lookup"><span data-stu-id="ba310-115">4</span></span></p></td>
<td><p><span data-ttu-id="ba310-116">50</span><span class="sxs-lookup"><span data-stu-id="ba310-116">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-117">5 </span><span class="sxs-lookup"><span data-stu-id="ba310-117">5</span></span></p></td>
<td><p><span data-ttu-id="ba310-118">50</span><span class="sxs-lookup"><span data-stu-id="ba310-118">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-119">6 </span><span class="sxs-lookup"><span data-stu-id="ba310-119">6</span></span></p></td>
<td><p><span data-ttu-id="ba310-120">50</span><span class="sxs-lookup"><span data-stu-id="ba310-120">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-121">7 </span><span class="sxs-lookup"><span data-stu-id="ba310-121">7</span></span></p></td>
<td><p><span data-ttu-id="ba310-122">50</span><span class="sxs-lookup"><span data-stu-id="ba310-122">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-123">8 </span><span class="sxs-lookup"><span data-stu-id="ba310-123">8</span></span></p></td>
<td><p><span data-ttu-id="ba310-124">4550</span><span class="sxs-lookup"><span data-stu-id="ba310-124">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-125">9 </span><span class="sxs-lookup"><span data-stu-id="ba310-125">9</span></span></p></td>
<td><p><span data-ttu-id="ba310-126">50</span><span class="sxs-lookup"><span data-stu-id="ba310-126">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-127">10 </span><span class="sxs-lookup"><span data-stu-id="ba310-127">10</span></span></p></td>
<td><p><span data-ttu-id="ba310-128">50</span><span class="sxs-lookup"><span data-stu-id="ba310-128">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ba310-129">這些往返時間的平均值是500毫秒 (5000 除以 10) 。</span><span class="sxs-lookup"><span data-stu-id="ba310-129">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="ba310-130">500毫秒是極大的往返時間;因此，您可能會相信，網路擁塞發生嚴重問題。</span><span class="sxs-lookup"><span data-stu-id="ba310-130">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="ba310-131"> (長的往返時間通常是超載網路的結果。 ) </span><span class="sxs-lookup"><span data-stu-id="ba310-131">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="ba310-132">當然，在現實中，90% 的來電已有極好的來回行程時間;您只會有一個會使整體結果歪斜的錯誤通話。</span><span class="sxs-lookup"><span data-stu-id="ba310-132">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="ba310-133">如果您只查看平均往返時間，您可能會跳到錯誤的結論。</span><span class="sxs-lookup"><span data-stu-id="ba310-133">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="ba310-134">媒體質量計量散佈報告可讓您透過顯示指定指標 (例如來回行程時間) ，來協助您避免跳到錯誤結論。</span><span class="sxs-lookup"><span data-stu-id="ba310-134">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="ba310-135">這兩個圖形可協助您明確您有九個非常好的呼叫和一個極壞的通話。</span><span class="sxs-lookup"><span data-stu-id="ba310-135">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="ba310-136">無可否認，您可能仍要進一步調查此呼叫;不過，10個通話中的九個事實很不錯，這表示沒有理由對您的網路進行任何重大的變更，至少此時間不是這麼。</span><span class="sxs-lookup"><span data-stu-id="ba310-136">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="ba310-137">篩選</span><span class="sxs-lookup"><span data-stu-id="ba310-137">Filters</span></span>

<span data-ttu-id="ba310-138">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="ba310-138">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="ba310-139">下表列出您可以搭配媒體質量計量散佈報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="ba310-139">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="ba310-140">媒體質量計量散佈報告篩選器</span><span class="sxs-lookup"><span data-stu-id="ba310-140">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ba310-141">名稱</span><span class="sxs-lookup"><span data-stu-id="ba310-141">Name</span></span></th>
<th><span data-ttu-id="ba310-142">描述</span><span class="sxs-lookup"><span data-stu-id="ba310-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ba310-143"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-143"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ba310-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ba310-146">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ba310-146">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba310-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="ba310-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba310-149">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ba310-149">7/7/2012</span></span></p>
<p><span data-ttu-id="ba310-150">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="ba310-150">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba310-151">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ba310-151">7/3/2012</span></span></p>
<p><span data-ttu-id="ba310-152">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="ba310-152">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-153"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-153"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ba310-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ba310-156">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ba310-156">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ba310-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="ba310-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ba310-159">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ba310-159">7/7/2012</span></span></p>
<p><span data-ttu-id="ba310-160">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="ba310-160">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ba310-161">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ba310-161">7/3/2012</span></span></p>
<p><span data-ttu-id="ba310-162">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="ba310-162">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-163"><strong>X 軸的最小值</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-163"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-164">要在圖形的 X 軸上顯示的最低值。</span><span class="sxs-lookup"><span data-stu-id="ba310-164">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-165"><strong>X 軸的最大值</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-165"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-166">要在圖形的 X 軸上顯示的最高值。</span><span class="sxs-lookup"><span data-stu-id="ba310-166">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-167"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-167"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-p110">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ba310-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba310-170">一切</span><span class="sxs-lookup"><span data-stu-id="ba310-170">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba310-171">內部</span><span class="sxs-lookup"><span data-stu-id="ba310-171">Internal</span></span></p></li>
<li><p><span data-ttu-id="ba310-172">外部</span><span class="sxs-lookup"><span data-stu-id="ba310-172">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ba310-173"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-173"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ba310-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba310-176">一切</span><span class="sxs-lookup"><span data-stu-id="ba310-176">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba310-177">VPN</span><span class="sxs-lookup"><span data-stu-id="ba310-177">VPN</span></span></p></li>
<li><p><span data-ttu-id="ba310-178">非 VPN</span><span class="sxs-lookup"><span data-stu-id="ba310-178">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ba310-179"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="ba310-179"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="ba310-p112">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ba310-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ba310-182">一切</span><span class="sxs-lookup"><span data-stu-id="ba310-182">[All]</span></span></p></li>
<li><p><span data-ttu-id="ba310-183">有線</span><span class="sxs-lookup"><span data-stu-id="ba310-183">Wired</span></span></p></li>
<li><p><span data-ttu-id="ba310-184">無線</span><span class="sxs-lookup"><span data-stu-id="ba310-184">Wireless</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

