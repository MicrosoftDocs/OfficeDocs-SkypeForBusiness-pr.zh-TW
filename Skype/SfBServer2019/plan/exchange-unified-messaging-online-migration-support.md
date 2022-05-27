---
title: Exchange 整合通訊線上移轉支援
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft 即將在 2020 年 2 月 28 日之前淘汰 Exchange Unified Messaging Online (ExchUMO) 服務。 本文摘要說明受影響的客戶應該知道的事項，以及如何規劃其商務持續性。
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676365"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 整合通訊線上移轉支援

> [!IMPORTANT]
> **自太平洋時間 2020 年 2 月 28 日下午 5 點起，Exchange Online中的整合傳訊服務已不支援。Microsoft 已將所有語音信箱帳戶移轉至雲端語音信箱服務。任何剩餘的自動語音應答流量將不會受到監視，而且可能會隨時中斷。**

在 2019 年 2 月 8 日的[公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)中，Microsoft 即將在 2020 年 2 月 28 日之前淘汰 Exchange Unified Messaging Online (ExchUMO) 服務。 本文提供受影響客戶應該知道的事項摘要，以及如何規劃其商務持續性。

ExchUMO 是由客戶針對語音信箱、自動語音應答、通話佇列和傳真整合服務所部署。 Microsoft 計畫協助客戶遷移至電話系統服務，這些服務已在 商務用 Skype Online 和 Microsoft Teams 上支援數千個客戶。

語音信箱主要是 Microsoft 驅動的移轉;客戶子集可能需要系統管理員介入和/或投資。 自動語音應答是系統管理員驅動的移轉;您必須在雲端自動語音應答雲端服務中重新建立現有的 ExchUMO 自動語音應答樹狀結構。 使用協力廠商 PBX 的任何 ExchUMO 功能的客戶將不會移轉至Skype雲端服務，因為他們不支援協力廠商 PBX 系統。 [此部落](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)格已宣佈協力廠商支援的淘汰方案，而此部署模型中的客戶可以將其使用者移轉至 Microsoft 的其中一個整合通訊平臺/服務，或為這些使用者取得協力廠商語音信箱和/或自動語音應答解決方案。 雲端式服務不支援傳真整合;客戶必須移轉至協力廠商解決方案。

## <a name="who-is-affected"></a>神秘會受到影響嗎？

使用 Exchange Unified Messaging Online 服務中下列任何功能的客戶都會受到影響：

- 語音信箱服務
- 自動語音應答服務
- 通話佇列服務
- 傳真整合

> [!Note]
> 使用任何Exchange Server內部部署與整合傳訊的客戶不會受到影響。

