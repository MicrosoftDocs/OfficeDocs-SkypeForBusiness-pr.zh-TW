---
title: 安全性和合規性概觀
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Microsoft Teams 安全性和合規性功能概觀，包括隱私權和加密、稽核與報告等。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 36cb67dc73177678206e5d5865ba145414ae37a9
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836920"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性和合規性

> [!IMPORTANT]
> 若要瞭解如何在 **COVID-19** 疫情期間，以最佳方式確保每個人在家工作時的安全性，請閱讀以下文章：
>  - [安全性團隊支援在家工作最常見的 12 項工作](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分割通道最佳化遠端使用者的 Microsoft 365 或 Office 365 連線能力](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新日期：2020 年 4 月 2 日 [：Teams 安全性指南](teams-security-guide.md)


Microsoft Teams 是建在 Microsoft 365 和 Office 365 超大規模企業級雲端上，提供客戶預期進位的安全性與合規性功能。 若要在 Microsoft 365 或 Office 365 中[](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)規劃安全性詳細資訊，安全性藍圖是一個很好的起點。 有關在 Microsoft 365 或 Office 365 中規劃合規性詳細資訊，您可以從安全性與合規性規劃 [&開始](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)。


本文將提供有關 Teams 特定安全性與合規性的進一步資訊。 千萬不要錯過以下有關安全性與合規性的 Microsoft 技術員影片：

- [Microsoft Teams IT 基本功能： (](https://youtu.be/91lHNKVVvQ4) 12：42 分鐘) 
- [Microsoft Teams 安全性與合規性控制措施](https://www.youtube.com/watch?v=Km4T4hMM__k) (10：54 分鐘) 

> [!IMPORTANT]
> 做為 Microsoft 365 或 Office 365 的客戶，您擁有並控制您的資料。 除了提供您訂閱的服務外，Microsoft 不會將您的資料用於其他用途。 作為服務提供者，我們不會掃描您的電子郵件、檔或小組，以用於廣告或與服務不相關的用途。 Microsoft 沒有上傳內容的存取權限。 與 Microsoft 365 中的 OneDrive 和 SharePoint 一樣，客戶資料會保留在租使用者內。 您可以在 Microsoft 信任中心查看我們的信任和安全性 [相關資訊](https://microsoft.com/trustcenter)。 Teams 遵循與 Microsoft 信任中心相同的指引和原則。

## <a name="security"></a>安全性

Teams 會強制執行全小組和全組織的雙因素驗證、透過 Active Directory 單一登入，以及傳輸中和靜態資料加密。 檔案會儲存在 SharePoint 中，並受到 SharePoint 加密的支援。 筆記會儲存在 OneNote 中，並受到 OneNote 加密的支援。 OneNote 資料會儲存在小組 SharePoint 網站中。 Wiki 定位停駐點也可以用來記錄筆記，其內容也會儲存在小組 SharePoint 網站中。

請閱讀[身分識別模型和驗證](identify-models-authentication.md)以深入瞭解驗證和 Teams，以及[](sign-in-teams.md)新式驗證如何運作，尤其有助於新式驗證。

由於 Teams 與 SharePoint、OneNote、Exchange 等專案共同合作，因此您應該很習慣在 Microsoft 365 或 Office 365 中全面管理安全性。 若要深入瞭解，請參閱 [如何設定您的 Microsoft 365 或 Office 365 組織，以提升安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前 [，私人頻道](private-channels.md) 支援有限的安全性和合規性功能。 即將推出私人頻道中完整組的安全性與合規性功能支援。

### <a name="advanced-threat-protection-atp"></a>ATP (進) 

Microsoft Teams (ATP) 提供進一步的威脅防護功能，以及 SharePoint 和 OneDrive，這些應用程式與 Teams 整合進行內容管理。 ATP 可讓您判斷這些應用程式中的內容是否具有惡意性質，並封鎖此內容以禁止使用者存取。

偵測後，受影響的內容管理方式，會視您于 Microsoft 365 或 Office 365 中選取的設定而決定。 我們強烈建議您在設定 ATP 時考慮所有應用程式，若要進一步閱讀 [，SharePoint、OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 和 Microsoft Teams 的 ATP 將會提供如何開始使用的詳細資訊。

### <a name="safe-links"></a>安全連結

雖然 Microsoft Teams 目前無法提供進一步威脅防護 (ATP) 安全連結，但現在透過我們的技術採用計畫[](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) (TAP) 公開預覽，而尚未設定一般可用性的發行日期，我們將在該時間到達時更新本文。 同時，如需 Microsoft 365 或 Office 365 安全連結的資訊，請參閱 [ATP 安全連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 ATP 安全連結可在 ATP 方案 1 和 [ATP 方案 2 中提供](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)。

### <a name="safe-attachments"></a>安全附件

安全附件是一項設計來檢查及偵測惡意附件，以增強使用者安全性的功能。 全域或安全性系統管理員會建立處理[](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)這些可疑惡意附件的策略，以防止這些可疑的惡意附件被送出給使用者、按一下附件及採取行動。 SharePoint、OneDrive 和 Microsoft Teams 可以使用安全附件保護，而 Microsoft 365 或 Office 365 進位威脅防護方案 1 和 [2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) 則具備此功能。 閱讀更多有關安全附件的資訊，以及這些附件如何協助保護貴組織在 [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)中的安全附件。

### <a name="secure-score"></a>安全分數

Microsoft Secure Score 是組織安全性狀態度量單位，數位越高，表示已採取更多改進動作。 您可以在 [Microsoft 365 安全性中心找到它](https://security.microsoft.com/securescore)。 遵循安全分數建議可保護貴組織不受威脅。 從 Microsoft 365 安全性中心的集中式儀表板，組織可以監控及處理其 Microsoft 365 身分、應用程式和裝置的安全性。 Microsoft Teams 現在有關于安全分數的建議，並鼓勵系統管理員監控他們在平臺上的安全性。

安全分數可協助組織：
- 報告組織安全性狀態目前的狀態。
- 提供可探索性、可見度、指引及控制，以改善其安全性狀態。
- 比較基準並建立 KPI (關鍵) 。


### <a name="how-conditional-access-policies-work-for-teams"></a>條件式 Access 政策如何適用于 Teams

Microsoft Teams 非常仰賴 Exchange Online、SharePoint 和商務用 Skype Online 來核心生產力案例，例如會議、日曆、交互操作聊天和檔案共用。 當使用者在任何用戶端上直接登錄 Microsoft Teams 時，針對這些雲端應用程式所設定的條件式存取原則會套用至 Microsoft Teams。

Microsoft Teams 在 Azure Active Directory 條件式存取策略中以雲端應用程式個別支援。 為 Microsoft Teams 雲端應用程式所設定的條件式存取原則會套用至 Microsoft Teams，當使用者登錄時。 不過，若沒有 Exchange Online 和 SharePoint 等其他應用程式的正確政策，使用者可能仍可以直接存取這些資源。 有關在 Azure 入口網站中設定條件式存取策略的資訊，請參閱 [Azure Active Directory 快速入門](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

Windows 和 Mac 版 Microsoft Teams 桌面用戶端支援新式驗證。 新式驗證會根據 Azure Active Directory 驗證庫和 ADAL (ADAL) 跨平臺的 Microsoft Office 用戶端應用程式進行登錄。

Microsoft Teams 桌面應用程式支援 AppLocker。  如需有關 AppLocker 先決條件的資訊，請參閱：使用 [AppLocker 的需求](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

## <a name="compliance"></a>合規性

Teams 提供豐富的資訊，可協助您處理合規性領域，包括頻道、聊天和附件的通訊合規性、保留政策、資料遺失防護 (DLP) 、頻道、聊天和檔案的 eDiscovery 和法律保留、稽核記錄搜尋，以及 Microsoft Intune 的行動應用程式管理。 我們在下面提供所有這些主題的一些資訊，您可以前往 [Microsoft 365](https://compliance.microsoft.com) 合規性中心管理這些設定。

### <a name="information-barriers"></a>資訊障礙

資訊障礙是由 Teams 系統管理員所套用，以執行一些操作，例如禁止人員或群組彼此通訊 (當他們不需要進行此作業時 (或法規理由禁止他們這麼做) ，它也可讓您設定與) 下方涵蓋的尋找和 eDiscovery (等相關政策。 這些策略可能會影響 1：1 聊天、群組聊天或小組層級的使用者。 資訊隔層功能可在公用雲端使用，自 2021 年 1 月開始已推出至 GCC 雲端。

若要進一步閱讀本主題，請前往 [Microsoft Teams 的資訊障礙](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通訊合規性

Microsoft 365 中的通訊合規性可讓您將使用者新加入範圍內政策，這些策略可針對 Microsoft Teams 通訊檢查攻擊性語言、敏感性資訊，以及與內部及法規標準相關的資訊。 您可以掃描公用和私人 Teams 頻道中的聊天通訊和相關附件、個別聊天和附件，協助將貴組織的通訊風險降到最低。 若要進一步瞭解如何設定策略，協助偵測、捕獲不當 Teams 通訊並採取行動，請參閱 [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)中的通訊合規性。

### <a name="retention-policies"></a>保留原則

Microsoft Teams 中的保留政策可讓您同時保留貴組織為法規、法律、商務或其他原因保留的重要資料，以及移除與保留不相關的內容和通訊。 您也可以使用保留原則將資料保留一段時間，然後將其刪除。 如需要詳細資訊，請參閱 [Microsoft Teams 中的保留政策](retention-policies.md)。

## <a name="sensitivity-labels"></a>敏感度標籤

使用 [敏感度標籤](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) ，以保護及規範在團隊內共同合作期間所建立之機密組織內容的存取權。 例如，請用標籤來設定 (或) 的隱私權、控制來賓存取和外部共用，以及管理來自未管理裝置的存取權限。 如需要詳細資訊，請參閱 [Microsoft Teams 中的敏感度標籤](sensitivity-labels.md)。

### <a name="data-loss-prevention-dlp"></a>DLP (資料外) 

Microsoft Teams (DLP) 中的資料外遺失防護，以及 Microsoft 365 或 Office 365 的更大 DLP 案例，都圍繞著保護機密檔與資料的商務準備狀態。 無論您對郵件或檔中的敏感性資訊有疑慮，DLP 政策都能協助確保您的使用者不會與錯誤人員共用此機密資料。

如需 Teams 中資料外遺失防護的資訊，請參閱 [Microsoft Teams 的 DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)。 適用于 O365 DLP 疑慮的一篇好文章是 [資料外遺失防護概觀](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>電子文件探索

電子探索或電子檔探索是識別、收集及產生電子儲存的資訊 (ESI) 以回應訴訟或調查之生產要求的電子層面。 功能包括案例管理、保留、搜尋、分析及匯出 Teams 資料。 這包括聊天、傳訊和檔案、會議與通話摘要。 針對 Teams 會議和通話，會建立會議與通話中事件發生的摘要，並可在 eDiscovery 中取得。

如需如何在安全性中心與合規性中心執行 Microsoft 365 或 Office 365 電子檔探索，以及針對 Teams 內容執行合規性內容搜尋的詳細資訊，請前往下列連結：

 - [電子文件探索](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

我們有一篇 Teams 專用文章，以進一瞭解更多資訊 [，例如來賓對來賓聊天的 eDiscovery](eDiscovery-investigation.md)。

客戶可以根據需求運用[eDiscovery 或 Advanced eDiscovery。](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) 下表概述兩者之間的差異：

| |電子文件探索  |進一版電子資料探索  |
|---------|---------|---------|
|案例管理     |X        |X         |
|存取控制  |X         |X         |
|內容搜尋     |X         | X        |
|按住 ()    |X         | X        |
|出口     |X         |X         |
|重複偵測     |-         |X         |
|使用機器學習進行相關性搜尋    |-         |X         |
|非結構化資料分析      |-         |X         |

### <a name="legal-hold"></a>法律保留

在訴訟期間，您可能需要保留與使用者 (監護) 或小組相關聯的所有資料，以保存為不可變數據，以便做為案件證據。 您可以將使用者置於使用者信箱 (，) 將小組置於法律保留狀態。 對於團隊法律保留，團隊的信箱可以置於下列保留狀態：

- In-Place透過 (查詢或篩選的內容，將信箱或網站集合的子集保留) 保留，或
- 訴訟 (將保留整個信箱或網站集合) 。

在這兩種情況下，一旦設定保留狀態，可確保即使使用者刪除或編輯群組信箱中的頻道訊息，該內容的不可變複本仍維持不變，並透過 eDiscovery 搜尋提供。 法律保留通常適用于電子檔探索案例。

請參閱 [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 概觀，以進一瞭解 Microsoft 365 合規性中心的保留與保留。 如需有關法律保留的 Teams 特定資訊，我們也會將 [Microsoft Teams](legal-hold.md) 使用者或小組擱置在法律上，以深入瞭解。

### <a name="compliance-content-search"></a>合規性內容搜尋

內容搜尋可用來透過豐富的篩選功能搜尋所有 Teams 資料。 產生的資料可以匯出至特定容器，以用於合規性和訴訟支援。 您可以執行此作業，也可以不使用 eDiscovery 案例。 這可讓合規性系統管理員收集所有使用者的 Teams 資料，並檢查並匯出這些資料，以便進一步處理。 請參閱內容 [搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search) 以深入瞭解如何在 Microsoft 365 合規性中心針對 Microsoft Teams 和其他 Microsoft 365 或 Office 365 內容執行合規性內容搜尋。

> [!TIP]
> 使用內容搜尋，您視需要只能篩選到 Microsoft Teams 的內容，例如聊天和頻道訊息、會議和通話。

如果您想要進一步提供有關內容搜尋的 Teams 特定資訊，請參閱 [Microsoft Teams 中的內容搜尋](content-search.md)。

### <a name="auditing-and-reporting"></a>稽核與報告

稽核記錄搜尋功能會直接插入 Microsoft 365 合規性中心，並允許您在無限制的稽核時程表中匯出特定工作負載或一般事件集供系統管理員使用和調查，讓您設定警示，以及報告稽核事件。 您可以在 Microsoft 365 合規性中心內設定所有稽核記錄資料的警示，並篩選及匯出這些資料以進一步分析。 請參閱搜尋 [稽核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 以深入瞭解如何執行 Microsoft 365 或 Office 365 的稽核記錄搜尋。 若要深入瞭解在 Microsoft 365 合規性中心搜尋 Microsoft Teams 事件，我們也會在 [Teams](audit-log-events.md) 中開啟稽核功能，供您查看。

## <a name="customer-key"></a>客戶金鑰

Microsoft 365 在內容的服務加密外，還提供額外的加密層。 使用您提供的金鑰，Customer Key 會加密 Microsoft Teams 中的數種不同類型的資料。 在應用程式層級使用 Customer Key，Customer Key 會加密儲存在 SharePoint Online 中的 Teams 檔案。 詳細資訊，請參閱使用 [Customer Key 進行服務加密](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)。 

在租使用者層級使用客戶金鑰時，Customer Key 會加密：
- 團隊聊天訊息 (1：1 聊天、群組聊天、會議聊天，以及頻道交談) 
- Teams 媒體訊息 (影像、程式碼段、影片和 Wiki 影像) 
- 儲存在 Teams 儲存空間的 Teams 通話和會議錄製
- Teams 聊天通知
- Cortana 的 Teams 聊天建議
- Teams 狀態訊息：詳細資訊，請參閱租使用者層級 [的 Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) 客戶金鑰概觀，並閱讀涵蓋 [Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)客戶金鑰支援的 Microsoft Teams 部落格，現已在公開預覽版中。 若要瞭解包含租使用者層級客戶金鑰的 Microsoft 資訊保護版本，請參閱宣告新的 Microsoft 資訊保護功能，以知道並保護您的 [機密資料](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

## <a name="privacy"></a>隱私權

在 Microsoft，保護您的資料是我們的最高優先順序。 若要瞭解我們的隱私權作法，請閱讀：  

- [Microsoft 隱私權](https://www.microsoft.com/trust-center/privacy)
- [我們對 Microsoft Teams 隱私權和安全性的承諾](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [適用于 IT 專業人員：Microsoft Teams 中的隱私權和安全性](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>資訊保護架構

下圖指出 Teams 資料的接收流程至 Exchange 和 SharePoint for Teams 檔案和郵件。

> [!div class="mx-imgBorder"]
> ![Teams 資料至 Exchange 和 SharePoint 工作流程圖表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下圖指出 Teams 會議與通話資料匯至 Exchange 的匯算流程。

> [!div class="mx-imgBorder"]
> ![Teams 會議工作流程圖表，以及將資料呼叫至 Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 探索 Teams 內容最多可能會延遲 24 小時。

## <a name="licensing"></a>授權

當涉及資訊保護功能時，Microsoft 365 訂閱、Office 365 訂閱和相關的獨立授權將決定可用的功能集。

如需決定授權需要為安全性與合規性執行功能的資訊，請參閱安全性與合規性功能的授權需求[](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

> [!NOTE]
> 內容搜尋和 eDiscovery 不需要在安全性與合規性中心&啟用。

## <a name="location-of-data-in-teams"></a>Teams 中的資料位置

Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。 若要查看目前支援哪些地區，請參閱 [Microsoft Teams 中資料的位置](location-of-data-in-teams.md)。

如果您需要查看哪些地區會為租使用者提供資料，請前往 Microsoft [365 系統管理中心](https://portal.office.com/adminportal/home)設定  >    >  **組織設定檔**。 向下捲動到 **資料位置**。

> [!div class="mx-imgBorder"]
> ![系統管理中心中包含 Teams 的資料位置資料表螢幕擷取畫面](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合規性標準

Teams 使用下列標準[：ISO 27001、ISO](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SOC 1 和 SOC 2、HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)和 EU Model [clauses (EUMC) 。](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) [](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech) 在 Microsoft 合規性架構中，Microsoft 將 Microsoft 365 和 Office 365 應用程式和服務分成四個類別。 每個類別是由 Microsoft 365 或 Office 365 服務或相關的 Microsoft 服務所必須符合的特定合規性承諾所定義，並列在該類別中。

詳細資料請參閱資料保護 [資源](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams 也支援雲端安全聯盟合規性。

## <a name="related-topics"></a>相關主題

[Microsoft 365 安全性](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 合規性](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft 合規性方案](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
