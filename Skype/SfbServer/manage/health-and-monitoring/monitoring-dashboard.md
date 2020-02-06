---
title: 在商務用 Skype 伺服器中使用監視儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 摘要：瞭解商務用 Skype 伺服器中的 [監視儀表板]。
ms.openlocfilehash: c2c86d5d5ede9581a2b41f32594118ab2605d63a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817822"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="57355-103">在商務用 Skype 伺服器中使用監視儀表板</span><span class="sxs-lookup"><span data-stu-id="57355-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="57355-104">**摘要：** 瞭解商務用 Skype 伺服器中的 [監視儀表板]。</span><span class="sxs-lookup"><span data-stu-id="57355-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="57355-105">[監視儀表板] 可讓系統管理員快速瞭解商務用 Skype Server 系統健康情況與系統使用量。</span><span class="sxs-lookup"><span data-stu-id="57355-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="57355-106">儀表板的設計目的是顯示主要系統規格的匯總視圖，並顯示下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="57355-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="57355-107">當天的合計。</span><span class="sxs-lookup"><span data-stu-id="57355-107">Totals for the current day.</span></span> <span data-ttu-id="57355-108">請注意，目前日期顯示的值代表從午夜到目前時間為止所記錄的資料（根據報表伺服器的當地時間）。</span><span class="sxs-lookup"><span data-stu-id="57355-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="57355-109">這表示您通常會查看部分日期的資料，而不是24小時的時間。</span><span class="sxs-lookup"><span data-stu-id="57355-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="57355-110">例如，如果伺服器的當地時間是 8:00 AM，您會看到八小時的資料，因為午夜和目前時間 8:00 AM 之間有八個小時。</span><span class="sxs-lookup"><span data-stu-id="57355-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="57355-111">周總計與過去六周的總趨勢。</span><span class="sxs-lookup"><span data-stu-id="57355-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="57355-112">當月總計及過去六個月的總趨勢（僅適用于系統使用量）。</span><span class="sxs-lookup"><span data-stu-id="57355-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="57355-113">請注意，您可以使用[CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) Cmdlet 來傳回用來存取商務用 Skype Server Monitoring 報告的 URL：</span><span class="sxs-lookup"><span data-stu-id="57355-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="57355-114">根據預設，[監視] 儀表板會針對目前的周數（以及前六周的趨勢總計）顯示下列度量單位的資料：</span><span class="sxs-lookup"><span data-stu-id="57355-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="57355-115">系統使用量指標</span><span class="sxs-lookup"><span data-stu-id="57355-115">System Usage Metrics</span></span>

 <span data-ttu-id="57355-116">**註冊**</span><span class="sxs-lookup"><span data-stu-id="57355-116">**Registration**</span></span>
  
- <span data-ttu-id="57355-117">唯一的使用者登錄</span><span class="sxs-lookup"><span data-stu-id="57355-117">Unique user logons</span></span>
    
  <span data-ttu-id="57355-118">**對等**</span><span class="sxs-lookup"><span data-stu-id="57355-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="57355-119">總會話數</span><span class="sxs-lookup"><span data-stu-id="57355-119">Total sessions</span></span>
    
- <span data-ttu-id="57355-120">IM 會話</span><span class="sxs-lookup"><span data-stu-id="57355-120">IM sessions</span></span>
    
- <span data-ttu-id="57355-121">音訊會話</span><span class="sxs-lookup"><span data-stu-id="57355-121">Audio sessions</span></span>
    
- <span data-ttu-id="57355-122">影片會議</span><span class="sxs-lookup"><span data-stu-id="57355-122">Video sessions</span></span>
    
- <span data-ttu-id="57355-123">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="57355-123">Application sharing</span></span>
    
- <span data-ttu-id="57355-124">音訊會話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="57355-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="57355-125">平均音訊會話分鐘數</span><span class="sxs-lookup"><span data-stu-id="57355-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="57355-126">**會議**</span><span class="sxs-lookup"><span data-stu-id="57355-126">**Conference**</span></span>
  
