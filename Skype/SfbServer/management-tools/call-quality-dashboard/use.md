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
description: 摘要：瞭解如何使用通話品質儀表板。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 09eb8bdae508ff9a5fe39fec67b0f440859efad0
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774703"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="e1f23-104">使用商務用 Skype Server 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="e1f23-104">Use Call Quality Dashboard for Skype for Business Server</span></span>

<span data-ttu-id="e1f23-105">**摘要：** 瞭解如何使用通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="e1f23-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="e1f23-106">[通話品質儀表板] 是商務用 Skype Server 的工具。</span><span class="sxs-lookup"><span data-stu-id="e1f23-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="e1f23-107">通話品質儀表板（CQD）可讓 IT 專業人員使用匯總資料來找出產生媒體質量問題的問題，方法是比較使用者群組的統計資料來識別趨勢和模式。</span><span class="sxs-lookup"><span data-stu-id="e1f23-107">Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by  comparing statistics for groups of users to identify trends and patterns.</span></span> <span data-ttu-id="e1f23-108">CQD 並非專注于解決個別的呼叫問題，但在識別適用于許多使用者的問題和解決方案上。</span><span class="sxs-lookup"><span data-stu-id="e1f23-108">CQD is not focused on solving individual call issues, but on identifying problems and solutions that apply to many users.</span></span>

## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="e1f23-109">通話品質儀表板使用者指南</span><span class="sxs-lookup"><span data-stu-id="e1f23-109">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="e1f23-110">CQD 是一種網頁入口網站，可根據體驗品質（QoE）資料快速建立及組織報表。</span><span class="sxs-lookup"><span data-stu-id="e1f23-110">CQD is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="e1f23-111">CQD 會部署一個 SSAS 立方體來匯總 QoE 公制資料庫中的資料，並讓系統管理員能夠即時建立及修改報告或進行調查。</span><span class="sxs-lookup"><span data-stu-id="e1f23-111">CQD deploys an SSAS cube to aggregate the data in the QoE Metrics database, and enables admins to create and modify reports or do investigations in real time.</span></span> <span data-ttu-id="e1f23-112">雖然您可以使用 Excel 直接連線至立方體，但入口網站已針對多個涉及 QoE 資料的工作流程進行優化。</span><span class="sxs-lookup"><span data-stu-id="e1f23-112">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="e1f23-113">資料包括：</span><span class="sxs-lookup"><span data-stu-id="e1f23-113">The data includes:</span></span>

- <span data-ttu-id="e1f23-114">可快速存取的快取報表資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-114">Cached report data for fast access</span></span>
- <span data-ttu-id="e1f23-115">深入瞭解資訊共用與發佈的報表頁面</span><span class="sxs-lookup"><span data-stu-id="e1f23-115">Deep links to report pages for information sharing and publishing</span></span>
- <span data-ttu-id="e1f23-116">簡化報表的編輯與建立，以及報表描述的可編輯中繼資料。</span><span class="sxs-lookup"><span data-stu-id="e1f23-116">Streamlined report editing and creation, and editable metadata for report descriptions.</span></span>

<span data-ttu-id="e1f23-117">此外，CQD 會公開 web Api，讓使用者以程式設計方式存取要在自訂儀表板中使用的多維資料集資料。</span><span class="sxs-lookup"><span data-stu-id="e1f23-117">Also, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>

### <a name="feature-overview"></a><span data-ttu-id="e1f23-118">功能概述</span><span class="sxs-lookup"><span data-stu-id="e1f23-118">Feature Overview</span></span>

<span data-ttu-id="e1f23-119">當您流覽 [通話品質] 儀表板時，您會看到下列畫面：</span><span class="sxs-lookup"><span data-stu-id="e1f23-119">When you visit the Call Quality Dashboard, you see the following screen:</span></span>

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. <span data-ttu-id="e1f23-121">您可以在 [摘要窗格] 中找到 [報表集] （右側）的內容。</span><span class="sxs-lookup"><span data-stu-id="e1f23-121">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span>
2. <span data-ttu-id="e1f23-122">按一下 [摘要 PaneReport] 中的 [編輯]，以設定階層屬性（包括 Y 軸高）。</span><span class="sxs-lookup"><span data-stu-id="e1f23-122">Click "Edit" in the Summary PaneReport to set level properties (including Y-axis height).</span></span>
3. <span data-ttu-id="e1f23-123">軌跡瀏覽可協助您識別報表集階層中您目前的位置。</span><span class="sxs-lookup"><span data-stu-id="e1f23-123">The Breadcrumb helps you identify your current location within the report set hierarchy.</span></span>
4. <span data-ttu-id="e1f23-124">含有子報表的報表會以藍色連結顯示。</span><span class="sxs-lookup"><span data-stu-id="e1f23-124">Reports with subreports are shown with a blue link.</span></span> <span data-ttu-id="e1f23-125">按一下連結以向下切入至 [子報表]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-125">Click the link to drill down to the child reports.</span></span>

<span data-ttu-id="e1f23-126">將滑鼠移至橫條圖和趨勢線上方，以顯示詳細的值。</span><span class="sxs-lookup"><span data-stu-id="e1f23-126">Move the mouse over the bar charts and trend lines to show detailed values.</span></span> <span data-ttu-id="e1f23-127">具有焦點的報表會顯示動作功能表： [編輯]、[克隆]、[刪除] 和 [下載]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-127">The report that has focus shows the action menu: "Edit", "Clone", "Delete", and "Download".</span></span>

### <a name="default-reports"></a><span data-ttu-id="e1f23-128">預設報表</span><span class="sxs-lookup"><span data-stu-id="e1f23-128">Default Reports</span></span>

<span data-ttu-id="e1f23-129">當您第一次存取通話品質儀表板入口網站時，系統會自動建立一組預設的報告。</span><span class="sxs-lookup"><span data-stu-id="e1f23-129">When you first access the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="e1f23-130">這些報告有時稱為「系統報告」。</span><span class="sxs-lookup"><span data-stu-id="e1f23-130">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="e1f23-131">您可以透過建立新的同輩與子報表來自由修改或刪除這些報表或進行延伸。</span><span class="sxs-lookup"><span data-stu-id="e1f23-131">You are able to freely modify or delete these reports or extend them by creating new sibling and child reports.</span></span>

