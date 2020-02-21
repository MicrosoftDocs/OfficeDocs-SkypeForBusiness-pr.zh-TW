---
title: Lync Server 2013： 使用監控儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Monitoring Dashboard
ms:assetid: e00e5783-116f-481f-ad17-3af847d6769a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721905(v=OCS.15)
ms:contentKeyID: 49733839
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 697023ef7c93191cbe13aa0abf4c175240e70ae9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-the-monitoring-dashboard-in-lync-server-2013"></a><span data-ttu-id="e10fd-102">Lync Server 2013 中使用監控儀表板</span><span class="sxs-lookup"><span data-stu-id="e10fd-102">Using the Monitoring Dashboard in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e10fd-103">_**上次修改主題：** 2014年-02-05_</span><span class="sxs-lookup"><span data-stu-id="e10fd-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="e10fd-104">監控儀表板提供系統管理員使用其 Microsoft Lync Server 2013 系統健康情況與系統使用情況的快速概觀。</span><span class="sxs-lookup"><span data-stu-id="e10fd-104">The Monitoring Dashboard provides administrators with a quick overview of their Microsoft Lync Server 2013 system health and system usage.</span></span> <span data-ttu-id="e10fd-105">儀表板被設計來顯示重要系統計量彙總檢視並若要這麼做會顯示下列一項：</span><span class="sxs-lookup"><span data-stu-id="e10fd-105">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>

  - <span data-ttu-id="e10fd-106">目前日期的總數。</span><span class="sxs-lookup"><span data-stu-id="e10fd-106">Totals for the current day.</span></span> <span data-ttu-id="e10fd-107">請注意顯示當天的值，代表已從午夜到目前的時間 （根據報表伺服器本地時間） 將記錄的資料。</span><span class="sxs-lookup"><span data-stu-id="e10fd-107">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="e10fd-108">這表示，您通常檢視資料部分的一天，以及不在 24 小時期間內。</span><span class="sxs-lookup"><span data-stu-id="e10fd-108">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="e10fd-109">例如，如果伺服器的本地時間為上午 8:00，您看到八個小時的資料因為有八個小時午夜與目前時間的上午 8:00 之間。</span><span class="sxs-lookup"><span data-stu-id="e10fd-109">For example, if the local time of the server is 8:00 AM, you see eight hours’ worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>

  - <span data-ttu-id="e10fd-110">當週的總計和過去六週的趨勢總計。</span><span class="sxs-lookup"><span data-stu-id="e10fd-110">Totals for the week, and trend totals for the past six weeks.</span></span>

  - <span data-ttu-id="e10fd-111">當月總計和過去六個月 （適用於僅限系統使用量） 的趨勢總計。</span><span class="sxs-lookup"><span data-stu-id="e10fd-111">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>

<span data-ttu-id="e10fd-112">請注意，您可以使用[Get-csreportingconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet 可傳回用來存取 Lync Server 2013 Monitoring Reports 的 URL:</span><span class="sxs-lookup"><span data-stu-id="e10fd-112">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsReportingConfiguration) cmdlet to return the URL used for accessing Lync Server 2013 Monitoring Reports:</span></span>

    Get-CsReportingConfiguration

<span data-ttu-id="e10fd-113">根據預設，監控儀表板會顯示的週 （以及前六週的趨勢總計） 的下列計量資料：</span><span class="sxs-lookup"><span data-stu-id="e10fd-113">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>

<div>

## <a name="system-usage-metrics"></a><span data-ttu-id="e10fd-114">系統使用狀況計量</span><span class="sxs-lookup"><span data-stu-id="e10fd-114">System Usage Metrics</span></span>

<span data-ttu-id="e10fd-115">**註冊**</span><span class="sxs-lookup"><span data-stu-id="e10fd-115">**Registration**</span></span>

  - <span data-ttu-id="e10fd-116">唯一的使用者登入</span><span class="sxs-lookup"><span data-stu-id="e10fd-116">Unique user logons</span></span>