深入瞭解使用者 [體驗影響中的使用者](#user-experience-impact)和系統管理員體驗影響。

## <a name="migration-plan-overview"></a>移轉計畫概觀

Microsoft 識別出各種取用 ExchUMO 功能的客戶部署，並將根據下列計畫協助客戶移轉。

|客戶群組 |時間表  |詳細資料  |
|---------|---------|---------|
|已準備好移轉的客戶<br><br>要移轉的功能：<br><ul><li>語音信箱</ul>   |   2019 年 3 月 - 5 月  |範例：<ul><li>    具有簡單語音信箱部署和使用量的客戶<li>已為 Microsoft 建立執行移轉之所有需求的客戶<ul>|
|具有必要條件的客戶<br><br>要移轉的功能：<br><ul><li>語音信箱<li>自動語音應答<li>通話佇列</ul> |  2019 年 5 月 - 12 月 |範例： <br><ul><li>混合式設定未完成<li>未設定混合式 PSTN 編號</ul>|
|需要系統管理員介入的客戶&客戶投資<br><br>要移轉的功能：<ul><li>語音 信箱<li>自動語音應答<li>通話佇列<li>傳真整合</ul>| 2020 年 2 月  | 範例： <br><ul><li>ExchUMO 服務由協力廠商 PBX 取用<li>具有 PSTN 訂閱者存取需求的客戶<li>SFB 2010 的客戶 (不支援的) <li>傳真整合</ul> |

## <a name="voicemail-migration-guidelines"></a>語音信箱移轉指導方針

### <a name="get-informed"></a>取得通知

熟悉 [部落格公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 和本文，為您的使用者規劃順暢的移轉。 如[需電話系統語音信箱](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)功能的詳細資訊，請參閱檢查商務用 Skype語音信箱和選項。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>建立商務用 Skype混合式拓撲

如果您尚未建立商務用 Skype混合式拓撲，則必須這麼做才能讓語音信箱使用者順暢地移轉。 如需詳細資訊，請參閱設定[混合式商務用 Skype](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)。

> [!Note]
> 您不需要在線上移轉使用者以進行語音信箱服務移轉。 不過，若要讓內部部署使用者利用語音信箱服務電話系統，必須建立混合式拓撲。

### <a name="plan-your-auto-attendant-migration"></a>規劃您的自動語音應答移轉

系統管理員可以隨時開始將其自動語音應答從 ExchUMO 移轉至雲端自動語音應答。 如需詳細資訊，請參閱[設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)。

Microsoft 會繼續提供客戶可能會認為其移轉所需的額外自動語音應答功能。 系統管理員應該評估功能集，並據以移轉其自動語音應答實例。 如需功能清單比較，請參閱 [ExchUMO 和 Azure 雲端式服務功能矩陣](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>規劃您的語音信箱移轉後驗證和測試

語音信箱移轉是 Microsoft 驅動的。 系統管理員不需要執行任何動作，因為已建立必要的混合式拓撲。 Microsoft 會執行必要的驗證和測試，以確保使用者的語音信箱移轉不會中斷。 我們鼓勵系統管理員在其端執行測試和驗證。 如需建議的測試計劃，請參閱系統 [管理員的建議測試計劃和移轉後驗證](#suggested-test-plan-and-post-migration-validation-for-admins) 。

> [!Note]
> 不支援 Lync Server 2010。 如果您是在 2010 伺服器部署中，您應該規劃伺服器升級，或考慮將使用者移轉至 Microsoft Teams。  

### <a name="monitor-the-admin-notification-center"></a>監視管理員通知中心

請在管理員通知中心觀看通知，並提供有關使用者移轉的進一步詳細資料和時程表。 通知會在移轉期間前至少 30 天傳送。

> [!Note]
> 如果您收到使用者移轉時程表的通知，而且基於業務關鍵的原因而想要延後移轉，您可以連絡Microsoft 支援服務。 您無法將移轉延後至 2020 年 2 月 28 日停用日期之後。 對於可能有更多問題的客戶，請連絡您的帳戶小組或Microsoft 支援服務。 已使用Microsoft 365或Office 365的客戶可以透過Microsoft 365 系統管理中心提交支援案例。

### <a name="consider-opting-in-for-a-planned-migration"></a>考慮加入宣告計劃性移轉

您可以加入宣告計劃性語音信箱服務移轉至 CVM。 加入宣告之前，請先檢閱本文的詳細資料，特別是下列各節：

- 本節 (移轉步驟) 
- ExchUMO 和 Azure 雲端式服務功能矩陣
- 使用者體驗影響

當您選擇受控移轉時，您不會在Microsoft 365系統管理入口網站訊息中心收到移轉前 30 天的通知。

若要加入宣告計劃性移轉，請使用下列資訊，從系統管理員的電子郵件地址傳送電子郵件要求至 [cvm@microsoft.com](mailto:cvm@microsoft.com) ：

- 慣用日期 (星期二) ：移轉波會在每個星期二執行一次。 請選取不超過 2019/12/3 的星期二日期。
 
- 租使用者識別碼：32 個字元的數位，格式為 0046728c-688a-4472-a38f-098fec60ac6x。 您可以在 Azure AD 下Microsoft 365管理入口網站中找到您的租使用者識別碼，或使用下列 PowerShell Cmdlet：`Get-CsTenant | Select ObjectId`

成功移轉租使用者之後，您會收到電子郵件確認。

## <a name="auto-attendant-migration-guidelines"></a>自動語音應答移轉指導方針

Microsoft 365和Office 365組織系統管理員必須在 Microsoft 雲端自動語音應答服務中重新建立其Exchange UM Online 自動語音應答，並在 2020 年 2 月 28 日 Exchange UMO 服務淘汰日期之前，將內部部署電話號碼切換至他們。 這是成功移轉和測試新的雲端自動語音應答的建議指導方針。 如果您有大量的自動語音應答，您可以使用[Exchange UM 自動語音應答到雲端自動語音應答移轉腳本](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)，以簡化自動語音應答的大量移轉。

### <a name="auto-attendant-setup"></a>自動語音應答設定

我們強烈建議您提早開始設定新的自動語音應答，以避免最後一分鐘發生問題，並熟悉雲端自動語音應答服務的功能和體驗。 對於需要一或多個間距功能的自動語音應答，您可以在間距功能可用來準備部署時，建立和測試自動語音應答。 如需間距功能的詳細資訊，請參閱 [附錄](#appendix)。

1. 使用 Exchange UMO Cmdlet，使用[Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant)匯出現有自動語音應答的設定。  

2. 使用 Exchange Online PowerShell 中的[Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) Cmdlet，在使用) 時匯出問候媒體檔案 (，並將它們轉換成.mp3格式。

3. 請遵循[規劃雲端自動語音應答](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)和[設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)中的指示，使用 Microsoft Teams 系統管理中心或 PowerShell 建立自動語音應答。

4. 如果功能表選項已變更，請檢閱您的問候語。

5. 使用本文的已知 [問題](#known-issues) 一節中的「自動語音應答來電傳送至 PSTN」因應措施，設定傳送至回應群組。  

6. 在內部呼叫新的自動語音應答，或指派測試電話號碼來測試新的自動語音應答。  

### <a name="cutover"></a>系統轉換

1. 將電話號碼從Exchange UMO 自動語音應答切換至新的自動語音應答。
2. 將 SIP URI 從連絡人物件移至資源帳戶。
3. 使用新指派的電話號碼來測試和驗證您的自動語音應答。

## <a name="appendix"></a>附錄

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 雲端式服務功能矩陣

| 服務 | 功能層級 | 功能 | 附註  | 雲端 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 服務功能| 支援協力廠商 PBX    | 包含所有提供給協力廠商 PBX 的功能，例如 MWI (訊息等候指標) 使用 SIP 通知來自 Exchange UM Online 的訊息 | N   | Y    |
| VM | 服務功能  | 支援商務用 Skype Server   |  | Y | Y    |
| VM | 服務功能 | 支援Microsoft Teams|  | Y | N    |
| VM | 服務功能 | eDiscovery 和 Hold  | 安全性與合規性  | Y | Y    |
| VM | 服務功能 | Exchange規則支援 | 安全性與合規性  | Y | Y    |
| VM | 使用者功能 | PSTN 撥入存取  | 訂閱者存取  | N | Y    |
| VM | 使用者功能 | 委託  | 未接來電的電子郵件  | N | Y    |
| VM | 使用者功能 | PSTN Outlook 語音存取   | 訂閱者存取  | N | Y    |
| VM | 使用者功能 | 使用已驗證端點的撥入 | 呼叫語音信箱服務以接聽語音訊息並變更語音信箱設定| Y | Y    |
| VM | 使用者功能 | 停用語音信箱的使用者設定   |  | Y | Y    |
| VM | 使用者功能 | 變更個人問候語的使用者設定  |  | Y | Y    |
| VM | 使用者功能 | 建立 OOF 問候語的使用者設定  |  | Y | Y    |
| VM | 使用者功能 | 變更預設語言的使用者設定  |  | Y | Y    |
| VM | 使用者功能 | 使用 TTS 覆寫預設問候語的使用者設定  |  | Y | N    |
| VM | 使用者功能 | 記錄已驗證裝置 (的個人問候語)  |  | Y | Y    |
| VM | 使用者功能 | 在 PSTN)  (錄製個人問候語 — 在手機上播放 |  | N | Y    |
| VM | 使用者功能 | 停用轉譯的使用者設定 |  | N | Y    |
| VM | 使用者功能 | 謄寫  |  | Y | Y    |
| VM | 使用者功能 | 使用 SIP 通知訊息) MWI (訊息等候指標 |  | N | Y    |
| VM | 使用者功能 | OUTLOOK中的 MP3 音訊檔案格式    |  | Y | Y    |
| VM | 使用者功能 | 變數速度播放控制項 |  | Y | Y    |
| VM | 使用者功能 | 轉寄語音信箱  | 將收到的語音信箱轉寄給其他使用者 | Y | Y    |
| VM | 使用者功能 | 傳送語音訊息給使用者群組  |語音信箱廣播   | N | Y   |
| VM | 使用者功能 | 使用 簡訊 的語音信箱通知    | 當使用者有新的語音信箱時，可以收到簡訊    | N | Y    |
| VM | 使用者功能 | 支援的問候語 | 這裡的詳細資料： [什麼是雲端自動語音應答？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| VM | 使用者功能 | 自動答錄規則 |  | Y | Y    |
| VM | 使用者功能 | 在電話上播放 (PSTN) - 播放訊息 | 在我的資料格上呼叫我以接聽語音訊息  | N | Y    |
| VM | 使用者功能 | 在電話上播放 (驗證) - 播放訊息 | 在我的已驗證裝置上呼叫我  | N | Y    |
| VM | 使用者功能 | 多個使用者之間的共用信箱 |  | Y | Y    |
| VM | 呼叫端功能  | 來電者體驗 - 受保護的語音信箱 | 呼叫端可以選擇將記錄的訊息標示為受保護的選項| N | Y    |
| VM | 呼叫端功能  | 來電者體驗 - 私人語音信箱 | 呼叫端可以選擇將錄製的訊息標示為私人的選項  | N | Y    |
| VM | 呼叫端功能  | 無聲偵測   |  | N | Y    |
| VM | Tenant-Admin功能 | 伺服器層級受保護的語音信箱    | 租使用者系統管理員可以設定服務層級規則，將傳入的語音信箱標示為受保護 | Y | Y    |
| VM | Tenant-Admin功能 | 變更錄製持續時間限制  |     | Y | Y    |
| VM | Tenant-Admin功能 | 變更無聲偵測逾時    |  | 不適用    | Y    |
| VM | Tenant-Admin功能 | 變更輸入失敗數目 | CVM：硬式編碼為 3 | N | Y    |
| VM | Tenant-Admin功能 | 變更預設語言 |  | Y | Y    |
| VM | Tenant-Admin功能 | 停用/啟用轉譯 |  | Y | Y    |
| VM | Tenant-Admin功能 | 停用/啟用未接來電通知 |  | N | Y    |
| VM | Tenant-Admin功能 | 協助 Microsoft 改善語音信箱預覽   這些選項可讓 Microsoft 改善語音信箱預覽的品質。    |  | Y | Y    |
| VM | Tenant-Admin功能 | 自訂已啟用使用者的簡訊|  | 不適用    | Y    |
| VM | Tenant-Admin功能 | 轉譯不雅內容遮罩|  | Y | N    |
| VM | Tenant-Admin功能 | 語音信箱原則    |   | Y | Y    |
| VM | Tenant-Admin功能 | 入口網站管理   |  | CY19   | Y    |
| VM | Tenant-Admin功能 | PowerShell   |  | Y | Y    |
| UM | 使用者功能 | 商務用 Skype認證手機上的訊息等候指標 (MWI)    |可以由電話合作夥伴提供  | 否 | 是    |
| 機 管 局 | 服務功能 | AA 支援協力廠商 PBX    |  | N | Y    |
| 機 管 局 | 服務功能 | 支援商務用 Skype Server   |  | Y | Y    |
| 機 管 局 | 服務功能 | 支援Microsoft Teams|  | Y | N    |
| 機 管 局 | 服務功能 | 依名稱撥號，DTMF 輸入    |  | Y | Y    |
| 機 管 局 | 服務功能 | 依名稱撥號，語音輸入  |  | Y | Y    |
| 機 管 局 | 服務功能 | 多語言支援 | 這裡的語言詳細資料： [什麼是雲端自動語音應答？](/microsoftteams/what-are-phone-system-auto-attendants) | Y | Y    |
| 機 管 局 | 服務功能 | 傳送至操作員、CQ 或使用者 |  | Y | Y    |
| 機 管 局 | 服務功能 | 在內部傳輸至 PSTN 號碼 (DID RNL)   |  | Y | Y    |
| 機 管 局 | 服務功能 | 從外部傳輸至 PSTN 號碼  |  | 請參閱下方的已知問題一節 | Y    |
| 機 管 局 | 服務功能 | 營業時間 |  | Y | Y    |
| 機 管 局 | 服務功能 | 功能表選項 | IVR 功能表選項  | Y | Y    |
| 機 管 局 | 服務功能 | 將雲端 PSTN 號碼指派給 AA |  | Y | N    |
| 機 管 局 | 服務功能 | 將內部部署 PSTN 號碼指派給 AA  |  | Y | Y    |
| 機 管 局 | 服務功能 | 自訂使用者選取專案  | 讓來電者連線到自訂的組織使用者清單| Y | Y    |
| 機 管 局 | 服務功能 | 下班和假日處理  |  | Y | Y    |
| 機 管 局 | 服務功能 | 使用文字轉換語音的自訂問候語  |  | Y | Y    |
| 機 管 局 | 服務功能 | 分機撥號   | 撥接使用者的擴充功能以連絡使用者  | Y   | Y    |
| 機 管 局 | 服務功能 | AA 呼叫者離開郵件的信箱    |  | Y   | Y    |
| 機 管 局 | 服務功能 | 多個 PSTN 編號指派給 AA|  | Y | Y    |
| 機 管 局 | Tenant-Admin功能 | 入口網站管理   |  | Y | N    |
| 機 管 局 | Tenant-Admin功能 | PowerShell Cmdlet  |  | Y | Y    |
| 傳真| 服務功能 | 傳真整合|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>系統管理員的建議測試計劃和移轉後驗證

若要驗證您的使用者是否已移轉至雲端語音信箱，請將語音信箱保留給使用者，並在Outlook中檢查訊息本文。 雲端語音信箱訊息的頁尾如下：

「感謝您使用轉譯！ 如果您在上面看不到文字記錄，這是因為音訊品質不夠清楚，無法轉譯。」

在移轉使用者之後測試語音信箱功能時，請務必考慮下列案例：

- 驗證組織中所有端點類型的語音信箱存取，例如應用程式和 IP 電話。
- 向範例使用者驗證已設定的個人化問候語會播放給來電者。
- 如果您的組織有停用使用者轉譯的法律或合規性需求，請確定移轉後已停用轉譯。 如需詳細資訊，[請參閱設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail)。
- 如果您先前已設定Exchange VM 原則和規則，請確定它們有效。
- 熟悉雲端語音信箱服務 PowerShell Cmdlet 來變更使用者設定。  

### <a name="user-experience-impact"></a>使用者體驗影響

以下是使用者語音信箱移轉體驗的概觀。


|體驗  |使用者體驗的變更|
|---------|---------|
|電子郵件通知 | 不變更<br>不會傳送任何電子郵件給使用者，通知他們語音信箱帳戶啟用/移轉。 |
|存取先前的訊息 | 不變更<br>使用者可以存取所有支援端點中先前的語音信箱訊息。 |
|在 Outlook、SFB Apps 中接收 VM| 不變更<br>使用者會繼續在所有支援的端點中接收其語音信箱訊息。 |
|謄寫 | 增強<br>CVM 轉譯的精確度率和支援語言遠高於 ExchUMO。 |
|使用者設定 | 新體驗<br>使用者可以從使用者設定入口網站變更其喜好設定 (USP) 。 使用者可以從語音信箱電子郵件中的超連結，或其 SFB 用戶端上的 [User-Settings] 按鈕存取其 USP; https://aka.ms/vmsettings.
 |功能| 如需詳細資訊，請參閱功能集比較。 |
|Outlook VM 訊息的規則 | 不變更<br>先前建立的規則會在移轉之後套用至 CVM 訊息。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的使用者管理和布建

新商務用 Skype使用者會在建立時自動布建為雲端語音信箱。 布建新的語音信箱使用者不需要額外的系統管理員工作或授權。 請參閱[設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail)，以瞭解現有和新使用者的原則管理。

### <a name="admin-auto-attendant-management-experience"></a>管理員自動語音應答管理體驗

若要深入瞭解自動語音應答，請參閱[設定雲端自動語音應答](/microsoftteams/create-a-phone-system-auto-attendant)。

### <a name="known-issues"></a>已知問題

#### <a name="greeting-inconsistencies"></a>問候語不一致

訂閱者存取權可能會繼續為您的租使用者工作，直到服務完全淘汰為止，即使您所有的使用者都已移轉至 雲端語音信箱。 若要避免使用者混淆和不一致的體驗，請停用訂閱者存取，因為問候語會在移轉後變更。 若要這樣做，請使用 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 移除每個訂閱者存取行的 EXUM 連絡人。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自動語音應答通話傳送至 PSTN

若要透過 自動語音應答 商務用 Skype Server 或回應群組服務 (RGS) 在 商務用 Skype Server 上轉接外部 PSTN 電話號碼，請建立新的內部部署使用者，並將通話轉接設定為 PSTN 電話號碼或 RGS 電話號碼。 使用者必須針對企業語音啟用並正確設定，並已指派語音原則。

#### <a name="shared-mailbox-is-still-accessible"></a>共用信箱仍可存取

使用 Exchange UM Online 設定的共用信箱會在移轉至 CVM 之後繼續接收訊息，並可透過Outlook存取使用者。 不過，一旦移轉至 CVM，將無法存取變更這些信箱的問候訊息。 使用共用信箱來擷取自動語音應答呼叫端的客戶，應在 2019 年 10 月 ETA (發行後，利用自動語音應答和通話佇列共用信箱功能) 。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>「使用者名稱未使用商務用 Skype」橫幅顯示

CVM 服務是以Microsoft Teams基礎結構為基礎，而來自商務用 Skype用戶端的呼叫可能會在用戶端上顯示資訊橫幅，其內容如下：「使用者名稱未使用商務用 Skype。 如需更豐富的體驗，請切換至Teams或開始Skype會議」。
請務必將使用者的商務用 Skype用戶端更新為最新的 C2R 用戶端更新，以防止此橫幅出現。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>「設定語音信箱」會帶您前往 OWA

在移轉至 CVM 之後，按一下用戶端的 [**設定語音信箱**] 會繼續將 商務用 Skype Server 2015/2013 客戶移轉至 Office Web 存取 (OWA) 入口網站頁面。 所有設定都已從 OWA 的 [語音信箱] 索引標籤中移除，而橫幅會顯示重新導向連結，將使用者帶往 CVM 使用者設定入口網站。

#### <a name="changing-greeting-remotely"></a>從遠端變更問候語

CVM 不支援 PSTN 訂閱者存取。 對於需要從遠端變更問候語的使用者，已將 [變更問候語] 功能表選項新增至行動用戶端的語音信箱 IVR 服務。 使用者可以在行動用戶端撥號臺上按住 「1」 鍵來呼叫此服務。