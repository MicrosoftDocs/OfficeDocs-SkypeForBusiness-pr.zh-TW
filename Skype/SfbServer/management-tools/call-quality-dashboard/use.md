---
title: 使用商務用 Skype Server 的通話品質儀表板
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: '摘要: 瞭解如何使用通話品質儀表板。 [通話品質儀表板] 是商務用 Skype Server 的工具。'
ms.openlocfilehash: b89f766cfcbfbc9fe2c700162f3c0b4e69a7e6bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186859"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="a7d19-104">使用商務用 Skype Server 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="a7d19-104">Use Call Quality Dashboard for Skype for Business Server</span></span>
 
<span data-ttu-id="a7d19-105">**摘要:** 瞭解如何使用通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="a7d19-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="a7d19-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="a7d19-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a7d19-107">CQD 可讓 IT 專業人員使用匯總資料來找出遇到媒體質量問題之環境中的焦點區域。</span><span class="sxs-lookup"><span data-stu-id="a7d19-107">CQD allows IT Pros to use aggregate data to identify focus areas in their environment experiencing media quality issues.</span></span> <span data-ttu-id="a7d19-108">它可讓 IT 專業人員比較不同使用者群組的統計資料, 並識別趨勢和模式。</span><span class="sxs-lookup"><span data-stu-id="a7d19-108">It allows an IT Pro to compare statistics for different groups of users and identify trends and patterns.</span></span> <span data-ttu-id="a7d19-109">它不是針對個別呼叫問題的重點, 而是針對在指定環境中針對許多使用者所套用的問題與解決方案。</span><span class="sxs-lookup"><span data-stu-id="a7d19-109">It is not focused on solving individual call issues, but on identifying problems and solutions that will apply to many users in a given environment.</span></span>
  
## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="a7d19-110">通話品質儀表板使用者指南</span><span class="sxs-lookup"><span data-stu-id="a7d19-110">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="a7d19-111">通話品質儀表板 (CQD) 是一種網頁入口網站, 可根據體驗品質 (QoE) 資料快速建立及組織報表。</span><span class="sxs-lookup"><span data-stu-id="a7d19-111">The Call Quality Dashboard (CQD) is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="a7d19-112">CQD [部署 SSAS] 立方體來匯總 QoE 度量資料庫中的資料。</span><span class="sxs-lookup"><span data-stu-id="a7d19-112">CQD deploys a SSAS cube to aggregate the data in the QoE Metrics database.</span></span> <span data-ttu-id="a7d19-113">這可讓使用者建立及修改報告, 並即時進行調查。</span><span class="sxs-lookup"><span data-stu-id="a7d19-113">This enables users to create and modify reports and do investigations in real-time.</span></span> <span data-ttu-id="a7d19-114">雖然您可以使用 Excel 直接連線至立方體, 但入口網站已針對多個涉及 QoE 資料的工作流程進行優化。</span><span class="sxs-lookup"><span data-stu-id="a7d19-114">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="a7d19-115">此資料包括快取快速存取的報表資料、深入的連結, 以取得資訊共用及發佈的報告頁面、簡化的報表編輯及建立, 以及報表描述的可編輯中繼資料。</span><span class="sxs-lookup"><span data-stu-id="a7d19-115">This data includes caching of report data for fast access, deep links to report pages for information sharing and publishing, streamlined report editing and creation, and editable metadata for report descriptions.</span></span> <span data-ttu-id="a7d19-116">此外, CQD 會公開 web Api, 讓使用者以程式設計方式存取要在自訂儀表板中使用的多維資料集資料。</span><span class="sxs-lookup"><span data-stu-id="a7d19-116">Additionally, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span> 
  
### <a name="feature-overview"></a><span data-ttu-id="a7d19-117">功能概述</span><span class="sxs-lookup"><span data-stu-id="a7d19-117">Feature Overview</span></span>

<span data-ttu-id="a7d19-118">當使用者造訪通話品質儀表板時, 這就是 s/他將會看到的內容:</span><span class="sxs-lookup"><span data-stu-id="a7d19-118">When a user visits the Call Quality Dashboard, this is what s/he will see:</span></span>
  
![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)
  
1. <span data-ttu-id="a7d19-120">您可以在 [摘要窗格] 中找到 [報表集] (右側) 的內容。</span><span class="sxs-lookup"><span data-stu-id="a7d19-120">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span> 
    
2. <span data-ttu-id="a7d19-121">您可以在 [摘要窗格] 中按一下 [編輯], 以設定報表設定層級屬性 (包括 Y 軸高度)。</span><span class="sxs-lookup"><span data-stu-id="a7d19-121">Report Set level properties (including Y-axis height) can be set by clicking on "Edit" in the Summary Pane.</span></span>
    
3. <span data-ttu-id="a7d19-122">軌跡瀏覽可協助使用者識別其在報表集階層中的目前位置。</span><span class="sxs-lookup"><span data-stu-id="a7d19-122">The Breadcrumb helps users identify their current location within the report set hierarchy.</span></span> 
    
4. <span data-ttu-id="a7d19-123">含有子報表的報表會以藍色連結顯示。</span><span class="sxs-lookup"><span data-stu-id="a7d19-123">Reports with sub-reports are shown with a blue link.</span></span> <span data-ttu-id="a7d19-124">按一下連結將會向下切入至子報表。</span><span class="sxs-lookup"><span data-stu-id="a7d19-124">Clicking on the link will drill down to the child reports.</span></span> 
    
<span data-ttu-id="a7d19-125">將滑鼠移至橫條圖和趨勢線上方, 就會顯示詳細的值。</span><span class="sxs-lookup"><span data-stu-id="a7d19-125">Moving the mouse over the bar charts and trend lines will show detailed values.</span></span> <span data-ttu-id="a7d19-126">具有焦點的報表會顯示動作功能表: 「編輯」、「克隆」、「刪除」和「下載」。</span><span class="sxs-lookup"><span data-stu-id="a7d19-126">The report that has focus will show the action menu: "Edit", "Clone", "Delete", and "Download".</span></span> 
  
### <a name="default-reports"></a><span data-ttu-id="a7d19-127">預設報表</span><span class="sxs-lookup"><span data-stu-id="a7d19-127">Default Reports</span></span>

