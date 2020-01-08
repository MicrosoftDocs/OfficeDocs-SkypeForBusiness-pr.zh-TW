---
title: Lync Server 2013：使用 [監視] 儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c5a435baf9ef6b2ef24e235270326507b68789
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976464"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="7f4f8-102">在 Lync Server 2013 中使用 [監視] 儀表板</span><span class="sxs-lookup"><span data-stu-id="7f4f8-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f4f8-103">_**主題上次修改日期：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="7f4f8-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="7f4f8-104">[監視儀表板] 可讓系統管理員快速概覽其 Microsoft Lync Server 2013 系統健康與系統使用量。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="7f4f8-105">儀表板的設計目的是顯示主要系統規格的匯總視圖，並顯示下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="7f4f8-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="7f4f8-106">當天的合計。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-106">Totals for the current day.</span></span> <span data-ttu-id="7f4f8-107">請注意，目前日期顯示的值代表從午夜到目前時間為止所記錄的資料（根據報表伺服器的當地時間）。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="7f4f8-108">這表示您通常會查看部分日期的資料，而不是24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="7f4f8-109">例如，如果伺服器的當地時間是 8:00 AM，您會看到八小時的資料，因為午夜和目前時間 8:00 AM 之間有八個小時。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="7f4f8-110">周總計與過去六周的總趨勢。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="7f4f8-111">當月總計及過去六個月的總趨勢（僅適用于系統使用量）。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="7f4f8-112">請注意，您可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) Cmdlet 來傳回用來存取 Lync Server 2013 監視報告的 URL：</span><span class="sxs-lookup"><span data-stu-id="7f4f8-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="7f4f8-113">根據預設，[監視] 儀表板會針對目前的周數（以及前六周的趨勢總計）顯示下列度量單位的資料：</span><span class="sxs-lookup"><span data-stu-id="7f4f8-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="7f4f8-114">系統使用量指標</span><span class="sxs-lookup"><span data-stu-id="7f4f8-114">System Usage Metrics</span></span>

<span data-ttu-id="7f4f8-115">**註冊**</span><span class="sxs-lookup"><span data-stu-id="7f4f8-115">**Registration**</span></span>

  - <span data-ttu-id="7f4f8-116">唯一的使用者登錄</span><span class="sxs-lookup"><span data-stu-id="7f4f8-116">Unique user logons</span></span>

<span data-ttu-id="7f4f8-117">**對等**</span><span class="sxs-lookup"><span data-stu-id="7f4f8-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="7f4f8-118">總會話數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-118">Total sessions</span></span>

  - <span data-ttu-id="7f4f8-119">IM 會話</span><span class="sxs-lookup"><span data-stu-id="7f4f8-119">IM sessions</span></span>

  - <span data-ttu-id="7f4f8-120">音訊會話</span><span class="sxs-lookup"><span data-stu-id="7f4f8-120">Audio sessions</span></span>

  - <span data-ttu-id="7f4f8-121">影片會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-121">Video sessions</span></span>

  - <span data-ttu-id="7f4f8-122">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="7f4f8-122">Application sharing</span></span>

  - <span data-ttu-id="7f4f8-123">音訊會話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-123">Total audio session minutes</span></span>

  - <span data-ttu-id="7f4f8-124">平均音訊會話分鐘數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-124">Avg. audio session minutes</span></span>

<span data-ttu-id="7f4f8-125">**會議**</span><span class="sxs-lookup"><span data-stu-id="7f4f8-125">**Conference**</span></span>

  - <span data-ttu-id="7f4f8-126">會議總數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-126">Total conferences</span></span>

  - <span data-ttu-id="7f4f8-127">IM 會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-127">IM conferences</span></span>

  - <span data-ttu-id="7f4f8-128">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-128">A/V conferences</span></span>

  - <span data-ttu-id="7f4f8-129">應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-129">Application sharing conferences</span></span>

  - <span data-ttu-id="7f4f8-130">網路會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-130">Web conferences</span></span>

  - <span data-ttu-id="7f4f8-131">召集人總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-131">Total organizers</span></span>

  - <span data-ttu-id="7f4f8-132">A/V 會議紀要總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="7f4f8-133">速率.A/V 會議紀要</span><span class="sxs-lookup"><span data-stu-id="7f4f8-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="7f4f8-134">PSTN 會議總數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="7f4f8-135">PSTN 參與者總數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-135">Total PSTN participants</span></span>

  - <span data-ttu-id="7f4f8-136">PSTN 參與者通話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="7f4f8-137">除了系統使用標準之外，下列度量單位還會顯示當天及前六天的總計（如果您選取 [**每週檢視**]），或是在您選取 [**每月檢視**] 時，則為 [目前周] 和 [過去六周]。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="7f4f8-138">每個使用者呼叫診斷</span><span class="sxs-lookup"><span data-stu-id="7f4f8-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="7f4f8-139">**有通話失敗的使用者**</span><span class="sxs-lookup"><span data-stu-id="7f4f8-139">**Users with call failures**</span></span>

  - <span data-ttu-id="7f4f8-140">使用通話失敗的使用者總數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-140">Total users with call failures</span></span>

  - <span data-ttu-id="7f4f8-141">含通話失敗的會議召集人</span><span class="sxs-lookup"><span data-stu-id="7f4f8-141">Conference organizers with call failures</span></span>