<span data-ttu-id="e1f23-132">在最上層，「音訊串流月趨勢」報告會顯示所有音訊資料流程的每月趨勢。</span><span class="sxs-lookup"><span data-stu-id="e1f23-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="e1f23-133">將滑鼠移至橫條圖中的條形上方，以顯示橫條圖所代表之資料的更詳細的視圖。</span><span class="sxs-lookup"><span data-stu-id="e1f23-133">Move the mouse over the bars in a bar chart to show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="e1f23-134">按一下 [音訊流量] 的 [每月趨勢報告] 標題，流覽至 [Managed vs 非託管音訊資料流程] 報告，其中的報告是在託管與未受管理的呼叫之間分割。</span><span class="sxs-lookup"><span data-stu-id="e1f23-134">Click the title of the Audio Streams Monthly Trend report to navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="e1f23-135">Managed 通話是透過有線連線在企業防火牆內進行的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e1f23-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="e1f23-136">非託管通話包括從公司防火牆以外的電話，以及透過 Wi-fi 進行的所有通話。</span><span class="sxs-lookup"><span data-stu-id="e1f23-136">Unmanaged calls include calls made from outside the corporate firewall and all calls made over Wi-Fi.</span></span>

<span data-ttu-id="e1f23-137">其他最上層的報表稱為「使用者報告的通話品質評等長條圖」。</span><span class="sxs-lookup"><span data-stu-id="e1f23-137">The other top-level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="e1f23-138">通話品質評等是通話結束時，商務用 Skype 使用者所提供的數位，表示通話的品質。</span><span class="sxs-lookup"><span data-stu-id="e1f23-138">Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="e1f23-139">評分編號的範圍從1到5，1是最差，5是最佳的。</span><span class="sxs-lookup"><span data-stu-id="e1f23-139">The rating numbers range from 1 to 5, 1 is the worst and 5 is the best.</span></span> <span data-ttu-id="e1f23-140">[長條圖] 會顯示在一個月中指定評等的音訊通話數量。</span><span class="sxs-lookup"><span data-stu-id="e1f23-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span>

<span data-ttu-id="e1f23-141">按一下任何報告的標題，即可在報表中流覽資料的其他篩選。</span><span class="sxs-lookup"><span data-stu-id="e1f23-141">Click the title of any of the reports to navigate into reports with more filters on the data.</span></span> <span data-ttu-id="e1f23-142">在系統報告中，每個子報表都會顯示其父報表中可用的資料子集。</span><span class="sxs-lookup"><span data-stu-id="e1f23-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="e1f23-143">解決問題的模型很簡單：調查資料或趨勢所限制的子報表，並逐漸縮小問題空間。</span><span class="sxs-lookup"><span data-stu-id="e1f23-143">The problem-solving model is simple: investigate which subreport the data or trend suggesting a problem is confined to, and gradually narrow down the problem space.</span></span> <span data-ttu-id="e1f23-144">建立子報表的功能可讓您調查特定資料趨勢的原因。</span><span class="sxs-lookup"><span data-stu-id="e1f23-144">The ability to create subreports allows you to investigate your own guesses about the cause of specific data trends.</span></span>

### <a name="create-and-edit-reports"></a><span data-ttu-id="e1f23-145">建立及編輯報表</span><span class="sxs-lookup"><span data-stu-id="e1f23-145">Create and Edit Reports</span></span>

<span data-ttu-id="e1f23-146">在報表的 [動作] 功能表中，按一下 [編輯]，查看 [報表編輯器]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-146">Click "Edit" in the action menu of a report to see the Report Editor.</span></span> <span data-ttu-id="e1f23-147">每個報告都會以查詢的方式支援到立方體中。</span><span class="sxs-lookup"><span data-stu-id="e1f23-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="e1f23-148">報表是其查詢所傳回資料的視覺效果。</span><span class="sxs-lookup"><span data-stu-id="e1f23-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="e1f23-149">[報告編輯者] 可協助您編輯這些查詢和報表的顯示選項。</span><span class="sxs-lookup"><span data-stu-id="e1f23-149">The Report Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="e1f23-150">當您開啟 [報表編輯器] 時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="e1f23-150">When you open the Report Editor, you  see:</span></span>

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="e1f23-152">在左窗格中選取 [維度]、[量值] 和 [篩選]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="e1f23-153">將游標暫留在其中一個現有的值上，以顯示 [x] 按鈕，讓您可以移除值。</span><span class="sxs-lookup"><span data-stu-id="e1f23-153">Hover over one of the existing values to show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="e1f23-154">按一下標題旁邊的 [加號] 按鈕，以開啟對話方塊，您可以在其中新增維度、量值或篩選。</span><span class="sxs-lookup"><span data-stu-id="e1f23-154">Click the "plus" button next to a heading to open the dialog where you can add a new dimension, measure, or filter.</span></span>
2. <span data-ttu-id="e1f23-155">圖表自訂的選項會顯示在頂端。</span><span class="sxs-lookup"><span data-stu-id="e1f23-155">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="e1f23-156">報表的預覽可在 [報表編輯器] 中取得。</span><span class="sxs-lookup"><span data-stu-id="e1f23-156">A preview of the report is available in the Report Editor.</span></span>
4. <span data-ttu-id="e1f23-157">您可以在底部的 [編輯] 方塊中建立詳細的報表描述。</span><span class="sxs-lookup"><span data-stu-id="e1f23-157">A detailed report description can be created with the edit box at the bottom.</span></span>

### <a name="sparklines-in-tables"></a><span data-ttu-id="e1f23-158">表格中的走勢圖</span><span class="sxs-lookup"><span data-stu-id="e1f23-158">Sparklines in Tables</span></span>

<span data-ttu-id="e1f23-159">開始時，月份會新增為維度，而且資料會以表格表單中的趨勢轉譯，橫條圖和走勢圖會顯示在表格儲存格內。</span><span class="sxs-lookup"><span data-stu-id="e1f23-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="e1f23-160">將滑鼠指標移至橫條圖和 [走勢圖] 上方，以顯示個別月份的值。</span><span class="sxs-lookup"><span data-stu-id="e1f23-160">Move the mouse pointer over the bar chart and the sparklines to show the values for individual months.</span></span>

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