<span data-ttu-id="a7d19-128">當使用者第一次存取通話品質儀表板入口網站時, 系統會自動建立一組預設的報告。</span><span class="sxs-lookup"><span data-stu-id="a7d19-128">When a user first accesses the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="a7d19-129">這些報告有時稱為「系統報告」。</span><span class="sxs-lookup"><span data-stu-id="a7d19-129">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="a7d19-130">使用者可以自由地修改或刪除這些報表。</span><span class="sxs-lookup"><span data-stu-id="a7d19-130">The user is able to freely modify or delete these reports.</span></span> <span data-ttu-id="a7d19-131">使用者通常會建立新的同輩與子報表來延伸。</span><span class="sxs-lookup"><span data-stu-id="a7d19-131">Generally, users will extend them by creating new sibling and child reports.</span></span> 
  
<span data-ttu-id="a7d19-132">在最上層, 「音訊串流月趨勢」報告會顯示所有音訊資料流程的每月趨勢。</span><span class="sxs-lookup"><span data-stu-id="a7d19-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="a7d19-133">將滑鼠移至橫條圖中的條形上方, 就會顯示橫條圖所代表資料的更詳細的視圖。</span><span class="sxs-lookup"><span data-stu-id="a7d19-133">Moving the mouse over the bars in a bar chart will show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="a7d19-134">按一下 [音訊流量] 的 [每月趨勢報告] 標題, 將會流覽到 [Managed vs 非託管音訊資料流程] 報告, 其中的報告在託管與未受管理的呼叫之間分割。</span><span class="sxs-lookup"><span data-stu-id="a7d19-134">Clicking on the title of the Audio Streams Monthly Trend report will navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="a7d19-135">Managed 通話是透過有線連線在企業防火牆內進行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="a7d19-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="a7d19-136">非託管通話包括來自公司防火牆以外的呼叫, 以及透過 Wi-fi 進行的所有通話。</span><span class="sxs-lookup"><span data-stu-id="a7d19-136">Unmanaged calls include calls made from outside the corporate firewall as well as all calls made over Wi-Fi.</span></span>
  
<span data-ttu-id="a7d19-137">其他最上層的報表稱為「使用者報告的通話品質評等長條圖」。</span><span class="sxs-lookup"><span data-stu-id="a7d19-137">The other top level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="a7d19-138">通話品質評等是通話結束時, 商務用 Skype 使用者所提供的數位, 代表通話的品質。</span><span class="sxs-lookup"><span data-stu-id="a7d19-138">The Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="a7d19-139">評分編號的範圍從1到 5, 1 為最差, 5 是最佳的。</span><span class="sxs-lookup"><span data-stu-id="a7d19-139">The rating numbers range from 1 to 5, with 1 being the worst and 5 being the best.</span></span> <span data-ttu-id="a7d19-140">[長條圖] 會顯示在一個月中指定評等的音訊通話數量。</span><span class="sxs-lookup"><span data-stu-id="a7d19-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span> 
  
<span data-ttu-id="a7d19-141">一般來說, 按一下任何報告的標題, 都將會以其他篩選資料的方式流覽至報表。</span><span class="sxs-lookup"><span data-stu-id="a7d19-141">In general, clicking on the title of any of the reports will navigate into reports with additional filters on the data.</span></span> <span data-ttu-id="a7d19-142">在系統報告中, 每個子報表都會顯示其父報表中可用的資料子集。</span><span class="sxs-lookup"><span data-stu-id="a7d19-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="a7d19-143">這會提供一種從概念上簡單的模型來解決問題: 透過調查問題資料或趨勢所限制的子報表, 縮小問題空間的範圍。</span><span class="sxs-lookup"><span data-stu-id="a7d19-143">This provides a conceptually simple model for problem solving: narrow down the problem space by investigating which sub-report the problematic data or trend is confined to.</span></span> <span data-ttu-id="a7d19-144">建立新子報表的功能可讓使用者調查自己的 hypotheses, 以 provenance 特定資料的趨勢。</span><span class="sxs-lookup"><span data-stu-id="a7d19-144">The ability to create new sub-reports allows users to investigate their own hypotheses as to the provenance of specific data trends.</span></span>
  
### <a name="creating-and-editing-reports"></a><span data-ttu-id="a7d19-145">建立及編輯報表</span><span class="sxs-lookup"><span data-stu-id="a7d19-145">Creating and Editing Reports</span></span>

<span data-ttu-id="a7d19-146">按一下報表的 [動作] 功能表中的 [編輯] 時, 使用者就會看到 [報表編輯器]。</span><span class="sxs-lookup"><span data-stu-id="a7d19-146">When clicking on "Edit" in the action menu of a report, users will see the Report Editor.</span></span> <span data-ttu-id="a7d19-147">每個報告都會以查詢的方式支援到立方體中。</span><span class="sxs-lookup"><span data-stu-id="a7d19-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="a7d19-148">報表是其查詢所傳回資料的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="a7d19-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="a7d19-149">[報告編輯器] 是編輯這些查詢的使用者介面, 以及報表的顯示選項。</span><span class="sxs-lookup"><span data-stu-id="a7d19-149">The Report Editor is a user interface for editing these queries, as well as the display options of the report.</span></span> <span data-ttu-id="a7d19-150">當使用者開啟 [報表編輯器] 時, 這就是 s/他將會看到的內容:</span><span class="sxs-lookup"><span data-stu-id="a7d19-150">When a user opens the Report Editor, this is what s/he will see:</span></span>
  
![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)
  
1. <span data-ttu-id="a7d19-152">在左窗格中選取 [維度]、[量值] 和 [篩選]。</span><span class="sxs-lookup"><span data-stu-id="a7d19-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="a7d19-153">將游標停留在其中一個現有的值上, 將會顯示一個 [x] 按鈕, 讓您可以移除值。</span><span class="sxs-lookup"><span data-stu-id="a7d19-153">Hovering over one of the existing values will show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="a7d19-154">按一下標題旁邊的 [加號] 按鈕, 就會開啟新增維度、量值或篩選的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="a7d19-154">Clicking on the "plus" button next to a heading will open the dialog for adding a new dimension, measure or filter.</span></span> 
    
2. <span data-ttu-id="a7d19-155">圖表自訂的選項會顯示在頂端。</span><span class="sxs-lookup"><span data-stu-id="a7d19-155">Options for chart customization are displayed at the top.</span></span>
    
3. <span data-ttu-id="a7d19-156">報表的預覽可在 [報表編輯器] 中取得。</span><span class="sxs-lookup"><span data-stu-id="a7d19-156">A preview of the report is available in the Report Editor.</span></span> 
    
