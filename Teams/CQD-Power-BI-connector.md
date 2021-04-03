---
title: 安裝 Power BI Connector 以使用 CQD 查詢範本
ms.author: serdars
author: SerdarSoysal
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
description: 安裝 Power BI Connector 以使用通話品質儀表板 (CQD) 查詢範本
ms.openlocfilehash: 51b989601b7ccec035bda84cc0177aca8f198d1f
ms.sourcegitcommit: e511748ede1c0410d1ba1ea8342f4afcbe1c61c7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "51495765"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a><span data-ttu-id="92c52-103">安裝 Power BI Connector 以使用 CQD 查詢範本</span><span class="sxs-lookup"><span data-stu-id="92c52-103">Install Power BI Connector to use CQD query templates</span></span>

<span data-ttu-id="92c52-104">在使用 Power BI 查詢範本 (PBIX 檔案) for Microsoft Teams 通話品質儀表板 (CQD) 之前，您必須使用下載中包含的 *MicrosoftCQD MicrosoftCQD* Power BI Connector。 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="92c52-104">Before you can use the Power BI query templates (PBIX files) for Microsoft Teams Call Quality Dashboard (CQD), you'll need to install the Power BI Connector for Microsoft CQD, using the *MicrosoftCallQuality.pqx* file included in the [download](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span>

<span data-ttu-id="92c52-105">請參閱使用 Power BI 分析 Teams 的 [CQD](CQD-Power-BI-query-templates.md) 資料，以瞭解這些範本。</span><span class="sxs-lookup"><span data-stu-id="92c52-105">Read [Use Power BI to analyze CQD data for Teams](CQD-Power-BI-query-templates.md) to learn about these templates.</span></span>

<span data-ttu-id="92c52-106">請確定您擁有正確的 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) ，以存取 Power BI 報表。</span><span class="sxs-lookup"><span data-stu-id="92c52-106">Make sure you have the right [CQD access role](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) to access the Power BI reports.</span></span>

> [!NOTE]
> <span data-ttu-id="92c52-107">CQD Power BI Connector 僅支援 Power BI 中的 DirectQuery;不支援輸入模式。</span><span class="sxs-lookup"><span data-stu-id="92c52-107">The CQD Power BI Connector only supports DirectQuery in Power BI; Import mode is not supported.</span></span> 

## <a name="installation"></a><span data-ttu-id="92c52-108">安裝</span><span class="sxs-lookup"><span data-stu-id="92c52-108">Installation</span></span>

<span data-ttu-id="92c52-109">Power BI 檔詳述安裝自訂連接器及調整安全性以啟用連接器使用 [的過程](/power-bi/desktop-connector-extensibility)。</span><span class="sxs-lookup"><span data-stu-id="92c52-109">The process for installing a custom connector and adjusting security to enable use of the connector is described in detail in the [Power BI documentation](/power-bi/desktop-connector-extensibility).</span></span> <span data-ttu-id="92c52-110">為了簡單起見，以下是快速說明：</span><span class="sxs-lookup"><span data-stu-id="92c52-110">For the sake of simplicity, here's a quick explanation:</span></span>

1. <span data-ttu-id="92c52-111">檢查您的電腦是否已經有檔 *\[ Power BI \] \\ 桌面 \\ 自訂連接器* 資料夾。</span><span class="sxs-lookup"><span data-stu-id="92c52-111">Check to see if your computer already has a *\[Documents\]\\Power BI Desktop\\Custom Connectors* folder.</span></span> <span data-ttu-id="92c52-112">如果沒有，請建立此資料夾。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="92c52-112">If not, create this folder.<sup>1</sup></span></span>

2. <span data-ttu-id="92c52-113">下載連接器檔案 (*\* .mez* 或 *\* .pqx* 檔案) 並放在 *自訂連接器* 目錄中。</span><span class="sxs-lookup"><span data-stu-id="92c52-113">Download the connector file (either a *\*.mez* or *\*.pqx* file) and place it in the *Custom Connectors* directory.</span></span>

