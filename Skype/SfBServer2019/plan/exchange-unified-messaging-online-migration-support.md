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
localization_priority: Normal
description: Microsoft 正在撤銷2020年2月28日的 Exchange 整合通訊線上 (ExchUMO) 服務。 本文摘要說明哪些受影響客戶應知道哪些專案，以及應如何規劃其業務持續性。
ms.openlocfilehash: 57f7575626d00cbd7c592349ca7a5a92c75eb34c
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255436"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Exchange 整合通訊線上移轉支援

> [!IMPORTANT]
> **Exchange Online 中的整合通訊服務的支援超出太平洋時間2月28日（2020、5 PM）。Microsoft 的所有語音信箱帳戶已遷移至雲端語音信箱服務。任何剩餘的自動語音應答流量都不會受到監控，而且可能會在任何時間中斷。**

在2019年2月8日 [發佈的宣告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 中，Microsoft 正在撤銷 Exchange 整合通訊線上 (ExchUMO) 服務，2020年2月28日。 本文摘要說明哪些受影響客戶應知道哪些專案，以及應如何規劃其業務連續性。

客戶會透過語音信箱、自動語音應答、通話佇列和傳真整合服務，部署 ExchUMO。 Microsoft 計畫可協助客戶遷移至已在商務用 Skype Online 和 Microsoft 團隊上支援數以千計客戶的電話系統服務。

語音信箱主要是 Microsoft 導向的遷移;客戶的子集可能需要系統管理員參與和/或投資。 自動語音應答是管理員導向的遷移;您必須在雲端自動語音應答雲端服務中重新建立現有的 ExchUMO 自動語音應答樹。 使用任何 ExchUMO 功能搭配協力廠商 PBX 的客戶，將不會遷移到 Skype 雲端服務，因為它們不支援協力廠商 PBX 系統。 在 [此博客](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)中已宣告協力廠商支援的退休計畫，而且此部署模型中的客戶可以將他們的使用者遷移至 Microsoft 的整合通訊平臺/服務之一，或為這些使用者取得協力廠商的語音信箱和/或自動語音應答解決方案。 雲端式服務不支援傳真整合;客戶將需要遷移至協力廠商解決方案。

## <a name="who-is-affected"></a>受影響的人員

使用來自 Exchange 整合通訊線上服務之下列任何功能的客戶都會受到影響：

- 語音信箱服務
- 自動語音應答服務
- 通話佇列服務
- 傳真整合

> [!Note]
> 使用任何 Exchange Server 內部部署與整合通訊的客戶都不會受到影響。

深入瞭解使用者與系統管理員經驗對 [使用者經驗](#user-experience-impact)的影響。

## <a name="migration-plan-overview"></a>遷移計畫概述

Microsoft 已識別出使用 ExchUMO 之功能的各種客戶部署，將會根據下列計畫來協助客戶進行遷移。

|客戶群組 |時間表  |詳細資料  |
|---------|---------|---------|
|準備好遷移的客戶<br><br>要遷移的功能：<br><ul><li>語音信箱</ul>   |   三月份--2019 年5月  |範例：<ul><li>    具有簡單語音信箱部署和使用狀況的客戶<li>已為 Microsoft 建立所有需求，以執行遷移的客戶<ul>|
|具有必要條件的客戶<br><br>要遷移的功能：<br><ul><li>語音信箱<li>自動語音應答<li>通話佇列</ul> |  可能-12 月2019 |範例： <br><ul><li>混合式設定未完成<li>不會設定混合 PSTN 號碼</ul>|
|需要系統管理員參與 & 客戶投資的客戶<br><br>要遷移的功能：<ul><li>語音 信箱<li>自動語音應答<li>通話佇列<li>傳真整合</ul>| 2020年2月  | 範例： <br><ul><li>ExchUMO 服務是由協力廠商 PBX 所使用<li>具有 PSTN 訂閱者存取需求的客戶<li>SFB 2010 (的客戶不支援) <li>傳真整合</ul> |

## <a name="voicemail-migration-guidelines"></a>語音信箱遷移指導方針

### <a name="get-informed"></a>取得通知

您可以熟悉 [博客宣告](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) 和本文，為您的使用者規劃順利遷移。 如需電話語音語音信箱功能的詳細資訊，請參閱 [查看商務用 Skype 語音信箱和選項](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) 。  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>建立商務用 Skype 混合式拓撲

如果您未建立商務用 Skype 混合式拓撲，您必須執行該動作才能啟用語音信箱使用者的平滑遷移。 如需詳細資訊，請參閱 [設定商務用 Skype 混合](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) 。

> [!Note]
> 您不需要在線上語音信箱服務遷移時遷移您的使用者。 不過，若要讓內部部署使用者利用電話語音語音信箱服務，必須建立混合式拓撲。

### <a name="plan-your-auto-attendant-migration"></a>規劃您的自動語音應答遷移

系統管理員可以隨時開始將其自動語音應答從 ExchUMO 遷移至雲端自動語音應答。 如需詳細資訊，請參閱 [設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 語音應答。

Microsoft 繼續提供額外的自動語音應答功能，讓客戶可能會考慮他們的遷移所需的功能。 管理員應該據此評估功能集和遷移其自動語音應答實例。 如需功能清單比較，請參閱 [ExchUMO 和 Azure 雲端架構服務功能矩陣](#exchumo-and-azure-cloud-based-services-feature-matrix)。

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>規劃您的語音信箱後續遷移驗證和測試

語音信箱遷移是指 Microsoft 所導向。 系統管理員不需要執行任何動作，前提是已建立必要條件混合式拓撲。 Microsoft 會執行必要的驗證和測試，確保使用者的語音信箱遷移未中斷。 系統管理員可以在他們的一面執行測試及驗證。 請參閱建議的 [測試計劃與系統管理員的遷移後驗證，](#suggested-test-plan-and-post-migration-validation-for-admins) 以取得建議的測試計劃。

> [!Note]
> 不支援 Lync Server 2010。 如果您在2010伺服器部署中，您應該規劃伺服器升級，或考慮將使用者遷移至 Microsoft 團隊或商務用 Skype Online。  

### <a name="monitor-the-admin-notification-center"></a>監視系統管理員通知中心

請在系統管理員通知中心觀看有關使用者遷移的詳細資料和時程表。 在遷移期間內，至少會傳送30天的通知。

> [!Note]
> 如果您接收到使用者的「遷移」時程表的通知，而且想要推遲您的遷移以滿足業務關鍵型原因，您可以聯繫 Microsoft 支援人員來執行此動作。 您無法將遷移推遲超過2月28日（2020）的退休日期。 針對可能有其他問題的客戶，請與您的帳戶小組或 Microsoft 支援人員聯繫。 已使用 Microsoft 365 或 Office 365 的客戶可以透過 Microsoft 365 系統管理中心提交支援案例。

### <a name="consider-opting-in-for-a-planned-migration"></a>考慮在規劃的遷移中使用的退出

您可以加入宣告規劃的語音信箱服務遷移至 CVM。 在 [加入] 中，請參閱本文的詳細資料，尤其是下列各節：

-  (此區段的遷移步驟) 
- ExchUMO 和 Azure 雲端式服務功能矩陣
- 使用者經驗影響

當您選擇受管理的遷移時，您將不會收到 Microsoft 365 系統管理入口網站訊息中心的預先遷移30天通知。

若要加入宣告計畫的遷移，請從系統管理員的電子郵件地址將電子郵件要求傳送至 [cvm@microsoft.com](mailto:cvm@microsoft.com) ，並提供下列資訊：

- 建議的日期 (週二) ：每週二執行遷移聲波。 請選取不超過12/3/2019 的星期二的日期。
 
- 承租人 ID:32 個字元，格式為 0046728c-688a-4472-a38f-098fec60ac6x。 您可以在 Azure AD 底下的 Microsoft 365 系統管理員入口網站中，或使用下列 PowerShell Cmdlet 找到您的租使用者識別碼： `Get-CsTenant | Select ObjectId`

當租使用者成功遷移後，您將會收到一封電子郵件確認。

## <a name="auto-attendant-migration-guidelines"></a>自動語音應答遷移指導方針

Microsoft 365 和 Office 365 組織管理員必須在 Microsoft 雲端自動語音應答服務中重新建立 Exchange UM 線上自動語音應答2020，並在 Exchange UMO 服務退休日的 Exchange 服務退休之前切換其內部部署電話號碼。 若要成功遷移和測試新的雲端自動語音應答，建議使用這種指導方針。 如果您有大量的自動語音應答，您可以使用 [EXCHANGE UM 自動](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) 語音應答加入雲端自動語音應答遷移腳本，以簡化自動語音應答的大量遷移。

### <a name="auto-attendant-setup"></a>自動語音應答設定

我們強烈建議您儘早開始設定新的自動語音應答，以避免過去分鐘的問題，並熟悉雲端自動語音應答服務的功能和經驗。 針對需要一或多個間隙功能的自動語音應答，您可以在有可用的缺口功能準備部署時，建立並測試自動語音應答。 如需差距功能的相關資訊，請參閱 [附錄](#appendix)。

1. 使用 Exchange UMO Cmdlet，使用 [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant)來匯出現有自動語音應答的設定。  
2. 在 Exchange Online PowerShell 中使用 [export-import-umprompt 指令程式](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) 來匯出問候語媒體檔案 (如果使用) 並將其轉換成 mp3 格式。
3. 遵循 [規劃雲端自動](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) 語音應答中的指示，並 [設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) 語音應答，以使用 Microsoft 團隊系統管理中心或 Powershell 建立自動語音應答。
4. 若功能表選項變更，請複查您的問候語。
5. 使用本文的「 [已知問題](#known-issues) 」區段中的「自動語音應答來電轉接至 PSTN」解決方法，設定傳送至回應群組。  
6. 在內部撥打或指派測試電話號碼，以測試新的自動語音應答。  

### <a name="cutover"></a>系統轉換

1. 將您的電話號碼從 Exchange UMO 自動語音應答切換至新的自動語音應答。
2. 將 SIP URI 從 contact 物件移至資源帳戶。
3. 使用新指派的電話號碼來測試及驗證自動語音應答。

## <a name="appendix"></a>附錄

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>ExchUMO 和 Azure 雲端式服務功能矩陣

| 服務 | 功能層級 | 功能 | 附註  | 雲端 VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| Vm  | 服務功能| 支援協力廠商 PBX    | 包括協力廠商 PBX 所提供的所有功能，例如 MWI (訊息等待指示器) 使用來自 Exchange UM Online 的 SIP 通知訊息 | N   | Y    |
| Vm | 服務功能  | 支援商務用 Skype Server   |  | Y | Y    |
| Vm | 服務功能 | 支援 Microsoft 團隊|  | Y | N    |
| Vm | 服務功能 | eDiscovery 和保留  | 出於安全性和合規性  | Y | Y    |
| Vm | 服務功能 | Exchange 規則支援 | 出於安全性和合規性  | Y | Y    |
| Vm | 使用者功能 | PSTN 撥入式存取  | 使用者存取  | N | Y    |
| Vm | 使用者功能 | 委託  | 未接來電電子郵件  | N | Y    |
| Vm | 使用者功能 | PSTN Outlook 語音存取   | 使用者存取  | N | Y    |
| Vm | 使用者功能 | 使用已驗證端點撥入 | 呼叫語音信箱服務收聽語音訊息及變更語音信箱設定| Y | Y    |
| Vm | 使用者功能 | 停用語音信箱的使用者設定   |  | Y | Y    |
| Vm | 使用者功能 | 變更個人問候語的使用者設定  |  | Y | Y    |
| Vm | 使用者功能 | 建立 OOF 問候語的使用者設定  |  | Y | Y    |
| Vm | 使用者功能 | 變更預設語言的使用者設定  |  | Y | Y    |
| Vm | 使用者功能 | 使用 TTS 覆寫預設問候語的使用者設定  |  | Y | N    |
| Vm | 使用者功能 | 記錄個人問候語 (已驗證裝置)  |  | Y | Y    |
| Vm | 使用者功能 | 在電話上播放 (PSTN) 上錄製個人問候語（play） |  | N | Y    |
| Vm | 使用者功能 | 停用的使用者設定 |  | N | Y    |
| Vm | 使用者功能 | 謄寫  |  | Y | Y    |
| Vm | 使用者功能 | MWI (郵件等候指示器) 使用 SIP 通知訊息 |  | N | Y    |
| Vm | 使用者功能 | Outlook 中 MP3 音訊檔案格式    |  | Y | Y    |
| Vm | 使用者功能 | 變速播放控制 |  | Y | Y    |
| Vm | 使用者功能 | 轉寄語音信箱  | 將收到的語音信箱轉寄給其他使用者 | Y | Y    |
| Vm | 使用者功能 | 傳送語音訊息給使用者群組  |語音信箱廣播   | N | Y   |
| Vm | 使用者功能 | 使用 SMS 的語音信箱通知    | 當使用者有新的語音信箱時，可以接收短信    | N | Y    |
| Vm | 使用者功能 | 支援的問候語語言 | 詳細資料： https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| Vm | 使用者功能 | 自動答錄規則 |  | Y | Y    |
| Vm | 使用者功能 | 在電話上播放 (PSTN) -播放郵件 | 在我的儲存格呼叫我收聽語音訊息  | N | Y    |
| Vm | 使用者功能 | 在電話上播放 (Auth) -播放郵件 | 在我的已驗證裝置上呼叫我  | Y | Y    |
| Vm | 使用者功能 | 多個使用者間的共用信箱 |  | Y | Y    |
| Vm | 來電者功能  | 來電者體驗-受保護的語音信箱 | 來電者可以選擇將錄製的郵件標記為受保護的選項| N | Y    |
| Vm | 來電者功能  | 來電者體驗-私人語音信箱 | 來電者可以選擇將錄製的郵件標記為私人的選項  | N | Y    |
| Vm | 來電者功能  | 靜音偵測   |  | N | Y    |
| Vm | 租使用者-系統管理功能 | 伺服器層級的受保護語音信箱    | 租使用者-系統管理員可以設定服務層級規則，將輸入的語音信箱標記為受保護 | Y | Y    |
| Vm | 租使用者-系統管理功能 | 變更錄製持續時間限制  |     | Y | Y    |
| Vm | 租使用者-系統管理功能 | 變更靜音偵測超時    |  | 不適用    | Y    |
| Vm | 租使用者-系統管理功能 | 變更輸入失敗的次數 | CVM：硬編碼為3 | N | Y    |
| Vm | 租使用者-系統管理功能 | 變更預設語言 |  | Y | Y    |
| Vm | 租使用者-系統管理功能 | 停用/啟用功能 |  | Y | Y    |
| Vm | 租使用者-系統管理功能 | 停用/啟用未接來電通知 |  | N | Y    |
| Vm | 租使用者-系統管理功能 | 協助 Microsoft 改善語音信箱預覽   這些選項可讓 Microsoft 改善語音信箱預覽的品質。    |  | Y | Y    |
| Vm | 租使用者-系統管理功能 | 自訂已啟用使用者的文字訊息|  | 不適用    | Y    |
| Vm | 租使用者-系統管理功能 | 應對猥褻遮罩|  | Y | N    |
| Vm | 租使用者-系統管理功能 | 語音信箱原則    |   | Y | Y    |
| Vm | 租使用者-系統管理功能 | 網頁入口網站管理   |  | CY19   | Y    |
| Vm | 租使用者-系統管理功能 | PowerShell   |  | Y | Y    |
| UM | 使用者功能 | 商務用 Skype 已驗證電話上的訊息等待指示器 (MWI)    |可由電話合作夥伴提供  | 否 | 是    |
| 機 管 局 | 服務功能 | AA 支援協力廠商 PBX    |  | N | Y    |
| 機 管 局 | 服務功能 | 支援商務用 Skype Server   |  | Y | Y    |
| 機 管 局 | 服務功能 | 支援 Microsoft 團隊|  | Y | N    |
| 機 管 局 | 服務功能 | 依名稱撥號，DTMF 輸入    |  | Y | Y    |
| 機 管 局 | 服務功能 | 依名稱撥號、語音輸入  |  | Y | Y    |
| 機 管 局 | 服務功能 | 多語言支援 | 此處為語言詳細資料： https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| 機 管 局 | 服務功能 | 轉接至操作員、CQ 或使用者 |  | Y | Y    |
| 機 管 局 | 服務功能 | 在內部 RNL)  (轉接至 PSTN 號碼  |  | Y | Y    |
| 機 管 局 | 服務功能 | 從外部轉接至 PSTN 號碼  |  | 請參閱下列的已知問題一節 | Y    |
| 機 管 局 | 服務功能 | 營業時間 |  | Y | Y    |
| 機 管 局 | 服務功能 | 功能表選項 | IVR 功能表選項  | Y | Y    |
| 機 管 局 | 服務功能 | 將雲端 PSTN 號碼指派給 AA |  | Y | N    |
| 機 管 局 | 服務功能 | 將部署 PSTN 號碼指派給 AA  |  | Y | Y    |
| 機 管 局 | 服務功能 | 自訂使用者選取範圍  | 讓來電者能夠接觸自訂的組織使用者清單| Y | Y    |
| 機 管 局 | 服務功能 | 下班後和假日處理  |  | Y | Y    |
| 機 管 局 | 服務功能 | 使用文字語音轉換的自訂問候語  |  | Y | Y    |
| 機 管 局 | 服務功能 | 分機撥號   | 撥打使用者的分機號碼來抵達使用者  | Y   | Y    |
| 機 管 局 | 服務功能 | 用於 AA 來電者留下訊息的信箱    |  | Y   | Y    |
| 機 管 局 | 服務功能 | 將多個 PSTN 號碼指派給 AA|  | Y | Y    |
| 機 管 局 | 租使用者-系統管理功能 | 網頁入口網站管理   |  | Y | N    |
| 機 管 局 | 租使用者-系統管理功能 | PowerShell Cmdlet  |  | Y | Y    |
| 傳真| 服務功能 | 傳真整合|  | N | Y    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>建議的測試計劃與系統管理員的遷移後驗證

若要驗證您的使用者是否已遷移至雲端語音信箱，請將語音信箱保留給使用者，並在 Outlook 中查看郵件內文。 雲端語音信箱訊息的頁尾是讀取：

「謝謝您使用「！」 如果您沒有看到上述的記錄，則這是因為音訊品質不夠清晰，無法 transcribe。」

當您已遷移使用者之後測試語音信箱功能時，請務必考慮下列案例：

- 驗證組織中所有端點類型的語音信箱存取，例如應用程式和 IP 電話。
- 使用範例使用者驗證已設定的個人化問候語會向來電者播放。
- 如果您的組織具備停用使用者功能的法律或法規遵從性需求，請確定已停用遷移後停用。 如需詳細資訊，請參閱 [設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail)。
- 如果您先前已設定 Exchange VM 原則和規則，請確定它們有效。
- 熟悉雲端語音信箱服務 PowerShell Cmdlet，以變更使用者設定。  

### <a name="user-experience-impact"></a>使用者經驗影響

以下是使用者語音信箱遷移經驗的概述。


|功能  |使用者經驗中的變更|
|---------|---------|
|電子郵件通知 | 不變更<br>不會傳送電子郵件給使用者，通知他們有關語音信箱帳戶啟用/遷移的資訊。 |
|存取舊版郵件 | 不變更<br>使用者可以在所有支援的端點中存取先前的語音信箱訊息。 |
|在 outlook 中接收 VM，SFB 應用程式| 不變更<br>使用者會繼續在所有支援的端點中收到其語音信箱訊息。 |
|謄寫 | 增強<br>CVM 方式的精確度率和支援的語言遠遠高於 ExchUMO。 |
|使用者設定 | 新的經驗<br>使用者可以從使用者設定入口網站 (USP) 變更其偏好。 使用者可以從其語音信箱電子郵件中的超連結，或其 SFB 用戶端上的使用者設定按鈕，存取其 USP; https://aka.ms/vmsettings.
 |功能| 如需詳細資訊，請參閱功能設定比較。 |
|VM 郵件的 Outlook 規則 | 不變更<br>先前建立的規則會在遷移之後套用至 CVM 郵件。
 |

### <a name="user-management-and-provisioning-in-cvm"></a>CVM 中的使用者管理與布建

建立時，會自動為雲端語音布布建新的商務用 Skype 使用者。 布建新的語音信箱使用者，不需要額外的系統管理員工作或授權。 請參閱 [設定雲端語音信箱](/microsoftteams/set-up-phone-system-voicemail) 以瞭解現有和新使用者的原則管理。

### <a name="admin-auto-attendant-management-experience"></a>系統管理員自動語音應答管理經驗

若要深入瞭解自動語音應答，請參閱 [設定雲端自動](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant)語音應答。

### <a name="known-issues"></a>已知問題

#### <a name="greeting-inconsistencies"></a>問候語不一致

訂閱者存取可能持續用於您的承租人，直到服務完全淘汰為止，即使所有的使用者都已遷移至雲端語音信箱也是一樣。 為了避免使用者混淆和不一致的體驗，請停用訂閱者存取，因為在遷移之後問候語會變更。 若要這麼做，請使用來移除每一位訂閱者存取行的 EXUM 連絡人 `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` 。

#### <a name="auto-attendant-call-transfer-to-pstn"></a>自動語音應答來電轉接至 PSTN

若要透過商務用 Skype server 或回應群組服務 (RGS) 在商務用 Skype Server 上，將自動語音應答來電轉接至外部 PSTN 電話號碼，請建立新的內部部署使用者與來電轉接設定為 PSTN 電話號碼或 RGS 電話號碼。 使用者必須啟用並正確地設定 Enterprise Voice，並已指派語音原則。

#### <a name="shared-mailbox-is-still-accessible"></a>仍然可以存取共用信箱

在遷移至 CVM 後，使用 Exchange UM Online 設定的共用信箱繼續接收郵件，而且可透過 Outlook 存取使用者。 不過，當您將這些信箱的存取權轉移至 CVM 後，就無法使用此存取權變更這些信箱的問候語郵件。 使用共用信箱（用來捕獲自動語音應答來電者）的客戶應在發行 (ETA 2019 年10月) 時，利用自動語音應答及通話佇列共用信箱功能。
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>「使用者名稱未使用商務用 Skype」橫幅顯示

CVM 服務是以 Microsoft 團隊基礎結構為基礎，而商務用 Skype 用戶端的呼叫可能會在用戶端上顯示資訊橫幅，以讀取：「使用者未使用商務用 Skype。 若要取得更豐富的體驗，請切換至 [小組] 或 [啟動 Skype 會議]。
請務必將使用者的商務用 Skype 用戶端更新為最新的 C2R 用戶端更新，以避免出現這種旗標。
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>「設定語音信箱」會帶您前往 OWA

在遷移至 CVM 後，按一下用戶端的 [ **設定語音信箱** ] 將繼續進行商務用 Skype Server 2015/2013 客戶前往 Office Web ACCESS (OWA) 入口網頁。 已從 OWA 的 [語音信箱] 索引標籤中移除所有設定，而且橫幅會以重新導向連結顯示，以將使用者帶至 CVM 使用者設定入口網站。

#### <a name="changing-greeting-remotely"></a>以遠端方式變更問候語

CVM 中不支援 PSTN 訂戶存取。 針對需要以遠端方式變更其問候語的使用者，「變更您的問候語」功能表選項已新增至行動用戶端的語音信箱 IVR 服務。 使用者可以在行動用戶端的撥號墊上按下並按住 "1" 鍵來呼叫此服務。
