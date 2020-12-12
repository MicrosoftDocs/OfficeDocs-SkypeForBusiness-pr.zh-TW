---
title: 安全性與合規性概述
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Microsoft 團隊安全性與合規性功能的概覽，包括隱私權與加密、審核及報告等。
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
ms.openlocfilehash: c17bf12a929f03ae766c57bb7f32da4e62f5a950
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662498"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Microsoft 團隊中的安全性與合規性

> [!IMPORTANT]
> 若要深入瞭解如何在 **COVID-19 爆發期間，從家用的任何人都** 能保證安全性，請閱讀以下文章：
>  - [安全性團隊支援在家工作最常見的 12 項工作](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分割通道最佳化遠端使用者的 Microsoft 365 或 Office 365 連線能力](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新2020年4月2日： [團隊安全性指南](teams-security-guide.md)


Microsoft 團隊是以 Microsoft 365 和 Office 365 超規模、企業級雲端為基礎，提供客戶預期的高級安全性與合規性功能。 如需在 Microsoft 365 或 Office 365 中規劃安全性的詳細資訊，您可以開始 [使用安全性藍圖](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) 。 如需在 Microsoft 365 或 Office 365 中規劃合規性的詳細資訊，您可以從 [安全性與合規性](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) 文章的方案開始。


本文將提供更多關於小組特定安全性與合規性的資訊。 不要錯過這些關於安全性與合規性的 Microsoft 規範影片：

- [適用于 IT 的 Microsoft 團隊基本版：安全性與合規性](https://youtu.be/91lHNKVVvQ4) (12:42 分鐘) 
- [Microsoft 團隊控制安全性與合規性](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 分鐘) 

> [!IMPORTANT]
> 作為 Microsoft 365 或 Office 365 的客戶，您擁有並控制您的資料。 除了向您提供已訂閱的服務之外，Microsoft 不會將您的資料用於任何其他專案。 身為服務提供者，我們不會掃描您的電子郵件、檔或團隊，以進行廣告或與服務相關的目的。 Microsoft 沒有已上傳內容的存取權。 就像 Microsoft 365 中的 OneDrive 和 SharePoint 一樣，客戶資料仍會留在租使用者內。 您可以在 [Microsoft 信任中心](https://microsoft.com/trustcenter)深入瞭解我們與安全性相關的資訊。 小組與 Microsoft 信任中心遵循相同的指導方針與原則。

## <a name="security"></a>安全性

團隊會強制進行整個小組和組織範圍的雙因素驗證、透過 Active Directory 進行單一登入，以及在中轉時加密資料。 檔案是儲存在 SharePoint 中，且由 SharePoint 加密來支援。 筆記是儲存在 OneNote 中，且由 OneNote 加密所支援。 OneNote 資料會儲存在小組 SharePoint 網站。 [Wiki] 索引標籤也可用於記事記錄，而其內容也會儲存在小組 SharePoint 網站中。

閱讀身分 [識別模型與驗證](identify-models-authentication.md) ，以深入瞭解驗證與團隊，以及 [新式驗證運作方式將如何](sign-in-teams.md) 協助新式驗證。

由於團隊在與 SharePoint、OneNote、Exchange 等合作夥伴合作，因此您應該輕鬆管理 Microsoft 365 或 Office 365 中的安全性。 若要深入瞭解，請參閱 [如何設定您的 Microsoft 365 或 Office 365 組織，以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前， [私有通道](private-channels.md) 支援有限的安全性與合規性功能。 我們即將推出私人通道中完整的安全性與合規性功能的支援。

### <a name="advanced-threat-protection-atp"></a> (ATP) 的 [高級威脅防護]

Microsoft 團隊提供高級威脅防護 (ATP) ，以及 SharePoint 和 OneDrive 等與團隊進行內容管理的應用程式。 ATP 可讓您判斷這些應用程式中的內容是否具有惡意性質，並封鎖來自使用者存取的內容。

在檢測到您在 Microsoft 365 或 Office 365 中所選取的設定之後，受影響內容的管理方式。 我們強烈建議您在設定 ATP 時考慮所有應用程式，並進一步閱讀 [SharePoint、OneDrive 和 Microsoft 團隊](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) 文章的相關詳細資訊，以取得如何開始使用的相關資訊。

### <a name="safe-links"></a>安全連結

不過，在此期間，Microsoft 團隊不提供 [高級威脅防護] (ATP) 安全連結，因為它們現在是透過我們的技術採納計畫來進行 [公開預覽](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) (請參閱) ，而且在該時間到達時，我們將會更新這篇文章。 同時，如需 Microsoft 365 或 Office 365 安全連結的相關資訊，請參閱 [ATP 安全連結](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 [Atp [方案 1] 和 [Atp 方案 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)] 中都有 [atp 安全連結]。

### <a name="safe-attachments"></a>安全附件

[安全附件] 是專門用來加強使用者安全性的功能，方法是檢查及偵測惡意附件。 全域或安全性系統管理員會建立處理這些可疑的惡意附件的 [原則](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) ，避免它們被傳送給使用者、按一下，以及採取的動作。 SharePoint、OneDrive 和 Microsoft 團隊都提供安全的附件保護功能，而且 Microsoft 365 或 Office 365 [高級威脅防護方案1和 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) 都有這項功能。 瞭解更多關於安全附件的資訊，以及他們如何協助保護[貴組織。](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="how-conditional-access-policies-work-for-teams"></a>條件式存取原則對於團隊的運作方式

Microsoft 團隊大量依賴 Exchange Online、SharePoint 及商務用 Skype Online 來取得核心生產力案例，例如會議、行事曆、交互操作聊天和檔案共用。 針對這些雲端應用程式設定的條件式存取原則，在使用者直接登入 Microsoft 團隊時（任何用戶端），都適用于 Microsoft 團隊。

Microsoft 團隊獨立支援在 Azure Active Directory 條件式存取原則中作為雲端 app。 在使用者登入時，針對 Microsoft 團隊雲端 app 設定的條件式存取原則適用于 Microsoft 團隊。 不過，在其他 app （例如 Exchange Online 和 SharePoint）上沒有正確的原則，使用者仍然可以直接存取這些資源。 如需在 azure 入口網站中設定條件式存取原則的詳細資訊，請移至： [Azure Active Directory 快速入門](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

適用于 Windows 和 Mac 的 Microsoft 團隊桌面用戶端支援新式驗證。 新式驗證會根據 Azure Active Directory 驗證庫（ () ADAL），在跨平臺的 Microsoft Office 用戶端應用程式中提供登入。

Microsoft 團隊桌面應用程式支援 AppLocker。  如需有關 AppLocker 必備元件的詳細資訊，請參閱：使用 [applocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)的需求。

## <a name="compliance"></a>合規性

團隊有大量的資訊可協助您處理合規性區域，包括頻道、聊天和附件的法規遵從性、保留原則、資料遺失保護 (DLP) 、eDiscovery 和法律封存（針對頻道、聊天和檔案、審核記錄搜尋，以及使用 Microsoft Intune 的行動應用程式管理）。 我們已提供下列所有主題的相關資訊，您可以移至 [Microsoft 365 合規性中心](https://compliance.microsoft.com) 來管理這些設定。

### <a name="information-barriers"></a>資訊障礙

資訊障礙是由團隊管理員在適當的地方進行設定，例如，當人員或群組無法與其他人進行通訊時，請不要與 (其他人進行通訊，只要他們不需要這樣做) ，就能讓您設定與查閱及 eDiscovery (所) 涵蓋的專案類似的原則。 這些原則會影響1:1 聊天、群組聊天或團隊階層的使用者。

如需進一步閱讀本主題，請參閱 [Microsoft 團隊中的資訊障礙](information-barriers-in-teams.md)。

### <a name="communication-compliance"></a>溝通合規性

Microsoft 365 中的通訊合規性可讓您將使用者新增至範圍內原則，這些策略可以設定以檢查適用于冒犯性語言的 Microsoft 團隊通訊、敏感資訊，以及與內部和法規標準相關的資訊。 您可以掃描公用和私人團隊頻道、個別聊天和附件中的聊天通信及相關附件，協助將貴組織的通訊風險降至最低。 如需如何設定原則以協助您偵測、捕獲並採取行動以進行不當小組通訊的詳細資訊，請參閱 [Microsoft 365 中的通訊合規性](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。

### <a name="retention-policies"></a>保留原則

Microsoft 團隊中的保留原則可讓您保留貴組織所重要的資料，以符合法規、法律、商業或其他原因，以及移除與保留不相關的內容與通訊。 您也可以使用保留原則，將資料保留一段時間，然後將其刪除。 如需進一步資訊，請參閱 [Microsoft 團隊文章中的保留原則](retention-policies.md) 。

### <a name="data-loss-prevention-dlp"></a> (DLP) 的資料遺失防護

Microsoft 團隊中的 [資料遺失防護] (DLP) ，以及適用于 Microsoft 365 或 Office 365 的較大 DLP 故事，在保護機密檔和資料時，也會涉及業務就緒性。 無論您是否擔心郵件或檔中的機密資訊，DLP 原則都可以協助確保您的使用者不會與錯誤的人員共用此機密資料。

如需有關團隊資料遺失防範功能的詳細資訊，請參閱 [Microsoft 團隊的 DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams)。 關於 O365 DLP 問題的好文章，就是 [資料遺失防護的概況](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>eDiscovery

電子查詢（或 eDiscovery）是識別、收集及出具以電子方式儲存資訊 () ESI 的電子資料，以回應法律訴訟或調查中的生產要求。 功能包括案例管理、保留、搜尋、分析，以及匯出團隊資料。 這包括聊天、訊息與檔案、會議和通話摘要。 針對團隊會議和通話，在會議和通話中所發生事件的摘要會在 eDiscovery 中建立並提供。

如需有關如何在安全性中心與合規性中心中執行 Microsoft 365 或 Office 365 eDiscovery 的詳細資料，以及執行小組內容的規範內容搜尋，請參閱下列連結：

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

我們有一個小組專用文章，如需詳細資訊，請 [EDiscovery 電子檔探索](eDiscovery-investigation.md)。

客戶可以根據電子檔的需求來利用 eDiscovery 或 [高級 ediscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) 。 下表說明兩個專案之間的差異：

| |eDiscovery  |高級 eDiscovery  |
|---------|---------|---------|
|案例管理     |X        |X         |
|存取控制  |X         |X         |
|內容搜尋     |X         | X        |
|按住 (s)    |X         | X        |
|匯出     |X         |X         |
|重複偵測     |-         |X         |
|使用電腦學習進行關聯性搜尋    |-         |X         |
|非結構化資料分析      |-         |X         |

### <a name="legal-hold"></a>法律封存

在訴訟期間，您可能需要與使用者 (保管人) 或團隊保持不變，才能作為案例的證據使用。 您可以將使用者 ([使用者信箱]) 或 [法律封存] 上的小組成員來執行此動作。 針對小組法律封存，小組的信箱可以放在下列保留中：

- In-Place 在已設定目標的查詢中 (保留信箱或網站集合的子集，或已將內容保留) 中，或
- 訴訟封存 (整個信箱或網站集合都會處於保留狀態) 。

在任何一種情況下，只要設定保留，就能確保即使使用者刪除或編輯群組信箱中的頻道訊息，該內容的不變複本仍能透過 eDiscovery 搜尋進行維護和使用。 法律封存一般會套用在 eDiscovery 案例的內容中。

請參閱 [保留原則](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) 文章的概覽，以深入瞭解 Microsoft 365 規範中心中保留並保留的資訊。 如需法律封存的相關小組特定資訊，我們也可以讓 [Microsoft 團隊使用者或團隊在法律封存](legal-hold.md) 中取得詳細資訊。

### <a name="compliance-content-search"></a>合規性內容搜尋

您可以使用內容搜尋，透過豐富的篩選功能搜尋所有團隊資料。 產生的資料可以匯出到特定容器，以進行合規性和訴訟支援。 您可以使用或不使用 eDiscovery 案例來完成此操作。 這可讓合規性系統管理員收集所有使用者的小組資料、審閱並匯出，以進行進一步的處理。 如需深入瞭解如何在 Microsoft 365 規範中心中搜尋 Microsoft 團隊以及其他 Microsoft 365 或 Office 365 內容，請參閱此 [內容搜尋](https://docs.microsoft.com/microsoft-365/compliance/content-search) 文章。

> [!TIP]
> 使用內容搜尋，您可以在必要時篩選到 Microsoft 團隊中的 [僅限交談] 和 [頻道訊息]、[會議] 和 [通話] 等內容。

如果您想進一步瞭解如何設定內容搜尋的相關資訊，請參閱 [Microsoft 團隊文章中的內容搜尋](content-search.md) 。

### <a name="auditing-and-reporting"></a>審核與報告

在 Microsoft 365 合規性中心直接進行審核記錄搜尋，讓您能夠設定警報，以及報告審核事件，方法是允許匯出工作負載的特定或一般事件集，以供管理員使用，並跨無限制的審核時程表進行調查。 您可以針對 Microsoft 365 合規性中心內的所有審核記錄資料設定警示，並篩選及匯出此資料以進行進一步分析。 請參閱 [搜尋審核記錄](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) 文章，進一步瞭解如何執行 Microsoft 365 或 Office 365 的審核記錄搜尋。 若要深入瞭解在 Microsoft 365 規範中心中搜尋 Microsoft 團隊活動，我們也會在 [團隊文章中開啟 [審核](audit-log-events.md) ]，讓您複習。

## <a name="privacy"></a>隱私權

在 Microsoft，保護您的資料是我們最高的優先順序。 若要瞭解我們的隱私權做法，請參閱：  

- [Microsoft 的隱私權](https://www.microsoft.com/trust-center/privacy)
- [我們在 Microsoft 團隊中的隱私權與安全性承諾](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [IT 專業人員： Microsoft 團隊中的隱私權與安全性](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>資訊保護架構

下圖顯示小組檔案和郵件的 [從 Exchange 與 SharePoint 接收] 資料的攝取流程。

![[小組] 資料至 Exchange 和 SharePoint 的工作流程圖表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下圖顯示團隊會議的攝取流程和呼叫資料至 Exchange。

![小組工作流程的圖表及呼叫資料至 Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 若要探索小組內容，最多可以有24小時的延遲時間。

## <a name="licensing"></a>授權

當您遇到資訊保護功能時，Microsoft 365 訂閱、Office 365 訂閱及相關聯的獨立授權將決定可用的功能集。

如需判斷授權必須實現安全性與合規性功能的相關資訊，請參閱安全性與合規性功能的 [授權需求](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) 。
> [!NOTE]
> 在安全性 & 合規性中心中不需要啟用 [內容搜尋] 和 [eDiscovery]，就能正常運作。

## <a name="location-of-data-in-teams"></a>Teams 中的資料位置

Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。 若要查看目前支援哪些地區，請參閱 [Microsoft 團隊中資料的位置](location-of-data-in-teams.md)。

如果您需要查看哪個地區駐留您租使用者的資料，請移至 [Microsoft 365 系統管理中心](https://portal.office.com/adminportal/home)  >  **設定**  >  **組織設定檔**。 向下捲動到 **資料位置**。

![資料位置資料表的螢幕擷取畫面，其中包含系統管理中心的團隊](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合規性標準

團隊使用下列標準： [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001)、 [iso 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018)、 [SSAE18 SOC 1 和 SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc)、 [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)，以及 [歐盟模型子句 (EUMC) ](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses)。 在 Microsoft 合規性架構中，Microsoft 將 Microsoft 365 與 Office 365 應用程式及服務分為四種類別。 每個類別都是由要在該類別中列出的 Microsoft 365 或 Office 365 服務或相關 Microsoft 服務所符合的特定合規性承諾所定義。

您可以在 [資料保護資源](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)中找到詳細資料。 團隊也支援雲端安全聯盟規範。

## <a name="related-topics"></a>相關主題

[Microsoft 365 安全性](https://docs.microsoft.com/microsoft-365/security/)

[Microsoft 365 合規性](https://docs.microsoft.com/microsoft-365/compliance/)

[Microsoft 合規性產品](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
