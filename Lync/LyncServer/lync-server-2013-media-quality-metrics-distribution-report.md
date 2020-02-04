---
title: Lync Server 2013：媒體質量度量值分佈報告
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
ms.openlocfilehash: 085525063d13c60dc1702ebf169fed92707675e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="5cd96-102">Lync Server 2013 中的媒體質量度量分佈報告</span><span class="sxs-lookup"><span data-stu-id="5cd96-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5cd96-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5cd96-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5cd96-104">媒體質量度量分佈報告可讓您查看顯示品質統計資料（例如抖動或資料包遺失）的分配值的圖形。</span><span class="sxs-lookup"><span data-stu-id="5cd96-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="5cd96-105">例如，假設您的使用者總共撥打10個通話;這10個通話會報告下列往返時間：</span><span class="sxs-lookup"><span data-stu-id="5cd96-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cd96-106">通話號碼</span><span class="sxs-lookup"><span data-stu-id="5cd96-106">Call Number</span></span></th>
<th><span data-ttu-id="5cd96-107">往返時間（毫秒）</span><span class="sxs-lookup"><span data-stu-id="5cd96-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-108">1</span><span class="sxs-lookup"><span data-stu-id="5cd96-108">1</span></span></p></td>
<td><p><span data-ttu-id="5cd96-109">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-110">2</span><span class="sxs-lookup"><span data-stu-id="5cd96-110">2</span></span></p></td>
<td><p><span data-ttu-id="5cd96-111">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-112">3</span><span class="sxs-lookup"><span data-stu-id="5cd96-112">3</span></span></p></td>
<td><p><span data-ttu-id="5cd96-113">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-114">4</span><span class="sxs-lookup"><span data-stu-id="5cd96-114">4</span></span></p></td>
<td><p><span data-ttu-id="5cd96-115">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-116">500</span><span class="sxs-lookup"><span data-stu-id="5cd96-116">5</span></span></p></td>
<td><p><span data-ttu-id="5cd96-117">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-118">6</span><span class="sxs-lookup"><span data-stu-id="5cd96-118">6</span></span></p></td>
<td><p><span data-ttu-id="5cd96-119">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-120">utf-7</span><span class="sxs-lookup"><span data-stu-id="5cd96-120">7</span></span></p></td>
<td><p><span data-ttu-id="5cd96-121">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-122">型</span><span class="sxs-lookup"><span data-stu-id="5cd96-122">8</span></span></p></td>
<td><p><span data-ttu-id="5cd96-123">4550</span><span class="sxs-lookup"><span data-stu-id="5cd96-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-124">9</span><span class="sxs-lookup"><span data-stu-id="5cd96-124">9</span></span></p></td>
<td><p><span data-ttu-id="5cd96-125">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-126">第</span><span class="sxs-lookup"><span data-stu-id="5cd96-126">10</span></span></p></td>
<td><p><span data-ttu-id="5cd96-127">50</span><span class="sxs-lookup"><span data-stu-id="5cd96-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5cd96-128">這些往返時間的平均值是500毫秒（5000除以10）。</span><span class="sxs-lookup"><span data-stu-id="5cd96-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="5cd96-129">500毫秒是相當大的往返時間;因此，您可能會相信您的網路擁塞存在嚴重問題。</span><span class="sxs-lookup"><span data-stu-id="5cd96-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="5cd96-130">（較長的往返時間通常是超載網路的結果）。</span><span class="sxs-lookup"><span data-stu-id="5cd96-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="5cd96-131">當然，事實上，90% 的通話時間有極好的往返行程;您只會有一個不正確的呼叫會將整體結果扭曲。</span><span class="sxs-lookup"><span data-stu-id="5cd96-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="5cd96-132">如果您只看看平均往返時間，可能會跳到一個非常錯誤的結論。</span><span class="sxs-lookup"><span data-stu-id="5cd96-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="5cd96-133">媒體質量度量分佈報告可讓您透過顯示指定指標的圖形化分佈（例如往返行程時間），協助您避免跳躍到錯誤的結論。</span><span class="sxs-lookup"><span data-stu-id="5cd96-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="5cd96-134">這些圖形可以讓您清楚，看看有九個好用的通話，還有一個非常糟糕的通話。</span><span class="sxs-lookup"><span data-stu-id="5cd96-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="5cd96-135">無可否認，您可能仍想要進一步調查該通話;不過，10個通話中有九不只是為了讓您的網路受到任何重大變更，至少不需要您在這個時間點。</span><span class="sxs-lookup"><span data-stu-id="5cd96-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="5cd96-136">濾鏡</span><span class="sxs-lookup"><span data-stu-id="5cd96-136">Filters</span></span>

