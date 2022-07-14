---
title: 安裝 Power BI 連接器以使用 CQD 查詢範本
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: 安裝 Power BI 連接器以使用通話品質儀表板 (CQD) 查詢範本
ms.openlocfilehash: 80d1b39c6fbe26f04998b06b22fb527b60bbb6a0
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789868"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>安裝 Power BI 的 Microsoft 通話品質連接器以使用通話品質儀表板查詢範本

在您可以使用 Power BI 查詢範本 (Microsoft Teams 通話品質儀表板 (CQD) 的 PBIX 檔案) 之前，您必須使用 [下載](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)中包含的 *MicrosoftCallQuality.pqx* 檔案來安裝 Power BI 的 Microsoft 通話品質連接器。

請閱讀 [使用 Power BI 來分析 Teams 的 CQD 資料](CQD-Power-BI-query-templates.md) 以瞭解這些範本。

請確定您擁有正確的 [CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) 來存取 Power BI 報表。

> [!NOTE]
> Microsoft 通話品質連接器只支援 Power BI 中的 DirectQuery;不支援匯入模式。 

## <a name="installation"></a>安裝

[Power BI 檔](/power-bi/desktop-connector-extensibility)詳細說明安裝自訂連接器及調整安全性以啟用連接器的程式。 為了簡潔起見，以下是一些快速的說明：

