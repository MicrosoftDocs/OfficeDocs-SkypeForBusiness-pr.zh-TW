---
title: 開啟並使用通話品質儀表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.cqd
- ms.lync.lac.ToolsCallQualityDashboard
ms.custom:
- Reporting
description: '瞭解如何開啟和使用通話品質儀表板，並取得通話品質的摘要報告。 '
ms.openlocfilehash: 4aea268e2c25e655b7f2dee914497ae3154f0008
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/29/2020
ms.locfileid: "41620020"
---
# <a name="turn-on-and-use-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>開啟並使用 Microsoft 團隊和商務用 Skype Online 的通話品質儀表板

瞭解如何設定您的 Office 365 組織，以使用通話品質儀表板來監控通話品質。
  
通話品質儀表板（CQD）可讓您深入瞭解使用 Microsoft 團隊和商務用 Skype Online 服務所進行的通話品質。 本主題描述開始收集資料的步驟，您可以用來疑難排解通話品質問題。

目前，您可以使用 [高級 CQD] 和 [CQD]。 您可以在<span>https://cqd.teams.microsoft.com</span>使用 [高級 CQD]。 使用您的系統管理員認證的新 URL，但相同的記錄。

## <a name="latest-changes-and-updates"></a>最新變更與更新


更新後的 CQD （在2019年11月之前）會提供近即時 CQD 儀表板。 CQD 資料現已于30分鐘內提供（與前一個 CQD，平均為24小時）。  更新的 CQD 會使用使用者可辨識的使用者可識別資訊（EUII），讓系統管理員能夠向下切入並放大使用者層級。 此外，您還可以報告互動支援新的案例，例如：


- 依地區通話品質：
  - 依區域日期
  - 依區域匯總
  - 特定位置
  - 特定子網上
  - 受影響的使用者或使用者

- 依地區撥打可靠性/失敗：
  - 依區域日期
  - 依區域匯總
  - 特定位置
  - 特定子網上
  - 受影響的使用者或使用者

- 依地區評定我的通話（RMC）：從 month 到特定位置，到提供低 RMC 等級的使用者。 CQD v3 也包含原義的意見反應。
- 支援人員：針對 P2P 通話或會議的特定使用者提供，或針對所有參與者和通話詳細資料。 根據網路位置、裝置或固件，協助找出可能的系統問題。  
- 用戶端版本：針對每個用戶端版本，查看會話與使用者計數，或向下切入至每個用戶端版本的使用者名稱。 針對產品和用戶端類型預先建立的篩選，可協助將版本集中到特定的用戶端。
- 端點：顯示對應至電腦/Mac 的品牌/型號的電腦端點。 依 [品牌]/[模型] 顯示匯總品質。 對應資料的上傳與建立資料類似。

如果無法使用 EUII 存取，則高級 CQD （V3）也會提供 RBAC 支援。  

系統管理員可以透過 CQD 版本3管理商務用 Skype Server 2019 （不只是商務用 Skype Online 和 Microsoft 團隊）。 這需要混合式實現，以及使用通話資料連線器。 如需詳細資訊，請參閱[規劃通話資料連線器](/SkypeForBusiness/hybrid/plan-call-data-connector)。

已新增 CQD 版本2：

- Microsoft 團隊及商務用 Skype Online 的資料
- 摘要報告包含產品篩選來選取 [所有資料]、[Microsoft 團隊資料] 或 [商務用 Skype Online] 資料
- 已更新的影片與 VBSS 資料流程品質分類邏輯。 請參閱[通話品質儀表板中](stream-classification-in-call-quality-dashboard.md)針對分類器定義的資料流程分類。

請參閱這篇文章，以取得[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)的清單。
  
> [!NOTE]
> 若要查看儀表板更新及變更的相關資訊，請按一下 [**好消息**] 中的連結！ [橫幅] 會顯示在儀表板上。

CQD 版本1已供應商務用 Skype Server 2015 管理員下列功能：

- 存取可快速存取的快取報表資料
- 報告頁面的深層連結，以共用和發佈資訊
- 簡化報表的編輯與建立，以及報表描述的可編輯中繼資料
- 提供對多維資料集資料進行程式設計存取的 Web Api，以便在自訂儀表板中使用

