---
title: Microsoft Teams|服務管理|品質
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 管理服務所需的工作Teams活動，包括監控服務健康情況，以及評估及確保網路品質和使用狀況
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c70b3c8300a8a11c8687da03c35991f80a37c8fd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849506"
---
# <a name="operate-your-service"></a>營運您的服務

![升級歷程圖，強調營運優化階段。](media/upgrade-banner-op-excellence.png "升級歷程的階段，強調營運優化階段")

本文是升級過程中營運優化階段的一部分，一旦完成從 商務用 Skype 升級到 Teams。

本文概觀說明升級後，Teams組織成功執行應用程式的需求。 您可以正確Teams服務，確保為貴組織提供高品質、可靠的體驗。

## <a name="introduction-to-the-operations-guide"></a>操作指南簡介

操作指南提供您所有工作與活動概觀，做為服務管理功能的一Microsoft Teams。

服務管理是一個廣泛的主題，涵蓋服務部署及啟用後Microsoft Teams服務之日常作業。 服務Teams包括Microsoft 365或Office 365部署于內部部署之基礎結構元件，例如 (網路) 。

服務管理的概念對於大多陣列織來說，很可能不是一個新概念。 您可能已經實施與現有服務相關聯的程式與工作。 也就是說，當您今天規劃服務管理以支援未來的服務管理時，Teams擴充目前的程式。

服務管理包含管理端對端管理Teams活動與程式。 如先前所述，服務管理的一些元件 ，即 Microsoft 365 或 Office 365 服務本身所組成的基礎結構，是由 Microsoft 負責，而客戶則負責管理 Teams、網路和端點的各個層面。

本指南中的工作和活動會分成八個類別，如下圖所示。 以下各節將展開這些類別。

![描述工作與活動類別清單的圖表。](media/operate-my-service-image1.png "描述服務管理之工作與活動類別清單的圖表Teams組成。圖表也說明服務管理主要是客戶的工作。")

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定如何針對 Teams。</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>完整閱覽作業指南。</li><li>執行符合貴組織目標的操作策略，以交付Teams品質和可靠性。</li><li>檢閱體驗品質檢閱指南。</li><li> 執行作業策略，定期執行體驗品質檢閱，以確保您的Teams部署處於最佳狀態。</li></ul></td></tr>

</table>

### <a name="operational-role-mapping"></a>操作角色映射

在構想階段期間，您針對作業所進行規劃至關重要，因為第一個試驗使用者啟用時，作業活動即會開始。 本指南列出必須每天、每週、每月或需要執行的活動和工作，以維護高品質的Teams部署。 本指南提供如何執行這些重要活動和工作的知識與指引。

成功部署的其中一個關鍵元件，是確保您在構想階段早期進行的計畫包括決定誰負責執行特定活動。 找出哪些工作和活動適用于您的部署之後，您必須瞭解並遵循您指派給這些工作與活動的群組或個人。

您識別的每個小組必須審查並同意所識別的工作與職責，並開始準備。 這可能包括訓練和準備、提供人員配置計畫更新，或確保外部提供者準備好提供。

本指南中定義的活動和角色在大部分情況下應該有效，但每個部署Teams都是唯一的;因此，您可以使用本指南做為起點，自訂活動與預設角色，以滿足您的需求。

確保每個負責的團隊都瞭解執行服務所需的活動。 第一個試驗開始之前，每個小組必須接受並簽署貴組織的責任。

在簽訂合約之後，對應的團隊應該開始執行其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td>
<td><ul><li>使用這份檔可協助進行操作角色的繪圖作業。</li><li>與各自的支援小組開會，將名稱指派給所需活動清單中的每個專案。</li><li>取得指派角色的接受或簽收。</li><li>請確定對應的團隊擁有適當的訓練、準備狀態和資源，以完成所需的活動。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams服務相依性

Microsoft Teams將整個Microsoft 365和Office 365技術彙集在一起，為團隊合作提供樞紐。 範例包括：

- Azure Active Directory (Azure AD) 提供驗證和授權服務Teams。

- Exchange Online提供進位功能，例如法律保留與電子探索。

- SharePointOnline 提供在頻道中共用檔案的能力，商務用 OneDrive提供在私人聊天中共用檔案的機制。

組織也可以利用內部部署基礎結構的現有投資。 例如，現有的內部部署 Active Directory 帳戶可以運用 Azure AD 連線。 您可以用Exchange Server版本來Exchange Online。