- <span data-ttu-id="57355-127">會議總數</span><span class="sxs-lookup"><span data-stu-id="57355-127">Total conferences</span></span>
    
- <span data-ttu-id="57355-128">IM 會議</span><span class="sxs-lookup"><span data-stu-id="57355-128">IM conferences</span></span>
    
- <span data-ttu-id="57355-129">A/V 會議</span><span class="sxs-lookup"><span data-stu-id="57355-129">A/V conferences</span></span>
    
- <span data-ttu-id="57355-130">應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="57355-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="57355-131">網路會議</span><span class="sxs-lookup"><span data-stu-id="57355-131">Web conferences</span></span>
    
- <span data-ttu-id="57355-132">召集人總計</span><span class="sxs-lookup"><span data-stu-id="57355-132">Total organizers</span></span>
    
- <span data-ttu-id="57355-133">A/V 會議紀要總計</span><span class="sxs-lookup"><span data-stu-id="57355-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="57355-134">速率.A/V 會議紀要</span><span class="sxs-lookup"><span data-stu-id="57355-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="57355-135">PSTN 會議總數</span><span class="sxs-lookup"><span data-stu-id="57355-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="57355-136">PSTN 參與者總數</span><span class="sxs-lookup"><span data-stu-id="57355-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="57355-137">PSTN 參與者通話總分鐘數</span><span class="sxs-lookup"><span data-stu-id="57355-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="57355-138">除了系統使用標準之外，下列度量單位還會顯示當天及前六天的總計（如果您選取 [**每週檢視**]），或是在您選取 [**每月檢視**] 時，則為 [目前周] 和 [過去六周]。</span><span class="sxs-lookup"><span data-stu-id="57355-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="57355-139">每個使用者呼叫診斷</span><span class="sxs-lookup"><span data-stu-id="57355-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="57355-140">**有通話失敗的使用者**</span><span class="sxs-lookup"><span data-stu-id="57355-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="57355-141">使用通話失敗的使用者總數</span><span class="sxs-lookup"><span data-stu-id="57355-141">Total users with call failures</span></span>
    
- <span data-ttu-id="57355-142">含通話失敗的會議召集人</span><span class="sxs-lookup"><span data-stu-id="57355-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="57355-143">**較差品質通話的使用者**</span><span class="sxs-lookup"><span data-stu-id="57355-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="57355-144">具有較差品質通話的使用者總數</span><span class="sxs-lookup"><span data-stu-id="57355-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="57355-145">呼叫診斷</span><span class="sxs-lookup"><span data-stu-id="57355-145">Call Diagnostics</span></span>

<span data-ttu-id="57355-146">對等</span><span class="sxs-lookup"><span data-stu-id="57355-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="57355-147">失敗總計</span><span class="sxs-lookup"><span data-stu-id="57355-147">Total failures</span></span>
    
- <span data-ttu-id="57355-148">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-148">Overall failure rate</span></span>
    
- <span data-ttu-id="57355-149">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-149">IM failure rate</span></span>
    
- <span data-ttu-id="57355-150">音訊失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-150">Audio failure rate</span></span>
    
- <span data-ttu-id="57355-151">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="57355-152">會議</span><span class="sxs-lookup"><span data-stu-id="57355-152">Conference</span></span>
  
- <span data-ttu-id="57355-153">失敗總計</span><span class="sxs-lookup"><span data-stu-id="57355-153">Total failures</span></span>
    
- <span data-ttu-id="57355-154">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-154">Overall failure rate</span></span>
    
- <span data-ttu-id="57355-155">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-155">IM failure rate</span></span>
    
- <span data-ttu-id="57355-156">A/V 失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-156">A/V failure rate</span></span>
    
- <span data-ttu-id="57355-157">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="57355-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="57355-158">依失敗的會話排前五台伺服器</span><span class="sxs-lookup"><span data-stu-id="57355-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="57355-159">媒體質量診斷</span><span class="sxs-lookup"><span data-stu-id="57355-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="57355-160">對等</span><span class="sxs-lookup"><span data-stu-id="57355-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="57355-161">低品質通話總計</span><span class="sxs-lookup"><span data-stu-id="57355-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="57355-162">品質不佳的通話百分比</span><span class="sxs-lookup"><span data-stu-id="57355-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="57355-163">品質不佳的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="57355-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="57355-164">會議</span><span class="sxs-lookup"><span data-stu-id="57355-164">Conference</span></span>
  
