---
title: 使用商務用 Skype Server 的通話品質儀表板
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
ms.collection: IT_Skype16
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：瞭解如何使用 [通話品質] 儀表板。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: ed1e5563a4677dce33648280590530ca2a9b1b9b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803103"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a><span data-ttu-id="ce147-104">使用商務用 Skype Server 的通話品質儀表板</span><span class="sxs-lookup"><span data-stu-id="ce147-104">Use Call Quality Dashboard for Skype for Business Server</span></span>

<span data-ttu-id="ce147-105">**摘要：** 瞭解如何使用通話品質儀表板。</span><span class="sxs-lookup"><span data-stu-id="ce147-105">**Summary:** Learn about how to use the Call Quality Dashboard.</span></span> <span data-ttu-id="ce147-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="ce147-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="ce147-107">通話品質儀表板 (CQD) 可讓 IT 專業人員使用匯總資料，透過比較使用者群組的統計資料來識別產生媒體質量問題的問題，以識別趨勢和模式。</span><span class="sxs-lookup"><span data-stu-id="ce147-107">Call Quality Dashboard (CQD) allows IT Pros to use aggregate data to identify problems creating media quality issues by  comparing statistics for groups of users to identify trends and patterns.</span></span> <span data-ttu-id="ce147-108">CQD 不會專注于解決個別通話問題，但可識別適用于許多使用者的問題和解決方案。</span><span class="sxs-lookup"><span data-stu-id="ce147-108">CQD is not focused on solving individual call issues, but on identifying problems and solutions that apply to many users.</span></span>

## <a name="call-quality-dashboard-user-guide"></a><span data-ttu-id="ce147-109">通話品質儀表板使用者指南</span><span class="sxs-lookup"><span data-stu-id="ce147-109">Call Quality Dashboard User Guide</span></span>

<span data-ttu-id="ce147-110">CQD 是一種網頁入口網站，可根據經驗品質 (QoE) 資料，快速建立及組織報表。</span><span class="sxs-lookup"><span data-stu-id="ce147-110">CQD is a web portal for quickly creating and organizing reports based on Quality of Experience (QoE) data.</span></span> <span data-ttu-id="ce147-111">CQD 會部署一個 SSAS cube，以匯總 QoE 度量資料庫中的資料，並可讓系統管理員即時建立及修改報告或進行調查。</span><span class="sxs-lookup"><span data-stu-id="ce147-111">CQD deploys an SSAS cube to aggregate the data in the QoE Metrics database, and enables admins to create and modify reports or do investigations in real time.</span></span> <span data-ttu-id="ce147-112">雖然您可以使用 Excel 直接連線到 cube，但已針對包含 QoE 資料的數個工作流程優化入口網站。</span><span class="sxs-lookup"><span data-stu-id="ce147-112">While it is possible to use Excel to connect directly to the cube, the portal is optimized for several workflows involving QoE data.</span></span> <span data-ttu-id="ce147-113">資料包括：</span><span class="sxs-lookup"><span data-stu-id="ce147-113">The data includes:</span></span>

- <span data-ttu-id="ce147-114">快速存取的快取報告資料</span><span class="sxs-lookup"><span data-stu-id="ce147-114">Cached report data for fast access</span></span>
- <span data-ttu-id="ce147-115">資訊共用及發佈的報告頁面深層連結</span><span class="sxs-lookup"><span data-stu-id="ce147-115">Deep links to report pages for information sharing and publishing</span></span>
- <span data-ttu-id="ce147-116">簡化的報表編輯和建立，以及報表描述的可編輯中繼資料。</span><span class="sxs-lookup"><span data-stu-id="ce147-116">Streamlined report editing and creation, and editable metadata for report descriptions.</span></span>

<span data-ttu-id="ce147-117">此外，CQD 會公開 web APIs，讓使用者以程式設計方式存取 cube 資料，以在自訂儀表板中使用。</span><span class="sxs-lookup"><span data-stu-id="ce147-117">Also, CQD exposes web APIs that give users programmatic access to the cube data for use in custom dashboards.</span></span>

### <a name="feature-overview"></a><span data-ttu-id="ce147-118">功能概觀</span><span class="sxs-lookup"><span data-stu-id="ce147-118">Feature Overview</span></span>