<span data-ttu-id="e10fd-117">**端對端**</span><span class="sxs-lookup"><span data-stu-id="e10fd-117">**Peer-to-peer**</span></span>

  - <span data-ttu-id="e10fd-118">工作階段總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-118">Total sessions</span></span>

  - <span data-ttu-id="e10fd-119">IM 工作階段</span><span class="sxs-lookup"><span data-stu-id="e10fd-119">IM sessions</span></span>

  - <span data-ttu-id="e10fd-120">音訊工作階段</span><span class="sxs-lookup"><span data-stu-id="e10fd-120">Audio sessions</span></span>

  - <span data-ttu-id="e10fd-121">視訊工作階段</span><span class="sxs-lookup"><span data-stu-id="e10fd-121">Video sessions</span></span>

  - <span data-ttu-id="e10fd-122">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="e10fd-122">Application sharing</span></span>

  - <span data-ttu-id="e10fd-123">音訊工作階段分鐘總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-123">Total audio session minutes</span></span>

  - <span data-ttu-id="e10fd-124">平均音訊工作階段分鐘</span><span class="sxs-lookup"><span data-stu-id="e10fd-124">Avg. audio session minutes</span></span>

<span data-ttu-id="e10fd-125">**會議**</span><span class="sxs-lookup"><span data-stu-id="e10fd-125">**Conference**</span></span>

  - <span data-ttu-id="e10fd-126">會議總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-126">Total conferences</span></span>

  - <span data-ttu-id="e10fd-127">IM 會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-127">IM conferences</span></span>

  - <span data-ttu-id="e10fd-128">A / V 會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-128">A/V conferences</span></span>

  - <span data-ttu-id="e10fd-129">應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-129">Application sharing conferences</span></span>

  - <span data-ttu-id="e10fd-130">Web 會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-130">Web conferences</span></span>

  - <span data-ttu-id="e10fd-131">召集人總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-131">Total organizers</span></span>

  - <span data-ttu-id="e10fd-132">A/V 會議總分鐘數</span><span class="sxs-lookup"><span data-stu-id="e10fd-132">Total A/V conference minutes</span></span>

  - <span data-ttu-id="e10fd-133">平均A / V 會議分鐘</span><span class="sxs-lookup"><span data-stu-id="e10fd-133">Avg. A/V conference minutes</span></span>

  - <span data-ttu-id="e10fd-134">PSTN 會議總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-134">Total PSTN conferences</span></span>

  - <span data-ttu-id="e10fd-135">PSTN 參與者總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-135">Total PSTN participants</span></span>

  - <span data-ttu-id="e10fd-136">PSTN 參與者分鐘總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-136">Total PSTN participant minutes</span></span>