4. <span data-ttu-id="a7d19-157">您可以使用底部的編輯方塊來建立詳細的報表描述。</span><span class="sxs-lookup"><span data-stu-id="a7d19-157">A detailed report description can be created using the edit box at the bottom.</span></span> 
    
### <a name="sparklines-in-tables"></a><span data-ttu-id="a7d19-158">表格中的走勢圖</span><span class="sxs-lookup"><span data-stu-id="a7d19-158">Sparklines in Tables</span></span>

<span data-ttu-id="a7d19-159">開始時, 月份會新增為維度, 而且資料會以表格表單中的趨勢轉譯, 橫條圖和走勢圖會顯示在表格儲存格內。</span><span class="sxs-lookup"><span data-stu-id="a7d19-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="a7d19-160">將滑鼠指標移至橫條圖上方, 走勢圖就會顯示個別月份的值。</span><span class="sxs-lookup"><span data-stu-id="a7d19-160">Moving the mouse pointer over the bar chart and the sparklines will show values for individual months.</span></span> 
  
![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)
  
<span data-ttu-id="a7d19-162">若要顯示橫條圖及走勢圖, 必須核取 [報表編輯器] 頂端的 [顯示走勢圖] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="a7d19-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="a7d19-163">這會選取趨勢選項, 並將月份向下移動到最後一個維度, 也可以按一下 [月], 然後使用向上鍵和向下鍵來將 [開始時間] 或 [下移]。</span><span class="sxs-lookup"><span data-stu-id="a7d19-163">This will select the Trend option and move Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span> 
  
### <a name="settings"></a><span data-ttu-id="a7d19-164">設置</span><span class="sxs-lookup"><span data-stu-id="a7d19-164">Settings</span></span>

<span data-ttu-id="a7d19-165">位於儀表板右上角的 [設定] 功能表中, 包含有用頁面的連結, 例如 [系統健康情況] 和 [關於] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a7d19-165">Located in the top right corner of the dashboard, the settings menu contains links to useful pages like the System Health and About pages.</span></span>
  
![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)
  
<span data-ttu-id="a7d19-167">是否顯示描述和時間戳記是由個別使用者決定, 這些設定只會影響儀表板的個別版本, 不會修改報告集或其他使用者所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="a7d19-167">Whether or not to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, not does not modify the report set or what other users see.</span></span> <span data-ttu-id="a7d19-168">清除快取會導致所有查詢從立方體重新載入其資料, 而還原預設值時會刪除所有使用者建立或修改的報告, 並重新建立系統報告集, 這是使用者第一次登入時所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="a7d19-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when logging in for the first time.</span></span>
  
<span data-ttu-id="a7d19-169">[使用者儀表板] 連結會顯示一個頁面, 使用者可以在其中查看 CQD 的其他使用者並流覽他們的報表。</span><span class="sxs-lookup"><span data-stu-id="a7d19-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="a7d19-170">當您共用報表集時, 只要複製 URL 列中的連結, 並與其他 CQD 使用者共用。</span><span class="sxs-lookup"><span data-stu-id="a7d19-170">When sharing a report set, simply copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="a7d19-171">此連結將會與其他使用者在使用者儀表板連結頁面上看到的使用者使用者名稱相同。</span><span class="sxs-lookup"><span data-stu-id="a7d19-171">This link will be the same as the one other users would see in the Users Dashboard Link page under the user's username.</span></span>
  
### <a name="supplying-subnet-information"></a><span data-ttu-id="a7d19-172">提供子網資訊</span><span class="sxs-lookup"><span data-stu-id="a7d19-172">Supplying Subnet Information</span></span>

<span data-ttu-id="a7d19-173">如果將網站特定資訊輸入到封存資料庫, 以提供子網間的對應資訊 (例如有線/無線通話品質 (透過組建)), 就可以顯示更多深入見解。</span><span class="sxs-lookup"><span data-stu-id="a7d19-173">Additional insights can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (e.g. wired/wireless call quality by building).</span></span> 
  
<span data-ttu-id="a7d19-174">至少, 必須填入下清單格, 才能建立這些報告:</span><span class="sxs-lookup"><span data-stu-id="a7d19-174">At a minimum, the following tables need to be populated to create these reports:</span></span>
  
- <span data-ttu-id="a7d19-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="a7d19-175">CqdBuilding</span></span>
    
- <span data-ttu-id="a7d19-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="a7d19-176">CqdNetwork</span></span>
    
<span data-ttu-id="a7d19-177">您可以在 CqdBuildingType 和 CqdBuildingOwnershipType 資料表中提供其他資訊, 以允許進一步篩選與向下切入。</span><span class="sxs-lookup"><span data-stu-id="a7d19-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span> 
  
<span data-ttu-id="a7d19-178">這些資料表的架構定義如下:</span><span class="sxs-lookup"><span data-stu-id="a7d19-178">The schema for these tables are defined as follows:</span></span>
  
<span data-ttu-id="a7d19-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="a7d19-179">**CqdBuilding**</span></span>

