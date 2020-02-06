---
title: CQD 開發範例
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
ms.collection: IT_Skype16
ms.assetid: 8ca9bf7a-2d6f-48d5-a821-531009726525
description: 摘要：請參閱通話品質儀表板的教學課程與開發範例。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 22b0e44ca3bf2e80d8d2674d0af1e6a8f157dc23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816872"
---
# <a name="cqd-development-samples"></a>CQD 開發範例

**摘要：** 查看通話品質儀表板的教學課程與開發範例。 [通話品質儀表板] 是商務用 Skype Server 的工具。

本文提供在通話品質儀表板（CQD）上開發的教學課程和範例。

## <a name="call-quality-dashboard-cqd-development-samples"></a>通話品質儀表板（CQD）開發範例

教學課程：使用 CQD 資料服務和知識庫服務 API 來建立自訂的報表簡報。

### <a name="introduction-to-cqd"></a>CQD 簡介

CQD 可讓您快速且輕鬆地存取內部部署商務用 Skype Server 部署的匯總通話品質資訊。 CQD 包含三個元件： [QoE] 封存資料庫、立方體及入口網站。 入口網站是主要的簡報圖層，可進一步分為下列三個元件：

1. 資料服務，可透過[商務用 Skype Server 中的 [通話品質儀表板] （CQD），透過資料 API](data-api.md)來存取已驗證的使用者。

2. 您可以透過[商務用 Skype Server 中的 [呼叫品質儀表板（CQD）](repository-api.md)] 的 [知識庫 API] 來存取 [知識庫服務]。

3. 網頁入口網站，它是 CQD 使用者查看及互動的 HTML5 式介面。 這對於經過驗證的使用者可以存取。

網頁入口網站上顯示的報表會歸入 [報表集]。 此圖顯示含有兩個報表的報表集合。 此儀表板中的每個報告都會顯示已套用各種篩選的 [良好通話數]、[通話較差] 與 [幾個月的通話百分比差] 的查詢結果。 

![CQD 範例報告](../../media/9e0723f7-f850-4d11-9ecd-7e8e013a8bed.png)

CQD 是在通話品質方法（CQM）之後建立，所以預設的報告集是與 CQM 所引進的調查流程相符。 使用者也可以靈活地編輯或建立自訂報表以滿足其需求。 不過，由於有多種方式可哥視化資料，因此 CQD 提供的視覺效果可能無法完全滿足每個使用者的需求。 在這種情況下，使用者可以利用資料 Api 和知識庫 Api 來建立自訂的報表頁面。 我們將在本教學課程中逐步完成一系列範例。

### <a name="how-the-dashboard-consumes-the-data-service"></a>儀表板如何使用資料服務

流覽至 CQD 首頁時（例如http://localhost/cqd)，已驗證且已授權的使用者的報告集及對應報告將會從知識庫服務中檢索）。 完整的 URL 會從報表集識別碼和年-月份來構造（在 URL 中，報表集識別碼是 "/#/" 區段後的整數），而且預設情況下，會在報表集 ID 的結尾加上斜線之後，附加目前的年-月份。 報告定義會以 JSON 格式儲存，且從知識庫服務中進行檢索時，就會將其當作資料服務的輸入使用。 資料服務會根據輸入產生多維度運算式（MDX）查詢，然後針對立方體執行這些 MDX 查詢，以針對每個報告取得資料。 

### <a name="building-customized-reports"></a>建立自訂報表

CQD 在自訂報表中已經有很大的彈性，但在某些情況下，使用者可能會想要在 CQD 中建立的多個報表上匯總資料。 例如，您可能需要建立報告，以顯示表格中所有可能的有線通話組合（例如圖形）的不佳通話百分比：

![CQD 資料表](../../media/ef19d535-5da6-44a9-91f6-1ed3f30b96f1.png)

如果您使用由 CQD 提供的入口網站，使用者就必須流覽多個報告，才能針對每個報告提取並記錄較差的通話% （如果有多個需要收集的資料點，可能會比較繁瑣）。 資料 Api 透過從資料服務（例如透過 AJAX 呼叫）中檢索資料，提供以程式設計方式來完成這項作業的方法。 

 **範例1：簡單的報表範例**