<span data-ttu-id="5cd96-137">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="5cd96-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="5cd96-138">下表列出您可搭配媒體質量規格分佈報告使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="5cd96-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="5cd96-139">媒體質量度量分佈報表篩選</span><span class="sxs-lookup"><span data-stu-id="5cd96-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5cd96-140">名稱</span><span class="sxs-lookup"><span data-stu-id="5cd96-140">Name</span></span></th>
<th><span data-ttu-id="5cd96-141">說明</span><span class="sxs-lookup"><span data-stu-id="5cd96-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-142"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-143">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="5cd96-143">Start date/time for the time range.</span></span> <span data-ttu-id="5cd96-144">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5cd96-144">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="5cd96-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5cd96-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5cd96-146">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="5cd96-146">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="5cd96-147">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="5cd96-147">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5cd96-148">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5cd96-148">7/7/2012</span></span></p>
<p><span data-ttu-id="5cd96-149">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="5cd96-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5cd96-150">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5cd96-150">7/3/2012</span></span></p>
<p><span data-ttu-id="5cd96-151">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="5cd96-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-152"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-153">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="5cd96-153">End date/time for the time range.</span></span> <span data-ttu-id="5cd96-154">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5cd96-154">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="5cd96-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="5cd96-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="5cd96-156">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="5cd96-156">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="5cd96-157">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="5cd96-157">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="5cd96-158">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="5cd96-158">7/7/2012</span></span></p>
<p><span data-ttu-id="5cd96-159">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="5cd96-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="5cd96-160">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="5cd96-160">7/3/2012</span></span></p>
<p><span data-ttu-id="5cd96-161">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="5cd96-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-162"><strong>X 軸中的最小值</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-163">要在圖表的 X 軸上顯示的最小值。</span><span class="sxs-lookup"><span data-stu-id="5cd96-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-164"><strong>X 軸中的最大值</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-165">要在圖表的 X 軸上顯示的最高值。</span><span class="sxs-lookup"><span data-stu-id="5cd96-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-166"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-167">指出撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="5cd96-167">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="5cd96-168">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5cd96-168">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5cd96-169">同時</span><span class="sxs-lookup"><span data-stu-id="5cd96-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="5cd96-170">內部</span><span class="sxs-lookup"><span data-stu-id="5cd96-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="5cd96-171">外來</span><span class="sxs-lookup"><span data-stu-id="5cd96-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5cd96-172"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-173">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="5cd96-173">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="5cd96-174">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5cd96-174">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5cd96-175">同時</span><span class="sxs-lookup"><span data-stu-id="5cd96-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="5cd96-176">點對點</span><span class="sxs-lookup"><span data-stu-id="5cd96-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="5cd96-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="5cd96-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5cd96-178"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="5cd96-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="5cd96-179">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="5cd96-179">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="5cd96-180">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="5cd96-180">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5cd96-181">同時</span><span class="sxs-lookup"><span data-stu-id="5cd96-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="5cd96-182">有線</span><span class="sxs-lookup"><span data-stu-id="5cd96-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="5cd96-183">無線</span><span class="sxs-lookup"><span data-stu-id="5cd96-183">Wireless</span></span></p></li>
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

