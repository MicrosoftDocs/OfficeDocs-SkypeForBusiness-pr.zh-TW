---
title: Lync Server 2013： PSTN 會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0dbb90d0776ee89fe9ab8b9f5796b182c5dc0457
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513110"
---
# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="1fc88-102">Lync Server 2013 中的 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="1fc88-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fc88-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1fc88-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1fc88-104">在 Microsoft Lync Server 2013 中，PSTN 會議是指至少有一個參與者透過使用 PSTN (公用交換電話網路) 電話，撥打音訊部分的任何會議。</span><span class="sxs-lookup"><span data-stu-id="1fc88-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="1fc88-105"> (PSTN 電話是 "室內電話"、"蜂窩電話] 或任何其他未利用 Voice over IP 的電話。 ) 雖然在監控報告中稱為 PSTN 會議，但這些會議甚至可能更常見，稱為電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="1fc88-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="1fc88-106">PSTN 會議摘要報告提供您組織中所有 PSTN 會議的相關資訊 (也就是說，所有具有至少一個撥入式使用者) 的會議。</span><span class="sxs-lookup"><span data-stu-id="1fc88-106">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user).</span></span> <span data-ttu-id="1fc88-107">此報告包含有關 PSTN 會議總數、參與這些會議的人員總數，以及最重要的電話撥入式使用者總數 (全部 PSTN 參與者度量) 中的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1fc88-107">The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="1fc88-108">存取 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="1fc88-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="1fc88-109">PSTN 會議摘要報告只可從監控報告首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="1fc88-109">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="1fc88-110">此報告未連結至任何其他報告。</span><span class="sxs-lookup"><span data-stu-id="1fc88-110">This report is not linked to any other reports.</span></span> <span data-ttu-id="1fc88-111">請注意，您無法為 PSTN 會議檢索詳細的呼叫資訊，因為個別端點負責提交此資訊。</span><span class="sxs-lookup"><span data-stu-id="1fc88-111">Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information.</span></span> <span data-ttu-id="1fc88-112">PSTN 電話不具備追蹤或送出通話詳細資訊的能力。</span><span class="sxs-lookup"><span data-stu-id="1fc88-112">PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="1fc88-113">PSTN 會議摘要報告的最佳用法</span><span class="sxs-lookup"><span data-stu-id="1fc88-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="1fc88-114">若要決定所有包含撥入使用者之會議的百分比，請將「PSTN 會議總數」度量值與 [Lync Server 2013 中「會議摘要」報告](lync-server-2013-conference-summary-report.md)上的 [會議總數] 度量值進行比較。</span><span class="sxs-lookup"><span data-stu-id="1fc88-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="1fc88-115">如果您看不到許多 PSTN 會議，如您可能會看到，請記住組織允許撥入使用者之會議的功能，取決於已指派給使用者的會議原則：如果允許很少的使用者持有 PSTN 會議，您顯然會看到極少的 PSTN 會議。</span><span class="sxs-lookup"><span data-stu-id="1fc88-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="1fc88-116">若有任何) 允許使用者在 Lync Server 管理命令介面中執行下列命令，您可以快速驗證 (的哪一種會議原則：</span><span class="sxs-lookup"><span data-stu-id="1fc88-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="1fc88-117">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="1fc88-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="1fc88-118">該命令將傳回類似下列的資料：</span><span class="sxs-lookup"><span data-stu-id="1fc88-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="1fc88-119">篩選</span><span class="sxs-lookup"><span data-stu-id="1fc88-119">Filters</span></span>

