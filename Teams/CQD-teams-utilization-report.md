---
title: 在 Power BI 中使用 CQD 資料來查看 Microsoft 團隊利用率
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 [小組利用率 Power BI 報表] 來追蹤貴組織中的 Microsoft 團隊使用方式。
ms.openlocfilehash: d22f37bb230ecbaa3cf6c33c2ba43f5ea92afaad
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559419"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="34d6b-103">在 Power BI 中使用 CQD 資料來查看 Microsoft 團隊利用率</span><span class="sxs-lookup"><span data-stu-id="34d6b-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="34d6b-104">我們新增了2020年3月的新功能，我們已將 [團隊利用率] 報告新增至可下載[的 POWER BI 查詢範本以供 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)使用。</span><span class="sxs-lookup"><span data-stu-id="34d6b-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="34d6b-105">這個新的團隊利用率報告可讓您查看使用者使用 Microsoft 團隊的方式（以及多少）。</span><span class="sxs-lookup"><span data-stu-id="34d6b-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams.</span></span> <span data-ttu-id="34d6b-106">這些報告是要成為集中位置，管理員與企業領導人都可以快速移至此資料。</span><span class="sxs-lookup"><span data-stu-id="34d6b-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="34d6b-107">[團隊利用率 Power BI] 報表包含兩個主要的報表： [**[通話計數摘要](#call-count-summary-report)**] 和 [**[音訊分鐘摘要](#audio-minutes-summary-report)**]。</span><span class="sxs-lookup"><span data-stu-id="34d6b-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="34d6b-108">當使用者利用 [深化] 報告時，[每日使用量](#daily-usage)和[地區音訊詳細資料](#regional-audio-details)報告就會發揮作用，請見下列說明。</span><span class="sxs-lookup"><span data-stu-id="34d6b-108">The [Daily Usage](#daily-usage) and [Regional Audio Details](#regional-audio-details) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="34d6b-109">必須填入建立和子網資料，才能提供區域和網路篩選功能。</span><span class="sxs-lookup"><span data-stu-id="34d6b-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="34d6b-110">[通話計數摘要] 報告</span><span class="sxs-lookup"><span data-stu-id="34d6b-110">Call Count Summary Report</span></span>

<span data-ttu-id="34d6b-111">主頁面（[通話計數摘要]）會立即提供最近30和90天的音訊、影片和螢幕共用會話數目，如章節標題中所述。</span><span class="sxs-lookup"><span data-stu-id="34d6b-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="34d6b-112">最初顯示的資料是針對組織而言，您可以使用頁面左側的 [交叉分析篩選器] 下拉式清單選項加以篩選。</span><span class="sxs-lookup"><span data-stu-id="34d6b-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="34d6b-114">在交叉分析篩選器下拉式清單的右側，依媒體類型進行的呼叫數量會在過去30天內細分為內部/外部視圖。</span><span class="sxs-lookup"><span data-stu-id="34d6b-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="34d6b-115">我們可以透過上述螢幕擷取畫面來查看更多來自外部組織位置的呼叫，從而讓您考慮目前的全域環境。</span><span class="sxs-lookup"><span data-stu-id="34d6b-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="34d6b-116">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-116">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="34d6b-117">在 [媒體類型計數] 方塊的右邊，我們有 [每月通話計數依據媒體類型]，最後90天。</span><span class="sxs-lookup"><span data-stu-id="34d6b-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="34d6b-118">每個資料行和媒體類型都可以進行懸停，以顯示前一月或目前月份的計數，以提供使用趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="34d6b-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="34d6b-119">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-119">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report3.png)</span></span>

1. <span data-ttu-id="34d6b-120">中間圖形的運作方式就是90天的圖表，但它提供過去30天的每日使用狀況視圖，並允許使用者以滑鼠右鍵按一下，並向下切入特定日期的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="34d6b-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="34d6b-121">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-121">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="34d6b-122">在頁面左下方，您會發現一個表格，提供過去一年每個媒體類型的總計值。</span><span class="sxs-lookup"><span data-stu-id="34d6b-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="34d6b-123">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report5.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-123">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report5.png)</span></span>
  
