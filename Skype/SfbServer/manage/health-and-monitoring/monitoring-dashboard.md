---
title: 在商務用 Skype Server 中使用監控儀表板
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e00e5783-116f-481f-ad17-3af847d6769a
description: 摘要：瞭解商務用 Skype Server 中的監控儀表板。
ms.openlocfilehash: 98a96b8a513bad485a25aff76a69d787fb3079b0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827783"
---
# <a name="using-the-monitoring-dashboard-in-skype-for-business-server"></a><span data-ttu-id="ecf81-103">在商務用 Skype Server 中使用監控儀表板</span><span class="sxs-lookup"><span data-stu-id="ecf81-103">Using the Monitoring Dashboard in Skype for Business Server</span></span>
 
<span data-ttu-id="ecf81-104">**摘要：** 深入瞭解商務用 Skype Server 中的監控儀表板。</span><span class="sxs-lookup"><span data-stu-id="ecf81-104">**Summary:** Learn about the Monitoring Dashboard in Skype for Business Server.</span></span>
  
<span data-ttu-id="ecf81-105">監控儀表板為系統管理員供應商務用 Skype Server 系統健康情況與系統使用狀況的快速綜述。</span><span class="sxs-lookup"><span data-stu-id="ecf81-105">The Monitoring Dashboard provides administrators with a quick overview of their Skype for Business Server system health and system usage.</span></span> <span data-ttu-id="ecf81-106">儀表板的設計目的是顯示主要系統計量的匯總視圖，並顯示下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="ecf81-106">The Dashboard is designed to show an aggregate view of key system metrics and to do so by displaying either:</span></span>
  
- <span data-ttu-id="ecf81-107">當天的合計。</span><span class="sxs-lookup"><span data-stu-id="ecf81-107">Totals for the current day.</span></span> <span data-ttu-id="ecf81-108">請注意，目前所顯示之天的值表示從午夜直到目前時間為止的資料 (，取決於報表伺服器的本機時間) 。</span><span class="sxs-lookup"><span data-stu-id="ecf81-108">Note that values shown for the current day represent data that has been recorded from midnight until the current time (based on the local time of the reporting server).</span></span> <span data-ttu-id="ecf81-109">這表示您通常會在一天中查看資料，而不是24小時的期間。</span><span class="sxs-lookup"><span data-stu-id="ecf81-109">That means that you will typically be viewing data for a partial day and not for a 24-hour period.</span></span> <span data-ttu-id="ecf81-110">例如，如果伺服器的本地時間是 8:00 AM，您會看到8小時的資料，因為介於午夜和目前的 8:00 AM 之間有八小時的時間。</span><span class="sxs-lookup"><span data-stu-id="ecf81-110">For example, if the local time of the server is 8:00 AM, you see eight hours' worth of data because there are eight hours between midnight and the current time of 8:00 AM.</span></span>
    
- <span data-ttu-id="ecf81-111">本周的總數和過去六周的趨勢總計。</span><span class="sxs-lookup"><span data-stu-id="ecf81-111">Totals for the week, and trend totals for the past six weeks.</span></span>
    
- <span data-ttu-id="ecf81-112">每月的總數，以及過去六個月的趨勢總計 (僅限系統使用量) 。</span><span class="sxs-lookup"><span data-stu-id="ecf81-112">Totals for the month, and trend totals for the past six months (for system usage only).</span></span>
    
<span data-ttu-id="ecf81-113">請注意，您可以使用 [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) Cmdlet 來傳回用來存取商務用 Skype Server Monitoring REPORTS 的 URL：</span><span class="sxs-lookup"><span data-stu-id="ecf81-113">Note that you can use the [Get-CsReportingConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csreportingconfiguration?view=skype-ps) cmdlet to return the URL used for accessing Skype for Business Server Monitoring Reports:</span></span>
  
```PowerShell
Get-CsReportingConfiguration
```

<span data-ttu-id="ecf81-114">根據預設，監控儀表板會顯示目前星期的下列度量值的資料 (及過去六周的趨勢總計) ：</span><span class="sxs-lookup"><span data-stu-id="ecf81-114">By default, the Monitoring Dashboard shows data for the following metrics for the current week (and trend totals for the previous six weeks):</span></span>
  
