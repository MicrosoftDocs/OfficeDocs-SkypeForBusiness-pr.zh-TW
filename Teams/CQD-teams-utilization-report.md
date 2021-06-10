---
title: 使用 CQD Microsoft Teams在 Power BI中查看使用方式
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: 使用 Teams使用方式Power BI報表Microsoft Teams通話品質儀表板 (CQD) ，以追蹤Microsoft Teams使用方式。
ms.openlocfilehash: 719f02ce7a5cd36e96ed7fd563c259c6e77764fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095037"
---
# <a name="view-microsoft-teams-utilization-in-power-bi-using-cqd-data"></a><span data-ttu-id="a06dd-103">使用 CQD Microsoft Teams在 Power BI中查看使用方式</span><span class="sxs-lookup"><span data-stu-id="a06dd-103">View Microsoft Teams utilization in Power BI using CQD data</span></span>

<span data-ttu-id="a06dd-104">新增于 2020 年 3 月，我們已新增 Teams 使用方式報表至可下載的[CQD Power BI查詢範本](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="a06dd-104">New in March 2020, we've added a Teams Utilization report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 

<span data-ttu-id="a06dd-105">這個新Teams使用方式報告可讓您存取 Teams 通話品質儀表板 (CQD) 資料，來瞭解 (以及您的) 使用者使用 Microsoft Teams 量。</span><span class="sxs-lookup"><span data-stu-id="a06dd-105">This new Teams Utilization reports lets you see how (and how much) your users are using Microsoft Teams by accessing Teams Call Quality Dashboard (CQD) data.</span></span> <span data-ttu-id="a06dd-106">這些報告是一個集中式位置，系統管理員和商務領導者都可以快速前往此資料。</span><span class="sxs-lookup"><span data-stu-id="a06dd-106">These reports are intended to be a centralized location that both administrators and business leaders can quickly go to for this data.</span></span>

<span data-ttu-id="a06dd-107">使用Teams報告Power BI兩個主要報告：通話 **[計數摘要](#call-count-summary-report)** 和 **[音訊分鐘摘要](#audio-minutes-summary-report)**。</span><span class="sxs-lookup"><span data-stu-id="a06dd-107">The Teams Utilization Power BI report consists of two primary reports: **[Call Count Summary](#call-count-summary-report)** and **[Audio Minutes Summary](#audio-minutes-summary-report)**.</span></span> <span data-ttu-id="a06dd-108">當使用者[利用](#daily-usage)[下列描述所述](#regional-audio-details)之向下切[](#conference-details)入報表時[](#user-list)，會使用每日使用量、地區音訊詳細資料、會議詳細資料及使用者清單報告。</span><span class="sxs-lookup"><span data-stu-id="a06dd-108">The [Daily Usage](#daily-usage), [Regional Audio Details](#regional-audio-details), [Conference Details](#conference-details) and [User List](#user-list) reports come into play when a user takes advantage of the drill-down reports, noted in the descriptions below.</span></span>

> [!NOTE]
> <span data-ttu-id="a06dd-109">必須填上建築物和子網資料，以提供地區和網路篩選功能。</span><span class="sxs-lookup"><span data-stu-id="a06dd-109">Building and subnet data must be populated to provide regional and network filtering capabilities.</span></span>

## <a name="call-count-summary-report"></a><span data-ttu-id="a06dd-110">通話計數摘要報表</span><span class="sxs-lookup"><span data-stu-id="a06dd-110">Call Count Summary Report</span></span>

<span data-ttu-id="a06dd-111">通話 (摘要) 首頁會如章節標題所述，立即提供過去 30 天和 90 天內的音訊、視視和螢幕共用會話數目。</span><span class="sxs-lookup"><span data-stu-id="a06dd-111">The main page (Call Count Summary) immediately provides the number of audio, video and screen sharing sessions over the last 30 and 90 days as noted in the section title.</span></span> <span data-ttu-id="a06dd-112">最初顯示的資料適用于整個組織，而且可以使用頁面左側的分析篩選器下拉式選項進行篩選。</span><span class="sxs-lookup"><span data-stu-id="a06dd-112">The data initially displayed is for the organization as a whole and can be filtered using the slicer dropdown options on the left side of the page.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report1.png)

1. <span data-ttu-id="a06dd-114">在分析分析片下拉式下拉清單的右側，媒體類型的通話數會細分為過去 30 天內的內部/外部視圖。</span><span class="sxs-lookup"><span data-stu-id="a06dd-114">To the right of the slicer dropdowns, the number of calls by media type is broken down to an internal/external view over the past thirty days.</span></span> <span data-ttu-id="a06dd-115">我們可以透過上述螢幕擷取畫面，看到組織外部位置發生更多通話，考慮到目前的全域環境，這很合理。</span><span class="sxs-lookup"><span data-stu-id="a06dd-115">We can see through the above screenshot that there are more calls happening from outside organizational locations, which makes sense considering the current global environment.</span></span>
  <span data-ttu-id="a06dd-116">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report2.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-116">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report2.png)</span></span>

1. <span data-ttu-id="a06dd-117">在媒體類型計數方塊的右側，我們有過去 90 天的按媒體類型計算每月通話計數。</span><span class="sxs-lookup"><span data-stu-id="a06dd-117">To the right of the media type count box, we have the Monthly Call Count by Media Type for the last 90 days.</span></span> <span data-ttu-id="a06dd-118">每一欄和媒體類型都可以停留在上方，以顯示前一個月或目前月份至今的計數，並提供使用趨勢資訊。</span><span class="sxs-lookup"><span data-stu-id="a06dd-118">Each column and media type can be hovered over to display the count for a previous month or the current month to date, providing usage trend information.</span></span>
  <span data-ttu-id="a06dd-119">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report3.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-119">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report3.png)</span></span>
 

1. <span data-ttu-id="a06dd-120">中間圖形的作用與 90 天圖形一樣，不過它提供過去 30 天的每日使用量視圖，並允許使用者以滑鼠右鍵按一下並向下向下切入特定日期的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a06dd-120">The middle graph functions as the 90-day graph does, however it provides a daily usage view for the past 30 days and allows a user to right click and drill down into details for a specific day.</span></span>
  <span data-ttu-id="a06dd-121">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report4.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-121">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report4.png)</span></span>

<span data-ttu-id="a06dd-122">在頁面左下區段，您可以找到一個表格，提供過去一年每種媒體類型的總計值。</span><span class="sxs-lookup"><span data-stu-id="a06dd-122">On the bottom left section of the page, you'll find a table providing total values for each media type over the past year.</span></span> 
    <span data-ttu-id="a06dd-123">![螢幕擷取畫面：Teams使用方式報告 ](media/CQD-teams-utilization-report5.png) ![ 螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report6.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-123">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report5.png) ![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report6.png)</span></span>   

<span data-ttu-id="a06dd-124">在表格右側，橫條圖會顯示過去 30 天內 (通話/) 流的用戶端。</span><span class="sxs-lookup"><span data-stu-id="a06dd-124">To the right of the table, a bar chart shows clients with the most use (calls/streams) for the past 30 days.</span></span>
   <span data-ttu-id="a06dd-125">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report7.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-125">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report7.png)</span></span>

<span data-ttu-id="a06dd-126">此頁面的最後一組圖表會個別顯示每一種媒體類型，以及顯示會議與 P2P 使用方式的明細。</span><span class="sxs-lookup"><span data-stu-id="a06dd-126">The last set of charts for this page show each media type individually, with a breakdown showing conference and P2P usage.</span></span> <span data-ttu-id="a06dd-127">下列圖表顯示，與 P2P 相比，會議使用量大幅增加。</span><span class="sxs-lookup"><span data-stu-id="a06dd-127">The charts below show that there is a significantly higher number of conference usage as compared to P2P.</span></span>
  <span data-ttu-id="a06dd-128">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report8.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-128">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report8.png)</span></span>

## <a name="audio-minutes-summary-report"></a><span data-ttu-id="a06dd-129">音訊分鐘摘要報告</span><span class="sxs-lookup"><span data-stu-id="a06dd-129">Audio Minutes Summary Report</span></span>

<span data-ttu-id="a06dd-130">在音訊分鐘使用量報告中，總分鐘使用量會透過幾個不同的視圖提供。</span><span class="sxs-lookup"><span data-stu-id="a06dd-130">On the Audio Minutes usage report, the total minute usage is provided through a few different views.</span></span> 

<span data-ttu-id="a06dd-131">我們有三十天的使用量摘要顯示在分析分析器旁邊，因為很容易使用文字方塊。</span><span class="sxs-lookup"><span data-stu-id="a06dd-131">We have the thirty-day usage summary shown next to the slicers as easy to consume text boxes.</span></span> <span data-ttu-id="a06dd-132">頂端數位會顯示三十天總計，其內部和外部明細低於該數位。</span><span class="sxs-lookup"><span data-stu-id="a06dd-132">The top number shows the thirty-day total, with internal and external breakdowns below that.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report9.png)

<span data-ttu-id="a06dd-134">右上方的橫條圖提供會議音訊使用量的一年模式。</span><span class="sxs-lookup"><span data-stu-id="a06dd-134">The top right bar graph provides a yearlong view of conference audio usage.</span></span> <span data-ttu-id="a06dd-135">將游標停留在月份上以顯示會議音訊分鐘數。</span><span class="sxs-lookup"><span data-stu-id="a06dd-135">Hover over the month to show the conference audio minutes.</span></span>

<span data-ttu-id="a06dd-136">若要顯示 P2P 和會議音訊的差異，左下角圖表會採用過去一年的所有音訊，並分為兩種類型。</span><span class="sxs-lookup"><span data-stu-id="a06dd-136">To show the difference in P2P and conference audio, the bottom left chart takes all audio for the past year and breaks it up between the two types.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report10.png)

