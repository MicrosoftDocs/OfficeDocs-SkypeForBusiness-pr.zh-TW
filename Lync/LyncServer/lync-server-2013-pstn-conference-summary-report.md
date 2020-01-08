---
title: Lync Server 2013： PSTN 會議摘要報告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b98628ea56fb36ec594e5ea4ff9915e9785b3cfa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-conference-summary-report-in-lync-server-2013"></a><span data-ttu-id="7eccd-102">Lync Server 2013 中的 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="7eccd-102">PSTN Conference Summary Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eccd-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7eccd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7eccd-104">在 Microsoft Lync Server 2013 中，PSTN 會議是一個會議，其中至少有一個參與者使用 PSTN （公開交換電話網絡）電話撥入音訊部分。</span><span class="sxs-lookup"><span data-stu-id="7eccd-104">In Microsoft Lync Server 2013, a PSTN conference is any conference in which at least one participant dials in to the audio portion by a using a PSTN (public switched telephone network) phone.</span></span> <span data-ttu-id="7eccd-105">（PSTN 手機是「有線電話、」手機或任何其他不使用語音 over IP 的電話）。雖然在監視報告中稱為 PSTN 會議，但這些會議可能更常見，也稱為撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="7eccd-105">(A PSTN phone is a "landline," a cell phone, or any other phone which does not make use of Voice over IP.) Although referred to as PSTN conferences in the Monitoring Reports, these conferences are perhaps more-commonly known as dial-in conferences.</span></span>

<span data-ttu-id="7eccd-106">PSTN 會議摘要報告提供貴組織中所有 PSTN 會議的相關資訊（也就是至少有一個撥入使用者的所有會議）。</span><span class="sxs-lookup"><span data-stu-id="7eccd-106">The PSTN Conference Summary Report provides information about all the PSTN conferences held in your organization (that is, all the conferences that had at least one dial-in user).</span></span> <span data-ttu-id="7eccd-107">此報告包含有關 PSTN 會議總數、參與這些會議的人數總數，以及最重要的電話撥入使用者總數（總 PSTN 參與者統計值）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7eccd-107">The report includes information about the total number of PSTN conferences, the total number of people who participated in those conferences, and, perhaps, most important, the total number of dial-in users (the Total PSTN participants metric).</span></span>

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a><span data-ttu-id="7eccd-108">存取 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="7eccd-108">Accessing the PSTN Conference Summary Report</span></span>

<span data-ttu-id="7eccd-109">PSTN 會議摘要報告只能從 [監控報告] 首頁進行存取。</span><span class="sxs-lookup"><span data-stu-id="7eccd-109">The PSTN Conference Summary Report can only be accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="7eccd-110">此報告未連結至任何其他報表。</span><span class="sxs-lookup"><span data-stu-id="7eccd-110">This report is not linked to any other reports.</span></span> <span data-ttu-id="7eccd-111">請注意，您無法取得 PSTN 會議的詳細呼叫資訊，因為個別端點負責提交此資訊。</span><span class="sxs-lookup"><span data-stu-id="7eccd-111">Note that you cannot retrieve detailed call information for a PSTN conference, in part because individual endpoints are responsible for submitting this information.</span></span> <span data-ttu-id="7eccd-112">PSTN 手機無法追蹤或提交通話詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7eccd-112">PSTN phones are not capable of tracking or submitting call detail information.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a><span data-ttu-id="7eccd-113">充分利用 PSTN 會議摘要報告</span><span class="sxs-lookup"><span data-stu-id="7eccd-113">Making the Best Use of the PSTN Conference Summary Report</span></span>

<span data-ttu-id="7eccd-114">若要判斷包含撥入使用者的所有會議的百分比，請比較 PSTN 會議總量與在[Lync Server 2013 的 [會議摘要] 報告中](lync-server-2013-conference-summary-report.md)找到的總會議度量值。</span><span class="sxs-lookup"><span data-stu-id="7eccd-114">To determine the percentage of all your conferences that include dial-in users, compare the value of the Total PSTN conferences metric with the Total conferences metric found on the [Conference Summary Report in Lync Server 2013](lync-server-2013-conference-summary-report.md).</span></span>