## <a name="system-usage-metrics"></a><span data-ttu-id="ecf81-115">系統使用狀況計量</span><span class="sxs-lookup"><span data-stu-id="ecf81-115">System Usage Metrics</span></span>

 <span data-ttu-id="ecf81-116">**註冊**</span><span class="sxs-lookup"><span data-stu-id="ecf81-116">**Registration**</span></span>
  
- <span data-ttu-id="ecf81-117">唯一的使用者登入</span><span class="sxs-lookup"><span data-stu-id="ecf81-117">Unique user logons</span></span>
    
  <span data-ttu-id="ecf81-118">**對等**</span><span class="sxs-lookup"><span data-stu-id="ecf81-118">**Peer-to-peer**</span></span>
  
- <span data-ttu-id="ecf81-119">工作階段總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-119">Total sessions</span></span>
    
- <span data-ttu-id="ecf81-120">IM 會話</span><span class="sxs-lookup"><span data-stu-id="ecf81-120">IM sessions</span></span>
    
- <span data-ttu-id="ecf81-121">音訊會話</span><span class="sxs-lookup"><span data-stu-id="ecf81-121">Audio sessions</span></span>
    
- <span data-ttu-id="ecf81-122">影片</span><span class="sxs-lookup"><span data-stu-id="ecf81-122">Video sessions</span></span>
    
- <span data-ttu-id="ecf81-123">應用程式共用</span><span class="sxs-lookup"><span data-stu-id="ecf81-123">Application sharing</span></span>
    
- <span data-ttu-id="ecf81-124">音訊會話分鐘總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-124">Total audio session minutes</span></span>
    
- <span data-ttu-id="ecf81-125">平均音訊會話分鐘數</span><span class="sxs-lookup"><span data-stu-id="ecf81-125">Avg. audio session minutes</span></span>
    
  <span data-ttu-id="ecf81-126">**會議**</span><span class="sxs-lookup"><span data-stu-id="ecf81-126">**Conference**</span></span>
  
- <span data-ttu-id="ecf81-127">會議總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-127">Total conferences</span></span>
    
- <span data-ttu-id="ecf81-128">IM 會議</span><span class="sxs-lookup"><span data-stu-id="ecf81-128">IM conferences</span></span>
    
- <span data-ttu-id="ecf81-129">會議 A/V</span><span class="sxs-lookup"><span data-stu-id="ecf81-129">A/V conferences</span></span>
    
- <span data-ttu-id="ecf81-130">應用程式共用會議</span><span class="sxs-lookup"><span data-stu-id="ecf81-130">Application sharing conferences</span></span>
    
- <span data-ttu-id="ecf81-131">Web 會議</span><span class="sxs-lookup"><span data-stu-id="ecf81-131">Web conferences</span></span>
    
- <span data-ttu-id="ecf81-132">召集人總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-132">Total organizers</span></span>
    
- <span data-ttu-id="ecf81-133">A/V 會議總分鐘數</span><span class="sxs-lookup"><span data-stu-id="ecf81-133">Total A/V conference minutes</span></span>
    
- <span data-ttu-id="ecf81-134">Avg。A/V 會議紀要</span><span class="sxs-lookup"><span data-stu-id="ecf81-134">Avg. A/V conference minutes</span></span>
    
- <span data-ttu-id="ecf81-135">PSTN 會議總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-135">Total PSTN conferences</span></span>
    
- <span data-ttu-id="ecf81-136">PSTN 參與者總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-136">Total PSTN participants</span></span>
    
- <span data-ttu-id="ecf81-137">PSTN 參與者分鐘總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-137">Total PSTN participant minutes</span></span>
    
<span data-ttu-id="ecf81-138">除了系統使用狀況度量之外，下列度量值會顯示當天和前六天的總計 (如果您選取 [) **每週** 模式] 或 [當周] 或 [過去六周]，則選取 [每月] [ **查看**]。</span><span class="sxs-lookup"><span data-stu-id="ecf81-138">In addition to the System Usage metrics, the following metrics displays total for the current day and the previous six days (if you select **Weekly View**) or for the current week and the past six weeks if you select **Monthly View**.</span></span>
  
## <a name="per-user-call-diagnostics"></a><span data-ttu-id="ecf81-139">Per-User 通話診斷</span><span class="sxs-lookup"><span data-stu-id="ecf81-139">Per-User Call Diagnostics</span></span>

 <span data-ttu-id="ecf81-140">**具有通話失敗的使用者**</span><span class="sxs-lookup"><span data-stu-id="ecf81-140">**Users with call failures**</span></span>
  