首先讓我們做一個簡單的範例。 如果我們想要在 HTML 頁面上顯示音訊完好資料流程，以及音訊不正確2015的資料流程計數，如圖所示：

![CQD 範例報表](../../media/f0e4e61f-1fa5-4d69-b192-f19e9612bf1c.png)

我們需要的是使用正確的參數傳送對資料服務的通話，並在 HTML 表格中顯示查詢結果。 以下是 JavaScript 程式碼範例：

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

這個範例可以進一步 deconstructed 為三個步驟：

1. 構造查詢（在這個範例中，是在變數 "query" 中定義的）。 查詢已定義為 JSON 物件，其中包含下列資料：

   是. 零個或多個維度。 每個維度都是由 DataModelName 來指示。

   乙. 零個或多個篩選。 每個篩選器都有：

   - DataModelName （將會有篩選集的維度）。

   - Value （將由運算元比較的值）。

   - 運算元（比較類型，0代表「等於」）。

     c-clip. 一或多個度量單位。

2. 透過 AJAX 呼叫將查詢傳送至資料服務。 需要提供下列要求參數：

   是. url （應為 HTTP：//[ServerName]/QoEDataService/RunQuery）。

   乙. 資料（這是 "query" 變數中定義的 JSON 物件的字串表示形式）。 資料服務會傳回查詢結果作為回叫函數的參數，以取得成功。

   c-clip. 類型（適用于 QoEDataService，RunQuery 只接受「帖子」要求）。

   希望. async （指示 AJAX 呼叫是否應為同步或非同步標誌）。

   e. contentType （應該是 "application/json"）。

   °. 成功（在 AJAX 呼叫成功完成後傳回函數）。

   7. 錯誤（AJAX 呼叫失敗時的錯誤處理函數）。

3. 在 HTML 中將資料放入 div 元素（在程式碼的範例中，這是在 AJAX 要求成功完成後透過匿名函數呼叫來完成）。

將 JavaScript 程式碼圍在 HTML 頁面中，頁面就會顯示類似圖所示的報表。 完整的 html 如下所示：

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

到目前為止，報表還是非常簡單。 使用者可以新增更多度量值、維度或篩選，來自訂報表。 例如，如果您想要顯示 AppSharing 的通話百分比不佳，則需要新增有關 AppSharing 的新度量單位。 如果您想要顯示所有 TCP 呼叫 v.s。 UDP 通話，應新增有關運輸類型的新維度。 如果您想要顯示特定建築物內不佳的通話次數，請新增一份新的篩選器，以選取該建築物的通話。

 **範例2：報表定義範例**

在建立查詢時，有人可能難以瞭解如何撰寫測量/維度/篩選及其對應值的完整清單。 在這種情況下，您可以移至入口網站、使用報表編輯器建立報表，以及查看報表定義的 JSON 字串，然後將定義複製到自訂報表中。 

在這個範例中，我們會建立一個網頁，如下圖中所示，使用者可以在其中輸入任何現有報表集（或報表）的識別碼，並在網頁上顯示報表集或報表的定義。 然後，使用者可以將每個報告的 JSON 字串插入與範例1中所示的程式碼，並構造使用者想要的任何自訂報表。 

![CQD 範例](../../media/01c45c23-c4d2-47b8-819f-0888cf71260f.png)

若要建立報表定義檢視器工具，我們需要將呼叫傳送到知識庫服務，以取得所需每個報表集之定義的 JSON 字串標記法。 知識庫 API 將根據指定的報告集識別碼，傳回報告集定義。 

簡單的範例如下所示，程式碼包含一個可將查詢傳送至知識庫服務的簡單範例，以根據其識別碼取得儲存庫專案的內容。 然後，程式碼的下一個部分（processReportSetData 方法）會傳送 AJAX 呼叫，以在該報告集中取得每個報表的定義。 因為 CQD 網頁入口網站中的識別碼是報表集的識別碼，所以 AJAX 呼叫會傳回報表集專案。 您可以在 [[取得專案](get-items.md)] 中找到有關知識庫 API 及特別是 GetItems 的更多詳細資料。 

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