- <span data-ttu-id="57355-165">低品質通話總計</span><span class="sxs-lookup"><span data-stu-id="57355-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="57355-166">品質不佳的通話百分比</span><span class="sxs-lookup"><span data-stu-id="57355-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="57355-167">品質不佳的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="57355-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="57355-168">低品質通話百分比的最差伺服器</span><span class="sxs-lookup"><span data-stu-id="57355-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="57355-169">使用 [監視儀表板]</span><span class="sxs-lookup"><span data-stu-id="57355-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="57355-170">如前所述，預設的合計會顯示在目前的周，而趨勢值則會顯示過去六周。</span><span class="sxs-lookup"><span data-stu-id="57355-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="57355-171">如果您想要查看當月的合計（以及過去六個月的趨勢值），請按一下儀表板右上角的 [**每月檢視**] 連結。</span><span class="sxs-lookup"><span data-stu-id="57355-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="57355-172">如果您決定要查看每月總計，連結文字將會變更為 [**每週] 視圖**。</span><span class="sxs-lookup"><span data-stu-id="57355-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="57355-173">您可以按一下該連結，切換回 [每週] 視圖。</span><span class="sxs-lookup"><span data-stu-id="57355-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="57355-174">[監視儀表板] 會限制您在過去六周（或幾個月）的 [本周] （或 [月]）和趨勢值中查看 [合計]。</span><span class="sxs-lookup"><span data-stu-id="57355-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="57355-175">您無法變更這些日期和時間。</span><span class="sxs-lookup"><span data-stu-id="57355-175">You cannot change these dates and times.</span></span> <span data-ttu-id="57355-176">例如，您無法使用儀表板來查看第九個月前的時間週期的報表合計。</span><span class="sxs-lookup"><span data-stu-id="57355-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="57355-177">[**本周]、[\*\*\*\*本月**] 或 [ **Today** ] 欄中顯示的值會將您連結到專案的更詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="57355-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="57355-178">請記住，欄名稱和顯示在該欄中的值通常會根據所選的度量，以及您是否已選取 [每週檢視] 或 [每月] 視圖而有所不同。</span><span class="sxs-lookup"><span data-stu-id="57355-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="57355-179">例如，如果您按一下 [針對**唯一的使用者登錄**統計顯示的合計]，您會在指定的時間範圍內看到 [**使用者註冊] 報告**。</span><span class="sxs-lookup"><span data-stu-id="57355-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="57355-180">您隨時都可以按一下 [**儀表板**] 返回 [監視] 儀表板。</span><span class="sxs-lookup"><span data-stu-id="57355-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="57355-181">您也可以按一下儀表板右上角的 [**報告**] 連結，以存取 [監視伺服器報告] 首頁。</span><span class="sxs-lookup"><span data-stu-id="57355-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="57355-182">[**趨勢**] 欄會顯示一個簡單的線形圖形，其中顯示過去六周的總計（或是根據公制和時間間隔、過去六天或過去六個月）。</span><span class="sxs-lookup"><span data-stu-id="57355-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="57355-183">這些簡單的折線圖會針對每個時間段顯示一個未標記的資料點（例如，過去六周內的一個未標記資料點）。</span><span class="sxs-lookup"><span data-stu-id="57355-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="57355-184">不過，您可以透過將滑鼠指標放在圖形上，來檢索這些圖表的實際值。</span><span class="sxs-lookup"><span data-stu-id="57355-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="57355-185">在這種情況下，工具提示會顯示圖形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="57355-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="57355-186">從 [監控] 儀表板匯出資料</span><span class="sxs-lookup"><span data-stu-id="57355-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="57355-187">[監視儀表板] 提供多種匯出目前儀表板視圖的方法。</span><span class="sxs-lookup"><span data-stu-id="57355-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="57355-188">在 [儀表板] 工具列上，您會看到一個圖示，看起來像是一個附加了綠色箭號的軟碟。</span><span class="sxs-lookup"><span data-stu-id="57355-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="57355-189">如果您按一下這個圖示，就會出現下拉式清單，提供下列資料匯出格式：</span><span class="sxs-lookup"><span data-stu-id="57355-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="57355-190">含報表資料的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="57355-190">XML file with report data</span></span>
    
