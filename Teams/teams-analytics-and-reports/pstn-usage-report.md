---
title: Microsoft Teams PSTN 使用方式報告
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: v-rifer
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何使用 Microsoft Teams 系統管理中心的 Teams PSTN 使用方式報告，以取得貴組織通話和音訊會議使用方式的概觀。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-voice
ms.openlocfilehash: 1539f679225334f71855300a54c4fba950ddd8f8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267628"
---
# <a name="microsoft-teams-pstn-usage-report"></a>Microsoft Teams PSTN 使用方式報告

Microsoft Teams 系統管理中心的 Teams PSTN (公用交換電話網路) 使用方式報告可讓您概略瞭解貴組織中的通話和音訊會議活動。 如果您使用 Microsoft 做為電話語音電信業者，您可以檢視通話方案的詳細通話活動，如果您使用自己的電話語音電信業者，則可檢視直接路由。

[ **通話方案]** 索引標籤會顯示資訊，包括使用者用於輸入和撥出 PSTN 通話的分鐘數，以及這些通話的成本。 [ **直接路由] 索引** 標籤會顯示資訊，包括 SIP 位址和通話開始和結束時間。 使用此報告中的資訊，深入瞭解貴組織中的 PSTN 使用狀況，並協助您調查、規劃及做出業務決策。

> [!NOTE]
> 如果您有 Telstra 或 Softbank 通話方案，就不會在 PSTN 使用方式報告中看到任何通話詳細記錄。 請連絡 Telstra 或 Softbank，瞭解您的報告需求。 

## <a name="view-the-pstn-usage-report"></a>檢視 PSTN 使用方式報告