<span data-ttu-id="7eccd-115">如果您沒有看到許多您可能會看到的 PSTN 會議，請記住，組織允許撥入使用者的會議的能力取決於已指派給使用者的會議原則：您的使用者數只有幾個使用者可以保留 PSTN-ZA&PLATFORM 會議您顯然會看到很少的 PSTN 會議。</span><span class="sxs-lookup"><span data-stu-id="7eccd-115">If you don't see as many PSTN conferences as you might have expected to see, keep in mind that the ability to organize a conference that allows dial-in users depends on the conferencing policy that has been assigned to a user: if very few of your users are allowed to hold PSTN conferences you would obviously see very few PSTN conferences.</span></span> <span data-ttu-id="7eccd-116">您可以透過在 Lync Server 管理命令介面中執行下列命令，快速確認您的會議原則（如果有的話）允許使用者排程 PSTN 會議：</span><span class="sxs-lookup"><span data-stu-id="7eccd-116">You can quickly verify which of your conferencing policies (if any) allow users to schedule PSTN conferences by running the following command from within the Lync Server Management Shell:</span></span>

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

<span data-ttu-id="7eccd-117">這樣會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="7eccd-117">That will return data similar to this:</span></span>

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

<span data-ttu-id="7eccd-118">這樣會傳回如下所示的資料：</span><span class="sxs-lookup"><span data-stu-id="7eccd-118">That will return data similar to this:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="7eccd-119">濾鏡</span><span class="sxs-lookup"><span data-stu-id="7eccd-119">Filters</span></span>