3. <span data-ttu-id="92c52-114">**如果連接器檔案是 *\* .mez* 檔案**，您也需要調整安全性設定，如自訂連接器設定檔 [所述](/power-bi/desktop-connector-extensibility#data-extension-security)。</span><span class="sxs-lookup"><span data-stu-id="92c52-114">**If the connector file is a *\*.mez* file,** you will also need to adjust your security settings as described in the [custom connector setup documentation](/power-bi/desktop-connector-extensibility#data-extension-security).</span></span>

<span data-ttu-id="92c52-115">如果 Microsoft Teams 版 Power BI Connector 發行新版本，只要將自訂連接器目錄中的舊連接器檔案取代為新檔案。</span><span class="sxs-lookup"><span data-stu-id="92c52-115">If a new version of this Power BI Connector for Microsoft Teams is released, simply replace the old connector file in the *Custom Connectors* directory with the new file.</span></span>

## <a name="setup"></a><span data-ttu-id="92c52-116">設置</span><span class="sxs-lookup"><span data-stu-id="92c52-116">Setup</span></span>

<span data-ttu-id="92c52-117">若要建立報表並執行查詢，您首先必須連接到 CQD 資料來源。</span><span class="sxs-lookup"><span data-stu-id="92c52-117">In order to build a report and run queries, you will first need to connect to the CQD data source.</span></span> <span data-ttu-id="92c52-118">請遵循下列步驟進行連結：</span><span class="sxs-lookup"><span data-stu-id="92c52-118">Follow the steps below in order to connect:</span></span>

1. <span data-ttu-id="92c52-119">在 Power BI 桌面的 [主版」 選項卡中，按一下 [ *取得資料*> 。</span><span class="sxs-lookup"><span data-stu-id="92c52-119">In the Home tab of Power BI Desktop, click on *Get Data*.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector1-resize.png)

2. <span data-ttu-id="92c52-121">此時 *應該會出現* 取得資料視窗。</span><span class="sxs-lookup"><span data-stu-id="92c52-121">The *Get Data* window should appear at this point.</span></span> <span data-ttu-id="92c52-122">流覽至 *線上服務，* 然後選取 Microsoft 通話品質 (*Beta) 並* 按 *Connect。*</span><span class="sxs-lookup"><span data-stu-id="92c52-122">Navigate to *Online Services*, then select *Microsoft Call Quality (Beta)* and hit *Connect*.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector2-resize.png)

3. <span data-ttu-id="92c52-124">下一步將會提示您進行登錄。</span><span class="sxs-lookup"><span data-stu-id="92c52-124">You will be prompted to sign in next.</span></span> <span data-ttu-id="92c52-125">使用您用於 CQD 的相同認證。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="92c52-125">Use the same credentials that you use for CQD.<sup>2</sup></span></span>

4. <span data-ttu-id="92c52-126">下一個提示會提供兩種資料連線 *模式之間的選項*。</span><span class="sxs-lookup"><span data-stu-id="92c52-126">The next prompt will give you the option between two *Data Connectivity modes*.</span></span> <span data-ttu-id="92c52-127">選取 *DirectQuery，* 然後按 *確定*。</span><span class="sxs-lookup"><span data-stu-id="92c52-127">Select *DirectQuery* and hit *OK*.</span></span>

5. <span data-ttu-id="92c52-128">最後，系統會提示您顯示 CQD 的整個資料模型。</span><span class="sxs-lookup"><span data-stu-id="92c52-128">Finally, you will be given a final prompt showing you the entire data model for CQD.</span></span> <span data-ttu-id="92c52-129">此時不會顯示任何資料，只會顯示 CQD 的資料模型。</span><span class="sxs-lookup"><span data-stu-id="92c52-129">No data will be visible at this point, only the data model for CQD.</span></span> <span data-ttu-id="92c52-130">選取 *載入* 以完成設定程式。</span><span class="sxs-lookup"><span data-stu-id="92c52-130">Select *Load* to complete the setup process.</span></span>

6. <span data-ttu-id="92c52-131">此時，Power BI 會將資料模型載入至視窗右側。</span><span class="sxs-lookup"><span data-stu-id="92c52-131">At this point, Power BI will load the data model onto the right side of the window.</span></span> <span data-ttu-id="92c52-132">頁面會保留空白，且預設不會載入任何查詢。</span><span class="sxs-lookup"><span data-stu-id="92c52-132">The page will remain otherwise blank, and no queries will be loaded by default.</span></span> <span data-ttu-id="92c52-133">繼續進行下方的 **建立** 查詢，以建立查詢並返回資料。</span><span class="sxs-lookup"><span data-stu-id="92c52-133">Proceed to **Building Queries** below in order to build a query and return data.</span></span>

<span data-ttu-id="92c52-134">如果此設定程式期間的任何步驟並未完全清楚，可以在快速入門中找到程式的詳細說明：在 [Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)中連接到資料。</span><span class="sxs-lookup"><span data-stu-id="92c52-134">If any of the steps during this setup process were not completely clear, a more detailed explanation of the process can be found in [Quickstart: Connect to data in Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).</span></span>

## <a name="building-queries"></a><span data-ttu-id="92c52-135">建立查詢</span><span class="sxs-lookup"><span data-stu-id="92c52-135">Building Queries</span></span>

<span data-ttu-id="92c52-136">設定完成後，您應該在欄位窗格中看到數百個維度和量值 *載入* 的名稱。</span><span class="sxs-lookup"><span data-stu-id="92c52-136">Once setup is complete, you should see the names of several hundred dimensions and measures load in the *Fields* pane.</span></span> <span data-ttu-id="92c52-137">從這裡建立實際查詢很簡單，只要選取您想要查詢的維度和度量，然後將它們拖放到頁面上。</span><span class="sxs-lookup"><span data-stu-id="92c52-137">Constructing actual queries from here is simple, just select the dimensions and measures you want for your query, then drag and drop them onto the page.</span></span> <span data-ttu-id="92c52-138">以下是更詳細的說明，以及一個簡單的範例：</span><span class="sxs-lookup"><span data-stu-id="92c52-138">Here's a more detailed explanation, with a simple example:</span></span>

1. <span data-ttu-id="92c52-139">從視覺效果窗格中選取您想要 *使用的視覺效果* 。</span><span class="sxs-lookup"><span data-stu-id="92c52-139">Select the visualization you want to use from the *Visualizations* pane.</span></span> <span data-ttu-id="92c52-140">該視覺效果的空白版本應該會出現在頁面上。</span><span class="sxs-lookup"><span data-stu-id="92c52-140">A blank version of that visualization should appear on the page.</span></span> <span data-ttu-id="92c52-141">為了本範例的目的，我們將使用表格 *視覺效果* 。</span><span class="sxs-lookup"><span data-stu-id="92c52-141">For the purposes of this example, we will be using the *Table* visualization.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector3-resize.png)