|<span data-ttu-id="a7d19-180">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a7d19-180">**Column**</span></span>|<span data-ttu-id="a7d19-181">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a7d19-181">**Data Type**</span></span>|<span data-ttu-id="a7d19-182">**允許 Null 嗎？**</span><span class="sxs-lookup"><span data-stu-id="a7d19-182">**Allow Nulls?**</span></span>|<span data-ttu-id="a7d19-183">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a7d19-183">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="a7d19-184">BuildingKey</span></span>  <br/> |<span data-ttu-id="a7d19-185">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-185">int</span></span>  <br/> |<span data-ttu-id="a7d19-186">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-186">No</span></span>  <br/> |<span data-ttu-id="a7d19-187">CqdBuilding 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="a7d19-187">Primary key for the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="a7d19-188">BuildingName</span></span>  <br/> |<span data-ttu-id="a7d19-189">Varchar (80)</span><span class="sxs-lookup"><span data-stu-id="a7d19-189">varchar(80)</span></span>  <br/> |<span data-ttu-id="a7d19-190">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-190">No</span></span>  <br/> |<span data-ttu-id="a7d19-191">建築物名稱。</span><span class="sxs-lookup"><span data-stu-id="a7d19-191">Building name.</span></span>  <br/> |
|<span data-ttu-id="a7d19-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="a7d19-192">BuildingShortName</span></span>  <br/> |<span data-ttu-id="a7d19-193">Varchar (10)</span><span class="sxs-lookup"><span data-stu-id="a7d19-193">varchar(10)</span></span>  <br/> |<span data-ttu-id="a7d19-194">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-194">No</span></span>  <br/> |<span data-ttu-id="a7d19-195">[建築物名稱] 的較短版本。</span><span class="sxs-lookup"><span data-stu-id="a7d19-195">Shorter version of the Building name.</span></span>  <br/> |
|<span data-ttu-id="a7d19-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="a7d19-196">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="a7d19-197">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-197">int</span></span>  <br/> |<span data-ttu-id="a7d19-198">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-198">No</span></span>  <br/> |<span data-ttu-id="a7d19-199">外鍵, 應與 CqdBuildingOwners 資料表中的其中一個 entreis 相符。</span><span class="sxs-lookup"><span data-stu-id="a7d19-199">Foreign key, should match one of the entreis in the CqdBuildingOwners table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="a7d19-200">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="a7d19-201">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-201">int</span></span>  <br/> |<span data-ttu-id="a7d19-202">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-202">No</span></span>  <br/> |<span data-ttu-id="a7d19-203">外鍵, 應與 CqdBuildingType 資料表中的其中一個專案相符。</span><span class="sxs-lookup"><span data-stu-id="a7d19-203">Foreign key, should match one of the entries in the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-204">Latitutde</span><span class="sxs-lookup"><span data-stu-id="a7d19-204">Latitutde</span></span>  <br/> |<span data-ttu-id="a7d19-205">浮</span><span class="sxs-lookup"><span data-stu-id="a7d19-205">float</span></span>  <br/> |<span data-ttu-id="a7d19-206">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-206">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-207">建築物的緯度。</span><span class="sxs-lookup"><span data-stu-id="a7d19-207">Latitude of the building.</span></span>  <br/> |
|<span data-ttu-id="a7d19-208">經度</span><span class="sxs-lookup"><span data-stu-id="a7d19-208">Longitude</span></span>  <br/> |<span data-ttu-id="a7d19-209">浮</span><span class="sxs-lookup"><span data-stu-id="a7d19-209">float</span></span>  <br/> |<span data-ttu-id="a7d19-210">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-210">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-211">建築物的經度。</span><span class="sxs-lookup"><span data-stu-id="a7d19-211">Longitude of the building.</span></span>  <br/> |
|<span data-ttu-id="a7d19-212">CityName</span><span class="sxs-lookup"><span data-stu-id="a7d19-212">CityName</span></span>  <br/> |<span data-ttu-id="a7d19-213">Varchar (30)</span><span class="sxs-lookup"><span data-stu-id="a7d19-213">varchar(30)</span></span>  <br/> |<span data-ttu-id="a7d19-214">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-214">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-215">建築物所在的市/縣名。</span><span class="sxs-lookup"><span data-stu-id="a7d19-215">City name where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a7d19-216">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="a7d19-216">ZipCode</span></span>  <br/> |<span data-ttu-id="a7d19-217">Varchar (25)</span><span class="sxs-lookup"><span data-stu-id="a7d19-217">varchar(25)</span></span>  <br/> |<span data-ttu-id="a7d19-218">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-218">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-219">組建所在的郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="a7d19-219">Zip code where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a7d19-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="a7d19-220">CountryShortCode</span></span>  <br/> |<span data-ttu-id="a7d19-221">Varchar (2)</span><span class="sxs-lookup"><span data-stu-id="a7d19-221">varchar(2)</span></span>  <br/> |<span data-ttu-id="a7d19-222">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-222">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-223">組建所在國家/地區的 ISO 3166-1 字母2代碼。</span><span class="sxs-lookup"><span data-stu-id="a7d19-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a7d19-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="a7d19-224">StateProvinceCode</span></span>  <br/> |<span data-ttu-id="a7d19-225">Varchar (3)</span><span class="sxs-lookup"><span data-stu-id="a7d19-225">varchar(3)</span></span>  <br/> |<span data-ttu-id="a7d19-226">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-226">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-227">組建所在之州/省的3個字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="a7d19-227">3-letter abbreviation for the State/Province where the building is located.</span></span>  <br/> |
|<span data-ttu-id="a7d19-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="a7d19-228">InsideCorp</span></span>  <br/> |<span data-ttu-id="a7d19-229">稍微</span><span class="sxs-lookup"><span data-stu-id="a7d19-229">bit</span></span>  <br/> |<span data-ttu-id="a7d19-230">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-230">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-231">[位] 表示組建是否是商業網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7d19-231">Bit indicating whether the building is part of the corporate network.</span></span>  <br/> |
|<span data-ttu-id="a7d19-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="a7d19-232">BuildingOfficeType</span></span>  <br/> |<span data-ttu-id="a7d19-233">Nvarchar (150)</span><span class="sxs-lookup"><span data-stu-id="a7d19-233">nvarchar(150)</span></span>  <br/> |<span data-ttu-id="a7d19-234">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-234">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-235">建立 office 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="a7d19-235">Description of the building office type.</span></span>  <br/> |
|<span data-ttu-id="a7d19-236">國家</span><span class="sxs-lookup"><span data-stu-id="a7d19-236">Region</span></span>  <br/> |<span data-ttu-id="a7d19-237">Varchar (25)</span><span class="sxs-lookup"><span data-stu-id="a7d19-237">varchar(25)</span></span>  <br/> |<span data-ttu-id="a7d19-238">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-238">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-239">組建所在的地區。</span><span class="sxs-lookup"><span data-stu-id="a7d19-239">Region where the building is located.</span></span>  <br/> |
   
<span data-ttu-id="a7d19-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="a7d19-240">**CqdNetwork**</span></span>