1. 在 Microsoft Teams 系統管理中心的左側導覽中，按一下 **[分析&報告**  >  **使用方式報告。** 在 [ **檢視報表]** 索引標籤的 [ **報表**] 底下，選取 **[PSTN 使用方式報告]**。
2. 在 **[日期範圍**] 底下，選取預先定義的 7 或 28 天範圍，或設定自訂範圍，然後選取 [ **執行報表]**。

## <a name="interpret-the-report"></a>解讀報表

### <a name="calling-plans"></a>通話方案

   ![系統管理中心中通話方案 PSTN 使用方式報告的螢幕擷取畫面](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png)![Microsoft Teams 系統管理中心內含編號圖說文字的 PSTN 使用方式報告螢幕擷取畫面](../media/teams-reports-pstn-usage-calling-plans-with-callouts.png#lightbox)

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視過去 7 天、28 天的趨勢或您所設定的自訂日期範圍。 |
|**2**   |每個報告都有產生報告的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**3**   |X 軸是特定報表的選取日期範圍。 Y 軸是所選時段內的通話總數。 <br>將游標停留在指定日期的點上，以查看該日期的總通話數。  |
|**4**   |此表格提供每個通話的 PSTN 使用量明細。 <ul><li>**時間戳記 (UTC)** 是通話開始的時間。</li><li>**顯示名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft Teams 系統管理中心的使用者設定頁面。</li><li>**使用者名稱** 是使用者的登入名稱。</li><li>**電話號碼** 是接聽撥入電話的號碼，或撥出的號碼。</li><li>**通話類型** 是指電話是 PSTN 撥出或撥入式通話，以及電話類型，例如使用者撥打的電話或音訊會議。 您可能會看到的通話類型包括：<br><br>**Teams 使用者通話類型**<ul><li>**user_in** - 使用者收到輸入 PSTN 通話</li><li>**user_out** - 使用者撥打了輸出 PSTN 通話</li><li>**user_out_conf** - 使用者已將兩個或多個 PSTN 參與者新增至通話，例如三向電話會議</li><li>**user_out_transfer** - 使用者將電話轉接到 PSTN 號碼</li><li>**user_out_forwarding** - 使用者將電話轉接至 PSTN 號碼</li><li>**conf_in** - 音訊會議橋接器的輸入通話</li><li>**conf_out** - 從音訊會議橋接器撥出電話，通常會將 PSTN 號碼新增至會議</li><li>**unassigned_in** - 透過通話方案撥打未指派號碼的輸入 PSTN 通話</li></ul><br>**Teams Bot 通話類型**<ul><li>**ucap_in** - Teams 機器人的輸入 PSTN 通話，例如自動語音應答或通話佇列</li><li>**ucap_out** - 來自 Teams Bot 的輸出 PSTN 通話，例如自動語音應答或通話佇列</li></ul><br><li>**[撥號至** ] 是撥號的號碼。</li><li>**對國家或地區** 是指撥號到的國家或地區。</li><li>**來電** 者是撥打電話的號碼。</li><li>**從國家或地區** 是撥打電話所在的國家或地區。</li><li>**費用** 是指向您的帳戶收取的通話金額或通話費用。 </li><li>**貨幣** 是用來計算通話成本的貨幣類型。 </li><li>**持續時間** 是連接通話的時間。</li><li>**國內/國際會** 根據使用者的位置，告知電話是國家或地區內的國內 () 或國家或地區之外的國際 () 。</li><li>**[通話識別碼** ] 是通話的來電識別碼。 這是撥打Microsoft 支援服務時可以使用的通話識別碼。</li><li>**號碼類型** 是使用者的電話號碼類型，例如免付費電話號碼的服務。 </li><li>**國家或地區** 是使用位置。 </li> <li>**會議 ID** 是音訊會議的會議 ID。 </li><li>**功能** 是通話所用的授權。 您可能會看到的授權類型包括：<ul><li>**MCOEV 或 MCOEV_VIRTUALUSER 或 MCOEV_VIRTUALUSER_GOV** - 語音應用程式，例如自動語音應答或通話佇列</li><li>**FREECALL** - 萬一發生技術問題而導致無法為通話定價，則會免費提供通話，並以此功能顯示</li><li>**MCOPSTN1** - 國內通話方案 (3000 分鐘 /1200 分鐘歐盟方案) </li><li>**MCOPSTN2** - 國際通話方案</li><li>**MCOPSTN5** - 國內通話方案 (120 分鐘通話方案) </li><li>**MCOPSTN6** - 國內通話方案 (240 分鐘通話方案) </li><li>**MCOPSTN8** - 每個使用者 120 分鐘國內通話方案 (不會像其他通話方案一樣跨使用者集合) </li><li>**MCOPSTN9** - 國際通話方案</li><li>**MCOPSTNCAP** - 通用區域電話</li><li>**MCOPSTNPP** - 通訊點數</li><li>**MCOMEETADD** - 音訊會議</li><li>**MCOMEETADD_DIALOUT_US** - 美國和加拿大的音訊會議撥出方案</li><li>**MCOMEETADD_CN_GLOBAL** - 非中國使用者的音訊會議</li><li>**MCOMEETADD_TATA** - Tata Communications Connections</li><li>**MCOMEETACPEA** - 音訊會議每分鐘付費 </li><li>**MCOMEETACPEA_GOV** - 政府專用的音訊會議每分鐘付費</li></ul></li></ul> 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**5**   |選取 **[編輯欄]** 以新增或移除表格中的欄。 |
|**6**   |選取 **[篩選** ]，依使用者名稱或通話類型篩選報表。 |
|**7**   |選取 **[全螢幕** ] 以全螢幕模式檢視報表。 |
|**8**   |您可以將報表匯出為 CSV 檔案以進行離線分析。 按一下 **[匯出至 Excel**]，然後在 [ **下載] 索引卷** 標上，按一下 [ **下載** ] 以在報表準備就緒時下載報表。|

### <a name="direct-routing"></a>直接路由

   ![系統管理中心中直接路由 PSTN 使用方式報告的螢幕擷取畫面](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png)![Microsoft Teams 系統管理中心內含編號圖說文字的直接路由 PSTN 使用方式報告螢幕擷取畫面](../media/teams-reports-pstn-usage-direct-routing-with-callouts.png#lightbox)

|標注 |描述  |
|--------|-------------|
|**1**   |您可以檢視過去 7 天或 28 天的趨勢報表。 |
|**2**   |每個報告都有產生報告的日期。 報告通常會反映啟用時間的 24 到 48 小時延遲。 |
|**3**   |X 軸是特定報表的選取日期範圍。 Y 軸是所選時段內的通話總數。<br>將游標停留在指定日期的點上，以查看該日期的總通話數。  |
|**4**   |此表格提供每個通話的 PSTN 使用量明細。 <ul><li>**時間戳記 (UTC)** 是通話開始的時間。</li><li>**顯示名稱** 是使用者的顯示名稱。 您可以按一下顯示名稱，移至 Microsoft Teams 系統管理中心的使用者設定頁面。 名稱也可以是 Bot 的名稱，例如通話佇列或雲端自動語音應答。 </li><li>**SIP 位址** 是收到或撥打電話之使用者或 Bot 的 SIP 位址。</li><li>**來電者號碼** 是撥打電話的使用者或 Bot 號碼。 </li><li>**來電者號碼** 是接聽來電的使用者或 Bot 號碼。 在給 Teams 使用者的撥入通話中，該使用者會是 Teams 使用者，在 Teams 使用者的撥出通話中，該使用者會是 PSTN 使用者。 </li><li>**通話類型** 是指電話是 PSTN 撥出或撥入式通話，以及電話類型，例如使用者撥打的電話或音訊會議。 您可能會看到的通話類型包括：<br><br>**Teams 使用者通話類型**<ul><li>**dr_in** - 使用者收到輸入 PSTN 通話</li><li>**dr_out** - 使用者撥打了輸出 PSTN 通話</li><li>**dr_out_user_conf** - 使用者已在通話中新增 PSTN 參與者</li><li>**dr_out_user_forwarding** - 使用者將電話轉接至 PSTN 號碼</li><li>**dr_out_user_transfer** - 使用者將電話轉接到 PSTN 號碼</li><li>**dr_emergency_out** - 使用者撥打了緊急電話</li><li>**dr_unassigned_in** - 透過直接路由到未指派號碼的輸入 PSTN 通話</li></ul><br>**Teams Bot 通話類型**<ul><li>**dr_in_bot** - Teams Bot 的輸入 PSTN 通話，例如自動語音應答或通話佇列</li><li>**dr_out_bot** - 來自 Teams Bot 的輸出 PSTN 通話，例如自動語音應答或通話佇列</li></ul><br><li>**來電** 者是指接聽來電的使用者號碼。</li><li>**開始時間 (UTC)** 是 SIP Proxy 在連出電話 (Teams/Bot 傳送 SIP 訊息 (SIP 訊息「200 確定」) 傳送至 PSTN 使用者) ，或是 SIP Proxy 將邀請傳送到 Teams 內的下一個躍點之後，輸入通話 (PSTN 使用者傳送到 Teams/Bot) 的時間。 </li><li>**邀請時間 (UTC)** 是指從 Teams 使用者或 Bot 來電傳送初始邀請給 SBC，或是透過 SBC 直接路由 SIP 的 SIP Proxy 元件在 Teams 或 Bot 通話中接聽來電時傳送初始邀請的時間。</li><li>**UTC)  (失敗時間** 是指通話失敗的時間。 僅適用于未接來電。 最終 SIP 代碼、最終 Microsoft 子代碼和最終 SIP 片語提供通話失敗的原因，並可協助進行疑難排解。 </li><li>**結束時間 (UTC)** 是通話結束 (成功通話的時間，) 。</li><li>**持續時間** 是指連接通話的時間，從邀請到通話結束或失敗。 針對來電轉接，持續時間包括 [通話佇列] 中的響鈴。</li><li>**號碼類型** 是使用者的電話號碼類型，例如免付費電話號碼的服務。 </li><li>**媒體略過** 表示是否啟用媒體略過的主幹。 </li> <li>**SBC FQDN 是 SBC**) 會話框線控制器 (FQDN (FQDN) 的完整功能變數名稱。 </li><li>**媒體用 Azure 區域** 是資料中心，在非略過的通話中用來做為媒體路徑。 </li><li>**用於訊號的 Azure 區域** 是用於略過和非略過通話訊號的資料中心。 </li><li>**事件種類** 是通話的事件種類。 您會看到成功通話成功和嘗試撥打失敗的通話。 </li><li>**最後的 SIP 代碼** 是通話結束的代碼。</li><li>**最終 Microsoft 子代碼** 是一個程式碼，代表發生特定動作。</li><li>**最後的 SIP 片語** 是 SIP 程式碼和 Microsoft 子代碼的描述。</li><li>**相互關聯標識** 符是通話的唯一識別碼，您可以在撥打Microsoft 支援服務時使用它。</li><li>**共用相互關聯識別碼** 只顯示在可下載的 CSV 檔案中，並不存在於入口網站中。 共用相互關聯識別碼至少存在於兩個相關的通話中。 請參閱下方的詳細描述。</li></ul> 若要在資料表中查看您要的資訊，請務必將欄新增至資料表。|
|**5**   |選取 **[編輯欄]** 以新增或移除表格中的欄。 |
|**6**   |選取 **[全螢幕** ] 以全螢幕模式檢視報表。 |
|**7**   |選 **取 [匯出至 Excel** ] 以以逗號分隔檔案 (CSV) 下載資料，以進行離線分析或使用它做為帳單系統的輸入。 |

#### <a name="callercallee-fields-considerations"></a>來電者/呼叫者欄位考慮

視通話方向而定，來電者或來電者名稱可能包含非 E164 號碼。

這些欄位可能來自客戶 SBC (的) 。 SBC 可以傳送三種格式給直接路由：E.164 數位、非 E.164 數位和字串。

- 從擁有 E.164 號碼的使用者到也有 E.164 號碼的使用者，撥打 E.164 電話號碼。 
- 從非 E.164 號碼撥號。 協力廠商 PBX 與直接路由相互連線的使用者撥打電話給 Teams 使用者。 在此情況下，來電者號碼可能是任何非 E.164 的號碼，例如 +1001。 
- 垃圾郵件來電，且不會顯示號碼，僅顯示名稱，例如「內部營收服務」。 此字串會顯示在報表中。

#### <a name="phone-number-obfuscation"></a>電話號碼混淆
每個國家/地區的隱私權需求包括不由客戶擁有的外部 (混淆) 電話號碼。 電話號碼的三位數或四位數會以星號 (+123 456789}) 取代。 

針對來電，來電者號碼會混淆，撥出電話的來電號碼會混淆。 這適用于租使用者管理員中心的 PSTN 和直接路由報告、資料匯出，以及透過 Microsoft Graph 取得的通話記錄。

混淆是根據組織的位置 (國家/地區) 。 完整電話號碼會顯示在下表未列出的國家/地區：

| 國家 | 混淆位數的數目 |
| :-: | :- |
|BE – 比利時 | 3 |
|CH – 瑞士 | 4 |
|DE - 德國 | 3 |
|DK – 丹麥 | 3 |
|ES – 西班牙 | 3 |
|FI – 芬蘭 | 3 |
|FR – 法國 | 4 |
|IT – 義大利 | 3 |
|NL - 荷蘭 | 3 |
|NO - 挪威 | 3 |
|SE - 瑞典 | 3 |

#### <a name="about-shared-correlation-id"></a>關於共用相互關聯識別碼

[共用相互關聯識別碼] 只會存在於您下載的匯出 Excel 檔案中，並指出兩個或多個通話相關聯。 下列說明不同的案例，以及共用相互關聯識別碼出現時。

1.    在 Teams 用戶端上稱為 Teams User 1 的 PSTN 端點上的 PSTN 使用者 1、通話類型Dr_In、相互關聯識別碼 57f28917-42k5-4c0c-9433-79734873f2ac，無共用相互關聯識別碼。
2.    Teams 用戶端上的 Teams 使用者 1 在 PSTN 端點上稱為 PSTN 使用者 1，通話類型Dr_Out 2c12b8ca-62eb-4c48-b68d-e451f518ff4，無共用相互關聯識別碼。
3.    在 Teams 用戶端上稱為 Teams 使用者 2 之 PSTN 端點上的 PSTN 使用者 1， 通話類型Dr_In f45e9a25-9f94-46e7-a457-84f5940efde9，共用相互關聯識別碼 f45e9a25-9f94-46e7-a457-84f5940efde9。
4.    現有通話 3 具有相互關聯識別碼 「f45e9a25-9f94-46e7-a457-84f5940efde9」。 使用 Teams User 2 進行通話中的 PSTN 使用者 1。 在通話給 Teams 或 PSTN 使用者) ，Teams 使用者 2 (視障或弱視轉移使用者， 通話類型 Dr_Out_User_Transfer 45a1da7c-9e97-481a-8a05-3fe19a9a77e0，共用相互關聯識別碼 f45e9a25-9f94-46e7-a457-84f5940efde9。

## <a name="exporting-the-reports"></a>匯出報表
按一下 **[匯出至 Excel**]，然後在 [ **下載] 索引卷** 標上，按一下 [ **下載** ] 以在報表準備就緒時下載報表。 根據資料量而定，匯出程式可能需要幾秒鐘到幾分鐘的時間才能完成。

這會匯出所有使用者的資料，並讓您進行簡單的排序和篩選，以進一步分析。 匯出的檔案包含線上報告中無法使用的其他欄位。 這些可用來進行疑難排解和自動化工作流程。

 您會收到名為「**通話.匯出」的 zip 檔案。 `[identifier]`.zip**「，識別碼是可用於疑難排解之匯出的唯一識別碼。

如果您同時有通話方案和直接路由，匯出的檔案可能包含這兩個產品的資料。 PSTN 使用方式報告檔案會有檔案名「**PSTN.calls」。 `[UTC date]`.csv**「 和 Direct Routing 」**DirectRouting.calls。 `[UTC date]`.csv**「。

 除了 PSTN 和直接路由檔案之外，封存還包含了具有所選匯出時間範圍和功能的檔案 「**parameters.json**」。

匯出的檔案採用逗號分隔值 (CSV) 格式，符合 [RFC 4180](https://tools.ietf.org/html/rfc4180) 標準。 檔案可以在 Excel 或任何其他符合標準的編輯器中開啟，而不需要任何轉換。

CSV 的第一列包含欄名。 所有日期都是 UTC 和 [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) 格式。

### <a name="exported-pstn-usage-report"></a>匯出 PSTN 使用方式報告

 除非國家/地區特定法規禁止將資料保留 12 個月，否則您最多可以從目前日期匯出資料一年。

> [!div class="has-no-wrap"]  
> | # | 名稱 | [資料類型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 描述 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | UsageId | `uniqueidentifier` | 唯一通話識別碼 |
> | 1 | 通話識別碼 | `nvarchar(64)` | 通話識別碼。 不保證是唯一 |
> | 2 | 會議 ID | `nvarchar(64)` | 音訊會議的識別碼 |
> | 3 | 使用者位置 | `nvarchar(2)` | 使用者的國家/地區代碼 [，ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 4 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中撥打使用者的識別碼。<br/> 此資訊和其他使用者資訊對於 bot 通話類型 (ucap_in為 Null/空白，ucap_out)  |
> | 5 | Upn | `nvarchar(128)` | UserPrincipalName (Azure Active Directory 中的登入名稱) 。<br/>這通常與使用者的 SIP 位址相同，而且可以與使用者的電子郵件地址相同 |
> | 6 | 使用者顯示名稱 | `nvarchar(128)` | 顯示使用者名稱 |
> | 7 | 來電顯示 | `nvarchar(128)` | 接聽撥入電話電話或撥出電話號碼的號碼。 [E.164](https://en.wikipedia.org/wiki/E.164) 格式 |
> | 8 | 通話類型 | `nvarchar(32)` | 通話是否為 PSTN 撥出或撥入電話，以及電話類型，例如使用者撥打電話或音訊會議 |
> | 9 | 數位類型 | `nvarchar(16)` | 使用者的電話號碼類型，例如免付費電話號碼的服務 |
> | 10 | 國內/國際 | `nvarchar(16)` | 通話是國家或地區內的國內 () 或國家或地區以外的國際 (，) 根據使用者的位置 |
> | 11 | 目的地已撥號 | `nvarchar(64)` | 撥號的國家或地區 |
> | 12 | 目的地號碼 | `nvarchar(32)` | [以 E.164](https://en.wikipedia.org/wiki/E.164)格式撥打的號碼 |
> | 13 | 開始時間 | `datetimeoffset` | 通話開始時間 |
> | 14 | 結束時間 | `datetimeoffset` | 通話結束時間 |
> | 15 | 工期秒數 | `int` | 通話已連線多久 |
> | 16 | 連線費用 | `numeric(16, 2)` | 連線費用價格 |
> | 17 | 負責 | `numeric(16, 2)` | 向您的帳戶收取的通話金額或通話費用 |
> | 18 | 貨幣 | `nvarchar(3)` | 用來計算 [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217) (通話成本的貨幣類型)  |
> | 19 | 功能 | `nvarchar(32)` | 通話所用的授權 |

### <a name="exported-direct-routing-usage-report"></a>匯出直接路由使用方式報告

除非國家/地區特定法規禁止保留該期間的資料，否則您最多可以從目前日期匯出資料 (150 天) 。

> [!div class="has-no-wrap"]  
> | # | 名稱 | [資料類型 (SQL Server) ](/sql/t-sql/data-types/data-types-transact-sql) | 描述 |
> | :-: | :-: | :-: |:------------------- |
> | 0 | CorrelationId | `uniqueidentifier` | 通話識別碼。 相同通話的多段小段可以共用相同的相互關聯Id |
> | 1 | AAD ObjectId | `uniqueidentifier` | 在 Azure Active Directory 中撥打使用者的識別碼。<br/> 對於 Bot 通話類型，此和其他使用者資訊可以是 Null/empty |
> | 2 | Upn | `nvarchar(128)` | UserPrincipalName (撥打或接聽來電之使用者或 Bot 的登入名稱、Azure Active Directory) 。<br/>這通常與使用者的 SIP 位址相同，而且可以與使用者的電子郵件地址相同 |
> | 3 | 顯示名稱 | `nvarchar(128)` | 使用者或通話機器人的名稱 (例如，Microsoft 365 系統管理中心中設定的通話佇列或自動語音應答)  |
> | 4 | 使用者國家/地區 | `nvarchar(2)` | 使用者的國家/地區代碼 [，ISO 3166-1 Alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) |
> | 5 | 邀請時間 | `datetimeoffset` | 當初始邀請從 Teams 使用者或 Bot 來電傳送至 SBC，或是由 SBC 直接路由的 SIP Proxy 元件在輸入至 Teams 或 Bot 通話時收到 |
> | 6 | 開始時間 | `datetimeoffset` | SIP Proxy 收到最終答案的時間 (SIP 訊息「200 確定」，) 從 SBC 的輸出 (Teams/Bot 傳送到 PSTN 使用者) ，或在 SIP Proxy 傳送邀請至 Teams 後端的下一個躍點之後，輸入通話 (PSTN 使用者傳送到 Teams/Bot) 。<br/>對於失敗和未接聽的來電，這可以等於邀請或失敗時間 |
> | 7 | 失敗時間 | `datetimeoffset` | 只有在未完全建立) 通話失敗 (才存在 |
> | 8 | 結束時間 | `datetimeoffset` | 只有成功 (完全建立的) 通話才存在。 通話結束的時間 |
> | 9 | 持續時間 (秒)  | `int` | 通話持續時間，從邀請到通話結束或失敗。 針對來電轉接，持續時間包括 [通話佇列] 中的響鈴。 |
> | 10 | 成功 | `nvarchar(3)` | 是/否。 成功或嘗試 |
> | 11 | 來電者號碼 | `nvarchar(32)` | 撥打電話的使用者或 Bot 號碼。 在輸入給 Teams 使用者時，電話會是 PSTN 使用者，從 Teams 使用者撥出電話時，會是 Teams 使用者號碼 |
> | 12 | 來電者號碼 | `nvarchar(32)` | 接聽來電的使用者或 Bot 號碼。 在輸入給 Teams 使用者時，它會是 Teams 使用者，在從 Teams 使用者撥出電話時，會是 PSTN 使用者 |
> | 13 | 通話類型 | `nvarchar(32)` | 通話類型和方向 |
> | 14 | 適用于媒體的 Azure 地區 | `nvarchar(8)` | 用於非略過通話中媒體路徑的資料中心 |
> | 15 | 用於訊號的 Azure 地區 | `nvarchar(8)` | 用於傳訊給略過和非略過通話的資料中心 |
> | 16 | 最終 SIP 代碼 | `int` | 通話結束的代碼 [RFC 3261](https://tools.ietf.org/html/rfc3261) |
> | 17 | 最終 Microsoft 子代碼 | `int` | 除了 SIP 代碼之外，Microsoft 還有自己的子代碼指出特定問題 |
> | 18 | 最後一個 SIP 片語 | `nvarchar(256)` | SIP 程式碼和 Microsoft 子代碼的描述 |
> | 19 | SBC FQDN | `nvarchar(64)` | 會話框線控制器的完整功能變數名稱 |
> | 20 | 媒體旁路 | `nvarchar(3)` | 是/否。 表示主幹是否已啟用媒體略過或未啟用 |
> | 21 | 共用相互關聯識別碼 | `uniqueidentifier` | 表示兩個或多個通話相關聯 |


## <a name="related-topics"></a>相關主題

- [Teams 分析與報告](teams-reporting-reference.md)
- [Microsoft Graph 中的 PSTN 通話報告](/graph/api/callrecords-callrecord-getpstncalls?view=graph-rest-1.0&tabs=http)
- [Microsoft Graph 中的直接路由報表](/graph/api/callrecords-callrecord-getdirectroutingcalls?view=graph-rest-1.0&tabs=http)
