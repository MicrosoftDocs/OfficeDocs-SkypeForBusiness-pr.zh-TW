---
title: Lync Server 2013：位置趨勢報告
description: Lync Server 2013：位置趨勢報告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83035bf81e793416035e1bd90906b3c27e51f7f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572119"
---
# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="78762-103">Lync Server 2013 中的位置趨勢報告</span><span class="sxs-lookup"><span data-stu-id="78762-103">Location Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78762-104">_**主題上次修改日期：** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="78762-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="78762-105">位置趨勢報告提供網路位置的通話品質趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="78762-105">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="78762-106">篩選</span><span class="sxs-lookup"><span data-stu-id="78762-106">Filters</span></span>

<span data-ttu-id="78762-p101">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。例如，位置趨勢報告可以讓您依據存取類型 (也就是指內部存取和外部存取) 或者按照有線/無線網路連線來篩選傳回的資料。您也可以選擇資料的分組方式。在這種情況下，通話會按照小時、天或星期加以分組。</span><span class="sxs-lookup"><span data-stu-id="78762-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="78762-111">下表列出您可以搭配位置趨勢報告的篩選器。</span><span class="sxs-lookup"><span data-stu-id="78762-111">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="78762-112">位置趨勢報告篩選器</span><span class="sxs-lookup"><span data-stu-id="78762-112">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="78762-113">名稱</span><span class="sxs-lookup"><span data-stu-id="78762-113">Name</span></span></th>
<th><span data-ttu-id="78762-114">描述</span><span class="sxs-lookup"><span data-stu-id="78762-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="78762-115"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="78762-115"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p102">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="78762-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="78762-118">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="78762-118">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="78762-p103">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="78762-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="78762-121">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="78762-121">7/7/2012</span></span></p>
<p><span data-ttu-id="78762-122">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="78762-122">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="78762-123">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="78762-123">7/3/2012</span></span></p>
<p><span data-ttu-id="78762-124">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="78762-124">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78762-125"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="78762-125"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p104">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="78762-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="78762-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="78762-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="78762-p105">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="78762-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="78762-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="78762-131">7/7/2012</span></span></p>
<p><span data-ttu-id="78762-132">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="78762-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="78762-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="78762-133">7/3/2012</span></span></p>
<p><span data-ttu-id="78762-134">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="78762-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78762-135"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="78762-135"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p106">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="78762-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78762-138">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="78762-138">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="78762-139">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="78762-139">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="78762-140">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="78762-140">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="78762-p107">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 1/1/2011 及 2/28/2011，將只會顯示 1/1/2011 上午 12:00 至 2/1/2011 上午 12:00 這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="78762-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78762-143"><strong>存取類型</strong></span><span class="sxs-lookup"><span data-stu-id="78762-143"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p108">指出撥打電腦時，用戶端是否登入內部網路或外部網路。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="78762-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78762-146">一切</span><span class="sxs-lookup"><span data-stu-id="78762-146">[All]</span></span></p></li>
<li><p><span data-ttu-id="78762-147">內部</span><span class="sxs-lookup"><span data-stu-id="78762-147">Internal</span></span></p></li>
<li><p><span data-ttu-id="78762-148">外部</span><span class="sxs-lookup"><span data-stu-id="78762-148">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="78762-149"><strong>網路類型</strong></span><span class="sxs-lookup"><span data-stu-id="78762-149"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p109">指出當撥打電話時，用戶端連線的網路類型。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="78762-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78762-152">一切</span><span class="sxs-lookup"><span data-stu-id="78762-152">[All]</span></span></p></li>
<li><p><span data-ttu-id="78762-153">有線</span><span class="sxs-lookup"><span data-stu-id="78762-153">Wired</span></span></p></li>
<li><p><span data-ttu-id="78762-154">無線</span><span class="sxs-lookup"><span data-stu-id="78762-154">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="78762-155"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="78762-155"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="78762-p110">指出當撥打電話時，外部用戶端是否使用虛擬私人網路 (VPN) 連線。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="78762-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="78762-158">一切</span><span class="sxs-lookup"><span data-stu-id="78762-158">[All]</span></span></p></li>
<li><p><span data-ttu-id="78762-159">VPN</span><span class="sxs-lookup"><span data-stu-id="78762-159">VPN</span></span></p></li>
<li><p><span data-ttu-id="78762-160">非 VPN</span><span class="sxs-lookup"><span data-stu-id="78762-160">Non-VPN</span></span></p></li>
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