這些技術彙集在一起，為使用者提供豐富、共同合作且智慧型通訊套件。 這種緊密整合是Teams的主要優點，但也推動跨技術的服務管理需求。

本指南涵蓋管理服務管理Teams領域。 您很可能已經針對您依賴的支援技術，有Teams方案。 如果沒有，您也需要為內部部署和線上 (技術元件建立) 方案。 這可協助確保您的使用者享有高品質、可靠的Teams。

#### <a name="references"></a>引用

[概觀Microsoft Teams](teams-overview.md)

[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)

[線上SharePoint與商務用 OneDrive互動的方式Microsoft Teams](sharepoint-onedrive-interact.md)

[Microsoft Teams共存商務用 Skype互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>作業指南活動

下列各節提供成功執行服務所需的活動Microsoft Teams概觀。 它們包括參考工具、關係資訊和其他內容，以協助您瞭解活動，並協助進行準備計畫。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>監控服務健康情況

您必須瞭解服務的整體健康情況Microsoft Teams，以便主動提醒貴組織中其他人任何影響服務的事件。 如先前所述，Teams依賴其他 Microsoft 365 和 Office 365 服務，例如 Azure Active Directory、Exchange Online、SharePoint Online 和 商務用 OneDrive。 因此，監控從屬服務的健康情況也相當重要。

將此活動納入事件管理程式，主動通知使用者、技術支援人員及您的營運小組，準備處理使用者升級。

下列各節說明您可以用來監控影響服務服務之服務事件[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1)Teams工具。 下表包含每個工具的好處摘要，以及您應該何時使用每個工具。

| 監控工具 | 優點 | 使用時間 |
|---|---|---|
| Microsoft 365 系統管理中心 | 可從任何具有支援瀏覽器的裝置使用。 | 當您不需要即時通知時，請使用。 |
| Microsoft 365 系統管理應用程式 | 提供推入通知至您的行動裝置。 | 當您在外時需要收到服務事件通知時，請使用。 |
| Microsoft System Center | 與 Microsoft System Center。 | 當您需要進一級的監控功能和通知支援時，請使用。 |
| Microsoft 365服務通訊 API | 以程式Microsoft 365存取Office 365服務健康狀態。 | 當您需要整合協力廠商監控工具或想要建立您自己的解決方案時，請使用。 |

> [!NOTE]
> 只有指派全域系統管理員或服務系統管理員 **角色的個人才能** 查看服務健康狀態。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

此[Microsoft 365 系統管理中心](https://portal.office.com/)服務健康情況[儀表板](https://portal.office.com/adminportal/home#/servicehealth)，您可以在其中查看從屬服務Teams服務目前的健康情況。

### <a name="monitoring-with-the-mobile-app"></a>使用行動應用程式監控

此Microsoft 365 系統管理應用程式可在 Apple iOS、Android 和 pc Windows (行動) 。 應用程式會提供系統管理員服務健康情況及近期變更的資訊。 應用程式支援推入通知，可在公告發布後立即提醒您。 這可協助您隨時瞭解服務的狀態、健康情況，以及任何即將進行的變更。 通知支援使它成為建議系統管理員的監控工具。 詳細資訊，請參閱：

[Microsoft 365 系統管理行動應用程式](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下載 Microsoft 365 系統管理行動應用程式](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center

Microsoft System Center是一個整合式管理平臺，可協助您管理資料中心、用戶端裝置和混合式雲端 IT 環境。 Microsoft 365或Office 365系統管理員System Center現在可以選擇輸入管理套件，讓他們可以在 System Center 中查看 Operations Manager 內的所有服務通訊。 使用此工具，您可以存取訂閱服務的狀態、使用中和已解決的服務事件，以及訊息中心通訊 (變更) 。 若要詳細資訊，請參閱下列 [部落格文章](https://www.microsoft.com/en-us/microsoft-365/blog/2014/07/29/new-office-365-admin-tools/)。

如果您利用 System Center 監控 Teams 服務健康情況 (和從屬服務) ，您可以進一步自訂管理套件，以提醒或通知已識別以對事件做出回應的特定群組或個人。
這些群組可以包含貴組織中服務擁有者、技術支援人員、第二層和第三層支援群組，以及事件管理員。

### <a name="monitoring-for-advanced-scenarios"></a>監控進位案例

您可以利用服務通訊 API 以程式化方式存取服務健康情況及變更，以監控服務健康情況及即將到來的變更。 使用此 API 建立您自己的監控工具，或將現有的監控工具連接到Microsoft 365或Office 365通訊，可能簡化您監控環境的方法。 詳細資訊，請參閱Microsoft 365[開發人員Office 365或Enterprise資訊](/office/developer-program/microsoft-365-developer-program-faq)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 監控服務健康情況 | 使用可用的Microsoft Teams，主動 (服務健康情況、) 和從屬服務。 從屬服務包括：Exchange Online、SharePoint Online、商務用 OneDrive、Azure Active Directory。 | 即時 | |
| 事件通知 | 將影響服務的事件通知Teams關係人。 內部關係人可以包含使用者、技術支援人員及事件管理員。 | 需要時 | |

### <a name="references"></a>引用

[如何檢查Microsoft 365或Office 365健康狀態](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[驗證服務健康Microsoft Teams](service-health.md)

[服務健康與持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理組織變更

Microsoft Teams是雲端式服務。 有了這項功能，您才能快速提供新功能。 持續創新為組織帶來明顯的好處，但組織內部必須妥善管理這些變更，以避免使用者對服務台的抵觸或升級。

系統會自動Teams更新給使用者。 您的使用者一定會擁有最新用戶端和功能，Teams服務。 無法管理向使用者推出Teams更新，因此透過有效的通訊、訓練和採用計畫管理變更至關重要。 如果您的使用者瞭解這項變更、瞭解其優點，並有權運用新功能，就能更快速地進行調整，並歡迎 &mdash; 這項變更。

### <a name="monitoring-for-change"></a>監控變更

變更管理的第一個步驟是監控計畫變更Teams。 監控這些變更的最佳來源是Microsoft 365藍圖，[](https://www.microsoft.com/microsoft-365/roadmap)其中列出目前正在開發、正在推出給客戶或已完全啟動的功能。 您可以使用提供的Teams來搜尋特定功能，或將藍圖下載至 Excel檔案以進一步分析。 藍圖會針對每項功能提供簡短描述，以及預期的發行日期。

在[Microsoft Teams部落](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)格中，您可以瞭解產品更新的最佳作法、趨勢Teams新聞。 預期會在這裡Teams主要功能更新。 您也可以透過 RSS 提要訂閱部落格。 接著，您可以將[RSS](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog)提要直接新Teams到頻道中，讓所有重要消息直接在 Teams。

所有發行的功能會記錄在 Microsoft Teams[的發行Microsoft Teams。](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)
您可以在這裡找到針對桌面、Web 和行動裝置所發行的功能清單。 同一組版本資訊也可在說明的新增功能選項卡[上找到](get-help-in-microsoft-teams.md)。

熟悉可用的資源，並確保您指派適用的擁有者來監控變更。

### <a name="planning-for-change"></a>規劃變更

現在，您已經發現即將對 Teams 服務進行變更，下一個步驟是準備並據此進行規劃。 評估每個變更，以判斷哪些變更需要與使用者溝通、認知活動、支援小組或使用者的訓練，或功能評估與採用活動。 這是貴組織中變更管理團隊的主要角色。 以下是可協助規劃變更之範例資料表集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：雲端錄製 (發行日期：2018 年 1 月) 

**一般追蹤**

| 變更準備狀態 | 地位 | 附注/下一個步驟 | 擁有者 |
|---|---|---|---|
| 法律評論 | 完成 | 這項功能是加入訓練小組的先決條件。 | Project小組 |

**技術變更管理**

| 變更準備狀態 | 地位 | 附注/下一個步驟 | 擁有者 |
|---|---|---|---|
| 需要 IT 變更 | 是 | 系統管理員只需要為識別的使用者啟用錄製。 | 支援小組 |
| 技術整備完成 | 是 | | 支援小組 |
| | | | |

**使用者變更管理**

| 變更準備狀態 | 地位 | 附注/下一個步驟 | 擁有者 |
|---|---|---|---|
| 使用者影響 | 低 | | |
| 需要使用者準備狀態 | 是 | | |
| 通訊就緒 | 否 | 通訊電子郵件已草擬，待審查。 | 通訊小組 |
| 訓練就緒 | 是 | 訓練會運用現有的 Microsoft 影片。 | 訓練小組 |

**狀態追蹤**

| 變更準備狀態 | 地位 | 附注/下一個步驟 | 擁有者 |
|---|---|---|---|
| 發行狀態 | 進行中 | 等待執行贊助人審查。 | 變更管理團隊 |
| 發行登出 | | | |
| 發行日期 | | | |

若要進一Teams規劃變更管理，請參閱為 Teams[建立變更管理Microsoft Teams。](change-management-strategy.md)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動| 描述| 節奏| 已指派團隊 |
|---|---|---|---|
| 監控變更| 監控服務即將Microsoft Teams變更。| 日常||
| 規劃變更| 評估及規劃新功能和功能，包括通訊計畫、認知活動及訓練。| 需要時 ||
| 使用者準備狀態| 執行目標通訊、認知或訓練活動，以確保使用者準備好進行即將到來的變更。| 需要時 ||
| 支援小組準備狀態 | 執行目標通訊、認知或訓練活動，以確保支援小組準備就緒。 支援小組可以包括「白手套」小組、技術支援人員、第 2 層或第 3 層支援、外部合作夥伴等等。 | 需要時 ||

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>評估Teams使用量

初始試驗開始之後，建立一般步頻以測量實際使用量Teams至關重要。 這可讓貴組織深入瞭解實際使用量如何與在構想階段預測的使用量保持一致。 雖然本節著重于Teams使用量，這應該是衡量及評估整體使用量Microsoft 365或Office 365工作的一部分。

在部署早期經常檢查使用方式，讓您有機會：

- 驗證使用者是否正在使用Teams。

- 找出潛在的採用挑戰，再在整個組織中造成重大問題。

- 瞭解構想階段需求與實際使用量之間是否有差異。

如果使用量與預期不同，這可能是因為部署問題、採用計畫未正確執行或其他問題。 根據低使用量背後的實際原因，系統管理員必須與相關的小組共同合作，協助移除使用障礙。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心

報告儀表板Teams資料。 Teams，您可以在三個不同的報告中找到使用方式資料。 第一份報表提供跨產品視圖，說明使用者使用各種服務在 Microsoft 365 或 Office 365。 此報告可在這裡找到：Microsoft 365[中心中的報告 - 使用中使用者](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他兩個報表Teams特定，並且從使用者和裝置Teams提供使用狀況的詳細資料。 這兩個報告都可以在這裡找到：

[Microsoft Teams裝置使用方式報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams使用者活動報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>必要的許可權

系統管理中心中的使用方式報告可由已指派全域系統管理員角色或產品特定系統管理員角色 (Exchange系統管理員、商務用 Skype系統管理員SharePoint系統管理員) 。    

此外，報表 **讀取** 者角色可供需要報表存取權，但不執行任何需要系統管理員層級許可權的工作的使用者使用。 您可以指派此角色，以向任何關係人提供使用方式報告，以監控和推動採用。 有關可用不同角色的資訊，請參閱[關於Microsoft 365角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>評估使用量

使用報告儀表板測量使用量之後，您必須將測量的使用量與專案構想階段期間定義的任何關鍵成功 (KSIs) 比較。 您可以定義可定義為作用中使用量的 KSI，或間接連結至作用中使用量的 KSI。

在繼續向其他網站或使用者推出之前，必須找出實際使用量與計畫使用量之間的任何差異。 您很可能會將組織學習識別為此活動的一部分，您可以利用這項活動，以確保下一批網站或使用者不會遇到相同的問題。

首先，找出這是採用還是技術問題。 首先調查下列專案，以便判斷問題所在位置。

1. 執行經驗品質檢閱 [來驗證品質](upgrade-monitor-quality.md)。

2. 與技術服務小組合作，檢查是否有導致使用者無法存取或使用服務的熱門技術問題。 如果問題趨勢存在，請使用本文稍後[](#endpoint-troubleshooting)的端點疑難排解區段，在吸引支援之前嘗試解決問題。

3. 請與訓練和採用小組合作，收集使用者的直接意見 (請參閱本文稍後的) [](#assess-user-sentiment)評估使用者情緒，並檢查認知和採用活動的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 測量啟用 (階段的使用量)  | 隨著網站在啟用Teams持續上移，測量及評估網站使用量。 按需要解決使用問題。 | 每週 | |
| 測量使用量 | 在部署完成後Teams並評估雲端硬碟價值階段 (使用量) 。 按需要解決使用問題。 | Biweekly | |
|  (磁碟機值階段)  | | | |
| 更新採用計畫 | 根據測量使用量與規劃目標的比較，更新您的採用計畫。 | 需要時 | |

### <a name="references"></a>引用

[關於Microsoft 365 系統管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[活動報告中Microsoft 365 系統管理中心](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>評估使用者情緒

瞭解使用者情緒可做為衡量您部署成功Teams標。 使用者的意見回饋可以推動貴組織的變更;這可能包括變更通訊計畫、訓練計畫，或您為使用者提供支援的方式。

及早取得意見回饋並持續評估專案整個生命週期及以後的使用者情緒非常重要。 請使用下列指南來判斷貴組織尋求意見回饋的時間間隔：

- **專案開始時**：在專案開始時評估使用者情緒，您可以提早瞭解使用者對於Teams的體驗。

- **重大里程碑之後**：收集整個專案週期的意見回饋，您可以持續評估使用者情緒，並根據需要進行變更。 在重大里程碑之後，這項功能特別有用。

- **Project：** 在專案結束時評估使用者情緒會告訴您完成得有多好，以及還需要在哪裡完成工作，並讓您比較結果與先前的問卷。

- **進行** 中：繼續無限期測量使用者情緒。 使用者情緒的變化可能是因為貴組織環境的變化，或是服務Teams變更。 您可以定期測量使用者情緒，瞭解服務管理團隊的績效，以及貴組織對服務變更Teams回應。

使用者情緒可以透過許多不同的方法進行評估。 這些可能包括電子郵件問卷、個人或電話式面試，或直接在 Teams 或 Yammer 中建立意見Yammer。 詳細資訊，請參閱在 Microsoft Teams 中的使用者[意見](best-practices-feedback.md)Microsoft Teams。

您也可以使用全產業的方法，評估稱為 NPS (淨) 的使用者情緒，如下一節所述。

### <a name="nps"></a>NPS

NPS (的淨) 分數是一項全產業的客戶效度度量，也是評估使用者情緒的一個好方法。 NPS 的計算方式有兩個問題：「您建議同事Teams嗎？」，後面接著免費格式問題「為什麼？」。

NPS 是一個範圍從 –100 到 100 的索引，可測量客戶建議公司產品或服務的意願。 NPS 是以透過電子郵件或其他電子方式傳送給使用者的匿名問卷為基礎。 NPS 會測量提供者與消費者之間的滿意度。 它只包含一個問題，要求使用者從 1 到 10 評等其體驗，並提供其他批註的選項。 然後根據下列評等來將使用者分類：

- 9 或 10 為促銷者：會宣傳您的服務和為其他人提供動力的效效愛好者。

- 7 或 8 為被動式：滿意但無法接受，容易受到其他服務或方案的影響。

- 從 1 到 6 是破壞者：不滿意的客戶可能會破壞您的服務並阻礙成長。

![顯示 NPS 縮放比例的圖表。](media/operate-my-service-image2.png "此圖表示範 NPS 刻度。這表示 0 到 6 的排名是誹謗者，7 到 8 是被動排名，而 9 到 10 是宣傳者。")

雖然基本 NPS 數位很有用，但分析使用者批註會獲得最大的值。 它們可協助您瞭解使用者為何 (建議) Teams建議。 這些批註可以提供寶貴的意見，協助專案或服務管理團隊瞭解提供高品質服務所需的調整。

若要提供 NPS 問卷給貴組織，您可以利用您最喜愛的線上問卷工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/如果需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 評估使用者情緒 | 使用問卷或面談，或透過意見Teams或Yammer。 | 需要時 | |
| 更新採用計畫 | 根據使用者的意見回饋來推動貴組織中的變化;這可能包括變更通訊計畫、訓練計畫，或您為使用者提供支援的方式。 | 需要時 | |

### <a name="references"></a>引用

[淨啟動者分數](https://en.wikipedia.org/wiki/Net_Promoter)

[使用Yammer收集意見](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[使用者意見回饋的最佳作法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理網路品質

許多核心規劃元素會進入優化、向右調整和補救您的網路基礎結構，以確保有高品質的、有效率Microsoft Teams服務。 我們的網路準備指南涵蓋規劃工作 [與](prepare-network.md) 需求。 由於升級、擴充或其他商務需求，網路通常會隨著時間而演進。 在網路規劃活動中，您必須考慮到Teams需求。

雖然網路規劃是部署Teams的一項重要內容，但根據業務或技術需求的變化，確保網路維持健康狀態並保持最新狀態也相當重要。

為了確保網路健康，需要定期執行一些作業活動。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 監控Microsoft 365或Office 365 IP 和 URL | 使用提供的 RSS [Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)監控 URL 和 IP 位址範圍的任何變更，[](https://go.microsoft.com/fwlink/p/?linkid=236301)並啟動對適用網路群組的變更要求。 | 日常 | |
| 根據 IP 或 URL Microsoft 365或Office 365更新網路 | 更新適用的網路元件 (防火牆、Proxy 伺服器、VPN、用戶端防火牆等) 以反映 Office 365 URL 和 IP 位址[範圍的變更](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 | 需要時 | |
| 提供建築物資料 | 提供更新的子網資訊給品質 (或相關的關係人) 以確保 [CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 中的建築物定義保持在最新狀態。 | 需要時 | |
| 執行變更 | 在網路中執行變更，以支援變更Teams和技術需求。 網路元素可以包括：<ul><li>防火牆</li><li>Vpn</li><li>有線Wi-Fi網路</li><li>網際網路連接和 ExpressRoute</li><li>DNS</li></ul> | 需要時 | |
| 網路監控與報告 | 使用網路提供者提供的現有協力廠商網路管理工具和報告功能，以端對端監控網路的可用性、使用方式和容量趨勢。 使用趨勢資料進行網路容量規劃。 | 每日、每週、每月 | |
| 容量規劃 | 與服務Teams共同合作，以瞭解可能推動其他容量變更的變更商務與技術需求。  | 需要時 | |
| 網路疑難排解和補救 | 協助Teams支援人員、服務擁有者和重要專案關係人疑難排解及補救Teams、可靠性或品質相關問題。 網路元素可以包括：<ul><li>防火牆</li><li>Vpn</li><li>有線Wi-Fi網路</li><li>網際網路連接和 ExpressRoute</li><li>DNS</li></ul> | 需要時 | |
| 災害復原和高可用性測試 | 在網路基礎結構上執行一般高可用性和災害復原測試，以確保它符合針對 Teams 服務所規定服務等級目標 (SLOs) 或服務等級協定 (SLA) 。 | 每月 | |

### <a name="references"></a>引用

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[建立資料架構](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>評估並確保品質

所有組織都需要一個群組或個人對品質負責。 這是服務管理中最重要的角色。 品質保護者角色會指派給對使用者體驗充滿熱忱的人或群組。
這個角色需要識別環境趨勢的技能，以及與其他團隊合作以推動補救的贊助。 品質優等者的最佳人選通常是客戶服務擁有者。 根據組織的規模和複雜度，這可能是任何一位對確保高品質的使用者體驗充滿熱忱的人或群組。

品質支援者利用現有的工具和檔程式 ，例如通話品質儀表板 (CQD) 以及改善[及監控 Teams](monitor-call-quality-qos.md)的通話品質，以監控使用者體驗、識別品質趨勢，以及視需要推動補救。
品質促進者應該與各自的小組合作，推動補救動作，並報告進度和任何未解決問題的監督委員會。

[改善及監控通話品質Teams](monitor-call-quality-qos.md)包括評估及提供對改善使用者體驗影響最大之重要地區的補救指引的活動。 品質經驗檢閱指南所提供的指引著重于使用 CQD Online 做為報告及調查每個區域的主要工具，並著重于音訊，以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接轉換成改善視像和桌面共用。

我們強烈建議您及早提名品質優等獎得主。 被提名後，他們應開始熟悉改善及監控通話品質中的內容[，Teams相關的訓練](monitor-call-quality-qos.md)教材。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 提名並訓練品質 ()  | 提名並訓練品質優等獎得主。 | 需要時 | |
| 在 QERs (品質檢閱)  | 執行 QER 以找出品質和可靠性的趨勢、針對已定義的目標檢閱，以及向組織的重要專案關係人報告。 | 部署 (每月)  | |
| 雲端硬碟修復 | 根據 QER 評定和結果，協調整個組織的補救工作。 | 需要時 | |
| 更新 CQD 中的建築物資料 | 當網路變更時，更新或新增 CQD 中的新建築物定義 (請參閱Upload[資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)) 。 | 需要時 | |
| 填寫品質促進者角色 | 組織中品質的端對端責任。 這包括：<ul><li>確保定期進行 QER。</li><li>向重要專案關係人報告品質狀態。</li><li>確定建築物資料定義是最新的。</li><li>協調整個組織的補救工作，確保使用者擁有高品質的Teams。</li></ul> | 日常 | |

### <a name="references"></a>引用

[Upload建築物資訊](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information)

[改善及監控通話品質Teams](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理端點

Microsoft Teams端點可定義為任何電腦、Mac、平板電腦或行動裝置 (，或執行用戶端) 裝置Teams裝置。 端點一詞不僅包含裝置本身，也包含使用者如何連接到裝置，例如，使用裝置內建的麥克風或喇叭、耳塞或優化的耳機。 部署端點之後，不得忘記端點。 端點Teams需要持續保養和維護。 下列各節說明要專注的特定區域。

### <a name="endpoint-requirements"></a>端點需求

其中一個Teams優點就是用戶端會自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新建立，並下載應用程式閒置時的新用戶端。 行動Teams應用程式會透過各自的 App Store 保持最新狀態。

用戶端Teams基礎軟體平臺的最低需求。 這些要求可能會隨著時間而變更，因此，您必須監控這些需求以檢查變更。 例如，Teams用戶端具有最小 iOS 版本。 如果用戶端使用網際網路瀏覽器，瀏覽器也需要保持最新狀態。 您可以在取得用戶端以取得[Microsoft Teams。](get-clients.md)

### <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆會對使用者體驗有重大的影響。
用戶端防火牆可能會影響通話品質，甚至防止建立通話。 在用戶端防火牆上已配置適當的排除專案之後，必須依據 URL 和 IP 位址範圍中的資訊Office 365[保持最新](/microsoft-365/enterprise/urls-and-ip-address-ranges)狀態。 您的協力廠商廠商將擁有如何更新排除專案的特定指引。

### <a name="wi-fi-drivers"></a>Wi-Fi驅動程式

Wi-Fi驅動程式可能有問題。 例如，驅動程式在訪問點之間可能有非常積極的漫遊行為，這會造成不必要的訪問點切換，導致通話品質不佳。 如果驅動程式Wi-Fi品質檢閱， (請參閱改善及監控 Teams 通話品質以) 。 [](monitor-call-quality-qos.md) 必須執行品質導向程式，監控新的Wi-Fi驅動程式，並確保在部署到一般使用者之前先測試這些驅動程式。

### <a name="endpoint-management"></a>端點管理

支援端點和介面裝置 (例如耳機) 應可供使用及維護。 此目錄會包含已選取並驗證為構想和板載階段一部分的核准裝置清單。 一般來說，會針對貴組織中每個人員類型選取特定裝置，以滿足該人員屬性的需求。 所有端點都有生命週期，您需要管理與這些裝置相關聯的廠商合約、保固、更換、發佈及維修政策。

### <a name="endpoint-troubleshooting"></a>端點疑難排解

即使您遵循了先前的指引，貴組織中使用者仍可能會遇到與Teams。 雖然問題可能並不存在於端點本身，但問題症狀通常會透過用戶端向使用者顯示。 下列指南旨在提供您可以採取之一般步驟以解決問題;這不一定只是一份完整的疑難排解指南。 這些步驟會以特定順序提供，但不必明確遵循，且可能不適用，視問題的性質而不同。

1. **驗證服務健康狀態：** 使用者可能會遇到的問題可能與事件有關，該事件會對服務Teams服務及其從屬服務造成負面影響。 首先，建議您確認沒有使用中服務問題。 請參閱[如何檢查Microsoft 365健康狀態](/office365/enterprise/view-service-health)。 請記得檢查從屬服務的狀態，例如 (、Exchange、SharePoint商務用 OneDrive) 。 在上一節的監控服務健康情況中，會更詳細的討論服務 [健康情況監控](#monitor-service-health)。

2. **驗證用戶端連接：** 連接問題會導致功能或登錄問題Teams。 我們建議您 (新網站或) 驗證服務的連接。 確保每個[Office 365都](/microsoft-365/enterprise/urls-and-ip-address-ranges)遵循下列 URL 和 IP 位址範圍指南。 您可以利用[Microsoft 網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885)執行連接測試，驗證媒體埠已正確開啟，Teams功能。 網路準備指南提供如何執行連接測試 [的詳細](prepare-network.md) 步驟。

3. **檢查已知問題清單：** 請參閱 [Teams](/MicrosoftTeams/troubleshoot/teams)疑難排解，判斷使用者是否受到這些問題之一的不良影響。 如果有一個 (，請遵循) 以解決問題。

4. **流覽Microsoft Teams社群：** 這個 [Microsoft Teams社群](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)提供專屬空間供Teams。 這個Teams社群提供以討論中心為中心的討論清單、部落格文章Teams。 您可以張貼問題或搜尋先前的討論，以尋找問題的解決方案。

5. **請聯絡 Microsoft 支援服務：** 您可以連線或電話Teams Microsoft 支援服務。 如需詳細資訊，請參閱 [聯絡商務產品支援人員 - 系統管理協助](/microsoft-365/admin/contact-support-for-business-products)。 針對頂級客戶，支援要求可以遵循與頂級客戶聯繫支援Microsoft Teams ([提出](https://support.microsoft.com/premier/contacts)) 。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 端點需求 | 請Teams端點繼續符合取得 Teams 用戶端中所列的所有[Microsoft Teams。](get-clients.md) | 每月 | |
| 端點防火牆 | 根據 URL 和 IP 位址範圍中的資訊，在端點防火牆Office 365[適當的排除專案](/microsoft-365/enterprise/urls-and-ip-address-ranges)。 您的協力廠商廠商將擁有如何維護排除專案的特定指引。 訂閱 [RSS 提要](https://support.office.com/o365ip/rss) ，以自動收到變更的通知。 | 需要時 | |
| Wi-Fi驅動程式 | 測試並Wi-Fi PC 上的驅動程式。 使用 CQD (改善及監控通話品質以驗證[Teams) 。](monitor-call-quality-qos.md) | 需要時 | |
| 端點管理 | 維護支援的端點和介面裝置目錄， (耳機或) 。 管理廠商合約、保固、分配、更換及維修政策。 | 每月 | |
| 端點疑難排解 | 疑難排解工作可能包括驗證連接、諮詢已知問題清單、記錄收集、分析，以及升級至 Microsoft 支援服務或協力廠商廠商。 | 需要時 | |

### <a name="references"></a>引用

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[取得 Microsoft Teams 用戶端](get-clients.md)

[Microsoft Teams社群](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)

[驗證服務健康Microsoft Teams](service-health.md)

[連絡商務產品的客戶支援 - 系統管理說明](https://support.office.com/article/Contact-support-for-business-products-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

[與頂級支援人員聯繫](https://support.microsoft.com/premier/contacts)

[疑難排解Teams影片](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署Microsoft Teams之後，您必須執行數個與系統管理相關的活動。 活動範圍從管理服務和個別使用者，到容量規劃與供應授權和電話號碼。 下列各節涵蓋這些常見的管理工作。

### <a name="service-administration"></a>服務管理

服務Teams多個設定，可設定整個租使用者。
對租使用者設定進行變更會影響所有已啟用此Teams。 有關這些設定的詳細清單，請參閱[管理Microsoft Teams的設定](enable-features-office-365.md)。

### <a name="user-administration"></a>使用者管理

若要支援使用者，組織可能需要任何數目的相關工作，而特定工作會因組織而異。 最終，這些工作必須由已指派這些營運職責的支援小組管理。 下列工作通常必須執行，才能支援 Teams。

#### <a name="general-tasks"></a>一般工作

[管理使用者對 Microsoft Teams](user-access.md)

### <a name="team-creation-optional"></a>小組建立 (選) 

根據預設，Exchange Online信箱的所有使用者都有許可權Microsoft 365群組，因此，Microsoft Teams。 如果您想要更嚴密地控制並限制建立新團隊[ (，](assign-roles-permissions.md#permissions-to-create-teams)進而建立新的 Microsoft 365 群組) ，您可以將群組的建立和管理許可權委派給一組系統管理員。 如果貴組織想要執行此選項，請參閱本文所述的程式，以允許使用者提交指派的團隊處理的要求。

<!--ENDOFSECTION-->

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動 | 描述 | 節奏 | 已指派團隊 |
|---|---|---|---|
| 服務管理 | 管理租使用者Teams設定。 | 需要時 | |
| 使用者管理 | 在 Teams 中管理使用者型Teams。 | 需要時 | |
| 授權管理 | 利用 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 使用方式報表和 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 分鐘 (方案與通訊) 方案，規劃使用者和消費型授權目前和未來的需求。 | 每週 | |
| 電話號碼管理 | 管理未來成長可用的電話號碼，並調整庫存量以滿足組織需求。 | 每週 | |
| 小組建立 (選)  | 審查並處理建立小組的要求。 | 需要時 | |

<!--ENDOFSECTION-->