<span data-ttu-id="1fc88-120">篩選器可以讓您傳回更精確的資料集或者以不同方法檢視傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="1fc88-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="1fc88-121">例如，PSTN 會議摘要報告可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="1fc88-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="1fc88-122">在此情況下，會依小時、天、周或月群組會議。</span><span class="sxs-lookup"><span data-stu-id="1fc88-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="1fc88-123">下表列出您可以搭配 PSTN 會議摘要報告使用的篩選器。</span><span class="sxs-lookup"><span data-stu-id="1fc88-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="1fc88-124">PSTN 會議摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="1fc88-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fc88-125">名稱</span><span class="sxs-lookup"><span data-stu-id="1fc88-125">Name</span></span></th>
<th><span data-ttu-id="1fc88-126">描述</span><span class="sxs-lookup"><span data-stu-id="1fc88-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-127"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-p106">時間範圍的開始日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc88-p106">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="1fc88-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1fc88-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fc88-p107">如果您未輸入開始時間，報告會自動從指定日期凌晨 12 點開始。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="1fc88-p107">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fc88-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fc88-133">7/7/2012</span></span></p>
<p><span data-ttu-id="1fc88-134">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="1fc88-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fc88-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fc88-135">7/3/2012</span></span></p>
<p><span data-ttu-id="1fc88-136">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="1fc88-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fc88-137"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-p108">時間範圍的結束日期/時間。若要按照小時檢視資料，請輸入開始日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1fc88-p108">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="1fc88-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="1fc88-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="1fc88-p109">如果您未輸入結束時間，報告會自動在指定日期凌晨 12 點結束。若要按照日期檢視資料，只要輸入日期即可：</span><span class="sxs-lookup"><span data-stu-id="1fc88-p109">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="1fc88-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="1fc88-143">7/7/2012</span></span></p>
<p><span data-ttu-id="1fc88-144">若要按星期或月份檢視，請輸入當週或該月您想檢視的日期 (您不必輸入當週或該月的第一天)：</span><span class="sxs-lookup"><span data-stu-id="1fc88-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="1fc88-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="1fc88-145">7/3/2012</span></span></p>
<p><span data-ttu-id="1fc88-146">星期永遠是從星期日開始星期六結束。</span><span class="sxs-lookup"><span data-stu-id="1fc88-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-p110">時間間隔。請選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="1fc88-p110">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="1fc88-150">每小時 (最多可以顯示 25 個小時)</span><span class="sxs-lookup"><span data-stu-id="1fc88-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fc88-151">每日 (最多可以顯示 31 天)</span><span class="sxs-lookup"><span data-stu-id="1fc88-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fc88-152">每週 (最多可以顯示 12 週)</span><span class="sxs-lookup"><span data-stu-id="1fc88-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="1fc88-153">每月 (最多可以顯示 12 個月)</span><span class="sxs-lookup"><span data-stu-id="1fc88-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="1fc88-p111">若開始與結束日期超出所選間隔允許的上限值，將只會顯示上限值 (從開始日期開始顯示)。例如，若您選取 [每日] 間隔，並將開始與結束日期分別設為 2012 年 7 月 7 日及 2012 年 2 月 28 日，將只會顯示 2012 年 8 月 7 日凌晨 12 點到 2012 年 9 月 7 日凌晨 12 點這段期間的資料 (亦即只會顯示 31 天的資料)。</span><span class="sxs-lookup"><span data-stu-id="1fc88-p111">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="1fc88-156">指標</span><span class="sxs-lookup"><span data-stu-id="1fc88-156">Metrics</span></span>

<span data-ttu-id="1fc88-157">下表列出 PSTN 會議摘要報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="1fc88-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="1fc88-158">PSTN 會議摘要報告計量</span><span class="sxs-lookup"><span data-stu-id="1fc88-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1fc88-159">姓名</span><span class="sxs-lookup"><span data-stu-id="1fc88-159">Name</span></span></th>
<th><span data-ttu-id="1fc88-160">可以排序這個項目嗎？</span><span class="sxs-lookup"><span data-stu-id="1fc88-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="1fc88-161">描述</span><span class="sxs-lookup"><span data-stu-id="1fc88-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-162"><strong>每小時</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="1fc88-163"><strong>每日</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="1fc88-164"><strong>每週</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="1fc88-165"><strong>每月</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-166">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-166">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-p112">指示所選的時間間隔。在適用的情況下，只要按一下指定的時間間隔，即可檢視該間隔的詳細資訊。例如，若您使用 [每日] 間隔並按一下 7/7/2012，將會顯示該日期之使用者登錄活動的每小時明細。</span><span class="sxs-lookup"><span data-stu-id="1fc88-p112">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fc88-170"><strong>PSTN 會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-171">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-171">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-172">允許撥入存取的會議總數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-173"><strong>參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-174">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-174">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-175">參與允許撥入存取之會議的人員總數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fc88-176"><strong>A/V 會議總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-177">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-177">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-178">音訊/視訊會議的總時數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-179"><strong>A/V 會議參與者總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-180">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-180">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-181">音訊/視頻參與者的總時數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-181">Total amount of audio/visual participant time.</span></span> <span data-ttu-id="1fc88-182">例如，如果一個參與者在 A/V 會議中花了五分鐘，另一個參與者在同一部會議中花三分鐘的時間，則會議參與者時間的總數 A/V 會是8分鐘。</span><span class="sxs-lookup"><span data-stu-id="1fc88-182">For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fc88-183"><strong>PSTN 參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-184">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-184">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-185">撥打至允許撥入存取之會議的總使用者人數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fc88-186"><strong>PSTN 參與者分鐘總數</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-187">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-187">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-188">撥號使用者所花費的會議時間總量。</span><span class="sxs-lookup"><span data-stu-id="1fc88-188">Total amount of conference time spent by dial-in users.</span></span> <span data-ttu-id="1fc88-189">例如，如果一個撥入式參與者在會議中花了五分鐘的時間，另一個參與者在同一部會議中花三分鐘的時間，則 PSTN 參與者時間總量會是8分鐘。</span><span class="sxs-lookup"><span data-stu-id="1fc88-189">For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fc88-190"><strong>獨特的會議召集人</strong></span><span class="sxs-lookup"><span data-stu-id="1fc88-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="1fc88-191">否</span><span class="sxs-lookup"><span data-stu-id="1fc88-191">No</span></span></p></td>
<td><p><span data-ttu-id="1fc88-192">組織至少一部允許撥入存取之會議的總使用者人數。</span><span class="sxs-lookup"><span data-stu-id="1fc88-192">Total number of users who organized at least one conference that allowed dial-in access.</span></span> <span data-ttu-id="1fc88-193">召集過多次會議的使用者計為一個專屬召集人，就像只召集過一次會議的使用者一樣。</span><span class="sxs-lookup"><span data-stu-id="1fc88-193">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

