---
title: 安裝 Power BI連接器以使用 CQD 查詢範本
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
description: 安裝 Power BI 連接器，以在 CQD (中) 通話品質儀表板
ms.openlocfilehash: 535a1d067dff81c8019a1c08d1a2a617019300989f515f97f89f471e845ca885
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288501"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>安裝 Microsoft 通話品質連接器Power BI使用通話品質儀表板查詢範本

在使用 Power BI 查詢範本 (PBIX 檔案) Microsoft Teams 通話品質儀表板 (CQD) 之前，您必須使用下載中包含的 *MicrosoftCallQuality.pqx* 檔案安裝 Power BI 的 Microsoft 通話品質 [連接器。](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

請參閱使用 Power BI 分析[CQD 資料Teams](CQD-Power-BI-query-templates.md)瞭解這些範本。

請確定您擁有正確的[CQD 存取角色](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd)，以存取Power BI報表。

> [!NOTE]
> Microsoft 通話品質連接器僅支援 DirectQuery Power BI;不支援輸入模式。 

## <a name="installation"></a>安裝

安裝自訂連接器及調整安全性以啟用連接器使用的過程，請參閱本文Power BI[說明](/power-bi/desktop-connector-extensibility)。 為了簡單起見，以下是快速說明：

1. 檢查您的電腦是否已在自訂連接器Power BI Desktop *\[ \] \\ \\ 檔*。 如果沒有，請建立此資料夾。<sup>1</sup>

2. 下載連接器檔案 (*\* .mez* 或 *\* .pqx* 檔案) 並放在 *自訂連接器* 目錄中。

3. **如果連接器檔案是 *\* .mez* 檔案**，您也需要調整安全性設定，如自訂連接器設定檔 [所述](/power-bi/desktop-connector-extensibility#data-extension-security)。

如果已發佈新版本的 Microsoft 通話品質連接器，請將自訂連接器目錄中的舊連接器檔案取代為新檔案。

## <a name="setup"></a>設置

若要建立報表並執行查詢，您首先必須連接到 CQD 資料來源。 請遵循下列步驟進行連結：

1. 在 [首頁Power BI Desktop中，按一下 [*取得資料*> 。

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector1-resize.png)

2. 此時 *應該會出現* 取得資料視窗。 流覽至 *線上服務，* 然後選取 *Microsoft* 通話品質 (Beta) 並按 *連線。*

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector2-resize.png)

3. 下一步將會提示您進行登錄。 使用您用於通話品質儀表板的相同認證。<sup>2</sup>

4. 下一個提示會提供兩種資料連線 *模式之間的選項*。 選取 *DirectQuery，* 然後按 *確定*。

5. 最後，系統最後會提示您顯示通話品質儀表板的整個資料模型。 此時不會顯示任何資料，只會顯示 CQD 的資料模型。 選取 *載入* 以完成設定程式。

6. 此時，Power BI將資料模型載入至視窗右側。 頁面會保留空白，且預設不會載入任何查詢。 繼續進行下方的 **建立** 查詢，以建立查詢並返回資料。

如果此設定程式期間的任何步驟都不清楚，可以在快速入門中找到程式的詳細說明[：連線](/power-bi/desktop-quickstart-connect-to-data)資料Power BI Desktop。

## <a name="building-queries"></a>建立查詢

設定完成後，您應該在欄位窗格中看到數百個維度和量值 *載入* 的名稱。 從這裡建立實際查詢很簡單，只要選取您想要查詢的維度和度量，然後將它們拖放到頁面上。 以下是更詳細的說明，以及一個簡單的範例：

1. 從視覺效果窗格中選取您想要 *使用的視覺效果* 。 該視覺效果的空白版本應該會出現在頁面上。 為了本範例的目的，我們將使用表格 *視覺效果* 。

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector3-resize.png)

2. 決定要用於 (的匯總符號) 以匯總符號表示的維度和度量，然後手動選取這些維度和度量，並將它們拖曳到黑色視覺效果上。 或者，將它們拖曳 *到視覺效果選項* 下方的值欄位。

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > 通話品質儀表板需要執行任何查詢的量值。 若無法新增量值至查詢，則會導致該查詢失敗。

3. 接下來，選取您想要篩選的任何維度，並將這些維度拖曳到篩選窗格此視覺欄位 *上的篩選。* Microsoft 通話品質連接器目前支援基本篩選 (從可能維度值) 、進位篩選 (清單中選取值以手動指定要篩選的值和運算元，類似通話品質儀表板 *) ，* 以及僅適用于結束時間和開始時間維度) 的相對日期篩選 (。    通話品質儀表板不支援根據 *前 N* 個篩選。

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector5-resize.png)