<span data-ttu-id="e1f23-162">若要顯示橫條圖及走勢圖，必須核取 [報表編輯器] 頂端的 [顯示走勢圖] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e1f23-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="e1f23-163">這會選取趨勢選項並將 Month 移至最後一個維度，也可以按一下 [月]，然後使用向上鍵和向下鍵來將 [開始時間] 或 [下移]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-163">This selects the Trend option and moves Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span>

### <a name="settings"></a><span data-ttu-id="e1f23-164">設置</span><span class="sxs-lookup"><span data-stu-id="e1f23-164">Settings</span></span>

<span data-ttu-id="e1f23-165">[設定] 功能表包含有用頁面的連結，例如 [系統健康情況] 和 [關於] 頁面，且位於儀表板的右上角。</span><span class="sxs-lookup"><span data-stu-id="e1f23-165">The settings menu contains links to useful pages like the System Health and About pages, and is located in the top-right corner of the dashboard.</span></span>

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

<span data-ttu-id="e1f23-167">是否顯示描述和時間戳記是由個別使用者決定，這些設定只會影響儀表板的個別版本，不會修改報告集或其他使用者所看到的內容。</span><span class="sxs-lookup"><span data-stu-id="e1f23-167">Whether to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, and do not modify the report set or what other users see.</span></span> <span data-ttu-id="e1f23-168">清除快取會導致所有查詢從立方體重新載入其資料，而還原預設值時會刪除所有使用者建立或修改過的報告，並重新建立系統報告集—使用者第一次登入時會看到的內容。</span><span class="sxs-lookup"><span data-stu-id="e1f23-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when they log in for the first time.</span></span>

<span data-ttu-id="e1f23-169">[使用者儀表板] 連結會顯示一個頁面，使用者可以在其中查看 CQD 的其他使用者並流覽他們的報表。</span><span class="sxs-lookup"><span data-stu-id="e1f23-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="e1f23-170">若要共用報表集，請複製 URL 列中的連結，並與其他 CQD 使用者共用。</span><span class="sxs-lookup"><span data-stu-id="e1f23-170">To share a report set, copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="e1f23-171">這個連結與其他使用者在 [使用者儀表板連結] 頁面上的使用者使用者名稱下看到的連結相同。</span><span class="sxs-lookup"><span data-stu-id="e1f23-171">This link is the same link other users would see in the Users Dashboard Link page under the user's username.</span></span>

### <a name="supplying-subnet-information"></a><span data-ttu-id="e1f23-172">提供子網資訊</span><span class="sxs-lookup"><span data-stu-id="e1f23-172">Supplying Subnet Information</span></span>

<span data-ttu-id="e1f23-173">如果將網站特定資訊輸入到封存資料庫，以提供子網間的對應資訊（例如有線/無線通話品質（透過組建）），就可以顯示其他資訊。</span><span class="sxs-lookup"><span data-stu-id="e1f23-173">Additional information can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (for example, wired/wireless call quality by building).</span></span>

<span data-ttu-id="e1f23-174">至少要完成下清單格，才能建立這些報告：</span><span class="sxs-lookup"><span data-stu-id="e1f23-174">At a minimum, complete the following tables to create these reports:</span></span>

- <span data-ttu-id="e1f23-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="e1f23-175">CqdBuilding</span></span>
- <span data-ttu-id="e1f23-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="e1f23-176">CqdNetwork</span></span>

<span data-ttu-id="e1f23-177">您可以在 CqdBuildingType 和 CqdBuildingOwnershipType 資料表中提供其他資訊，以允許進一步篩選與向下切入。</span><span class="sxs-lookup"><span data-stu-id="e1f23-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span>

<span data-ttu-id="e1f23-178">這些資料表所用的資料定義如下：</span><span class="sxs-lookup"><span data-stu-id="e1f23-178">The data used for these tables are defined as follows:</span></span>

<span data-ttu-id="e1f23-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="e1f23-179">**CqdBuilding**</span></span>