<span data-ttu-id="34d6b-124">該表也有可用的向下切入，您可以在這裡查看地區資料細目。</span><span class="sxs-lookup"><span data-stu-id="34d6b-124">The table also has an available drill down where you can see a regional data breakdown.</span></span>
    <span data-ttu-id="34d6b-125">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-125">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report6.png)</span></span>

<span data-ttu-id="34d6b-126">在表格右側，橫條圖會顯示過去30天內最常使用（通話/串流）的用戶端。</span><span class="sxs-lookup"><span data-stu-id="34d6b-126">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="34d6b-127">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-127">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report7.png)</span></span>


<span data-ttu-id="34d6b-128">此頁面的最後一組圖表會分別顯示每個媒體類型，以及顯示會議與 P2P 使用方式的細目分類。</span><span class="sxs-lookup"><span data-stu-id="34d6b-128">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="34d6b-129">下表顯示與 P2P 相比，有明顯較高的會議使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-129">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="34d6b-130">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-130">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="34d6b-131">音訊分鐘摘要報告</span><span class="sxs-lookup"><span data-stu-id="34d6b-131">Audio Minutes Summary Report</span></span>

<span data-ttu-id="34d6b-132">在 [音訊分鐘使用方式] 報告中，會透過幾種不同的視圖提供總分鐘使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-132">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="34d6b-133">我們會在交叉分析篩選器旁顯示三十天的使用方式摘要，輕鬆地使用文字方塊。</span><span class="sxs-lookup"><span data-stu-id="34d6b-133">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="34d6b-134">[最大值] 會顯示三十天的總計，並在其下方加上內部和外部細目。</span><span class="sxs-lookup"><span data-stu-id="34d6b-134">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="34d6b-136">右上方橫條圖提供會議音訊使用量的 yearlong。</span><span class="sxs-lookup"><span data-stu-id="34d6b-136">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="34d6b-137">將游標暫留在月份上以顯示會議音訊分鐘數。</span><span class="sxs-lookup"><span data-stu-id="34d6b-137">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="34d6b-138">若要在 P2P 與會議音訊中顯示差異，左下角圖表會取得過去一年的所有音訊，並在這兩種類型之間分割。</span><span class="sxs-lookup"><span data-stu-id="34d6b-138">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

<span data-ttu-id="34d6b-139">![螢幕擷取畫面：通話縣摘要](media/CQD-teams-utilization-report10.png)報告 [音訊分鐘數] 頁面的最後一個圖表顯示全域地圖覆蓋上的音訊分鐘使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-139">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report10.png) The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="34d6b-140">只有在建立和子網資料上傳到租使用者時，才能使用此圖表。</span><span class="sxs-lookup"><span data-stu-id="34d6b-140">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="34d6b-141">在地圖上重迭的圓形圖可以深化到其中，進而提供區域音訊使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-141">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report11.png)

## <a name="drill-through-capabilities"></a><span data-ttu-id="34d6b-143">鑽取功能</span><span class="sxs-lookup"><span data-stu-id="34d6b-143">Drill-through capabilities</span></span>

<span data-ttu-id="34d6b-144">如先前所述，使用者可以深入探索每日和地區使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="34d6b-144">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="34d6b-145">每日使用量</span><span class="sxs-lookup"><span data-stu-id="34d6b-145">Daily Usage</span></span>

<span data-ttu-id="34d6b-146">每日使用方式報告可讓系統管理員透過一天的時間來識別高峰期消耗量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-146">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="34d6b-147">除了用法之外，我們還能捕獲該日的整體使用者觀點和意見反應。</span><span class="sxs-lookup"><span data-stu-id="34d6b-147">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="34d6b-149">這個資料可用來找出在高峰期內遇到問題的區域。</span><span class="sxs-lookup"><span data-stu-id="34d6b-149">This data can be used to identify regions having problems during peak consumption times.</span></span>