4. 最後，選取視覺效果 *窗格中* 的格式索引鍵，以為查詢設置樣式和格式。

    > [!NOTE]
    > 通話品質儀表板查詢至少需要一個量值才能執行。 如果您的查詢未載入，請仔細檢查您是否在查詢中包含量值。

## <a name="creating-a-drillthrough-report"></a>建立鑽研報表

[在 Power BI](/power-bi/desktop-drillthrough)中鑽取可讓您建立焦點報表，您可以使用其他報表的值做為上下文來快速篩選。 瞭解如何使用 Microsoft 通話品質連接器建立第一個查詢之後，建立鑽取甚至會更加簡單。

1. 為焦點報表建立另一個頁面，然後將查詢新增到該頁面。

2. Select the dimension you want to use as a drillthrough filter and drag them onto the *Drillthrough* field under on the *Visualizations* pane.

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector6-resize.png)

3. **就是這樣\!** 使用該維度的另一個頁面上任何其他查詢現在都可以深入到該頁面，並自動將鑽取維度的值當做篩選。

    ![螢幕擷取畫面：Power BI連接器](media/CQD-power-bi-connector7-resize.png)

與通話品質儀表板不同，Power BI支援非連續的鑽取。 如果查詢包含必要的維度，它可以切至任何其他頁面。

### <a name="best-practice"></a>最佳做法

Microsoft 通話品質連接器查詢在設計時，應牢記鑽取功能。 與其嘗試一次載入所有資料，然後以篩選向下切開，請從更廣泛的低基數查詢開始，然後向下切至高基數查詢。 例如，當您嘗試診斷哪些子網對品質問題影響最大時，先找出造成問題的區域及國家/地區，然後向下向下切入到該區域或國家/地區的子網會很有説明。 通話品質連接器範本是採用這種方式設計，以做為範例。

## <a name="limitations"></a>限制

雖然使用 Power BI，但 Microsoft 通話品質連接器Power BI並非所有的 Power BI 功能都受到支援，無論是因為通話品質儀表板資料模型的限制，還是 DirectQuery 連接器的一般限制。 下列清單會說明連接器的一些較值得注意的限制，但這份清單不應視為詳盡無遺：

1. **計算欄 –** DirectQuery 連接器一般對計算結果欄的支援有限，Power BI。 某些計算結果欄可能會與連接器一起使用，因為這些資料行是例外。 一般而言，計算結果欄無法運作。

2. **匯總 –** 通話品質儀表板資料模型是建在 Cube 模型上，這表示匯總已經以量值的形式支援。 嘗試手動將匯總新增到不同的維度或變更度量的匯總類型，無法與連接器一起使用，而且通常會導致錯誤。

3. **自訂視覺效果 –** 雖然 Microsoft 通話品質連接器可處理一系列自訂視覺效果，但我們無法保證所有自訂視覺效果的相容性。 許多自訂視覺效果仰賴計算欄或輸入資料的使用，這兩者均不受 DirectQuery 連接器支援。

4. **參照緩存** 資料 – Power BI目前不支援以任何方式參照 DirectQuery 連接器的緩存資料。 任何參照查詢結果的嘗試都會產生新的查詢。

5. **相對資料篩選 –** Microsoft 通話品質連接器支援，但僅支援 *開始時間和**結束時間* 維度。 雖然 *日期* 維度可能是相對日期篩選的明顯選擇，但 *日期* 不會儲存為日期時間物件，因此不支援 Power BI。

6. **僅度量查詢 -** Microsoft 通話品質連接器目前不支援。 建立具有三個或多個度量且沒有維度的視覺效果時，欄資料會轉置。 若要避免這種情況，在視覺效果中 (至少一個維度，例如：) 年資料。 這是預定在即將推出的 Microsoft 通話品質連接器中解決Power BI。

7. **政府社群雲端 (GCC) 支援 –** 對於在 GCC 環境中的客戶，Microsoft 通話品質連接器只有在使用Power BI Desktop才能使用。 Microsoft 通話品質連接器目前與Power BI服務GCC相容。

這些問題大部分是直接查詢連接器設計的限制Power BI或 CQD 資料模型設計的基本限制。

## <a name="troubleshooting"></a>疑難排解

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>我嘗試使用日期欄做為日期分割器。 一旦將此欄的資料類型轉換為日期，就會收到此錯誤

> **無法載入此** 視覺效果的資料：OLE DB 或 ODBC 錯誤：[Expression.Error] 無法將運算式折至資料來源。 請嘗試更簡單的運算式。

Microsoft 通話品質連接器不支援日期分割器。 若要指定日期範圍，請對報表使用兩種篩選，指定小於及大於日期。