<span data-ttu-id="a06dd-138">音訊分鐘數頁面的最後一個圖表會顯示全域地圖覆本上的音訊分鐘使用量。</span><span class="sxs-lookup"><span data-stu-id="a06dd-138">The last chart for the Audio minutes page shows audio minute usage on a global map overlay.</span></span> <span data-ttu-id="a06dd-139">只有當建築物和子網資料上傳至租使用者時，此圖表才能使用。</span><span class="sxs-lookup"><span data-stu-id="a06dd-139">This chart will only work if building and subnet data is uploaded to the tenant.</span></span> <span data-ttu-id="a06dd-140">您可以向下切入地圖上的圓形圖覆面，提供地區音訊使用量。</span><span class="sxs-lookup"><span data-stu-id="a06dd-140">The pie chart overlay on the map can be drilled into, subsequently providing regional audio usage.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report11.png)


## <a name="drill-through-capabilities"></a><span data-ttu-id="a06dd-142">深入分析功能</span><span class="sxs-lookup"><span data-stu-id="a06dd-142">Drill-through capabilities</span></span>

<span data-ttu-id="a06dd-143">如先前所指出，使用者可以深入查看每日和區域使用方式報告。</span><span class="sxs-lookup"><span data-stu-id="a06dd-143">As previously noted, users can drill into the daily and regional usage reports.</span></span>