2. <span data-ttu-id="92c52-143">決定要用於 (的匯總符號) 以匯總符號表示的維度和度量，然後手動選取這些維度和度量，並將它們拖曳到黑色視覺效果上。</span><span class="sxs-lookup"><span data-stu-id="92c52-143">Determine which dimensions and measures (denoted by an aggregation symbol by their name) you wish to use for your query, then manually select them and drag them onto the black visualization.</span></span> <span data-ttu-id="92c52-144">或者，將它們拖曳 *到視覺效果選項* 下方的值欄位。</span><span class="sxs-lookup"><span data-stu-id="92c52-144">Alternately, drag them onto the *Values* field beneath the visualization options.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > <span data-ttu-id="92c52-146">通話品質儀表板需要執行任何查詢的量值。</span><span class="sxs-lookup"><span data-stu-id="92c52-146">Call Quality Dashboard requires a measure for any query to run.</span></span> <span data-ttu-id="92c52-147">若無法將量值新增到查詢，則會導致該查詢失敗。</span><span class="sxs-lookup"><span data-stu-id="92c52-147">Failure to add a measure to a query will cause that query to fail.</span></span>

3. <span data-ttu-id="92c52-148">接下來，選取您想要篩選的任何維度，並將這些維度拖曳到篩選窗格此視覺欄位 *上的篩選。*</span><span class="sxs-lookup"><span data-stu-id="92c52-148">Next, select any dimensions you want to filter on and drag them to the *Filters on this visual* field in the *Filters* pane.</span></span> <span data-ttu-id="92c52-149">CQD Power BI Connector 目前支援基本篩選 (從可能維度值清單中選取值) 、進位篩選 *(* 手動指定要篩選的值和操作 *數，類似* Advanced CQD) ，以及僅適用于結束時間和開始時間維度) 的相對日期篩選 (。   </span><span class="sxs-lookup"><span data-stu-id="92c52-149">The CQD Power BI Connector currently supports *Basic filtering* (select values from a list of possible dimension values), *Advanced filtering* (manually specify values and operands to filter on, similar to Advanced CQD), and *Relative date filtering* (only available for the *End Time* and *Start Time* dimensions).</span></span> <span data-ttu-id="92c52-150">CQD 不支援根據 *前 N* 個篩選。</span><span class="sxs-lookup"><span data-stu-id="92c52-150">Filtering according to *Top N* is not supported by CQD.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector5-resize.png)

4. <span data-ttu-id="92c52-152">最後，選取視覺效果 *窗格中* 的格式索引鍵，以為查詢設置樣式和格式。</span><span class="sxs-lookup"><span data-stu-id="92c52-152">Finally, select the *Format* tab within the *Visualizations* pane to style and format your query.</span></span>

    > [!NOTE]
    > <span data-ttu-id="92c52-153">CQD 查詢至少需要一個量值才能執行。</span><span class="sxs-lookup"><span data-stu-id="92c52-153">CQD queries require at least one measure in order to run.</span></span> <span data-ttu-id="92c52-154">如果您的查詢未載入，請仔細檢查您是否在查詢中包含量值。</span><span class="sxs-lookup"><span data-stu-id="92c52-154">If your query does not load, double check that you have included a measure in the query.</span></span>

## <a name="creating-a-drillthrough-report"></a><span data-ttu-id="92c52-155">建立鑽研報表</span><span class="sxs-lookup"><span data-stu-id="92c52-155">Creating a Drillthrough Report</span></span>