|<span data-ttu-id="e1f23-180">左欄</span><span class="sxs-lookup"><span data-stu-id="e1f23-180">Column</span></span>|<span data-ttu-id="e1f23-181">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1f23-181">Data Type</span></span>|<span data-ttu-id="e1f23-182">允許 Null 嗎？</span><span class="sxs-lookup"><span data-stu-id="e1f23-182">Allow Nulls?</span></span>|<span data-ttu-id="e1f23-183">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-183">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="e1f23-184">BuildingKey</span></span> |<span data-ttu-id="e1f23-185">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-185">int</span></span> |<span data-ttu-id="e1f23-186">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-186">No</span></span> |<span data-ttu-id="e1f23-187">CqdBuilding 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="e1f23-187">Primary key for the CqdBuilding table.</span></span> |
|<span data-ttu-id="e1f23-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="e1f23-188">BuildingName</span></span> |<span data-ttu-id="e1f23-189">Varchar （80）</span><span class="sxs-lookup"><span data-stu-id="e1f23-189">varchar(80)</span></span> |<span data-ttu-id="e1f23-190">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-190">No</span></span> |<span data-ttu-id="e1f23-191">建築物名稱。</span><span class="sxs-lookup"><span data-stu-id="e1f23-191">Building name.</span></span> |
|<span data-ttu-id="e1f23-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="e1f23-192">BuildingShortName</span></span> |<span data-ttu-id="e1f23-193">Varchar （10）</span><span class="sxs-lookup"><span data-stu-id="e1f23-193">varchar(10)</span></span> |<span data-ttu-id="e1f23-194">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-194">No</span></span> |<span data-ttu-id="e1f23-195">[建築物名稱] 的較短版本。</span><span class="sxs-lookup"><span data-stu-id="e1f23-195">Shorter version of the Building name.</span></span> |
|<span data-ttu-id="e1f23-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="e1f23-196">OwnershipTypeId</span></span> |<span data-ttu-id="e1f23-197">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-197">int</span></span> |<span data-ttu-id="e1f23-198">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-198">No</span></span> |<span data-ttu-id="e1f23-199">外鍵，與 CqdBuildingOwners 資料表中的其中一個專案相符。</span><span class="sxs-lookup"><span data-stu-id="e1f23-199">Foreign key, matches one of the entries in the CqdBuildingOwners table.</span></span> |
|<span data-ttu-id="e1f23-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="e1f23-200">BuildingTypeId</span></span> |<span data-ttu-id="e1f23-201">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-201">int</span></span> |<span data-ttu-id="e1f23-202">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-202">No</span></span> |<span data-ttu-id="e1f23-203">外鍵，與 CqdBuildingType 資料表中的其中一個專案相符。</span><span class="sxs-lookup"><span data-stu-id="e1f23-203">Foreign key, matches one of the entries in the CqdBuildingType table.</span></span> |
|<span data-ttu-id="e1f23-204">款</span><span class="sxs-lookup"><span data-stu-id="e1f23-204">Latitude</span></span> |<span data-ttu-id="e1f23-205">浮</span><span class="sxs-lookup"><span data-stu-id="e1f23-205">float</span></span> |<span data-ttu-id="e1f23-206">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-206">Yes</span></span> |<span data-ttu-id="e1f23-207">建築物的緯度。</span><span class="sxs-lookup"><span data-stu-id="e1f23-207">Latitude of the building.</span></span> |
|<span data-ttu-id="e1f23-208">經度</span><span class="sxs-lookup"><span data-stu-id="e1f23-208">Longitude</span></span> |<span data-ttu-id="e1f23-209">浮</span><span class="sxs-lookup"><span data-stu-id="e1f23-209">float</span></span> |<span data-ttu-id="e1f23-210">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-210">Yes</span></span> |<span data-ttu-id="e1f23-211">建築物的經度。</span><span class="sxs-lookup"><span data-stu-id="e1f23-211">Longitude of the building.</span></span> |
|<span data-ttu-id="e1f23-212">CityName</span><span class="sxs-lookup"><span data-stu-id="e1f23-212">CityName</span></span> |<span data-ttu-id="e1f23-213">Varchar （30）</span><span class="sxs-lookup"><span data-stu-id="e1f23-213">varchar(30)</span></span> |<span data-ttu-id="e1f23-214">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-214">Yes</span></span> |<span data-ttu-id="e1f23-215">建築物所在的市/縣名。</span><span class="sxs-lookup"><span data-stu-id="e1f23-215">City name where the building is located.</span></span> |
|<span data-ttu-id="e1f23-216">郵遞區號</span><span class="sxs-lookup"><span data-stu-id="e1f23-216">ZipCode</span></span> |<span data-ttu-id="e1f23-217">Varchar （25）</span><span class="sxs-lookup"><span data-stu-id="e1f23-217">varchar(25)</span></span> |<span data-ttu-id="e1f23-218">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-218">Yes</span></span> |<span data-ttu-id="e1f23-219">組建所在的郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="e1f23-219">Zip code where the building is located.</span></span> |
|<span data-ttu-id="e1f23-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="e1f23-220">CountryShortCode</span></span> |<span data-ttu-id="e1f23-221">Varchar （2）</span><span class="sxs-lookup"><span data-stu-id="e1f23-221">varchar(2)</span></span> |<span data-ttu-id="e1f23-222">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-222">Yes</span></span> |<span data-ttu-id="e1f23-223">組建所在國家/地區的 ISO 3166-1 字母2代碼。</span><span class="sxs-lookup"><span data-stu-id="e1f23-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span> |
|<span data-ttu-id="e1f23-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="e1f23-224">StateProvinceCode</span></span> |<span data-ttu-id="e1f23-225">Varchar （3）</span><span class="sxs-lookup"><span data-stu-id="e1f23-225">varchar(3)</span></span> |<span data-ttu-id="e1f23-226">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-226">Yes</span></span> |<span data-ttu-id="e1f23-227">建築物所在之州/省的三個字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="e1f23-227">Three-letter abbreviation for the State/Province where the building is located.</span></span> |
|<span data-ttu-id="e1f23-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="e1f23-228">InsideCorp</span></span> |<span data-ttu-id="e1f23-229">稍微</span><span class="sxs-lookup"><span data-stu-id="e1f23-229">bit</span></span> |<span data-ttu-id="e1f23-230">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-230">Yes</span></span> |<span data-ttu-id="e1f23-231">[位] 表示該組建是否為商業網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="e1f23-231">Bit indicates whether the building is part of the corporate network.</span></span> |
|<span data-ttu-id="e1f23-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="e1f23-232">BuildingOfficeType</span></span> |<span data-ttu-id="e1f23-233">Nvarchar （150）</span><span class="sxs-lookup"><span data-stu-id="e1f23-233">nvarchar(150)</span></span> |<span data-ttu-id="e1f23-234">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-234">Yes</span></span> |<span data-ttu-id="e1f23-235">建立 office 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="e1f23-235">Description of the building office type.</span></span> |
|<span data-ttu-id="e1f23-236">國家</span><span class="sxs-lookup"><span data-stu-id="e1f23-236">Region</span></span> |<span data-ttu-id="e1f23-237">Varchar （25）</span><span class="sxs-lookup"><span data-stu-id="e1f23-237">varchar(25)</span></span> |<span data-ttu-id="e1f23-238">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-238">Yes</span></span> |<span data-ttu-id="e1f23-239">組建所在的地區。</span><span class="sxs-lookup"><span data-stu-id="e1f23-239">Region where the building is located.</span></span> |
|||||

<span data-ttu-id="e1f23-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="e1f23-240">**CqdNetwork**</span></span>

