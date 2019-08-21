---
title: 開啟並使用通話品質儀表板
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
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
description: '瞭解如何開啟並使用商務用 Skype Online 的通話品質儀表板, 並取得通話品質的摘要報告。 '
ms.openlocfilehash: cf937a159eba723ee4ac7fc2ae01aa733e57170f
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483767"
---
# <a name="turning-on-and-using-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>開啟並使用 Microsoft 團隊及商務用 Skype Online 的通話品質儀表板

瞭解如何設定您的 Office 365 組織, 以使用通話品質儀表板來監控通話品質。
  
Microsoft 團隊和商務用 Skype Online 的通話品質儀表板 (CQD) 可讓您深入瞭解使用 Microsoft 團隊和商務用 Skype 服務所進行的通話品質。 本主題描述開始收集資料所需完成的步驟。
  
  
## <a name="latest-changes-and-updates"></a>最新變更與更新

最近的 CQD 變更如下所示:
  
- 包括 Microsoft 團隊資料 (除了商務用 Skype Online 資料之外)。
    
- 摘要報告包含 [產品] 篩選器, 可供您選取 [所有資料]、[Microsoft 團隊資料] 或 [商務用 Skype Online] 資料。

- 已更新視頻與 VBSS 資料流程品質分類邏輯。 請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md), 以取得最新的分類器定義。

請參閱這篇文章, 以取得[通話品質儀表板中提供的維度與量值](dimensions-and-measures-available-in-call-quality-dashboard.md)的清單。
  
> [!NOTE]
> 您可以按一下 [**好消息**] 中的連結, 找到有關儀表板更新和變更的資訊! 顯示在儀表板上的橫幅。
  
## <a name="activate-microsoft-call-quality-dashboard-cqd-summary-reports"></a>啟動 Microsoft 通話品質儀表板 (CQD) 摘要報告

在您開始使用 CQD 之前, 您必須針對您的 Office 365 組織啟用它。