<span data-ttu-id="92c52-156">[Power BI 中的鑽](/power-bi/desktop-drillthrough) 取可讓您建立焦點報表，您可以使用其他報表的值做為上下文來快速篩選。</span><span class="sxs-lookup"><span data-stu-id="92c52-156">[Drillthrough in Power BI](/power-bi/desktop-drillthrough) allows you to create focused reports that you can quickly filter using the values of other reports as context.</span></span> <span data-ttu-id="92c52-157">瞭解如何使用 CQD Connector 建立第一個查詢之後，建立切線就更簡單了。</span><span class="sxs-lookup"><span data-stu-id="92c52-157">Once you know how to create your first query with the CQD Connector, creating a drillthrough is even simpler.</span></span>

1. <span data-ttu-id="92c52-158">為焦點報表建立另一個頁面，然後將查詢新增到該頁面。</span><span class="sxs-lookup"><span data-stu-id="92c52-158">Create another page for the focused report, and then add your queries to that page.</span></span>

2. <span data-ttu-id="92c52-159">Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.</span><span class="sxs-lookup"><span data-stu-id="92c52-159">Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector6-resize.png)

3. <span data-ttu-id="92c52-161">**就是這樣\!**</span><span class="sxs-lookup"><span data-stu-id="92c52-161">**That's it\!**</span></span> <span data-ttu-id="92c52-162">其他頁面上使用該維度的其他查詢現在都可以鑽取至該頁面，自動將鑽取維度的值當做篩選。</span><span class="sxs-lookup"><span data-stu-id="92c52-162">Any other query on another page that uses that dimension can now drillthrough to that page, automatically applying the drillthrough dimension's value as a filter.</span></span>

    ![螢幕擷取畫面：Power BI Connector](media/CQD-power-bi-connector7-resize.png)

<span data-ttu-id="92c52-164">與 Advanced CQD 不同，Power BI 支援非連續切線。</span><span class="sxs-lookup"><span data-stu-id="92c52-164">Unlike Advanced CQD, Power BI supports non-sequential drillthrough.</span></span> <span data-ttu-id="92c52-165">只要查詢包含必要的維度，它就可以切至任何其他頁面。</span><span class="sxs-lookup"><span data-stu-id="92c52-165">So long as a query includes the necessary dimension, it can drillthrough to any other page.</span></span>

### <a name="best-practice"></a><span data-ttu-id="92c52-166">最佳做法</span><span class="sxs-lookup"><span data-stu-id="92c52-166">Best practice</span></span>

<span data-ttu-id="92c52-167">通話品質連接器查詢在設計時，應牢記鑽取功能。</span><span class="sxs-lookup"><span data-stu-id="92c52-167">Call Quality connector queries should be designed with drillthrough functionality in mind.</span></span> <span data-ttu-id="92c52-168">與其嘗試一次載入所有資料，然後使用篩選進行切分，請從更廣泛的低基數查詢開始，然後向下切至高基數查詢。</span><span class="sxs-lookup"><span data-stu-id="92c52-168">Instead of trying to load all the data at once, and then slicing down with filters, start with broader, low-cardinality queries and drill down to high-cardinality queries.</span></span> <span data-ttu-id="92c52-169">例如，當您嘗試診斷哪些子網對品質問題影響最大時，先找出造成問題的區域及國家/地區，然後向下向下切入到該區域或國家/地區的子網會很有説明。</span><span class="sxs-lookup"><span data-stu-id="92c52-169">For instance, when attempting to diagnose which subnets contribute most to quality issues, it's helpful to first identify those regions and countries which contribute to the problem, then drill down to the subnets in that region or country.</span></span> <span data-ttu-id="92c52-170">通話品質連接器範本是採用這種方式設計，以做為範例。</span><span class="sxs-lookup"><span data-stu-id="92c52-170">The Call Quality connector templates have been designed in this manner in order to act as an example.</span></span>

## <a name="limitations"></a><span data-ttu-id="92c52-171">限制</span><span class="sxs-lookup"><span data-stu-id="92c52-171">Limitations</span></span>

<span data-ttu-id="92c52-172">雖然已使用 Power BI，但並非所有 Power BI 功能都受到 CQD Connector 的支援，無論是因為 CQD 資料模型或 DirectQuery 連接器的一般限制。</span><span class="sxs-lookup"><span data-stu-id="92c52-172">Despite making use of Power BI, not all Power BI functionality is support by the CQD Connector, either as a result of limitations on CQD data model or on DirectQuery connectors in general.</span></span> <span data-ttu-id="92c52-173">下列清單會說明連接器的一些較值得注意的限制，但這份清單不應視為詳盡無遺：</span><span class="sxs-lookup"><span data-stu-id="92c52-173">The list below notes some of the Connector's more noteworthy limitations, but this list should not be considered exhaustive:</span></span>

1. <span data-ttu-id="92c52-174">**計算欄 –** DirectQuery 連接器一般對 Power BI 中計算結果欄的支援有限。</span><span class="sxs-lookup"><span data-stu-id="92c52-174">**Calculated Columns –** DirectQuery connectors in general have limited support for calculated columns in Power BI.</span></span> <span data-ttu-id="92c52-175">雖然某些計算結果欄可能用於連接器，但應視為例外。</span><span class="sxs-lookup"><span data-stu-id="92c52-175">While some calculated columns may work with the Connector, these should be considered exceptions.</span></span> <span data-ttu-id="92c52-176">根據一般規則，計算結果欄不會運作。</span><span class="sxs-lookup"><span data-stu-id="92c52-176">As a general rule, calculated columns will not function.</span></span>

