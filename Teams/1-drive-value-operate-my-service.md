---
title: Microsoft Teams作業指南
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Teams服務管理所需的工作和活動，包括監控服務健康情況，以及評估和確保網路品質和使用狀況。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 614b3a16a5c0d59a63f06d1328c68f42e3497af5
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823418"
---
# <a name="operate-my-service"></a>營運我的服務

本文提供貴組織成功操作雲端語音服務需求的概觀。 藉由正確操作雲端語音服務，您可以確保為組織提供高品質、可靠的體驗。

## <a name="introduction-to-the-operations-guide"></a>操作指南簡介

操作指南提供您Microsoft Teams服務管理功能中所有必要工作和活動的概觀。

服務管理是一個廣泛的主題，涵蓋Microsoft Teams服務在部署並啟用使用者之後的日常作業。 Teams服務包含Microsoft 365或Office 365，以及部署在內部部署 (例如網路) 的基礎結構元件。

服務管理的概念對大多陣列織來說可能不是新的概念。 您可能已經實作與現有服務相關聯的程式和工作。 不過，當您今天規劃服務管理以支援未來Teams時，或許可以擴充目前的程式。

服務管理包含管理端對尾Teams的所有活動和程式。 如先前所述，服務管理的某些元件是Microsoft 365或Office 365服務本身所構成的基礎結構，由 Microsoft 負責，而您這個客戶則會對您的使用者負責管理您所提供之Teams、網路和端點的各個層面。

本指南中的工作和活動分為八個類別，如下圖所述。 下列各節會逐一展開這些類別。

![描述工作和活動類別清單的圖表。](media/operate-my-service-image1.png "描述服務管理為Teams所組成之工作與活動的類別清單的圖表。圖表也說明服務管理主要是客戶的工作。")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定如何實作Teams作業。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>完整檢閱操作指南。</li><li>實作符合貴組織目標的操作策略，以提供雲端語音工作負載的品質及可靠性。</li><li>檢 [閱監視通話品質](monitor-call-quality-qos.md)。</li><li> 實作作業策略以定期執行體驗品質檢閱，以確保您的雲端語音部署在最尖峰時運作。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>營運角色對應

您在 [想像] 階段進行作業的基礎規劃至關重要，因為作業活動會在第一個試驗使用者啟用時開始。 本指南列出必須在每日、每週、每月或視需要執行的活動和工作，以維持高品質Teams部署。 本指南提供如何執行這些重要活動和工作的知識和指導方針。

成功部署的其中一個重要元件是確保您在 [想像] 階段初期所做的規劃包含決定誰將負責執行特定活動。 在您瞭解哪些工作和活動套用到您的部署之後，您必須瞭解這些工作，後面接著您指派給他們的群組或個人。

您識別的每一個小組都必須檢閱並同意已識別的工作和職責，並開始準備。 這可能包括訓練和整備、提供教職員計畫更新，或確保外部提供者已準備好進行配送。

在大多數案例中，本指南中定義的活動和角色應有效，但每個Teams部署都是唯一的，因此，您可以使用本指南做為起點，自訂活動和預設角色以符合您的需求。

確保每個可負責的小組都能夠深入瞭解執行服務所需的活動。 在第一次試驗開始之前，每個小組都必須接受並簽署他們在貴組織中的責任。

合約簽訂之後，對應的團隊應開始運作其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td>
<td><ul><li>使用此檔可促進操作角色對應練習。</li><li>與個別支援小組開會，以指派必要活動清單中每個專案的名稱。</li><li>接受或簽核指派的角色。</li><li>確定對應的小組有適當的訓練、整備和資源，以完成所需的活動。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams服務相依性

Microsoft Teams整合Microsoft 365或Office 365的技術，以提供團隊合作中心。 範例包括：

-   Azure Active Directory (Azure AD) 提供Teams的驗證和授權服務。

-   Exchange Online提供進階功能，例如法律保留和電子探索。

-   SharePoint Online 提供在頻道中共用檔案的功能，而商務用 OneDrive提供在私人聊天中共用檔案的機制。

組織也可以運用內部部署基礎結構中的現有投資。 例如，現有的內部部署的 Active Directory帳戶可以利用 Azure AD 連線來進行驗證。 某些版本的 Exchange Server 可用來取代 Exchange Online。

這些技術整合在一起，為使用者提供豐富的共同作業和智慧型通訊套件。 這種緊密整合是Teams的主要優點，但也推動了跨這些技術的服務管理需求。

本指南涵蓋管理Teams服務的重點領域。 您很可能有Teams所依之支援技術的服務管理計畫。 如果沒有，您也必須為這些技術元件建立適當的服務管理計畫， (內部部署和線上) 。 這有助於確保您的使用者享有高品質、可靠的Teams體驗。

#### <a name="references"></a>引用 

[Microsoft Teams概觀](teams-overview.md)

[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)

[SharePoint Online 和 商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)