1. 檢查您的電腦是否已經有 *\[ [檔 \] \\ Power BI Desktop \\ 自訂連接器* 資料夾。 如果沒有，請建立此資料夾。<sup>1</sup>

2. 下載連接器檔案 (*\* .mez* 或 *\* .pqx* 檔案) ，並將它放在 *[自訂連接器*] 目錄中。

3. **如果連接器檔案是 *\* .mez* 檔案，** 您也需要調整安全性設定，如 [自訂連接器設定檔](/power-bi/desktop-connector-extensibility#data-extension-security)中所述。

如果發行新版 Microsoft 通話品質連接器，請以新檔案取代 *自訂連接器* 目錄中的舊連接器檔案。

## <a name="setup"></a>設置

若要建立報表並執行查詢，您必須先連線至 CQD 資料來源。 請依照下列步驟進行以連線：

1. 在 Power BI Desktop 的 [常用] 索引標籤中，按一下 [*取得資料]*。

    ![在 Power BI Connector 中取得資料。](media/CQD-power-bi-connector1-resize.png)

2. 此時應該會出現 [ *取得資料* ] 視窗。 流覽至 *[線上服務*]，然後選 *取 [Microsoft 通話品質] (Beta)* 並按 [ *連線]*。

    ![Power BI Connector 中的 Microsoft 通話品質。](media/CQD-power-bi-connector2-resize.png)

3. 系統會提示您下次登入。 使用與通話品質儀表板相同的認證。<sup>2</sup>

4. 下一個提示會在兩種 *資料連線模式* 之間提供選項。 選取 *[DirectQuery]* ，然後按 [ *確定]*。

5. 最後，系統會提供最終提示，顯示通話品質儀表板的整個資料模型。 此時不會顯示任何資料，只有 CQD 的資料模型。 選 *取 [載入* ] 以完成設定程式。

6. 此時，Power BI 會將資料模型載入視窗右側。 否則頁面會保持空白，預設不會載入任何查詢。 請繼續進行下方 **的建置查詢** ，以建立查詢並傳回資料。

如果在此設定程式期間有任何步驟都不清楚，請參閱[快速入門：連線至Power BI Desktop中的資料](/power-bi/desktop-quickstart-connect-to-data)，以取得程式的更詳細說明。

## <a name="building-queries"></a>建置查詢

設定完成後，您應該會在 [欄位 *] 窗格* 中看到數百個維度和量值載入的名稱。 從這裡建構實際查詢很簡單，只要選取查詢所需的維度和量值，然後將它們拖放到頁面上即可。 以下是更詳細的說明，其中包含一個簡單的範例：

1. 從 [視覺效果] 窗格選取您要使用的 *視覺* 效果。 該視覺效果的空白版本應該會顯示在頁面上。 在此範例中，我們將使用 [ *表格* ] 視覺效果。

    ![Power BI Connector 中的 [視覺效果] 窗格。](media/CQD-power-bi-connector3-resize.png)

2. 決定哪些維度和量值 (由匯總符號的名稱表示，) 您想要用於查詢，然後手動選取它們，然後將它們拖曳到黑色視覺效果上。 或者，將它們拖曳到視覺效果選項下方的 [ *值* ] 欄位。

    !Power BI Connector 中的視覺效果查詢。] (媒體/CQD-power-bi-connector4-resize2.png) 

    > [!IMPORTANT]
    > 通話品質儀表板需要執行任何查詢的量值。 若無法在查詢中新增量值，會導致查詢失敗。

3. 接下來，選取您要篩選的任何維度，然後將它們拖曳到 [篩選] 窗格中 *此視覺* 欄位上的 [ *篩選]* 。 Microsoft 通話品質連接器目前支援 *基本篩選* (從可能維度值清單中選取值) 、 *進階篩選* (手動指定要篩選的值和運算元，類似通話品質儀表板) ， *以及相對日期篩選* (僅適用于結束 *時間* 和 *開始時間* 維度) 。 通話品質儀表板不支援根據 *前 N* 進行篩選。

    ![視覺效果會篩選 Power BI Connector 中的視覺效果。](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > 只有在套用至維度時才支援篩選。 通話品質儀表板不支援篩選度量值。

4. 最後，在 [*視覺效果*] 窗格中選取 [*格式*] 索引標籤，以樣式化查詢並設定查詢格式。

    > [!NOTE]
    > 通話品質儀表板查詢需要至少一個量值才能執行。 如果您的查詢未載入，請再次檢查您是否已在查詢中包含量值。

## <a name="creating-a-drillthrough-report"></a>建立切入報表

[在 Power BI 中切入](/power-bi/desktop-drillthrough) 可讓您建立焦點報表，讓您可以使用其他報表的值做為上下文快速篩選。 一旦您知道如何使用 Microsoft 通話品質連接器建立您的第一個查詢，建立切入更簡單。

1. 為焦點報表建立另一個頁面，然後將查詢新增至該頁面。

2. 選取您要做為切入篩選的維度，然後將它們拖曳到 *[視覺效果*] 窗格下方的 [*切入]* 欄位。

    ![在 Power BI 連接器中切入。](media/CQD-power-bi-connector6-resize.png)

3. **就是這樣\!** 使用該維度的其他任何查詢現在可以切入該頁面，自動套用切入維度的值做為篩選。

    ![在 Power BI 連接器中切入篩選器。](media/CQD-power-bi-connector7-resize.png)

不同于通話品質儀表板，Power BI 支援非循序的切入。 如果查詢包含必要的維度，則可切入到任何其他頁面。

### <a name="best-practice"></a>最佳做法

Microsoft 通話品質連接器查詢的設計應考慮到切入功能。 與其嘗試一次載入所有資料，然後使用篩選向下切入，而是從更廣泛的低基數查詢開始，然後向下切入至高基數查詢。 例如，嘗試診斷哪些子網最能造成品質問題，建議您先找出參與問題的區域與國家，然後向下切入到該區域或國家/地區的子網。 「通話品質」連接器範本是以這種方式設計，以做為範例。

## <a name="limitations"></a>限制

儘管使用了 Power BI，並非所有 Power BI 功能都受到 Microsoft 通話品質連接器的支援，可能是因為通話品質儀表板資料模型的限制，或一般在 DirectQuery 連接器上所提供的支援。 下列清單會記下一些連接器的一些值得注意的限制，但此清單不應視為詳盡的：

1. **計算結果欄 –** DirectQuery 連接器在 Power BI 中對計算結果欄的支援一般有限。 有些計算結果欄可能與連接器搭配使用，這些欄是例外。 一般規則是，計算結果欄無法運作。

2. **匯總 –** 通話品質儀表板資料模型建置在 Cube 模型上，這表示已經以量值形式支援匯總。 嘗試手動將匯總新增至不同的維度，或變更量值的匯總類型將無法與連接器搭配使用，且通常會導致錯誤。

3. **自訂視覺效果 –** 雖然 Microsoft 通話品質連接器可搭配各種自訂視覺效果使用，但我們無法保證與所有自訂視覺效果的相容性。 許多自訂視覺效果都仰賴計算結果欄或匯入資料的使用，DirectQuery 連接器不支援這些專案。

4. **參照快取資料 –** Power BI 目前不支援以任何方式參照 DirectQuery 連接器中的快取資料。 任何嘗試參照查詢的結果都會產生新的查詢。

5. **相對資料篩選 –** Microsoft 通話品質連接器支援，但僅支援 *[開始時間* ] 和 [ *結束時間]* 維度。 雖然 *[日期]* 維度可能是相對日期篩選的明顯選擇，但 *[日期* ] 並未儲存為日期時間物件，因此不支援 Power BI 中的相對日期篩選。

6. **僅限度量查詢 -** Microsoft 通話品質連接器目前不支援。 使用三個以上的度量單位建立視覺效果且沒有維度時，欄資料會轉置。 若要避免這種情況，視覺效果中一律至少包含一個維 (例如：月份年) 。 我們預計在即將發行的 Power BI 的 Microsoft 通話品質連接器中解決此問題。

7. **政府社群雲端 (GCC) 支援 –** 對於 GCC 環境中的客戶，Microsoft 通話品質連接器只能在使用Power BI Desktop時運作。 Microsoft 通話品質連接器目前與 GCC 客戶的Power BI 服務不相容。

這些問題大多是 Power BI 中對 DirectQuery 連接器設計的限制，或是 CQD 資料模型設計的基本限制。

## <a name="troubleshooting"></a>疑難排解

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>我嘗試使用 [日期] 欄做為 [日期] 交叉分析篩選器。 一旦我將此欄的資料類型轉換為 [日期]，就會收到這個錯誤

> **無法載入此視覺效果的資料**：OLE DB 或 ODBC 錯誤：[Expression.Error] 我們無法將運算式折迭至資料來源。 請嘗試更簡單的運算式。

Microsoft 通話品質連接器不支援日期交叉分析篩選器。 若要指定日期範圍，請將兩個篩選套用至報表，指定小於及大於日期。

或者，如果您想要檢視的日期是最近日期，請套用相對日期篩選，只顯示過去 N 天/周/月的資料。


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>當我新增特定維度至報表時，視覺效果會立即傳回 **「無法載入此視覺效果的資料」**。 移除維度可以修正視覺效果 ， 發生什麼事？

這是 Microsoft 通話品質連接器中的已知問題;任何公開為整數的維度都會以「匯總」欄的形式顯示在 Power BI 中，其中 Power BI 會嘗試預設的摘要動作， (通常是「加總」) 。 在某些情況下，即使結果不實用，此行為仍會成功加總值，因為像第二個 WiFi 通道這樣的維度「加總」是無意義的。 在其他情況下，此摘要動作會失敗，並在視覺效果中造成錯誤。

若要解決此問題，請先從視覺效果中移除維度。 從 [欄位] 清單中選取維度，流覽至功能區中的 [欄工具] 索引標籤，按一下 [摘要] 下拉式功能表，然後選取 [ **不要摘要]**。 維度現在可以再次新增至視覺效果。


## <a name="error-codes"></a>錯誤碼

就您可以建構的查詢類型而言，Power BI 的 Microsoft 通話品質連接器比瀏覽器應用程式受到的限制較少，因此您偶爾可能會在建立查詢時遇到許多錯誤。 如果您收到 「CQDError」 類型的錯誤訊息。 RunQuery – 查詢執行錯誤」，請參閱下列清單並提供 ErrorType 編號，以針對查詢的可能問題進行疑難排解。 以下是您可能會遇到的 CQD Power BI Connector 最常見的錯誤類型代碼：

- **ErrorType 1 - 查詢結構錯誤：** 查詢結構錯誤通常是因為連接器無法建立正確格式化的查詢所導致。 此情況最常在使用不受支援的功能時發生，如上述限制中所述。 再次確認您並未針對該查詢使用任何計算結果欄或自訂視覺效果。

  - **ErrorType 2 - 查詢建置錯誤：** 查詢建置錯誤的原因是 Microsoft 通話品質連接器無法正確剖析您嘗試建立的查詢。 此情況最常在使用不受支援的功能時發生，如上述限制中所述。 再次確認您並未針對該查詢使用任何計算結果欄或自訂視覺效果。

  - **ErrorType 5 - 執行逾時：** 查詢已到達計時前的最大可能執行時間。請嘗試新增更多篩選至查詢，以限制其範圍。 縮小資料範圍通常是達成此目標最有效的方法。

  - **ErrorType 7 - 沒有測量錯誤：** 通話品質儀表板查詢需要量值才能正常運作。 再次檢查您的查詢是否包含量值。 Microsoft 通話品質連接器中的量值會以名稱前面的匯總 (加總) 符號表示。

如果您遇到超出此範圍的任何其他錯誤，請通知通話品質儀表板小組，讓我們可以協助疑難排解問題，並視需要更新檔。

## <a name="footnotes"></a>註腳

**<sup>1</sup>** 某些程式和應用程式 (例如，OneDrive) 可能會導致您的 [檔] 根資料夾變更;確認 *Power BI Desktop \\ Custom Connectors* 目錄已置於目前 [檔] 資料夾的根資料夾內。

**<sup>2</sup>** 您用於通話品質儀表板的登入認證 *，不需要* 與您用來登入Power BI Desktop應用程式本身的認證相同。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Power BI 連接器何時會從「Beta」狀態更新？

儘管有 Beta 標籤，Power BI 的 Microsoft 通話品質 (Beta) 連接器是第一個「發行」版本的連接器，而且已經正式由 Power BI 小組簽署以反映這一點。 在首次發行連接器時，Power BI 小組無法提供支援和更廣泛的認證，但仍準備證明 Microsoft 通話品質連接器的安全性、真實性和一般功能。 我們計畫近期內投資 Power BI 的 Microsoft 通話品質連接器。

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>與瀏覽器中的通話品質儀表板相比，為什麼連接器看起來比較慢？ 我該怎麼做來改善效能？

各種範本的查詢效能實際上在瀏覽器和連接器中都是相同的。  就像任何其他獨立應用程式一樣，Power BI 會為我們的效能新增其驗證和轉譯時間。 此外，兩者的差異出在執行的並行查詢數目上。 由於瀏覽器版本的通話品質儀表板較不完善且資訊密集的視覺效果選項，因此大部分的報告一次只能載入 2-3 個查詢。 另一方面，連接器範本通常會顯示 20 個以上的並行查詢。 如果您想要建立回應與舊版報表一樣回應的報表，請嘗試建立每個索引標籤不超過 2-3 個查詢的報告。

如需詳細資訊，請參閱下列文章：

- [Power BI 優化指南](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 模型指引](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>我發現在執行查詢時，我會經常遇到 10，000 列的限制。 如何讓連接器傳回超過 10，000 列？

10，000 列的限制實際上是在 API 端指定，其設計可協助大幅改善效能，並降低記憶體不足所導致的查詢執行錯誤風險。

與其嘗試增加結果列計數，建議您根據連接器最佳做法來重建報表。 我們包含的範本旨在示範這些最佳做法。 請盡可能先使用更廣泛的基數維度來查看您的 KPI，例如月份、年份、日期、地區、國家/地區等。您可以從該處向下切入越來越高基數維度。 技術服務人員和Location-Enhanced報告都提供此向下切入工作流程的良好範例。



## <a name="related-topics"></a>相關主題

[使用 Power BI 來分析 Teams 的 CQD 資料](CQD-Power-BI-query-templates.md)