2. <span data-ttu-id="92c52-177">**匯總 –** CQD 資料模型是建在 Cube 模型上，這表示以度量形式已支援匯總。</span><span class="sxs-lookup"><span data-stu-id="92c52-177">**Aggregations –** The CQD data model is built on a cube model, meaning that aggregations are already supported in the form of measures.</span></span> <span data-ttu-id="92c52-178">嘗試手動將匯總新增到不同的維度或變更度量的匯總類型，無法與連接器一同使用，而且通常會導致錯誤。</span><span class="sxs-lookup"><span data-stu-id="92c52-178">Attempting to manually add aggregations to different dimensions or changing the aggregation type of a measure will not work with the Connector, and it will generally result in an error.</span></span>

3. <span data-ttu-id="92c52-179">**自訂視覺效果 –** 雖然 CQD Connector 確實可處理一系列自訂視覺效果，但我們無法保證所有自訂視覺效果的相容性。</span><span class="sxs-lookup"><span data-stu-id="92c52-179">**Custom Visuals –** While the CQD Connector does work with a range of custom visuals, we are unable to guarantee compatibility with all custom visuals.</span></span> <span data-ttu-id="92c52-180">許多自訂視覺效果仰賴計算資料行或輸入資料的使用，而 DirectQuery 連接器不支援或不支援這些資料。</span><span class="sxs-lookup"><span data-stu-id="92c52-180">Many custom visuals rely on the use of calculated columns or imported data, neither or which are supported by DirectQuery connectors.</span></span>

4. <span data-ttu-id="92c52-181">**參照緩存資料 –** Power BI 目前不支援以任何方式參照 DirectQuery 連接器的緩存資料。</span><span class="sxs-lookup"><span data-stu-id="92c52-181">**Referencing Cached Data –** Power BI currently does not support referencing cached data from a DirectQuery connector in any way.</span></span> <span data-ttu-id="92c52-182">任何參照查詢結果的嘗試都會產生新的查詢。</span><span class="sxs-lookup"><span data-stu-id="92c52-182">Any attempt to reference the results of a query will result in a new query.</span></span>

5. <span data-ttu-id="92c52-183">**相對資料篩選 –** CQD Connector 支援，但僅支援 *開始時間和\*\*結束時間* 維度。</span><span class="sxs-lookup"><span data-stu-id="92c52-183">**Relative Data Filtering –** Is supported in the CQD Connector, but only with the *Start Time* and *End Time* dimensions.</span></span> <span data-ttu-id="92c52-184">雖然 *日期維度* 可能是相對日期篩選的明顯選擇，但 *日期* 不會儲存為日期時間物件，因此不支援 Power BI 中的相對日期篩選。</span><span class="sxs-lookup"><span data-stu-id="92c52-184">Although the *Date* dimension may be the obvious choice for relative date filtering, *Date* is not stored as a date time object and thus does not support relative date filtering in Power BI.</span></span>

6. <span data-ttu-id="92c52-185">**政府社群雲端 (GCC) 支援 –** 對於 GCC 環境中的客戶，使用 Power BI Desktop 時，CQD Power BI Connector 將無法工作。</span><span class="sxs-lookup"><span data-stu-id="92c52-185">**Government Community Cloud (GCC) Support –** For customers in the GCC environment, the CQD Power BI Connector will not work when using Power BI Desktop.</span></span> <span data-ttu-id="92c52-186">CQD Power BI 連接器目前與 GCC 客戶的 Power BI 服務不相容。</span><span class="sxs-lookup"><span data-stu-id="92c52-186">The CQD Power BI connector is not presently compatible with the Power BI service for GCC customers.</span></span>

<span data-ttu-id="92c52-187">這些問題大部分是 Power BI 中 DirectQuery 連接器設計的限制，或是 CQD 資料模型設計的基本問題。</span><span class="sxs-lookup"><span data-stu-id="92c52-187">Most of these issues are either restrictions to DirectQuery connector design in Power BI or fundamental to the design of the CQD data model.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="92c52-188">疑難排解</span><span class="sxs-lookup"><span data-stu-id="92c52-188">Troubleshooting</span></span>

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a><span data-ttu-id="92c52-189">我嘗試使用日期欄做為日期分割器。</span><span class="sxs-lookup"><span data-stu-id="92c52-189">I'm trying to use the Date column as a Date slicer.</span></span> <span data-ttu-id="92c52-190">一旦將此欄的資料類型轉換成日期，就會收到此錯誤</span><span class="sxs-lookup"><span data-stu-id="92c52-190">As soon as I convert the data type of this column to Date, I get this error</span></span>