### <a name="daily-usage"></a><span data-ttu-id="a06dd-144">每日使用量</span><span class="sxs-lookup"><span data-stu-id="a06dd-144">Daily Usage</span></span>

<span data-ttu-id="a06dd-145">每日使用量報告可讓系統管理員識別一天中的尖峰消費期間。</span><span class="sxs-lookup"><span data-stu-id="a06dd-145">The Daily Usage report allows an administrator to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="a06dd-146">除了使用方式之外，我們也能夠收集當天的整體使用者情緒和意見。</span><span class="sxs-lookup"><span data-stu-id="a06dd-146">In addition to usage, we are also able to capture overall user sentiment and feedback for that day.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report12.png)

<span data-ttu-id="a06dd-148">每日使用量報告會顯示所選日的音訊、視音訊和螢幕畫面共用數量，並新增了區分內部和外部連接的能力。</span><span class="sxs-lookup"><span data-stu-id="a06dd-148">The Daily usage report displays the number of Audio, Video and Screen shares for the selected day with the added ability to differentiate between internal and external connectivity.</span></span> <span data-ttu-id="a06dd-149">會議與對等分解位於模式總計方塊的右方。</span><span class="sxs-lookup"><span data-stu-id="a06dd-149">A Conference and Peer to Peer breakdown is to the immediate right of the modality total box.</span></span> <span data-ttu-id="a06dd-150">報表的右上方會提供一份會議清單，包含其相關聯的 ID 和當天的參與者。</span><span class="sxs-lookup"><span data-stu-id="a06dd-150">The top right of the report provides a list of conferences with their associated ID and participants for the day.</span></span> <span data-ttu-id="a06dd-151">會議清單也提供另一個向下切入至會議詳細資料包表。</span><span class="sxs-lookup"><span data-stu-id="a06dd-151">The conference list provides an additional drill down to the Conference Details report as well.</span></span> <span data-ttu-id="a06dd-152">取代圖形</span><span class="sxs-lookup"><span data-stu-id="a06dd-152">REPLACE GRAPHIC</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report13.png)