## <a name="cqd-near-real-time-nrt-data"></a>CQD 近乎即時（NRT）資料

先進 CQD （V3 2019 年11月）使用近乎即時的資料摘要。 通話記錄可在通話結束後的30分鐘內，于 CQD 入口網站中取得。 從資料集移除 NRT 管線中的記錄前，只能有幾個月提供給它。 CQD v3 會從來自 v3 管線的 NRT 資料合併目前 v2 管線的資料。 在 v2 和 v3 入口網站上，來自存檔週期之資料的查詢會產生相同的結果。 NRT 資料的 V2 和 v3 資料查詢與 NRT Data + PII 期間會不同。

### <a name="piieuii-data"></a>PII/EUII 資料

PII 或 EUII 資料只來自 v3 管線。 出於合規性原因，PII/EUII 資料只會保留30天。 當 NRT 資料超過30日標記時，會清除 PII/EUII 欄位，從而產生 PII 免費 NRT 資料。 PII/EUII 欄位包括：

- 完整 IP 位址
- 媒體存取控制（MAC）位址
- 基本服務組識別元（BSSID）
- 會話初始通訊協定（SIP） URI （僅適用于商務用 Skype）
- 使用者主體名稱（UPN）
- 電腦端點名稱
- 使用者逐字的意見反應
- 物件識別碼（端點使用者的 Active Directory 物件識別碼）

### <a name="date-controls"></a>日期控制項

CQD v3 會新增下列新的滾動趨勢類型：

- 5天
- 7天
- 30天
- 60-日
- 90-日

URL 日期參數現在可以接受 Day 欄位。 [日常報告] 使用 YYYY MM 格式中指定的日期做為趨勢的最後一天。  URL 日期參數 "00" 代表 "today"。

|網址| 滾動日趨勢的結束日期|
|:---|:---|
|<span>HTTPs://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02/</span>   |2019年2月的目前日期|
|<span>HTTPs://<cqdv3>/Spd/#/Dashboard/<reportid>/2019-02-15/</span>|2019年2月15日|
|<span>HTTPs://<cqdv3>/Spd/#/Dashboard/<reportid>/00/</span>        |當天|
|||

根據預設，每個月的當天是用來做為滾動日趨勢的最後一天。

### <a name="drill-thru-functionality"></a>鑽取功能

CQD v3 支援在 SPD 報告中使用 [鑽取] 或 [向下切入] 欄位。 如果選取這些維度欄位，報告會自動開啟不同的 [報表] 索引標籤，並篩選選取的值。 具有指定 [鑽取] 篩選的欄位會在您將游標移到它們上方時，以不同的游標圖示（指標）區分。

選取 [鑽取] 欄位時，儀表板會自動流覽至新的指定索引標籤，並套用含所選值的篩選。 如果該索引標籤有自己的 [鑽取] 欄位，而其中一個已選取，則前一個 [鑽取] 篩選與新的篩選。 這可讓您建立報告，以逐漸縮小產生的資料集。

例如，在通話品質的 [鑽取] 報表中，使用者可以按一下其想要「鑽取」的日期，這會產生 [位置] 索引標籤。

![螢幕擷取畫面：顯示 [鑽取] 報表](media/CQD-drill-thru-report.png)

您可以從 [位置] 索引標籤新增多個日期，例如將2019-09-22 新增至日期：2019-09-24： 

![螢幕擷取畫面：在 [鑽研報表] 中新增日期](media/CQD-add-date.png)

> [!NOTE]
> 不要直接跳到最後一個索引標籤。從先前的搜尋結果中選取的篩選不會太大，無法顯示在表格上。

## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>啟動 Microsoft 通話品質儀表板（CQD）摘要報告

在您開始使用 CQD 之前，請先為您的 Office 365 組織啟動它，如下所示：

![](media/teams-logo-30x30.png) **使用 microsoft 團隊系統管理中心**顯示 microsoft 小組標誌的圖示

