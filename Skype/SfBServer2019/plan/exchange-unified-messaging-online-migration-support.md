---
title: Exchange 整合通訊線上移轉支援
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft 正在淘汰2020年2月的 Exchange 整合訊息 Online （ExchUMO）服務。 本文將摘要說明客戶應該知道哪些內容，並針對其業務連續性進行規劃。
ms.openlocfilehash: adef85a59a5d0add990196e5b76587b502f052b5
ms.sourcegitcommit: 4ccc24dcf61cf9b59224b85757f93f8aceae1771
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2019
ms.locfileid: "40854088"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 整合通訊線上移轉支援

如需2019年2月8日的[公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)參考，Microsoft 即將于2020年2月前淘汰 Exchange 整合訊息線上（ExchUMO）服務。 本文將摘要說明客戶應該知道的內容，並針對其業務連續性進行規劃。
 
ExchUMO 是由客戶針對語音信箱、自動語音應答、通話佇列及傳真整合服務進行部署。 Microsoft 方案可協助客戶遷移到已支援商務用 Skype Online 和 Microsoft 團隊的成千上萬客戶的手機系統服務。

語音信箱主要是 Microsoft 導向的遷移;客戶的子集可能需要系統管理員參與與/或投資。 自動語音應答是系統管理員導向的遷移;您將需要在雲端自動語音應答雲端服務中重新建立現有的 ExchUMO 自動語音應答樹。 使用任何 ExchUMO 功能與協力廠商 PBX 的客戶將不會被遷移到 Skype 雲端服務，因為它們不支援協力廠商 PBX 系統。 在[此博客](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)中宣告的協力廠商支援的退休方案，此部署模型中的客戶可以將他們的使用者遷移至 Microsoft 的整合通訊平臺/服務，或為這些使用者取得協力廠商的語音信箱和/或自動語音應答方案。 雲端服務不支援 [傳真整合];客戶將需要遷移至協力廠商解決方案。

### <a name="who-is-affected"></a>誰會受到影響？

使用 Exchange 整合訊息線上服務的下列任何功能的客戶會受到影響：

- 語音信箱服務
- 自動助理服務
- 通話佇列服務
- 傳真整合

> [!Note]
> 使用任何 Exchange Server 內部部署且具有整合訊息的客戶不會受到影響。 