<span data-ttu-id="a06dd-154">中央區域中的橫條圖可讓使用者識別一天中的尖峰消費期間。</span><span class="sxs-lookup"><span data-stu-id="a06dd-154">The bar graph in the center area allows the user to identify peak consumption periods through the course of a day.</span></span> <span data-ttu-id="a06dd-155">使用者可以向下向下切入圖形上代表的小時，該小時會呈現使用者清單報表。</span><span class="sxs-lookup"><span data-stu-id="a06dd-155">Users may drill down into the hour represented on the graph which will present the User List report for the hour.</span></span>

<span data-ttu-id="a06dd-156">在橫條圖右側，使用者意見回饋會以視覺格式呈現。</span><span class="sxs-lookup"><span data-stu-id="a06dd-156">To the right of the bar graph, User Feedback is presented in a visual format.</span></span> <span data-ttu-id="a06dd-157">雖然使用者情緒可能有些不一樣，但它提供深入見解，可用來識別潛在問題。</span><span class="sxs-lookup"><span data-stu-id="a06dd-157">While user sentiment can be subjective, it does provide insight that can be used to identify potential issues.</span></span>

<span data-ttu-id="a06dd-158">底端表格提供一天的度量範圍。</span><span class="sxs-lookup"><span data-stu-id="a06dd-158">The bottom table provides a range of metrics for the day.</span></span> <span data-ttu-id="a06dd-159">不佳的百分比與失敗率可以為系統管理員提供潛在的改進領域。</span><span class="sxs-lookup"><span data-stu-id="a06dd-159">Poor percentages along with failure rates can provide an administrator with potential areas of improvement.</span></span> <span data-ttu-id="a06dd-160">每小時也可以個別選取，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a06dd-160">Each hour can also be selected individually as shown below.</span></span>

<span data-ttu-id="a06dd-161">此資料可用來識別在尖峰消費期間發生問題的區域。</span><span class="sxs-lookup"><span data-stu-id="a06dd-161">This data can be used to identify regions having problems during peak consumption times.</span></span>


<span data-ttu-id="a06dd-162">按一下該天的欄以顯示該小時的度量。</span><span class="sxs-lookup"><span data-stu-id="a06dd-162">Click on the column for that day to display metrics for that hour.</span></span>
<span data-ttu-id="a06dd-163">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report14.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-163">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report14.png)</span></span>
  
  1.  <span data-ttu-id="a06dd-164">圖表下方的表格會顯示該小時的度量單位。</span><span class="sxs-lookup"><span data-stu-id="a06dd-164">The table below the chart will display the metrics for that hour.</span></span> <span data-ttu-id="a06dd-165">這可排序任何欄標題;不過，我們有興趣尋找有問題的區域。</span><span class="sxs-lookup"><span data-stu-id="a06dd-165">This can be sorted by any column header; however, we would be interested in finding problematic areas.</span></span>  
    ![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report15.png)
    
  2.  <span data-ttu-id="a06dd-167">我們看到 IND 區域在這段期間，在會議中遇到不佳的視像效果。</span><span class="sxs-lookup"><span data-stu-id="a06dd-167">We see that the IND region is experiencing poor video performance in conferences during this time frame.</span></span> <span data-ttu-id="a06dd-168">接著，當已識別地區與時間範圍時，CQD QER Microsoft 報告可用來縮小有問題的位置。</span><span class="sxs-lookup"><span data-stu-id="a06dd-168">Subsequently, the CQD QER Microsoft reports can be used to narrow down the problematic location as the region and time frame has been identified.</span></span>