|<span data-ttu-id="a7d19-241">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a7d19-241">**Column**</span></span>|<span data-ttu-id="a7d19-242">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a7d19-242">**Data Type**</span></span>|<span data-ttu-id="a7d19-243">**允許 Null 嗎？**</span><span class="sxs-lookup"><span data-stu-id="a7d19-243">**Allow Nulls?**</span></span>|<span data-ttu-id="a7d19-244">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a7d19-244">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-245">局域網</span><span class="sxs-lookup"><span data-stu-id="a7d19-245">Network</span></span>  <br/> |<span data-ttu-id="a7d19-246">Varchar (25)</span><span class="sxs-lookup"><span data-stu-id="a7d19-246">varchar(25)</span></span>  <br/> |<span data-ttu-id="a7d19-247">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-247">No</span></span>  <br/> |<span data-ttu-id="a7d19-248">子網位址。</span><span class="sxs-lookup"><span data-stu-id="a7d19-248">Subnet address.</span></span>  <br/> |
|<span data-ttu-id="a7d19-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="a7d19-249">NetworkRange</span></span>  <br/> |<span data-ttu-id="a7d19-250">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a7d19-250">tinyint</span></span>  <br/> |<span data-ttu-id="a7d19-251">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-251">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-252">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="a7d19-252">Subnet mask.</span></span>  <br/> |
|<span data-ttu-id="a7d19-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="a7d19-253">NetworkNameID</span></span>  <br/> |<span data-ttu-id="a7d19-254">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-254">int</span></span>  <br/> |<span data-ttu-id="a7d19-255">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-255">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-256">選擇性地對應至 CqdNetworkName 資料表中的列。</span><span class="sxs-lookup"><span data-stu-id="a7d19-256">Optionally maps to a row in CqdNetworkName table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="a7d19-257">BuildingKey</span></span>  <br/> |<span data-ttu-id="a7d19-258">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-258">int</span></span>  <br/> |<span data-ttu-id="a7d19-259">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-259">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-260">外鍵, 應與 CqdBuilding 資料表中的其中一個專案相符。</span><span class="sxs-lookup"><span data-stu-id="a7d19-260">Foreign key, should match one of the entries in the CqdBuilding table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="a7d19-261">UpdatedDate</span></span>  <br/> |<span data-ttu-id="a7d19-262">datetime</span><span class="sxs-lookup"><span data-stu-id="a7d19-262">datetime</span></span>  <br/> |<span data-ttu-id="a7d19-263">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-263">No</span></span>  <br/> |<span data-ttu-id="a7d19-264">上次更新專案的日期時間。</span><span class="sxs-lookup"><span data-stu-id="a7d19-264">Datetime for when the entry was last updated.</span></span>  <br/> |
   
<span data-ttu-id="a7d19-265">根據預設, 下一個資料表有一個專案 (0, "Unknown")。</span><span class="sxs-lookup"><span data-stu-id="a7d19-265">By default this next table has one entry (0, 'Unknown').</span></span>
  
<span data-ttu-id="a7d19-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="a7d19-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="a7d19-267">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a7d19-267">**Column**</span></span>|<span data-ttu-id="a7d19-268">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a7d19-268">**Data Type**</span></span>|<span data-ttu-id="a7d19-269">**允許 Null 嗎？**</span><span class="sxs-lookup"><span data-stu-id="a7d19-269">**Allow Nulls?**</span></span>|<span data-ttu-id="a7d19-270">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a7d19-270">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="a7d19-271">BuildingTypeId</span></span>  <br/> |<span data-ttu-id="a7d19-272">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-272">int</span></span>  <br/> |<span data-ttu-id="a7d19-273">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-273">No</span></span>  <br/> |<span data-ttu-id="a7d19-274">CqdBuildingType 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="a7d19-274">Primary key for the CqdBuildingType table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="a7d19-275">BuildingTypeDesc</span></span>  <br/> |<span data-ttu-id="a7d19-276">char (18)</span><span class="sxs-lookup"><span data-stu-id="a7d19-276">char(18)</span></span>  <br/> |<span data-ttu-id="a7d19-277">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-277">No</span></span>  <br/> |<span data-ttu-id="a7d19-278">[建築物類型描述]。</span><span class="sxs-lookup"><span data-stu-id="a7d19-278">Building type description.</span></span>  <br/> |
   
<span data-ttu-id="a7d19-279">根據預設, 下一個資料表有一個專案 (0, "Unknown", 0, null)。</span><span class="sxs-lookup"><span data-stu-id="a7d19-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="a7d19-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="a7d19-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="a7d19-281">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a7d19-281">**Column**</span></span>|<span data-ttu-id="a7d19-282">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a7d19-282">**Data Type**</span></span>|<span data-ttu-id="a7d19-283">**允許 Null 嗎？**</span><span class="sxs-lookup"><span data-stu-id="a7d19-283">**Allow Nulls?**</span></span>|<span data-ttu-id="a7d19-284">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a7d19-284">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="a7d19-285">OwnershipTypeId</span></span>  <br/> |<span data-ttu-id="a7d19-286">int</span><span class="sxs-lookup"><span data-stu-id="a7d19-286">int</span></span>  <br/> |<span data-ttu-id="a7d19-287">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-287">No</span></span>  <br/> |<span data-ttu-id="a7d19-288">CqdBuildingOwnershipType 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="a7d19-288">Primary key for the CqdBuildingOwnershipType table.</span></span>  <br/> |
|<span data-ttu-id="a7d19-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="a7d19-289">OwnershipTypeDesc</span></span>  <br/> |<span data-ttu-id="a7d19-290">Varchar (25)</span><span class="sxs-lookup"><span data-stu-id="a7d19-290">varchar(25)</span></span>  <br/> |<span data-ttu-id="a7d19-291">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-291">No</span></span>  <br/> |<span data-ttu-id="a7d19-292">擁有權類型描述。</span><span class="sxs-lookup"><span data-stu-id="a7d19-292">Ownership type description.</span></span>  <br/> |
|<span data-ttu-id="a7d19-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="a7d19-293">LeaseInd</span></span>  <br/> |<span data-ttu-id="a7d19-294">Tinyint</span><span class="sxs-lookup"><span data-stu-id="a7d19-294">tinyint</span></span>  <br/> |<span data-ttu-id="a7d19-295">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-295">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-296">參照 CqdBuildingOwnershipType 資料表中另一列的索引, 用於識別租的建築物。</span><span class="sxs-lookup"><span data-stu-id="a7d19-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span>  <br/> |
|<span data-ttu-id="a7d19-297">擁有者</span><span class="sxs-lookup"><span data-stu-id="a7d19-297">Owner</span></span>  <br/> |<span data-ttu-id="a7d19-298">Varchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7d19-298">varchar(50)</span></span>  <br/> |<span data-ttu-id="a7d19-299">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-299">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-300">建立擁有者。</span><span class="sxs-lookup"><span data-stu-id="a7d19-300">Building owner.</span></span>  <br/> |
   
<span data-ttu-id="a7d19-301">根據預設, 下一個資料表有一個專案 (0, "Unknown", 0, null)。</span><span class="sxs-lookup"><span data-stu-id="a7d19-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>
  
