---
title: Lync Server 2013： 媒體品質計量散佈報告
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
ms.openlocfilehash: 48ee62d2eee4ab6e18b3c0c07b46f79b779bcce1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a><span data-ttu-id="b4a94-102">Lync Server 2013 中的媒體品質計量散佈報告</span><span class="sxs-lookup"><span data-stu-id="b4a94-102">The Media Quality Metrics Distribution Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4a94-103">_**主題上次修改日期：** 2012年-06-06_</span><span class="sxs-lookup"><span data-stu-id="b4a94-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="b4a94-104">媒體品質計量散佈報告可讓您查看顯示經驗品質度量單位，例如抖動或封包遺失的通訊值的圖表。</span><span class="sxs-lookup"><span data-stu-id="b4a94-104">The Media Quality Metrics Distribution Report enables you to see a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span> <span data-ttu-id="b4a94-105">例如，假設您的使用者進行 10 電話; 總計這些 10 呼叫報告下列的來回時間：</span><span class="sxs-lookup"><span data-stu-id="b4a94-105">For example, suppose your users make a total of 10 phone calls; those 10 calls report the following roundtrip times:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a94-106">撥打號碼</span><span class="sxs-lookup"><span data-stu-id="b4a94-106">Call Number</span></span></th>
<th><span data-ttu-id="b4a94-107">往返時間 （毫秒）</span><span class="sxs-lookup"><span data-stu-id="b4a94-107">Roundtrip Time (milliseconds)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-108">1</span><span class="sxs-lookup"><span data-stu-id="b4a94-108">1</span></span></p></td>
<td><p><span data-ttu-id="b4a94-109">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-109">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-110">2</span><span class="sxs-lookup"><span data-stu-id="b4a94-110">2</span></span></p></td>
<td><p><span data-ttu-id="b4a94-111">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-111">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-112">3</span><span class="sxs-lookup"><span data-stu-id="b4a94-112">3</span></span></p></td>
<td><p><span data-ttu-id="b4a94-113">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-113">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-114">4</span><span class="sxs-lookup"><span data-stu-id="b4a94-114">4</span></span></p></td>
<td><p><span data-ttu-id="b4a94-115">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-115">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-116">5</span><span class="sxs-lookup"><span data-stu-id="b4a94-116">5</span></span></p></td>
<td><p><span data-ttu-id="b4a94-117">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-117">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-118">6 </span><span class="sxs-lookup"><span data-stu-id="b4a94-118">6</span></span></p></td>
<td><p><span data-ttu-id="b4a94-119">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-119">50</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-120">7 </span><span class="sxs-lookup"><span data-stu-id="b4a94-120">7</span></span></p></td>
<td><p><span data-ttu-id="b4a94-121">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-121">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-122">8 </span><span class="sxs-lookup"><span data-stu-id="b4a94-122">8</span></span></p></td>
<td><p><span data-ttu-id="b4a94-123">4550</span><span class="sxs-lookup"><span data-stu-id="b4a94-123">4550</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-124">9 </span><span class="sxs-lookup"><span data-stu-id="b4a94-124">9</span></span></p></td>
<td><p><span data-ttu-id="b4a94-125">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-125">50</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-126">10 </span><span class="sxs-lookup"><span data-stu-id="b4a94-126">10</span></span></p></td>
<td><p><span data-ttu-id="b4a94-127">50</span><span class="sxs-lookup"><span data-stu-id="b4a94-127">50</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b4a94-128">這些來回時間的平均值為 500 毫秒 (5000 除以 10)。</span><span class="sxs-lookup"><span data-stu-id="b4a94-128">The average for those roundtrip times is 500 milliseconds (5000 divided by 10).</span></span> <span data-ttu-id="b4a94-129">五百毫秒是非常大的來回時間;因此，您可能會認為您有網路壅塞嚴重的問題。</span><span class="sxs-lookup"><span data-stu-id="b4a94-129">Five hundred milliseconds is an extremely large roundtrip time; as a result, you might believe that you have a serious problem with network congestion.</span></span> <span data-ttu-id="b4a94-130">（長的來回時間通常是多載網路的結果）。</span><span class="sxs-lookup"><span data-stu-id="b4a94-130">(Long roundtrip times are typically the result of overloaded networks.)</span></span>

<span data-ttu-id="b4a94-131">在現實情況下，當然，90%的呼叫有極佳的來回行程時間;您只是有一個不正確的呼叫偏斜整體的結果。</span><span class="sxs-lookup"><span data-stu-id="b4a94-131">In reality, of course, 90% of your calls had excellent round trip times; you merely had one bad call that skewed the overall results.</span></span> <span data-ttu-id="b4a94-132">如果您只看看您可能會跳至非常錯誤的結論的平均往返時間。</span><span class="sxs-lookup"><span data-stu-id="b4a94-132">If you only look at the average roundtrip time you might jump to a very wrong conclusion.</span></span>