### <a name="conference-details"></a><span data-ttu-id="a06dd-169">會議詳細資料</span><span class="sxs-lookup"><span data-stu-id="a06dd-169">Conference Details</span></span>

<span data-ttu-id="a06dd-170">會議詳細資料包告提供會議的其他深入資訊，從出席者清單到會話期間使用的媒體類型。</span><span class="sxs-lookup"><span data-stu-id="a06dd-170">The Conference Details report provides additional insight for meetings, from an attendee list, to the media types used during the session.</span></span>

<span data-ttu-id="a06dd-171">以滑鼠右鍵按一下 [每日使用狀況」 頁面上會議 ID 圖表中的參與者欄，以向下向下切入會議詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a06dd-171">Right click a conference the participant bar in the conference ID chart on the Daily usage page to drill down into the conference details.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report24.png)

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report25.png)
  

<span data-ttu-id="a06dd-174">我們可以查看會議參與者，以及所有相關資訊，包括封包遺失和抖動，以協助下表中的潛在疑難排解工作。</span><span class="sxs-lookup"><span data-stu-id="a06dd-174">We can see the participants in the conference as well as all the pertinent information down to packet loss and jitter to assist with potential troubleshooting efforts in the bottom table.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report26.png)


### <a name="regional-audio-details"></a><span data-ttu-id="a06dd-176">地區音訊詳細資料</span><span class="sxs-lookup"><span data-stu-id="a06dd-176">Regional Audio Details</span></span>

<span data-ttu-id="a06dd-177">地區音訊詳細資料向下向下縮小，專門顯示所選區域的音訊分鐘使用量。</span><span class="sxs-lookup"><span data-stu-id="a06dd-177">The Regional Audio Details drill down specifically shows the audio minute usage for the selected region.</span></span> <span data-ttu-id="a06dd-178">具有 CQD 存取權的使用者可以看到所選地區內 P2P 和會議音訊的使用趨勢。</span><span class="sxs-lookup"><span data-stu-id="a06dd-178">Users with access to CQD can see usage trends for both P2P and conference audio within the selected region.</span></span>

1.  <span data-ttu-id="a06dd-179">在呼叫計數摘要頁面上，在表格中以特定區域方式向下切入。</span><span class="sxs-lookup"><span data-stu-id="a06dd-179">On the Call Count Summary page, drill-through to as specific region through the table.</span></span>
  <span data-ttu-id="a06dd-180">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report16.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-180">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report16.png)</span></span>

2.  <span data-ttu-id="a06dd-181">選取包含區域的其他資訊列。</span><span class="sxs-lookup"><span data-stu-id="a06dd-181">Select the row with the region additional information is needed for.</span></span>
  <span data-ttu-id="a06dd-182">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report17.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-182">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report17.png)</span></span>

3.  <span data-ttu-id="a06dd-183">資料趨勢顯示內部網路上使用大量分鐘數，而會議遠超過 P2P 使用。</span><span class="sxs-lookup"><span data-stu-id="a06dd-183">The data trends show a significant number of minutes being used on the internal network, with conferencing far surpassing P2P use.</span></span>
  <span data-ttu-id="a06dd-184">![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report18.png)</span><span class="sxs-lookup"><span data-stu-id="a06dd-184">![Screenshot: Teams Utilization Reports](media/CQD-teams-utilization-report18.png)</span></span>