1.  <span data-ttu-id="34d6b-150">在 [通話計數摘要] 頁面上，在特定日期進行鑽取。</span><span class="sxs-lookup"><span data-stu-id="34d6b-150">On the Call Count Summary page, drill-through on a specific date.</span></span> <span data-ttu-id="34d6b-151">查看當天的每小時趨勢，找出峰值使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-151">Look at the hourly trend that day to find the peak utilization.</span></span>
  <span data-ttu-id="34d6b-152">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report13.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-152">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report13.png)</span></span>

2.  <span data-ttu-id="34d6b-153">按一下該日期的欄，即可顯示該小時的度量單位。</span><span class="sxs-lookup"><span data-stu-id="34d6b-153">Click on the column for that day to display metrics for that hour.</span></span>
  <span data-ttu-id="34d6b-154">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-154">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report14.png)</span></span>
    
    1.  <span data-ttu-id="34d6b-155">圖表下方的表格會顯示該小時的度量單位。</span><span class="sxs-lookup"><span data-stu-id="34d6b-155">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="34d6b-156">這可以依據任何欄標題來排序;不過，我們很樂意找出有問題的區域。</span><span class="sxs-lookup"><span data-stu-id="34d6b-156">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
        ![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report15.png)
    
    2.  <span data-ttu-id="34d6b-158">我們在此期間看到 IND 區域在會議中遇到較差的視頻效能。</span><span class="sxs-lookup"><span data-stu-id="34d6b-158">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="34d6b-159">接著，您可以使用 CQD QER Microsoft 報表來縮小有問題的位置，因為已識別出區域和時間範圍。</span><span class="sxs-lookup"><span data-stu-id="34d6b-159">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="regional-audio-details"></a><span data-ttu-id="34d6b-160">地區音訊詳細資料</span><span class="sxs-lookup"><span data-stu-id="34d6b-160">Regional Audio Details</span></span>

<span data-ttu-id="34d6b-161">[地區音訊詳細資料] 向下切入特別顯示所選區域的音訊分鐘使用量。</span><span class="sxs-lookup"><span data-stu-id="34d6b-161">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="34d6b-162">擁有 CQD 存取權的使用者可以查看所選區域內 P2P 與會議音訊的使用方式趨勢。</span><span class="sxs-lookup"><span data-stu-id="34d6b-162">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="34d6b-163">在 [通話計數摘要] 頁面上，透過資料表以特定區域為依據。</span><span class="sxs-lookup"><span data-stu-id="34d6b-163">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="34d6b-164">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-164">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="34d6b-165">選取需要其他區域資訊的那一列。</span><span class="sxs-lookup"><span data-stu-id="34d6b-165">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="34d6b-166">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-166">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="34d6b-167">資料趨勢會顯示在內部網路上所使用的大量分鐘數，以及會議最超越 P2P 的使用方式。</span><span class="sxs-lookup"><span data-stu-id="34d6b-167">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="34d6b-168">![螢幕擷取畫面：撥打縣摘要報告](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="34d6b-168">![Screenshot: Call County Summary Report](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="34d6b-169">地區音訊趨勢可以用來顯示使用者如何受到世界各地的影響。</span><span class="sxs-lookup"><span data-stu-id="34d6b-169">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="34d6b-170">具體來說，我們會預期您會看到 EMEA 與 APAC 區域的外部使用方式，讓人員能在遠端作業時增加。</span><span class="sxs-lookup"><span data-stu-id="34d6b-170">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>



## <a name="related-topics"></a><span data-ttu-id="34d6b-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="34d6b-171">Related topics</span></span>

[<span data-ttu-id="34d6b-172">通話品質儀表板中提供的維度和量值</span><span class="sxs-lookup"><span data-stu-id="34d6b-172">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="34d6b-173">通話品質儀表板中的資料流分類</span><span class="sxs-lookup"><span data-stu-id="34d6b-173">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="34d6b-174">設定商務用 Skype 通話分析</span><span class="sxs-lookup"><span data-stu-id="34d6b-174">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="34d6b-175">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="34d6b-175">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="34d6b-176">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="34d6b-176">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)
 