> <span data-ttu-id="92c52-191">**無法載入此** 視覺效果的資料：OLE DB 或 ODBC 錯誤：[Expression.Error] 無法將運算式折至資料來源。</span><span class="sxs-lookup"><span data-stu-id="92c52-191">**Couldn't load the data for this visual**: OLE DB or ODBC error: [Expression.Error] We couldn't fold the expression to the data source.</span></span> <span data-ttu-id="92c52-192">請嘗試更簡單的運算式。</span><span class="sxs-lookup"><span data-stu-id="92c52-192">Please try a simpler expression.</span></span>

<span data-ttu-id="92c52-193">Power BI Connector 不支援日期分割器。</span><span class="sxs-lookup"><span data-stu-id="92c52-193">Date slicers aren't supported with the Power BI Connector.</span></span> <span data-ttu-id="92c52-194">若要指定日期範圍，請對報表使用兩種篩選，指定小於及大於日期。</span><span class="sxs-lookup"><span data-stu-id="92c52-194">To specify a date range, apply two filters to the report, specifying a less than and greater than date.</span></span>

<span data-ttu-id="92c52-195">或者，如果您想要查看的日期是最近的日期，請申請相對日期篩選，只顯示過去 N 天/周/月的資料。</span><span class="sxs-lookup"><span data-stu-id="92c52-195">Alternatively, if the dates you want to view are recent, apply a relative date filter to show only data for the last N days/weeks/months.</span></span>

## <a name="error-codes"></a><span data-ttu-id="92c52-196">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="92c52-196">Error Codes</span></span>

<span data-ttu-id="92c52-197">由於 CQD Power BI Connector 在可建構的查詢類型方面，比瀏覽器應用程式限制較少，因此在建立查詢時，您偶爾可能會遇到許多錯誤。</span><span class="sxs-lookup"><span data-stu-id="92c52-197">Because the CQD Power BI Connector is less restricted than the browser app in terms of kinds of queries you can construct, you may occasionally encounter a number of errors while building your queries.</span></span> <span data-ttu-id="92c52-198">萬一您收到「CQDError」類型的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="92c52-198">In the event that you receive an error message of the type "CQDError.</span></span> <span data-ttu-id="92c52-199">RunQuery – 查詢執行錯誤」，請參照下列清單，提供 ErrorType 號碼，以疑難排解查詢可能的問題。</span><span class="sxs-lookup"><span data-stu-id="92c52-199">RunQuery – Query Execution Error", reference the list below with the ErrorType number provided in order to troubleshoot the possible issue with the query.</span></span> <span data-ttu-id="92c52-200">以下是您可能會遇到的 CQD Power BI Connector 最常見的錯誤類型代碼：</span><span class="sxs-lookup"><span data-stu-id="92c52-200">The following are the most common Error Type codes you may encounter with the CQD Power BI Connector:</span></span>

- <span data-ttu-id="92c52-201">**ErrorType 1 - 查詢結構錯誤：** 查詢結構錯誤通常是由連接器無法建立正確格式的查詢所導致。</span><span class="sxs-lookup"><span data-stu-id="92c52-201">**ErrorType 1 - Query Structure Error:** A query structure error is typically caused by the Connector failing to build a properly formatted query.</span></span> <span data-ttu-id="92c52-202">使用不支援的功能時，通常會發生此情況，如上述限制所指定。</span><span class="sxs-lookup"><span data-stu-id="92c52-202">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="92c52-203">請仔細檢查您並未針對該查詢使用任何計算結果欄或自訂視覺效果。</span><span class="sxs-lookup"><span data-stu-id="92c52-203">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="92c52-204">**ErrorType 2 - 查詢建立錯誤：** 查詢建立錯誤是由 CQD Connector 無法正確剖析您嘗試建立之查詢所導致。</span><span class="sxs-lookup"><span data-stu-id="92c52-204">**ErrorType 2 - Query Building Error:** A query building error is caused by the CQD Connector being unable to properly parse the query you are attempting to build.</span></span> <span data-ttu-id="92c52-205">使用不支援的功能時，通常會發生此情況，如上述限制所指定。</span><span class="sxs-lookup"><span data-stu-id="92c52-205">This happens most often when using unsupported functionality, as specified in the Limitations above.</span></span> <span data-ttu-id="92c52-206">請仔細檢查您並未針對該查詢使用任何計算結果欄或自訂視覺效果。</span><span class="sxs-lookup"><span data-stu-id="92c52-206">Double check that you are not using any calculated columns or custom visuals for that query.</span></span>

  - <span data-ttu-id="92c52-207">**ErrorType 5 - 執行超時：** 查詢在超時前已達到可能的最大執行時間。請嘗試在查詢中新增更多篩選，以限制其範圍。</span><span class="sxs-lookup"><span data-stu-id="92c52-207">**ErrorType 5 - Execution Timeout:** The query has reached the maximum possible runtime before timing out. Try adding more filters to the query in order to limit its scope.</span></span> <span data-ttu-id="92c52-208">縮小資料範圍通常是達成此目標最有效的方法。</span><span class="sxs-lookup"><span data-stu-id="92c52-208">Narrowing the data range is often the most effective way to achieve this.</span></span>

  - <span data-ttu-id="92c52-209">**ErrorType 7 - 無度量錯誤：** CQD 查詢需要量值才能運作。</span><span class="sxs-lookup"><span data-stu-id="92c52-209">**ErrorType 7 - No Measurements Error:** CQD queries require a measure in order to function.</span></span> <span data-ttu-id="92c52-210">請仔細檢查您的查詢是否包含量值。</span><span class="sxs-lookup"><span data-stu-id="92c52-210">Double check that your query includes measure.</span></span> <span data-ttu-id="92c52-211">CQD Connector 中的度量以其名稱 (加) 符號的匯總表示。</span><span class="sxs-lookup"><span data-stu-id="92c52-211">Measures in the CQD Connector are denoted by the aggregation (sum) symbol before their name.</span></span>