<span data-ttu-id="7f4f8-142">**較差品質通話的使用者**</span><span class="sxs-lookup"><span data-stu-id="7f4f8-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="7f4f8-143">具有較差品質通話的使用者總數</span><span class="sxs-lookup"><span data-stu-id="7f4f8-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="7f4f8-144">呼叫診斷</span><span class="sxs-lookup"><span data-stu-id="7f4f8-144">Call Diagnostics</span></span>

<span data-ttu-id="7f4f8-145">對等</span><span class="sxs-lookup"><span data-stu-id="7f4f8-145">Peer-to-peer</span></span>

  - <span data-ttu-id="7f4f8-146">失敗總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-146">Total failures</span></span>

  - <span data-ttu-id="7f4f8-147">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-147">Overall failure rate</span></span>

  - <span data-ttu-id="7f4f8-148">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-148">IM failure rate</span></span>

  - <span data-ttu-id="7f4f8-149">音訊失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-149">Audio failure rate</span></span>

  - <span data-ttu-id="7f4f8-150">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-150">Application sharing failure rate</span></span>

<span data-ttu-id="7f4f8-151">會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-151">Conference</span></span>

  - <span data-ttu-id="7f4f8-152">失敗總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-152">Total failures</span></span>

  - <span data-ttu-id="7f4f8-153">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-153">Overall failure rate</span></span>

  - <span data-ttu-id="7f4f8-154">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-154">IM failure rate</span></span>

  - <span data-ttu-id="7f4f8-155">A/V 失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-155">A/V failure rate</span></span>

  - <span data-ttu-id="7f4f8-156">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="7f4f8-156">Application sharing failure rate</span></span>