- <span data-ttu-id="57355-191">CSV （逗號分隔）</span><span class="sxs-lookup"><span data-stu-id="57355-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="57355-192">PDF</span><span class="sxs-lookup"><span data-stu-id="57355-192">PDF</span></span>
    
- <span data-ttu-id="57355-193">MHTML （網頁檔案）</span><span class="sxs-lookup"><span data-stu-id="57355-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="57355-194">Excel</span><span class="sxs-lookup"><span data-stu-id="57355-194">Excel</span></span>
    
- <span data-ttu-id="57355-195">TIFF 檔案</span><span class="sxs-lookup"><span data-stu-id="57355-195">TIFF file</span></span>
    
- <span data-ttu-id="57355-196">Word</span><span class="sxs-lookup"><span data-stu-id="57355-196">Word</span></span>
    
<span data-ttu-id="57355-197">若要匯出目前的儀表板視圖（及其值），請按一下所需的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="57355-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="57355-198">商務用 Skype 伺服器會以指定的格式產生報表，然後提供開啟或儲存該報表的選項。</span><span class="sxs-lookup"><span data-stu-id="57355-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="57355-199">請注意，根據預設，商務用 Skype 伺服器標題是 [報告**監控] 儀表板**，並將它儲存到您的 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="57355-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="57355-200">若要為報表指定不同的名稱，或將其儲存在不同的資料夾，請按一下 [**儲存**] 按鈕旁的箭號，然後按一下 [**另存**新檔]。</span><span class="sxs-lookup"><span data-stu-id="57355-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="57355-201">如果您使用 [名稱**監視] 儀表板**，並將報告儲存在 [下載] 資料夾中，您就可以按一下 [**儲存**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="57355-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="57355-202">您可以嘗試匯出儀表板資料時，會出現 [**安全性警告**] 對話方塊，並顯示「您目前的設定不允許下載此檔案」訊息。</span><span class="sxs-lookup"><span data-stu-id="57355-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="57355-203">如果發生這種情況，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57355-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="57355-204">在 Internet Explorer 中，選取 [**網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="57355-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="57355-205">在 [**網際網路選項**] 對話方塊中，按一下 [**安全性**] 索引標籤上的 [**信任的網站**]，然後按一下 [**網站**]。</span><span class="sxs-lookup"><span data-stu-id="57355-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="57355-206">在 [**信任的網站**] 對話方塊中，按一下 [**新增**]，將執行商務用 Skype 伺服器報告的商務用 skype 伺服器新增至信任的網站集合。</span><span class="sxs-lookup"><span data-stu-id="57355-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="57355-207">按一下 [**關閉**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="57355-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="57355-208">然後，您必須重新整理監視儀表板，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="57355-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="57355-209">若要這樣做，請按 F5 或按一下儀表板工具列中**的 [重新**整理] 圖示。</span><span class="sxs-lookup"><span data-stu-id="57355-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="57355-210">（[重新整理 **] 圖示是**一個在其中有一對綠色箭號的圓圈）。</span><span class="sxs-lookup"><span data-stu-id="57355-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="57355-211">您也可以建立包含即時資料摘要的 Excel 試算表，其中包含最新監視儀表板資料的連結。</span><span class="sxs-lookup"><span data-stu-id="57355-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="57355-212">若要建立即時資料摘要檔案，請按一下工具列中的 [橙色**匯出至資料**摘要] 圖示。</span><span class="sxs-lookup"><span data-stu-id="57355-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="57355-213">如果您想要列印目前的儀表板，請按一下工具列中的 [印表機] 圖示。</span><span class="sxs-lookup"><span data-stu-id="57355-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

