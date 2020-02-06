---
title: 使用商務用 Skype Server 的通話品質儀表板
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
ms.assetid: ec62b70f-885e-4272-b9d2-a574ea434b64
description: 摘要：瞭解如何使用通話品質儀表板。 [通話品質儀表板] 是商務用 Skype Server 的工具。
ms.openlocfilehash: 61b20062925f59474d387a022a92663e0ffcd6ba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816662"
---
# <a name="use-call-quality-dashboard-for-skype-for-business-server"></a>使用商務用 Skype Server 的通話品質儀表板

**摘要：** 瞭解如何使用通話品質儀表板。 [通話品質儀表板] 是商務用 Skype Server 的工具。

通話品質儀表板（CQD）可讓 IT 專業人員使用匯總資料來找出產生媒體質量問題的問題，方法是比較使用者群組的統計資料來識別趨勢和模式。 CQD 並非專注于解決個別的呼叫問題，但在識別適用于許多使用者的問題和解決方案上。

## <a name="call-quality-dashboard-user-guide"></a>通話品質儀表板使用者指南

CQD 是一種網頁入口網站，可根據體驗品質（QoE）資料快速建立及組織報表。 CQD 會部署一個 SSAS 立方體來匯總 QoE 公制資料庫中的資料，並讓系統管理員能夠即時建立及修改報告或進行調查。 雖然您可以使用 Excel 直接連線至立方體，但入口網站已針對多個涉及 QoE 資料的工作流程進行優化。 資料包括：

- 可快速存取的快取報表資料
- 深入瞭解資訊共用與發佈的報表頁面
- 簡化報表的編輯與建立，以及報表描述的可編輯中繼資料。

此外，CQD 會公開 web Api，讓使用者以程式設計方式存取要在自訂儀表板中使用的多維資料集資料。

### <a name="feature-overview"></a>功能概觀

當您流覽 [通話品質] 儀表板時，您會看到下列畫面：

![使用 CQD](../../media/1e061858-db6f-452b-9ae4-eab507220371.png)

1. 您可以在 [摘要窗格] 中找到 [報表集] （右側）的內容。
2. 按一下 [摘要 PaneReport] 中的 [編輯]，以設定階層屬性（包括 Y 軸高）。
3. 軌跡瀏覽可協助您識別報表集階層中您目前的位置。
4. 含有子報表的報表會以藍色連結顯示。 按一下連結以向下切入至 [子報表]。

將滑鼠移至橫條圖和趨勢線上方，以顯示詳細的值。 具有焦點的報表會顯示動作功能表： [編輯]、[克隆]、[刪除] 和 [下載]。

### <a name="default-reports"></a>預設報表

當您第一次存取通話品質儀表板入口網站時，系統會自動建立一組預設的報告。 這些報告有時稱為「系統報告」。 您可以透過建立新的同輩與子報表來自由修改或刪除這些報表或進行延伸。

在最上層，「音訊串流月趨勢」報告會顯示所有音訊資料流程的每月趨勢。 將滑鼠移至橫條圖中的條形上方，以顯示橫條圖所代表之資料的更詳細的視圖。 按一下 [音訊流量] 的 [每月趨勢報告] 標題，流覽至 [Managed vs 非託管音訊資料流程] 報告，其中的報告是在託管與未受管理的呼叫之間分割。 Managed 通話是透過有線連線在企業防火牆內進行的呼叫。 非託管通話包括從公司防火牆以外的電話，以及透過 Wi-fi 進行的所有通話。

其他最上層的報表稱為「使用者報告的通話品質評等長條圖」。 通話品質評等是通話結束時，商務用 Skype 使用者所提供的數位，表示通話的品質。 評分編號的範圍從1到5，1是最差，5是最佳的。 [長條圖] 會顯示在一個月中指定評等的音訊通話數量。