上述會產生類似圖中所示的網頁（在初次造訪時沒有報表定義）。 從 CQD 入口網站取得報表集 ID （在 [/#/"登入 CQD 入口網站 URL 中）（例如， 在第一個圖表中，報告集 ID 是3024），並將此報告集識別碼放在此網頁的輸入區段中。 按 [載入] 按鈕，查看報表集的完整定義（測量、維度、篩選器清單）。

在 [摘要] 中，您可以快速取得報表/報表集的完整定義。 步驟如下：

1. 移至入口網站，並使用 [查詢編輯器] 自訂報表（按一下報表上方的 [編輯] 按鈕，即可編輯、新增、移除度量/維度/篩選，然後儲存報表）。

2. 從 URL 取得報表集 ID （位於 "/#/" 登入 URL 後的整數）。

3. 啟動在範例2中建立的此報告定義網頁，然後輸入報告集識別碼，並檢索報告集的完整定義（以用於資料 API 呼叫）。

   **範例3：計分卡範例**

時間做為更複雜的工作。 如果我們想要建立網頁等圖，該怎麼辦？ 我們必須更新範例1（在範例2中產生的網頁說明），以取得任何報告的完整定義，以便我們能處理大量的資料。

在這種情況下，我們需要更新測量與維度清單。 瞭解如何新增/編輯測量與/或維度的方式，就是遵循範例2中的指示，並檢索完整的報表定義，包括完整的度量和維度清單。 將完整的報表定義插入範例程式碼。 

以下是從範例1中提供的範例移至圖中的計分卡頁面的詳細步驟：

1. 將 "query" 變數中的度量值`[Measures].[Audio Good Streams JPDR Count]`更新`[Measures].[Audio Poor Streams JPDR Count]`為`[Measures].[AudioPoorJPDRPercentage]`[從] 到 [到]。 

2. 更新篩選器。 範例1中的篩選器 JSON 資料有一個在維度`[StartDate].[Month]`上設定的篩選。 因為篩選是一個 JSON 陣列，所以可以在篩選清單中新增其他維度。 例如，若要在「currentMonth」的有線通話中取得伺服器用戶端，我們應該使用下列篩選器：

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

   這裡的維度`[Scenarios].[ScenarioPair]`設定為 [等於`[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`]。 `[Scenario.][ScenarioPair]`是建立以簡化報表建立的特殊維度。 它有六個對應的`[FirstIsServer], [SecondIsServer], [FirstInside], [SecondIsServer], [FirstConnectionType], [SecondConnectionType]`值。 所以，請不要使用6個篩選的組合來定義案例，只需要使用1個篩選。 在我們的範例中， `[1]&amp;[0]&amp;[1]&amp;[1]&amp;[Wired]&amp;[Wired]`此值會轉化為：第一個是伺服器、第二個是伺服器、第二個是伺服器、第二個是內部、第二個連線類型是有線的，而第二個連線類型是「伺服器-用戶端-在有線」的確切定義。

3. 針對每個案例建立一個篩選集合。 這個計分卡中的每個資料列代表不同的案例，而這會是不同的篩選（尺寸與測量保持不變）。 

4. 分析 AJAX 呼叫的結果，並將它們放在表格的正確位置。 由於這大多是 HTML 和 JavaScript 的操作，因此我們不會在這裡找到詳細資料。 相反地，附錄 A 提供了程式碼。

    > [!NOTE]
    >  如果啟用 [跨來源資源分享（CORS）]，使用者可能會遇到錯誤，例如「沒有」要求的資源上出現「不」存取控制-來源」標頭。 因此，"null" 是不允許存取的。 若要解決此問題，請將 HTML 檔案放在已安裝入口網站的資料夾（預設情況下） `%SystemDrive%\Program Files\Skype for Business 2015 CQD\CQD)`。 然後透過任何瀏覽器使用 URL `http://<servername>/cqd/<html_file_name>`來存取 html。 （當地 CQD 儀表板的預設 URL 為`http://<servername>/cqd.`） 

### <a name="appendix-a"></a>附錄 A

範例3的 HTML 程式碼（分計分卡範例）：

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