|<span data-ttu-id="e1f23-241">左欄</span><span class="sxs-lookup"><span data-stu-id="e1f23-241">Column</span></span>|<span data-ttu-id="e1f23-242">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1f23-242">Data Type</span></span>|<span data-ttu-id="e1f23-243">允許 Null 嗎？</span><span class="sxs-lookup"><span data-stu-id="e1f23-243">Allow Nulls?</span></span>|<span data-ttu-id="e1f23-244">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-244">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-245">局域網</span><span class="sxs-lookup"><span data-stu-id="e1f23-245">Network</span></span> |<span data-ttu-id="e1f23-246">Varchar （25）</span><span class="sxs-lookup"><span data-stu-id="e1f23-246">varchar(25)</span></span> |<span data-ttu-id="e1f23-247">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-247">No</span></span> |<span data-ttu-id="e1f23-248">子網位址。</span><span class="sxs-lookup"><span data-stu-id="e1f23-248">Subnet address.</span></span> |
|<span data-ttu-id="e1f23-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="e1f23-249">NetworkRange</span></span> |<span data-ttu-id="e1f23-250">Tinyint</span><span class="sxs-lookup"><span data-stu-id="e1f23-250">tinyint</span></span> |<span data-ttu-id="e1f23-251">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-251">Yes</span></span> |<span data-ttu-id="e1f23-252">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="e1f23-252">Subnet mask.</span></span> |
|<span data-ttu-id="e1f23-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="e1f23-253">NetworkNameID</span></span> |<span data-ttu-id="e1f23-254">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-254">int</span></span> |<span data-ttu-id="e1f23-255">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-255">Yes</span></span> |<span data-ttu-id="e1f23-256">選擇性地對應至 CqdNetworkName 資料表中的列。</span><span class="sxs-lookup"><span data-stu-id="e1f23-256">Optionally maps to a row in CqdNetworkName table.</span></span> |
|<span data-ttu-id="e1f23-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="e1f23-257">BuildingKey</span></span> |<span data-ttu-id="e1f23-258">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-258">int</span></span> |<span data-ttu-id="e1f23-259">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-259">Yes</span></span> |<span data-ttu-id="e1f23-260">外鍵，與 CqdBuilding 資料表中的其中一個專案相符。</span><span class="sxs-lookup"><span data-stu-id="e1f23-260">Foreign key, matches one of the entries in the CqdBuilding table.</span></span> |
|<span data-ttu-id="e1f23-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="e1f23-261">UpdatedDate</span></span> |<span data-ttu-id="e1f23-262">datetime</span><span class="sxs-lookup"><span data-stu-id="e1f23-262">datetime</span></span> |<span data-ttu-id="e1f23-263">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-263">No</span></span> |<span data-ttu-id="e1f23-264">上次更新專案的日期時間。</span><span class="sxs-lookup"><span data-stu-id="e1f23-264">Datetime for when the entry was last updated.</span></span> |
||||||

<span data-ttu-id="e1f23-265">根據預設，下一個資料表有一個專案（0，"Unknown"）。</span><span class="sxs-lookup"><span data-stu-id="e1f23-265">By default this next table has one entry (0, 'Unknown').</span></span>

<span data-ttu-id="e1f23-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="e1f23-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="e1f23-267">左欄</span><span class="sxs-lookup"><span data-stu-id="e1f23-267">Column</span></span>|<span data-ttu-id="e1f23-268">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1f23-268">Data Type</span></span>|<span data-ttu-id="e1f23-269">允許 Null 嗎？</span><span class="sxs-lookup"><span data-stu-id="e1f23-269">Allow Nulls?</span></span>|<span data-ttu-id="e1f23-270">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-270">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="e1f23-271">BuildingTypeId</span></span> |<span data-ttu-id="e1f23-272">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-272">int</span></span> |<span data-ttu-id="e1f23-273">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-273">No</span></span> |<span data-ttu-id="e1f23-274">CqdBuildingType 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="e1f23-274">Primary key for the CqdBuildingType table.</span></span> |
|<span data-ttu-id="e1f23-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="e1f23-275">BuildingTypeDesc</span></span> |<span data-ttu-id="e1f23-276">char （18）</span><span class="sxs-lookup"><span data-stu-id="e1f23-276">char(18)</span></span> |<span data-ttu-id="e1f23-277">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-277">No</span></span> |<span data-ttu-id="e1f23-278">[建築物類型描述]。</span><span class="sxs-lookup"><span data-stu-id="e1f23-278">Building type description.</span></span> |
|||||

<span data-ttu-id="e1f23-279">根據預設，下一個資料表有一個專案（0，"Unknown"，0，null）。</span><span class="sxs-lookup"><span data-stu-id="e1f23-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="e1f23-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="e1f23-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="e1f23-281">左欄</span><span class="sxs-lookup"><span data-stu-id="e1f23-281">Column</span></span>|<span data-ttu-id="e1f23-282">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1f23-282">Data Type</span></span>|<span data-ttu-id="e1f23-283">允許 Null 嗎？</span><span class="sxs-lookup"><span data-stu-id="e1f23-283">Allow Nulls?</span></span>|<span data-ttu-id="e1f23-284">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-284">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="e1f23-285">OwnershipTypeId</span></span> |<span data-ttu-id="e1f23-286">int</span><span class="sxs-lookup"><span data-stu-id="e1f23-286">int</span></span> |<span data-ttu-id="e1f23-287">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-287">No</span></span> |<span data-ttu-id="e1f23-288">CqdBuildingOwnershipType 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="e1f23-288">Primary key for the CqdBuildingOwnershipType table.</span></span> |
|<span data-ttu-id="e1f23-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="e1f23-289">OwnershipTypeDesc</span></span> |<span data-ttu-id="e1f23-290">Varchar （25）</span><span class="sxs-lookup"><span data-stu-id="e1f23-290">varchar(25)</span></span> |<span data-ttu-id="e1f23-291">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-291">No</span></span> |<span data-ttu-id="e1f23-292">擁有權類型描述。</span><span class="sxs-lookup"><span data-stu-id="e1f23-292">Ownership type description.</span></span> |
|<span data-ttu-id="e1f23-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="e1f23-293">LeaseInd</span></span> |<span data-ttu-id="e1f23-294">Tinyint</span><span class="sxs-lookup"><span data-stu-id="e1f23-294">tinyint</span></span> |<span data-ttu-id="e1f23-295">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-295">Yes</span></span> |<span data-ttu-id="e1f23-296">參照 CqdBuildingOwnershipType 資料表中另一列的索引，用於識別租的建築物。</span><span class="sxs-lookup"><span data-stu-id="e1f23-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span> |
|<span data-ttu-id="e1f23-297">擁有者</span><span class="sxs-lookup"><span data-stu-id="e1f23-297">Owner</span></span> |<span data-ttu-id="e1f23-298">Varchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1f23-298">varchar(50)</span></span> |<span data-ttu-id="e1f23-299">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-299">Yes</span></span> |<span data-ttu-id="e1f23-300">建立擁有者。</span><span class="sxs-lookup"><span data-stu-id="e1f23-300">Building owner.</span></span> |
|||||

<span data-ttu-id="e1f23-301">根據預設，下一個資料表有一個專案（0，"Unknown"，0，null）。</span><span class="sxs-lookup"><span data-stu-id="e1f23-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="e1f23-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="e1f23-302">**CqdBssid**</span></span>