![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示
 
1. 使用 Microsoft 團隊服務系統管理員帳戶登入您的 Office 365 組織, 然後選取 [系統**管理**] 磚以開啟系統管理中心。
    
2. 在左窗格中的 [系統**管理中心**] 底下, 選取 [ **microsoft 團隊**] 以開啟 microsoft 團隊系統管理中心。
    
3. 在 Microsoft [團隊管理中心] 中, 選取左窗格中的 [**通話品質儀表板**]。
    
  
4. 在開啟的頁面上, 使用您的全域系統管理員帳戶或 Microsoft 團隊服務系統管理員帳戶登入, 然後在出現提示時提供該帳戶的認證。
    
     ![顯示 [認證提示] 的螢幕擷取畫面](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登入後, CQD 就會開始收集及處理資料。  
> [!NOTE]
> 可能需要幾個小時的時間來處理足夠的資料, 才能在報表中顯示有意義的結果。 

![](media/sfb-logo-30x30.png) **使用商務用 skype 系統管理中心**顯示商務用 skype 標誌的圖示
 
1. 使用系統管理員帳戶登入您的 Office 365 組織, 然後選取 [系統**管理**] 磚以開啟系統管理中心。
    
2. 在左窗格中的 [系統**管理中心**] 底下, 選取 [**商務用 skype** ] 以開啟商務用 skype 系統管理中心。
    
3. 在商務用 Skype 系統管理中心中, 選取左窗格中的 [**工具**], 然後選取 [**商務用 Skype Online 通話品質儀表板**]。
    
     ![螢幕擷取畫面顯示選取通話品質儀表板](media/6cc7f80f-b8e2-4a9b-aab8-ac871d07a261.png)
  
4. 在開啟的頁面上, 使用您的全域系統管理員帳戶登入, 然後在出現提示時提供該帳戶的認證。
    
     ![顯示 [認證提示] 的螢幕擷取畫面](media/ac4c1699-d8c1-4bda-af30-0fec35b5fd22.png)
  
登入後, CQD 就會開始收集及處理資料。


  
## <a name="features-of-the-call-quality-dashboard-for-microsoft-teams-and-skype-for-business-online"></a>Microsoft 團隊和商務用 Skype Online 的通話品質儀表板功能 
<a name="BKMKFeaturesOfTheCQD"> </a>

CQD 摘要報告提供規劃詳細報告之功能的子集。 這兩種版本之間的差異摘要如下:
  
|**功能**|**摘要報告**|**詳細報告**|
|:-----|:-----|:-----|
|應用程式共用躍點數  <br/> |不  <br/> |是的  <br/> |
|客戶建立資訊支援  <br/> |是的  <br/> |是的  <br/> |
|用戶端點資訊支援  <br/> |僅限 cqd.teams.microsoft.com  <br/> |僅限 cqd.teams.microsoft.com  <br/> |
|向下切入分析支援  <br/> |不  <br/> |是的  <br/> |
|媒體可靠性度量單位  <br/> |不  <br/> |是的  <br/> |
|外框報告  <br/> |是的  <br/> |是的  <br/> |
|[總覽] 報表  <br/> |是的  <br/> |是的  <br/> |
|每個使用者的報表集  <br/> |不  <br/> |是的  <br/> |
|報表集自訂 (新增、刪除、修改報告)  <br/> |不  <br/> |是的  <br/> |
|以影片為基礎的畫面共用規格  <br/> |不  <br/> |是的  <br/> |
|影片度量單位  <br/> |不  <br/> |是的  <br/> |
|可用的資料量  <br/> |過去6個月  <br/> |過去6個月  <br/> |
|Microsoft 團隊資料  <br/> |是的  <br/> |是的  <br/> |
   
### <a name="out-of-the-box-reports"></a>外框報告

這兩個版本的 CQD 都提供全新的體驗, 讓您可以呼叫品質指標, 而不需要建立任何新的報表。 在後端處理完資料之後, 您就可以開始在報表中查看通話品質資料。
  
### <a name="overview-reports"></a>[總覽] 報表

這兩個版本的 CQD 都提供了整體通話品質資訊的高層進入點, 但資訊在摘要報告中呈現的方式與詳細報告的方式不同。
  
[摘要報告] 提供簡化的索引標籤式頁面報表檢視, 可讓使用者快速流覽並瞭解整體通話品質狀態與趨勢。
  
四個索引標籤包括:
  
- **整體通話品質**-提供所有資料流程的相關資訊, 這些資料流程是伺服器用戶端資料流程與用戶端資料流程的匯總, 以及獨立的伺服器用戶端和用戶端資料流程, 其形式為每月和每日趨勢。
    
- **伺服器-用戶端**-針對伺服器與用戶端端點之間的資料流程提供其他詳細資料。
    
- **用戶端-用戶端**-針對兩個用戶端端點之間的資料流程提供其他詳細資料。
    
- **語音品質 SLA** -提供包含在商務用 Skype Online 語音品質 SLA 中之通話的相關資訊。
    
### <a name="overall-call-quality-tab"></a>[整體通話品質] 索引標籤

使用此索引標籤上的資料, 透過查看串流數量及較差的百分比來評估通話品質狀態與趨勢。 右上角的圖例會顯示哪些色彩和視覺元素代表這些度量單位。
  
![顯示 [通話品質] 索引標籤的螢幕擷取畫面](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)
  
串流分為三個群組: [完好]、[差] 和 [未分類]。 此外, 也會計算出*較差的%* 值, 可讓您將資料流程分類為不*佳*至總分類資料流程計數的比例。 由於*差% = 無法正確的資料流程/(資料流程 + 良好資料流程) * 100* , 這會讓目前狀態與多個未*分類*資料流程產生不受影響的*差%* 。 針對用來將串流分類為不良或良好的用途, 請參閱[通話品質儀表板中的資料流程分類](stream-classification-in-call-quality-dashboard.md)。
  
使用左邊的刻度來測量串流計數值。
  
![顯示串流計數值的螢幕擷取畫面](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)
  
使用右側的刻度來測量較差的% 值。
  
![螢幕擷取畫面顯示較差的% 值](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)
  
您也可以將滑鼠游標停留在列上方, 以取得實際數值。
  
> [!NOTE]
> 下列範例是來自非常小的範例資料集, 且這些值對於實際部署而言並不切合實際。 
  
![顯示使用滑鼠存取資料的螢幕擷取畫面](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)
  
整個資料流量是判斷計算出不佳百分比的相關程度的重要因素。 總體資料流程的數量越小, 報告的低百分比值就越不可靠。
  
### <a name="server-client-tab-and-client-client-tabs"></a>[伺服器-用戶端] 索引標籤和用戶端用戶端索引標籤

這兩個索引標籤提供在其端點對端點案例中所發生之資料流程的其他詳細資料。 [伺服器-用戶端] 索引標籤有四個可折迭的區段, 代表媒體資料流程流向的四種案例。
  
- 有線內
    
- 外有線
    
- 內部 Wifi
    
- Wifi 外

同樣地, [用戶端-用戶端] 索引標籤有五個可折疊區段:

- 有線內

- 有線內-在外有線

- 有線外部-有線外

- 內部-Wifi 內側

- 有線內部-Wifi 外
    
    
#### <a name="inside-test"></a>內部測試

在處理期間, CQD 後端會使用建築物資訊 (如果有的話) 將串流分類為*內部*或*外部*。 每個串流的端點都會與子網位址產生關聯。 如果子網位於已上傳的建築物資訊中標示為 InsideCorp 的子網清單中, 則會被視為*內部*。 如果建築物資訊尚未上傳, 則在測試中將永遠會將資料流程分類為*外部*。 請注意, 在伺服器用戶端案例的內部測試中, 只會考慮用戶端端點。 因為伺服器永遠都不是從使用者的角度來看, 所以在測試中並不考慮。
  
#### <a name="wired-vs-wifi"></a>有線與 wifi

如名稱所指出, 這是依據用戶端連線類型的分類準則。 同樣地, 伺服器總是是有線的, 而且不會包含在計算中。
  
> [!NOTE]
> 如果有一個資料流程, 如果兩個端點中有一個連接至 Wifi 網路, 則會在 CQD 中分類為 Wifi。 
  
## <a name="selecting-product-data-to-see-in-reports"></a>選取要在報表中查看的產品資料
<a name="BKMKProductFilter"></a>

您可以在 [摘要] 和 [位置] 增強式報表中, 使用 [**產品篩選**] 下拉式清單來顯示所有產品資料、只顯示 Microsoft 團隊資料, 或只顯示商務用 Skype Online 資料。
  
![顯示 [產品] 篩選控制項選項的螢幕擷取畫面](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)
  
在 [詳細報告] 中, 您可以使用 [**成為團隊**維度] 來篩選資料至 Microsoft 團隊或商務用 Skype Online 資料 (請見定義報表)。
  
## <a name="upload-tenant-data-information"></a>上傳租使用者資料資訊
<a name="BKMKTenantDataInformationUpload"></a>

CQD 摘要報告儀表板包含**租使用者資料上傳**頁面, 方法是從右上角的 [設定] 功能表中選取 [**租使用者資料上傳**]。 此頁面可供系統管理員上傳自己的資訊, 例如 IP 位址和地理資訊的對應、對應每個無線 AP 及其 MAC 位址、將端點對應到端點產生/模型/類型等。
  
![顯示 [通話品質] 儀表板的螢幕擷取畫面](media/839c9ab4-0246-46c9-8402-aafd83a0bc63.png)
  
1. 在 [**租使用者資料上傳**] 頁面上, 使用下拉式功能表, 選擇要上傳的資料檔案類型。 [檔案] 資料類型代表檔案的內容 (例如, "建築物" 代表 IP 位址與建築物以及其他地理位置資訊, "端點" 代表將端點名稱對應到端點 [建立/模型/類型 ...]。 資訊)。 我們目前支援針對 cqd.teams.microsoft.com 上傳「大樓」和「端點」資料類型 (在預覽階段中, 尚未正式提供), cqd.lync.com 只支援上傳「組建」資料類型。 後續版本中將會新增更多的資料類型。
    
2. 選取 [檔案] 資料類型之後, 按一下 **[流覽]** 以選擇資料檔案。
    
   - 資料檔案必須是. tsv (以 Tab 分隔的值) 檔案或 .csv (逗號分隔值) 檔案。 如果使用 .csv 檔案, 任何包含逗號的欄位都必須以引號括住, 或移除逗號。 例如, 如果您的建築物名稱是 NY、NY, 請在 .csv 檔案中輸入 "NY, NY"。
    
   - 資料檔的大小必須不超過不可50MB。

   - 上傳到 cqd.teams.microsoft.com 的檔案已展開的列限制為 1000000, 以便保持查詢效能。 我們也可能會在 cqd.lync.com 上強加該限制。
    
   - 針對每個資料檔案, 檔案中的每一欄都必須符合預先定義的資料類型, 本主題稍後將討論。
    
3. 選取資料檔之後, 請指定**開始日期**, 也可以**指定結束日期**。
    
4. 選取 [**開始日期**] 後, 選取 **[上傳**], 將檔案上傳到 CQD 伺服器。
    
    檔案上傳之前, 先進行驗證。 驗證之後, 就會儲存在 Azure blob 中。 如果驗證失敗, 或檔案無法儲存在 Azure blob 中, 則會顯示一則錯誤訊息, 要求對檔案進行修正。 下列影像顯示當資料檔案中的欄數不正確時, 會發生錯誤。
    
     ![顯示上傳驗證錯誤的螢幕擷取畫面](media/22716a32-3d3d-4870-983c-46089e8b212a.png)
  
5. 如果驗證期間沒有發生任何錯誤, 檔案上傳就會成功。 接著, 您可以在 [我的上**傳**] 資料表中看到上傳的資料檔, 該檔案會在該頁面的底部顯示目前租使用者的所有已上傳檔案的完整清單。
    
    每個記錄會顯示一個上傳的租使用者資料檔, 其中包含檔案類型、上次更新時間、時間段、描述、移除圖示及下載圖示。 若要移除檔案, 請選取表格中的 [回收站] 圖示。 若要下載檔案, 請選取表格 [**下載**] 欄中的 [下載] 圖示。
    
     ![顯示 [我的上傳] 資料表的螢幕擷取畫面](media/4168a883-bbea-461a-80b1-42eedf2e7732.png)

6. 請注意, 如果您選擇使用多個建立資料檔案或多個端點資料檔, 一些報告的作業速度會較慢。

### <a name="tenant-data-file-format-and-structure"></a>租使用者資料檔案格式與結構
<a name="BKMKTenantDataFile"> </a>

### <a name="building-data-file"></a>建立資料檔案
CQD 會先從展開 [網路 + NetworkRange] 欄, 然後將 [子網] 欄加入至通話記錄的第一個子網/第二個子網欄, 以顯示建築物/城市/國家/地區 .。。 錯誤資訊. 您上傳的資料檔案格式必須符合下列規則, 才能在上傳前通過驗證檢查。
  
- 檔案必須是一個 tsv 檔案, 也就是說, 在每個資料列中, 欄會以一個索引標籤分隔, 或是以逗號分隔每個資料行的 .csv 檔案。
    
- 資料檔案的內容不會包含表格標題。 這表示資料檔案的第一行應該是真實資料, 而不是像是「網路」等的標頭。
    
- 針對每個資料行, 資料類型只能是 String、Number 或 Bool。 如果是 Number, 則該值必須是一個數值;如果是 Bool, 則該值必須是0或1。
    
- 針對每個資料行, 如果資料類型是 string, 則資料可以是空白 (但必須以適當的分隔符號 (亦即定位字元或逗號) 分隔。 這只會將該欄位指派為空白字串值。
    
- 每個資料列都必須有14個數據行, 每一欄都必須具有下列資料類型, 且欄必須按照下表所列的順序排列:
    
|**欄名稱**|**資料類型**|**範例**|
|:-----|:-----|:-----|
|局域網  <br/> |String  <br/> |192.168.1.0  <br/> |
|NetworkName  <br/> |String  <br/> |美國/西雅圖/西雅圖-海-1  <br/> |
|NetworkRange  <br/> |電話  <br/> |26  <br/> |
|BuildingName  <br/> |String  <br/> |北京-海-1  <br/> |
|OwnershipType  <br/> |String  <br/> |尚未  <br/> |
|BuildingType  <br/> |String  <br/> |終止  <br/> |
|BuildingOfficeType  <br/> |String  <br/> |工程學  <br/> |
|座  <br/> |String  <br/> |西雅圖  <br/> |
|郵遞區號  <br/> |String  <br/> |98001  <br/> |
|國家  <br/> |String  <br/> |一下  <br/> |
|市  <br/> |String  <br/> |華盛頓  <br/> |
|國家  <br/> |String  <br/> |MSUS  <br/> |
|InsideCorp  <br/> |Bool  <br/> |sr-1  <br/> |
|ExpressRoute  <br/> |Bool  <br/> |0  <br/> |
   
> [!IMPORTANT]
> 網路範圍可用來代表 supernet (多個子網與單一路由前置詞的組合)。 所有新的建築物上傳都會被檢查, 以取得任何重迭的範圍。 如果您先前上傳的是組建檔案, 您應該下載目前的檔案, 然後重新上傳以找出任何重疊, 並修正問題, 然後再重新上傳。 先前上傳的檔案中的任何交疊, 可能會導致無法正確地將子網對應至報表中的建築物。 某些 VPN 實現不會精確地報告子網資訊。 建議將 VPN 子網新增至組建檔案, 而不是子網的一個專案時, 會針對 VPN 子網中的每個位址, 為個別的32位網路新增個別專案。 每個資料列都可以有相同的建築物中繼資料。 例如, 172.16.18.0/24 不只一列, 您應該有256列, 每個位址都有一個資料列, 其中每個位址都在 172.16.18.0/32 和 172.16.18.255/32 之間 (含)。 

### <a name="endpoint-data-file"></a>端點資料檔案
CQD 會使用端點資料檔案, 方法是將其點字聯接至通話記錄的第一個用戶端端點名稱/第二個用戶端端點名稱欄, 以顯示端點產生/模型/類型資訊。 您上傳的資料檔案格式必須符合下列規則, 才能在上傳前通過驗證檢查。

- 檔案必須是一個 tsv 檔案, 也就是說, 在每個資料列中, 欄會以一個索引標籤分隔, 或是以逗號分隔每個資料行的 .csv 檔案。

- 資料檔案的內容不會包含表格標題。 這表示資料檔的第一行應該是實際資料, 而不是像是「終結點」等的標頭。

- 針對每個資料行, 資料類型只能是字串, 且不應超過64個字元 (最大允許長度)。

- 針對每一欄, 資料都可以是空白的 (但必須以適當的分隔符號 (亦即定位字元或逗號) 分隔。 這只會將該欄位指派為空白字串值。

- 每個資料列都必須有7欄, 且欄必須按照下表所列的順序排列。

- 終結點必須是唯一的, 否則上傳會因為重複的資料列而失敗, 因為這會造成不正確的聯接。

-  EndpointLabel1、EndpointLabel2、EndpointLable3 是使用者可自訂的標籤, 它們可以是空白字串或使用者喜歡的值, 例如「IT 部門指派2018膝上型電腦」、「資產標籤5678」 .。。等.

|**欄名稱**|**資料類型**|**範例**|
|:-----|:-----|:-----|
|點  <br/> |String  <br/> |1409W3534  <br/> |
|EndpointMake  <br/> |String  <br/> |Fabrikam Inc。  <br/> |
|EndpointModel  <br/> |String  <br/> |Fabrikam 模型123  <br/> |
|EndpointType   <br/> |String  <br/> |筆記本  <br/> |
|EndpointLabel1  <br/> |String  <br/> |指派2018膝上型電腦  <br/> |
|EndpointLabel2  <br/> |String  <br/> |資產標記5678  <br/> |
|EndpointLabel3  <br/> |String  <br/> |購買2018   <br/> |


## <a name="selecting-media-type-in-detailed-reports"></a>選取 [詳細報告] 中的媒體類型
<a name="BKMKMediaType"></a>

詳細報告支援針對音訊、影片、應用程式共用及影片式螢幕共用媒體類型, 查看品質與媒體的可靠性。 單一媒體類型專用的維度、量值及篩選, 具有 "音訊"、"影片"、"AppSharing" 或 "VBSS" 做為前置詞。
  
![螢幕擷取畫面顯示 [通話品質儀表板] 尺寸。](media/ae132202-d6dc-43bd-b8b3-ea9c24c519e8.png)
  
如果您想要針對單一媒體類型查看維度與量值, 可能需要新的媒體類型維度和篩選器。 例如, 若要讓報表顯示不同媒體類型的總會話計數, 請包含 [媒體類型] 維度。
  
![螢幕擷取畫面顯示 [通話品質儀表板總串流數]。](media/21d5d0dc-2321-415e-8ef2-cea06165601c.png)

## <a name="related-topics"></a>相關主題
[設定商務用 Skype 通話分析](set-up-call-analytics.md)

[使用呼叫分析來排查不佳的通話品質問題](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[[通話分析] 和 [通話品質儀表板]](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