按一下任何報告的標題，即可在報表中流覽資料的其他篩選。 在系統報告中，每個子報表都會顯示其父報表中可用的資料子集。 解決問題的模型很簡單：調查資料或趨勢所限制的子報表，並逐漸縮小問題空間。 建立子報表的功能可讓您調查特定資料趨勢的原因。

### <a name="create-and-edit-reports"></a>建立及編輯報表

在報表的 [動作] 功能表中，按一下 [編輯]，查看 [報表編輯器]。 每個報告都會以查詢的方式支援到立方體中。 報表是其查詢所傳回資料的視覺效果。 [報告編輯者] 可協助您編輯這些查詢和報表的顯示選項。 當您開啟 [報表編輯器] 時，您會看到：

![使用 CQD](../../media/e8969625-e6f9-4d67-873f-93e78dd12b35.png)

1. 在左窗格中選取 [維度]、[量值] 和 [篩選]。 將游標暫留在其中一個現有的值上，以顯示 [x] 按鈕，讓您可以移除值。 按一下標題旁邊的 [加號] 按鈕，以開啟對話方塊，您可以在其中新增維度、量值或篩選。
2. 圖表自訂的選項會顯示在頂端。
3. 報表的預覽可在 [報表編輯器] 中取得。
4. 您可以在底部的 [編輯] 方塊中建立詳細的報表描述。

### <a name="sparklines-in-tables"></a>表格中的走勢圖

開始時，月份會新增為維度，而且資料會以表格表單中的趨勢轉譯，橫條圖和走勢圖會顯示在表格儲存格內。 將滑鼠指標移至橫條圖和 [走勢圖] 上方，以顯示個別月份的值。

![使用 CQD](../../media/fe6b18d7-b8cf-472a-9c93-0f7703f5a700.png)

若要顯示橫條圖及走勢圖，必須核取 [報表編輯器] 頂端的 [顯示走勢圖] 核取方塊。 這會選取趨勢選項並將 Month 移至最後一個維度，也可以按一下 [月]，然後使用向上鍵和向下鍵來將 [開始時間] 或 [下移]。

### <a name="settings"></a>設置

[設定] 功能表包含有用頁面的連結，例如 [系統健康情況] 和 [關於] 頁面，且位於儀表板的右上角。

![使用 CQD](../../media/0e9ae123-e231-4fea-94e1-5788e8f3e1d3.png)

是否顯示描述和時間戳記是由個別使用者決定，這些設定只會影響儀表板的個別版本，不會修改報告集或其他使用者所看到的內容。 清除快取會導致所有查詢從立方體重新載入其資料，而還原預設值時會刪除所有使用者建立或修改過的報告，並重新建立系統報告集—使用者第一次登入時會看到的內容。

[使用者儀表板] 連結會顯示一個頁面，使用者可以在其中查看 CQD 的其他使用者並流覽他們的報表。 若要共用報表集，請複製 URL 列中的連結，並與其他 CQD 使用者共用。 這個連結與其他使用者在 [使用者儀表板連結] 頁面上的使用者使用者名稱下看到的連結相同。

### <a name="supplying-subnet-information"></a>提供子網資訊

如果將網站特定資訊輸入到封存資料庫，以提供子網間的對應資訊（例如有線/無線通話品質（透過組建）），就可以顯示其他資訊。

至少要完成下清單格，才能建立這些報告：

- CqdBuilding
- CqdNetwork

您可以在 CqdBuildingType 和 CqdBuildingOwnershipType 資料表中提供其他資訊，以允許進一步篩選與向下切入。

這些資料表所用的資料定義如下：

**CqdBuilding**