<span data-ttu-id="7eccd-120">篩選提供一種方式，可讓您傳回更精細設定目標的資料集，或以不同方式查看傳回的資料。</span><span class="sxs-lookup"><span data-stu-id="7eccd-120">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="7eccd-121">例如，PSTN 會議摘要報告可讓您選擇資料的分組方式。</span><span class="sxs-lookup"><span data-stu-id="7eccd-121">For example, the PSTN Conference Summary Report enables you to choose how data should be grouped.</span></span> <span data-ttu-id="7eccd-122">在這種情況下，會議會依小時、日、周或月進行分組。</span><span class="sxs-lookup"><span data-stu-id="7eccd-122">In this case, conferences are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="7eccd-123">下表列出您可搭配 PSTN 會議摘要報告使用的篩選準則。</span><span class="sxs-lookup"><span data-stu-id="7eccd-123">The following table lists the filters that you can use with the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-filters"></a><span data-ttu-id="7eccd-124">PSTN 會議摘要報告篩選器</span><span class="sxs-lookup"><span data-stu-id="7eccd-124">PSTN Conference Summary Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eccd-125">名稱</span><span class="sxs-lookup"><span data-stu-id="7eccd-125">Name</span></span></th>
<th><span data-ttu-id="7eccd-126">描述</span><span class="sxs-lookup"><span data-stu-id="7eccd-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-127"><strong>從</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-127"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-128">時間範圍的開始日期/時間。</span><span class="sxs-lookup"><span data-stu-id="7eccd-128">Start date/time for the time range.</span></span> <span data-ttu-id="7eccd-129">若要依時間查看資料，請輸入 [開始日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7eccd-129">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="7eccd-130">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7eccd-130">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7eccd-131">如果您沒有輸入開始時間，報告會在指定日期自動于12:00 點開始。</span><span class="sxs-lookup"><span data-stu-id="7eccd-131">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7eccd-132">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="7eccd-132">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7eccd-133">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7eccd-133">7/7/2012</span></span></p>
<p><span data-ttu-id="7eccd-134">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7eccd-134">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7eccd-135">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7eccd-135">7/3/2012</span></span></p>
<p><span data-ttu-id="7eccd-136">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="7eccd-136">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eccd-137"><strong>自</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-137"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-138">時間範圍的結束日期/時間。</span><span class="sxs-lookup"><span data-stu-id="7eccd-138">End date/time for the time range.</span></span> <span data-ttu-id="7eccd-139">若要依時間查看資料，請輸入 [結束日期] 和 [時間]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7eccd-139">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="7eccd-140">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="7eccd-140">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="7eccd-141">如果您沒有輸入結束時間，報告會在指定日期自動結束于12:00。</span><span class="sxs-lookup"><span data-stu-id="7eccd-141">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="7eccd-142">若要依天查看資料，只需輸入日期：</span><span class="sxs-lookup"><span data-stu-id="7eccd-142">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="7eccd-143">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="7eccd-143">7/7/2012</span></span></p>
<p><span data-ttu-id="7eccd-144">若要依周或依月查看，請在您要查看的周或月份中，輸入您要查看的日期（不需要輸入周或月的第一天）：</span><span class="sxs-lookup"><span data-stu-id="7eccd-144">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="7eccd-145">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="7eccd-145">7/3/2012</span></span></p>
<p><span data-ttu-id="7eccd-146">周數總是從星期日到星期六執行。</span><span class="sxs-lookup"><span data-stu-id="7eccd-146">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-147"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-147"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-148">時間間隔。</span><span class="sxs-lookup"><span data-stu-id="7eccd-148">Time interval.</span></span> <span data-ttu-id="7eccd-149">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7eccd-149">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="7eccd-150">每小時（最多可顯示25小時）</span><span class="sxs-lookup"><span data-stu-id="7eccd-150">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7eccd-151">每天（最多可以顯示31天）</span><span class="sxs-lookup"><span data-stu-id="7eccd-151">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7eccd-152">每週（最多可以顯示12周）</span><span class="sxs-lookup"><span data-stu-id="7eccd-152">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="7eccd-153">每月（最多可以顯示12個月）</span><span class="sxs-lookup"><span data-stu-id="7eccd-153">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="7eccd-154">如果 [開始] 和 [結束] 日期超過所選間隔所允許的最大值數，則會顯示值的數目上限（從開始日期開始）。</span><span class="sxs-lookup"><span data-stu-id="7eccd-154">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="7eccd-155">例如，如果您選取 [開始日期 7/7/2012] 和 [結束日期] 2/28/2012 的 [日間隔]，則會顯示 8/7/2012 12:00 AM 至 9/7/2012 12:00 AM （也就是31天內的資料）的資料。</span><span class="sxs-lookup"><span data-stu-id="7eccd-155">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="7eccd-156">指標</span><span class="sxs-lookup"><span data-stu-id="7eccd-156">Metrics</span></span>

<span data-ttu-id="7eccd-157">下表列出 PSTN 會議摘要報告中的資訊。</span><span class="sxs-lookup"><span data-stu-id="7eccd-157">The following table lists the information in the PSTN Conference Summary Report.</span></span>

### <a name="pstn-conference-summary-report-metrics"></a><span data-ttu-id="7eccd-158">PSTN 會議摘要報告度量單位</span><span class="sxs-lookup"><span data-stu-id="7eccd-158">PSTN Conference Summary Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eccd-159">名稱</span><span class="sxs-lookup"><span data-stu-id="7eccd-159">Name</span></span></th>
<th><span data-ttu-id="7eccd-160">您可以針對此專案進行排序嗎？</span><span class="sxs-lookup"><span data-stu-id="7eccd-160">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="7eccd-161">描述</span><span class="sxs-lookup"><span data-stu-id="7eccd-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-162"><strong>工資</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-162"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="7eccd-163"><strong>日常</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-163"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="7eccd-164"><strong>周更新</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-164"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="7eccd-165"><strong>次</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-165"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-166">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-166">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-167">指出選取的時間間隔。</span><span class="sxs-lookup"><span data-stu-id="7eccd-167">Indicates the selected time interval.</span></span> <span data-ttu-id="7eccd-168">在適當的地方，您可以按一下指定的時間間隔，以查看該間隔的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7eccd-168">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="7eccd-169">例如，如果您使用的是每日間隔，而您按一下 [7/7/2012]，就會看到該日期的使用者註冊活動的每小時細目。</span><span class="sxs-lookup"><span data-stu-id="7eccd-169">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eccd-170"><strong>PSTN 會議總數</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-170"><strong>Total PSTN conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-171">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-171">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-172">允許撥入存取的會議總數。</span><span class="sxs-lookup"><span data-stu-id="7eccd-172">Total number conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-173"><strong>參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-173"><strong>Total participants</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-174">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-174">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-175">參與允許撥入存取之會議的人員總數。</span><span class="sxs-lookup"><span data-stu-id="7eccd-175">Total number of people who participated in conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eccd-176"><strong>A/V 會議紀要總計</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-176"><strong>Total A/V conference minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-177">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-177">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-178">音訊/視訊會議的總時間。</span><span class="sxs-lookup"><span data-stu-id="7eccd-178">Total amount of audio/visual conference time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-179"><strong>A/V 會議參與者紀要總計</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-179"><strong>Total A/V conference participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-180">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-180">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-181">音訊/視覺參與者的總時間。</span><span class="sxs-lookup"><span data-stu-id="7eccd-181">Total amount of audio/visual participant time.</span></span> <span data-ttu-id="7eccd-182">例如，如果一個參與者在 A/V 會議中花費了五分鐘，而另一個參與者在同一筆會議中花費了三分鐘，則總的 A/V 會議參與者時間會是八分鐘。</span><span class="sxs-lookup"><span data-stu-id="7eccd-182">For example, if one participant spent five minutes in an A/V conference and another participant spent three minutes in the same conference, the total A/V conference participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eccd-183"><strong>PSTN 參與者總數</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-183"><strong>Total PSTN participants</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-184">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-184">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-185">撥入會議且允許撥入存取的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="7eccd-185">Total number of users who dialed in to conferences that allowed dial-in access.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eccd-186"><strong>PSTN 參與者通話總分鐘數</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-186"><strong>Total PSTN participant minutes</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-187">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-187">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-188">撥入使用者所花費的會議時間總量。</span><span class="sxs-lookup"><span data-stu-id="7eccd-188">Total amount of conference time spent by dial-in users.</span></span> <span data-ttu-id="7eccd-189">例如，如果一個撥入參與者在會議中花了五分鐘的時間，而另一個參與者在同一個會議中花費了三分鐘，則 PSTN 參與者時間總會是八分鐘。</span><span class="sxs-lookup"><span data-stu-id="7eccd-189">For example, if one dial-in participant spent five minutes in a conference and another participant spent three minutes in the same conference, the total PSTN participant time would be eight minutes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eccd-190"><strong>唯一的會議召集人</strong></span><span class="sxs-lookup"><span data-stu-id="7eccd-190"><strong>Unique conference organizers</strong></span></span></p></td>
<td><p><span data-ttu-id="7eccd-191">否</span><span class="sxs-lookup"><span data-stu-id="7eccd-191">No</span></span></p></td>
<td><p><span data-ttu-id="7eccd-192">組織至少有一部允許撥入存取的會議的使用者總數。</span><span class="sxs-lookup"><span data-stu-id="7eccd-192">Total number of users who organized at least one conference that allowed dial-in access.</span></span> <span data-ttu-id="7eccd-193">組織多個會議的使用者會算作一個唯一的召集人，就像只組織單一會議的使用者。</span><span class="sxs-lookup"><span data-stu-id="7eccd-193">Users who organized more than one conference are counted as one unique organizer, just like users who only organized a single conference.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