<span data-ttu-id="a7d19-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="a7d19-302">**CqdBssid**</span></span>

|<span data-ttu-id="a7d19-303">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a7d19-303">**Column**</span></span>|<span data-ttu-id="a7d19-304">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a7d19-304">**Data Type**</span></span>|<span data-ttu-id="a7d19-305">**允許 Null 嗎？**</span><span class="sxs-lookup"><span data-stu-id="a7d19-305">**Allow Nulls?**</span></span>|<span data-ttu-id="a7d19-306">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a7d19-306">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-307">面臨</span><span class="sxs-lookup"><span data-stu-id="a7d19-307">bss</span></span>  <br/> |<span data-ttu-id="a7d19-308">Nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7d19-308">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a7d19-309">不</span><span class="sxs-lookup"><span data-stu-id="a7d19-309">No</span></span>  <br/> |<span data-ttu-id="a7d19-310">CqdBssid 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="a7d19-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="a7d19-311">是 Wifi 存取點的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="a7d19-311">Is the BSSID of the Wifi Access Point.</span></span>  <br/> |
|<span data-ttu-id="a7d19-312">員工</span><span class="sxs-lookup"><span data-stu-id="a7d19-312">ess</span></span>  <br/> |<span data-ttu-id="a7d19-313">Nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7d19-313">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a7d19-314">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-314">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-315">Wifi 存取點控制器資訊。</span><span class="sxs-lookup"><span data-stu-id="a7d19-315">Wifi Access Point Controller information.</span></span>  <br/> |
|<span data-ttu-id="a7d19-316">phy</span><span class="sxs-lookup"><span data-stu-id="a7d19-316">phy</span></span>  <br/> |<span data-ttu-id="a7d19-317">Nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7d19-317">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a7d19-318">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-318">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-319">Phy 資訊。</span><span class="sxs-lookup"><span data-stu-id="a7d19-319">Phy information.</span></span>  <br/> |
|<span data-ttu-id="a7d19-320">應付</span><span class="sxs-lookup"><span data-stu-id="a7d19-320">ap</span></span>  <br/> |<span data-ttu-id="a7d19-321">Nvarchar (50)</span><span class="sxs-lookup"><span data-stu-id="a7d19-321">nvarchar(50)</span></span>  <br/> |<span data-ttu-id="a7d19-322">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-322">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-323">Wifi 存取點名稱。</span><span class="sxs-lookup"><span data-stu-id="a7d19-323">Wifi Access Point Name.</span></span>  <br/> |
|<span data-ttu-id="a7d19-324">創建</span><span class="sxs-lookup"><span data-stu-id="a7d19-324">Building</span></span>  <br/> |<span data-ttu-id="a7d19-325">Nvarchar (500)</span><span class="sxs-lookup"><span data-stu-id="a7d19-325">nvarchar(500)</span></span>  <br/> |<span data-ttu-id="a7d19-326">是的</span><span class="sxs-lookup"><span data-stu-id="a7d19-326">Yes</span></span>  <br/> |<span data-ttu-id="a7d19-327">Wifi 存取點所在的建築物名稱。</span><span class="sxs-lookup"><span data-stu-id="a7d19-327">The Building Name the Wifi Access Point is located in.</span></span>  <br/> |
   
## <a name="cqd-streams"></a><span data-ttu-id="a7d19-328">CQD 串流</span><span class="sxs-lookup"><span data-stu-id="a7d19-328">CQD Streams</span></span>

<span data-ttu-id="a7d19-329">CQD 串流將是良好、較差或未分類。</span><span class="sxs-lookup"><span data-stu-id="a7d19-329">A CQD stream will be good, poor or unclassified.</span></span> <span data-ttu-id="a7d19-330">CQM 1.5 現在使用下列 CQD 定義:</span><span class="sxs-lookup"><span data-stu-id="a7d19-330">CQM 1.5 now uses the following CQD definition:</span></span> 
  
- <span data-ttu-id="a7d19-331">較差的資料流程是不佳的呼叫指標超出閾值的任何組合。</span><span class="sxs-lookup"><span data-stu-id="a7d19-331">A poor stream is any combination of the poor call metrics going beyond threshold.</span></span>
    
- <span data-ttu-id="a7d19-332">當通話中的一個資料流程不佳時, 兩個通話串流都會標示為不佳。</span><span class="sxs-lookup"><span data-stu-id="a7d19-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="a7d19-333">在會議中, 每個參與者都會算作唯一通話, 而且會與其他人獨立報告。</span><span class="sxs-lookup"><span data-stu-id="a7d19-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
    
- <span data-ttu-id="a7d19-334">未分類的資料流程是不含品質標準 (亦即綜合交易、短通話) 的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a7d19-334">Unclassified streams are streams without quality metrics (i.e. Synthetic Transactions, short calls).</span></span>
    
- <span data-ttu-id="a7d19-335">有效的資料流程 = 非行動用戶端</span><span class="sxs-lookup"><span data-stu-id="a7d19-335">Valid Streams = non-mobile clients</span></span>
    
- <span data-ttu-id="a7d19-336">無法修改分類器</span><span class="sxs-lookup"><span data-stu-id="a7d19-336">Classifier cannot be modified</span></span>
    
<span data-ttu-id="a7d19-337">**較差的通話定義/分類器**</span><span class="sxs-lookup"><span data-stu-id="a7d19-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="a7d19-338">**衡量**</span><span class="sxs-lookup"><span data-stu-id="a7d19-338">**Metric**</span></span>|<span data-ttu-id="a7d19-339">**閾值**</span><span class="sxs-lookup"><span data-stu-id="a7d19-339">**Threshold**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a7d19-340">DDegradationAvg</span><span class="sxs-lookup"><span data-stu-id="a7d19-340">DDegradationAvg</span></span>  <br/> |<span data-ttu-id="a7d19-341">大於 1.0 (-1 網路 MOS)</span><span class="sxs-lookup"><span data-stu-id="a7d19-341">Greater than 1.0 (-1 network MOS)</span></span>  <br/> |
|<span data-ttu-id="a7d19-342">環路</span><span class="sxs-lookup"><span data-stu-id="a7d19-342">RoundTrip</span></span>  <br/> |<span data-ttu-id="a7d19-343">大於500</span><span class="sxs-lookup"><span data-stu-id="a7d19-343">Greater than 500</span></span>  <br/> |
|<span data-ttu-id="a7d19-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="a7d19-344">PacketLossRate</span></span>  <br/> |<span data-ttu-id="a7d19-345">大於. 1 (10%)</span><span class="sxs-lookup"><span data-stu-id="a7d19-345">Greater than .1 (10%)</span></span>  <br/> |
|<span data-ttu-id="a7d19-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="a7d19-346">JitterInterArrival</span></span>  <br/> |<span data-ttu-id="a7d19-347">超過30</span><span class="sxs-lookup"><span data-stu-id="a7d19-347">Greater than 30</span></span>  <br/> |
|<span data-ttu-id="a7d19-348">RRatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a7d19-348">RRatioConcealedSamplesAvg</span></span>  <br/> |<span data-ttu-id="a7d19-349">大於07</span><span class="sxs-lookup"><span data-stu-id="a7d19-349">Greater than .07</span></span>  <br/> |
   