|<span data-ttu-id="e1f23-303">左欄</span><span class="sxs-lookup"><span data-stu-id="e1f23-303">Column</span></span>|<span data-ttu-id="e1f23-304">資料類型</span><span class="sxs-lookup"><span data-stu-id="e1f23-304">Data Type</span></span>|<span data-ttu-id="e1f23-305">允許 Null 嗎？</span><span class="sxs-lookup"><span data-stu-id="e1f23-305">Allow Nulls?</span></span>|<span data-ttu-id="e1f23-306">詳細資料</span><span class="sxs-lookup"><span data-stu-id="e1f23-306">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-307">面臨</span><span class="sxs-lookup"><span data-stu-id="e1f23-307">bss</span></span> |<span data-ttu-id="e1f23-308">Nvarchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1f23-308">nvarchar(50)</span></span> |<span data-ttu-id="e1f23-309">不</span><span class="sxs-lookup"><span data-stu-id="e1f23-309">No</span></span> |<span data-ttu-id="e1f23-310">CqdBssid 資料表的主鍵。</span><span class="sxs-lookup"><span data-stu-id="e1f23-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="e1f23-311">是 WiFi 存取點的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="e1f23-311">Is the BSSID of the WiFi Access Point.</span></span> |
|<span data-ttu-id="e1f23-312">員工</span><span class="sxs-lookup"><span data-stu-id="e1f23-312">ess</span></span> |<span data-ttu-id="e1f23-313">Nvarchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1f23-313">nvarchar(50)</span></span> |<span data-ttu-id="e1f23-314">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-314">Yes</span></span> |<span data-ttu-id="e1f23-315">Wifi 存取點控制器資訊。</span><span class="sxs-lookup"><span data-stu-id="e1f23-315">Wifi Access Point Controller information.</span></span> |
|<span data-ttu-id="e1f23-316">phy</span><span class="sxs-lookup"><span data-stu-id="e1f23-316">phy</span></span> |<span data-ttu-id="e1f23-317">Nvarchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1f23-317">nvarchar(50)</span></span> |<span data-ttu-id="e1f23-318">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-318">Yes</span></span> |<span data-ttu-id="e1f23-319">Phy 資訊。</span><span class="sxs-lookup"><span data-stu-id="e1f23-319">Phy information.</span></span> |
|<span data-ttu-id="e1f23-320">應付</span><span class="sxs-lookup"><span data-stu-id="e1f23-320">ap</span></span> |<span data-ttu-id="e1f23-321">Nvarchar （50）</span><span class="sxs-lookup"><span data-stu-id="e1f23-321">nvarchar(50)</span></span> |<span data-ttu-id="e1f23-322">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-322">Yes</span></span> |<span data-ttu-id="e1f23-323">Wifi 存取點名稱。</span><span class="sxs-lookup"><span data-stu-id="e1f23-323">Wifi Access Point Name.</span></span> |
|<span data-ttu-id="e1f23-324">創建</span><span class="sxs-lookup"><span data-stu-id="e1f23-324">Building</span></span> |<span data-ttu-id="e1f23-325">Nvarchar （500）</span><span class="sxs-lookup"><span data-stu-id="e1f23-325">nvarchar(500)</span></span> |<span data-ttu-id="e1f23-326">是的</span><span class="sxs-lookup"><span data-stu-id="e1f23-326">Yes</span></span> |<span data-ttu-id="e1f23-327">WiFi 存取點所在的建築物名稱。</span><span class="sxs-lookup"><span data-stu-id="e1f23-327">The Building Name the WiFi Access Point is located in.</span></span> |
||||

## <a name="cqd-streams"></a><span data-ttu-id="e1f23-328">CQD 串流</span><span class="sxs-lookup"><span data-stu-id="e1f23-328">CQD Streams</span></span>

<span data-ttu-id="e1f23-329">CQD 串流被認為是良好、較差或未分類。</span><span class="sxs-lookup"><span data-stu-id="e1f23-329">A CQD stream is considered good, poor, or unclassified.</span></span> <span data-ttu-id="e1f23-330">CQM 1.5 現在使用下列 CQD 定義：</span><span class="sxs-lookup"><span data-stu-id="e1f23-330">CQM 1.5 now uses the following CQD definition:</span></span>

- <span data-ttu-id="e1f23-331">不良的資料流程是不太穩定的呼叫指標的任何組合。</span><span class="sxs-lookup"><span data-stu-id="e1f23-331">A poor stream is any combination of the poor call metrics beyond threshold.</span></span>
- <span data-ttu-id="e1f23-332">當通話中的一個資料流程不佳時，兩個通話串流都會標示為不佳。</span><span class="sxs-lookup"><span data-stu-id="e1f23-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="e1f23-333">在會議中，每個參與者都會算作唯一通話，而且會與其他人獨立報告。</span><span class="sxs-lookup"><span data-stu-id="e1f23-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
- <span data-ttu-id="e1f23-334">未分類的資料流程是不含品質標準（也就是綜合交易或短通話）的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e1f23-334">Unclassified streams are streams without quality metrics (that is, Synthetic Transactions or short calls).</span></span>
- <span data-ttu-id="e1f23-335">有效的資料流程 = 非行動用戶端</span><span class="sxs-lookup"><span data-stu-id="e1f23-335">Valid Streams = non-mobile clients</span></span>
- <span data-ttu-id="e1f23-336">無法修改分類器</span><span class="sxs-lookup"><span data-stu-id="e1f23-336">Classifier cannot be modified</span></span>