1. 使用 Microsoft 團隊服務系統管理員帳戶登入您的 Office 365 組織，然後選取 [系統**管理**] 磚以開啟系統管理中心。
2. 在左窗格中的 [系統**管理中心**] 底下，選取 [ **microsoft 團隊**] 以開啟 microsoft 團隊系統管理中心。
3. 在 Microsoft [團隊管理中心] 中，選取左窗格中的 [**通話品質儀表板**]。
4. \(在開啟 HTTPs://<span>cqd.teams.microsoft.com<span/>\)的頁面上，按一下 [登**入**]，然後輸入您的全域系統管理員帳戶或 microsoft 團隊服務系統管理員帳戶資訊。

    ![螢幕擷取畫面：顯示 [認證] 提示](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登入後，CQD 就會開始收集及處理資料。  
> [!NOTE]
> 在報告中，可能需要一或幾個小時的時間來處理足夠的資料，以顯示有意義的結果。

![](media/sfb-logo-30x30.png) **使用商務用 skype 傳統版入口網站**的商務用 skype 標誌圖示

1. 使用系統管理員帳戶登入您的 Office 365 組織，然後選取 [系統**管理**] 磚以開啟系統管理中心。
2. 在左窗格中的 [系統**管理中心**] 底下，選取 [ **microsoft 團隊**] 以開啟 microsoft 團隊系統管理中心。
3. 在 Microsoft [團隊管理中心] 中，選取左窗格中的 [**舊版入口網站**]，選取 [**工具**]，然後選取 [**商務用 Skype Online 通話品質儀表板**]。

     ![螢幕擷取畫面：選取 [通話品質] 儀表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)

4. 在開啟的頁面上，使用您的全域系統管理員帳戶登入，然後在出現提示時提供該帳戶的認證。

登入後，通話品質儀表板就會開始收集及處理資料。

## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Microsoft 團隊和商務用 Skype Online 的通話品質儀表板功能

<a name="BKMKFeaturesOfTheCQD"> </a>


CQD 摘要報告提供規劃詳細報告之功能的子集。 版本間的差異摘要如下：
  
|功能|摘要報告|詳細報告|
|:--- |:--- |:--- |
|應用程式共用躍點數 | 否 | 是 |
|客戶建立資訊支援 | 是 | 是 |
|用戶端點資訊支援 | 僅限<span>cqd.teams.microsoft.com<span/> | 僅限<span>cqd.teams.microsoft.com<span/> |
|深化分析支援   | 否   | 是   |
|媒體可靠性度量單位   | 否   | 是   |
|外框報告   | 是   | 是   |
|[總覽] 報表   | 是   | 是   |
|每個使用者的報表集   | 否   | 是   |
|報表集自訂（新增、刪除、修改報告）   | 否   | 是   |
|以影片為基礎的畫面共用規格   | 否   | 是   |
|影片度量單位   | 否   | 是   |
|可用的資料量   | 過去12個月   | 過去12個月   |
|Microsoft 團隊資料   | 是   | 是   |
| | | |

### <a name="out-of-the-box-reports"></a>外框報告

所有版本的 CQD 都提供一種體驗，讓您能提供通話品質指標，而不需要建立新的報告。 在後端處理完資料之後，您會在報表中看到 [通話品質資料]。

2020年1月[的新功能：下載 POWER BI 查詢範本以進行 CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD Power BI query templates.zip?raw=true)。 可自訂的 Power BI 範本，您可以用來分析及報告您的 CQD 資料。
  
### <a name="overview-reports"></a>[總覽] 報表

CQD 的所有版本都提供了整體通話品質資訊的高層進入點，但資訊在摘要報告中呈現的方式與詳細報表不同。  
  
[摘要報告] 提供簡化的索引標籤式頁面報表檢視，您可以快速流覽並瞭解整體通話品質狀態與趨勢。

四個索引標籤包括：
  
- **整體通話品質**-提供所有資料流程的相關資訊，這是一種匯總，顯示每月和每日趨勢：
  - 伺服器-用戶端資料流程
  - 用戶端-用戶端資料流程
  - 個別的伺服器-用戶端和用戶端資料流程
- **伺服器-用戶端**-提供伺服器與用戶端端點之間資料流程的詳細資料。
- **用戶端-用戶端**-提供兩個用戶端端點之間資料流程的詳細資料。
- **語音品質 SLA** -提供包含在商務用 Skype Online 語音品質 SLA 中之通話的相關資訊。

> [!NOTE]
> CQD 版本3可與 Microsoft 團隊、商務用 Skype Online 和商務用 Skype 伺服器搭配使用。 若要在商務用 Skype Server 2019 中使用 CQD，您必須[設定 [呼叫資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-call-data-connector)]。 請參閱[規劃通話資料連線器](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-call-data-connector)，然後再開始進行。

- 依地區通話品質：

  - 依區域日期
  - 依區域匯總
  - 特定位置
  - 特定子網上
  - 受影響的使用者或使用者

- 依地區撥打可靠性/失敗：
  - 依區域日期
  - 依區域匯總
  - 特定位置
  - 特定子網上
  - 受影響的使用者或使用者

- 依地區評定我的通話（RMC）：從 month 到特定位置，到提供低 RMC 等級的使用者。 CQD v3 也包含原義的意見反應。
- 支援人員：針對 P2P 通話或會議的特定使用者提供，或針對所有參與者和通話詳細資料。 根據網路位置、裝置或固件，協助找出可能的系統問題。  
- 用戶端版本：針對每個用戶端版本，查看會話與使用者計數，或向下切入至每個用戶端版本的使用者名稱。 針對產品和用戶端類型預先建立的篩選，可協助將版本集中到特定的用戶端。
- 端點：顯示對應至電腦/Mac 的品牌/型號的電腦端點。 依 [品牌]/[模型] 顯示匯總品質。 對應資料的上傳與建立資料類似。

### <a name="overall-call-quality-tab"></a>[整體通話品質] 索引標籤

使用此索引標籤上的資料來評估通話品質狀態，以及根據串流數與較差百分比的趨勢。 右上角的圖例會顯示哪些色彩和視覺元素代表這些度量單位。
  
![螢幕擷取畫面：顯示 [通話品質] 索引標籤](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
串流分為三個群組： [完好]、[差] 和 [未分類]。 此外，也會計算出*較差的%* 值，可讓您將資料流程分類為不*佳*至總分類資料流程計數的比例。 由於*差% = 無法正常使用的資料流程/（資料流程 + 良好資料流程） * 100*，*糟糕的%* 不會受到多個未*分類*資料流程的存在影響。 若要查看如何將串流分類為不良或良好，請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md)。
  
使用左邊的刻度來測量串流計數值。
  
![螢幕擷取畫面：顯示資料流程計數值](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右側的刻度來測量較差的% 值。
  
![螢幕擷取畫面：顯示差% 的值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
您也可以將滑鼠游標停留在列上方，以取得實際數值。
  
> [!NOTE]
> 下列範例是來自非常小的範例資料集，且這些值對於實際部署而言並不切合實際。
  
![螢幕擷取畫面：顯示用來存取資料的滑鼠](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
整個串流大量可協助判斷計算出的低百分比。 總體資料流程的數量越小，報告的低百分比值就越不可靠。
  
### <a name="server-client-tab-and-client-client-tabs"></a>[伺服器-用戶端] 索引標籤和用戶端用戶端索引標籤

這兩個索引標籤提供在其端點對端點案例中所發生之資料流程的詳細資料。 [伺服器-用戶端] 索引標籤有四個可折迭的區段，分別代表媒體資料流程流向的四種案例。
  
- 有線內
- 外有線
- 內部 Wifi
- Wifi 外

同樣地，[用戶端-用戶端] 索引標籤有五個可折疊區段：

- 有線內-內側-有線
- 有線內-向外佈線
- 有線外-有線外側
- 內側無線內-Wifi 內側
- 內側無線-Wifi 外

#### <a name="inside-test"></a>內部測試

在處理期間，CQD 後端會使用建築物資訊（如果有的話）將串流分類為*內部*或*外部*。 每個串流的端點都會與子網位址產生關聯。 如果子網位於已上傳的建築物資訊中標示為 InsideCorp 的子網清單中，則會被視為*內部*。 如果建築物資訊尚未上傳，請在測試中永遠將串流分類為*外部*。  

> [!NOTE]
> 伺服器用戶端案例的內部測試只會考慮用戶端端點。 因為伺服器永遠都不是從使用者的角度來看，所以在測試中並不考慮。
  
#### <a name="wired-vs-wifi"></a>有線與 wifi

如名稱所指出，分類準則是以用戶端連線的類型為基礎。 同樣地，伺服器總是是有線的，而且不會包含在計算中。
  
> [!NOTE]
> 如果有一個資料流程，如果兩個端點中有一個連接至 Wifi 網路，則會在 CQD 中分類為 Wifi。
  
## <a name="selecting-product-data-to-see-in-reports"></a>選取要在報表中查看的產品資料

<a name="BKMKProductFilter"></a>

您可以在 [摘要] 和 [位置] 增強式報表中，使用 [**產品篩選**] 下拉式清單來顯示所有產品資料、只顯示 Microsoft 團隊資料，或只顯示商務用 Skype Online 資料。
  
![螢幕擷取畫面：顯示 [產品] 篩選控制項選項](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
在 [詳細報告] 中，您可以使用 [**成為團隊**維度] 來篩選資料至 Microsoft 團隊或商務用 Skype Online 資料。
  
## <a name="upload-tenant-data-information"></a>上傳租使用者資料資訊

<a name="BKMKTenantDataInformationUpload"></a>

CQD 摘要報告儀表板包含**租使用者資料上傳**頁面，方法是從右上角的 [設定] 功能表中選取 [**租使用者資料上傳**]。 此頁面可供系統管理員上傳自己的資訊，例如：

- IP 位址與地理位置資訊的地圖
- 每個無線 AP 及其 MAC 位址的地圖
- 端點和模型/類型等的端點地圖。
  
> [!NOTE]
> 您上傳至 CQD 的報告標籤會在您的 Office 365 協定下處理為*支援資料*，包括任何其他應視為*客戶資料*或*個人資料*的資訊。 請勿包含您不想提供給 Microsoft 做為*支援資料*的資料，microsoft 工程師將能看到此資訊以供支援使用。

![螢幕擷取畫面：顯示通話品質儀表板租使用者資料](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在 [**租使用者資料上傳**] 頁面上，使用下拉式功能表選擇要上傳的資料檔案類型。 [檔案] 資料類型代表檔案的內容（例如，"建築物" 指的是 IP 位址與建築物及其他地理位置資訊，"端點" 是指將端點名稱對應到 Endpoint 產生/模型/類型資訊）。 目前 CQD 支援 cqd.teams.microsoft.com 的 "建築物" 和 "Endpoint" 資料類型（在預覽階段中，尚未正式提供），cqd.lync.com 只支援 "建築物" 資料類型。



2. 選取 [檔案] 資料類型之後，按一下 **[流覽]** 以選擇資料檔案。

   - 資料檔案必須是. tsv （以定位字元分隔的值）檔案或 .csv （逗號分隔值）檔案。 如果使用 .csv 檔案，任何包含逗號的欄位都必須以引號括住，或移除逗號。 例如，如果您的建築物名稱是 NY，NY，請在 .csv 檔案中輸入「NY，NY」。
   - 資料檔案不能大於 50 MB。
   - 上傳到 cqd.teams.microsoft.com 的檔案的展開列限制為1000000，以讓查詢效能保持在快速。 這個限制也適用于 CQD<span></span><span></span>上的 CQD v2。
   - 針對每個資料檔案，檔案中的每一欄都必須符合預先定義的資料類型，本主題稍後將討論。
3. 接下來，指定**開始日期**，並根據需要**指定結束日期**。
4. 最後，選取 **[上傳**]，將檔案上傳到 CQD 伺服器。
    檔案上傳之前，先進行驗證。 驗證之後，就會儲存在 Azure blob 中。 如果驗證失敗，或檔案無法儲存在 Azure blob 中，錯誤訊息會要求對檔案進行修正。 下列圖像顯示的是資料檔中的欄數不正確的樣本錯誤。

     ![螢幕擷取畫面：顯示上傳驗證錯誤](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果驗證期間沒有發生任何錯誤，檔案上傳就會成功。 然後，您就可以在 [我的上**傳**] 資料表中看到上傳的資料檔案。 該頁面的底部也會顯示目前租使用者上傳之所有檔案的完整清單。
    每個記錄會顯示一個上傳的租使用者資料檔，其中包含檔案類型、上次更新時間、時間段、描述、移除圖示及下載圖示。 若要移除檔案，請選取表格中的 [回收站] 圖示。 若要下載檔案，請選取表格 [**下載**] 欄中的 [下載] 圖示。

     ![螢幕擷取畫面：顯示 [我的上傳] 表格](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. 如果您選擇使用多個建立資料檔案或多個端點資料檔，某些報告產生的速度會更慢。

### <a name="tenant-data-file-format-and-structure"></a>租使用者資料檔案格式與結構

<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>建立資料檔案

CQD 使用建築物資料檔，這可協助提供有用的通話詳細資料。 [子網] 欄是透過展開 [網路 + NetworkRange] 欄，然後將 [子網] 欄加入通話記錄的第一個子網或 [第二個子網] 欄，來顯示建築物、城市、國家或地區資訊。 您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：

您可以[在此](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下載範例範本
  
- 檔案必須是 tsv 檔案（由索引標籤分隔欄）或 .csv 檔案（欄以逗號分隔）。
- 資料檔案不包含表格標題列。 資料檔案的第一行應該是真實資料，而不是標頭標籤（例如「網路」）。
- 檔案中的資料類型只能是 String、Integer 或 Boolean。 針對整數資料類型，此值必須是一個數值。 布林值必須是0或1。
- 如果資料行使用 [字串] 資料類型，資料欄位可以是空的，但仍必須以 tab 或逗號分隔。 空白資料欄位只會指派空的字串值。
- 每個資料列都必須有14個數據行，每一欄都必須具有適當的資料類型，且欄必須按照下表所列的順序排列：

||||||||||||||||
|:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:--- |:---  |:--- |:---|
|**欄欄位名稱**|NetworkIP  |NetworkName              |NetworkRange|BuildingName  |OwnershipType| BuildingType  |BuildingOfficeType|座   |郵遞區號|國家|市 |地區|InsideCorp&dagger;|ExpressRoute&Dagger;|VPN （選用）|
|**資料類型**        | String    | String                  |電話      | String       | String      | String        |String            |String |String |String |String|String|Boolean   |Boolean     |Boolean|
|**範例值**    |192.168.1.0|美國/西雅圖/西雅圖-海-1| 26         | 北京-海-1| 尚未     | 終止|工程學       |西雅圖|98001  |一下     |華盛頓    |MSUS  | 1        |0           | 0|
|||||||||||||||||

&dagger;此設定可用於反映子網是否位於公司網路內。 您可以根據自己的需求來自訂其他用途的使用方式。

&Dagger;此設定可用於反映網路是否使用 Azure ExpressRoute。 您可以根據自己的需求來自訂其他用途的使用方式。  

**範例列：**

`192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> 網路範圍可用來代表 supernet （多個子網與單一路由前置詞的組合）。 所有新的建築物上傳都會被檢查，以取得任何重迭的範圍。 如果您先前上傳的是組建檔案，您應該下載目前的檔案，然後重新上傳以找出任何重疊，並修正問題，然後再重新上傳。 先前上傳的檔案中的任何交疊，可能會導致無法正確地將子網對應至報表中的建築物。 某些 VPN 實現不會精確地報告子網資訊。 建議將 VPN 子網新增至組建檔案，而不是子網的一個專案時，會針對 VPN 子網中的每個位址，為個別的32位網路新增個別專案。 每個資料列都可以有相同的建築物中繼資料。 例如，172.16.18.0/24 不只一列，您應該有256列，每個位址都有一個資料列，其中每個位址都在 172.16.18.0/32 和 172.16.18.255/32 之間（含）。
>
> [VPN] 欄是選擇性的，預設為0。  如果 VPN 欄的值設為1，則該資料列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。  請謹慎使用這個方式，然後只針對 VPN 子網，因為完全擴充這些子網會對涉及建立資料之查詢的查詢時間造成負面影響。

### <a name="endpoint-data-file"></a>端點資料檔案

CQD 會使用端點資料檔案。 欄值會用於通話記錄的第一個用戶端端點名稱或第二個用戶端端點名稱欄，以顯示端點、模型或類型資訊。 您上傳的資料檔案格式，必須符合下列準則，才能在上傳前進行驗證檢查：

- 檔案必須是 tsv 檔案（由索引標籤分隔欄）或 .csv 檔案（欄以逗號分隔）。
- 資料檔案的內容不會包含表格標題。 資料檔案的第一行應該是真實資料，而不是像是 "終結點" 這樣的標頭標籤。
- 所有七個數據列都只使用字串資料類型。 允許的最大長度為64個字元。
- 資料欄位可以是空的，但仍須以 tab 或逗號分隔。 空白資料欄位只會指派空的字串值。
- 終結點必須是唯一的，否則上傳就會失敗。 如果有重複的資料列，或是兩列使用相同的終結點，衝突將會導致不正確的聯接。
- EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自訂的標籤。 它們可以是空白字串或 "IT 部門指派2018膝上型電腦" 或 "資產標記 5678" 等值。
- 每個資料列必須有七個數據行，且欄必須以下列順序排列：

  **欄位順序：**

終結點、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3

  **範例列：**

' 1409W3534，123製造商，Fabrikam 模型123，膝上型電腦，IT 指派2018膝上型電腦，資產標籤5678，購買2018

## <a name="migrate-reports-from-previous-version-of-cqd"></a>從舊版本的 CQD 遷移報表

如果您在商務用 Skype 中建立報告或上傳的租使用者資料（對應）https://cqd.lync.com)檔案至 CQD （並想要將它們遷移https://cqd.teams.microsoft.com)至小組的 CQD），請參閱：

1.  移至[https://cqd.lync.com/cqd/](https://cqd.lync.com/cqd/)並流覽至您要匯出的報表集合。 
2.  將游標暫留在報表上，然後在 [...]功能表中，選擇 [**匯出報表樹**]。 儲存匯出檔案。
3.  移至[https://cqd.teams.microsoft.com/cqd/](https://cqd.teams.microsoft.com/cqd/)並流覽至您要匯入報表的位置。
4.  從左側的連結中，按一下 [匯**入**]，然後選取匯出的檔案。 
5.  匯入報告之後，您會看到以下訊息：「已成功匯入報告。 新的報表已在報表集的結尾新增。」 


## <a name="create-custom-detailed-reports"></a>建立自訂的詳細報告

如果您發現想要以提供的詳細報告以外的方式來建立焦點在資料維度上的特定報表，請建立自訂報表。

\(從 [登入**摘要報告**]\)畫面所顯示之畫面頂端的 [報告] 下拉式清單中，選取 [**詳細報告**] **，然後在**報告的 [動作] 功能表中，按一下 [編輯]，以查看 [查詢編輯器]。 每個報告都會以查詢的方式支援到立方體中。 報表是其查詢所傳回資料的視覺效果。 [查詢編輯器] 可協助您編輯這些查詢和報表的顯示選項。 當您開啟新報表的 [查詢編輯器] 時，您會看到類似此螢幕擷取畫面的內容：

![編輯新報表](media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. 在左窗格中選取 [維度]、[量值] 和 [篩選]。 按一下標題旁邊的 [加號] 按鈕，以開啟對話方塊，您可以在其中新增維度、測量或篩選，並核取對應的方塊。 如果您編輯現有的報表，您可以取消核取現有的值以將其移除。 如需詳細資訊，請參閱[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)。
2. 圖表自訂的選項會顯示在頂端。
3. 報表的預覽可在 [查詢編輯器] 中取得。
4. 您可以在底部的 [編輯] 方塊中建立詳細的報表名稱和描述。

## <a name="frequently-asked-questions"></a>常見問題

### <a name="why-does-my-cqd-v2-report-data-look-different-than-the-cqd-v3-report-data"></a>為什麼 CQD v2 報告資料看起來與 CQD v3 報告資料不同？ 

如果您看到 CQD v2 與 v3 之間的資料差異，請確定資料比較或驗證是在 "蘋果" 和 [窄] 層級完成，而不是 [匯總層級]。 例如，如果您篩選兩個報告以進行 MSIT ' 建築物 30 ' WiFi 小組桌面用戶端資料，那麼在 v2 與 v3 之間，品質較差的百分比應該相同。

CQD v2 和 CQD v3 具有不同的總計數，因為 CQD v3 有新的案例不在 CQD v2 中。 [摘要總計] 或 [匯總] 不含篩選的所有數位，都應該是不同的。  

如果使用案例包含商務用 Skype Server 2019 通話，CQD v3 資料包括 Skype Bot 呼叫（自動語音應答、CVI、虛擬桌面介面）、即時事件和 PSTN 通話。 CQD v2 不使用此資料。 （CQD v3 需要已設定雲端資料連線器的商務用 Skype Server 2019。）

例如，如果您在 CQD v2 摘要報告中看到200000音訊串流，5000且出現5500失敗的300000音訊資料流程（差別可能是由於商務用 Skype Server 2019 通話、CVI 通話、PSTN 通話等等），在 CQD v3 摘要報告中。

若要消除不預期的差異，請查看整個資料的多個細目分類。 根據下列一個或多個參數篩選資料：

- 使用者代理類別對
- 第一個產品
- 第二個產品

### <a name="other-expected-differences-between-cqd-v2-and-cqd-v3"></a>CQD v2 與 CQD v3 之間的其他預期差異

團隊中有幾項品質與可靠性改善功能，但在商務用 Skype Online 中則不會有這些改進：

- 自動重新連線
- 快速漫遊
- 改良的 BW 管理

當您比較這兩個服務的資料時：

- 挑選一個具有緊密焦點的案例，例如公司有線連線、Windows 桌面或單一區域或組建。
- 檢查 [團隊 MR]、[TR] 或 [MP IP 範圍]。 團隊範圍比商務用 Skype Online 還新，可能會導致防火牆產生連線問題
- 不要比較摘要或最上層的數位。 這些比較將會使您能夠將公司有線連線的大型通話量與商務用 Skype Online 通話數與 LTE 或私人網路上的大量小組通話進行比較。
- 請注意，位置偏向及人口差異：有許多比較過於不同的比較都很有用：
  - NOAM： APAC
  - 紐約州： Goa
  - 有線： wifi
  - 公司網路：家用網路
  
### <a name="why-cant-i-see-euii-in-cqd"></a>為什麼在 CQD 中看不到 EUII？

這些系統管理員角色可以存取 CQD，但他們無法查看 EUII （使用者可辨識的資訊）：
- Office 365 報告閱讀程式
- 團隊溝通支援專家

若要深入瞭解可存取 CQD 的角色，包括 EUII 讀取[指派角色以存取 CQD](quality-of-experience-review-guide.md#assign-roles-for-accessing-cqd)。

### <a name="why-am-i-seeing-skype-for-business-information-in-cqd-when-ive-filtered-for-teams-only"></a>為什麼我只針對團隊進行篩選時，我會在 CQD 中看到商務用 Skype 資訊？

如果您只在 CQD 報表（isTeams = 1）中篩選團隊，則會針對*第一個端點*為團隊的所有呼叫進行篩選。 如果*第二個端點*是商務用 Skype，該資訊將會顯示在您的 CQD 報告中。

## <a name="related-topics"></a>相關主題

[通話品質儀表板中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[通話品質儀表板中的資料流分類](stream-classification-in-call-quality-dashboard.md)

[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用通話分析來疑難排解不良通話品質](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[通話分析和通話品質儀表板](difference-between-call-analytics-and-call-quality-dashboard.md)