<span data-ttu-id="a7d19-350">JPDR definition = 差的通話定義減去 RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="a7d19-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span> 
  
## <a name="where-is-callercallee"></a><span data-ttu-id="a7d19-351">來電者/被叫方的位置為何？</span><span class="sxs-lookup"><span data-stu-id="a7d19-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="a7d19-352">CQD 不使用 [來電者/被叫方] 欄位。</span><span class="sxs-lookup"><span data-stu-id="a7d19-352">CQD doesn't use Caller/Callee fields.</span></span> <span data-ttu-id="a7d19-353">這些已重新命名為「First」和 "Second", 因為來電者與被叫方之間有中間個步驟。</span><span class="sxs-lookup"><span data-stu-id="a7d19-353">These have been renamed "First" and "Second" because there are intervening steps between the caller and callee.</span></span>
  
 <span data-ttu-id="a7d19-354">**首先**永遠是伺服器端點 (例如 AV MCU);中繼伺服器) 如果資料流程中包含伺服器。</span><span class="sxs-lookup"><span data-stu-id="a7d19-354">**First** Will always be the Server endpoint (e.g. AV MCU; Mediation Server) if a Server is involved in the stream.</span></span>
  
 <span data-ttu-id="a7d19-355">**秒**除非是伺服器-伺服器資料流程, 否則將永遠是用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="a7d19-355">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>
  
<span data-ttu-id="a7d19-356">**第一和第二個分類範例**</span><span class="sxs-lookup"><span data-stu-id="a7d19-356">**Example of First and Second classification**</span></span>