<span data-ttu-id="7f4f8-157">依失敗的會話排前五台伺服器</span><span class="sxs-lookup"><span data-stu-id="7f4f8-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="7f4f8-158">媒體質量診斷</span><span class="sxs-lookup"><span data-stu-id="7f4f8-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="7f4f8-159">對等</span><span class="sxs-lookup"><span data-stu-id="7f4f8-159">Peer-to-peer</span></span>

  - <span data-ttu-id="7f4f8-160">低品質通話總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-160">Total poor quality calls</span></span>

  - <span data-ttu-id="7f4f8-161">品質不佳的通話百分比</span><span class="sxs-lookup"><span data-stu-id="7f4f8-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="7f4f8-162">品質不佳的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="7f4f8-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="7f4f8-163">會議</span><span class="sxs-lookup"><span data-stu-id="7f4f8-163">Conference</span></span>

  - <span data-ttu-id="7f4f8-164">低品質通話總計</span><span class="sxs-lookup"><span data-stu-id="7f4f8-164">Total poor quality calls</span></span>

  - <span data-ttu-id="7f4f8-165">品質不佳的通話百分比</span><span class="sxs-lookup"><span data-stu-id="7f4f8-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="7f4f8-166">品質不佳的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="7f4f8-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="7f4f8-167">低品質通話百分比的最差伺服器</span><span class="sxs-lookup"><span data-stu-id="7f4f8-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="7f4f8-168">使用 [監視儀表板]</span><span class="sxs-lookup"><span data-stu-id="7f4f8-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="7f4f8-169">如前所述，預設的合計會顯示在目前的周，而趨勢值則會顯示過去六周。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="7f4f8-170">如果您想要查看當月的合計（以及過去六個月的趨勢值），請按一下儀表板右上角的 [**每月檢視**] 連結。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="7f4f8-171">如果您決定要查看每月總計，連結文字將會變更為 [**每週] 視圖**。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="7f4f8-172">您可以按一下該連結，切換回 [每週] 視圖。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7f4f8-173">[監視儀表板] 會限制您在過去六周（或幾個月）的 [本周] （或 [月]）和趨勢值中查看 [合計]。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="7f4f8-174">您無法變更這些日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-174">You cannot change these dates and times.</span></span> <span data-ttu-id="7f4f8-175">例如，您無法使用儀表板來查看第九個月前的時間週期的報表合計。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="7f4f8-176">[**本周]、[\*\*\*\*本月**] 或 [ **Today** ] 欄中顯示的值會將您連結到專案的更詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="7f4f8-177">請記住，欄名稱和顯示在該欄中的值通常會根據所選的度量，以及您是否已選取 [每週檢視] 或 [每月] 視圖而有所不同。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="7f4f8-178">例如，如果您按一下 [針對**唯一的使用者登錄**統計顯示的合計]，您會在指定的時間範圍內看到 [**使用者註冊] 報告**。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="7f4f8-179">您隨時都可以按一下 [**儀表板**] 返回 [監視] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="7f4f8-180">您也可以按一下儀表板右上角的 [<STRONG>報告</STRONG>] 連結，以存取 [監視伺服器報告] 首頁。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="7f4f8-181">[**趨勢**] 欄會顯示一個簡單的線形圖形，其中顯示過去六周的總計（或是根據公制和時間間隔、過去六天或過去六個月）。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="7f4f8-182">這些簡單的折線圖會針對每個時間段顯示一個未標記的資料點（例如，過去六周內的一個未標記資料點）。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="7f4f8-183">不過，您可以透過將滑鼠指標放在圖形上，來檢索這些圖表的實際值。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="7f4f8-184">在這種情況下，工具提示會顯示圖形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="7f4f8-185">從 [監控] 儀表板匯出資料</span><span class="sxs-lookup"><span data-stu-id="7f4f8-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="7f4f8-186">[監視儀表板] 提供多種匯出目前儀表板視圖的方法。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="7f4f8-187">在 [儀表板] 工具列上，您會看到一個圖示，看起來像是一個附加了綠色箭號的軟碟。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="7f4f8-188">如果您按一下這個圖示，就會出現下拉式清單，提供下列資料匯出格式：</span><span class="sxs-lookup"><span data-stu-id="7f4f8-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="7f4f8-189">含報表資料的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="7f4f8-189">XML file with report data</span></span>

  - <span data-ttu-id="7f4f8-190">CSV （逗號分隔）</span><span class="sxs-lookup"><span data-stu-id="7f4f8-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="7f4f8-191">PDF</span><span class="sxs-lookup"><span data-stu-id="7f4f8-191">PDF</span></span>

  - <span data-ttu-id="7f4f8-192">MHTML （網頁檔案）</span><span class="sxs-lookup"><span data-stu-id="7f4f8-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="7f4f8-193">Excel</span><span class="sxs-lookup"><span data-stu-id="7f4f8-193">Excel</span></span>

  - <span data-ttu-id="7f4f8-194">TIFF 檔案</span><span class="sxs-lookup"><span data-stu-id="7f4f8-194">TIFF file</span></span>

  - <span data-ttu-id="7f4f8-195">Word</span><span class="sxs-lookup"><span data-stu-id="7f4f8-195">Word</span></span>

<span data-ttu-id="7f4f8-196">若要匯出目前的儀表板視圖（及其值），請按一下所需的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="7f4f8-197">Lync Server 2013 會以指定的格式產生報表，然後提供開啟或儲存該報表的選項。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="7f4f8-198">請注意，根據預設，Lync Server 會將 [報告**監控] 儀表板**標題儲存至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="7f4f8-199">若要為報表指定不同的名稱，或將其儲存在不同的資料夾，請按一下 [**儲存**] 按鈕旁的箭號，然後按一下 [**另存**新檔]。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="7f4f8-200">如果您使用 [名稱**監視] 儀表板**，並將報告儲存在 [下載] 資料夾中，您就可以按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="7f4f8-201">您可以嘗試匯出儀表板資料時，會出現 [**安全性警告**] 對話方塊，並顯示「您目前的設定不允許下載此檔案」訊息。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="7f4f8-202">如果發生這種情況，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7f4f8-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="7f4f8-203">在 Internet Explorer 中，選取 [**網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="7f4f8-204">在 [**網際網路選項**] 對話方塊中，按一下 [**安全性**] 索引標籤上的 [**信任的網站**]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="7f4f8-205">在 [**信任的網站**] 對話方塊中，按一下 [**新增**]，將運行 lync Server 2013 報告的 lync server 2013 新增至信任的網站集合。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="7f4f8-206">按一下 [**關閉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="7f4f8-207">然後，您必須重新整理監視儀表板，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="7f4f8-208">若要這樣做，請按 F5 或按一下儀表板工具列中**的 [重新**整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="7f4f8-209">（[重新整理 **] 圖示是**一個在其中有一對綠色箭號的圓圈）。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="7f4f8-210">您也可以建立包含即時資料摘要的 Excel 試算表，其中包含最新監視儀表板資料的連結。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="7f4f8-211">若要建立即時資料摘要檔案，請按一下工具列中的 [橙色**匯出至資料**摘要] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="7f4f8-212">如果您想要列印目前的儀表板，請按一下工具列中的 [印表機] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7f4f8-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