深入瞭解使用者與系統管理經驗對[使用者經驗的影響](#user-experience-impact)。

## <a name="migration-plan-overview"></a>遷移方案概覽

Microsoft 已發現各種使用 ExchUMO 功能的客戶部署，並將根據下列方案協助客戶進行遷移。 

|客戶群組 |時間表  |詳細資料  |
|---------|---------|---------|
|已準備好要開始遷移的客戶<br><br>要遷移的功能：<br><ul><li>語音信箱</ul>   |   三月（2019年5月）  |示例<ul><li>    具備簡單語音信箱部署和使用方式的客戶<li>已針對 Microsoft 建立所有需求以執行遷移的客戶<ul>|
|具有先決條件的客戶<br><br>要遷移的功能：<br><ul><li>語音信箱<li>自動語音應答<li>通話佇列</ul> |  五月-2019 年12月 |示例 <br><ul><li>混合式設定無法完成<li>混合式 PSTN 數位沒有設定</ul>|
|需要系統管理員參與才能 & 客戶投資的客戶<br><br>要遷移的功能：<ul><li>語音信箱<li>自動語音應答<li>通話佇列<li>傳真整合</ul>| 2020年2月  | 示例 <br><ul><li>ExchUMO 服務是由協力廠商 PBX 所使用<li>具備 PSTN 訂閱者存取需求的客戶<li>SFB 2010 上的客戶（不支援）<li>傳真整合</ul> |

## <a name="voicemail-migration-steps"></a>語音信箱遷移步驟

1.  **取得通知**
 
    熟悉[博客公告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/)和本文，為您的使用者規劃平滑的遷移。 如需手機系統語音信箱功能的詳細資料，請參閱[查看商務用 Skype 語音信箱和選項](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8)。  
 
2.  **建立商務用 Skype 混合式拓朴**

    如果您沒有建立商務用 Skype 混合式拓朴，您必須執行此動作，才能順利地遷移語音信箱使用者。 如需詳細資訊，請參閱[設定商務用 Skype 混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)式。 

    > [!Note]
    > 您不需要將使用者連線至線上語音信箱服務的遷移。 不過，對於內部部署使用者，若要利用電話系統語音信箱服務，必須建立混合式拓撲。

3. **規劃您的自動助理遷移**
    
    系統管理員可以隨時開始將其自動語音應答從 ExchUMO 遷移到雲端自動語音應答。 如需詳細資訊，請參閱[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。 Microsoft 繼續提供客戶可能會考慮其遷移所需的其他自動語音應答功能，系統管理員應該評估該功能集並據此遷移其自動助理實例。 如需功能清單比較，請參閱[ExchUMO 和 Azure 雲端服務功能矩陣](#exchumo-and-azure-cloud-based-services-feature-matrix)。

4. **規劃語音信箱的遷移後驗證與測試**

    語音信箱遷移是由 Microsoft 所驅動。 系統管理員不需要執行任何動作，前提是已建立預先必備的混合式拓撲。 Microsoft 會執行所需的驗證與測試，以確保使用者的語音信箱遷移不會中斷。 系統會鼓勵管理員在其側邊進行測試和驗證。 針對建議的測試方案，請參閱[適用于系統管理員的建議測試計劃和遷移後驗證](#suggested-test-plan-and-post-migration-validation-for-admins)。 

    > [!Note]
    > 不支援 Lync Server 2010。 如果您使用的是2010伺服器部署，您應該規劃伺服器升級，或考慮將您的使用者遷移至 Microsoft 團隊或商務用 Skype Online。  

5. **監控系統管理員通知中心**

    在系統管理通知中心中查看有關使用者遷移的詳細資料與時程表的相關通知。 通知會在您的遷移期間前至少在30天內傳送。 

    > [!Note]
    > 如果您收到與使用者的 [遷移] 時程表的通知，而且想要推遲您的遷移以滿足業務關鍵型的原因，您可以使用 Microsoft 支援服務來執行此動作。 請注意，您無法將遷移推遲到2020年2月的退休日期之後。 針對可能有其他問題的客戶，請聯絡您的帳戶小組或 Microsoft 支援人員。 已使用 Office 365 的客戶可透過 Office 365 管理入口網站提交支援案例。 

6. **考慮在規劃的遷移中加入宣告**

    您可以加入宣告規劃的語音信箱服務遷移以進行 CVM。 在選擇之前，請先複習本文的詳細資料，尤其是下列各節：

    - 遷移步驟（本節）
    - ExchUMO 和 Azure 雲端服務功能矩陣
    - 使用者經驗影響

    當您選擇受管理的遷移時，您將不會在 Microsoft 365 系統管理入口網站訊息中心收到30天的預遷移通知。
 
    若要加入宣告規劃的遷移，請從您的系統管理員電子郵件地址傳送電子郵件要求，以使用下列資訊來[cvm@microsoft.com](mailto:cvm@microsoft.com) ：

    - [慣用日期（星期二）]：每週二都會執行一次遷移波。 請在星期二，選取不超過12/3/2019 的日期。
 
    - 租使用者識別碼：32字元數格式為 0046728c-688a-4472-a38f-098fec60ac6x。 您可以在 Microsoft 365 系統管理入口網站下的 Azure AD 中找到您的租使用者識別碼，或使用下列 PowerShell Cmdlet：`Get-CsTenant | Select ObjectId`
 
    當您的租使用者成功遷移之後，您會收到一封電子郵件確認。

## <a name="auto-attendant-migration-guidelines"></a>自動助理遷移指導方針

Office 365 租使用者管理員必須在 Microsoft 雲端自動語音應答服務中重新建立 Exchange UM 線上自動語音應答，並將其內部部署的電話號碼切換到2020年2月28日，即 Exchange UMO 服務將退出. 這是成功遷移並測試新雲端自動語音應答的建議原則。 如果您有大量的自動語音應答，您可以使用[EXCHANGE UM 自動語音應答加入雲端自動助理遷移腳本](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA)，以簡化自動語音應答的大量遷移。

### <a name="setup"></a>Setup.exe

我們強烈建議您提前開始設定新的自動語音應答，以避免過去的分鐘問題，並熟悉雲端自動語音應答服務的功能和體驗。 針對需要一個或多個差距功能的自動語音應答，您可以在有間距功能可供部署時，建立並測試自動語音應答。 如需有關差距功能的詳細資訊，請參閱[附錄](#appendix)。

1. 使用 [Exchange UMO Cmdlet]，透過[UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)來匯出現有自動語音應答的設定。  
2. 使用 Exchange Online PowerShell 中的[Export UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) Cmdlet 來匯出問候語媒體檔案（如果有的話），並將其轉換為 mp3 格式。
3. 依照[規劃雲端自動](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md)語音應答中的指示進行，並[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答，以使用 Microsoft 團隊系統管理中心或 Powershell 來建立自動語音應答。
4. 如果功能表選項變更，請查看您的問候語。
5. 在本文的 [[已知問題](#known-issues)] 區段中，使用「自動語音應答來電轉接到 PSTN」的因應措施來設定轉移到您的回應群組。  
6. 測試新的自動語音應答。 若要測試，請在內部呼叫它們或指派測試電話號碼。  

### <a name="cutover"></a>切換

1. 將您的電話號碼從 Exchange UMO [自動語音應答] 切換到新的自動語音應答。
2. 從連絡人物件將 SIP URI 移至資源帳戶。
3. 使用新近指派的電話號碼來測試和驗證自動語音應答。 

## <a name="appendix"></a>參見

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 雲端服務功能矩陣

| Services | 功能層級 | 功能 | 筆記  | 雲端 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | 服務功能| 支援協力廠商 PBX    | 在 Exchange UM Online 中使用 SIP 通知訊息，包括提供給協力廠商 PBX （例如 MWI （訊息等候指示器）的所有功能 | 否   | 是    |
| VM | 服務功能  | 支援商務用 Skype Server   |  | 是 | 是    |
| VM | 服務功能 | 支援 Microsoft 團隊|  | 是 | 否    |
| VM | 服務功能 | 電子檔探索和保留  | 針對安全性與合規性  | 是 | 是    |
| VM | 服務功能 | Exchange 規則支援 | 針對安全性與合規性  | 是 | 是    |
| VM | 使用者功能 | PSTN 撥入存取  | 訂閱者存取  | 否 | 是    |
| VM | 使用者功能 | PSTN Outlook 語音存取   | 訂閱者存取  | 否 | 是    |
| VM | 使用者功能 | 使用已驗證的端點撥入 | 呼叫語音信箱服務收聽語音訊息及變更語音信箱設定| 是 | 是    |
| VM | 使用者功能 | 停用語音信箱的使用者設定   |  | 是 | 是    |
| VM | 使用者功能 | 變更個人問候語的使用者設定  |  | 是 | 是    |
| VM | 使用者功能 | 建立 OOF 問候的使用者設定  |  | 是 | 是    |
| VM | 使用者功能 | 變更預設語言的使用者設定  |  | 是 | 是    |
| VM | 使用者功能 | 使用 TTS 覆寫預設問候語的使用者設定  |  | 是 | 否    |
| VM | 使用者功能 | 錄製個人問候（經過驗證的裝置） |  | 是 | 是    |
| VM | 使用者功能 | 錄製個人問候（PSTN）-在手機上播放 |  | 否 | 是    |
| VM | 使用者功能 | 停用文字的使用者設定 |  | 否 | 是    |
| VM | 使用者功能 | 轉譯  |  | 是 | 是    |
| VM | 使用者功能 | 所有端點上的視覺語音信箱   | 在所有支援的端點上，都可以使用使用者控制項來播放、刪除、訊息等候標記，以及狀態切換  | 是 | 是    |
| VM | 使用者功能 | Outlook 中的 MP3 音訊檔案格式    |  | 是 | 是    |
| VM | 使用者功能 | 變速播放控制 |  | 是 | 是    |
| VM | 使用者功能 | 轉寄語音信箱  | 將收到的語音信箱轉寄給其他使用者 | 是 | 是    |
| VM | 使用者功能 | 傳送語音訊息給一組使用者  |語音信箱廣播   | 否 | 是   |
| VM | 使用者功能 | 使用 SMS 的語音信箱通知    | 當使用者有新的語音信箱時，可能會收到一則 SMS    | 否 | 是    |
| VM | 使用者功能 | 支援的問候語言 | 詳細資料如下：https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 是 | 是    |
| VM | 使用者功能 | 呼叫應答規則 |  | 是 | 是    |
| VM | 使用者功能 | 在電話上播放（PSTN）-播放訊息 | 在我的儲存格上呼叫我以聽取語音訊息  | 否 | 是    |
| VM | 使用者功能 | 在電話上播放（驗證）-播放訊息 | 在已驗證的裝置上呼叫我  | 是 | 是    |
| VM | 使用者功能 | 在多個使用者之間共用信箱 |  | 是 | 是    |
| VM | 來電者功能  | 來電者體驗-受保護的語音信箱 | 來電者可以選擇將錄製的郵件標示為受保護的選項。| 否 | 是    |
| VM | 來電者功能  | 來電者體驗-私人語音信箱 | 來電者可以選擇將錄製的郵件標示為私人的選項。  | 否 | 是    |
| VM | 來電者功能  | 靜音偵測   |  | 否 | 是    |
| VM | 租使用者-系統管理功能 | 伺服器層級受保護的語音信箱    | 租使用者-系統管理員可以設定服務層級規則，將來電語音信箱標示為受保護 | 是 | 是    |
| VM | 租使用者-系統管理功能 | 變更錄製持續時間限制  |     | 是 | 是    |
| VM | 租使用者-系統管理功能 | 變更靜音偵測超時    |  | 不適用    | 是    |
| VM | 租使用者-系統管理功能 | 變更輸入失敗次數 | CVM：硬性編碼為3 | 否 | 是    |
| VM | 租使用者-系統管理功能 | 變更預設語言 |  | 是 | 是    |
| VM | 租使用者-系統管理功能 | 停用/啟用 [文字] |  | 是 | 是    |
| VM | 租使用者-系統管理功能 | 停用/啟用未接來電通知 |  | 否 | 是    |
| VM | 租使用者-系統管理功能 | 協助 Microsoft 改善語音信箱預覽    |  | 是 | 是    |
| VM | 租使用者-系統管理功能 | 自訂已啟用使用者的文字訊息|  | 不適用    | 是    |
| VM | 租使用者-系統管理功能 | [有褻瀆的猥褻遮罩]|  | 是 | 否    |
| VM | 租使用者-系統管理功能 | 語音信箱原則    |   | 是 | 是    |
| VM | 租使用者-系統管理功能 | 網頁入口網站管理   |  | CY19   | 是    |
| VM | 租使用者-系統管理功能 | PowerShell   |  | 是 | 是    |
| AA | 服務功能 | AA 支援協力廠商 PBX    |  | 否 | 是    |
| AA | 服務功能 | 支援商務用 Skype Server   |  | 是 | 是    |
| AA | 服務功能 | 支援 Microsoft 團隊|  | 是 | 否    |
| AA | 服務功能 | 以名稱、DTMF 輸入撥打電話    |  | 是 | 是    |
| AA | 服務功能 | 撥號者名稱、語音輸入  |  | 是 | 是    |
| AA | 服務功能 | 多語言支援 | [語言詳細資料] 如下：https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | 是 | 是    |
| AA | 服務功能 | 轉接至操作員、CQ 或使用者 |  | 是 | 是    |
| AA | 服務功能 | 內部轉接至 PSTN 號碼（RNL）  |  | 是 | 是    |
| AA | 服務功能 | 外部轉接至 PSTN 號碼  |  | 請參閱下方的 [已知問題] 區段 | 是    |
| AA | 服務功能 | 商務時間 |  | 是 | 是    |
| AA | 服務功能 | 功能表選項 | IVR 功能表選項  | 是 | 是    |
| AA | 服務功能 | 將雲端 PSTN 編號指派給 AA |  | 是 | 否    |
| AA | 服務功能 | 將內部部署 PSTN 編號指派給 AA  |  | 是 | 是    |
| AA | 服務功能 | 自訂使用者選取專案  | 啟用呼叫者以取得自訂的組織使用者清單| 是 | 是    |
| AA | 服務功能 | 下班後和假日治療  |  | 是 | 是    |
| AA | 服務功能 | 使用文字到語音的自訂問候語  |  | 是 | 是    |
| AA | 服務功能 | 擴充撥號   | 撥打電話給使用者以進行延伸  | 是   | 是    |
| AA | 服務功能 | AA 呼叫者信箱來留言    |  | 是   | 是    |
| AA | 服務功能 | 將多個 PSTN 號碼指派給 AA|  | 是 | 是    |
| AA | 租使用者-系統管理功能 | 網頁入口網站管理   |  | 是 | 否    |
| AA | 租使用者-系統管理功能 | PowerShell Cmdlet  |  | 是 | 是    |
| 傳入| 服務功能 | 傳真整合|  | 否 | 是    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>系統管理員建議的測試計劃和遷移後驗證

若要驗證您的使用者是否已遷移至雲端語音信箱，請將語音信箱提供給使用者，並在 Outlook 中檢查郵件的正文。  雲端語音信箱訊息的頁尾為：

**感謝您使用 [文字]！如果您沒有看到上述記錄，這是因為音訊品質不足以將抄寫。**

當您在使用者遷移之後測試語音信箱功能時，請務必考慮下列案例：

- 驗證貴組織中所有端點類型的語音信箱存取： app 與 IP 電話。 
- 使用範例使用者進行驗證，將已設定的個人化問候語播放給呼叫者。   
- 如果您的組織有法律或合規性需求來停用使用者，請確認它已停用遷移後。 如需詳細資訊，請參閱[設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail)。
- 如果您先前設定過 Exchange VM 原則與規則，請確定它們有效。
- 熟悉雲端語音信箱服務 PowerShell Cmdlet 來變更使用者設定。  

### <a name="user-experience-impact"></a>使用者經驗影響

以下是最終使用者語音信箱遷移體驗的概覽。


|體驗  |使用者體驗中的變更|
|---------|---------|
|電子郵件通知 | 沒有變更<br>不會傳送電子郵件給使用者，通知他們有關語音信箱帳戶啟用/遷移的資訊。 |
|存取前一封郵件 | 沒有變更<br>使用者可以在所有支援的端點中存取先前的語音信箱訊息。 |
|在 outlook 中接收 VM，SFB 應用程式| 沒有變更<br>使用者繼續在所有支援的端點中接收語音信箱訊息。 |
|轉譯 | 增強<br>CVM 的精確度率和支援的語言比 ExchUMO 高得多。 |
|使用者設定 | 新的體驗<br>使用者可以從使用者設定入口網站（USP）變更其喜好設定。 使用者可以從其語音信箱電子郵件中的超連結存取其 USP，或從其 SFB 用戶端上的 [使用者設定] 按鈕。https://aka.ms/vmsettings.   
 |Features| 請參閱功能設定比較，以取得詳細資料。 |
|VM 郵件的 Outlook 規則 | 沒有變更<br>在遷移之後，先前建立的規則將會套用至 CVM 的訊息。
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的使用者管理和資源調配

新的商務用 Skype 使用者會在建立時自動為雲端語音配置。 您不需要額外的系統管理員工作或授權，就能提供新的語音信箱使用者。 請參閱[設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail)，瞭解現有與新使用者的原則管理。

#### <a name="admin-auto-attendant-management-experience"></a>管理員自動語音應答管理體驗

若要深入瞭解自動語音應答，請參閱[設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。

#### <a name="known-issues"></a>已知問題

**自動語音應答來電轉接至 PSTN**我們鼓勵客戶設定暫時的因應措施，以滿足將自動語音應答來電轉接至外部 PSTN 號碼或 RGS 實例的需求。 
 
在品質保證期間發現 [轉接到 PSTN 號碼] 功能時，不會及時固定該問題，讓客戶在2020年2月1日的排程退休日期之前開始遷移。 作為因應措施，管理員可以將自動語音應答呼叫者轉接至內部部署虛擬使用者，並使用 [作用中的呼叫轉寄] 設定來傳送至所需的 PSTN 電話號碼或 RGS 電話號碼。 
 
預期體驗
- 系統管理員不需要授權虛擬使用者，因為這是一個因應措施解決方法 
- 系統管理員可以將所需的號碼指派給虛擬使用者，或使用 SBC 數位操作功能，來操縱 PSTN 接收器所能看到的本機號碼
- PSTN 呼叫者在來電轉接期間不會遇到任何延遲，而且在傳輸成功後，會繼續看到自動語音應答的本機號碼  

**共用信箱：** 使用 Exchange UM Online 設定的共用信箱會在遷移至 CVM 後繼續接收訊息，並可透過 Outlook 繼續透過使用者存取。 不過，一旦遷移至 CVM，就無法使用變更這些信箱之問候語的存取權。 使用共用信箱來捕獲自動語音應答呼叫者的客戶，在發佈之後，就應該使用自動語音應答及呼叫佇列共用信箱功能（ETA 年10月2019）。
  
**升級至 SFB 用戶端上的團隊橫幅：** CVM 服務是以 Microsoft 團隊基礎結構為基礎;從商務用 Skype 用戶端撥打電話給它，可能會導致在用戶端顯示資訊橫幅，閱讀：「Username 不是使用商務用 Skype。 若要取得更豐富的體驗，請切換至 [團隊] 或 [開始 Skype 會議]。
請務必將您使用者的商務用 Skype 用戶端更新為最新的 C2R 用戶端更新，以免出現這種橫幅。
  
**設定您的語音信箱會將您帶到 OWA：** 按一下用戶端上的 [設定語音信箱]，將會在遷移至 CVM 之後，繼續將商務用 Skype Server 2015/2013 客戶帶到 Office Web Access （OWA）入口網站頁面。 所有設定都已從 OWA 中的 [語音信箱] 索引標籤中移除，且會顯示一個 [重新導向] 連結，讓使用者移至 CVM [使用者設定] 入口網站。
 
**變更問候語行動裝置存取：** CVM 不支援 PSTN 訂閱者存取。 針對需要在遠端變更其問候語的使用者，會將 [變更您的問候] 功能表選項新增至行動用戶端的語音信箱 IVR 服務。 使用者可以在行動用戶端撥號盤上，按住 [1] 鍵來呼叫此服務。