|左欄|資料類型|允許 Null 嗎？|詳細資料|
|:-----|:-----|:-----|:-----|
|BuildingKey |int |否 |CqdBuilding 資料表的主鍵。 |
|BuildingName |Varchar （80） |否 |建築物名稱。 |
|BuildingShortName |Varchar （10） |否 |[建築物名稱] 的較短版本。 |
|OwnershipTypeId |int |否 |外鍵，與 CqdBuildingOwners 資料表中的其中一個專案相符。 |
|BuildingTypeId |int |否 |外鍵，與 CqdBuildingType 資料表中的其中一個專案相符。 |
|款 |浮 |是 |建築物的緯度。 |
|經度 |浮 |是 |建築物的經度。 |
|CityName |Varchar （30） |是 |建築物所在的市/縣名。 |
|郵遞區號 |Varchar （25） |是 |組建所在的郵遞區號。 |
|CountryShortCode |Varchar （2） |是 |組建所在國家/地區的 ISO 3166-1 字母2代碼。 |
|StateProvinceCode |Varchar （3） |是 |建築物所在之州/省的三個字母縮寫。 |
|InsideCorp |稍微 |是 |[位] 表示該組建是否為商業網路的一部分。 |
|BuildingOfficeType |Nvarchar （150） |是 |建立 office 類型的描述。 |
|地區 |Varchar （25） |是 |組建所在的地區。 |
|||||

**CqdNetwork**

|左欄|資料類型|允許 Null 嗎？|詳細資料|
|:-----|:-----|:-----|:-----|
|網路 |Varchar （25） |否 |子網位址。 |
|NetworkRange |Tinyint |是 |子網路遮罩。 |
|NetworkNameID |int |是 |選擇性地對應至 CqdNetworkName 資料表中的列。 |
|BuildingKey |int |是 |外鍵，與 CqdBuilding 資料表中的其中一個專案相符。 |
|UpdatedDate |datetime |否 |上次更新專案的日期時間。 |
||||||

根據預設，下一個資料表有一個專案（0，"Unknown"）。

**CqdBuildingType**

|左欄|資料類型|允許 Null 嗎？|詳細資料|
|:-----|:-----|:-----|:-----|
|BuildingTypeId |int |否 |CqdBuildingType 資料表的主鍵。 |
|BuildingTypeDesc |char （18） |否 |[建築物類型描述]。 |
|||||

根據預設，下一個資料表有一個專案（0，"Unknown"，0，null）。

**CqdBuildingOwnershipType**

|左欄|資料類型|允許 Null 嗎？|詳細資料|
|:-----|:-----|:-----|:-----|
|OwnershipTypeId |int |否 |CqdBuildingOwnershipType 資料表的主鍵。 |
|OwnershipTypeDesc |Varchar （25） |否 |擁有權類型描述。 |
|LeaseInd |Tinyint |是 |參照 CqdBuildingOwnershipType 資料表中另一列的索引，用於識別租的建築物。 |
|擁有者 |Varchar （50） |是 |建立擁有者。 |
|||||

根據預設，下一個資料表有一個專案（0，"Unknown"，0，null）。

**CqdBssid**

|左欄|資料類型|允許 Null 嗎？|詳細資料|
|:-----|:-----|:-----|:-----|
|面臨 |Nvarchar （50） |否 |CqdBssid 資料表的主鍵。 是 WiFi 存取點的 BSSID。 |
|員工 |Nvarchar （50） |是 |Wifi 存取點控制器資訊。 |
|phy |Nvarchar （50） |是 |Phy 資訊。 |
|應付 |Nvarchar （50） |是 |Wifi 存取點名稱。 |
|創建 |Nvarchar （500） |是 |WiFi 存取點所在的建築物名稱。 |
||||

## <a name="cqd-streams"></a>CQD 串流

CQD 串流被認為是良好、較差或未分類。 CQM 1.5 現在使用下列 CQD 定義：

- 不良的資料流程是不太穩定的呼叫指標的任何組合。
- 當通話中的一個資料流程不佳時，兩個通話串流都會標示為不佳。 在會議中，每個參與者都會算作唯一通話，而且會與其他人獨立報告。
- 未分類的資料流程是不含品質標準（也就是綜合交易或短通話）的資料流程。
- 有效的資料流程 = 非行動用戶端
- 無法修改分類器