[Microsoft Teams與商務用 Skype共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>營運指南活動

下列各節提供成功操作Microsoft Teams服務所需的活動概觀。 其中包括工具、關聯式資訊及其他內容的參照，以協助您瞭解活動並協助整備計畫。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>監控服務健康情況

請務必瞭解Microsoft Teams服務的整體健康情況，這樣您才能主動提醒組織中的其他人任何會影響服務的事件。 如先前所述，Teams取決於其他Microsoft 365或Office 365服務，例如 Azure Active Directory、Exchange Online、SharePoint Online 和商務用 OneDrive。 因此，您同樣必須監控相依服務的健康情況。

將此活動整合到您的事件管理程式中，以主動通知使用者、技術服務人員和您的作業小組，以準備處理使用者升級。

下列各節說明您可以運用的工具來監控影響Teams服務的服務[事件](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1)。 下表包含每個工具的優點摘要，以及您應該使用每個工具的時機。

| 監控工具                       | 優點                                            | 何時使用                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 系統管理中心                     | 可在任何裝置上使用支援的瀏覽器。 | 當您不需要即時通知時使用。                                          |
| Microsoft 365或Office 365 系統管理員應用程式                  | 提供推播通知到您的行動裝置。  | 當您外出時需要收到服務事件通知時使用。                  |
| Microsoft System Center               | 與 Microsoft System Center 整合。           | 當您需要進階監視功能和通知支援時使用。                       |
| Microsoft 365或 Office 365 Service Communications API | 以程式設計方式存取Microsoft 365或Office 365服務健康情況。   | 當您需要與協力廠商監視工具整合，或想要建立您自己的解決方案時使用。 |

> [!NOTE]
> 只有獲指派 **全域系統管理員** 或 **服務系統管理員** 角色的人，才能檢視服務健康情況。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心監控

[Microsoft 365 系統管理中心提供](https://portal.office.com/)[服務健康情況儀表板](https://portal.office.com/adminportal/home#/servicehealth)，您可以在此檢視目前Teams服務的健康情況，以及相依的服務。

### <a name="monitoring-with-the-mobile-app"></a>使用行動裝置應用程式監控

Microsoft 365或Office 365 系統管理員應用程式可在 Apple iOS、Android 以及Windows (電腦和行動) 上使用。 應用程式會提供服務系統管理員有關服務健康情況和近期變更的資訊。 應用程式支援推播通知，在張貼建議後，幾乎可以立即提醒您。 這可協助您隨時掌握服務的狀態、健康情況，以及任何即將進行的變更。 通知支援會使其成為系統管理員建議的監控工具。 如需詳細資訊，請參閱：

[Office 365 系統管理員行動裝置 App](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下載Office 365 系統管理員行動裝置 App](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center監控

Microsoft System Center 是一個整合式管理平臺，可協助您管理資料中心、用戶端裝置和混合式雲端 IT 環境。 Office 365使用 System Center 的系統管理員現在可以選擇匯入 Office 365 管理套件，以便在 System Center 中檢視 Operations Manager 中的所有服務通訊。 使用此工具可讓您存取訂閱服務的狀態、作用中且已解決的服務事件，以及訊息中心通訊 (即將進行的變更) 。 如需詳細資訊，請參閱下列 [部落格文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果您利用System Center監控Teams服務健康情況 (和相依服務) ，您可以進一步自訂管理套件，以提醒或通知已識別為要對事件做出反應的特定群組或個人。
這些群組可以包括服務擁有者、技術服務人員、第二層和第三層支援群組，以及貴組織的事件管理員。

### <a name="monitoring-for-advanced-scenarios"></a>監控進階案例

您可以利用 Office 365 Service Communications API 以程式設計方式存取Office 365服務健康情況和變更，來監控服務健康情況和近期變更。 使用此 API 建立您自己的監視工具，或將現有的監視工具連線至Office 365服務通訊，以可能簡化您監視環境的方式。 如需詳細資訊，請參閱[Enterprise開發人員的Office 365](https://developer.microsoft.com/office)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動               | 描述                                                                                                                                                                                                               | 節奏   | 已指派小組 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 監控服務健康情況 | 使用可用的工具，主動監控Microsoft Teams服務健康情況、 (和從屬服務) 。 相依服務包括：Exchange Online、SharePoint Online、商務用 OneDrive、Azure Active Directory。 | 即時 |               |
| 事件通知  | 通知內部專案關係人影響Teams服務的事件。 內部專案關係人可以包含使用者、技術服務人員和事件管理員。                                                                          | 視需要 |               |

### <a name="references"></a>引用 

[如何檢查Office 365服務健康情況](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[確認Microsoft Teams的服務健康情況](service-health.md)

[服務健康情況與持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理組織變更

Microsoft Teams是雲端式服務。 如此一來，我們也能夠快速地提供新功能。 提供持續創新對組織有明顯的好處，但您必須在組織內適當管理這些變更，以避免使用者抵觸或升級至技術服務人員。

系統會自動向您的使用者推出Teams更新。 您的使用者永遠會有Teams服務中提供的最新用戶端和功能。 您無法管理使用者推出Teams更新，因此透過有效通訊、訓練和採用程式管理變更至關重要。 如果您的使用者已經瞭解此變更、瞭解其優點，並進一步運用新功能 &mdash; ，他們就能更快速地適應並歡迎變更。

### <a name="monitoring-for-change"></a>監控變更

變更管理的第一個步驟是監控針對Teams所規劃的變更。 監控這些變更的最佳來源是[Office 365藍圖](https://products.office.com/business/office-365-roadmap)，其中列出目前正在開發、向客戶推出或已完全啟動的功能。 您可以使用提供的篩選來搜尋Teams特定功能，或是將藍圖下載到Excel檔案以進一步分析。 針對每個功能，藍圖會提供簡短描述，以及預期的發行日期。

在[Microsoft Teams部落](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)格中，您可以瞭解最佳做法、趨勢，以及產品更新Teams新聞。 預期會在這裡宣佈要Teams的主要功能更新。 您也可以透過 RSS 摘要訂閱部落格。 接著，您可以將[RSS 摘](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)要直接新增至Teams頻道，如此一來，所有重要消息都會直接在Teams內傳遞。

發行的所有功能都會記錄在[Microsoft Teams 的版本資訊](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)中。
您可以在這裡找到針對桌上型電腦、網路和行動裝置發行的功能清單。 同一組版本資訊也可在 [說明] **的 [新增功能** ] 索引卷 [標上使用](get-help-in-microsoft-teams.md)。

熟悉可用資源，並確保您指派適用的擁有者監控變更。

### <a name="planning-for-change"></a>規劃變更

現在您已經知道Teams服務即將變更，下一個步驟是準備並據此規劃。 評估每個變更，以判斷哪些變更需要與使用者溝通、宣傳活動、支援小組或使用者的訓練，或功能評估和採用行銷活動。 這是貴組織中變更管理小組的主要角色。 以下是可協助您規劃變更的範例資料表集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：雲端錄製 (發行日期：2018 年 1 月) 

**一般曲目**

| 變更整備 | 地位   | 附注/後續步驟 | 擁有者 |
|----|----|----|-----|
| 法律檢閱   | 完成     | 這項功能是讓訓練團隊上線的必要條件。 | Project小組  |

**技術變更管理**

|       變更整備       | 地位 |                      附注/後續步驟                      |    擁有者     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     需要 IT 變更      |  是   | 管理員只需要為已識別的使用者啟用錄製功能。 | 支援小組 |
| 技術整備完成 |  是   |                                                            | 支援小組 |
|                              |        |                                                            |              |

**使用者變更管理** 

| 變更整備 | 地位   | 附注/後續步驟 | 擁有者 |
|----|----|----|-----|
| 使用者影響                  | 低                  |                                                                 |                        |
| 需要使用者整備      | 是                  |                                                                 |                        |
| 通訊準備就緒         | 否                   | 已擬定通訊電子郵件，等待檢閱。            | 通訊小組    |
| 訓練準備就緒               | 是                  | 訓練將運用現有的 Microsoft 影片。                | 訓練小組          |

**狀態追蹤**

| 變更整備 | 地位   | 附注/後續步驟 | 擁有者 |
|----|----|----|-----|
| 發行狀態               | 進行中          | 高階主管贊助者正在等待檢閱。               | 變更管理小組 |
| 版本簽核             |                      |                                                                 |                        |
| 發行日期                 |                      |                                                                 |                        |

如需使用Teams規劃變更管理的詳細資訊，請參閱[建立Microsoft Teams的變更管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動               | 描述                                                                                                                                                                                                                | 節奏   | 已指派小組 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 監視變更     | 監控Microsoft Teams服務近期變更。                                                                                                                                                                   | 日常     |               |
| 規劃變更    | 評估並規劃新功能，包括通訊計畫、宣傳活動和訓練。                                                                                                     | 視需要 |               |
| 使用者整備             | 執行目標通訊、意識或訓練活動，以確保使用者已準備好迎接即將到來的變更。                                                                                                        | 視需要 |               |
| 支援小組整備 | 執行目標溝通、意識或訓練活動，以確保支援小組已準備就緒。 支援小組可以包括「白眼套」團隊、技術服務人員、第 2 層或第 3 層支援、外部合作夥伴等等。 | 視需要 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>評估Teams使用量

初始試驗開始之後，建立一般頻率以測量實際Teams使用量至關重要。 這可讓您的組織深入瞭解實際使用量如何與您在 [想像] 階段預測的使用量一致。 雖然本節著重于Teams使用量，但這應是衡量及評估Office 365使用狀況的更廣泛努力的一部分。

在部署初期經常檢閱使用方式可讓您有機會：

-   驗證使用者是否使用Teams。

-   在組織中建立重大問題之前，先找出可能的採用挑戰。

-   瞭解想像階段需求與實際使用量之間是否有差異。

如果使用方式與預期的不同，可能是部署問題、採用計畫無法正確執行，或是發生其他問題。 根據低使用量背後的實際原因，服務系統管理員必須與相關小組共同作業，以協助移除使用障礙。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用Microsoft 365 系統管理中心測量使用量

來自 Teams 的使用狀況資料可在 [報告] 儀表板中使用。 Teams使用狀況資料可在三個不同的報告中找到。 第一份報告提供使用者如何使用Office 365中的各種服務進行通訊和共同作業的跨產品檢視。 您可以在這裡找到此報告：[Office 365作用中使用者報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

另外兩個報告是Teams特定的，並從使用者和裝置的觀點提供Teams使用方式的進一步詳細資料。 您可以在這裡找到這兩個報告：

[Microsoft Teams裝置使用方式報告](/microsoftteams/teams-analytics-and-reports/device-usage-report)

[Microsoft Teams使用者活動報告](/microsoftteams/teams-analytics-and-reports/user-activity-report)

#### <a name="required-permissions"></a>必要許可權

系統管理中心的使用方式報告可以由獲指派全域管理員角色的人員存取，或是Exchange系統 **管理員****、****商務用 Skype** 系統管理員SharePoint系統 **管理員)  (** 特定產品的系統管理員角色。

此外，報表 **閱讀** 程式角色也適用于需要存取報表，但不執行任何需要系統管理員層級許可權的工作的使用者。 您指派這個角色以提供使用方式報告給任何專案關係人，以監控並推動採用。 如需可用不同角色的詳細資訊，請參閱[關於Office 365系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>評估使用量

在您使用 [報告] 儀表板來測量使用量之後，請務必將測量使用量與您在專案 [想像] 階段定義 (KSIS) 任何關鍵成功指標進行比較。 您可以定義可能定義為使用中的 KSI，或間接連結到使用中的 KSI。

在繼續推出至其他網站或使用者之前，請務必先找出實際和計畫使用量之間的任何變異數。 您可能會將組織學習識別為此活動的一部分，藉此確保下一批網站或使用者不會遇到相同的問題。

首先，請確定這是採用還是技術問題。 首先依序調查下列專案以判斷問題所在位置。

1.  執行體驗品質檢閱以驗證品質 (請參閱[改善及監控Teams的通話品質，](monitor-call-quality-qos.md)以取得詳細) 。

2.  請與技術服務小組合作，確認沒有造成使用者無法存取或使用服務的趨勢技術問題。 如果問題趨勢確實存在，請使用本文稍後的 [端點疑難排解](#endpoint-troubleshooting) 一節，嘗試在取得支援之前解決問題。

3.  與訓練和採用小組合作，收集使用者的直接意見反應 (請參閱本文稍後) [評估使用者情緒](#assess-user-sentiment) ，並檢查意識和採用活動的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動                         | 描述                                                                                                                      | 節奏   | 已指派小組 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 測量使用 (啟用階段)  | 當網站在啟用階段期間持續上線時，測量及評估Teams使用量。 視需要解決使用問題。 | 每週    |               |
| 測量使用 (磁片磁碟機值階段)                            | 在) 完成部署之後，測量並評估磁片磁碟機值階段 (中的Teams使用量。 視需要解決使用問題。 | Biweekly  |               |
| 更新採用計畫             | 根據測量使用量與規劃目標的比較方式，更新採用計畫。                                         | 視需要 |               |

### <a name="references"></a>引用 

[關於Microsoft 365 系統管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 系統管理中心中的活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>評估使用者情緒

瞭解使用者情緒可以做為衡量Teams部署成功的關鍵指標。 使用者意見反應可能會推動貴組織中的變更;這可能包括變更您的通訊計畫、訓練程式，或您為使用者提供支援的方式。

請務必提早取得意見反應，並繼續評估專案及其他期間的使用者情緒。 使用下列指引來決定貴組織尋找意見反應的時間間隔：

-   **專案開頭**：透過在專案開始時評估使用者的情緒，您可以提早瞭解使用者對於其Teams體驗的感覺。

-   **重大里程碑之後**：透過收集整個專案生命週期的意見反應，您可以持續評估使用者的情緒，並視需要進行變更。 這在主要里程碑之後特別有用。

-   **Project總結**：評估專案結尾的使用者情緒會告訴您已完成的狀況以及仍需完成工作的位置，並可讓您比較結果與上一個問卷。

-   **持續** 進行：繼續無限期地衡量使用者的情緒。 使用者情緒的改變可能是由於貴組織環境的變更或Teams服務的變更所致。 您可以定期測量使用者情緒，瞭解服務管理小組的效能，以及貴組織對Teams服務變更的回應程度。

您可以透過許多不同的方法來評估使用者的情緒。 這些內容可能包括電子郵件問卷、個人或電話式面試，或直接在Teams或Yammer中建立意見反應頻道。 如需詳細資訊，請參閱[Microsoft Teams中使用者意見反應方法的最佳做法](best-practices-feedback.md)。

您也可以使用全業界的方法來評估稱為網路促銷員分數 (NPS) 的使用者情緒，如下一節所述。

### <a name="nps"></a>NPS 

NPS)  (Net promoter 分數是全業界客戶忠誠度衡量標準，也是用來評估使用者情緒的好方法。 NPS 可以藉由詢問兩個問題來計算：「您建議同事Teams的可能性如何？」，後面接著手繪多邊形問題「為什麼？」

NPS 是一種索引，範圍從 –100 到 100 不等，用來衡量客戶建議公司產品或服務的可能性。 NPS 是以透過電子郵件或其他電子方式傳送給使用者的匿名問卷為基礎。 NPS 會衡量提供者與消費者之間的忠誠度。 它只包含一個問題，要求使用者為 1 到 10 的體驗評分，並可選擇提供其他批註。 使用者接著會根據下列評分進行分類：

-   9 或 10 位是推廣者：將為您的服務推廣並為其他人提供動力的熱衷愛好者。

-   7 或 8 為被動：滿意但不具熱情、容易受到其他服務或服務的侵害。

-   從 1 到 6 是減損者：會損害您的服務並阻礙成長的不滿意的客戶。

![顯示 NPS 比例的圖表。](media/operate-my-service-image2.png "此圖表會示範 NPS 縮放比例。它顯示 0 到 6 的排名是減量器，7 到 8 是被動的，而 9 到 10 是升階者。")

雖然基本 NPS 數位很有用，但您會從分析使用者批註獲得最大價值。 它們可協助您瞭解使用者為何 (或不建議其他人) Teams。 這些批註可提供寶貴的意見反應，協助專案或服務管理小組瞭解提供優質服務所需的調整。

若要提供 NPS 問卷給您的組織，您可以運用您最愛的線上問卷工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要執行工作

| 活動              | 描述                                                                                                                                                                         | 節奏   | 已指派小組 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 評估使用者情緒 | 使用問卷或面試，或透過Teams或Yammer中的意見反應頻道來擷取和評估使用者的情緒。                                                                 | 視需要 |               |
| 更新採用計畫 | 根據使用者意見反應推動貴組織中的變更;這可能包括變更您的通訊計畫、訓練程式，或您為使用者提供支援的方式。 | 視需要 |               |

### <a name="references"></a>引用 

[Net Promoter Score](https://en.wikipedia.org/wiki/Net_Promoter)

[使用Yammer收集意見反應](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[使用者意見反應的最佳做法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理網路品質

許多核心規劃元素會進入優化、以滑鼠右鍵調整及補救您的網路基礎結構，以確保有高品質且有效率的Microsoft Teams服務路徑。 我們的 [網路整備](3-envision-evaluate-my-environment.md#network-readiness) 指導方針涵蓋規劃工作和需求。 由於升級、擴充或其他業務需求，網路通常會隨著時間而改變。 請務必考慮您在網路規劃活動中Teams的需求。

雖然網路規劃是Teams部署的重要層面，但同樣務必確保網路保持良好狀態，並根據變更商務或技術需求維持在最新狀態。

為了確保網路健康情況，必須定期執行許多作業活動。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動                                                       | 描述                                                                                                                                                                                                                                                                                                                                                                 | 節奏                | 已指派小組 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 監控 Office 365 IP 和 URL                                | 使用提供的[RSS](https://go.microsoft.com/fwlink/p/?linkid=236301)摘要監控[Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)的任何變更，並起始對適用網路群組的變更要求。                                                                                                                                | 日常                  |               |
| 根據OFFICE 365 IP 和 URL 的變更來更新網路 | 更新防火牆 (、Proxy 伺服器、VPN、用戶端防火牆等適用的網路元件) ，以反映[Office 365 URL 和 IP 位址範圍的](/microsoft-365/enterprise/urls-and-ip-address-ranges)變更。                                                                                                                                                              | 視需要              |               |
| 提供建築物資料                                          | 提供更新的子網路資訊給品質冠軍 (或相關專案關係人) ，以確保 [CQD 中的建築物定義](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 保持在最新狀態。 | 視需要              |               |
| 實作變更                                               | 在網路上實作變更以支援變更Teams業務和技術需求。 網路元素可能包括：<ul><li>防火牆</li><li>Vpn</li><li>有線和Wi-Fi網路</li><li>網際網路連線和 ExpressRoute</li><li>DNS</li></ul>     | 視需要              |               |
| 網路監控與報告                               | 使用網路提供者提供的現有協力廠商網路管理工具和報告功能，監控網路端至端的可用性、使用率和容量趨勢。 將趨勢資料用於網路容量規劃。                                                                                                            | 每日、每週、每月 |               |
| 容量規劃                                              | 與Teams服務擁有者共同作業，瞭解變更可能會推動額外容量變更的企業和技術需求。                                | 視需要              |               |
| 網路疑難排解與補救                        | 協助Teams技術服務人員、服務擁有者和重要專案關係人，針對Teams連線、可靠性或品質的相關問題進行疑難排解和補救。 網路元素可能包括：<ul><li>防火牆</li><li>Vpn</li><li>有線和Wi-Fi網路</li><li>網際網路連線和 ExpressRoute</li><li>DNS</li></ul>    | 視需要              |               |
| 災害復原和高可用性測試                | 在網路基礎結構上定期執行高可用性和災害復原測試，以確保它符合 SLO () 或服務層級合約中所述的服務層級目標， (Teams服務的 SLAs) 。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>引用 

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[建置資料架構](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>評估並確保品質 

所有組織都需要有群組或個人負責品質。 這是服務管理中最重要的角色。 品質冠軍角色會指派給對使用者體驗充滿熱情的人員或群組。
這個角色需要技能來識別環境的趨勢和贊助，才能與其他團隊合作以推動補救。 品質冠軍的最佳人選通常是客戶服務擁有者。 視組織的大小和複雜度而定，這可能會是任何熱衷確保高品質使用者體驗的人員或群組。

品質冠軍運用現有的工具和檔處理常式，例如通話品質儀表板 (CQD) ，以監控使用者體驗、識別品質趨勢，以及視需要進行磁片磁碟機修復。
品質冠軍應該與個別小組合作以推動補救動作，並向指導委員會報告進度和任何公開問題。

請閱讀[改善及監控Teams的通話品質](monitor-call-quality-qos.md)，其中說明哪些活動會評估及提供主要區域的補救指導方針，這些活動對於改善使用者體驗有最大影響。 本文中提供的指導方針著重于使用 CQD 做為報告和調查每個區域的主要工具，並著重于音訊以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接翻譯成視訊和桌面共用的改進。

我們強烈建議您提早將品質冠軍指名。 在註冊之後，他們應該開始熟悉 [監控通話品質](monitor-call-quality-qos.md) 內容及相關的訓練資料。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動                               | 描述                                                                                                                                                                                                                                                                                                 | 節奏                             | 已指派小組 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
|  () ，為高品質之冠軍指名和訓練 | 為品質冠軍進行指名和訓練。                                                                                                                                                                                                                                                                   | 視需要                           |               |
| 執行 (QER) 體驗品質檢閱     | 執行 QER 以識別品質及可靠性的趨勢、檢閱已定義的目標，以及向組織中的重要專案關係人報告。                                                                                                                            | 在部署期間每週 ()  |               |
| 磁片磁碟機修復                      | 根據 QER 評定和結果，協調整個組織的補救工作。                                                                                                                                                                                                           | 視需要                           |               |
| 在 CQD 中更新建築物資料            | 當對網路進行變更時，在 CQD 中更新或新增建築物定義 (請[參閱Upload建築物資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)) 。 | 視需要                           |               |
| 填入品質冠軍角色      | 組織中品質的端對端責任。 這包括：<ul><li>確定定期進行 QER。</li><li>向重要的專案關係人報告品質狀態。</li><li>確定建築物資料定義是最新狀態。</li><li>協調整個組織的補救工作，以確保使用者擁有高品質的Teams體驗。</li></ul>          | 日常                               |               |



### <a name="references"></a>引用 


[在 CQD 中Upload租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[改善及監控Teams的通話品質](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理端點

Microsoft Teams端點可以定義為任何 PC、Mac、平板電腦或行動裝置 (或執行Teams用戶端的任何其他) 裝置。 端 *點* 一詞不僅包含裝置本身，也包含使用者連線到裝置的方式，例如使用裝置的內建麥克風或喇叭、耳機或優化的耳機。 部署之後，端點就不能忘記。 Teams端點需要持續保養和維護。 下列各節說明要著重的特定區域。

### <a name="endpoint-requirements"></a>端點需求

Teams的主要優點之一是用戶端會自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新組建，並在應用程式閒置時下載新用戶端。 Teams行動裝置 App 會透過各自的 App 市集保持最新狀態。

就基礎軟體平臺而言，Teams用戶端的最低需求。 這些需求可能會隨著時間而改變，因此請務必監控這些需求以取得變更。 例如，Teams用戶端擁有最低iOS版本。 如果用戶端使用網際網路瀏覽器，瀏覽器也必須保持在最新狀態。 您可以在取得[Microsoft Teams的客戶](get-clients.md)端中找到支援的平臺清單。

### <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆可能會嚴重影響使用者體驗。
用戶端防火牆可能會影響通話品質，甚至無法建立通話。 在用戶端防火牆上設定適當的排除專案之後，必須根據[Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的資訊，將它們保持在最新狀態。 您的協力廠商廠商將提供如何更新排除專案的特定指導方針。

### <a name="wi-fi-drivers"></a>Wi-Fi驅動程式

Wi-Fi驅動程式可能有問題。 例如，驅動程式可能會在存取點之間有非常積極且不必要的存取點切換，導致通話品質不佳的漫遊行為。 可能會透過體驗品質檢閱發現效能不佳的Wi-Fi驅動程式 (請參閱[改善及監控Teams的通話品質，](monitor-call-quality-qos.md)以取得詳細) 。 實作監控新Wi-Fi驅動程式的品質導向流程至關重要，並確保在部署到一般使用者母體之前已經過測試。

### <a name="endpoint-management"></a>端點管理

 (如耳機) 支援的端點和介面裝置目錄應可供使用及維護。 此目錄將包含已選取並驗證為 [想像] 和 [上線] 階段一部分之核准裝置的清單。 一般而言，系統會針對組織中的每個角色類型選取特定裝置，以符合該角色屬性的需求。 所有端點都有生命週期，您必須管理與這些裝置相關聯的廠商合約、保固、更換、散發及維修原則。

### <a name="endpoint-troubleshooting"></a>端點疑難排解

即使您已遵循先前的指引，貴組織中的使用者仍可能會遇到Teams問題。 雖然問題可能不是端點本身，但問題症狀通常是透過用戶端向使用者顯示。 下列指引旨在提供您可以採取的一般步驟來解決問題;這不是完整的疑難排解指南。 這些步驟是以特定順序提供，但並不一定明確地遵循，而且可能不適用，視問題的性質而定。

1.  **驗證服務健康情況：** 使用者所遇到的問題可能與對Teams服務或其相依服務產生負面影響的事件相關。 在第一個步驟中，建議您確認沒有作用中的服務問題。 請參閱[如何檢查Office 365服務健康情況](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    請記得檢查從屬服務 (的狀態，例如Exchange、SharePoint商務用 OneDrive) 。 如需詳細討論服務健康情況，請參閱上一節 [的監控服務健康情況](#monitor-service-health)。

2.  **驗證用戶端連線：** 連線問題會導致Teams中的功能或登入問題。 我們建議您 (特別針對驗證服務連線) 的新網站或位置。 請確定每個網站已遵循下列[Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)指導方針。 您可以利用 [Microsoft 網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) 來執行連線測試，以驗證已針對雲端語音功能正確開啟媒體埠。 有關如何執行連線測試的詳細步驟，請參閱 [網路整備](3-envision-evaluate-my-environment.md#network-readiness) 指導方針。

3.  **檢查已知問題清單：** 請參 [閱Teams疑難排解](/MicrosoftTeams/troubleshoot/teams)，判斷使用者是否受到下列其中一個問題的負面影響。 如果有解決此問題的) ，請遵循 (提供的因應措施。

4.  **造訪Microsoft Teams社群：**[Microsoft Teams社](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)群為Teams提供專屬空間。 Teams社群提供以Teams為中心的討論清單、部落格文章和公告。 您可以張貼問題或搜尋先前的討論，以取得問題的解決方案。

5.  **連絡Microsoft 支援服務：** 如有線上或電話Teams問題，您可以連絡Microsoft 支援服務。 如需詳細資訊，請參閱 [連絡商務產品的支援](/microsoft-365/admin/contact-support-for-business-products)。
    對於頂級客戶，支援要求可以遵循連絡[Microsoft Teams (Premier 客戶) 的](https://support.microsoft.com/premier/contacts)指引來提出。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動                 | 描述                                                                                                                                                                                                                                                                                                                                                                     | 節奏   | 已指派小組 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 端點需求    | 請確定Teams端點會持續符合Teams在取得Microsoft Teams用戶端中列出的所有軟體[需求](get-clients.md)。                                                                                                                                                                                       | 每月   |               |
| 端點防火牆       | 根據Office 365 [URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)中的資訊，維護端點防火牆上的適當排除專案。 您的協力廠商廠商將會有有關如何維持排除範圍的特定指導方針。 訂閱 [RSS 摘](https://support.office.com/o365ip/rss) 要以自動收到變更通知。 | 視需要 |               |
| Wi-Fi驅動程式            | 測試並更新電腦上的Wi-Fi驅動程式。 使用 CQD ([改善及監控Teams) 的通話品質](monitor-call-quality-qos.md)來驗證結果。                                                                                                                                                                                                                                                                   | 視需要 |               |
| 端點管理      | 維護支援的端點和介面裝置的目錄， (例如耳機) 。 管理廠商合約、保固、散發、更換和維修原則。                                                                                                                                                                                                        | 每月   |               |
| 端點疑難排解 | 疑難排解工作可能包括驗證連線、諮詢已知問題清單、記錄收集、分析，以及向Microsoft 支援服務或協力廠商廠商升級。                                                                                                                                                                                               | 視需要 |               |

### <a name="references"></a>引用 

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[取得 Microsoft Teams 用戶端](get-clients.md)

[Microsoft Teams社群](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)

[確認Microsoft Teams的服務健康情況](service-health.md)

[連絡商務產品的客戶支援 - 系統管理說明](/microsoft-365/admin/contact-support-for-business-products)

[連絡頂級支援](https://support.microsoft.com/premier/contacts)

[疑難排解Teams影片](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署Microsoft Teams服務之後，您必須執行數個與其系統管理相關的活動。 活動範圍從管理服務和個別使用者，到容量規劃和布建授權和電話號碼。 下列各節涵蓋一些常見的系統管理工作。

### <a name="service-administration"></a>服務系統管理

Teams服務有多個設定，可以設定整個租使用者。
對租使用者設定所做的變更會影響已啟用Teams的所有使用者。 如需這些設定的詳細清單，請參閱[管理組織的Microsoft Teams設定](enable-features-office-365.md)。

### <a name="user-administration"></a>使用者系統管理

若要支援使用者，組織可能需要任何數量的相關工作—特定工作會因組織而異。 最後，這些工作必須由已獲指派這些營運職責的支援小組來管理。 下列工作通常需要在Teams中支援使用者。

#### <a name="general-tasks"></a>一般工作

[管理使用者存取Microsoft Teams](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>電話系統 的一般工作

[指派、變更或移除使用者的電話號碼](./assign-change-or-remove-a-phone-number-for-a-user.md)

[指派或變更使用者的緊急位址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[新增、變更或移除貴組織的緊急位置](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[建立和管理撥號對應表](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>音訊會議 的一般工作

[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)

[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>授權管理

隨著貴組織的成長或合約的增加，請務必針對目前和未來的需求規劃授權。 除了雲端語音功能[電話系統和音訊會議](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing#requirements-for-audio-conferencing)授權之外，還有基本[Teams](here-s-what-you-get-with-phone-system.md)授權。

針對Teams，電話系統授權需要相關聯[的通話方案](calling-plan-landing-page.md)授權。 通話方案授權可讓您撥打和接聽國內及/或國際電話。 這些方案是以使用方式為基礎，並且有與這些方案相關聯的分鐘集區。 布建 [通訊點](what-are-communications-credits.md) 數可確保您永遠不會服務用完。

音訊會議允許付費電話撥入式會議和國內撥出式會議服務。 免付費電話撥入式會議或非國內撥出案例可能會導致您產生需要 [通訊點數](what-are-communications-credits.md) 的額外費用。

通訊點數可以補充通話方案和音訊會議授權。 通話方案授權和通訊點數都是以使用方式為基礎，因此需要受到監控和布建。

您可以利用 [PSTN 使用方式報告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) ，協助您監控通話方案通話分鐘數和通訊點數的使用方式。 根據此活動的結果，您可以據以調整您的授權。 我們即將提供 [PSTN 分鐘集區](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 報告，以更有效率地協助這項工作。

### <a name="telephone-number-management"></a>電話號碼管理

在Teams中取得號碼的方法有兩種：您可以從另一個提供者移轉電話號碼，或直接從 Microsoft 的號碼庫存布建電話號碼。 這兩種方法在 [取得使用者的電話號碼](getting-phone-numbers-for-your-users.md)中都有說明。

您可以從 Microsoft 的電話號碼庫存中布建的電話號碼數量有限制。 限制是由您可以 [取得多少電話號碼？](how-many-phone-numbers-can-you-get.md)中詳述的數個因素所決定。
限制取決於號碼類型：免付費服務號碼、付費服務號碼以及使用者 (使用者) 號碼。 每個都有其本身的限制，而且必須獨立管理。 如果您快要達到限制 (或已達到限制) ，您可以套用對限制的遞增。 此程式會在上一個段落中一文中說明。

有時候，在提供服務的地區中，可能無法布建數位。 如需要求號碼程式的相關資訊，請參閱 [管理組織的電話號碼](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>團隊建立 (選擇性) 

根據預設，在Exchange Online中擁有信箱的所有使用者都有權建立Microsoft 365群組，因此Microsoft Teams中的團隊。 如果您想要更緊密地控制及[限制建立新團隊](assign-roles-permissions.md#permissions-to-create-teams) (，並因此建立新Microsoft 365群組) ，您可以將群組建立和管理許可權委派給一組系統管理員。 如果貴組織想要執行此選項，請參閱本文所述的程式，允許使用者提交由指派的小組處理的要求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/視需要的工作

| 活動                    | 描述                                                                                                                                                                                                                                                                                                                                                                                                             | 節奏   | 已指派小組 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服務系統管理      | 管理全租使用者Teams設定。                                                                                                                                                                                                                                                                                                                                                                           | 視需要 |               |
| 使用者系統管理         | 在 Teams 中管理使用者型設定和授權。                                                                                                                                                                                                                                                                                                                                                           | 視需要 |               |
| 授權管理          | 利用 [PSTN 使用方式報告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 和 [PSTN 分鐘集區](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 報告，規劃使用者和消費型授權 (通話方案和通訊點數) 的目前和未來需求。 | 每週    |               |
| 電話號碼管理 | 管理未來成長可用的電話號碼，並調整庫存量以符合您的組織需求。                                                                                                                                                                                                                                                                                                | 每週    |               |
| 團隊建立 (選擇性)     | 檢閱和處理建立團隊的要求。                                                                                                                                                                                                                                                                                                                                                                          | 視需要 |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>改善及監控通話品質

[改善及監控Teams的通話品質](monitor-call-quality-qos.md)包括一組活動，這些活動會評估及提供主要區域的補救指引，對改善使用者體驗有最大影響，如下所示。

![在體驗品質檢閱期間要檢查的區域圖表。](media/plan-my-service-management-image2.png "在體驗品質檢閱期間檢查的關鍵領域：音訊、可靠性和使用者問卷調查結果。")

透過持續評估和補救指南中描述的區域，您可以降低這些區域對使用者體驗造成負面影響的可能性。 在部署中遇到的大部分使用者體驗問題都可以分組為下列類別：

-   不完整的防火牆或 Proxy 設定

-   不佳的Wi-Fi涵蓋範圍

-   頻寬不足

-   VPN

-   使用不優化或內建的音訊裝置

-   有問題的子網或網路裝置

[改善及監控Teams通話品質](monitor-call-quality-qos.md)中提供的指引著重于使用通話品質儀表板 (CQD) Online 做為報告和調查所述每個區域的主要工具，並著重于音訊以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接翻譯成視訊和桌面共用的改進。

我們強烈建議您提早將品質冠軍指名。 在參與之後，他們應該開始熟悉[改善及監控Teams通話品質](monitor-call-quality-qos.md)中的內容。

<!--ENDOFSECTION-->