- <span data-ttu-id="ecf81-141">具有通話失敗的使用者總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-141">Total users with call failures</span></span>
    
- <span data-ttu-id="ecf81-142">具有通話失敗的會議召集人</span><span class="sxs-lookup"><span data-stu-id="ecf81-142">Conference organizers with call failures</span></span>
    
  <span data-ttu-id="ecf81-143">**通話品質不良的使用者**</span><span class="sxs-lookup"><span data-stu-id="ecf81-143">**Users with poor quality calls**</span></span>
  
- <span data-ttu-id="ecf81-144">具有不良通話品質的使用者總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-144">Total users with poor quality calls</span></span>
    
## <a name="call-diagnostics"></a><span data-ttu-id="ecf81-145">通話診斷</span><span class="sxs-lookup"><span data-stu-id="ecf81-145">Call Diagnostics</span></span>

<span data-ttu-id="ecf81-146">對等</span><span class="sxs-lookup"><span data-stu-id="ecf81-146">Peer-to-peer</span></span>
  
- <span data-ttu-id="ecf81-147">失敗總計</span><span class="sxs-lookup"><span data-stu-id="ecf81-147">Total failures</span></span>
    
- <span data-ttu-id="ecf81-148">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-148">Overall failure rate</span></span>
    
- <span data-ttu-id="ecf81-149">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-149">IM failure rate</span></span>
    
- <span data-ttu-id="ecf81-150">音訊失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-150">Audio failure rate</span></span>
    
- <span data-ttu-id="ecf81-151">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-151">Application sharing failure rate</span></span>
    
<span data-ttu-id="ecf81-152">會議</span><span class="sxs-lookup"><span data-stu-id="ecf81-152">Conference</span></span>
  
- <span data-ttu-id="ecf81-153">失敗總計</span><span class="sxs-lookup"><span data-stu-id="ecf81-153">Total failures</span></span>
    
- <span data-ttu-id="ecf81-154">整體失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-154">Overall failure rate</span></span>
    
- <span data-ttu-id="ecf81-155">IM 失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-155">IM failure rate</span></span>
    
- <span data-ttu-id="ecf81-156">A/V 失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-156">A/V failure rate</span></span>
    
- <span data-ttu-id="ecf81-157">應用程式共用失敗率</span><span class="sxs-lookup"><span data-stu-id="ecf81-157">Application sharing failure rate</span></span>
    
<span data-ttu-id="ecf81-158">依失敗會話的前5部伺服器</span><span class="sxs-lookup"><span data-stu-id="ecf81-158">Top five servers by failed sessions</span></span>
  
## <a name="media-quality-diagnostics"></a><span data-ttu-id="ecf81-159">媒體質量診斷</span><span class="sxs-lookup"><span data-stu-id="ecf81-159">Media Quality Diagnostics</span></span>

<span data-ttu-id="ecf81-160">對等</span><span class="sxs-lookup"><span data-stu-id="ecf81-160">Peer-to-peer</span></span>
  
- <span data-ttu-id="ecf81-161">品質不良通話總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-161">Total poor quality calls</span></span>
    
- <span data-ttu-id="ecf81-162">品質不良通話百分比</span><span class="sxs-lookup"><span data-stu-id="ecf81-162">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ecf81-163">品質不良的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="ecf81-163">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ecf81-164">會議</span><span class="sxs-lookup"><span data-stu-id="ecf81-164">Conference</span></span>
  
- <span data-ttu-id="ecf81-165">品質不良通話總數</span><span class="sxs-lookup"><span data-stu-id="ecf81-165">Total poor quality calls</span></span>
    
- <span data-ttu-id="ecf81-166">品質不良通話百分比</span><span class="sxs-lookup"><span data-stu-id="ecf81-166">Poor quality call percentage</span></span>
    
- <span data-ttu-id="ecf81-167">品質不良的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="ecf81-167">PSTN calls with poor quality</span></span>
    
<span data-ttu-id="ecf81-168">低品質通話百分比的最惡化伺服器</span><span class="sxs-lookup"><span data-stu-id="ecf81-168">Top worst servers by poor quality call percentage</span></span>
  
## <a name="working-with-the-monitoring-dashboard"></a><span data-ttu-id="ecf81-169">使用監控儀表板</span><span class="sxs-lookup"><span data-stu-id="ecf81-169">Working with the Monitoring Dashboard</span></span>