<span data-ttu-id="e1f23-337">**較差的通話定義/分類器**</span><span class="sxs-lookup"><span data-stu-id="e1f23-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="e1f23-338">衡量</span><span class="sxs-lookup"><span data-stu-id="e1f23-338">Metric</span></span>|<span data-ttu-id="e1f23-339">閾值</span><span class="sxs-lookup"><span data-stu-id="e1f23-339">Threshold</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1f23-340">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="e1f23-340">DegradationAvg</span></span> |<span data-ttu-id="e1f23-341">大於1.0 （-1 網路 MOS）</span><span class="sxs-lookup"><span data-stu-id="e1f23-341">Greater than 1.0 (-1 network MOS)</span></span> |
|<span data-ttu-id="e1f23-342">環路</span><span class="sxs-lookup"><span data-stu-id="e1f23-342">RoundTrip</span></span> |<span data-ttu-id="e1f23-343">大於500</span><span class="sxs-lookup"><span data-stu-id="e1f23-343">Greater than 500</span></span> |
|<span data-ttu-id="e1f23-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e1f23-344">PacketLossRate</span></span> |<span data-ttu-id="e1f23-345">大於0.1 （10%）</span><span class="sxs-lookup"><span data-stu-id="e1f23-345">Greater than 0.1 (10%)</span></span> |
|<span data-ttu-id="e1f23-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e1f23-346">JitterInterArrival</span></span> |<span data-ttu-id="e1f23-347">超過30</span><span class="sxs-lookup"><span data-stu-id="e1f23-347">Greater than 30</span></span> |
|<span data-ttu-id="e1f23-348">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e1f23-348">RatioConcealedSamplesAvg</span></span> |<span data-ttu-id="e1f23-349">大於0.07</span><span class="sxs-lookup"><span data-stu-id="e1f23-349">Greater than 0.07</span></span> |
|||

<span data-ttu-id="e1f23-350">JPDR definition = 差的通話定義減去 RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e1f23-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span>

## <a name="where-is-callercallee"></a><span data-ttu-id="e1f23-351">來電者/被叫方的位置為何？</span><span class="sxs-lookup"><span data-stu-id="e1f23-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="e1f23-352">CQD 不使用 [來電者/被叫獲方程式] 欄位，而是使用 "First" 和 "Second"，因為來電者與被叫方之間有中間個步驟。</span><span class="sxs-lookup"><span data-stu-id="e1f23-352">CQD doesn't use Caller/Callee fields, instead it uses "First" and "Second" because there are intervening steps between the caller and callee.</span></span>

 <span data-ttu-id="e1f23-353">**首先**如果資料流程中包含伺服器，則會一直是伺服器端點（例如，AV MCU 或轉送伺服器）。</span><span class="sxs-lookup"><span data-stu-id="e1f23-353">**First** Will always be the Server endpoint (for example, AV MCU or Mediation Server) if a Server is involved in the stream.</span></span>

 <span data-ttu-id="e1f23-354">**秒**除非是伺服器-伺服器資料流程，否則將永遠是用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="e1f23-354">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>

<span data-ttu-id="e1f23-355">**第一和第二個分類範例**</span><span class="sxs-lookup"><span data-stu-id="e1f23-355">**Example of First and Second classification**</span></span>

|<span data-ttu-id="e1f23-356">端點 1 UAType</span><span class="sxs-lookup"><span data-stu-id="e1f23-356">Endpoint 1 UAType</span></span>|<span data-ttu-id="e1f23-357">端點 2 UUAType</span><span class="sxs-lookup"><span data-stu-id="e1f23-357">Endpoint 2 UUAType</span></span>|<span data-ttu-id="e1f23-358">一</span><span class="sxs-lookup"><span data-stu-id="e1f23-358">First</span></span>|<span data-ttu-id="e1f23-359">第二個</span><span class="sxs-lookup"><span data-stu-id="e1f23-359">Second</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e1f23-360">2（AVMCU）</span><span class="sxs-lookup"><span data-stu-id="e1f23-360">2 (AVMCU)</span></span> |<span data-ttu-id="e1f23-361">4（商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="e1f23-361">4 (Skype for Business)</span></span> |<span data-ttu-id="e1f23-362">端點1</span><span class="sxs-lookup"><span data-stu-id="e1f23-362">Endpoint 1</span></span> |<span data-ttu-id="e1f23-363">端點2</span><span class="sxs-lookup"><span data-stu-id="e1f23-363">Endpoint 2</span></span> |
|<span data-ttu-id="e1f23-364">2（AVMCU）</span><span class="sxs-lookup"><span data-stu-id="e1f23-364">2 (AVMCU)</span></span> |<span data-ttu-id="e1f23-365">1（mMediationServer）</span><span class="sxs-lookup"><span data-stu-id="e1f23-365">1 (mMediationServer)</span></span> |<span data-ttu-id="e1f23-366">端點2</span><span class="sxs-lookup"><span data-stu-id="e1f23-366">Endpoint 2</span></span> |<span data-ttu-id="e1f23-367">端點1</span><span class="sxs-lookup"><span data-stu-id="e1f23-367">Endpoint 1</span></span> |
|<span data-ttu-id="e1f23-368">4（商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="e1f23-368">4 (Skype for Business)</span></span> |<span data-ttu-id="e1f23-369">4（商務用 Skype）</span><span class="sxs-lookup"><span data-stu-id="e1f23-369">4 (Skype for Business)</span></span> |<span data-ttu-id="e1f23-370">MediaLine 中的來電者</span><span class="sxs-lookup"><span data-stu-id="e1f23-370">The Caller in MediaLine</span></span> |<span data-ttu-id="e1f23-371">MMediaLine 中的被呼叫者</span><span class="sxs-lookup"><span data-stu-id="e1f23-371">The Callee in MMediaLine</span></span> |
|||||