<span data-ttu-id="b4a94-133">媒體品質計量散佈報告可協助您避免跳至錯誤的結論顯示圖形的通訊群組的指定度量單位，（例如來回行程時間）。</span><span class="sxs-lookup"><span data-stu-id="b4a94-133">The Media Quality Metrics Distribution Report helps you avoid jumping to wrong conclusions by showing you a graphical distribution of a specified metric (such as round trip time).</span></span> <span data-ttu-id="b4a94-134">這些圖形可以協助使用者更清除您有九個很好的接聽電話和一個非常不良通話。</span><span class="sxs-lookup"><span data-stu-id="b4a94-134">These graphs can help make it clear that you had nine very good calls and one very bad call.</span></span> <span data-ttu-id="b4a94-135">不可否認，您可能仍想要進一步調查，一次呼叫;不過，超出 10 呼叫 9 是很好的事實建議是沒有變更任何激烈到您的網路，至少不在目前的理由。</span><span class="sxs-lookup"><span data-stu-id="b4a94-135">Admittedly, you might still want to further investigate that one call; however, the fact that 9 out of the 10 calls were very good suggests that there is no reason to make any drastic changes to your network, at least not at this point in time.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="b4a94-136">篩選</span><span class="sxs-lookup"><span data-stu-id="b4a94-136">Filters</span></span>

<span data-ttu-id="b4a94-137">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="b4a94-137">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="b4a94-138">下表列出您可以搭配媒體品質計量散佈報告篩選器。</span><span class="sxs-lookup"><span data-stu-id="b4a94-138">The following table lists the filters that you can use with the Media Quality Metrics Distribution Report.</span></span>

### <a name="media-quality-metrics-distribution-report-filters"></a><span data-ttu-id="b4a94-139">媒體品質計量散佈報告篩選器</span><span class="sxs-lookup"><span data-stu-id="b4a94-139">Media Quality Metrics Distribution Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4a94-140">名稱</span><span class="sxs-lookup"><span data-stu-id="b4a94-140">Name</span></span></th>
<th><span data-ttu-id="b4a94-141">描述</span><span class="sxs-lookup"><span data-stu-id="b4a94-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-142"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-142"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="b4a94-145">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b4a94-145">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b4a94-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b4a94-148">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="b4a94-148">7/7/2012</span></span></p>
<p><span data-ttu-id="b4a94-149">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="b4a94-149">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b4a94-150">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="b4a94-150">7/3/2012</span></span></p>
<p><span data-ttu-id="b4a94-151">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="b4a94-151">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-152"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-152"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="b4a94-155">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="b4a94-155">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="b4a94-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="b4a94-158">2012/7/7</span><span class="sxs-lookup"><span data-stu-id="b4a94-158">7/7/2012</span></span></p>
<p><span data-ttu-id="b4a94-159">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="b4a94-159">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="b4a94-160">2012/7/3</span><span class="sxs-lookup"><span data-stu-id="b4a94-160">7/3/2012</span></span></p>
<p><span data-ttu-id="b4a94-161">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="b4a94-161">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-162"><strong>在 x 軸上最小值</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-162"><strong>Minimum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-163">在此圖形的 X 軸上顯示的最低值。</span><span class="sxs-lookup"><span data-stu-id="b4a94-163">Lowest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-164"><strong>在 x 軸上的最大</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-164"><strong>Maximum in x axis</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-165">若要顯示在圖表 X 軸上的最高值。</span><span class="sxs-lookup"><span data-stu-id="b4a94-165">Highest value to be displayed on the X axis of the graph.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-166"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-166"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-p110">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p110">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4a94-169">[全部]</span><span class="sxs-lookup"><span data-stu-id="b4a94-169">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4a94-170">內部</span><span class="sxs-lookup"><span data-stu-id="b4a94-170">Internal</span></span></p></li>
<li><p><span data-ttu-id="b4a94-171">External</span><span class="sxs-lookup"><span data-stu-id="b4a94-171">External</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4a94-172"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-172"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-p111">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p111">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4a94-175">[全部]</span><span class="sxs-lookup"><span data-stu-id="b4a94-175">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4a94-176">VPN</span><span class="sxs-lookup"><span data-stu-id="b4a94-176">VPN</span></span></p></li>
<li><p><span data-ttu-id="b4a94-177">非 VPN</span><span class="sxs-lookup"><span data-stu-id="b4a94-177">Non-VPN</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4a94-178"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="b4a94-178"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="b4a94-p112">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b4a94-p112">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="b4a94-181">[全部]</span><span class="sxs-lookup"><span data-stu-id="b4a94-181">[All]</span></span></p></li>
<li><p><span data-ttu-id="b4a94-182">有線</span><span class="sxs-lookup"><span data-stu-id="b4a94-182">Wired</span></span></p></li>
<li><p><span data-ttu-id="b4a94-183">無線</span><span class="sxs-lookup"><span data-stu-id="b4a94-183">Wireless</span></span></p></li>
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