<span data-ttu-id="ecf81-170">如前文所述，目前的星期顯示預設合計，而走向值則顯示過去六周。</span><span class="sxs-lookup"><span data-stu-id="ecf81-170">As noted, by default totals are shown for the current week and trend values are shown for the past six weeks.</span></span> <span data-ttu-id="ecf81-171">如果您想要查看目前月份的合計 (以及過去六個月的趨勢值) ，請按一下儀表板右上角的 [ **月度 View** ] 連結。</span><span class="sxs-lookup"><span data-stu-id="ecf81-171">If you would prefer to see totals for the current month (as well as trend values for the past six months), click the **Monthly View** link in the upper right corner of the dashboard.</span></span> <span data-ttu-id="ecf81-172">如果您決定要查看每月合計，連結文字會變更為 **每週** 模式。</span><span class="sxs-lookup"><span data-stu-id="ecf81-172">If you decide to view monthly totals, the link text will change to **Weekly View**.</span></span> <span data-ttu-id="ecf81-173">您可以按一下該連結，切換回每週的視圖。</span><span class="sxs-lookup"><span data-stu-id="ecf81-173">You can switch back to the weekly view by clicking that link.</span></span>
  
> [!TIP]
> <span data-ttu-id="ecf81-174">監控儀表板會限制您在過去六周的 [ (] 或 [月]) 和「趨勢」值 (或月) 中查看目前的周數。</span><span class="sxs-lookup"><span data-stu-id="ecf81-174">The Monitoring Dashboard restricts you to looking at totals for the current week (or month) and trend values for the past six weeks (or months).</span></span> <span data-ttu-id="ecf81-175">您無法變更這些日期和時間。</span><span class="sxs-lookup"><span data-stu-id="ecf81-175">You cannot change these dates and times.</span></span> <span data-ttu-id="ecf81-176">例如，您無法使用儀表板來查看過去9個月前的時段的報表總計。</span><span class="sxs-lookup"><span data-stu-id="ecf81-176">For example, you cannot use the Dashboard to view report totals for the time period beginning nine months ago.</span></span> 
  
<span data-ttu-id="ecf81-177">在 [ **本周**]、[ **月**] 或 [ **今日** ] 欄中顯示的值可連結至更詳細的專案相關資訊。</span><span class="sxs-lookup"><span data-stu-id="ecf81-177">The values shown in the **This week**, **This month**, or **Today** columns link you to more detailed information about the item.</span></span> <span data-ttu-id="ecf81-178">請記住，欄名稱及顯示在該欄中的值通常會因所選擇的度量而異，也取決於您是否已選取每週檢視或每月模式。</span><span class="sxs-lookup"><span data-stu-id="ecf81-178">Keep in mind that the column name and the values displayed in that column will often differ depending on the metric chosen and depending on whether you have selected weekly view or monthly view.</span></span> <span data-ttu-id="ecf81-179">例如，如果您按一下 [ **唯一使用者** 登入量] 的 [顯示總數]，您將會看到 **使用者註冊報告** 指定的時間週期。</span><span class="sxs-lookup"><span data-stu-id="ecf81-179">For example, if you click the totals shown for the **Unique user logons** metric you will see the **User Registration Report** for the specified time period.</span></span> <span data-ttu-id="ecf81-180">您可以隨時按一下 [ **儀表板**] 以回到監控儀表板。</span><span class="sxs-lookup"><span data-stu-id="ecf81-180">You can return to the Monitoring Dashboard at any time by clicking **Dashboard**.</span></span>
  
> [!TIP]
> <span data-ttu-id="ecf81-181">您也可以按一下儀表板右上角的 [ **報告** ] 連結，以存取監控伺服器報告首頁。</span><span class="sxs-lookup"><span data-stu-id="ecf81-181">You can also access the Monitoring Server Reports home page by clicking the **Reports** link in the upper right corner of the Dashboard.</span></span>
  