<span data-ttu-id="92c52-212">如果您遇到超出此範圍的其他錯誤，請通知 CQD 小組，以便我們協助疑難排解問題並視需要更新檔。</span><span class="sxs-lookup"><span data-stu-id="92c52-212">If you encounter any additional errors outside of this scope, please notify the CQD team so that we can help troubleshoot the issue and update the documentation as appropriate.</span></span>

## <a name="footnotes"></a><span data-ttu-id="92c52-213">註腳</span><span class="sxs-lookup"><span data-stu-id="92c52-213">Footnotes</span></span>

<span data-ttu-id="92c52-214">**<sup>1</sup>** 某些程式 (應用程式，例如 OneDrive) 可能會導致您的 [檔根資料夾》 變更;請確定 *Power BI 桌面 \\ 自訂連接器* 目錄已置於目前的根資料夾檔資料夾內。</span><span class="sxs-lookup"><span data-stu-id="92c52-214">**<sup>1</sup>** Certain processes and apps (e.g., OneDrive) may cause your Documents root folder to change; make sure that the *Power BI Desktop\\Custom Connectors* directory is placed inside of the current root folder Documents folder.</span></span>

<span data-ttu-id="92c52-215">**<sup>2</sup>** 您用於 CQD 的登入認證不需要與登入 Power BI Desktop 應用程式本身時使用的認證相同。</span><span class="sxs-lookup"><span data-stu-id="92c52-215">**<sup>2</sup>** The login credentials you use for CQD *do not* need to be the same credentials you use for logging into the Power BI Desktop app itself.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="92c52-216">常見問題集</span><span class="sxs-lookup"><span data-stu-id="92c52-216">Frequently asked questions</span></span>

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a><span data-ttu-id="92c52-217">何時會從 「Beta」狀態更新 Power BI 連接器</span><span class="sxs-lookup"><span data-stu-id="92c52-217">When will the Power BI Connector be updated from "Beta" status</span></span>

<span data-ttu-id="92c52-218">雖然有 Beta 標記，但 Power BI 的通話品質連接器是連接器的發行版本本，且已由 Power BI 小組正式簽署安全性，以反映這一點。</span><span class="sxs-lookup"><span data-stu-id="92c52-218">Despite the Beta tag, the Call Quality Connector for Power BI is the release version of the connector and has been officially security signed by the Power BI team to reflect this.</span></span> <span data-ttu-id="92c52-219">移除該 Beta 標記的認證程式非常廣泛，而且需要 Power BI 小組承諾提供連接器的直接支援。</span><span class="sxs-lookup"><span data-stu-id="92c52-219">The certification process to remove that Beta tag is an extensive one and requires a commitment from the Power BI team to provide direct support to the connector as well.</span></span> <span data-ttu-id="92c52-220">由於時間限制，Power BI 小組目前無法提供該支援及更廣泛的認證，但仍準備證明 Microsoft 通話品質連接器的安全性、真實性和一般功能。</span><span class="sxs-lookup"><span data-stu-id="92c52-220">Due to time constraints, the Power BI team is currently unable to provide that support and broader certification, but is still prepared to attest to the security, authenticity, and general functionality of the Microsoft Call Quality connector.</span></span>

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a><span data-ttu-id="92c52-221">為什麼與瀏覽器中的 Advanced CQD 相比，連接器看起來比較慢？</span><span class="sxs-lookup"><span data-stu-id="92c52-221">Why does the connector seem slower compared to Advanced CQD in the browser?</span></span> <span data-ttu-id="92c52-222">我可以做些什麼來改善績效</span><span class="sxs-lookup"><span data-stu-id="92c52-222">What can I do to improve performance</span></span>

<span data-ttu-id="92c52-223">在瀏覽器和連接器中，各種範本的查詢績效實際上是相同的。</span><span class="sxs-lookup"><span data-stu-id="92c52-223">Query performance for the various templates is actually the same in both the browser and in the connector.</span></span>  <span data-ttu-id="92c52-224">就像任何其他獨立應用程式一樣，Power BI 會將驗證和呈現時間加到我們的績效中。</span><span class="sxs-lookup"><span data-stu-id="92c52-224">Just like any other standalone app, Power BI adds its authentication and rendering time to our performance.</span></span> <span data-ttu-id="92c52-225">此外，差異在於同時執行查詢的數量。</span><span class="sxs-lookup"><span data-stu-id="92c52-225">In addition, the difference comes in the number of concurrent queries being run.</span></span> <span data-ttu-id="92c52-226">由於瀏覽器內版本的 CQD 有較不周全且資訊密度較濃的視覺效果選項，因此我們的大部分報告一次只能載入 2-3 個查詢。</span><span class="sxs-lookup"><span data-stu-id="92c52-226">Because the in-browser version of CQD had less well-developed and information-dense visualization options, most of our reports were limited to loading 2-3 queries at a time.</span></span> <span data-ttu-id="92c52-227">另一方面，連接器範本通常會顯示 20 多個並行查詢。</span><span class="sxs-lookup"><span data-stu-id="92c52-227">On the other hand, the connector templates often display 20+ concurrent queries.</span></span> <span data-ttu-id="92c52-228">如果您想要建立與舊版報表一樣回應的報表，請嘗試建立每個索引點不超過 2-3 個查詢的報表。</span><span class="sxs-lookup"><span data-stu-id="92c52-228">If you wish to build reports that are just as responsive as the older ones you were used to, try creating reports with no more than 2-3 queries per tab.</span></span>

<span data-ttu-id="92c52-229">詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="92c52-229">For more information, see the following articles:</span></span>

- [<span data-ttu-id="92c52-230">Power BI 優化指南</span><span class="sxs-lookup"><span data-stu-id="92c52-230">Optimization guide for Power BI</span></span>](/power-bi/guidance/power-bi-optimization)
- [<span data-ttu-id="92c52-231">DirectQuery 模型指南</span><span class="sxs-lookup"><span data-stu-id="92c52-231">DirectQuery model guidance</span></span>](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a><span data-ttu-id="92c52-232">我發現執行查詢時，會經常遇到 10，000 列的限制。</span><span class="sxs-lookup"><span data-stu-id="92c52-232">I find that I routinely run into the 10,000-row limit when running queries.</span></span> <span data-ttu-id="92c52-233">如何讓連接器返回超過 10，000 列</span><span class="sxs-lookup"><span data-stu-id="92c52-233">How can I get the connector to return more than 10,000 rows</span></span>

<span data-ttu-id="92c52-234">10，000 列的限制實際上是在 API 端指定，其設計可協助大幅提升績效，並降低因記憶體不足而造成查詢執行錯誤的風險。</span><span class="sxs-lookup"><span data-stu-id="92c52-234">The 10,000-row limit is actually specified on the API end, and it is designed to help significantly improve performance and reduce the risk of query execution errors resulting from low memory conditions.</span></span>

<span data-ttu-id="92c52-235">與其嘗試增加結果列數，最好根據連接器最佳做法來重新組織報表。</span><span class="sxs-lookup"><span data-stu-id="92c52-235">Instead of attempting to increase the result row count, it is best to restructure your reports according to connector best practices.</span></span> <span data-ttu-id="92c52-236">我們包含的範本是專為示範這些最佳做法所設計。</span><span class="sxs-lookup"><span data-stu-id="92c52-236">The templates we have included are designed to demonstrate these best practices.</span></span> <span data-ttu-id="92c52-237">如果可能的話，首先使用較寬、基數較低的維度來查看 KPI，例如月、年、日期、地區、國家/地區等。您可以在那裡向下向下切入到愈高基數維度。</span><span class="sxs-lookup"><span data-stu-id="92c52-237">Where possible, start by looking at your KPIs using broader, lower-cardinality dimensions, such as Month, Year, Date, Region, Country, etc. From there, you can drill down into increasingly higher-cardinality dimensions.</span></span> <span data-ttu-id="92c52-238">說明台和Location-Enhanced報表都提供此向下切入工作流程的範例。</span><span class="sxs-lookup"><span data-stu-id="92c52-238">The Helpdesk and Location-Enhanced Reports both provide good examples of this drill down workflow.</span></span>



## <a name="related-topics"></a><span data-ttu-id="92c52-239">相關主題</span><span class="sxs-lookup"><span data-stu-id="92c52-239">Related topics</span></span>

[<span data-ttu-id="92c52-240">使用 Power BI 分析 Teams 的 CQD 資料</span><span class="sxs-lookup"><span data-stu-id="92c52-240">Use Power BI to analyze CQD data for Teams</span></span>](CQD-Power-BI-query-templates.md)
