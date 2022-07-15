---
title: 安全性與合規性概觀
author: MSFTTracyP
ms.author: tracyp
manager: laurawi
ms.date: 04/12/2022
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Microsoft Teams 安全性與合規性功能的概觀，包括隱私權與加密、稽核和報告等等。
ms.localizationpriority: medium
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
ms.openlocfilehash: c4e31e59992d24aeac190c4f1ffb40d8c3dfef78
ms.sourcegitcommit: 2871c05e00458a0cc76d919ff822b0b354bd1f72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2022
ms.locfileid: "66810065"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft Teams 中的安全性與合規性

> [!IMPORTANT]
> 若要瞭解如何在 **COVID-19 疫情爆發期間確保每個人在家工作時的安全** 性，請閱讀下列文章：
>  - [安全性團隊支援在家工作最常見的 12 項工作](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分割通道最佳化遠端使用者的 Microsoft 365 或 Office 365 連線能力](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 2020 年 4 月 2 日更新： [Teams 安全性指南](teams-security-guide.md)


Microsoft Teams 建置於 Microsoft 365 和Office 365超規模企業級雲端，提供客戶預期的進階安全性和合規性功能。 如需有關在 Microsoft 365 或 Office 365 中規劃安全性的資訊，[安全性藍圖](/microsoft-365/security/office-365-security/security-roadmap)是一個很好的起點。 如需有關在 Microsoft 365 或 Office 365 中規劃合規性的詳細資訊，您可以從[安全性&合規性規劃](/microsoft-365/compliance/plan-for-security-and-compliance)開始。


本文將提供有關 Teams 特定安全性和合規性的進一步資訊。 請勿錯過這些有關安全性與合規性的 Microsoft 技師影片：

- [適用于 IT 的Microsoft Teams 基本版：安全性與合規性](https://youtu.be/91lHNKVVvQ4) (12：42 分鐘) 
- [Microsoft Teams 安全性與合規性控](https://www.youtube.com/watch?v=Km4T4hMM__k) 件 (10：54 分鐘) 

> [!IMPORTANT]
> 身為 Microsoft 365 或 Office 365 的客戶，您擁有並控制您的資料。 除了提供您訂閱的服務之外，Microsoft 不會將您的資料用於其他專案。 身為服務提供者，我們不會掃描您的電子郵件、檔或小組以顯示廣告或是針對與服務無關的用途。 Microsoft 無法存取上傳的內容。 與 Microsoft 365 中的 OneDrive 和 SharePoint 一樣，客戶資料會保留在租使用者內。 您可以在 [Microsoft 信任中心](https://microsoft.com/trustcenter)查看有關我們信任和安全性相關資訊的詳細資訊。 Teams 遵循與 Microsoft 信任中心相同的指導方針和原則。

## <a name="security"></a>安全性

Teams 會強制執行全團隊和整個組織的雙因素驗證、透過 Active Directory 強制執行單一登入，以及透過傳輸和剩餘時間加密資料。 檔案會儲存在 SharePoint 中，並由 SharePoint 加密提供支援。 筆記會儲存在 OneNote 中，並由 OneNote 加密提供支援。 OneNote 資料會儲存在小組 SharePoint 網站中。 Wiki 索引標籤也可以用來記錄筆記，其內容也會儲存在小組 SharePoint 網站中。

閱讀 [身分識別模型和驗證](identify-models-authentication.md) 以深入瞭解驗證和 Teams，以及 [新式驗證的運作方式](sign-in-teams.md) 將特別協助新式驗證。

由於 Teams 能與 SharePoint、OneNote、Exchange 等裝置合作，因此您應該習慣管理 Microsoft 365 中的安全性，或Office 365全面管理。 若要深入瞭解，請參閱[如何設定您的 Microsoft 365 或Office 365組織，提高安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前 [，私人通道](private-channels.md) 支援有限的安全性與合規性功能。 我們即將推出對私人頻道中完整安全性與合規性功能的支援。

### <a name="microsoft-defender-for-office-365"></a>適用於 Office 365 的 Microsoft Defender

適用於 Office 365 的 Microsoft Defender適用于 Microsoft Teams，以及與 Teams 整合以進行內容管理的 SharePoint 和 OneDrive 應用程式。 適用於 Office 365 的 Defender可讓您判斷這些應用程式中的內容是否具有惡意性質，並禁止使用者存取此內容。

在偵測之後如何管理受影響的內容，可在您在 Microsoft 365 或 Office 365 中選取的設定。 我們強烈建議您在設定適用於 Office 365 的 Defender時考慮所有應用程式，如需進一步閱讀，請參閱[安全連結運作方式的概觀，以及設定](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)步驟，以取得開始使用的詳細資訊。

### <a name="safe-links-in-microsoft-teams"></a>Microsoft Teams 中的安全連結

適用於 Office 365 的 Defender Microsoft Teams 中提供安全連結。 若要取得有關何種安全連結以及如何使用此功能的詳細資訊，請閱讀 [Teams 的安全連結設定](/microsoft-365/security/office-365-security/safe-links?view=o365-worldwide)。 適用於 Office 365 的 Defender[方案 1 和方案 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)都有提供安全連結。

### <a name="safe-attachments"></a>安全附件

安全附件是一項設計來加強使用者安全性功能，方法是檢查及偵測惡意附件。 全域或安全性系統管理員 [會開啟此功能](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams?view=o365-worldwide) ，並 [建立](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide) 原則以處理這些可疑的惡意附件，以防止它們傳送給使用者、按一下及執行動作。

安全的附件保護適用于 SharePoint、OneDrive 和 Microsoft Teams，以及[適用於 Office 365 的 Microsoft Defender 方案 1 和方案 2](/microsoft-365/security/office-365-security/overview?view=o365-worldwide)中的 Microsoft 365 或 Office 365。 閱讀 [本文](/microsoft-365/security/office-365-security/set-up-safe-attachments-policies?view=o365-worldwide)深入瞭解安全附件及其如何協助保護您的組織。

### <a name="secure-score"></a>安全分數

Microsoft Secure Score 是組織安全性狀態的度量，較高的數位表示採取的改進動作較多。 您可以在Microsoft 365 安全性中心中[找到。](https://security.microsoft.com/securescore) 遵循安全分數建議可以保護貴組織免于受到威脅。 從Microsoft 365 安全性中心集中式儀表板，組織可以監控及處理其 Microsoft 365 身分識別、應用程式和裝置的安全性。 Microsoft Teams 現在提供關於安全分數的建議，並鼓勵系統管理員監控他們在平臺上的安全性問題。

安全分數可協助組織：
- 報告組織安全性狀態的目前狀態。
- 藉由提供可探索性、可見度、指引和控制，改善其安全性姿勢。
- 比較基準， (KPI) 建立關鍵效能指標。

### <a name="how-conditional-access-policies-work-for-teams"></a>Teams 的條件式存取原則的運作方式

Microsoft Teams 非常仰賴Exchange Online、SharePoint 和 商務用 Skype Online 的核心生產力案例，例如會議、行事曆、聊天室間和檔案共用。 針對這些雲端應用程式設定的條件式存取原則，會在使用者直接登入任何用戶端上的 Microsoft Teams 時套用至 Microsoft Teams。

在 Azure Active Directory 條件式存取原則中，Microsoft Teams 是另行支援的雲端應用程式。 為 Microsoft Teams 雲端應用程式設定的條件式存取原則會在使用者登入時套用至 Microsoft Teams。 不過，如果沒有像是 Exchange Online 和 SharePoint 等其他應用程式的正確原則，使用者仍然可以直接存取這些資源。 如需在 Azure 入口網站 中設定條件式存取原則的詳細資訊，請參閱[Azure Active Directory 快速入門](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

適用于 Windows 和 Mac 的 Microsoft Teams 桌面用戶端支援新式驗證。 新式驗證會根據 Azure Active Directory Authentication Library (ADAL) 登入跨平臺的 Microsoft Office 用戶端應用程式。

Microsoft Teams 桌面應用程式支援 AppLocker。  如需有關 AppLocker 必要條件的詳細資訊，請參閱：使用 [AppLocker 的需求](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

## <a name="compliance"></a>合規性

Teams 提供各種資訊來協助您處理合規性領域，包括頻道、聊天和附件的通訊合規性、保留原則、DLP)  (資料外泄防護、頻道的電子檔探索和法律保留、聊天和檔案、稽核記錄搜尋，以及Microsoft Intune的行動應用程式管理。 我們已提供下列所有主題的一些資訊，您可以移至[Microsoft Purview 合規性入口網站](https://compliance.microsoft.com)來管理這些設定。

### <a name="information-barriers"></a>資訊障礙

Microsoft Purview 資訊障礙是 Teams 系統管理員設定的原則，可讓使用者或群組在沒有商務需求的情況下，進行彼此通訊 (，或是因法規理由封鎖他們進行此類) ，同時也可讓您設定與查閱和 eDiscovery (涵蓋在下方) 等事項相關的原則。 這些原則可能會影響一對一聊天、群組聊天或小組層級的使用者。 資訊隔隔功能可在公用雲端使用，自 2021 年 1 月開始，這項功能已推出至 GCC 雲端。

如需進一步閱讀本主題，請移至 [Microsoft Teams 中的資訊障礙](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>通訊合規性

Microsoft Purview 通訊合規性可讓您將使用者新增至範圍原則，這些原則可設定為檢查 Microsoft Teams 通訊中令人反感的語言、敏感性資訊，以及與內部和法規標準相關的資訊。 您可以掃描公用和私人 Teams 頻道中的聊天通訊和相關聯的附件、個別聊天和附件，以協助將組織中的通訊風險降至最低。 如需如何設定原則以協助您偵測、擷取不當 Teams 通訊及採取動作的詳細資訊，請參閱 [瞭解通訊合規性](/microsoft-365/compliance/communication-compliance)。

### <a name="sensitivity-labels"></a>敏感度標籤

套用 [敏感度標籤](/microsoft-365/compliance/sensitivity-labels) 以保護並規範在團隊內共同作業期間所建立之敏感組織內容的存取權。 例如，套用標籤來設定團隊的隱私 (公用或私人) 、控制來賓存取和外部共用，以及管理未受管理裝置的存取權。 如需詳細資訊，請 [檢閱 Microsoft Teams 中的敏感度標籤](sensitivity-labels.md)。

### <a name="microsoft-purview-data-loss-prevention-dlp"></a>Microsoft Purview 資料外洩防護 (DLP) 

Microsoft Teams 中的資料外泄防護 (DLP) ，以及 Microsoft Purview 的大型 DLP 案例，圍繞著保護機密檔和資料時的業務整備。 無論您對郵件或檔中的機密資訊有任何疑慮，DLP 原則都能協助確保您的使用者不會與錯誤的人員共用此機密資料。

如需 Teams 中資料外泄防護的相關資訊，請檢閱 [Microsoft Teams 的 DLP](/microsoft-365/compliance/dlp-microsoft-teams)。 DLP 考慮的一篇好文章是 [瞭解資料外泄防護](/microsoft-365/compliance/dlp-learn-about-dlp)。

### <a name="customer-key"></a>客戶金鑰

Microsoft 365 會在內容的服務加密之上提供一層額外的加密。 使用您提供的金鑰，客戶金鑰會加密 Microsoft Teams 中數種不同類型的資料。 使用應用程式層級的客戶金鑰，客戶金鑰會加密儲存在 SharePoint Online 中的 Teams 檔案。 如需詳細資訊，請參閱使用 [Microsoft Purview 客戶金鑰進行服務加密](/microsoft-365/compliance/customer-key-overview)。

在租使用者層級使用客戶金鑰，客戶金鑰加密：
- Teams 聊天訊息 (一對一聊天、群組聊天、會議聊天和頻道交談) 
- Teams 媒體訊息 (影像、程式碼片段、影片和 Wiki 影像) 
- 儲存在 Teams 儲存空間中的 Teams 通話和會議錄製
- Teams 聊天通知
- Cortana 提供的 Teams 聊天建議
- Teams 狀態訊息

如需詳細資訊，請參閱 [租使用者層級的客戶金鑰概觀](/microsoft-365/compliance/customer-key-tenant-level) ，並閱讀 Microsoft Teams 部落格以 [公開預覽涵蓋 Microsoft Teams 的客戶金鑰支援](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)。 如需在租使用者層級包含客戶金鑰的Microsoft Purview 資訊保護發行資訊，請參閱[宣佈新Microsoft Purview 資訊保護功能以瞭解及保護您的機密資料](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

### <a name="retention-policies"></a>保留原則

Microsoft Teams 中的保留原則可讓您基於法規、法律、業務或其他原因，同時保留貴組織要保留的重要資料，以及移除與保留不相關的內容和通訊。 您也可以使用保留原則來保留資料一段時間，然後刪除資料。 如需詳細資訊，請 [檢閱 Microsoft Teams 中的保留原則](retention-policies.md)。

### <a name="ediscovery"></a>電子文件探索

電子化探索或電子檔探索是識別、收集及產生電子儲存資訊的電子層面， (ESI) ，以回應法律或調查中的生產要求。 功能包括案例管理、保留、搜尋、分析及 Teams 資料匯出。 這包括聊天、訊息和檔案、會議和通話摘要。 針對 Teams 會議和通話，會在 eDiscovery 中建立並提供會議和通話中發生的事件摘要。

如需如何在Microsoft Purview 合規性入口網站中使用電子檔探索工具來搜尋 Teams 內容的詳細資料，請移至下列連結：

- [電子文件探索](/microsoft-365/compliance/manage-legal-investigations)

- [內容搜尋](/microsoft-365/compliance/search-for-content)

我們有 Teams 專屬的文章，如需詳細資訊，請參閱對 [Microsoft Teams 中的內容進行電子檔探索調查](eDiscovery-investigation.md)。

客戶可以根據自己的需求運用 eDiscovery 或 [eDiscovery (Premium) ](/microsoft-365/compliance/office-365-advanced-ediscovery) 。 下表概述這兩者之間的差異：

|&nbsp; |電子文件探索  |eDiscovery (Premium)   |
|---------|---------|---------|
|案例管理     |X        |X         |
|存取控制  |X         |X         |
|內容搜尋     |X         | X        |
|按住 (的)    |X         | X        |
|出口     |X         |X         |
|複製偵測     |-         |X         |
|使用機器學習進行相關性搜尋    |-         |X         |
|非結構化資料分析      |-         |X         |

### <a name="legal-hold"></a>法律保留

在訴訟期間，您可能需要保留與使用者 (監管人) 或小組相關聯的所有資料，才能保留為無法保存的資料，以便用來做為案例的證明。 您可以透過將使用者 (使用者信箱) 或將小組設為法律保留來執行此動作。 對於團隊的法律保留，小組的信箱可以設為下列保留：

- In-Place透過目標查詢或篩選的內容保留 (信箱或網站集合的子集合會保留) ，或
- 訴訟資料暫留 (整個信箱或網站集合會) 保留。

無論哪種情況，一旦設定保留狀態，就會確保即使使用者刪除或編輯群組信箱中的頻道訊息，該內容的不可失效複本仍可透過電子檔探索搜尋維護並取得。 法律保留通常會在 eDiscovery 案例中套用。

請參閱[保留原則概觀](/microsoft-365/compliance/retention-policies)，以深入瞭解保留和保留Microsoft Purview 合規性入口網站。 如需法律保留上的更多 Teams 特定資訊，我們也已將 [Microsoft Teams 使用者或團隊設為法律保留](legal-hold.md) 狀態，讓您深入瞭解。

### <a name="content-search"></a>內容搜尋

內容搜尋可用來透過豐富的篩選功能來搜尋所有 Teams 資料。 結果資料可匯出至特定容器，以獲得合規性與訴訟支援。 這可以使用電子檔探索案例或不包含電子檔探索案例來完成。 這可讓合規性系統管理員收集所有使用者的 Teams 資料、檢閱並匯出資料以進行進一步處理。 請參閱[內容搜尋](/microsoft-365/compliance/content-search)，以深入瞭解如何在 Microsoft Purview 合規性入口網站 中對 Microsoft Teams 和其他 Microsoft 365 或Office 365內容進行合規性內容搜尋。

> [!TIP]
> 如有需要，您可以使用內容搜尋篩選到僅限 Microsoft Teams 的內容，例如聊天和頻道訊息、會議和通話。

如果您想要進一步瞭解設定內容搜尋的 Teams 特定資訊，請 [檢閱 Microsoft Teams 中的內容搜尋](content-search.md)。

### <a name="auditing"></a>稽核

稽核記錄搜尋會直接插入Microsoft Purview 合規性入口網站，並允許系統管理員使用工作負載特定或一般事件集，並在無限制的稽核時程表上調查工作負載，讓您能夠設定提醒及稽核附隨報告。 您可以針對Microsoft Purview 合規性入口網站中的所有稽核記錄資料設定警示，並篩選和匯出此資料以進一步分析。 若要深入瞭解如何在 Microsoft Purview 合規性入口網站 中搜尋 Microsoft Teams 事件，請參閱[搜尋 Microsoft Teams 中事件的稽核記錄](audit-log-events.md)。

## <a name="privacy"></a>隱私權

在 Microsoft，保護您的資料是我們的首要之務。 若要瞭解我們的隱私權做法，請閱讀：  

- [Microsoft 的隱私權](https://www.microsoft.com/trust-center/privacy)
- [我們對 Microsoft Teams 中隱私權和安全性的承諾](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [適用于 IT 專業人員：Microsoft Teams 中的隱私權和安全性](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>資訊保護架構

下圖指出 Teams 資料同時向 Exchange 和 SharePoint for Teams 檔案和訊息的擷取流程。

> [!div class="mx-imgBorder"]
> ![Teams 資料至 Exchange 和 SharePoint 的工作流程圖表。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下圖表示 Teams 會議和通話資料到 Exchange 的摱取流程。

> [!div class="mx-imgBorder"]
> ![Teams 會議和通話資料到 Exchange 的工作流程圖表。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 探索 Teams 內容最多可能需要 24 小時。

## <a name="licensing"></a>授權

若要瞭解資訊保護功能，Microsoft 365 訂閱、Office 365訂閱以及相關聯的獨立授權將決定可用的功能集。

如需判斷授權是否需要實作安全性與合規性功能的相關資訊，請檢閱安全性與合規性功能的 [授權需求](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 。

> [!NOTE]
> 內容搜尋、eDiscovery (Standard) 和 eDiscovery (Premium) 不需要在Microsoft Purview 合規性入口網站中啟用即可運作。 如需詳細資訊，請參閱 [Microsoft 365 電子檔探索解決方案](/microsoft-365/compliance/ediscovery)。

## <a name="location-of-data-in-teams"></a>Teams 中的資料位置

Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。 若要查看目前支援哪些地區，請 [檢閱 Microsoft Teams 中的資料位置](location-of-data-in-teams.md)。

如果您需要查看哪些地區會容納您租使用者的資料，請移至 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)  >  **Settings**  >  **組織設定檔。** 向下捲動到 **資料位置**。

> [!div class="mx-imgBorder"]
> ![[資料位置] 表格的螢幕擷取畫面，包括系統管理中心的 Teams。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合規性標準

Teams 使用下列標準： [ISO 27001](/microsoft-365/compliance/offering-iso-27001)、 [ISO 27018](/microsoft-365/compliance/offering-iso-27018)、 [SSAE18 SOC 1 和 SOC 2](/microsoft-365/compliance/offering-soc)、 [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)和 [EU Model Clauses (EUMC) ](/microsoft-365/compliance/offering-eu-model-clauses)。 在 Microsoft 合規性架構中，Microsoft 將 Microsoft 365 和Office 365應用程式與服務分類為四種類別。 每個類別都是根據特定合規性承諾所定義，必須滿足 Microsoft 365 或Office 365服務或相關 Microsoft 服務，才能列在該類別中。

您可以在 [資料保護資源](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)中找到詳細資料。 Teams 也支援 Cloud Security Alliance 合規性。

## <a name="related-topics"></a>相關主題

[Microsoft 365 安全性](/microsoft-365/security/)

[Microsoft 365 合規性](/microsoft-365/compliance/)

[Microsoft 合規性服務](/microsoft-365/compliance/offering-home)