<span data-ttu-id="ecf81-182">**Trend** 欄會顯示簡單的折線圖，顯示過去六周的總計 (，或根據度量和時間間隔、過去六個月或過去六個月) 。</span><span class="sxs-lookup"><span data-stu-id="ecf81-182">The **Trend** column displays a simple line graph that shows totals for the past six weeks (or, depending on the metric and the time interval, the past six days or the past six months).</span></span> <span data-ttu-id="ecf81-183">這些簡易折線圖會針對每個時間 (週期顯示一個未標記的資料點，例如，每個過去六周的每一個未標記的資料點) 。</span><span class="sxs-lookup"><span data-stu-id="ecf81-183">These simple line graphs display one unlabeled data point for each time period (for example, one unlabeled data point for each of the past six weeks).</span></span> <span data-ttu-id="ecf81-184">不過，您可以在圖形上按住滑鼠指標，以取得這些圖形的實際值。</span><span class="sxs-lookup"><span data-stu-id="ecf81-184">However, you can retrieve actual values for these graphs by holding your mouse pointer over the graph.</span></span> <span data-ttu-id="ecf81-185">在此情況下，工具提示會顯示圖形中的最大值和最小值。</span><span class="sxs-lookup"><span data-stu-id="ecf81-185">In that case, a tool tip shows you the maximum and minimum values in the graph.</span></span>
  
## <a name="exporting-data-from-the-monitoring-dashboard"></a><span data-ttu-id="ecf81-186">從監控儀表板匯出資料</span><span class="sxs-lookup"><span data-stu-id="ecf81-186">Exporting Data from the Monitoring Dashboard</span></span>

<span data-ttu-id="ecf81-187">監控儀表板提供多種方式可匯出目前的儀表板視圖。</span><span class="sxs-lookup"><span data-stu-id="ecf81-187">The Monitoring Dashboard provides a number of ways to export the current dashboard view.</span></span> <span data-ttu-id="ecf81-188">在 [儀表板] 工具列上，您會看到一個圖示，看起來像是連有綠色箭號的軟碟。</span><span class="sxs-lookup"><span data-stu-id="ecf81-188">On the Dashboard toolbar, you'll see an icon that looks like a floppy disk with a green arrow attached to it.</span></span> <span data-ttu-id="ecf81-189">如果您按一下此圖示，就會出現下拉式清單，提供下列資料匯出格式：</span><span class="sxs-lookup"><span data-stu-id="ecf81-189">If you click this icon, a dropdown list will appear giving you the following data export formats:</span></span>
  
- <span data-ttu-id="ecf81-190">XML 檔附加報告資料</span><span class="sxs-lookup"><span data-stu-id="ecf81-190">XML file with report data</span></span>
    
- <span data-ttu-id="ecf81-191">CSV (逗點分隔)</span><span class="sxs-lookup"><span data-stu-id="ecf81-191">CSV (comma delimited)</span></span>
    
- <span data-ttu-id="ecf81-192">PDF</span><span class="sxs-lookup"><span data-stu-id="ecf81-192">PDF</span></span>
    
- <span data-ttu-id="ecf81-193">MHTML (網頁封存)</span><span class="sxs-lookup"><span data-stu-id="ecf81-193">MHTML (web archive)</span></span>
    
- <span data-ttu-id="ecf81-194">Excel</span><span class="sxs-lookup"><span data-stu-id="ecf81-194">Excel</span></span>
    
- <span data-ttu-id="ecf81-195">TIFF 檔</span><span class="sxs-lookup"><span data-stu-id="ecf81-195">TIFF file</span></span>
    
- <span data-ttu-id="ecf81-196">Word</span><span class="sxs-lookup"><span data-stu-id="ecf81-196">Word</span></span>
    
<span data-ttu-id="ecf81-197">若要匯出目前的儀表板 view (及其值) ，請按一下所需的匯出選項。</span><span class="sxs-lookup"><span data-stu-id="ecf81-197">To export the current dashboard view (and its values), click the desired export option.</span></span> <span data-ttu-id="ecf81-198">商務用 Skype 伺服器會以指定的格式產生報表，然後提供開啟該報表或儲存該報表的選項。</span><span class="sxs-lookup"><span data-stu-id="ecf81-198">Skype for Business Server generates a report in the specified format and then give you the option of opening that report or saving it.</span></span> <span data-ttu-id="ecf81-199">請注意，根據預設，商務用 Skype 伺服器標題為 [報表 **監控] 儀表板** ，並將其儲存至 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ecf81-199">Note that, by default, Skype for Business Server titles the report **Monitoring Dashboard** and saves it to your Downloads folder.</span></span> <span data-ttu-id="ecf81-200">若要讓報表使用不同的名稱，或將它儲存在不同的資料夾中，請按一下 [ **儲存** ] 按鈕旁的箭號，然後按一下 [ **另存** 新檔]。</span><span class="sxs-lookup"><span data-stu-id="ecf81-200">To give the report a different name or to store it in a different folder, click the arrow next to the **Save** button and then click **Save As**.</span></span> <span data-ttu-id="ecf81-201">如果您很熟悉名稱 **監控儀表板** ，且已將報告儲存在 [下載] 資料夾中，您只需要按一下 [ **儲存** ] 按鈕即可。</span><span class="sxs-lookup"><span data-stu-id="ecf81-201">If you are fine with name **Monitoring Dashboard** and with having the report saved in the Downloads folder you can just click the **Save** button.</span></span>
  