<span data-ttu-id="e1f23-372">如果兩個端點都是相同的類型，CQD 會先進行呼叫者輸入，然後再撥被叫方。</span><span class="sxs-lookup"><span data-stu-id="e1f23-372">If both endpoints are the same type, CQD makes the Caller entry First and the Callee Second.</span></span> <span data-ttu-id="e1f23-373">如需有關端點名稱的詳細資訊，請參閱[此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e1f23-373">For more information about endpoint names, see [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).</span></span>

## <a name="accounting-for-vpn"></a><span data-ttu-id="e1f23-374">VPN 記帳</span><span class="sxs-lookup"><span data-stu-id="e1f23-374">Accounting for VPN</span></span>

<span data-ttu-id="e1f23-375">如果已知 VPN 解決方案能正確設定 VPN 標誌，就是一切都已設定好了。</span><span class="sxs-lookup"><span data-stu-id="e1f23-375">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="e1f23-376">否則，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="e1f23-376">Otherwise, use one of the following methods:</span></span>

- <span data-ttu-id="e1f23-377">建立名為 [VPN （慣用）] 的網路類型，然後將 VPN 子網與這個新的 VPN NetworkType。</span><span class="sxs-lookup"><span data-stu-id="e1f23-377">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
- <span data-ttu-id="e1f23-378">建立名為 [VPN] 的建築物，然後將 VPN 子網與此組建建立關聯。</span><span class="sxs-lookup"><span data-stu-id="e1f23-378">Create a building called VPN, then Associate VPN Subnets with this building.</span></span>

## <a name="query-fundamentals"></a><span data-ttu-id="e1f23-379">查詢基礎</span><span class="sxs-lookup"><span data-stu-id="e1f23-379">Query Fundamentals</span></span>

<span data-ttu-id="e1f23-380">標準格式的查詢包含下列三個參數：</span><span class="sxs-lookup"><span data-stu-id="e1f23-380">A well-formed query contains all three of these parameters:</span></span>

- <span data-ttu-id="e1f23-381">數值</span><span class="sxs-lookup"><span data-stu-id="e1f23-381">Measurement</span></span>
- <span data-ttu-id="e1f23-382">焦點</span><span class="sxs-lookup"><span data-stu-id="e1f23-382">Dimension</span></span>
- <span data-ttu-id="e1f23-383">Filter</span><span class="sxs-lookup"><span data-stu-id="e1f23-383">Filter</span></span>

<span data-ttu-id="e1f23-384">標準格式的查詢範例是「顯示我的資料流程不佳 [度量衡]：由子網 [Dimension] 用於建築物 6 [篩選]。」</span><span class="sxs-lookup"><span data-stu-id="e1f23-384">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

## <a name="what-does-union-do"></a><span data-ttu-id="e1f23-385">UNION 運算是什麼？</span><span class="sxs-lookup"><span data-stu-id="e1f23-385">What does UNION do?</span></span>

<span data-ttu-id="e1f23-386">[聯合] 可讓您使用 AND 運算子來篩選準則。</span><span class="sxs-lookup"><span data-stu-id="e1f23-386">Union allows you to filter conditions with the AND operator.</span></span> <span data-ttu-id="e1f23-387">在某些情況下，您可以將多個篩選準則結合在一起，以達到與 OR 運算類似的結果。</span><span class="sxs-lookup"><span data-stu-id="e1f23-387">There are scenarios where you can combine multiple Filter conditions together to achieve a result similar to an OR operation.</span></span>

<span data-ttu-id="e1f23-388">範例：若要從建築物取得所有資料流程，同盟會提供合併資料集的獨特視圖。</span><span class="sxs-lookup"><span data-stu-id="e1f23-388">Example: To get all streams from a building, UNION provides a distinct view of the merged dataset.</span></span> <span data-ttu-id="e1f23-389">若要使用 UNION，請在您想要合併的兩個篩選準則上，將一般文字插入聯合欄位。</span><span class="sxs-lookup"><span data-stu-id="e1f23-389">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span>

## <a name="default-report-breakdown"></a><span data-ttu-id="e1f23-390">預設報告細目</span><span class="sxs-lookup"><span data-stu-id="e1f23-390">Default Report Breakdown</span></span>

<span data-ttu-id="e1f23-391">如果是內部管理無線，您可以在 Managed bucket 中重新建立無線報告。</span><span class="sxs-lookup"><span data-stu-id="e1f23-391">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span>

![CQD 報告細目](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a><span data-ttu-id="e1f23-393">操作程式</span><span class="sxs-lookup"><span data-stu-id="e1f23-393">Operational Processes</span></span>

<span data-ttu-id="e1f23-394">先審查及修正受管理的資料流程。</span><span class="sxs-lookup"><span data-stu-id="e1f23-394">Review and remediate Managed Streams first.</span></span> <span data-ttu-id="e1f23-395">此區域中的品質應該在您的控制項內是 100%，因此最容易修正。</span><span class="sxs-lookup"><span data-stu-id="e1f23-395">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span>

### <a name="managed-streams"></a><span data-ttu-id="e1f23-396">受管理的資料流程</span><span class="sxs-lookup"><span data-stu-id="e1f23-396">Managed Streams</span></span>

<span data-ttu-id="e1f23-397">以下列順序查看及修正受管理的資料流程：</span><span class="sxs-lookup"><span data-stu-id="e1f23-397">Review and remediate managed streams in the following order:</span></span>

1. <span data-ttu-id="e1f23-398">伺服器-伺服器</span><span class="sxs-lookup"><span data-stu-id="e1f23-398">Server-Server</span></span>
2. <span data-ttu-id="e1f23-399">伺服器-內接線</span><span class="sxs-lookup"><span data-stu-id="e1f23-399">Server-Wired-Inside</span></span>
3. <span data-ttu-id="e1f23-400">有線-有線-內</span><span class="sxs-lookup"><span data-stu-id="e1f23-400">Wired-Wired-Inside</span></span>

### <a name="unmanaged-streams"></a><span data-ttu-id="e1f23-401">非託管資料流程</span><span class="sxs-lookup"><span data-stu-id="e1f23-401">Unmanaged Streams</span></span>

<span data-ttu-id="e1f23-402">以下列順序評審及修正非託管的資料流程：</span><span class="sxs-lookup"><span data-stu-id="e1f23-402">Review and remediate unmanaged streams in the following order:</span></span>

1. <span data-ttu-id="e1f23-403">伺服器-Wifi-內</span><span class="sxs-lookup"><span data-stu-id="e1f23-403">Server-Wifi-Inside</span></span>
2. <span data-ttu-id="e1f23-404">伺服器-在外-有線</span><span class="sxs-lookup"><span data-stu-id="e1f23-404">Server-Wired-Outside</span></span>
3. <span data-ttu-id="e1f23-405">伺服器-Wifi-外</span><span class="sxs-lookup"><span data-stu-id="e1f23-405">Server-Wifi-Outside</span></span>
4. <span data-ttu-id="e1f23-406">有線-直向外</span><span class="sxs-lookup"><span data-stu-id="e1f23-406">Wired-Outside-Direct</span></span>
5. <span data-ttu-id="e1f23-407">有線外部中繼</span><span class="sxs-lookup"><span data-stu-id="e1f23-407">Wired-Outside-Relay</span></span>
6. <span data-ttu-id="e1f23-408">其他未受管理</span><span class="sxs-lookup"><span data-stu-id="e1f23-408">Other Unmanaged</span></span>