<span data-ttu-id="e10fd-137">除了系統使用狀況計量，下列計量可以顯示總當天與前六天 （如果您選取 [**每週檢視**) 或週與過去六週如果您選取 [**每月檢視**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-137">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>

</div>

<div>

## <a name="per-user-call-diagnostics"></a><span data-ttu-id="e10fd-138">每位使用者通話診斷</span><span class="sxs-lookup"><span data-stu-id="e10fd-138">Per-User Call Diagnostics</span></span>

<span data-ttu-id="e10fd-139">**通話失敗的使用者**</span><span class="sxs-lookup"><span data-stu-id="e10fd-139">**Users with call failures**</span></span>

  - <span data-ttu-id="e10fd-140">通話失敗的使用者總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-140">Total users with call failures</span></span>

  - <span data-ttu-id="e10fd-141">通話失敗的會議召集人</span><span class="sxs-lookup"><span data-stu-id="e10fd-141">Conference organizers with call failures</span></span>

<span data-ttu-id="e10fd-142">**通話品質不良的使用者**</span><span class="sxs-lookup"><span data-stu-id="e10fd-142">**Users with poor quality calls**</span></span>

  - <span data-ttu-id="e10fd-143">通話品質不良的使用者總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-143">Total users with poor quality calls</span></span>

</div>

<div>

## <a name="call-diagnostics"></a><span data-ttu-id="e10fd-144">通話診斷</span><span class="sxs-lookup"><span data-stu-id="e10fd-144">Call Diagnostics</span></span>

<span data-ttu-id="e10fd-145">端對端</span><span class="sxs-lookup"><span data-stu-id="e10fd-145">Peer-to-peer</span></span>

  - <span data-ttu-id="e10fd-146">失敗總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-146">Total failures</span></span>

  - <span data-ttu-id="e10fd-147">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-147">Overall failure rate</span></span>

  - <span data-ttu-id="e10fd-148">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-148">IM failure rate</span></span>

  - <span data-ttu-id="e10fd-149">音訊失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-149">Audio failure rate</span></span>

  - <span data-ttu-id="e10fd-150">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-150">Application sharing failure rate</span></span>

<span data-ttu-id="e10fd-151">會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-151">Conference</span></span>

  - <span data-ttu-id="e10fd-152">失敗總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-152">Total failures</span></span>

  - <span data-ttu-id="e10fd-153">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-153">Overall failure rate</span></span>

  - <span data-ttu-id="e10fd-154">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-154">IM failure rate</span></span>

  - <span data-ttu-id="e10fd-155">A / V 失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-155">A/V failure rate</span></span>

  - <span data-ttu-id="e10fd-156">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="e10fd-156">Application sharing failure rate</span></span>

<span data-ttu-id="e10fd-157">工作階段失敗的前五部伺服器</span><span class="sxs-lookup"><span data-stu-id="e10fd-157">Top five servers by failed sessions</span></span>

</div>

<div>

## <a name="media-quality-diagnostics"></a><span data-ttu-id="e10fd-158">媒體品質診斷</span><span class="sxs-lookup"><span data-stu-id="e10fd-158">Media Quality Diagnostics</span></span>

<span data-ttu-id="e10fd-159">端對端</span><span class="sxs-lookup"><span data-stu-id="e10fd-159">Peer-to-peer</span></span>

  - <span data-ttu-id="e10fd-160">通話品質不良總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-160">Total poor quality calls</span></span>

  - <span data-ttu-id="e10fd-161">通話品質不良百分比</span><span class="sxs-lookup"><span data-stu-id="e10fd-161">Poor quality call percentage</span></span>

  - <span data-ttu-id="e10fd-162">品質不良的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e10fd-162">PSTN calls with poor quality</span></span>

<span data-ttu-id="e10fd-163">會議</span><span class="sxs-lookup"><span data-stu-id="e10fd-163">Conference</span></span>

  - <span data-ttu-id="e10fd-164">通話品質不良總數</span><span class="sxs-lookup"><span data-stu-id="e10fd-164">Total poor quality calls</span></span>

  - <span data-ttu-id="e10fd-165">通話品質不良百分比</span><span class="sxs-lookup"><span data-stu-id="e10fd-165">Poor quality call percentage</span></span>

  - <span data-ttu-id="e10fd-166">品質不良的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="e10fd-166">PSTN calls with poor quality</span></span>

<span data-ttu-id="e10fd-167">通話品質不良百分比最差的伺服器</span><span class="sxs-lookup"><span data-stu-id="e10fd-167">Top worst servers by poor quality call percentage</span></span>

</div>

<div>

## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="e10fd-168">使用監控儀表板</span><span class="sxs-lookup"><span data-stu-id="e10fd-168">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="e10fd-169">如所述，預設總計會顯示目前日當週，並顯示過去六週的趨勢值。</span><span class="sxs-lookup"><span data-stu-id="e10fd-169">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="e10fd-170">如果您偏好以查看總針對本月 （以及過去六個月的趨勢值），按一下 [儀表板右上角中的**每月檢視**] 連結。</span><span class="sxs-lookup"><span data-stu-id="e10fd-170">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="e10fd-171">如果您決定要檢視每月總計，連結文字將變更為**每週檢視**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-171">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="e10fd-172">您可以切換回每週檢視，請按一下該連結。</span><span class="sxs-lookup"><span data-stu-id="e10fd-172">You can switch back to the weekly view by clicking that link.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e10fd-173">監控儀表板會限制您查看目前星期幾 （或） 的總計和過去六週 （或月數） 的趨勢值。</span><span class="sxs-lookup"><span data-stu-id="e10fd-173">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="e10fd-174">您無法變更這些日期和時間。</span><span class="sxs-lookup"><span data-stu-id="e10fd-174">You cannot change these dates and times.</span></span> <span data-ttu-id="e10fd-175">例如，您無法使用儀表板，來檢視報表總計開始前九個月的時間週期。</span><span class="sxs-lookup"><span data-stu-id="e10fd-175">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span>



</div>

<span data-ttu-id="e10fd-176">所顯示的值在**本週**]、 [**這個月**，或 [**今天**] 資料行連結您關於項目的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="e10fd-176">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="e10fd-177">請記住，資料行名稱並顯示在該欄的值將會經常而有所不同選擇評量，並根據您是否已選取每週檢視] 或 [每月檢視。</span><span class="sxs-lookup"><span data-stu-id="e10fd-177">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="e10fd-178">例如，如果您按一下 [顯示為**唯一的使用者登入**評量的總計您會看到**使用者註冊報告**在指定的時間週期內。</span><span class="sxs-lookup"><span data-stu-id="e10fd-178">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="e10fd-179">您可以回到 [監控儀表板隨時按一下**儀表板**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-179">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="e10fd-180">您也可以存取監控伺服器報告首頁上，按一下儀表板右上角的 [<STRONG>報告</STRONG>] 連結。</span><span class="sxs-lookup"><span data-stu-id="e10fd-180">You can also access the Monitoring Server Reports home page by clicking the <STRONG>Reports</STRONG> link in the upper right corner of the Dashboard.</span></span>



</div>

<span data-ttu-id="e10fd-181">**趨勢**資料行會顯示過去六週的 （或，視評量和過去六天或過去六個月的時間間隔而定） 顯示總計簡單線條圖。</span><span class="sxs-lookup"><span data-stu-id="e10fd-181">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="e10fd-182">這些簡單線條圖形會顯示一個未標示的資料點的每個時間週期 （例如，過去六週的每一個未標示的資料點）。</span><span class="sxs-lookup"><span data-stu-id="e10fd-182">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="e10fd-183">不過，您可以透過此圖形按住滑鼠指標擷取這些圖形的實際值。</span><span class="sxs-lookup"><span data-stu-id="e10fd-183">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="e10fd-184">在此情況下，工具提示顯示您的最大和最小值圖形中。</span><span class="sxs-lookup"><span data-stu-id="e10fd-184">In that case, a tooltip shows you the maximum and minimum values in the graph.</span></span>

</div>

<div>

## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="e10fd-185">從監控儀表板匯出資料</span><span class="sxs-lookup"><span data-stu-id="e10fd-185">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="e10fd-186">監控儀表板提供多種方式來匯出目前的儀表板檢視。</span><span class="sxs-lookup"><span data-stu-id="e10fd-186">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="e10fd-187">在儀表板] 工具列中，您會看到帶有綠色箭頭附加至它看起來像軟碟圖示。</span><span class="sxs-lookup"><span data-stu-id="e10fd-187">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="e10fd-188">如果您按一下此圖示，會出現] 下拉式清單，提供您下列的資料匯出格式：</span><span class="sxs-lookup"><span data-stu-id="e10fd-188">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>

  - <span data-ttu-id="e10fd-189">XML 檔附加報告資料</span><span class="sxs-lookup"><span data-stu-id="e10fd-189">XML file with report data</span></span>

  - <span data-ttu-id="e10fd-190">CSV (逗點分隔)</span><span class="sxs-lookup"><span data-stu-id="e10fd-190">CSV (comma delimited)</span></span>

  - <span data-ttu-id="e10fd-191">PDF</span><span class="sxs-lookup"><span data-stu-id="e10fd-191">PDF</span></span>

  - <span data-ttu-id="e10fd-192">MHTML (網頁封存)</span><span class="sxs-lookup"><span data-stu-id="e10fd-192">MHTML (web archive)</span></span>

  - <span data-ttu-id="e10fd-193">Excel</span><span class="sxs-lookup"><span data-stu-id="e10fd-193">Excel</span></span>

  - <span data-ttu-id="e10fd-194">TIFF 檔</span><span class="sxs-lookup"><span data-stu-id="e10fd-194">TIFF file</span></span>

  - <span data-ttu-id="e10fd-195">Word</span><span class="sxs-lookup"><span data-stu-id="e10fd-195">Word</span></span>

<span data-ttu-id="e10fd-196">若要匯出目前的儀表板檢視 （和其值），請按一下想要的匯出的選項。</span><span class="sxs-lookup"><span data-stu-id="e10fd-196">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="e10fd-197">Lync Server 2013 產生報告，以指定的格式，然後為您提供的開啟該報表，或將它儲存選項。</span><span class="sxs-lookup"><span data-stu-id="e10fd-197">Lync Server 2013 generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="e10fd-198">請注意，根據預設，Lync Server titles 報表**監控儀表板**並將它儲存到您的下載項目] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="e10fd-198">Note that, by default, Lync Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="e10fd-199">若要授與報表的不同的名稱，或將它儲存在不同的資料夾，按一下 [**儲存**] 按鈕旁的箭號，然後按一下 [**另存新檔**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-199">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="e10fd-200">如果您是好名稱**監控儀表板**並與需要儲存的下載項目資料夾中的報告您也可以按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e10fd-200">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>

<span data-ttu-id="e10fd-201">有可能，當您嘗試匯出儀表板的資料，**安全性警訊**] 對話方塊會顯示訊息以及 「 您目前的設定不允許下載這個檔案。 」</span><span class="sxs-lookup"><span data-stu-id="e10fd-201">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="e10fd-202">如果發生這種情形，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e10fd-202">If that occurs, do the following:</span></span>

  - <span data-ttu-id="e10fd-203">Internet Explorer 中，選取 [**網際網路選項**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-203">In Internet Explorer, select **Internet Options**.</span></span>

  - <span data-ttu-id="e10fd-204">在 [**網際網路選項**] 對話方塊的 [**安全性**] 索引標籤中，按一下 [**信任的網站**，然後按一下 [**網站**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-204">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>

  - <span data-ttu-id="e10fd-205">在 [**信任的網站**] 對話方塊中，按一下 [**新增**若要新增至信任的網站集合執行 Lync Server 2013 Reports Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="e10fd-205">In the **Trusted sites** dialog box, click **Add** to add the Lync Server 2013 that is running Lync Server 2013 Reports to the collections of trusted websites.</span></span>

  - <span data-ttu-id="e10fd-206">按一下 [**關閉**]，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="e10fd-206">Click **Close** and then click **OK**.</span></span>

<span data-ttu-id="e10fd-207">您接著需要重新整理監控儀表板之前所做的變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="e10fd-207">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="e10fd-208">若要這麼做，請按 f5 鍵或按一下 [儀表板工具列中的 [**重新整理**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e10fd-208">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="e10fd-209">（[**重新整理**] 圖示是圓中它的綠色箭頭的一組）。</span><span class="sxs-lookup"><span data-stu-id="e10fd-209">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>

<span data-ttu-id="e10fd-210">您也可以建立 Excel 試算表，其中包含即時資料摘要，包括最新的監控儀表板資料的連結。</span><span class="sxs-lookup"><span data-stu-id="e10fd-210">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="e10fd-211">若要建立的即時資料摘要的檔案，按一下工具列中橘色的 [**匯出至資料摘要**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e10fd-211">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>

<span data-ttu-id="e10fd-212">如果您偏好列印目前的儀表板，然後按一下工具列中的 [印表機] 圖示。</span><span class="sxs-lookup"><span data-stu-id="e10fd-212">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