<span data-ttu-id="a06dd-185">地區音訊趨勢可用來顯示使用者受到外部影響的影響。</span><span class="sxs-lookup"><span data-stu-id="a06dd-185">The regional audio trend can be used to show how users are impacted by external influences in the world.</span></span> <span data-ttu-id="a06dd-186">具體來說，目前我們預期 EMEA 和 APAC 地區的外部使用量會增加，因為有人要求遠端工作。</span><span class="sxs-lookup"><span data-stu-id="a06dd-186">Specifically, right now, we would expect to see the external usage for the EMEA and APAC regions to increase with people being asked to work remotely.</span></span>


### <a name="user-list"></a><span data-ttu-id="a06dd-187">使用者清單</span><span class="sxs-lookup"><span data-stu-id="a06dd-187">User List</span></span>

<span data-ttu-id="a06dd-188">使用者清單向下切入會如預期提供檢視報表之人員所選取之特定時間的使用者特定資訊。</span><span class="sxs-lookup"><span data-stu-id="a06dd-188">The User List drill down provides, as one might expect, user specific information for a specific hour selected by the person viewing the report.</span></span> <span data-ttu-id="a06dd-189">使用者清單報表可在每日使用量報表的每小時趨勢圖形中向下向下切入來訪問。</span><span class="sxs-lookup"><span data-stu-id="a06dd-189">The User List report is accessible through a drill down in the Hourly Trends graph on the Daily Usage report.</span></span> <span data-ttu-id="a06dd-190">以滑鼠右鍵按一下需要額外資訊的時間，然後選取 [鑽取及使用者清單>，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a06dd-190">Right click on the hour additional information is needed for and select Drill through and User List, as shown below.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report19.png)

<span data-ttu-id="a06dd-192">使用者清單報表會透過頁面頂端中心的環圈圖顯示內部/外部連接。</span><span class="sxs-lookup"><span data-stu-id="a06dd-192">The User List report shows internal/external connectivity through the doughnut chart in the top center of the page.</span></span> <span data-ttu-id="a06dd-193">如下圖所示，在公司網路外部有大量參與。</span><span class="sxs-lookup"><span data-stu-id="a06dd-193">We can see that there is a large amount of participation from Outside the corporate network in the below image.</span></span>

<span data-ttu-id="a06dd-194">圖形的右上方顯示每個使用者在一小時內的通話次數。</span><span class="sxs-lookup"><span data-stu-id="a06dd-194">The top right of the graph shows the number of calls made by each user within that hour.</span></span>

![螢幕擷取畫面：Teams使用方式報告](media/CQD-teams-utilization-report20.png)

<span data-ttu-id="a06dd-196">底部表格提供每個使用者在這一小時參與會話的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="a06dd-196">The bottom table provides detailed information for the sessions each user participated in during that hour.</span></span> <span data-ttu-id="a06dd-197">在判斷導致通話下拉的原因時，失敗類型欄很有用。</span><span class="sxs-lookup"><span data-stu-id="a06dd-197">The Failure Type column is useful in determining what caused a call to drop.</span></span> <span data-ttu-id="a06dd-198">在識別通話品質不佳的原因時，捕獲和呈現裝置欄非常實用。</span><span class="sxs-lookup"><span data-stu-id="a06dd-198">The Capture and Render Device columns are useful in identifying why a call was reported having poor quality.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a06dd-199">相關主題</span><span class="sxs-lookup"><span data-stu-id="a06dd-199">Related topics</span></span>

[<span data-ttu-id="a06dd-200">通話品質儀表板中提供的維度和量值</span><span class="sxs-lookup"><span data-stu-id="a06dd-200">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a06dd-201">通話品質儀表板中的資料流分類</span><span class="sxs-lookup"><span data-stu-id="a06dd-201">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a06dd-202">設定商務用 Skype 通話分析</span><span class="sxs-lookup"><span data-stu-id="a06dd-202">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="a06dd-203">使用通話分析來疑難排解不良通話品質</span><span class="sxs-lookup"><span data-stu-id="a06dd-203">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="a06dd-204">通話分析和通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="a06dd-204">Call Analytics and Call Quality Dashboard</span></span>](./monitor-call-quality-qos.md)

[<span data-ttu-id="a06dd-205">Teams 疑難排解</span><span class="sxs-lookup"><span data-stu-id="a06dd-205">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