<span data-ttu-id="ecf81-202">當您嘗試匯出儀表板資料時，可能會出現 [ **安全性警示** ] 對話方塊，並顯示「目前的設定不允許下載這個檔案」訊息。</span><span class="sxs-lookup"><span data-stu-id="ecf81-202">It's possible that, when you try to export dashboard data, a **Security Alert** dialog box will appear along with the message "Your current settings do not allow this file to be downloaded."</span></span> <span data-ttu-id="ecf81-203">如果發生這種情況，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ecf81-203">If that occurs, do the following:</span></span>
  
- <span data-ttu-id="ecf81-204">在 Internet Explorer 中，選取 [ **網際網路選項**]。</span><span class="sxs-lookup"><span data-stu-id="ecf81-204">In Internet Explorer, select **Internet Options**.</span></span>
    
- <span data-ttu-id="ecf81-205">在 [ **網際網路選項** ] 對話方塊的 [ **安全性** ] 索引標籤上，按一下 [ **信任的網站** ]，然後按一下 [ **網站**]。</span><span class="sxs-lookup"><span data-stu-id="ecf81-205">In the **Internet Options** dialog box, on the **Security** tab, click **Trusted sites** and then click **Sites**.</span></span>
    
- <span data-ttu-id="ecf81-206">在 [ **信任的網站** ] 對話方塊中，按一下 [ **新增** ]，將執行商務用 Skype 伺服器報告的商務用 skype 伺服器新增至信任的網站集合。</span><span class="sxs-lookup"><span data-stu-id="ecf81-206">In the **Trusted sites** dialog box, click **Add** to add the Skype for Business Server that is running Skype for Business Server Reports to the collections of trusted websites.</span></span>
    
- <span data-ttu-id="ecf81-207">按一下 [ **關閉** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ecf81-207">Click **Close** and then click **OK**.</span></span>
    
<span data-ttu-id="ecf81-208">您必須先重新整理監控儀表板，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="ecf81-208">You will then need to refresh the Monitoring Dashboard before the changes take effect.</span></span> <span data-ttu-id="ecf81-209">若要這麼做，請按 F5 或按一下儀表板工具列中的重新 **整理圖示。**</span><span class="sxs-lookup"><span data-stu-id="ecf81-209">To do that, either press F5 or click the **Refresh** icon in the Dashboard toolbar.</span></span> <span data-ttu-id="ecf81-210"> (重新 **整理圖示是** 具有一對綠色箭號的圓形。 ) </span><span class="sxs-lookup"><span data-stu-id="ecf81-210">(The **Refresh** icon is a circle with a pair of green arrows in it.)</span></span>
  
<span data-ttu-id="ecf81-211">您也可以建立包含即時資料摘要的 Excel 試算表，其中包含最新監控儀表板資料的連結。</span><span class="sxs-lookup"><span data-stu-id="ecf81-211">You can also create an Excel spreadsheet that includes live data feeds, which includes links to the latest Monitoring Dashboard data.</span></span> <span data-ttu-id="ecf81-212">若要建立即時資料摘要檔案，請按一下工具列中的 [橙色 **匯出至資料** 摘要] 圖示。</span><span class="sxs-lookup"><span data-stu-id="ecf81-212">To create a live data feed file, click the orange **Export to Data Feed** icon in the toolbar.</span></span>
  
<span data-ttu-id="ecf81-213">如果您想要列印目前的儀表板，請按一下工具列中的印表機圖示。</span><span class="sxs-lookup"><span data-stu-id="ecf81-213">If you would prefer to print the current Dashboard then click the printer icon in the toolbar.</span></span>
  