|<span data-ttu-id="a7d19-357">**端點 1 UAType**</span><span class="sxs-lookup"><span data-stu-id="a7d19-357">**Endpoint 1 UAType**</span></span>|<span data-ttu-id="a7d19-358">**端點 2 UUAType**</span><span class="sxs-lookup"><span data-stu-id="a7d19-358">**Endpoint 2 UUAType**</span></span>|<span data-ttu-id="a7d19-359">**一**</span><span class="sxs-lookup"><span data-stu-id="a7d19-359">**First**</span></span>|<span data-ttu-id="a7d19-360">**第二個**</span><span class="sxs-lookup"><span data-stu-id="a7d19-360">**Second**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7d19-361">2 (AVMCU)</span><span class="sxs-lookup"><span data-stu-id="a7d19-361">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="a7d19-362">4 (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="a7d19-362">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a7d19-363">端點1</span><span class="sxs-lookup"><span data-stu-id="a7d19-363">Endpoint 1</span></span>  <br/> |<span data-ttu-id="a7d19-364">端點2</span><span class="sxs-lookup"><span data-stu-id="a7d19-364">Endpoint 2</span></span>  <br/> |
|<span data-ttu-id="a7d19-365">2 (AVMCU)</span><span class="sxs-lookup"><span data-stu-id="a7d19-365">2 (AVMCU)</span></span>  <br/> |<span data-ttu-id="a7d19-366">1 (mMediationServer)</span><span class="sxs-lookup"><span data-stu-id="a7d19-366">1 (mMediationServer)</span></span>  <br/> |<span data-ttu-id="a7d19-367">端點2</span><span class="sxs-lookup"><span data-stu-id="a7d19-367">Endpoint 2</span></span>  <br/> |<span data-ttu-id="a7d19-368">端點1</span><span class="sxs-lookup"><span data-stu-id="a7d19-368">Endpoint 1</span></span>  <br/> |
|<span data-ttu-id="a7d19-369">4 (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="a7d19-369">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a7d19-370">4 (商務用 Skype)</span><span class="sxs-lookup"><span data-stu-id="a7d19-370">4 (Skype for Business)</span></span>  <br/> |<span data-ttu-id="a7d19-371">MediaLine 中的來電者</span><span class="sxs-lookup"><span data-stu-id="a7d19-371">The Caller in MediaLine</span></span>  <br/> |<span data-ttu-id="a7d19-372">MMediaLine 中的被呼叫者</span><span class="sxs-lookup"><span data-stu-id="a7d19-372">The Callee in MMediaLine</span></span>  <br/> |
   
<span data-ttu-id="a7d19-373">如果兩個端點都是相同的類型, CQD 將會先進行本機號碼, 而被叫用者將會成為第二個端點。</span><span class="sxs-lookup"><span data-stu-id="a7d19-373">If both endpoints are the same type, CQD will make the Caller entry First and Callee will become Second.</span></span> <span data-ttu-id="a7d19-374">如需詳細資訊, 請參閱[這篇博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a7d19-374">See [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx) for more information.</span></span>
  
## <a name="accounting-for-vpn"></a><span data-ttu-id="a7d19-375">VPN 記帳</span><span class="sxs-lookup"><span data-stu-id="a7d19-375">Accounting for VPN</span></span>

<span data-ttu-id="a7d19-376">如果已知 VPN 解決方案能正確設定 VPN 標誌, 就是一切都已設定好了。</span><span class="sxs-lookup"><span data-stu-id="a7d19-376">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="a7d19-377">否則, 請使用下列其中一種方法:</span><span class="sxs-lookup"><span data-stu-id="a7d19-377">Otherwise, use one of the methods below:</span></span>
  
- <span data-ttu-id="a7d19-378">建立名為 [VPN (慣用)] 的網路類型, 然後將 VPN 子網與這個新的 VPN NetworkType。</span><span class="sxs-lookup"><span data-stu-id="a7d19-378">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
    
- <span data-ttu-id="a7d19-379">建立名為 [VPN] 的建築物, 然後將 VPN 子網與此組建建立關聯。</span><span class="sxs-lookup"><span data-stu-id="a7d19-379">Create a building called VPN, then Associate VPN Subnets with this building.</span></span> 
    
## <a name="query-fundamentals"></a><span data-ttu-id="a7d19-380">查詢基礎</span><span class="sxs-lookup"><span data-stu-id="a7d19-380">Query Fundamentals</span></span>

<span data-ttu-id="a7d19-381">標準格式的查詢包含下列三個參數:</span><span class="sxs-lookup"><span data-stu-id="a7d19-381">A well-formed query contains all three of these parameters:</span></span> 
  
- <span data-ttu-id="a7d19-382">數值</span><span class="sxs-lookup"><span data-stu-id="a7d19-382">Measurement</span></span>
    
- <span data-ttu-id="a7d19-383">焦點</span><span class="sxs-lookup"><span data-stu-id="a7d19-383">Dimension</span></span>
    
- <span data-ttu-id="a7d19-384">Filter</span><span class="sxs-lookup"><span data-stu-id="a7d19-384">Filter</span></span>
    
<span data-ttu-id="a7d19-385">標準格式的查詢範例是「顯示我的資料流程不佳 [度量衡]: 由子網 [Dimension] 用於建築物 6 [篩選]。」</span><span class="sxs-lookup"><span data-stu-id="a7d19-385">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>
  
## <a name="what-does-union-do"></a><span data-ttu-id="a7d19-386">UNION 運算是什麼？</span><span class="sxs-lookup"><span data-stu-id="a7d19-386">What does UNION do?</span></span>

<span data-ttu-id="a7d19-387">[聯合] 可讓您使用 AND 運算子來篩選準則。</span><span class="sxs-lookup"><span data-stu-id="a7d19-387">Union allows you to filter conditions using the AND operator.</span></span> <span data-ttu-id="a7d19-388">在某些情況下, 您需要將多個篩選準則結合在一起, 以達到或類似的結果</span><span class="sxs-lookup"><span data-stu-id="a7d19-388">There are scenarios where you need to combine multiple Filter conditions together to achieve an OR like result</span></span>
  
<span data-ttu-id="a7d19-389">範例: 當您需要從建築物同盟取得所有資料流程時, 將會提供合併資料集的不同視圖。</span><span class="sxs-lookup"><span data-stu-id="a7d19-389">Example: When you need to get all streams from a building UNION will provide a distinct view of the merged dataset.</span></span> <span data-ttu-id="a7d19-390">若要使用 UNION, 請在您想要合併的兩個篩選準則上, 將一般文字插入聯合欄位。</span><span class="sxs-lookup"><span data-stu-id="a7d19-390">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span> 
  
## <a name="default-report-breakdown"></a><span data-ttu-id="a7d19-391">預設報告細目</span><span class="sxs-lookup"><span data-stu-id="a7d19-391">Default Report Breakdown</span></span>

<span data-ttu-id="a7d19-392">如果是內部管理無線, 您可以在 Managed bucket 中重新建立無線報告。</span><span class="sxs-lookup"><span data-stu-id="a7d19-392">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span> 
  
![CQD 報告細目](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)
  
## <a name="operational-processes"></a><span data-ttu-id="a7d19-394">操作程式</span><span class="sxs-lookup"><span data-stu-id="a7d19-394">Operational Processes</span></span>

<span data-ttu-id="a7d19-395">首先, 查看並修正受管理的資料流程。</span><span class="sxs-lookup"><span data-stu-id="a7d19-395">Start by reviewing and remediating Managed Streams.</span></span> <span data-ttu-id="a7d19-396">此區域中的品質應該在您的控制項內是 100%, 因此最容易修正。</span><span class="sxs-lookup"><span data-stu-id="a7d19-396">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span> 
  
### <a name="managed-streams"></a><span data-ttu-id="a7d19-397">受管理的資料流程</span><span class="sxs-lookup"><span data-stu-id="a7d19-397">Managed Streams</span></span>

<span data-ttu-id="a7d19-398">以下列順序查看及修正受管理的資料流程:</span><span class="sxs-lookup"><span data-stu-id="a7d19-398">Review and remediate managed streams in the following order:</span></span> 
  
1. <span data-ttu-id="a7d19-399">伺服器-伺服器</span><span class="sxs-lookup"><span data-stu-id="a7d19-399">Server-Server</span></span> 
    
2.  <span data-ttu-id="a7d19-400">伺服器-內接線</span><span class="sxs-lookup"><span data-stu-id="a7d19-400">Server-Wired-Inside</span></span>
    
3. <span data-ttu-id="a7d19-401">有線-有線-內</span><span class="sxs-lookup"><span data-stu-id="a7d19-401">Wired-Wired-Inside</span></span> 
    
### <a name="unmanaged-streams"></a><span data-ttu-id="a7d19-402">非託管資料流程</span><span class="sxs-lookup"><span data-stu-id="a7d19-402">Unmanaged Streams</span></span>

<span data-ttu-id="a7d19-403">以下列順序評審及修正非託管的資料流程:</span><span class="sxs-lookup"><span data-stu-id="a7d19-403">Review and remediate unmanaged streams in the following order:</span></span> 
  
1. <span data-ttu-id="a7d19-404">伺服器-Wifi-內</span><span class="sxs-lookup"><span data-stu-id="a7d19-404">Server-Wifi-Inside</span></span>
    
2. <span data-ttu-id="a7d19-405">伺服器-在外-有線</span><span class="sxs-lookup"><span data-stu-id="a7d19-405">Server-Wired-Outside</span></span>
    
3. <span data-ttu-id="a7d19-406">伺服器-Wifi-外</span><span class="sxs-lookup"><span data-stu-id="a7d19-406">Server-Wifi-Outside</span></span>
    
4. <span data-ttu-id="a7d19-407">有線-直向外</span><span class="sxs-lookup"><span data-stu-id="a7d19-407">Wired-Outside-Direct</span></span>
    
5. <span data-ttu-id="a7d19-408">有線外部中繼</span><span class="sxs-lookup"><span data-stu-id="a7d19-408">Wired-Outside-Relay</span></span>
    
6. <span data-ttu-id="a7d19-409">其他未受管理</span><span class="sxs-lookup"><span data-stu-id="a7d19-409">Other Unmanaged</span></span>
    

