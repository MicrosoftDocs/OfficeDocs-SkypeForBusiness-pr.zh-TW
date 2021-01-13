---
title: CQD 開發範例
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
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 摘要：檢查通話品質儀表板的教學課程和開發範例。 通話品質儀表板是商務用 Skype 伺服器的工具。
ms.openlocfilehash: 193a03662d6f771b19c57017d909cc6574a755ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832723"
---
# <a name="cqd-development-samples"></a><span data-ttu-id="d2493-104">CQD 開發範例</span><span class="sxs-lookup"><span data-stu-id="d2493-104">CQD Development Samples</span></span>

<span data-ttu-id="d2493-105">**摘要：** 回顧通話品質儀表板的教學課程和開發範例。</span><span class="sxs-lookup"><span data-stu-id="d2493-105">**Summary:** Review a tutorial and development samples for Call Quality Dashboard.</span></span> <span data-ttu-id="d2493-106">通話品質儀表板是商務用 Skype 伺服器的工具。</span><span class="sxs-lookup"><span data-stu-id="d2493-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="d2493-107">本文提供在通話品質儀表板 (CQD) 上開發的教學課程和範例。</span><span class="sxs-lookup"><span data-stu-id="d2493-107">This article provides a tutorial and samples on development for Call Quality Dashboard (CQD).</span></span>

## <a name="call-quality-dashboard-cqd-development-samples"></a><span data-ttu-id="d2493-108">通話品質儀表板 (CQD) 開發範例</span><span class="sxs-lookup"><span data-stu-id="d2493-108">Call Quality Dashboard (CQD) Development Samples</span></span>

<span data-ttu-id="d2493-109">教程：使用 CQD 資料服務和知識庫服務 API 建立自訂的報表簡報。</span><span class="sxs-lookup"><span data-stu-id="d2493-109">Tutorial: Building Customized Report Presentation using the CQD Data Service and Repository Service API's.</span></span>

### <a name="introduction-to-cqd"></a><span data-ttu-id="d2493-110">CQD 簡介</span><span class="sxs-lookup"><span data-stu-id="d2493-110">Introduction to CQD</span></span>

<span data-ttu-id="d2493-111">CQD 提供對內部部署商務用 Skype Server 部署的匯總通話品質資訊的快速快捷的存取。</span><span class="sxs-lookup"><span data-stu-id="d2493-111">CQD offers quick and easy access to aggregated call quality information for on-premise Skype for Business Server deployments.</span></span> <span data-ttu-id="d2493-112">CQD 由三個元件組成： QoE 封存資料庫、Cube 及入口網站。</span><span class="sxs-lookup"><span data-stu-id="d2493-112">CQD consists of three components: the QoE Archive database, the Cube, and the Portal.</span></span> <span data-ttu-id="d2493-113">入口網站為主要簡報層，可進一步分為下列三個元件：</span><span class="sxs-lookup"><span data-stu-id="d2493-113">The Portal is the main presentation layer and can be further divided into the following three components:</span></span>

1. <span data-ttu-id="d2493-114">資料服務，可透過 [商務用 Skype Server 中的「呼叫品質」儀表板 (CQD) 中的「資料 API](data-api.md)」來存取驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="d2493-114">Data Service, which is accessible for authenticated users through the [Data API for Call Quality Dashboard (CQD) in Skype for Business Server](data-api.md).</span></span>

2. <span data-ttu-id="d2493-115">存放庫服務，可透過 [商務用 Skype Server 中的「儲存庫 (API」 CQD) ](repository-api.md)來存取已驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="d2493-115">Repository Service, which is accessible for authenticated users through the [Repository API for Call Quality Dashboard (CQD) in Skype for Business Server](repository-api.md).</span></span>

3. <span data-ttu-id="d2493-116">網頁入口網站，也就是 CQD 使用者所看到及與其互動的 HTML5 基礎介面。</span><span class="sxs-lookup"><span data-stu-id="d2493-116">Web portal, which is the HTML5 based interface that CQD users see and interact with.</span></span> <span data-ttu-id="d2493-117">這可供已驗證的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="d2493-117">This is accessible for authenticated users.</span></span>

<span data-ttu-id="d2493-118">網頁入口網站上顯示的報告會分組成「報表集」。</span><span class="sxs-lookup"><span data-stu-id="d2493-118">The reports shown on the web portal are grouped into "report sets".</span></span> <span data-ttu-id="d2493-119">此圖顯示含兩個報告的報表集。</span><span class="sxs-lookup"><span data-stu-id="d2493-119">The figure shows a report set with two reports.</span></span> <span data-ttu-id="d2493-120">下列儀表板中的每個報告均會顯示查詢結果中的正常通話次數、數個月的通話量和使用各種篩選的低通話百分比。</span><span class="sxs-lookup"><span data-stu-id="d2493-120">Each report in this dashboard below shows query results on number of good calls, poor calls and poor call percentage for several months, with various filters applied.</span></span> 