<span data-ttu-id="ce147-119">當您造訪通話品質儀表板時，您會看到下列螢幕：</span><span class="sxs-lookup"><span data-stu-id="ce147-119">When you visit the Call Quality Dashboard, you see the following screen:</span></span>

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. <span data-ttu-id="ce147-121">「摘要窗格」是指可以找到右側)  (的「報表集」內容。</span><span class="sxs-lookup"><span data-stu-id="ce147-121">The "Summary Pane" is where context for the "Report Set" (to the right) can be found.</span></span>
2. <span data-ttu-id="ce147-122">在 [摘要 PaneReport] 中按一下 [編輯]，以設定層級屬性 (包括) Y 座標軸的高度）。</span><span class="sxs-lookup"><span data-stu-id="ce147-122">Click "Edit" in the Summary PaneReport to set level properties (including Y-axis height).</span></span>
3. <span data-ttu-id="ce147-123">痕跡連結可協助您識別您目前在報表集階層內的位置。</span><span class="sxs-lookup"><span data-stu-id="ce147-123">The Breadcrumb helps you identify your current location within the report set hierarchy.</span></span>
4. <span data-ttu-id="ce147-124">含有子報表的報表會以藍色連結顯示。</span><span class="sxs-lookup"><span data-stu-id="ce147-124">Reports with subreports are shown with a blue link.</span></span> <span data-ttu-id="ce147-125">按一下連結以向下流覽至子報表。</span><span class="sxs-lookup"><span data-stu-id="ce147-125">Click the link to drill down to the child reports.</span></span>

<span data-ttu-id="ce147-126">將滑鼠移到橫條圖和趨勢線上，以顯示詳細的值。</span><span class="sxs-lookup"><span data-stu-id="ce147-126">Move the mouse over the bar charts and trend lines to show detailed values.</span></span> <span data-ttu-id="ce147-127">具有焦點的報表會顯示動作功能表：「編輯」、「克隆」、「刪除」及「下載」。</span><span class="sxs-lookup"><span data-stu-id="ce147-127">The report that has focus shows the action menu: "Edit", "Clone", "Delete", and "Download".</span></span>

### <a name="default-reports"></a><span data-ttu-id="ce147-128">預設報表</span><span class="sxs-lookup"><span data-stu-id="ce147-128">Default Reports</span></span>

<span data-ttu-id="ce147-129">當您第一次存取通話品質儀表板入口網站時，會自動建立預設的報表集。</span><span class="sxs-lookup"><span data-stu-id="ce147-129">When you first access the Call Quality Dashboard portal, a default set of reports is automatically created.</span></span> <span data-ttu-id="ce147-130">這些報告有時也稱為「系統報告」。</span><span class="sxs-lookup"><span data-stu-id="ce147-130">These reports are sometimes referred to as system reports.</span></span> <span data-ttu-id="ce147-131">您可以透過建立新的同輩和子報表，隨意修改或刪除這些報表或加以擴充。</span><span class="sxs-lookup"><span data-stu-id="ce147-131">You are able to freely modify or delete these reports or extend them by creating new sibling and child reports.</span></span>

<span data-ttu-id="ce147-132">在最上層，「音訊資料流程每月趨勢」報告會顯示所有音訊資料流程的每月趨勢。</span><span class="sxs-lookup"><span data-stu-id="ce147-132">At the top level, the "Audio Streams Monthly Trend" report shows the monthly trend for all audio streams.</span></span> <span data-ttu-id="ce147-133">將滑鼠移到柱狀圖中的橫條圖上方，以顯示柱狀圖所代表的資料更詳細的視圖。</span><span class="sxs-lookup"><span data-stu-id="ce147-133">Move the mouse over the bars in a bar chart to show a more detailed view of the data represented by the bar chart.</span></span> <span data-ttu-id="ce147-134">按一下 [音訊資料流程每月趨勢報告] 的標題，以流覽至「受管理的 vs 音訊流量」報告，該報告會在受管理和非管理的呼叫間分割。</span><span class="sxs-lookup"><span data-stu-id="ce147-134">Click the title of the Audio Streams Monthly Trend report to navigate to the "Managed vs Unmanaged Audio Streams" report, where the reports are split between Managed and Unmanaged calls.</span></span> <span data-ttu-id="ce147-135">受管理的來電是透過有線連線從公司防火牆內部撥打的電話。</span><span class="sxs-lookup"><span data-stu-id="ce147-135">Managed calls are calls made from inside the corporate firewall over wired connections.</span></span> <span data-ttu-id="ce147-136">未管理的呼叫包括從公司防火牆外撥出的電話，以及透過 Wi-Fi 所進行的所有通話。</span><span class="sxs-lookup"><span data-stu-id="ce147-136">Unmanaged calls include calls made from outside the corporate firewall and all calls made over Wi-Fi.</span></span>

<span data-ttu-id="ce147-137">其他最上層的報表稱為「使用者報告的通話品質分級長條圖」。</span><span class="sxs-lookup"><span data-stu-id="ce147-137">The other top-level report is called the "User-reported Call Quality Rating Histogram."</span></span> <span data-ttu-id="ce147-138">通話品質評級是通話結束時，商務用 Skype 使用者提供的數位，用來表示通話的品質。</span><span class="sxs-lookup"><span data-stu-id="ce147-138">Call Quality Ratings are the numbers given by Skype for Business users at the end of a call to indicate the quality of the call.</span></span> <span data-ttu-id="ce147-139">分級編號範圍介於1到5、1是最差值和5。</span><span class="sxs-lookup"><span data-stu-id="ce147-139">The rating numbers range from 1 to 5, 1 is the worst and 5 is the best.</span></span> <span data-ttu-id="ce147-140">長條圖會顯示在一個月中指定分級的音訊通話數目。</span><span class="sxs-lookup"><span data-stu-id="ce147-140">The histogram shows the number of audio calls that had the indicated rating in one month.</span></span>

<span data-ttu-id="ce147-141">按一下任何報告的標題，以流覽至資料中具有更多篩選的報表。</span><span class="sxs-lookup"><span data-stu-id="ce147-141">Click the title of any of the reports to navigate into reports with more filters on the data.</span></span> <span data-ttu-id="ce147-142">在系統報告中，每個子報表會顯示其父報表中可用的資料子集。</span><span class="sxs-lookup"><span data-stu-id="ce147-142">In the system reports, each child report displays a subset of the data available in its parent report.</span></span> <span data-ttu-id="ce147-143">解決問題的模型很簡單：調查哪個子報表會限制問題的資料或趨勢，並逐步縮小問題空間。</span><span class="sxs-lookup"><span data-stu-id="ce147-143">The problem-solving model is simple: investigate which subreport the data or trend suggesting a problem is confined to, and gradually narrow down the problem space.</span></span> <span data-ttu-id="ce147-144">建立子報表的功能可讓您針對特定資料趨勢的原因，調查您自己的猜測。</span><span class="sxs-lookup"><span data-stu-id="ce147-144">The ability to create subreports allows you to investigate your own guesses about the cause of specific data trends.</span></span>

### <a name="create-and-edit-reports"></a><span data-ttu-id="ce147-145">建立及編輯報表</span><span class="sxs-lookup"><span data-stu-id="ce147-145">Create and Edit Reports</span></span>

<span data-ttu-id="ce147-146">在報表的 [動作] 功能表中，按一下 [編輯]，以查看報告編輯器。</span><span class="sxs-lookup"><span data-stu-id="ce147-146">Click "Edit" in the action menu of a report to see the Report Editor.</span></span> <span data-ttu-id="ce147-147">查詢會將每個報告都備份到 cube。</span><span class="sxs-lookup"><span data-stu-id="ce147-147">Each report is backed by a query into the cube.</span></span> <span data-ttu-id="ce147-148">報表是指其查詢所傳回之資料的形象。</span><span class="sxs-lookup"><span data-stu-id="ce147-148">A report is a visualization of the data returned by its query.</span></span> <span data-ttu-id="ce147-149">報告編輯器可協助您編輯這些查詢以及報告的顯示選項。</span><span class="sxs-lookup"><span data-stu-id="ce147-149">The Report Editor helps you edit these queries and the display options of the report.</span></span> <span data-ttu-id="ce147-150">當您開啟報表編輯器時，您會看到：</span><span class="sxs-lookup"><span data-stu-id="ce147-150">When you open the Report Editor, you  see:</span></span>

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. <span data-ttu-id="ce147-152">在左窗格中選取維度、量值及篩選。</span><span class="sxs-lookup"><span data-stu-id="ce147-152">Dimensions, measures, and filters are chosen in the left pane.</span></span> <span data-ttu-id="ce147-153">將游標移至其中一個現有的值，以顯示允許移除值的 "x" 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ce147-153">Hover over one of the existing values to show an "x" button that allows the value to be removed.</span></span> <span data-ttu-id="ce147-154">按一下標題旁的 [加號] 按鈕，開啟可以新增維度、量值或篩選的對話方塊。</span><span class="sxs-lookup"><span data-stu-id="ce147-154">Click the "plus" button next to a heading to open the dialog where you can add a new dimension, measure, or filter.</span></span>
2. <span data-ttu-id="ce147-155">圖表自訂的選項會顯示在頂端。</span><span class="sxs-lookup"><span data-stu-id="ce147-155">Options for chart customization are displayed at the top.</span></span>
3. <span data-ttu-id="ce147-156">報表的預覽會出現在報表編輯器中。</span><span class="sxs-lookup"><span data-stu-id="ce147-156">A preview of the report is available in the Report Editor.</span></span>
4. <span data-ttu-id="ce147-157">您可以使用底部的 [編輯] 方塊來建立詳細的報告描述。</span><span class="sxs-lookup"><span data-stu-id="ce147-157">A detailed report description can be created with the edit box at the bottom.</span></span>

### <a name="sparklines-in-tables"></a><span data-ttu-id="ce147-158">表格中的走勢圖表</span><span class="sxs-lookup"><span data-stu-id="ce147-158">Sparklines in Tables</span></span>

<span data-ttu-id="ce147-159">當 StartDate 的 Month 新增為維度，而且資料在表格表單中呈現為趨勢時，橫條圖和走勢圖會顯示在表格儲存格內。</span><span class="sxs-lookup"><span data-stu-id="ce147-159">When StartDate.Month is added as a dimension and the data is rendered as a trend in table form, bar charts and sparklines can be shown inside the table cells.</span></span> <span data-ttu-id="ce147-160">將滑鼠指標移到長條圖和走勢圖上方，以顯示個別月的值。</span><span class="sxs-lookup"><span data-stu-id="ce147-160">Move the mouse pointer over the bar chart and the sparklines to show the values for individual months.</span></span>

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

<span data-ttu-id="ce147-162">為了顯示長條圖及顯示的走勢圖，必須勾選報表編輯器頂端的 [顯示股價] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="ce147-162">In order for the bar charts and the sparklines to appear, the "Show sparklines" checkbox at the top of the Report Editor must be checked.</span></span> <span data-ttu-id="ce147-163">這會選取 [趨勢] 選項，並將 Month 移至最後一個維度，也可以透過按一下 [月]，然後使用向上鍵和向下鍵來移動 StartDate。上移或下移月。</span><span class="sxs-lookup"><span data-stu-id="ce147-163">This selects the Trend option and moves Month down to be the last dimension, which can also be accomplished by clicking on Month and using the up and down arrows to shift StartDate.Month up or down.</span></span>

### <a name="settings"></a><span data-ttu-id="ce147-164">設定</span><span class="sxs-lookup"><span data-stu-id="ce147-164">Settings</span></span>

<span data-ttu-id="ce147-165">[設定] 功能表包含有用頁面的連結，例如「系統健康情況」和「關於頁面」，而且位於儀表板的右上角。</span><span class="sxs-lookup"><span data-stu-id="ce147-165">The settings menu contains links to useful pages like the System Health and About pages, and is located in the top-right corner of the dashboard.</span></span>

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

<span data-ttu-id="ce147-167">是否顯示描述和時間戳記是由個別使用者所決定，而且這些設定只會影響儀表板的個別版本，不會修改報告集或其他使用者看到的內容。</span><span class="sxs-lookup"><span data-stu-id="ce147-167">Whether to show descriptions and time stamps is up to individual users, and these settings only affect the individual's version of the dashboard, and do not modify the report set or what other users see.</span></span> <span data-ttu-id="ce147-168">清除快取會使所有查詢從 cube 重新載入其資料，而還原預設值會刪除所有使用者建立或修改的報表，並重新建立系統報告集（使用者在第一次登入時會看到哪些專案）。</span><span class="sxs-lookup"><span data-stu-id="ce147-168">Clearing the cache causes all queries to reload their data from the cube, while restoring defaults deletes all of user-created or modified reports and recreates the system report set — what a user would see when they log in for the first time.</span></span>

<span data-ttu-id="ce147-169">[使用者] 儀表板連結會顯示使用者可以在其中查看 CQD 之其他使用者的頁面，並流覽其報表。</span><span class="sxs-lookup"><span data-stu-id="ce147-169">The Users Dashboard Link shows a page where users can view other users of CQD and browse their reports.</span></span> <span data-ttu-id="ce147-170">若要共用報表集，請複製 URL 欄中的連結，並與其他 CQD 使用者共用。</span><span class="sxs-lookup"><span data-stu-id="ce147-170">To share a report set, copy the link in the URL bar and share it with another CQD user.</span></span> <span data-ttu-id="ce147-171">此連結是在使用者的使用者名稱下，其他使用者會在 [使用者儀表板連結] 頁面上看到的連結。</span><span class="sxs-lookup"><span data-stu-id="ce147-171">This link is the same link other users would see in the Users Dashboard Link page under the user's username.</span></span>

### <a name="supplying-subnet-information"></a><span data-ttu-id="ce147-172">提供子網資訊</span><span class="sxs-lookup"><span data-stu-id="ce147-172">Supplying Subnet Information</span></span>

<span data-ttu-id="ce147-173">如果在封存資料庫中輸入網站特有的資訊，以提供子網對大樓對應資訊，則可能會顯示其他資訊 (例如，透過建立) 的有線/無線通話品質。</span><span class="sxs-lookup"><span data-stu-id="ce147-173">Additional information can be revealed if site-specific information is entered into the Archive database to provide subnet-to-building mapping information (for example, wired/wireless call quality by building).</span></span>

<span data-ttu-id="ce147-174">請至少完成下清單格，以建立這些報告：</span><span class="sxs-lookup"><span data-stu-id="ce147-174">At a minimum, complete the following tables to create these reports:</span></span>

- <span data-ttu-id="ce147-175">CqdBuilding</span><span class="sxs-lookup"><span data-stu-id="ce147-175">CqdBuilding</span></span>
- <span data-ttu-id="ce147-176">CqdNetwork</span><span class="sxs-lookup"><span data-stu-id="ce147-176">CqdNetwork</span></span>

<span data-ttu-id="ce147-177">您可以在 CqdBuildingType 和 CqdBuildingOwnershipType 表格中提供其他資訊，以允許進一步篩選及向下切入。</span><span class="sxs-lookup"><span data-stu-id="ce147-177">Additional information can be provided in CqdBuildingType and CqdBuildingOwnershipType tables to allow further filtering and drill-down.</span></span>

<span data-ttu-id="ce147-178">這兩個數據表所用的資料定義如下：</span><span class="sxs-lookup"><span data-stu-id="ce147-178">The data used for these tables are defined as follows:</span></span>

<span data-ttu-id="ce147-179">**CqdBuilding**</span><span class="sxs-lookup"><span data-stu-id="ce147-179">**CqdBuilding**</span></span>

|<span data-ttu-id="ce147-180">欄</span><span class="sxs-lookup"><span data-stu-id="ce147-180">Column</span></span>|<span data-ttu-id="ce147-181">資料類型</span><span class="sxs-lookup"><span data-stu-id="ce147-181">Data Type</span></span>|<span data-ttu-id="ce147-182">允許 Null？</span><span class="sxs-lookup"><span data-stu-id="ce147-182">Allow Nulls?</span></span>|<span data-ttu-id="ce147-183">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce147-183">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-184">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="ce147-184">BuildingKey</span></span> |<span data-ttu-id="ce147-185">int</span><span class="sxs-lookup"><span data-stu-id="ce147-185">int</span></span> |<span data-ttu-id="ce147-186">否</span><span class="sxs-lookup"><span data-stu-id="ce147-186">No</span></span> |<span data-ttu-id="ce147-187">CqdBuilding 表格的主鍵。</span><span class="sxs-lookup"><span data-stu-id="ce147-187">Primary key for the CqdBuilding table.</span></span> |
|<span data-ttu-id="ce147-188">BuildingName</span><span class="sxs-lookup"><span data-stu-id="ce147-188">BuildingName</span></span> |<span data-ttu-id="ce147-189">Varchar (80) </span><span class="sxs-lookup"><span data-stu-id="ce147-189">varchar(80)</span></span> |<span data-ttu-id="ce147-190">否</span><span class="sxs-lookup"><span data-stu-id="ce147-190">No</span></span> |<span data-ttu-id="ce147-191">大樓名稱。</span><span class="sxs-lookup"><span data-stu-id="ce147-191">Building name.</span></span> |
|<span data-ttu-id="ce147-192">BuildingShortName</span><span class="sxs-lookup"><span data-stu-id="ce147-192">BuildingShortName</span></span> |<span data-ttu-id="ce147-193">Varchar (10) </span><span class="sxs-lookup"><span data-stu-id="ce147-193">varchar(10)</span></span> |<span data-ttu-id="ce147-194">否</span><span class="sxs-lookup"><span data-stu-id="ce147-194">No</span></span> |<span data-ttu-id="ce147-195">較短的大樓名稱版本。</span><span class="sxs-lookup"><span data-stu-id="ce147-195">Shorter version of the Building name.</span></span> |
|<span data-ttu-id="ce147-196">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="ce147-196">OwnershipTypeId</span></span> |<span data-ttu-id="ce147-197">int</span><span class="sxs-lookup"><span data-stu-id="ce147-197">int</span></span> |<span data-ttu-id="ce147-198">否</span><span class="sxs-lookup"><span data-stu-id="ce147-198">No</span></span> |<span data-ttu-id="ce147-199">外鍵，符合 CqdBuildingOwners 表格中的其中一個專案。</span><span class="sxs-lookup"><span data-stu-id="ce147-199">Foreign key, matches one of the entries in the CqdBuildingOwners table.</span></span> |
|<span data-ttu-id="ce147-200">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="ce147-200">BuildingTypeId</span></span> |<span data-ttu-id="ce147-201">int</span><span class="sxs-lookup"><span data-stu-id="ce147-201">int</span></span> |<span data-ttu-id="ce147-202">否</span><span class="sxs-lookup"><span data-stu-id="ce147-202">No</span></span> |<span data-ttu-id="ce147-203">外鍵，符合 CqdBuildingType 表格中的其中一個專案。</span><span class="sxs-lookup"><span data-stu-id="ce147-203">Foreign key, matches one of the entries in the CqdBuildingType table.</span></span> |
|<span data-ttu-id="ce147-204">緯度</span><span class="sxs-lookup"><span data-stu-id="ce147-204">Latitude</span></span> |<span data-ttu-id="ce147-205">float</span><span class="sxs-lookup"><span data-stu-id="ce147-205">float</span></span> |<span data-ttu-id="ce147-206">是</span><span class="sxs-lookup"><span data-stu-id="ce147-206">Yes</span></span> |<span data-ttu-id="ce147-207">大樓的緯度。</span><span class="sxs-lookup"><span data-stu-id="ce147-207">Latitude of the building.</span></span> |
|<span data-ttu-id="ce147-208">經度</span><span class="sxs-lookup"><span data-stu-id="ce147-208">Longitude</span></span> |<span data-ttu-id="ce147-209">float</span><span class="sxs-lookup"><span data-stu-id="ce147-209">float</span></span> |<span data-ttu-id="ce147-210">是</span><span class="sxs-lookup"><span data-stu-id="ce147-210">Yes</span></span> |<span data-ttu-id="ce147-211">大樓的經度。</span><span class="sxs-lookup"><span data-stu-id="ce147-211">Longitude of the building.</span></span> |
|<span data-ttu-id="ce147-212">CityName</span><span class="sxs-lookup"><span data-stu-id="ce147-212">CityName</span></span> |<span data-ttu-id="ce147-213">Varchar (30) </span><span class="sxs-lookup"><span data-stu-id="ce147-213">varchar(30)</span></span> |<span data-ttu-id="ce147-214">是</span><span class="sxs-lookup"><span data-stu-id="ce147-214">Yes</span></span> |<span data-ttu-id="ce147-215">組建所在的城市名稱。</span><span class="sxs-lookup"><span data-stu-id="ce147-215">City name where the building is located.</span></span> |
|<span data-ttu-id="ce147-216">ZipCode</span><span class="sxs-lookup"><span data-stu-id="ce147-216">ZipCode</span></span> |<span data-ttu-id="ce147-217">Varchar (25) </span><span class="sxs-lookup"><span data-stu-id="ce147-217">varchar(25)</span></span> |<span data-ttu-id="ce147-218">是</span><span class="sxs-lookup"><span data-stu-id="ce147-218">Yes</span></span> |<span data-ttu-id="ce147-219">樓號所在的郵遞區號。</span><span class="sxs-lookup"><span data-stu-id="ce147-219">Zip code where the building is located.</span></span> |
|<span data-ttu-id="ce147-220">CountryShortCode</span><span class="sxs-lookup"><span data-stu-id="ce147-220">CountryShortCode</span></span> |<span data-ttu-id="ce147-221">Varchar (2) </span><span class="sxs-lookup"><span data-stu-id="ce147-221">varchar(2)</span></span> |<span data-ttu-id="ce147-222">是</span><span class="sxs-lookup"><span data-stu-id="ce147-222">Yes</span></span> |<span data-ttu-id="ce147-223">組建所在國家的 ISO 3166-1 Alpha-2 碼。</span><span class="sxs-lookup"><span data-stu-id="ce147-223">ISO 3166-1 alpha-2 codes for the country where the building is located.</span></span> |
|<span data-ttu-id="ce147-224">StateProvinceCode</span><span class="sxs-lookup"><span data-stu-id="ce147-224">StateProvinceCode</span></span> |<span data-ttu-id="ce147-225">Varchar (3) </span><span class="sxs-lookup"><span data-stu-id="ce147-225">varchar(3)</span></span> |<span data-ttu-id="ce147-226">是</span><span class="sxs-lookup"><span data-stu-id="ce147-226">Yes</span></span> |<span data-ttu-id="ce147-227">組建所在之州/省的三個字母縮寫。</span><span class="sxs-lookup"><span data-stu-id="ce147-227">Three-letter abbreviation for the State/Province where the building is located.</span></span> |
|<span data-ttu-id="ce147-228">InsideCorp</span><span class="sxs-lookup"><span data-stu-id="ce147-228">InsideCorp</span></span> |<span data-ttu-id="ce147-229">位</span><span class="sxs-lookup"><span data-stu-id="ce147-229">bit</span></span> |<span data-ttu-id="ce147-230">是</span><span class="sxs-lookup"><span data-stu-id="ce147-230">Yes</span></span> |<span data-ttu-id="ce147-231">Bit 表示組建是否屬於公司網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce147-231">Bit indicates whether the building is part of the corporate network.</span></span> |
|<span data-ttu-id="ce147-232">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="ce147-232">BuildingOfficeType</span></span> |<span data-ttu-id="ce147-233">Nvarchar (150) </span><span class="sxs-lookup"><span data-stu-id="ce147-233">nvarchar(150)</span></span> |<span data-ttu-id="ce147-234">是</span><span class="sxs-lookup"><span data-stu-id="ce147-234">Yes</span></span> |<span data-ttu-id="ce147-235">建立 office 類型的描述。</span><span class="sxs-lookup"><span data-stu-id="ce147-235">Description of the building office type.</span></span> |
|<span data-ttu-id="ce147-236">地區</span><span class="sxs-lookup"><span data-stu-id="ce147-236">Region</span></span> |<span data-ttu-id="ce147-237">Varchar (25) </span><span class="sxs-lookup"><span data-stu-id="ce147-237">varchar(25)</span></span> |<span data-ttu-id="ce147-238">是</span><span class="sxs-lookup"><span data-stu-id="ce147-238">Yes</span></span> |<span data-ttu-id="ce147-239">組建所在的地區。</span><span class="sxs-lookup"><span data-stu-id="ce147-239">Region where the building is located.</span></span> |
|||||

<span data-ttu-id="ce147-240">**CqdNetwork**</span><span class="sxs-lookup"><span data-stu-id="ce147-240">**CqdNetwork**</span></span>

|<span data-ttu-id="ce147-241">欄</span><span class="sxs-lookup"><span data-stu-id="ce147-241">Column</span></span>|<span data-ttu-id="ce147-242">資料類型</span><span class="sxs-lookup"><span data-stu-id="ce147-242">Data Type</span></span>|<span data-ttu-id="ce147-243">允許 Null？</span><span class="sxs-lookup"><span data-stu-id="ce147-243">Allow Nulls?</span></span>|<span data-ttu-id="ce147-244">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce147-244">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-245">網路</span><span class="sxs-lookup"><span data-stu-id="ce147-245">Network</span></span> |<span data-ttu-id="ce147-246">Varchar (25) </span><span class="sxs-lookup"><span data-stu-id="ce147-246">varchar(25)</span></span> |<span data-ttu-id="ce147-247">否</span><span class="sxs-lookup"><span data-stu-id="ce147-247">No</span></span> |<span data-ttu-id="ce147-248">子網位址。</span><span class="sxs-lookup"><span data-stu-id="ce147-248">Subnet address.</span></span> |
|<span data-ttu-id="ce147-249">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="ce147-249">NetworkRange</span></span> |<span data-ttu-id="ce147-250">Tinyint</span><span class="sxs-lookup"><span data-stu-id="ce147-250">tinyint</span></span> |<span data-ttu-id="ce147-251">是</span><span class="sxs-lookup"><span data-stu-id="ce147-251">Yes</span></span> |<span data-ttu-id="ce147-252">子網路遮罩。</span><span class="sxs-lookup"><span data-stu-id="ce147-252">Subnet mask.</span></span> |
|<span data-ttu-id="ce147-253">NetworkNameID</span><span class="sxs-lookup"><span data-stu-id="ce147-253">NetworkNameID</span></span> |<span data-ttu-id="ce147-254">int</span><span class="sxs-lookup"><span data-stu-id="ce147-254">int</span></span> |<span data-ttu-id="ce147-255">是</span><span class="sxs-lookup"><span data-stu-id="ce147-255">Yes</span></span> |<span data-ttu-id="ce147-256">（選用）對應至 CqdNetworkName table 中的列。</span><span class="sxs-lookup"><span data-stu-id="ce147-256">Optionally maps to a row in CqdNetworkName table.</span></span> |
|<span data-ttu-id="ce147-257">BuildingKey</span><span class="sxs-lookup"><span data-stu-id="ce147-257">BuildingKey</span></span> |<span data-ttu-id="ce147-258">int</span><span class="sxs-lookup"><span data-stu-id="ce147-258">int</span></span> |<span data-ttu-id="ce147-259">是</span><span class="sxs-lookup"><span data-stu-id="ce147-259">Yes</span></span> |<span data-ttu-id="ce147-260">外鍵，符合 CqdBuilding 表格中的其中一個專案。</span><span class="sxs-lookup"><span data-stu-id="ce147-260">Foreign key, matches one of the entries in the CqdBuilding table.</span></span> |
|<span data-ttu-id="ce147-261">UpdatedDate</span><span class="sxs-lookup"><span data-stu-id="ce147-261">UpdatedDate</span></span> |<span data-ttu-id="ce147-262">datetime</span><span class="sxs-lookup"><span data-stu-id="ce147-262">datetime</span></span> |<span data-ttu-id="ce147-263">否</span><span class="sxs-lookup"><span data-stu-id="ce147-263">No</span></span> |<span data-ttu-id="ce147-264">上次更新專案的日期時間。</span><span class="sxs-lookup"><span data-stu-id="ce147-264">Datetime for when the entry was last updated.</span></span> |
||||||

<span data-ttu-id="ce147-265">根據預設，此表格有一個專案 (0，' Unknown ' ) 。</span><span class="sxs-lookup"><span data-stu-id="ce147-265">By default this next table has one entry (0, 'Unknown').</span></span>

<span data-ttu-id="ce147-266">**CqdBuildingType**</span><span class="sxs-lookup"><span data-stu-id="ce147-266">**CqdBuildingType**</span></span>

|<span data-ttu-id="ce147-267">欄</span><span class="sxs-lookup"><span data-stu-id="ce147-267">Column</span></span>|<span data-ttu-id="ce147-268">資料類型</span><span class="sxs-lookup"><span data-stu-id="ce147-268">Data Type</span></span>|<span data-ttu-id="ce147-269">允許 Null？</span><span class="sxs-lookup"><span data-stu-id="ce147-269">Allow Nulls?</span></span>|<span data-ttu-id="ce147-270">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce147-270">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-271">BuildingTypeId</span><span class="sxs-lookup"><span data-stu-id="ce147-271">BuildingTypeId</span></span> |<span data-ttu-id="ce147-272">int</span><span class="sxs-lookup"><span data-stu-id="ce147-272">int</span></span> |<span data-ttu-id="ce147-273">否</span><span class="sxs-lookup"><span data-stu-id="ce147-273">No</span></span> |<span data-ttu-id="ce147-274">CqdBuildingType 表格的主鍵。</span><span class="sxs-lookup"><span data-stu-id="ce147-274">Primary key for the CqdBuildingType table.</span></span> |
|<span data-ttu-id="ce147-275">BuildingTypeDesc</span><span class="sxs-lookup"><span data-stu-id="ce147-275">BuildingTypeDesc</span></span> |<span data-ttu-id="ce147-276">char (18) </span><span class="sxs-lookup"><span data-stu-id="ce147-276">char(18)</span></span> |<span data-ttu-id="ce147-277">否</span><span class="sxs-lookup"><span data-stu-id="ce147-277">No</span></span> |<span data-ttu-id="ce147-278">大樓類型描述。</span><span class="sxs-lookup"><span data-stu-id="ce147-278">Building type description.</span></span> |
|||||

<span data-ttu-id="ce147-279">根據預設，此表格有一個專案 (0、' Unknown '、0、null) 。</span><span class="sxs-lookup"><span data-stu-id="ce147-279">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="ce147-280">**CqdBuildingOwnershipType**</span><span class="sxs-lookup"><span data-stu-id="ce147-280">**CqdBuildingOwnershipType**</span></span>

|<span data-ttu-id="ce147-281">欄</span><span class="sxs-lookup"><span data-stu-id="ce147-281">Column</span></span>|<span data-ttu-id="ce147-282">資料類型</span><span class="sxs-lookup"><span data-stu-id="ce147-282">Data Type</span></span>|<span data-ttu-id="ce147-283">允許 Null？</span><span class="sxs-lookup"><span data-stu-id="ce147-283">Allow Nulls?</span></span>|<span data-ttu-id="ce147-284">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce147-284">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-285">OwnershipTypeId</span><span class="sxs-lookup"><span data-stu-id="ce147-285">OwnershipTypeId</span></span> |<span data-ttu-id="ce147-286">int</span><span class="sxs-lookup"><span data-stu-id="ce147-286">int</span></span> |<span data-ttu-id="ce147-287">否</span><span class="sxs-lookup"><span data-stu-id="ce147-287">No</span></span> |<span data-ttu-id="ce147-288">CqdBuildingOwnershipType 表格的主鍵。</span><span class="sxs-lookup"><span data-stu-id="ce147-288">Primary key for the CqdBuildingOwnershipType table.</span></span> |
|<span data-ttu-id="ce147-289">OwnershipTypeDesc</span><span class="sxs-lookup"><span data-stu-id="ce147-289">OwnershipTypeDesc</span></span> |<span data-ttu-id="ce147-290">Varchar (25) </span><span class="sxs-lookup"><span data-stu-id="ce147-290">varchar(25)</span></span> |<span data-ttu-id="ce147-291">否</span><span class="sxs-lookup"><span data-stu-id="ce147-291">No</span></span> |<span data-ttu-id="ce147-292">擁有權類型描述。</span><span class="sxs-lookup"><span data-stu-id="ce147-292">Ownership type description.</span></span> |
|<span data-ttu-id="ce147-293">LeaseInd</span><span class="sxs-lookup"><span data-stu-id="ce147-293">LeaseInd</span></span> |<span data-ttu-id="ce147-294">Tinyint</span><span class="sxs-lookup"><span data-stu-id="ce147-294">tinyint</span></span> |<span data-ttu-id="ce147-295">是</span><span class="sxs-lookup"><span data-stu-id="ce147-295">Yes</span></span> |<span data-ttu-id="ce147-296">參照 CqdBuildingOwnershipType 表中另一個資料列的索引，用來識別租的大樓。</span><span class="sxs-lookup"><span data-stu-id="ce147-296">Index referencing another row in the CqdBuildingOwnershipType table, used for identifying leased buildings.</span></span> |
|<span data-ttu-id="ce147-297">擁有者</span><span class="sxs-lookup"><span data-stu-id="ce147-297">Owner</span></span> |<span data-ttu-id="ce147-298">Varchar (50) </span><span class="sxs-lookup"><span data-stu-id="ce147-298">varchar(50)</span></span> |<span data-ttu-id="ce147-299">是</span><span class="sxs-lookup"><span data-stu-id="ce147-299">Yes</span></span> |<span data-ttu-id="ce147-300">建立擁有者。</span><span class="sxs-lookup"><span data-stu-id="ce147-300">Building owner.</span></span> |
|||||

<span data-ttu-id="ce147-301">根據預設，此表格有一個專案 (0、' Unknown '、0、null) 。</span><span class="sxs-lookup"><span data-stu-id="ce147-301">By default this next table has one entry (0, 'Unknown', 0, null).</span></span>

<span data-ttu-id="ce147-302">**CqdBssid**</span><span class="sxs-lookup"><span data-stu-id="ce147-302">**CqdBssid**</span></span>

|<span data-ttu-id="ce147-303">欄</span><span class="sxs-lookup"><span data-stu-id="ce147-303">Column</span></span>|<span data-ttu-id="ce147-304">資料類型</span><span class="sxs-lookup"><span data-stu-id="ce147-304">Data Type</span></span>|<span data-ttu-id="ce147-305">允許 Null？</span><span class="sxs-lookup"><span data-stu-id="ce147-305">Allow Nulls?</span></span>|<span data-ttu-id="ce147-306">詳細資料</span><span class="sxs-lookup"><span data-stu-id="ce147-306">Details</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-307">Bss</span><span class="sxs-lookup"><span data-stu-id="ce147-307">bss</span></span> |<span data-ttu-id="ce147-308">Nvarchar (50) </span><span class="sxs-lookup"><span data-stu-id="ce147-308">nvarchar(50)</span></span> |<span data-ttu-id="ce147-309">否</span><span class="sxs-lookup"><span data-stu-id="ce147-309">No</span></span> |<span data-ttu-id="ce147-310">CqdBssid 表格的主鍵。</span><span class="sxs-lookup"><span data-stu-id="ce147-310">Primary key for the CqdBssid table.</span></span> <span data-ttu-id="ce147-311">為 WiFi 存取點的 BSSID。</span><span class="sxs-lookup"><span data-stu-id="ce147-311">Is the BSSID of the WiFi Access Point.</span></span> |
|<span data-ttu-id="ce147-312">Ess</span><span class="sxs-lookup"><span data-stu-id="ce147-312">ess</span></span> |<span data-ttu-id="ce147-313">Nvarchar (50) </span><span class="sxs-lookup"><span data-stu-id="ce147-313">nvarchar(50)</span></span> |<span data-ttu-id="ce147-314">是</span><span class="sxs-lookup"><span data-stu-id="ce147-314">Yes</span></span> |<span data-ttu-id="ce147-315">Wifi 存取點控制器資訊。</span><span class="sxs-lookup"><span data-stu-id="ce147-315">Wifi Access Point Controller information.</span></span> |
|<span data-ttu-id="ce147-316">Phy</span><span class="sxs-lookup"><span data-stu-id="ce147-316">phy</span></span> |<span data-ttu-id="ce147-317">Nvarchar (50) </span><span class="sxs-lookup"><span data-stu-id="ce147-317">nvarchar(50)</span></span> |<span data-ttu-id="ce147-318">是</span><span class="sxs-lookup"><span data-stu-id="ce147-318">Yes</span></span> |<span data-ttu-id="ce147-319">Phy 資訊。</span><span class="sxs-lookup"><span data-stu-id="ce147-319">Phy information.</span></span> |
|<span data-ttu-id="ce147-320">美聯社</span><span class="sxs-lookup"><span data-stu-id="ce147-320">ap</span></span> |<span data-ttu-id="ce147-321">Nvarchar (50) </span><span class="sxs-lookup"><span data-stu-id="ce147-321">nvarchar(50)</span></span> |<span data-ttu-id="ce147-322">是</span><span class="sxs-lookup"><span data-stu-id="ce147-322">Yes</span></span> |<span data-ttu-id="ce147-323">Wifi 存取點名稱。</span><span class="sxs-lookup"><span data-stu-id="ce147-323">Wifi Access Point Name.</span></span> |
|<span data-ttu-id="ce147-324">建築</span><span class="sxs-lookup"><span data-stu-id="ce147-324">Building</span></span> |<span data-ttu-id="ce147-325">Nvarchar (500) </span><span class="sxs-lookup"><span data-stu-id="ce147-325">nvarchar(500)</span></span> |<span data-ttu-id="ce147-326">是</span><span class="sxs-lookup"><span data-stu-id="ce147-326">Yes</span></span> |<span data-ttu-id="ce147-327">WiFi 存取點所在的大樓名稱。</span><span class="sxs-lookup"><span data-stu-id="ce147-327">The Building Name the WiFi Access Point is located in.</span></span> |
||||

## <a name="cqd-streams"></a><span data-ttu-id="ce147-328">CQD 資料流程</span><span class="sxs-lookup"><span data-stu-id="ce147-328">CQD Streams</span></span>

<span data-ttu-id="ce147-329">CQD 資料流程被視為好、不良或未分類。</span><span class="sxs-lookup"><span data-stu-id="ce147-329">A CQD stream is considered good, poor, or unclassified.</span></span> <span data-ttu-id="ce147-330">CQM 1.5 現在使用下列 CQD 定義：</span><span class="sxs-lookup"><span data-stu-id="ce147-330">CQM 1.5 now uses the following CQD definition:</span></span>

- <span data-ttu-id="ce147-331">不良的資料流程是指超出臨界值的不良呼叫計量值的任何組合。</span><span class="sxs-lookup"><span data-stu-id="ce147-331">A poor stream is any combination of the poor call metrics beyond threshold.</span></span>
- <span data-ttu-id="ce147-332">當通話中的某個資料流程不良時，會將通話的兩個數據流標示為較差。</span><span class="sxs-lookup"><span data-stu-id="ce147-332">When one stream in a call is poor, both streams of the call are flagged poor.</span></span> <span data-ttu-id="ce147-333">在會議中，每位參與者都會以唯一通話的方式進行計算，而且會獨立于其他人員報告。</span><span class="sxs-lookup"><span data-stu-id="ce147-333">In conferences, each participant is counted as a unique call and is reported on independently of all others.</span></span>
- <span data-ttu-id="ce147-334">未分類的資料流程是指沒有品質計量的資料流程 (也就是說，綜合交易或簡短呼叫) 。</span><span class="sxs-lookup"><span data-stu-id="ce147-334">Unclassified streams are streams without quality metrics (that is, Synthetic Transactions or short calls).</span></span>
- <span data-ttu-id="ce147-335">有效的資料流程 = 非行動用戶端</span><span class="sxs-lookup"><span data-stu-id="ce147-335">Valid Streams = non-mobile clients</span></span>
- <span data-ttu-id="ce147-336">無法修改分類器</span><span class="sxs-lookup"><span data-stu-id="ce147-336">Classifier cannot be modified</span></span>

<span data-ttu-id="ce147-337">**通話不良定義/分類器**</span><span class="sxs-lookup"><span data-stu-id="ce147-337">**Poor call definition/classifier**</span></span>

|<span data-ttu-id="ce147-338">計量</span><span class="sxs-lookup"><span data-stu-id="ce147-338">Metric</span></span>|<span data-ttu-id="ce147-339">臨界值</span><span class="sxs-lookup"><span data-stu-id="ce147-339">Threshold</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce147-340">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="ce147-340">DegradationAvg</span></span> |<span data-ttu-id="ce147-341">大於 1.0 (-1 網路 MOS) </span><span class="sxs-lookup"><span data-stu-id="ce147-341">Greater than 1.0 (-1 network MOS)</span></span> |
|<span data-ttu-id="ce147-342">往返</span><span class="sxs-lookup"><span data-stu-id="ce147-342">RoundTrip</span></span> |<span data-ttu-id="ce147-343">大於500</span><span class="sxs-lookup"><span data-stu-id="ce147-343">Greater than 500</span></span> |
|<span data-ttu-id="ce147-344">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="ce147-344">PacketLossRate</span></span> |<span data-ttu-id="ce147-345">大於 0.1 (10% ) </span><span class="sxs-lookup"><span data-stu-id="ce147-345">Greater than 0.1 (10%)</span></span> |
|<span data-ttu-id="ce147-346">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="ce147-346">JitterInterArrival</span></span> |<span data-ttu-id="ce147-347">大於30</span><span class="sxs-lookup"><span data-stu-id="ce147-347">Greater than 30</span></span> |
|<span data-ttu-id="ce147-348">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ce147-348">RatioConcealedSamplesAvg</span></span> |<span data-ttu-id="ce147-349">大於0.07</span><span class="sxs-lookup"><span data-stu-id="ce147-349">Greater than 0.07</span></span> |
|||

<span data-ttu-id="ce147-350">JPDR definition = 不良通話定義減去 RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="ce147-350">JPDR definition = Poor call definition minus RatioConcealedSamplesAvg</span></span>

## <a name="where-is-callercallee"></a><span data-ttu-id="ce147-351">來電者/被叫方位於何處？</span><span class="sxs-lookup"><span data-stu-id="ce147-351">Where is Caller/Callee?</span></span>

<span data-ttu-id="ce147-352">CQD 不使用來電者/被叫用方欄位，而是使用 "First" 和 "Second"，因為來電者和被叫方之間有介入的步驟。</span><span class="sxs-lookup"><span data-stu-id="ce147-352">CQD doesn't use Caller/Callee fields, instead it uses "First" and "Second" because there are intervening steps between the caller and callee.</span></span>

 <span data-ttu-id="ce147-353">**First** 會一直是伺服器端點 (例如，AV MCU 或轉送伺服器) （如果此資料流程中包含伺服器）。</span><span class="sxs-lookup"><span data-stu-id="ce147-353">**First** Will always be the Server endpoint (for example, AV MCU or Mediation Server) if a Server is involved in the stream.</span></span>

 <span data-ttu-id="ce147-354">**第二** 除非是 Server-Server 資料流程，否則會永遠為用戶端端點。</span><span class="sxs-lookup"><span data-stu-id="ce147-354">**Second** Will always be the Client endpoint, unless it is a Server-Server stream.</span></span>

<span data-ttu-id="ce147-355">**第一及第二個分類的範例**</span><span class="sxs-lookup"><span data-stu-id="ce147-355">**Example of First and Second classification**</span></span>

|<span data-ttu-id="ce147-356">端點 1 UAType</span><span class="sxs-lookup"><span data-stu-id="ce147-356">Endpoint 1 UAType</span></span>|<span data-ttu-id="ce147-357">端點 2 UUAType</span><span class="sxs-lookup"><span data-stu-id="ce147-357">Endpoint 2 UUAType</span></span>|<span data-ttu-id="ce147-358">名字</span><span class="sxs-lookup"><span data-stu-id="ce147-358">First</span></span>|<span data-ttu-id="ce147-359">秒</span><span class="sxs-lookup"><span data-stu-id="ce147-359">Second</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ce147-360">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="ce147-360">2 (AVMCU)</span></span> |<span data-ttu-id="ce147-361">4 (商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="ce147-361">4 (Skype for Business)</span></span> |<span data-ttu-id="ce147-362">端點1</span><span class="sxs-lookup"><span data-stu-id="ce147-362">Endpoint 1</span></span> |<span data-ttu-id="ce147-363">端點2</span><span class="sxs-lookup"><span data-stu-id="ce147-363">Endpoint 2</span></span> |
|<span data-ttu-id="ce147-364">2 (AVMCU) </span><span class="sxs-lookup"><span data-stu-id="ce147-364">2 (AVMCU)</span></span> |<span data-ttu-id="ce147-365">1 (mMediationServer) </span><span class="sxs-lookup"><span data-stu-id="ce147-365">1 (mMediationServer)</span></span> |<span data-ttu-id="ce147-366">端點2</span><span class="sxs-lookup"><span data-stu-id="ce147-366">Endpoint 2</span></span> |<span data-ttu-id="ce147-367">端點1</span><span class="sxs-lookup"><span data-stu-id="ce147-367">Endpoint 1</span></span> |
|<span data-ttu-id="ce147-368">4 (商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="ce147-368">4 (Skype for Business)</span></span> |<span data-ttu-id="ce147-369">4 (商務用 Skype) </span><span class="sxs-lookup"><span data-stu-id="ce147-369">4 (Skype for Business)</span></span> |<span data-ttu-id="ce147-370">MediaLine 的來電者</span><span class="sxs-lookup"><span data-stu-id="ce147-370">The Caller in MediaLine</span></span> |<span data-ttu-id="ce147-371">MMediaLine 中的被呼叫者</span><span class="sxs-lookup"><span data-stu-id="ce147-371">The Callee in MMediaLine</span></span> |
|||||

<span data-ttu-id="ce147-372">如果兩個端點都是相同類型，則 CQD 會先將來電者專案和被叫方的第二個端點。</span><span class="sxs-lookup"><span data-stu-id="ce147-372">If both endpoints are the same type, CQD makes the Caller entry First and the Callee Second.</span></span> <span data-ttu-id="ce147-373">如需端點名稱的詳細資訊，請參閱 [此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ce147-373">For more information about endpoint names, see [this blog](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx).</span></span>

## <a name="accounting-for-vpn"></a><span data-ttu-id="ce147-374">VPN 的記帳</span><span class="sxs-lookup"><span data-stu-id="ce147-374">Accounting for VPN</span></span>

<span data-ttu-id="ce147-375">如果已知 VPN 解決方案可正確設定 VPN 旗標，您就是全部設定。</span><span class="sxs-lookup"><span data-stu-id="ce147-375">If VPN solution is known to accurately set VPN flag, you're all set.</span></span> <span data-ttu-id="ce147-376">否則，請使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="ce147-376">Otherwise, use one of the following methods:</span></span>

- <span data-ttu-id="ce147-377">建立名為 VPN (首選) 的網路類型，然後將 VPN 子網與這個新的 VPN NetworkType 建立關聯。</span><span class="sxs-lookup"><span data-stu-id="ce147-377">Create a Network Type called VPN (preferred), then Associate VPN Subnets with this new VPN NetworkType.</span></span>
- <span data-ttu-id="ce147-378">建立名為 VPN 的大樓，然後將 VPN 子網與此大樓產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ce147-378">Create a building called VPN, then Associate VPN Subnets with this building.</span></span>

## <a name="query-fundamentals"></a><span data-ttu-id="ce147-379">查詢基礎</span><span class="sxs-lookup"><span data-stu-id="ce147-379">Query Fundamentals</span></span>

<span data-ttu-id="ce147-380">格式正確的查詢包含下列所有三個參數：</span><span class="sxs-lookup"><span data-stu-id="ce147-380">A well-formed query contains all three of these parameters:</span></span>

- <span data-ttu-id="ce147-381">測量</span><span class="sxs-lookup"><span data-stu-id="ce147-381">Measurement</span></span>
- <span data-ttu-id="ce147-382">維度</span><span class="sxs-lookup"><span data-stu-id="ce147-382">Dimension</span></span>
- <span data-ttu-id="ce147-383">篩選</span><span class="sxs-lookup"><span data-stu-id="ce147-383">Filter</span></span>

<span data-ttu-id="ce147-384">例如，格式正確的查詢將會是「使用子網的「顯示不良資料流程」（Dimension）」（Filter）。</span><span class="sxs-lookup"><span data-stu-id="ce147-384">An example of a well-formed query would be "Show me Poor Streams [Measurement] by Subnet [Dimension] for Building 6 [Filter]."</span></span>

## <a name="what-does-union-do"></a><span data-ttu-id="ce147-385">同盟的功能為何？</span><span class="sxs-lookup"><span data-stu-id="ce147-385">What does UNION do?</span></span>

<span data-ttu-id="ce147-386">同盟可讓您使用 AND 運算子來篩選準則。</span><span class="sxs-lookup"><span data-stu-id="ce147-386">Union allows you to filter conditions with the AND operator.</span></span> <span data-ttu-id="ce147-387">在某些情況下，您可以將多個篩選準則結合在一起，以取得類似 OR 運算的結果。</span><span class="sxs-lookup"><span data-stu-id="ce147-387">There are scenarios where you can combine multiple Filter conditions together to achieve a result similar to an OR operation.</span></span>

<span data-ttu-id="ce147-388">範例：若要從大樓取得所有資料流程，同盟會提供合併資料集的不同視圖。</span><span class="sxs-lookup"><span data-stu-id="ce147-388">Example: To get all streams from a building, UNION provides a distinct view of the merged dataset.</span></span> <span data-ttu-id="ce147-389">若要使用同盟，請在您想要同盟的兩個篩選準則上，將一般文字插入同盟欄位。</span><span class="sxs-lookup"><span data-stu-id="ce147-389">To use the UNION, insert common text into the UNION field on the two filter conditions you want to UNION.</span></span>

## <a name="default-report-breakdown"></a><span data-ttu-id="ce147-390">預設報表細目</span><span class="sxs-lookup"><span data-stu-id="ce147-390">Default Report Breakdown</span></span>

<span data-ttu-id="ce147-391">如果在內部管理無線，您可以在受管理的桶中重新建立無線報告。</span><span class="sxs-lookup"><span data-stu-id="ce147-391">If Wireless is managed internally, you can recreate the Wireless reports in the Managed bucket.</span></span>

![CQD 報告分解](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a><span data-ttu-id="ce147-393">運作過程</span><span class="sxs-lookup"><span data-stu-id="ce147-393">Operational Processes</span></span>

<span data-ttu-id="ce147-394">請先複查和修正受管理的資料流程。</span><span class="sxs-lookup"><span data-stu-id="ce147-394">Review and remediate Managed Streams first.</span></span> <span data-ttu-id="ce147-395">此區域中的品質應該是在您的控制項內的100%，因此可讓您更容易修正。</span><span class="sxs-lookup"><span data-stu-id="ce147-395">Quality in this area should be 100% within your control and therefore easiest to remediate.</span></span>

### <a name="managed-streams"></a><span data-ttu-id="ce147-396">受管理的資料流程</span><span class="sxs-lookup"><span data-stu-id="ce147-396">Managed Streams</span></span>

<span data-ttu-id="ce147-397">依下列順序複查和修正受管理的資料流程：</span><span class="sxs-lookup"><span data-stu-id="ce147-397">Review and remediate managed streams in the following order:</span></span>

1. <span data-ttu-id="ce147-398">Server-Server</span><span class="sxs-lookup"><span data-stu-id="ce147-398">Server-Server</span></span>
2. <span data-ttu-id="ce147-399">伺服器-內部接線</span><span class="sxs-lookup"><span data-stu-id="ce147-399">Server-Wired-Inside</span></span>
3. <span data-ttu-id="ce147-400">有線-有線-內部</span><span class="sxs-lookup"><span data-stu-id="ce147-400">Wired-Wired-Inside</span></span>

### <a name="unmanaged-streams"></a><span data-ttu-id="ce147-401">非管理資料流程</span><span class="sxs-lookup"><span data-stu-id="ce147-401">Unmanaged Streams</span></span>

<span data-ttu-id="ce147-402">依下列順序複查和修正非管理的資料流程：</span><span class="sxs-lookup"><span data-stu-id="ce147-402">Review and remediate unmanaged streams in the following order:</span></span>

1. <span data-ttu-id="ce147-403">伺服器-Wifi-內部</span><span class="sxs-lookup"><span data-stu-id="ce147-403">Server-Wifi-Inside</span></span>
2. <span data-ttu-id="ce147-404">伺服器-接線外</span><span class="sxs-lookup"><span data-stu-id="ce147-404">Server-Wired-Outside</span></span>
3. <span data-ttu-id="ce147-405">伺服器-Wlan-外線</span><span class="sxs-lookup"><span data-stu-id="ce147-405">Server-Wifi-Outside</span></span>
4. <span data-ttu-id="ce147-406">接線外-直接</span><span class="sxs-lookup"><span data-stu-id="ce147-406">Wired-Outside-Direct</span></span>
5. <span data-ttu-id="ce147-407">有線外轉送</span><span class="sxs-lookup"><span data-stu-id="ce147-407">Wired-Outside-Relay</span></span>
6. <span data-ttu-id="ce147-408">其他非管理</span><span class="sxs-lookup"><span data-stu-id="ce147-408">Other Unmanaged</span></span>
