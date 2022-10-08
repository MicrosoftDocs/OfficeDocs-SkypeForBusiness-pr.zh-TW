---
title: '[通話品質儀表板] (CQD) 中的資料和報告'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: 瞭解 Microsoft 通話品質儀表板 (CQD) 中提供的資料和報告。
ms.openlocfilehash: 7d89c17f299302f39e00e6aebcfd9309ead3eaae
ms.sourcegitcommit: 021cfac01a38282a8cde6e913d74be2d54c39162
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2022
ms.locfileid: "68218512"
---
# <a name="data-and-reports-in-call-quality-dashboard-cqd"></a>[通話品質儀表板] (CQD) 中的資料和報告

Microsoft Call Quality Dashboard (CQD) 使用接近即時 (NRT) 資料摘要。 通話記錄可在通話結束後的 30 分鐘內使用 CQD。 從 NRT 管線撥打電話的記錄，只有在從資料集移除前幾個月才能使用。

## <a name="many-ways-to-access-cqd-data"></a>許多存取 CQD 資料的方式

您可以透過數種不同方式存取 CQD 資料。 挑選最符合您需求的工具：

|&nbsp;|&nbsp;|
|---|---|
|Teams 系統管理中心[ (https://admin.teams.microsoft.com) ](https://admin.teams.microsoft.com)|CQD 資料會包含在 Teams 系統管理中心的 [ **使用者** ] 頁面上，以簡單易讀的格式顯示您最常用的資料。 您無法自訂 [ **使用者**] 底下的 CQD 資料。|
|CQD 入口[網站 (https://cqd.teams.microsoft.com) ](https://cqd.teams.microsoft.com)|透過切入篩選，可滿足大多數需求的強固摘要和詳細報告。 您也可以在 CQD 入口網站中自訂報表。 <br><br>取得兩個 [CQD 報表範本](#import-the-cqd-report-templates) ，協助您分析 CQD 入口網站中的資料。|
|Power BI|使用可 [自訂的 Power BI 範本](CQD-Power-BI-query-templates.md)，使用直接查詢在 Power BI 中檢視您的 CQD 資料。 [下載適用于 CQD 的 Power BI 查詢範本](https://www.microsoft.com/download/details.aspx?id=102291)。<br><br>您也可以 [使用 REST API 透過 Power BI 存取 CQD 資料](/skypeforbusiness/management-tools/call-quality-dashboard/data-api) 。 如果您想要下載 CQD 資料以便離線工作，請使用這個方法。 使用此方法的好處是效能更好，尤其對於在您上線時在 Power BI 中變慢的大型資料集特別有用。|
|Graph API|使用圖形 API自行存取通話品質[資料。](/graph/api/resources/callrecords-api-overview) 這是最複雜的方法，但可讓您在分析通話品質資料時，擁有最大的控制能力和彈性。 例如，如果您需要將它與組織的其他資料聯結，您可以使用圖形 API建立資料模型，並整合通話品質資料。|

## <a name="import-the-cqd-report-templates"></a>匯入 CQD 報表範本

 (所有網路和受管理的網路下載 [兩個精選的 CQD 報告範本](https://aka.ms/qertemplates)) ，協助您快速上手使用 CQD。 [所有網路] 範本雖然已針對建築物資料檔進行優化處理，但可在您收集及上傳建築物資訊至 CQD 時使用，如下一節所述。

**若要匯入範本 (。CQDX) 入 CQD**：

1. 在 CQD 中，從頁面頂端的功能表中選取 [ **詳細報告** ]。

2. 在左面板中，選取 [ **匯入]**。 流覽至第一個 CQDX 範本，然後選取 **[開啟]**。

3. 上傳範本之後，快顯視窗會顯示「報告匯入成功」訊息。

4. 針對第二個 CQD 範本重複步驟 2 和 3。

   > [!NOTE]
   > 每個使用者都必須將 CQD 範本匯入至其 CQD 實例。

## <a name="euii-data"></a>EUII 資料

基於合規性原因，使用者標識資訊 (EUII) 資料 (也稱為個人識別資訊或 PII) 只會保留 28 天。 當 NRT 資料越過 28 天標記時，會清除包含 EUII 的欄位，導致不含 EUII 的 NRT 資料。 包含 EUII 資料的欄位為：

- 完整 IP 位址
- 媒體存取控制 (MAC) 位址
- 基本服務組識別元 (BSSID) 
- SIP) URI (會話初始通訊協定僅 (商務用 Skype) 
- UPN (使用者主體名稱) 
- 電腦端點名稱
- 使用者逐字意見反應
- 物件識別碼 (端點使用者的 Active Directory 物件識別碼) 
- 電話號碼
- 自動語音應答身分識別
- 通話佇列身分識別
- 視訊電話會議 (VTC) 裝置名稱
-  (VTC) 裝置詳細資料的視訊電話會議

### <a name="admin-roles-with-and-without-euii-access"></a>管理員具有或不含 EUII 存取權的角色

這些 [RBAC](/azure/role-based-access-control/overview) 角色 **DO** 具有 EUII 存取權：

- 全域管理員
- Teams 服務管理員
- Teams Communications 管理員
- Teams 通訊支援工程師
- 全域閱讀程式
- 商務用 Skype 管理員

這些 RBAC 角色 **沒有** EUII 存取權：

- 報表閱讀程式
- Teams 通訊支援專家

## <a name="date-controls"></a>日期控制項

CQD 支援下列滾動趨勢類型：

- 5 天
- 7 天
- 30 天
- 60 天
- 90 天

URL Date 參數接受 Day 欄位。 滾動日報表使用 YYYY-MM-DD 格式所指定的日期做為趨勢的最後一天。 URL Date 參數 「00」 表示 「today」。

|Url|滾動日趨勢的結束日期|
|:---|:---|
|<span>\<cqdv3>HTTPs:///spd/#/Dashboard/ \<reportid> /2019-02/</span>|2019 年 2 月當天|
|<span>\<cqdv3>HTTPs:///spd/#/Dashboard/ \<reportid> /2019-02-15/</span>|2019 年 2 月 15 日|
|<span>\<cqdv3>HTTPs:///spd/#/Dashboard/ \<reportid> /00/</span>|當天|

根據預設，當月的最後一天會用來做為 [滾動日] 趨勢的最後一天。

## <a name="data-available-in-cqd-reports"></a>CQD 報告中可用的資料

您只需要管理組織通話品質的預設摘要和詳細的 CQD 報告即可。如有需要，您可以 [建立自訂報表](#create-custom-detailed-reports)。

如果您想要使用 Power BI 來分析您的 CQD 資料，請參閱 [使用 Power BI 來分析 Teams 的 CQD 資料](CQD-Power-BI-query-templates.md)。

|功能|摘要報表|詳細報告|
|:---|:---|:---|
|應用程式共用指稱|否|是|
|客戶建築物資訊支援|是|是|
|用戶端點資訊支援|僅限 cqd.teams.microsoft.com <span><span/>|僅限 cqd.teams.microsoft.com <span><span/>|
|向下切入分析支援|否|是|
|媒體可靠性指派|否|是|
|開箱即用的報告|是|是|
|概觀報表|是|是|
|每個使用者報告集|否|是|
|報表集自訂 (新增、刪除、修改報告) |否|是|
|以視訊為基礎的螢幕畫面分享指派|否|是|
|視訊指派|否|是|
|可用的資料量|過去 12 個月|過去 12 個月|
|Microsoft Teams 資料|是|是|

### <a name="select-product-data-to-see-in-reports"></a>選取要在報告中查看的產品資料

在 [摘要與Location-Enhanced報表] 中，您可以使用 **[產品篩選**] 下拉式清單顯示所有產品資料，僅顯示 Microsoft Teams 資料，或僅商務用 Skype線上資料。

> [!div class="mx-imgBorder"]
> ![螢幕擷取畫面：顯示 [產品篩選] 控制選項。](media/206ad818-0f72-4c8e-b25e-3cc8fcfbef05.png)

在 [詳細報告] 中，您可以使用 **Is Teams** 維度來篩選資料至 Microsoft Teams 或商務用 Skype線上資料。

## <a name="summary-reports"></a>摘要報表

以下是您第一次登入 CQD 時會在 CQD 儀表板上看到的報表。 它們可讓您快速查看品質趨勢與每日、每月及表格報表，以協助識別品質不佳的子網。

|選項 卡|描述|
|---|---|
|整體通話品質|其他 3 個索引標籤的匯總。|
|伺服器 — 用戶端|伺服器與用戶端端點之間的串流詳細資料。|
|用戶端 — 用戶端|兩個用戶端端點之間的串流詳細資料。|
|語音品質 SLA|商務用 Skype語音品質[SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)中包含之通話的相關資訊。|

### <a name="overall-call-quality-tab"></a>[整體通話品質] 索引標籤

使用此索引標籤上的資料，根據串流計數和不佳的百分比來評估通話品質狀態和趨勢。 右上角的圖例顯示代表這些計量的色彩和視覺元素。

> [!div class="mx-imgBorder"]
> ![螢幕擷取畫面：顯示 [通話品質] 索引標籤。](media/c8d183b1-6592-49b0-a81d-35cc0568d5f0.png)

串流分為三個群組：[良好]、[不佳] 和 [未分類]。 此外，還有計算 [  *不佳%]*  值，讓您將分類為 *[差*  ] 的串流與總分類串流計數的比例計算出來。 由於 *不佳 % = 不佳的串流/ (不佳的串流+ 良好的串流) \* 100*， *因此不受影響的百分* 比不受多個 *未分類*  串流的影響。 若要查看將串流分類為不佳或良好，請參閱 [通話品質儀表板中的 [串流分類]](stream-classification-in-call-quality-dashboard.md)。

使用左側的縮放比例來測量串流計數值。

> [!div class="mx-imgBorder"]
> ![螢幕擷取畫面：顯示串流計數值。](media/850bd25d-d9b2-4df4-8ca6-526a528897c2.png)

使用右側的縮放比例來測量 [不佳百分比] 值。

> [!div class="mx-imgBorder"]
> ![螢幕擷取畫面：顯示不佳的 % 值。](media/29795f71-ca96-4763-a76c-b4bb7c0e5828.png)

您也可以將滑鼠停留在橫條上，以取得實際的數值。

> [!NOTE]
> 下列範例來自極小的範例資料集，而實際部署的值並不實際。

> [!div class="mx-imgBorder"]
> ![螢幕擷取畫面：顯示用來存取資料的滑鼠。](media/8724b016-1a50-4d19-b48a-3b1aae4eb895.png)

整體串流磁片區可協助判斷計算的不佳百分比的相關性。 整體串流的流量越小，所報告的不佳百分比值就越不可靠。

### <a name="server-client-tab-and-client-client-tabs"></a>Server-Client索引標籤和Client-Client索引標籤

這兩個索引標籤提供端點對端點案例中所發生之串流的詳細資料。 [Server-Client] 索引標籤有四個可折迭的區段，代表媒體串流在其中的四個案例。

- 內部有線
- 外部有線
- 內部 WiFi
- 外部 WiFi

同樣地，[Client-Client] 索引標籤有五個可折迭的區段：

- 內部有線 - 內部有線
- 內部有線 - 外部有線
- 外部有線 - 外部有線
- 內部有線 - 內部 WiFi
- 內部有線 - 外部 WiFi

#### <a name="inside-versus-outside"></a>內部與外部

如果存在，CQD 會使用建築物資訊將串流  *分類為內部*  或 *外部*  。 每個串流的端點都與子網位址相關聯。 如果子網在上傳的建築物資訊中標示為 InsideCorp 的子網清單中，則 *會視為內部*。 如果尚未上傳建築物資訊，則內部測試一律將串流分類為 *[外部]*。

Server-Client案例的內部測試只會考慮用戶端端點。 因為從使用者的觀點來看，伺服器一律不在外部，因此這不會計入測試中。

#### <a name="wired-versus-wifi"></a>有線與 WiFi

如名稱所示，分類準則是根據用戶端連線的類型。 伺服器一律有線，不會包含在計算中。 在指定的串流中，如果兩個端點中的其中一個已連線到 WiFi 網路，則 CQD 會將其分類為 WiFi。

> [!NOTE]
> 假設有串流，如果兩個端點中的其中一個已連線到 WiFi 網路，則在 CQD 中會將其分類為 WiFi。

## <a name="tenant-data-information"></a>租使用者資料資訊

CQD 摘要報告儀表板包含租 **使用者資料上傳** 頁面，可從右上角的設定功能表中選取 [ **租使用者資料上傳** ] 來存取。 此頁面供系統管理員上傳自己的資訊，例如：

- IP 位址和地理位置資訊的地圖。
- 每個無線 AP 及其 MAC 位址的地圖。
- 端點對應到端點的 [製作/模型/類型] 等。

我們建議您上傳租使用者、建築物和位置資料，讓 CQD 可以將這項資訊包含在您的報告中。 如果您尚未上傳此資料，請閱讀 [上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)。

## <a name="detailed-reports"></a>詳細報告

|名稱|描述|
|---|---|
|Location-Enhanced報告|根據位置資訊顯示品質趨勢。 只有在您 [已上傳租使用者資料](CQD-upload-tenant-building-data.md)時，才會顯示此報告。|
|可靠性報告|包含音訊、視訊、視訊螢幕共用 (VBSS) ，以及應用程式共用報告。|
|體驗品質報告|所有用戶端和裝置的音訊品質和可靠性，包括會議室。 這些報告是可下載 [CQD 範本](https://aka.ms/QERtemplates)的「精簡」版本，著重于分析音訊品質和可靠性的重要領域。|
|品質向下切入報表|向下切入：依地區、位置、子網、小時和使用者的日期。|
|向下切入失敗報告|向下切入：依地區、位置、子網、小時和使用者的日期。|
|為我的通話報告評分|依地區、位置或使用者分析使用者的通話分級。 包含逐字記錄的意見反應。|
|技術支援中心報告|技術支援中心報告查看個別使用者、使用者群組或每個人的通話和會議資料。 這些報告結合建築物和 EUII 資料，可根據網路位置、會議詳細資料、裝置或韌體，協助找出可能的系統問題。|
|用戶端版本報告|用戶端版本摘要：檢視會話和使用者會計算每個用戶端應用程式版本的計數<br><br>使用者的用戶端版本：檢視每個用戶端應用程式版本的使用者名稱 <br><br>[產品] 和 [用戶端類型] 預先建立的篩選可協助將版本焦點放在特定的用戶端。|
|端點報表|顯示電腦端點 (電腦製造商和型號) 的通話品質。 如果您已上傳，這些報告會包含建築物資料。|

## <a name="create-custom-detailed-reports"></a>建立自訂詳細報告

如果預設 CQD 報表不符合您的需求，請使用這些指示建立自訂報表。 或者 (自 2020 年 1 月起) [改用 Power BI for CQD 報告 ](cqd-power-bi-query-templates.md)。

從顯示在登入 [**摘要報告**] 畫面 \) 的螢幕 \( 頂端報表下拉式清單中，選取 [**詳細報告**]，然後選取 [**新增]**。 按一下報告中的 **[編輯**] 以查看查詢編輯器。 每個報表都由查詢在 Cube 中備份。 報表是其查詢所傳回資料的視覺效果。 查詢編輯器可協助您編輯這些查詢和報表的顯示選項。

> [!IMPORTANT]
> 網路範圍可用來表示數個子網的超級網路 (組合，以及單一路由前置詞) 。 所有新的建築物上傳都會檢查是否有任何重迭的範圍。 如果您先前已上傳建築物檔案，您應該下載目前的檔案並重新上傳，以找出任何重迭專案並修正問題，再重新上傳。 先前上傳的檔案中的任何重迭可能會導致報表中子網對應到建築物的錯誤。 某些 VPN 實作不會正確回報子網資訊。 建議您在將 VPN 子網新增至建築物檔案時，不要為子網新增一個專案，VPN 子網中的每一個位址會以個別的 32 位網路新增個別專案。 每一列可以有相同的建築物中繼資料。 例如，172.16.18.0/24 應有 256 列，且每個位址在 172.16.18.0/32 和 172.16.18.255/32 之間各包含一列。
>
> VPN 欄為選用，預設為 0。  如果 VPN 欄的值設為 1，該列所代表的子網將會完全展開，以符合子網中的所有 IP 位址。  請謹慎使用此功能，而且僅適用于 VPN 子網，因為完全展開這些子網會對涉及建置資料的查詢時間產生負面影響。

指向報表中的橫條圖和趨勢線以顯示詳細的值。 焦點報表會顯示動作功能表： **[編輯**]、[ **複製**]、[ **刪除]**、[ **下載**] 和 [ **匯出報表樹]**。

## <a name="query-filters"></a>查詢篩選

查詢篩選是使用 CQD 中的查詢編輯器實作。 這些篩選可用來減少 CQD 傳回的記錄數目，因此可將報表的整體大小和查詢時間降到最低。 這對於篩選未受管理的網路特別有用。 下表中列出的篩選會使用 RegEx)  (正則運算式。

|Filter|描述|CQD 查詢篩選範例|
|---|---|---|
|無空白值|某些篩選器沒有篩選空白值的選項。 若要手動篩選空白值，請使用空白運算式，並根據您的需求將篩選設定為 [等於] 或 [不等於]。|第二棟大樓名稱 \<\> \^ \\\*\$|
|排除常見的子網|如果沒有有效的建築物檔案來將管理的網路與未受管理的網路分開，家用網路就會包含在報告中。 這些家用子網不在 IT 的控制範圍之外，而且可以快速地從報表中排除。 如本指南所定義，一般子網為 10.0.0.0、192.168.1.0 和 192.168.0.0。|第二個子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0|
|僅限內部檢視|用來篩選) 內受管理 (或未受管理 () 外的報表。 受管理的 CQD 範本已在這些篩選器中預先設定。|Second Inside Corp = Inside|

## <a name="report-filters"></a>報表篩選

使用 CQD 報表篩選來縮小調查的焦點。 您可以在報表的查詢編輯器或直接在報表中新增篩選至轉場的報表，藉此使用報表篩選。 下列報表篩選會用於整個 [CQD 範本](https://aka.ms/QERtemplates)。

|Filter|描述|CQD 報表篩選範例|
|---|---|---|
|月|從第一年開始，然後從月份開始。|2017-10|
|字母|篩選任何字母字元。|[a-z]|
|數位|篩選任何數值字元。|[0-9]|
|百分比|篩選百分比。| ([3-9] \\ .) \| ([3-9]) \| ([1-9][0-9]) |

### <a name="drill-down-filters"></a>向下切入篩選

CQD 報告具有數種向下切入篩選，這些篩選是可縮小通話品質調查焦點的強大工具。 如果您選取向下切入欄位，報表會自動開啟適當的索引標籤，並篩選選取的值。 如果該索引標籤有自己的向下切入欄位，而且已選取其中一個欄位，則會套用這兩組篩選，逐漸縮小結果資料集的範圍。

![說明向下切入報表流程的圖表。](media/qerguide-image-drillthrureportflow.png)

#### <a name="adding-and-editing-drill-down-fields"></a>新增及編輯向下切入欄位

編輯報表時，您可以選擇使用報表指定自己的向下切入欄位查詢編輯器。

首先，按一下 **...** 以取得您要編輯的報告，然後選取 [ **編輯]**。

![編輯向下切入欄位的螢幕擷取畫面。](media/qerguide-image-addeditdrilldownfields.png)

從查詢編輯器左側的清單中選取維度。 然後按一下 [ **流覽至** ] 標籤下方的下拉式清單，然後選取您要讓 [維度] 切入的索引標籤和展開器群組。 注意：目前，向下切入功能只能透過流覽至不同的索引標籤來運作。 稍後將會新增深入瞭解特定展開器的支援。 最後，按一下 [**關閉**] 將變更儲存到 [維度]，**然後按一下**[儲存] 以儲存並關閉查詢編輯器。

![在查詢編輯器中選取維度的螢幕擷取畫面。](media/qerguide-image-selectquerydimension.png)

### <a name="multi-select-filters"></a>多重選取篩選

除了向下切入功能，CQD 也支援指定含有多個值的篩選 (OR 篩選) 。

若要選取多個篩選值，請先在報表中新增篩選。 在 **[篩選] 卷** 標旁邊按一下 **+** ，輸入您要使用的維度名稱，然後按一下 [**新增]**。

![新增多重選取篩選的螢幕擷取畫面。](media/qerguide-image-addmultiselectfilter.png)

然後，按一下 [ **搜尋** (新篩選) 旁的放大鏡圖示。 您會看到文字欄位和一些選項，包括 **[全選** ] 和 [ **反轉]**。 輸入值，然後按一下該欄位旁的 [ **搜尋** ] 進行搜尋。 或者，將文字欄位保留空白，然後按一下 [ **搜尋** ] 檢視前 100 個選項。

```powershell
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

範例：

![新增查詢篩選的螢幕擷取畫面。](media/qerguide-image-addfilter.png)

### <a name="dashboard-level-filters"></a>儀表板層級篩選

某些 CQD 報表會將儀表板層級篩選新增至這些報表，方便您依常用參數進行篩選。 這些篩選會顯示在一般報表索引標籤之外，並直接顯示在 [產品篩選] 下方，並套用至儀表板中的所有篩選。

![儀表板篩選器的螢幕擷取畫面。](media/qerguide-image-dashboardfilters.png)

```powershell
/filter/[AllStreams].[Is Teams]|[TRUE | FALSE]
```

### <a name="url-filters"></a>URL 篩選

CQD 支援新增篩選至 URL。 這可讓您輕鬆共用或將 CQD 查詢加入書簽。 您可以定義 URL 中的參數，例如趨勢月、租使用者識別碼或語言。 您也可以新增產品或儀表板層級篩選至 URL。
當您修復受管理的建築物或網路，同盟端點可能會影響您的報表時，從 CQD 報表排除同盟資料會很有用。

若要新增篩選，請將下列內容附加到 URL 的結尾：

```console
/filter/[AllStreams].[Second Tenant Id]\|[YOUR TENANT ID HERE]
```

範例：

`https://cqd.teams.microsoft.com/cqd/#/1234567/2018-08/filter/[AllStreams].[Second Tenant Id]|[TENANTID]`

若要將儀表板層級篩選新增至 URL，該篩選必須在 CQD 中作為產品或儀表板層級篩選存在。 將這些篩選新增到趨勢月份之後和 URL 參數之前的 URL：

`filter/DATA_MODEL_NAME|VALUE`

例如，若要套用 Microsoft Teams 的 [產品] 篩選值，您可以新增下列專案：

`filter/[AllStreams].[Is%20Teams]|[True]`

您的整個 URL 看起來像這樣：

`https://cqd.teams.microsoft.com/spd/#/Dashboard/2624085/2018-9/filter/[AllStreams].[Is%20Teams]|[True]`

若要套用含有多重選取值的 URL 篩選器，請使用管道 ( |) 字元。 例如：

`filter/[AllStreams].[Media%20Type]|[Video]|[Audio]|[VBSS]`

如果您指定不正確名稱或值，則不會套用 URL 篩選。

您可以使用 URL 篩選來篩選每個報表的特定維度。 最常見的 URL 篩選是用來篩選報表以排除同盟參與者遙測，或只將焦點放在 Teams 或 商務用 Skype Online。 當您修復受管理的建築物或網路，同盟端點可能會影響您的報表時，從 CQD 報表排除同盟資料會很有用。

|Filter|描述|CQD 查詢篩選範例|
|---|---|---|
|無空白值|某些篩選器沒有篩選空白值的選項。 若要手動篩選空白值，請使用空白運算式，並根據您的需求將篩選設定為 [等於] 或 [不等於]。|第二棟大樓名稱 \<\> \^ \\\*\$|
|排除常見的子網|如果沒有有效的建築物檔案來將管理的網路與未受管理的網路分開，家用網路就會包含在報告中。 這些家用子網不在 IT 的控制範圍之外，而且可以快速地從報表中排除。 如本文所定義，一般子網為 10.0.0.0、192.168.1.0 和 192.168.0.0。|第二個子網 \<\> 10.0.0.0 \| 192.168.0.0 \| 192.168.1.0|
|僅限內部檢視|用來篩選) 內受管理 (或未受管理 () 外的報表。 受管理的 CQD 範本已在這些篩選器中預先設定。|Second Inside Corp = Inside|

#### <a name="how-to-find-your-tenant-id"></a>如何尋找您的租使用者識別碼

CQD 中的租使用者識別碼會對應到 Azure 中的目錄識別碼。 如果您不知道目錄識別碼，可以在Azure 入口網站中找到：

1. 登入 Microsoft Azure 入口網站：<https://portal.azure.com>

2. 選 **取 Azure Active Directory**。

3. 在 [ **管理] 底** 下，選取 [ **內容]**。 您的租使用者識別碼位於 [ **目錄識別碼** ] 方塊中。

您也可以使用 PowerShell 找到您的租使用者識別碼：

```powershell
Login-AzureRmAccount
```

## <a name="comparing-teams-and-skype-for-business-cqd-data"></a>比較 Teams 和 商務用 Skype CQD 資料

檢閱資料時，您可能會看到 Teams 和 商務用 Skype 之間的資料差異。 一些原因：

- 確保效能與可靠性的機制差異：
  - Teams 有自動重新連線和快速漫遊功能。 商務用 Skype不行。
  - Teams 具有動態頻寬管理。 商務用 Skype不行。
- Teams 與 商務用 Skype 之間[IP 位址範圍](Office-365-URLs-IP-address-ranges.md)的差異。 Teams IP 範圍較新，可能會導致防火牆發生連線問題。

## <a name="related-topics"></a>相關主題

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

[什麼是 CQD？](CQD-what-is-call-quality-dashboard.md)

[設定呼叫品質儀表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md)

[上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[使用 CQD 管理通話和會議品質](quality-of-experience-review-guide.md)

[CQD 中提供的維度和量值](dimensions-and-measures-available-in-call-quality-dashboard.md)

[CQD 中的串流分類](stream-classification-in-call-quality-dashboard.md)

[使用 Power BI 分析 CQD 資料](CQD-Power-BI-query-templates.md)