![CQD 範例報告](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

<span data-ttu-id="d2493-122">CQD 是以通話品質方法 (CQM) 建立，所以預設的報表集是設計為與 CQM 所引進的調查流程對齊。</span><span class="sxs-lookup"><span data-stu-id="d2493-122">CQD is created following the Call Quality Methodology (CQM), so the default set of reports is designed to align with the investigation flow introduced by CQM.</span></span> <span data-ttu-id="d2493-123">使用者也可以靈活地編輯或建立自訂報表，以符合其需求。</span><span class="sxs-lookup"><span data-stu-id="d2493-123">Users also have the flexibility to edit or create custom reports to meet their needs.</span></span> <span data-ttu-id="d2493-124">不過，由於有多種方式可顯示資料，因此 CQD 提供的視覺化效果可能無法完全滿足每一位使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="d2493-124">However, since there are multiple ways to visualize the data, the visualization provided by CQD may not fully address the needs of every user.</span></span> <span data-ttu-id="d2493-125">在這種情況下，使用者可以利用資料 APIs 及存放庫 APIs 來建立自訂報表頁面。</span><span class="sxs-lookup"><span data-stu-id="d2493-125">In such situations, a user can leverage the Data APIs and Repository APIs to create custom report pages.</span></span> <span data-ttu-id="d2493-126">我們將在本教學課程中深入一系列的範例。</span><span class="sxs-lookup"><span data-stu-id="d2493-126">We will go through a series of examples in this tutorial.</span></span>

### <a name="how-the-dashboard-consumes-the-data-service"></a><span data-ttu-id="d2493-127">儀表板使用資料服務的方式</span><span class="sxs-lookup"><span data-stu-id="d2493-127">How the dashboard consumes the data service</span></span>

<span data-ttu-id="d2493-128">流覽至 CQD 首頁時 (例如 http://localhost/cqd) ，已驗證及授權之使用者的報表集和對應報告會從存放庫服務中檢索。</span><span class="sxs-lookup"><span data-stu-id="d2493-128">When navigating to the CQD homepage (e.g. http://localhost/cqd), the report set and corresponding reports for an authenticated and authorized user will be retrieved from the Repository Service.</span></span> <span data-ttu-id="d2493-129">完整的 URL 會從報表集識別碼中構造，而每年月 (報表集識別碼是在 URL 中的 '/#/' 區段後面的整數數位，預設會在斜線) 之後的報表集識別碼結尾加上目前的年月。</span><span class="sxs-lookup"><span data-stu-id="d2493-129">A full URL will be constructed from the report-set ID and the year-month (report-set ID is the integer number after '/#/' section in URL, and by default the current year-month is appended at the end of the report-set ID after the slash).</span></span> <span data-ttu-id="d2493-130">報告定義會以 JSON 格式儲存，並在從存放庫服務中檢索時，將被當作資料服務的輸入使用。</span><span class="sxs-lookup"><span data-stu-id="d2493-130">The report definitions are stored in JSON format and when retrieved from the Repository Service, will then be used as input to the Data Service.</span></span> <span data-ttu-id="d2493-131">資料服務會根據輸入產生多維度運算式 (MDX) 查詢，然後對 Cube 執行這些 MDX 查詢，以取得每個報告的資料。</span><span class="sxs-lookup"><span data-stu-id="d2493-131">The Data Service generates Multi-Dimension expressions (MDX) queries based on the input and then run these MDX queries against the Cube to retrieve data for each report.</span></span> 

### <a name="building-customized-reports"></a><span data-ttu-id="d2493-132">建立自訂報告</span><span class="sxs-lookup"><span data-stu-id="d2493-132">Building customized reports</span></span>

<span data-ttu-id="d2493-133">CQD 在自訂報表時已有許多彈性，但在某些情況下，使用者可能會想要將資料匯總到在 CQD 中建立的多個報表上。</span><span class="sxs-lookup"><span data-stu-id="d2493-133">CQD already has a lot of flexibility in customizing reports, but there could be situations where users may want to aggregate data across multiple reports created in CQD.</span></span> <span data-ttu-id="d2493-134">例如，您可能需要建立報告，顯示表格中所有可能的有線通話組合的低通話百分比 (結果如圖) 所示：</span><span class="sxs-lookup"><span data-stu-id="d2493-134">For example, there could be a need to create a report that shows the poor call percentages of all possible combinations of wired calls in a table (a result like the figure):</span></span>

![CQD 表格](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

<span data-ttu-id="d2493-136">使用者可以使用 CQD 提供的入口網站流覽多個報告，以提取並記錄每個報告中的「不良通話」%，如果有許多需要收集的資料點，則可以費力。</span><span class="sxs-lookup"><span data-stu-id="d2493-136">Using the Portal provided by CQD, a user would have to navigate to multiple reports to extract and record the poor call % for each one, which can be laborious if there are many data points that need to be collected.</span></span> <span data-ttu-id="d2493-137">資料 APIs 為使用者提供一種程式設計方式，透過從資料服務 (（例如透過 AJAX 通話) ）來檢索資料，以完成此作業。</span><span class="sxs-lookup"><span data-stu-id="d2493-137">The Data APIs provide users with a programmatic way to accomplish this, by retrieving data from the Data Service (e.g. via AJAX calls).</span></span> 

 <span data-ttu-id="d2493-138">**範例1：簡易報表範例**</span><span class="sxs-lookup"><span data-stu-id="d2493-138">**Example 1: Simple report sample**</span></span>

<span data-ttu-id="d2493-139">請先讓我們做一個簡單的範例。</span><span class="sxs-lookup"><span data-stu-id="d2493-139">Let us take a simple example first.</span></span> <span data-ttu-id="d2493-140">如果我們想要在 HTML 頁面上顯示音訊良好資料流程，以及在 HTML 頁面上，在2015年2月的資料流程計數不正確，請如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="d2493-140">If we want to show the Audio Good Stream and the Audio Bad stream count of February 2015 on an HTML page like the figure:</span></span>

![CQD 範例報告](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

<span data-ttu-id="d2493-142">我們需要的是使用適當參數傳送資料服務的來電，並以 HTML 表格顯示查詢結果。</span><span class="sxs-lookup"><span data-stu-id="d2493-142">What we need is to send a call to the Data Service with the proper parameters, and show the query results in an HTML table.</span></span> <span data-ttu-id="d2493-143">下列為 JavaScript 程式碼的範例：</span><span class="sxs-lookup"><span data-stu-id="d2493-143">The following is a sample of the JavaScript code:</span></span>

```javascript        
$($.fn.freeFormReport = function (queries, urlApi, presentation) {
            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }
            });
        });
```

<span data-ttu-id="d2493-144">這個範例可進一步 deconstructed 三個步驟：</span><span class="sxs-lookup"><span data-stu-id="d2493-144">This example can be further deconstructed into three steps:</span></span>

1. <span data-ttu-id="d2493-145">在範例中建立查詢 (，此範例是在變數 ' query ' ) 中定義的。</span><span class="sxs-lookup"><span data-stu-id="d2493-145">Construct the query (in the example this is defined in the variable 'query').</span></span> <span data-ttu-id="d2493-146">此查詢定義為 JSON 物件，其中包含下列資料：</span><span class="sxs-lookup"><span data-stu-id="d2493-146">The query is defined as a JSON object, which includes the following data:</span></span>

   <span data-ttu-id="d2493-147">a.</span><span class="sxs-lookup"><span data-stu-id="d2493-147">a.</span></span> <span data-ttu-id="d2493-148">零個或多個維度。</span><span class="sxs-lookup"><span data-stu-id="d2493-148">Zero or more dimensions.</span></span> <span data-ttu-id="d2493-149">每個維度都是由 DataModelName 所表示。</span><span class="sxs-lookup"><span data-stu-id="d2493-149">Each dimension is indicated by a DataModelName.</span></span>

   <span data-ttu-id="d2493-150">b.</span><span class="sxs-lookup"><span data-stu-id="d2493-150">b.</span></span> <span data-ttu-id="d2493-151">零個或多個篩選。</span><span class="sxs-lookup"><span data-stu-id="d2493-151">Zero or more filters.</span></span> <span data-ttu-id="d2493-152">每個篩選器有：</span><span class="sxs-lookup"><span data-stu-id="d2493-152">Each filter has:</span></span>

   - <span data-ttu-id="d2493-153">DataModelName (將篩選設定) 的維度。</span><span class="sxs-lookup"><span data-stu-id="d2493-153">DataModelName (the dimension that will have the filter set).</span></span>

   - <span data-ttu-id="d2493-154">值 (將由運算元) 進行比較的值。</span><span class="sxs-lookup"><span data-stu-id="d2493-154">Value (the value that will be compared by the operand).</span></span>

   - <span data-ttu-id="d2493-155">運算元 (比較類型0，表示「等於」 ) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-155">Operand (comparison type, 0 means "Equal").</span></span>

     <span data-ttu-id="d2493-156">c.</span><span class="sxs-lookup"><span data-stu-id="d2493-156">c.</span></span> <span data-ttu-id="d2493-157">一或多個度量。</span><span class="sxs-lookup"><span data-stu-id="d2493-157">One or more measurements.</span></span>

2. <span data-ttu-id="d2493-158">透過 AJAX 呼叫，將查詢傳送至資料服務。</span><span class="sxs-lookup"><span data-stu-id="d2493-158">Send the query to Data Service via AJAX call.</span></span> <span data-ttu-id="d2493-159">需要提供下列要求參數：</span><span class="sxs-lookup"><span data-stu-id="d2493-159">The following request parameters need to be provided:</span></span>

   <span data-ttu-id="d2493-160">a.</span><span class="sxs-lookup"><span data-stu-id="d2493-160">a.</span></span> <span data-ttu-id="d2493-161">url (，其應該是 HTTP：//[ServerName]/QoEDataService/RunQuery) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-161">url (which should be http://[ServerName]/QoEDataService/RunQuery).</span></span>

   <span data-ttu-id="d2493-162">b.</span><span class="sxs-lookup"><span data-stu-id="d2493-162">b.</span></span> <span data-ttu-id="d2493-163">資料 (這是在 "query" 變數) 中所定義之 JSON 物件的字串表示。</span><span class="sxs-lookup"><span data-stu-id="d2493-163">data (this is the string representation of the JSON object defined in the 'query' variable).</span></span> <span data-ttu-id="d2493-164">資料服務會將查詢結果傳回成回叫功能成功的參數。</span><span class="sxs-lookup"><span data-stu-id="d2493-164">Data Service will return the query results as a parameter of the call back function for success.</span></span>

   <span data-ttu-id="d2493-165">c.</span><span class="sxs-lookup"><span data-stu-id="d2493-165">c.</span></span> <span data-ttu-id="d2493-166">輸入 QoEDataService 的 (，RunQuery 只接受「POST」要求) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-166">type (for QoEDataService, RunQuery only accepts 'POST' requests).</span></span>

   <span data-ttu-id="d2493-167">d.</span><span class="sxs-lookup"><span data-stu-id="d2493-167">d.</span></span> <span data-ttu-id="d2493-168">非同步 (旗標，指出 AJAX 呼叫應該是同步或非同步) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-168">async (a flag indicating whether the AJAX call should be synchronous or asynchronous).</span></span>

   <span data-ttu-id="d2493-169">e.</span><span class="sxs-lookup"><span data-stu-id="d2493-169">e.</span></span> <span data-ttu-id="d2493-170">contentType (應該是 "application/json" ) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-170">contentType (should be "application/json").</span></span>

   <span data-ttu-id="d2493-171">f.</span><span class="sxs-lookup"><span data-stu-id="d2493-171">f.</span></span> <span data-ttu-id="d2493-172">當 AJAX 呼叫成功完成時， (回叫功能) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-172">success (call-back function for when the AJAX call finishes successfully).</span></span>

   <span data-ttu-id="d2493-173">g.</span><span class="sxs-lookup"><span data-stu-id="d2493-173">g.</span></span> <span data-ttu-id="d2493-174">當 AJAX 呼叫失敗時， (錯誤處理函數的錯誤) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-174">error (error handling function for when AJAX call fails).</span></span>

3. <span data-ttu-id="d2493-175">將資料放入 div 元素 (中的程式碼範例中，當 AJAX 要求順利完成) 之後，就可以透過匿名的函數呼叫進行。</span><span class="sxs-lookup"><span data-stu-id="d2493-175">Put data into div elements in the HTML (in the example in the code, this is done via the anonymous function call after the AJAX request is completed successfully).</span></span>

<span data-ttu-id="d2493-176">將 JavaScript 程式碼包含在 HTML 頁面中，而頁面會顯示如圖所示的報表。</span><span class="sxs-lookup"><span data-stu-id="d2493-176">Enclosing the JavaScript code into an HTML page, and the page will show a report like the one shown in the figure.</span></span> <span data-ttu-id="d2493-177">完整的 html 如下：</span><span class="sxs-lookup"><span data-stu-id="d2493-177">The full html is as follows:</span></span>

```javascript
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
</head>
<body>
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        $($.fn.freeFormReport = function (queries, urlApi, presentation) {

            var query = {
                Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                Filters: [{
                    DataModelName: '[StartDate].[Month]',
                    Value: '[2015-02-01T00:00:00]',
                    Operand: 0
                }],
                Measurements:
                    [{ DataModelName: '[Measures].[Audio Good Streams JPDR Count]' },
                     { DataModelName: '[Measures].[Audio Poor Streams JPDR Count]' },]
            };            

            $.ajax({
                url: 'http://localhost/QoEDataService/RunQuery',
                data: JSON.stringify(query),
                type: 'POST',
                async: true,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    //This is the jQuery syntax for document.GetElementById()
                    $('#AudioGoodStreamsJPDRCount').html(data.DataResult[0][1]);
                    $('#AudioPoorStreamsJPDRCount').html(data.DataResult[0][2]);
                }
                error: function (error) {
                    alert('Error getting data, check that the data service is running and that the URL is correct.');
           }

            });
        });
    </script>
    <table border="1">
        <tr>
            <td></td>
            <td><div>Audio Good Streams JPDR Count</div></td>
            <td><div>Audio Poor Streams JPDR Count</div></td>
        </tr>
        <tr>
            <td>February</td>
            <td><div id="AudioGoodStreamsJPDRCount"></div></td>
            <td><div id="AudioPoorStreamsJPDRCount"></div></td>
        </tr>
    </table>
</body>
</html>
```

<span data-ttu-id="d2493-178">到目前為止，報表仍然非常簡單。</span><span class="sxs-lookup"><span data-stu-id="d2493-178">So far, the report is still very simple.</span></span> <span data-ttu-id="d2493-179">使用者可以新增更多度量、維度或篩選，以自訂報告。</span><span class="sxs-lookup"><span data-stu-id="d2493-179">The user can add more measurements, dimensions, or filters to customize the report.</span></span> <span data-ttu-id="d2493-180">例如，如果您想要顯示 AppSharing 的通話百分比不佳，必須新增相關的 AppSharing 度量。</span><span class="sxs-lookup"><span data-stu-id="d2493-180">For example, if you want to show AppSharing poor call percentage, then a new measurement regarding AppSharing needs to be added.</span></span> <span data-ttu-id="d2493-181">如果您想要顯示所有的 TCP 呼叫 v.s。</span><span class="sxs-lookup"><span data-stu-id="d2493-181">If you want to show all TCP calls v.s.</span></span> <span data-ttu-id="d2493-182">UDP 通話，應新增有關運輸類型的新維度。</span><span class="sxs-lookup"><span data-stu-id="d2493-182">UDP calls, a new dimension regarding transportation type should be added.</span></span> <span data-ttu-id="d2493-183">如果您想要顯示特定大樓內不良通話的數目，則應新增新的篩選器，以選取要與該大樓進行的通話。</span><span class="sxs-lookup"><span data-stu-id="d2493-183">If you want to show the number of poor calls within a specific building, then a new filter should be added to select the calls to and from that building.</span></span>

 <span data-ttu-id="d2493-184">**範例2：報告定義範例**</span><span class="sxs-lookup"><span data-stu-id="d2493-184">**Example 2: Report definition sample**</span></span>

<span data-ttu-id="d2493-185">在建立查詢時，某人可能很難判斷如何撰寫度量/維度/篩選及其對應值的完整清單。</span><span class="sxs-lookup"><span data-stu-id="d2493-185">It might be difficult for someone to figure out how to write the full list of measurements/dimensions/filters and their corresponding values when constructing a query.</span></span> <span data-ttu-id="d2493-186">在此情況下，您可以移至入口網站、使用報表編輯器建立報告，以及查看報告定義的 JSON 字串，然後將定義複製到自訂報告中。</span><span class="sxs-lookup"><span data-stu-id="d2493-186">In this case, you can go to the Portal, build a report using the report editor, and view the JSON string of the report definition, and then copy the definition into a custom report.</span></span> 

<span data-ttu-id="d2493-187">在此範例中，我們會建立一個網頁，如下圖所示，使用者可以在其中輸入任何現有報表集的識別碼 (或報表) ，並在網頁上顯示報表集或報表的定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-187">In this example, we will create a web page like the one shown in the figure where a user can enter the ID of any existing report set (or report) and show the definition of the report set or report on the web page.</span></span> <span data-ttu-id="d2493-188">然後，使用者可以將每個報告的 JSON 字串插入類似于範例1所示的程式碼，並建立使用者想要的任何自訂報告。</span><span class="sxs-lookup"><span data-stu-id="d2493-188">The user can then plug the JSON string of each report into code similar to the one shown in Example 1 and construct any customized report the user desires.</span></span> 

![CQD 範例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

<span data-ttu-id="d2493-190">若要建立「報告定義檢視器」工具，我們需要傳送呼叫至存放庫服務，以取得所需之每個報告集之定義的 JSON 字串表示。</span><span class="sxs-lookup"><span data-stu-id="d2493-190">To create the report definition viewer tool, we need to send calls to Repository Service to retrieve the JSON string representations of the definitions of every report-set we want.</span></span> <span data-ttu-id="d2493-191">根據指定的報表集識別碼，存放庫 API 將會傳回報表集定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-191">The Repository API will return report-set definition based on a given report set ID.</span></span> 

<span data-ttu-id="d2493-192">快速範例如下所示，此程式碼包含一個簡單的範例，可將查詢傳送至存放庫服務，以根據識別碼取得存放庫專案的內容。</span><span class="sxs-lookup"><span data-stu-id="d2493-192">A quick example is as follows, the code contains a block that is a simple example to send a query to the Repository service to get the contents of a repository item based on its identifier.</span></span> <span data-ttu-id="d2493-193">和下一個程式碼 (processReportSetData 方法) 會傳送 AJAX 呼叫，以取得該報告集內每個報告的定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-193">And the next portion of code (processReportSetData method) is sending AJAX calls to get the definition of each report within that report set.</span></span> <span data-ttu-id="d2493-194">由於 CQD 網頁入口網站中的識別碼是報表集的識別碼，所以 AJAX 呼叫會傳回報表集專案。</span><span class="sxs-lookup"><span data-stu-id="d2493-194">Since the ID in the CQD web portal is the ID of a report set, the AJAX call will return a report set item.</span></span> <span data-ttu-id="d2493-195">您可以在 [ [取得專案](get-items.md)] 中找到存放庫 API 的詳細資訊，尤其是 GetItems。</span><span class="sxs-lookup"><span data-stu-id="d2493-195">More detail on the Repository API and specifically, GetItems, can be found in the [Get Items](get-items.md).</span></span> 

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta http-equiv="x-content-type-options" content="nosniff">
    <title>CQD Report definition viewer</title>
</head>
<body>    
    <div style="font-size:32pt">CQD Report definition viewer</div>
        <p>ReportSet Id: <input id="reportSetId" /></p>
        <button onclick='loadReportSet()'>Load</button>
        <div id="Report"></div>
    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <script>
        var urlRepositoryApi = 'http://localhost/QoERepositoryService/repository/item/';

        var loadReportSet = function ()
        {
            var reportSetId = document.getElementById('reportSetId').value;

            $.ajax({
                url: urlRepositoryApi + reportSetId,
                data: '',
                type: 'GET',
                async: false,
                contentType: 'application/json;charset=utf-8',
                success: function (data) {
                    var reportSetDiv = document.getElementById('Report');
                    reportSetDiv.innerHTML = '';
                    processReportSetData(reportSetDiv, data);
                },
                error: function (error) {
                    alert('Error getting Report, check that the qoe data service is running and url is correct.');
                }
            });
        };

        var processReportSetData = function (divReportSet, reportSetDef) {
             //show the report set definition like Title, Description, etc
            showReportSetDefinition(divReportSet, reportSetDef);

            //for each Report in the Reportset, get the Report definition from the Repository Service
            for (var i = 0; i < reportSetDef.subItemIds.length; i++)
            {
                //the reportId is in the subItemIds array.  This is not shown in the CQD UI at all
                var reportId = reportSetDef.subItemIds[i];

                var divReport = document.createElement('div');
                divReport.style.margin = '12px';                
                divReportSet.appendChild(divReport);

                //retrieve the report definition with the reportId
                $.ajax({
                    url: urlRepositoryApi + reportId,
                    data: '',
                    type: 'GET',
                    async: false,
                    contentType: 'application/json;charset=utf-8',
                    success: function (reportData) {
                        processReportData(divReport, reportData, reportId);
                    },
                    error: function (error) {
                        alert('Error getting Report ' + reportId.toString() + ', check that the qoe data service is running and url is correct.');
                    }
                });
            }
        };

        //helper function to render the ReportSet definition
        var showReportSetDefinition = function (divReportSet, reportSetDef) {
            var div = document.createElement('div');
            ReportSetDefinition = reportSetDef.content;
            txt = document.createTextNode(ReportSetDefinition);
            div.style.margin = '12px';
            div.appendChild(txt);
            divReportSet.appendChild(div);
        };

        //show the report definition
        var processReportData = function (divReport, reportData, itemId) {
            if (divReport != undefined &amp;&amp; reportData.content != undefined) {
                var Report = JSON.parse(reportData.content);

                var divReportId = document.createElement('div');
                var subItemId = reportData.subItemIds.length > 0 ? reportData.subItemIds[0].toString() : 'none';
                divReportId.innerHTML = 'ItemId: ' + itemId.toString() + ' (' + Report.Title + ') [subItemId:' + subItemId + ']';
                divReport.appendChild(divReportId);

                var divReportDef = document.createElement('div');
                txt = document.createTextNode(JSON.stringify(Report));
                divReportDef.style.margin = '12px';
                divReportDef.appendChild(txt);                            
                divReport.appendChild(divReportDef);
            }
        };
    </script>
</body>
</html>
```

<span data-ttu-id="d2493-196">上述會產生如圖所示的網頁，但在初次造訪) 時未使用報表定義 (。</span><span class="sxs-lookup"><span data-stu-id="d2493-196">The above will result in a web page like the one in the figure (without the report definition upon initial visit).</span></span> <span data-ttu-id="d2493-197">從 CQD 入口網站取得報表集識別碼。 (入口網站 URL 後 (它會是 '/#/' 登入 CQD 例如。</span><span class="sxs-lookup"><span data-stu-id="d2493-197">Get the report set ID from CQD portal (it is after '/#/' sign in CQD portal URL (E.g.</span></span> <span data-ttu-id="d2493-198">在第一個圖中，報表集識別碼為 3024) ，並將此報表集識別碼放入此網頁的輸入區段中。</span><span class="sxs-lookup"><span data-stu-id="d2493-198">in the first figure the report set ID is 3024), and put this report set ID into the input section of this web page.</span></span> <span data-ttu-id="d2493-199">按下「載入」按鈕，並查看完整的定義 (度量、維度、篩選器清單) 的報表集。</span><span class="sxs-lookup"><span data-stu-id="d2493-199">Press the "load" button and see the full definition (measurements, dimensions, filters lists) of the report set.</span></span>

<span data-ttu-id="d2493-200">在 [摘要] 中，為了快速取得報告/報表集的完整定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-200">In summary, in order to quickly get the full definition of a report/report set.</span></span> <span data-ttu-id="d2493-201">步驟如下：</span><span class="sxs-lookup"><span data-stu-id="d2493-201">The steps are:</span></span>

1. <span data-ttu-id="d2493-202">移至入口網站，並使用 [查詢編輯器] 自訂報告 (按一下報表上方的 [編輯] 按鈕，即可編輯、新增、移除度量/維度/篩選，然後儲存報表) 。</span><span class="sxs-lookup"><span data-stu-id="d2493-202">Go to the Portal and use the query editor to customize a report (click the "Edit" button above a report to edit, add, remove measurements/dimensions/filters, and then save the report).</span></span>

2. <span data-ttu-id="d2493-203">從 URL (的報表集識別碼，在 [/#/"登入 URL]) 後取得整數。</span><span class="sxs-lookup"><span data-stu-id="d2493-203">Get the report set ID from URL (the integer after '/#/' sign in URL).</span></span>

3. <span data-ttu-id="d2493-204">啟動範例2所建立的此報告定義網頁，並輸入報表集識別碼，並在) 中使用 (，以在資料 API 呼叫中使用的報表集的完整定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-204">Launch this Report Definition web page created in Example 2, and enter the report set ID and retrieve the full definition of a report set (to use in Data API calls).</span></span>

   <span data-ttu-id="d2493-205">**範例3：計分卡範例**</span><span class="sxs-lookup"><span data-stu-id="d2493-205">**Example 3: Scorecard sample**</span></span>

<span data-ttu-id="d2493-206">較為複雜的工作時間。</span><span class="sxs-lookup"><span data-stu-id="d2493-206">Time for a more complicated task.</span></span> <span data-ttu-id="d2493-207">若要建立網頁（如圖），該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="d2493-207">What if we want to create a web page like the figure?</span></span> <span data-ttu-id="d2493-208">我們需要以範例2所產生之網頁的說明來更新範例1， (，以取得任何報表) 的完整定義，以便處理大量的資料。</span><span class="sxs-lookup"><span data-stu-id="d2493-208">We need to update Example 1, (with the help of the web page generated in Example 2 to retrieve the full definition of any report) so that we can handle larger amount of data.</span></span>

<span data-ttu-id="d2493-209">在此情況下，我們需要更新度量和維度清單。</span><span class="sxs-lookup"><span data-stu-id="d2493-209">In this case, we need to update the measurement and dimension list.</span></span> <span data-ttu-id="d2493-210">若要瞭解如何新增/編輯度量和/或維度的方式，請遵循範例2中的指示，並取得完整的報表定義，包括完整的度量和維度清單。</span><span class="sxs-lookup"><span data-stu-id="d2493-210">The way to figure out how to add/edit a measurement and/or a dimension is to follow the instructions in Example 2, and retrieve the full report definition, including the full measurement and dimension lists.</span></span> <span data-ttu-id="d2493-211">將完整的報告定義插入範例程式碼。</span><span class="sxs-lookup"><span data-stu-id="d2493-211">Plug the full report definition into the sample code.</span></span> 

<span data-ttu-id="d2493-212">以下是從範例1所提供之範例的圖中，取得計分卡頁面的詳細步驟：</span><span class="sxs-lookup"><span data-stu-id="d2493-212">Here are the detailed steps to get to the scorecard page in the figure from the sample provided in Example 1:</span></span>

1. <span data-ttu-id="d2493-213">將 ' 查詢 ' 變數中的測量值  `[Measures].[Audio Good Streams JPDR Count]` 更新 `[Measures].[Audio Poor Streams JPDR Count]` 為 and to to `[Measures].[AudioPoorJPDRPercentage]` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-213">Update Measurements in the 'query' variable from  `[Measures].[Audio Good Streams JPDR Count]` and `[Measures].[Audio Poor Streams JPDR Count]` to `[Measures].[AudioPoorJPDRPercentage]`.</span></span> 

2. <span data-ttu-id="d2493-214">更新篩選。</span><span class="sxs-lookup"><span data-stu-id="d2493-214">Update the filters.</span></span> <span data-ttu-id="d2493-215">範例1中的篩選器 JSON 資料有一個篩選，它是在維度上設定  `[StartDate].[Month]` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-215">The JSON data for Filters in Example 1 has one filter, which is set on the dimension  `[StartDate].[Month]`.</span></span> <span data-ttu-id="d2493-216">因為篩選器是一個 JSON 陣列，所以可以將其他維度新增至篩選清單。</span><span class="sxs-lookup"><span data-stu-id="d2493-216">Since Filters is a JSON array, additional dimensions can be added to the list of filters.</span></span> <span data-ttu-id="d2493-217">例如，若要取得 "currentMonth" 的有線通話中的伺服器-用戶端，我們應該會有下列篩選：</span><span class="sxs-lookup"><span data-stu-id="d2493-217">For example, to get the server-client inside wired calls for the "currentMonth", we should have the following filters:</span></span>

   ```javascript
   Filters: [
     { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
    {
        "DataModelName": "[Scenarios].[ScenarioPair]",
         "Caption": " Server-Inside-wired,Client-Inside-wired",
         "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
         "Operand": 0,
         "UnionGroup": ""
     },

     { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
   ],
   ```

   <span data-ttu-id="d2493-218">`[Scenarios].[ScenarioPair]`將維度設定為相等 `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-218">Here the dimension  `[Scenarios].[ScenarioPair]` is set to equal `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`.</span></span> <span data-ttu-id="d2493-219">`[Scenario.][ScenarioPair]`是建立以簡化報表建立的特殊維度。</span><span class="sxs-lookup"><span data-stu-id="d2493-219">The  `[Scenario.][ScenarioPair]` is a special dimension created to simplify report creation.</span></span> <span data-ttu-id="d2493-220">它具有對應的六個值 `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-220">It has six values corresponding to `[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`.</span></span> <span data-ttu-id="d2493-221">所以，請不要使用6個篩選的組合來定義案例，只需要使用1個篩選。</span><span class="sxs-lookup"><span data-stu-id="d2493-221">So instead of using a combination of 6 filters to define a scenario, we only need to use 1 filter.</span></span> <span data-ttu-id="d2493-222">在我們的範例中，此值  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` 會轉譯為： first 為 server，第二個不是伺服器、第二個為內部、第二個內部的連線類型，而第二個連線類型是有線的，這是「伺服器-用戶端接線」的確切定義。</span><span class="sxs-lookup"><span data-stu-id="d2493-222">In our example, the value  `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]` translates to the scenario where: first is server, second is not server, first is inside, second is inside, first connection type is wired, and second connection type is wired, which is the exact definition of "Server-Client-Inside Wired".</span></span>

3. <span data-ttu-id="d2493-223">針對每個案例建立一個篩選集合。</span><span class="sxs-lookup"><span data-stu-id="d2493-223">Create one filter set per scenario.</span></span> <span data-ttu-id="d2493-224">在 [計分卡] 中的每一列都代表不同的情況，當尺寸及量值保持相同) 時，這會是不同的篩選 (。</span><span class="sxs-lookup"><span data-stu-id="d2493-224">Each row in the scorecard, in the figure, represents a different scenario, which will be a different filter (while the dimensions and measurements stay the same).</span></span> 

4. <span data-ttu-id="d2493-225">分析 AJAX 呼叫的結果，並將其放在資料表的正確位置。</span><span class="sxs-lookup"><span data-stu-id="d2493-225">Parse the results from the AJAX calls and place them in the correct position of the table.</span></span> <span data-ttu-id="d2493-226">由於這大多是 HTML 並 JavaScript 操作，我們不會深入討論這裡的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d2493-226">Since this is mostly HTML and JavaScript manipulation, we will not go into the details here.</span></span> <span data-ttu-id="d2493-227">相反地，程式碼會在附錄 A 中提供。</span><span class="sxs-lookup"><span data-stu-id="d2493-227">Instead, the code is provided in Appendix A.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d2493-228">如果已啟用「跨原始資源分享 (CORS) ，使用者可能會遇到錯誤，例如「沒有」存取控制--控制項-允許」標頭存在於要求的資源上。</span><span class="sxs-lookup"><span data-stu-id="d2493-228">If Cross-Origin Resource Sharing (CORS) is enabled, users may encounter errors like "No 'Access-Control-Allow-Origin' header is present on the requested resource.</span></span> <span data-ttu-id="d2493-229">來源 ' null ' 因此不允許存取」。</span><span class="sxs-lookup"><span data-stu-id="d2493-229">Origin 'null' is therefore not allowed access".</span></span> <span data-ttu-id="d2493-230">若要解決此問題，請將 HTML 檔案放在安裝入口網站的資料夾底下 (預設會是 `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-230">To resolve the issue, place the HTML file under the folder where the Portal is installed (by default, it should be `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`.</span></span> <span data-ttu-id="d2493-231">然後透過具有 URL 的任何瀏覽器存取 html  `http://<servername>/cqd/<html_file_name>` 。</span><span class="sxs-lookup"><span data-stu-id="d2493-231">Then access the html through any browser with the URL  `http://<servername>/cqd/<html_file_name>`.</span></span> <span data-ttu-id="d2493-232"> (local CQD 儀表板的預設 URL  `http://<servername>/cqd.`) </span><span class="sxs-lookup"><span data-stu-id="d2493-232">(The default URL for local CQD dashboard is  `http://<servername>/cqd.`)</span></span> 

### <a name="appendix-a"></a><span data-ttu-id="d2493-233">附錄 A</span><span class="sxs-lookup"><span data-stu-id="d2493-233">Appendix A</span></span>

<span data-ttu-id="d2493-234">範例 3 (的 HTML 程式碼) 範例：</span><span class="sxs-lookup"><span data-stu-id="d2493-234">HTML code for Example 3 (Scorecard sample):</span></span>

```html
<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <meta http-equiv='cache-control' content='no-cache'>
    <meta http-equiv='expires' content='0'>
    <meta http-equiv='pragma' content='no-cache'>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Scoreboard Sample</title>

    <style>
        .row {
            margin-right: -15px;
            margin-left: -15px;
            display: table-row;
        }
        .col-md-3 {
            width: 25%;
            display: table-cell;
        }
        .col-md-2 {
            width: 16.66666667%;
            display: table-cell;
        }
        .col-md-1 {
            width: 8.33333333%;
            display: table-cell;
        }

    </style>
</head>
<body>    

    <!-- Third party Libraries -->
    <script src="OpenSourceSoftware/Scripts/jquery-2.1.1.js"></script>

    <table id="ScoreCardTable" style="margin:100px">
        <tr>
            <td width="250px" style="text-align: center; font-size: 24px; font-family: 'Segoe UI'; font-weight: lighter; color: white; background-color: #505050">
                <div style="margin:10px">Scoreboard Sample</div>
            </td>
            <td width="1200px">
                <div style="margin:10px;background-color:#D9D9D9" >
                    <div class="row" id="Header" style="font-size:24px;font-family:'Segoe UI';font-weight:lighter;color:white;background-color:#505050">
                        <div class="col-md-3">Poor Call %</div>
                        <div class="col-md-1">Month1</div>
                        <div class="col-md-1">Month2</div>
                        <div class="col-md-1">Month3</div>
                        <div class="col-md-1">Month4</div>
                        <div class="col-md-1">Month5</div>
                        <div class="col-md-1">Month6</div>
                    </div>                    
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wired</div></div>
                    <div class="row" id="SS"><div class="col-md-3">Server-Server</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WWI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WIWO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Wireless</div></div>
                    <div class="row" id="SWFI"><div class="col-md-3">Server-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SWFO"><div class="col-md-3">Server-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFIWFI"><div class="col-md-3">Client-Client (inside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="WFOWFO"><div class="col-md-3">Client-Client (outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Mobile/Broadband</div></div>
                    <div class="row" id="SMP"><div class="col-md-3">Server-MobilePhone</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row" id="SMBB"><div class="col-md-3">Server-MobileBroadBand</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                    <div class="row"><div class="col-md-3" style="font-weight:bold">Lync Web App</div></div>
                    <div class="row" id="SLWA"><div class="col-md-3">Server-Client (inside &amp; outside)</div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div><div class="col-md-1"></div></div>
                </div>
            </td>
        </tr>
        <tr>
            <td><br /></td>
        </tr>
    </table>

    <script>

        $(function () {
            var month_names_short = ['NAM', 'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec'];
            var currentMonth = '2015-3';

            //update the header with the month names
            var row = document.getElementById('Header');
            var numMonthsToShow = 6;
            for (var m = numMonthsToShow-1; m >= 0; m--) {
                var dateSplit = currentMonth.split('-');
                var monthInt = parseInt(dateSplit[1]);
                var yearInt = parseInt(dateSplit[0]);
                monthInt = monthInt - m;
                if (monthInt < 1)
                {
                    monthInt += 12;
                    yearInt--;
                }
                row.children[numMonthsToShow-m].innerHTML = month_names_short[monthInt];
            }

            var queries = [
            {
                Label: "Server-Server",
                ID: "SS",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]'}],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Server-Inside-wired",
                          "Value": "[1]&amp;[1]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: ""}
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]'}],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWI",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Inside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWO",
                Query:
                {
                  Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                  Filters: [
                      {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": " Server-Inside-wired,Client-Outside-wired",
                          "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                      },
                      { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                      { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                  ],
                  Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                  Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                 }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WWI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-wired,Client-Inside-wired",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }
            ,
            {
                Label: "Client-Client (outside)",
                ID: "WIWO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wired,Client-Outside-Wired",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wired]&amp;[Wired]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (inside)",
                ID: "SWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Server-Inside-wired,Client-Inside-wifi",
                            "Value": "[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-Client (outside)",
                ID: "SWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                         {
                             "DataModelName": "[Scenarios].[ScenarioPair]",
                             "Caption": " Server-Inside-wired,Client-Outside-wifi",
                             "Value": "[1]&amp;[0]&amp;[1]&amp;[0]&amp;[Wired]&amp;[Wifi]",
                             "Operand": 0,
                             "UnionGroup": ""
                         },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (inside)",
                ID: "WFIWFI",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                            "DataModelName": "[Scenarios].[ScenarioPair]",
                            "Caption": " Client-Inside-Wifi,Client-Inside-Wifi",
                            "Value": "[0]&amp;[0]&amp;[1]&amp;[1]&amp;[Wifi]&amp;[Wifi]",
                            "Operand": 0,
                            "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Client-Client (outside)",
                ID: "WFOWFO",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {
                          "DataModelName": "[Scenarios].[ScenarioPair]",
                          "Caption": "Client-Outside-Wifi,Client-Outside-Wifi",
                          "Value": "[0]&amp;[0]&amp;[0]&amp;[0]&amp;[Wifi]&amp;[Wifi]",
                          "Operand": 0,
                          "UnionGroup": ""
                        },
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                        { DataModelName: '[StreamType].[StreamType]', Caption: "Valid", Value: "[False]", Operand: 0, UnionGroup: "" }
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobilePhone",
                ID: "SMP",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "AndroidLync | iPhoneLync | WPLync","Value": "[AndroidLync],[iPhoneLync],[WPLync]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 },
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-MobileBroadBand",
                ID: "SMBB",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[Second Network Connection Type].[Network Connection Detail]","Caption": "MobileBB","Value": "[MobileBB]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second Is Server].[Agent]","Caption": "Client ","Value": "[0]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            },
            {
                Label: "Server-LWA",
                ID: "SLWA",
                Query:
                {
                    Dimensions: [{ DataModelName: '[StartDate].[Month]' }],
                    Filters: [
                        {"DataModelName": "[First Is Server].[Agent]","Caption": "Server","Value": "[1]","Operand": 0,"UnionGroup": ""},
                        {"DataModelName": "[Second User Agent].[User Agent Type]","Caption": "LWA","Value": "[LWA]","Operand": 0,"UnionGroup": ""},
                        { DataModelName: '[StartDate].[Month]', Value: currentMonth, Operand: 0 }                       
                    ],
                    Measurements: [{ DataModelName: '[Measures].[AudioPoorJPDRPercentage]' }],
                    Trend: { EnableTrend: true, SpanCount: numMonthsToShow, TrendDate: currentMonth, Type: 0 }
                }
            }

            ];

            //get the overall corpnet data
            for (var i = 0; i < queries.length; i++) {
                $.ajax({

                    url: 'http://localhost/QoEDataService/RunQuery',
                    data: JSON.stringify(queries[i].Query),
                    type: 'POST',
                    async: false,
                    withCredentials: true,
                    contentType: 'application/json;charset=utf-8',
                    success: function (data) {

                        //find the table row corresponding to the name of this query
                        var row = document.getElementById(queries[i].ID);

                        //update the values for each month
                        for (var m = 0; m < data.DataResult.length; m++)
                        {
                            row.children[m + 1].innerHTML = data.DataResult[m][1].toFixed(2).toString();
                        }

                    },
                    error: function (error) {
                        var row = document.getElementById(queries[i].ID);
                        row.children[1].innerHTML = 'error';
                    }
                });
            }
        });
    </script>
</body>
</html>
```