**較差的通話定義/分類器**

|衡量|閾值|
|:-----|:-----|
|DegradationAvg |大於1.0 （-1 網路 MOS） |
|環路 |大於500 |
|PacketLossRate |大於0.1 （10%） |
|JitterInterArrival |超過30 |
|RatioConcealedSamplesAvg |大於0.07 |
|||

JPDR definition = 差的通話定義減去 RatioConcealedSamplesAvg

## <a name="where-is-callercallee"></a>來電者/被叫方的位置為何？

CQD 不使用 [來電者/被叫獲方程式] 欄位，而是使用 "First" 和 "Second"，因為來電者與被叫方之間有中間個步驟。

 **首先**如果資料流程中包含伺服器，則會一直是伺服器端點（例如，AV MCU 或轉送伺服器）。

 **秒**除非是伺服器-伺服器資料流程，否則將永遠是用戶端端點。

**第一和第二個分類範例**

|端點 1 UAType|端點 2 UUAType|一|第二個|
|:-----|:-----|:-----|:-----|
|2（AVMCU） |4（商務用 Skype） |端點1 |端點2 |
|2（AVMCU） |1（mMediationServer） |端點2 |端點1 |
|4（商務用 Skype） |4（商務用 Skype） |MediaLine 中的來電者 |MMediaLine 中的被呼叫者 |
|||||

如果兩個端點都是相同的類型，CQD 會先進行呼叫者輸入，然後再撥被叫方。 如需有關端點名稱的詳細資訊，請參閱[此博客](https://blogs.technet.com/b/jenstr/archive/2015/05/22/call-quality-dashboard-tips-and-tricks.aspx)。

## <a name="accounting-for-vpn"></a>VPN 記帳

如果已知 VPN 解決方案能正確設定 VPN 標誌，就是一切都已設定好了。 否則，請使用下列其中一種方法：

- 建立名為 [VPN （慣用）] 的網路類型，然後將 VPN 子網與這個新的 VPN NetworkType。
- 建立名為 [VPN] 的建築物，然後將 VPN 子網與此組建建立關聯。

## <a name="query-fundamentals"></a>查詢基礎

標準格式的查詢包含下列三個參數：

- 數值
- 焦點
- Filter

標準格式的查詢範例是「顯示我的資料流程不佳 [度量衡]：由子網 [Dimension] 用於建築物 6 [篩選]。」

## <a name="what-does-union-do"></a>UNION 運算是什麼？

[聯合] 可讓您使用 AND 運算子來篩選準則。 在某些情況下，您可以將多個篩選準則結合在一起，以達到與 OR 運算類似的結果。

範例：若要從建築物取得所有資料流程，同盟會提供合併資料集的獨特視圖。 若要使用 UNION，請在您想要合併的兩個篩選準則上，將一般文字插入聯合欄位。

## <a name="default-report-breakdown"></a>預設報告細目

如果是內部管理無線，您可以在 Managed bucket 中重新建立無線報告。

![CQD 報告細目](../../media/658b8568-0d68-4f5f-83e8-5abc63a85c1d.png)

## <a name="operational-processes"></a>操作程式

先審查及修正受管理的資料流程。 此區域中的品質應該在您的控制項內是100%，因此最容易修正。

### <a name="managed-streams"></a>受管理的資料流程

以下列順序查看及修正受管理的資料流程：

1. 伺服器-伺服器
2. 伺服器-內接線
3. 有線-有線-內

### <a name="unmanaged-streams"></a>非託管資料流程

以下列順序評審及修正非託管的資料流程：

1. 伺服器-Wifi-內
2. 伺服器-在外-有線
3. 伺服器-Wifi-外
4. 有線-直向外
5. 有線外部中繼
6. 其他未受管理
