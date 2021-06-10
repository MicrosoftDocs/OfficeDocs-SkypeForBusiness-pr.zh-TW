---
title: 安全性和合規性概觀
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: 安全性與Microsoft Teams功能概觀，包括隱私權和加密、稽核與報告等。
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
ms.openlocfilehash: bfa593aaeabe8d7aab9446a1070134b267ea6ef4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107609"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>安全性與合規性Microsoft Teams

> [!IMPORTANT]
> 若要瞭解如何在 **COVID-19** 疫情期間，以最佳方式確保每個人在家工作時的安全性，請閱讀以下文章：
>  - [安全性團隊支援在家工作最常見的 12 項工作](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [使用 VPN 分割通道最佳化遠端使用者的 Microsoft 365 或 Office 365 連線能力](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - 更新日期：Teams[指南](teams-security-guide.md)


Microsoft Teams建在超大規模Microsoft 365 Office 365雲端上，提供客戶預期進位的安全性與合規性功能。 若要進一Microsoft 365或Office 365安全性規劃，安全性藍圖是一個很好的起點。 [](/microsoft-365/security/office-365-security/security-roadmap) 如要進一Microsoft 365或Office 365合規性規劃，您可以從安全性與合規性規劃[&開始](/microsoft-365/compliance/plan-for-security-and-compliance)。


本文將提供有關特定安全性Teams合規性的進一步資訊。 千萬不要錯過以下有關安全性與合規性的 Microsoft 技術員影片：

- Microsoft Teams IT 基本功能[： (](https://youtu.be/91lHNKVVvQ4) 12：42 分鐘) 
- [Microsoft Teams](https://www.youtube.com/watch?v=Km4T4hMM__k) 10：54 分鐘 (安全性與合規性控制) 

> [!IMPORTANT]
> 做為客戶或Microsoft 365 Office 365，您擁有並控制您的資料。 除了提供您訂閱的服務外，Microsoft 不會將您的資料用於其他用途。 作為服務提供者，我們不會掃描您的電子郵件、檔或小組，以用於廣告或與服務不相關的用途。 Microsoft 沒有上傳內容的存取權限。 就像OneDrive中的SharePoint和Microsoft 365，客戶資料會保留在租使用者內。 您可以在 Microsoft 信任中心查看我們的信任和安全性 [相關資訊](https://microsoft.com/trustcenter)。 Teams Microsoft 信任中心遵循相同的指引和原則。

## <a name="security"></a>安全性

Teams強制執行全小組和全組織的雙因素驗證、透過 Active Directory 單一登入，以及傳輸中和靜態資料加密。 檔案會儲存在SharePoint，並受到加密SharePoint備份。 筆記會儲存在OneNote中，並受到加密OneNote備份。 資料OneNote儲存在小組或SharePoint中。 Wiki 定位停駐點也可以用來記錄筆記，其內容也會儲存在小組SharePoint網站。

請閱讀[身分識別模型](identify-models-authentication.md)和驗證，以深入瞭解驗證Teams，以及新式驗證如何運作[](sign-in-teams.md)，尤其有助於新式驗證。

由於Teams與 SharePoint、OneNote、Exchange 等專案共同運作，因此您應該很熟悉管理 Microsoft 365 或 Office 365 安全性。 若要深入瞭解，請參閱如何設定您的Microsoft 365[或Office 365組織，以提升安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。

> [!NOTE]
> 目前 [，私人頻道](private-channels.md) 支援有限的安全性和合規性功能。 即將推出私人頻道的完整安全性和合規性功能支援。

### <a name="advanced-threat-protection-atp"></a>ATP (進) 

進 (ATP) 適用于 Microsoft Teams，以及 SharePoint 和 OneDrive，與 Teams 整合進行內容管理的應用程式。 ATP 可讓您判斷這些應用程式中的內容是否具有惡意性質，並封鎖此內容以禁止使用者存取。

偵測後，受影響的內容管理方式，會以您選取的設定Microsoft 365或Office 365。 我們強烈建議您在配置 ATP 時考慮所有應用程式，若要進一步閱讀，SharePoint、OneDrive 和 Microsoft Teams 的[ATP](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams)將會提供如何開始使用的詳細資訊。

### <a name="safe-links"></a>安全連結

雖然目前 Microsoft Teams 中無法提供進一步威脅防護 (ATP) 安全連結，但現在透過我們的技術採用計畫 ([](/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) TAP) 提供公開預覽，而尚未設定一般可用性的發行日期，我們將在該時間到達時更新本文。 同時，如需有關Microsoft 365或Office 365連結的資訊，請參閱[ATP 安全連結](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)。 ATP 安全連結可在 ATP 方案 1 和 [ATP 方案 2 中提供](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)。

### <a name="safe-attachments"></a>安全附件

安全附件是一項設計來檢查及偵測惡意附件，以增強使用者安全性的功能。 全域或安全性系統管理員會建立處理[](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide)這些可疑惡意附件的策略，以防止這些可疑的惡意附件送出給使用者、按一下附件及採取行動。 安全附件保護適用于 SharePoint、OneDrive 和 Microsoft Teams，Microsoft 365 或 Office 365 進威脅防護計畫 1 和[2](/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)具有此功能。 閱讀更多有關安全附件的資訊，以及這些附件如何協助保護貴組織在 Microsoft Defender for [Office 365。](/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>安全分數

Microsoft Secure Score 是組織安全性狀態的度量單位，較高的數位表示已採取更多改進動作。 您可以在安全中心找到[Microsoft 365。](https://security.microsoft.com/securescore) 遵循安全分數建議可保護貴組織不受威脅。 從安全中心集中式儀表板Microsoft 365，組織可以監控及處理其Microsoft 365、應用程式和裝置的安全性。 Microsoft Teams有關于安全分數的建議，我們鼓勵系統管理員監控他們在平臺上的安全性。

安全分數可協助組織：
- 報告組織安全性狀態目前的狀態。
- 提供可探索性、可見度、指引及控制，以改善其安全性狀態。
- 比較基準並建立 KPI (關鍵) 。


### <a name="how-conditional-access-policies-work-for-teams"></a>條件式 Access 政策如何適用于Teams

Microsoft Teams大量仰賴 Exchange Online、SharePoint 和 商務用 Skype Online 來核心生產力案例，例如會議、日曆、交互操作聊天和檔案共用。 針對這些雲端應用程式所設定的條件式存取原則Microsoft Teams使用者直接在任何用戶端上Microsoft Teams時，

Microsoft Teams條件式存取規則中的雲端應用程式，Azure Active Directory支援。 為雲端應用程式設定的條件式存取原則Microsoft Teams套用至Microsoft Teams使用者登錄時所設定的條件式存取原則。 不過，如果沒有其他應用程式上的正確Exchange Online和SharePoint，使用者可能仍然能夠直接存取這些資源。 有關在 Azure 入口網站中設定條件式存取策略Azure Active Directory[快速入門](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)。

Microsoft Teams和 Mac 版桌面Windows支援新式驗證。 新式驗證會根據 ADAL Azure Active Directory驗證庫 (ADAL) 跨Microsoft Office用戶端應用程式。

Microsoft Teams應用程式支援 AppLocker。  如需有關 AppLocker 先決條件的資訊，請參閱：使用 [AppLocker 的需求](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)。

## <a name="compliance"></a>合規性

Teams 提供豐富的資訊，可協助您處理合規性領域，包括頻道、聊天和附件的通訊合規性、保留政策、資料遺失保護 (DLP) 、頻道、聊天和檔案的 eDiscovery 和法律保留、稽核記錄搜尋，以及使用 Microsoft Intune 進行行動應用程式管理。 我們在下面提供所有這些主題的一些資訊，您可以前往規範中心Microsoft 365[管理](https://compliance.microsoft.com)這些設定。

### <a name="information-barriers"></a>資訊障礙

資訊障礙是由 Teams 系統管理員所套用，以執行一些操作，例如禁止人員或群組彼此通訊 (當他們不需要進行此作業時 (或法規理由禁止他們這麼做) ，它也可讓您設定與) 下方涵蓋的尋找和 eDiscovery (等相關政策。 這些策略可能會影響 1：1 聊天、群組聊天或小組層級的使用者。 資訊隔層功能可在公用雲端使用，自 2021 年 1 月開始已推出至 GCC 雲端。

若要進一步閱讀本主題，請前往 中[的資訊](information-barriers-in-teams.md)Microsoft Teams。

### <a name="communication-compliance"></a>通訊合規性

Microsoft 365中的通訊合規性可讓您將使用者新加入範圍內政策，這些策略可配置為檢查 Microsoft Teams 通訊中的攻擊性語言、敏感性資訊，以及與內部及法規標準有關的資訊。 您可以掃描公用和私人聊天Teams頻道、個別聊天和附件中的聊天通訊和相關附件，協助將貴組織的通訊風險降到最低。 若要進一步瞭解如何設定策略，協助偵測、捕獲不當通訊並採取行動Teams，請參閱[在](/microsoft-365/compliance/communication-compliance)Microsoft 365。

### <a name="retention-policies"></a>保留原則

Microsoft Teams 中的保留政策可讓您同時保留貴組織為法規、法律、商務或其他原因保留的重要資料，以及移除與保留不相關的內容和通訊。 您也可以使用保留政策將資料保留一段時間，然後將其刪除。 如需要詳細資訊，請參閱[中的保留Microsoft Teams。](retention-policies.md)

## <a name="sensitivity-labels"></a>敏感度標籤

使用 [敏感度標籤](/microsoft-365/compliance/sensitivity-labels) ，以保護及規範在團隊內共同合作期間所建立之機密組織內容的存取權。 例如，請用標籤來設定 (或) 的隱私權、控制來賓存取和外部共用，以及管理來自未管理裝置的存取權限。 進一步的資訊，請參閱中的敏感度[Microsoft Teams。](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>DLP (資料外) 

 () 中的 Microsoft Teams資料外) DLP，以及 Microsoft 365 或 Office 365 的更大 DLP 案例，都圍繞著保護機密檔和資料的商務準備狀態。 無論您對郵件或檔中的敏感性資訊有疑慮，DLP 政策都能協助確保您的使用者不會與錯誤人員共用此機密資料。

如需在 Teams 中防止資料外Teams，請參閱[DLP Microsoft Teams。](/microsoft-365/compliance/dlp-microsoft-teams) 適用于 O365 DLP 疑慮的一篇好文章是 [資料外遺失防護概觀](/microsoft-365/compliance/data-loss-prevention-policies)。

### <a name="ediscovery"></a>電子文件探索

電子探索或電子檔探索是識別、收集及產生電子儲存的資訊 (ESI) 以回應訴訟或調查之生產要求的電子層面。 功能包括案例管理、保留、搜尋、分析和匯出Teams資料。 這包括聊天、傳訊和檔案、會議與通話摘要。 針對Teams通話，會建立會議和通話中事件發生的摘要，並可在 eDiscovery 中取得。

如需如何在安全性中心與合規性中心Microsoft 365或Office 365電子檔探索，以及針對 Teams 內容執行合規性內容搜尋的詳細資訊，請前往下列連結：

 - [電子文件探索](/microsoft-365/compliance/manage-legal-investigations)

 - [內容搜尋](/microsoft-365/compliance/search-for-content)

我們有一Teams特定文章，以進一瞭解更多資訊，例如來賓對來賓聊天的[eDiscovery](eDiscovery-investigation.md)。

客戶可以運用 eDiscovery 或[Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery)需求。 下表概述兩者之間的差異：

| |電子文件探索  |Advanced eDiscovery  |
|---------|---------|---------|
|案例管理     |X        |X         |
|存取控制  |X         |X         |
|內容搜尋     |X         | X        |
|按住 ()    |X         | X        |
|出口     |X         |X         |
|重複偵測     |-         |X         |
|相關性搜尋機器學習    |-         |X         |
|非結構化資料分析      |-         |X         |

### <a name="legal-hold"></a>法律保留

在訴訟期間，您可能需要保留與使用者 (監護) 或小組相關聯的所有資料，以保存為不可變數據，以便做為案件證據。 您可以將使用者置於使用者信箱 (，) 將小組置於法律保留狀態。 對於團隊法律保留，團隊的信箱可以置於下列保留狀態：

- In-Place透過 () 查詢或篩選的內容保留信箱或網站集合的子集，或
- 訴訟保留 (整個信箱或網站集合會保留) 。

無論是哪種情況，一旦設定保留狀態，它可確保即使使用者刪除或編輯群組信箱中的頻道訊息，該內容的不可變複本仍可以維護，並透過 eDiscovery 搜尋提供。 法律保留通常適用于電子檔探索案例。

請參閱[保留原則](/microsoft-365/compliance/retention-policies)概觀，以進一Microsoft 365保留。 如需Teams保留的特定資訊，我們也會Microsoft Teams保留使用者或小組，以深入瞭解[](legal-hold.md)。

### <a name="compliance-content-search"></a>合規性內容搜尋

內容搜尋可用來透過豐富的篩選功能Teams所有資料。 產生的資料可以匯出至特定容器，以用於合規性和訴訟支援。 您可以執行此作業，也可以不使用 eDiscovery 案例。 這可讓合規性系統管理員收集Teams所有使用者的資料，並檢查並匯出資料以便進一步處理。 請參閱內容[搜尋](/microsoft-365/compliance/content-search)以深入瞭解如何執行合規性內容搜尋，以搜尋 Microsoft Teams 規範中心Microsoft 365或Office 365內容Microsoft 365內容。

> [!TIP]
> 使用內容搜尋，您可以向下篩選Microsoft Teams內容，例如聊天和頻道訊息、會議和通話 ，如有需要。

如果您想要進一步Teams內容搜尋的特定資訊，請參閱在 Microsoft Teams 中[搜尋](content-search.md)內容。

### <a name="auditing-and-reporting"></a>稽核與報告

稽核記錄搜尋功能會直接插入 Microsoft 365 合規性中心，讓您能設定警示，以及報告稽核事件，允許匯出工作負載特定或一般事件集，供系統管理員使用，並跨無限稽核時程表進行調查。 您可以在合規性中心內設定所有稽核記錄資料的Microsoft 365，並篩選及匯出這些資料以進一步分析。 請參閱搜尋[稽核](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)記錄以深入瞭解如何執行稽核記錄搜尋Microsoft 365或Office 365。 若要深入瞭解在 Microsoft Teams合規性中心搜尋Microsoft 365事件，我們也會在 Teams 中開啟稽核功能，Teams供[](audit-log-events.md)您查看。

## <a name="customer-key"></a>客戶金鑰

Microsoft 365內容的服務加密功能外，還提供額外的加密層。 使用您提供的金鑰，Customer Key 會加密多個不同類型的Microsoft Teams。 在應用程式層級使用 Customer Key，Customer Key 會加密儲存在 Teams Online 中的SharePoint檔案。 詳細資訊，請參閱使用 [Customer Key 進行服務加密](/microsoft-365/compliance/customer-key-overview)。 

在租使用者層級使用客戶金鑰，客戶金鑰會加密：
- Teams聊天訊息 (1：1 聊天、群組聊天、會議聊天，以及頻道交談) 
- Teams媒體訊息 (影像、程式碼段、影片和 Wiki 影像) 
- Teams儲存在儲存空間中的通話和Teams錄製
- Teams聊天通知
- Teams Cortana 提供聊天建議
- Teams狀態訊息 的詳細資訊，請參閱租使用者層級的[Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level)客戶金鑰概觀，並閱讀涵蓋 Microsoft Teams 客戶金鑰支援的 Microsoft Teams 部落格[。](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893) 若要瞭解包含租使用者層級客戶金鑰的 Microsoft 資訊保護版本，請參閱宣告新的 Microsoft 資訊保護功能，以知道並保護您的 [機密資料](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)。

## <a name="privacy"></a>隱私權

在 Microsoft，保護您的資料是我們的最高優先順序。 若要瞭解我們的隱私權作法，請閱讀：  

- [Microsoft 隱私權](https://www.microsoft.com/trust-center/privacy)
- [我們對於隱私權和安全性的承諾Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [適用于 IT 專業人員：隱私權和安全性Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>資訊保護架構

下圖指出將資料輸入Teams至Exchange和SharePoint的Teams流程。

> [!div class="mx-imgBorder"]
> ![將資料Teams到Exchange SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

下圖指出會議與Teams資料的輸入流程Exchange。

> [!div class="mx-imgBorder"]
> ![會議與Teams資料的工作流程圖表Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> 您最多可能會延遲 24 小時才能探索Teams內容。

## <a name="licensing"></a>授權

當涉及資訊保護功能時，Microsoft 365訂閱、Office 365訂閱，以及相關聯的獨立授權將決定可用的功能集。

如需決定授權需要為安全性與合規性執行功能的資訊，請參閱安全性與合規性功能的授權需求[](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

> [!NOTE]
> 內容搜尋和 eDiscovery 不需要在安全性與合規性中心&啟用。

## <a name="location-of-data-in-teams"></a>Teams 中的資料位置

Teams 中的資料位於與 Microsoft 365 或 Office 365 組織關聯的地理區域中。 若要查看目前支援哪些地區，請參閱資料[在 Microsoft Teams 中的位置](location-of-data-in-teams.md)。

如果您需要查看哪些地區會為租使用者提供資料，請前往系統管理中心 [](https://portal.office.com/adminportal/home)Microsoft 365組織設定  >    >  **設定檔**。 向下捲動到 **資料位置**。

> [!div class="mx-imgBorder"]
> ![系統管理中心資料位置資料表的螢幕擷取畫面Teams資料位置資料表](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>合規性標準

Teams使用下列標準[：ISO 27001、ISO](/microsoft-365/compliance/offering-iso-27001) [27018、SSAE18](/microsoft-365/compliance/offering-iso-27018) [SOC 1 和 SOC 2、HIPAA](/microsoft-365/compliance/offering-soc)和歐盟示範條款[ (EUMC) 。](/microsoft-365/compliance/offering-eu-model-clauses) [](/microsoft-365/compliance/offering-hipaa-hitech) 在 Microsoft 合規性架構中，Microsoft 將Microsoft 365與Office 365應用程式與服務分成四個類別。 每個類別是由特定合規性承諾所定義，這些承諾必須Microsoft 365或Office 365服務或相關的 Microsoft 服務，以列在該類別中。

詳細資料請參閱資料保護 [資源](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides)。 Teams也支援雲端安全聯盟合規性。

## <a name="related-topics"></a>相關主題

[Microsoft 365安全](/microsoft-365/security/)

[Microsoft 365合 規](/microsoft-365/compliance/)

[Microsoft 合規性方案](/microsoft-365/compliance/offering-home)