---
title: Lync Server 2013：位置趨勢報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68c1eac461d65c2c0b023086422bb66505e9c929
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977067"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="dbf22-102">Lync Server 2013 中的位置趨勢報告</span><span class="sxs-lookup"><span data-stu-id="dbf22-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbf22-103">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="dbf22-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="dbf22-104">[位置趨勢] 報告可提供網路位置的通話品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="dbf22-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="dbf22-105">濾鏡</span><span class="sxs-lookup"><span data-stu-id="dbf22-105">Filters</span></span>

<span data-ttu-id="dbf22-106">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="dbf22-106">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="dbf22-107">例如，[位置趨勢] 報告可讓您篩選傳回的資料，例如存取類型（也就是間隔存取與外部存取）或有線/無線網路連線等專案。</span><span class="sxs-lookup"><span data-stu-id="dbf22-107">For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="dbf22-108">您也可以選擇分組資料的方式。</span><span class="sxs-lookup"><span data-stu-id="dbf22-108">You can also choose how data should be grouped.</span></span> <span data-ttu-id="dbf22-109">在這種情況下，通話會依小時、天或周分組。</span><span class="sxs-lookup"><span data-stu-id="dbf22-109">In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="dbf22-110">下表列出可與 [位置趨勢] 報表搭配使用的篩選。</span><span class="sxs-lookup"><span data-stu-id="dbf22-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="dbf22-111">位置趨勢報表篩選</span><span class="sxs-lookup"><span data-stu-id="dbf22-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbf22-112">名稱</span><span class="sxs-lookup"><span data-stu-id="dbf22-112">Name</span></span></th>
<th><span data-ttu-id="dbf22-113">描述</span><span class="sxs-lookup"><span data-stu-id="dbf22-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbf22-114"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-115">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="dbf22-115">Start date/time for the time range.</span></span> <span data-ttu-id="dbf22-116">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dbf22-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="dbf22-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dbf22-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbf22-118">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="dbf22-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbf22-119">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="dbf22-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbf22-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dbf22-120">7/7/2012</span></span></p>
<p><span data-ttu-id="dbf22-121">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="dbf22-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbf22-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dbf22-122">7/3/2012</span></span></p>
<p><span data-ttu-id="dbf22-123">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="dbf22-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf22-124"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-125">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="dbf22-125">End date/time for the time range.</span></span> <span data-ttu-id="dbf22-126">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dbf22-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="dbf22-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="dbf22-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="dbf22-128">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="dbf22-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="dbf22-129">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="dbf22-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="dbf22-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="dbf22-130">7/7/2012</span></span></p>
<p><span data-ttu-id="dbf22-131">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="dbf22-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="dbf22-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="dbf22-132">7/3/2012</span></span></p>
<p><span data-ttu-id="dbf22-133">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="dbf22-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf22-134"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-135">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="dbf22-135">Time interval.</span></span> <span data-ttu-id="dbf22-136">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="dbf22-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf22-137">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="dbf22-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dbf22-138">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="dbf22-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="dbf22-139">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="dbf22-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="dbf22-140">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="dbf22-140">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="dbf22-141">例如，如果您選取 [開始日期 1/1/2011] 和 [結束日期] 2/28/2011 的 [日間隔]，則會顯示 8/1/2011 12:00 AM 至 9/1/2011 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="dbf22-141">For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf22-142"><strong>Access 類型</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-143">指出撥打電話時，用戶端是否已登入內部網路或外部網路。</span><span class="sxs-lookup"><span data-stu-id="dbf22-143">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="dbf22-144">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="dbf22-144">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf22-145">同時</span><span class="sxs-lookup"><span data-stu-id="dbf22-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbf22-146">內部</span><span class="sxs-lookup"><span data-stu-id="dbf22-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="dbf22-147">外來</span><span class="sxs-lookup"><span data-stu-id="dbf22-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbf22-148"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-149">指出撥打電話時，用戶端連線到的網路類型。</span><span class="sxs-lookup"><span data-stu-id="dbf22-149">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="dbf22-150">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="dbf22-150">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf22-151">同時</span><span class="sxs-lookup"><span data-stu-id="dbf22-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbf22-152">有線</span><span class="sxs-lookup"><span data-stu-id="dbf22-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="dbf22-153">無線</span><span class="sxs-lookup"><span data-stu-id="dbf22-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbf22-154"><strong>點對點</strong></span><span class="sxs-lookup"><span data-stu-id="dbf22-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="dbf22-155">指示在撥打電話時，外部用戶端是否正在使用虛擬私人網路（VPN）連線。</span><span class="sxs-lookup"><span data-stu-id="dbf22-155">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="dbf22-156">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="dbf22-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbf22-157">同時</span><span class="sxs-lookup"><span data-stu-id="dbf22-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="dbf22-158">點對點</span><span class="sxs-lookup"><span data-stu-id="dbf22-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="dbf22-159">非 VPN</span><span class="sxs-lookup"><span data-stu-id="dbf22-159">Non-VPN</span></span></p></li>
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