或者，如果您想要查看的日期是最近的日期，請申請相對日期篩選，只顯示過去 N 天/周/月的資料。

## <a name="error-codes"></a>錯誤碼

由於 Microsoft 通話品質連接器的 Power BI 在可建構的查詢類型方面，比瀏覽器應用程式限制較少，因此在建立查詢時，您偶爾可能會遇到一些錯誤。 萬一您收到「CQDError」類型的錯誤訊息。 RunQuery – 查詢執行錯誤」，請參照下列清單，提供 ErrorType 號碼，以疑難排解查詢可能的問題。 以下是您可能會遇到的 CQD 連接器中最常見的錯誤類型Power BI代碼：

- **ErrorType 1 - 查詢結構錯誤：** 查詢結構錯誤通常是由連接器無法建立正確格式的查詢所導致。 使用不支援的功能時，通常會發生此情況，如上述限制所指定。 請仔細檢查您並未針對該查詢使用任何計算結果欄或自訂視覺效果。

  - **ErrorType 2 - 查詢建立錯誤：** 查詢建立錯誤是由 Microsoft 通話品質連接器無法正確剖析您嘗試建立之查詢所導致。 使用不支援的功能時，通常會發生此情況，如上述限制所指定。 請仔細檢查您並未針對該查詢使用任何計算結果欄或自訂視覺效果。

  - **ErrorType 5 - 執行超時：** 查詢在超時前已達到可能的最大執行時間。請嘗試在查詢中新增更多篩選，以限制其範圍。 縮小資料範圍通常是達成此目標最有效的方法。

  - **ErrorType 7 - 無度量錯誤：** 通話品質儀表板查詢需要量值才能運作。 請仔細檢查您的查詢是否包含量值。 Microsoft 通話品質連接器中的量值會以匯總表示， (名稱) 符號。

如果您遇到此範圍以外的任何其他錯誤，請通知通話品質儀表板小組，以便我們協助疑難排解問題並在適當時更新檔。

## <a name="footnotes"></a>註腳

**<sup>1</sup>** 特定程式 (應用程式，例如，OneDrive) 可能會導致您的檔根資料夾變更;請確定自訂 *連接器Power BI Desktop \\* 目錄放在目前的根資料夾檔資料夾內。

**<sup>2</sup>** 您用於通話品質儀表板的登入認證不需要與登入應用程式本身時Power BI Desktop認證。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>何時會從Power BI Beta 狀態更新連接器？

雖然有 Beta 標記，Power BI 版 Microsoft 通話品質 (Beta) 連接器是連接器的第一個發行版本本，並經過 Power BI 小組正式簽署安全性，以反映這一點。 在連接器初次發行時，Power BI 小組無法提供支援和更廣泛的認證，但仍準備證明 Microsoft 通話品質連接器的安全性、真實性和一般功能。 展望未來，我們計畫在近期內投資 microsoft 通話品質連接器Power BI電話品質連接器。

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>為什麼連接器看起來比瀏覽器中的通話品質儀表板慢？ 我可以做些什麼來改善績效？

在瀏覽器和連接器中，各種範本的查詢績效實際上是相同的。  就像任何其他獨立應用程式一樣，Power BI將驗證和呈現時間加到我們的績效中。 此外，差異在於同時執行查詢的數量。 由於瀏覽器內版本的通話品質儀表板具有較不良好開發且資訊濃密的視覺效果選項，因此大部分的報告一次只能載入 2-3 個查詢。 另一方面，連接器範本通常會顯示 20 多個並行查詢。 如果您想要建立與舊版報表一樣回應的報表，請嘗試建立每個索引點不超過 2-3 個查詢的報表。

詳細資訊，請參閱下列文章：

- [優化指南Power BI](/power-bi/guidance/power-bi-optimization)
- [DirectQuery 模型指南](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>我發現執行查詢時，會經常遇到 10，000 列的限制。 如何讓連接器返回超過 10，000 列？

10，000 列的限制實際上是在 API 端指定，其設計可協助大幅提升績效，並降低因記憶體不足而造成查詢執行錯誤的風險。

與其嘗試增加結果列數，最好根據連接器最佳做法來重新組織報表。 我們包含的範本是專為示範這些最佳做法所設計。 如果可能的話，首先使用較寬、基數較低的維度來查看 KPI，例如月、年、日期、地區、國家/地區等。您可以在那裡向下向下切入到愈高基數維度。 說明台和Location-Enhanced報表都提供此向下切入工作流程的範例。



## <a name="related-topics"></a>相關主題

[使用 Power BI 來分析 CQD 資料Teams](CQD-Power-BI-query-templates.md)
