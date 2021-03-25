---
title: Microsoft Teams 的操作指南
author: rmw2890
ms.author: Rowille
audience: admin
manager: serdars
ms.date: 06/11/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Teams 服務管理所需的工作和活動，包括監控服務健康情況，以及評估及確保網路品質和使用狀況。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5684ad62107fa61af7c9f2f22c6f15b4bfe1da30
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112649"
---
# <a name="operate-my-service"></a>營運我的服務

本文概觀貴組織成功營運雲端語音服務的需求。 您可以正確操作雲端語音服務，確保為貴組織提供高品質、可靠的體驗。

## <a name="introduction-to-the-operations-guide"></a>操作指南簡介

操作指南提供 Microsoft Teams 服務管理功能之一部分之所有工作與活動概觀。

服務管理是一個廣泛的主題，涵蓋 Microsoft Teams 服務在部署並啟用使用者之後，其日常運作。 Teams 服務包含 Microsoft 365 或 Office 365，以及部署在內部部署基礎結構元件 (例如網路) 。

服務管理的概念對於大多陣列織來說，很可能不是一個新概念。 您可能已經實施與現有服務相關聯的程式與工作。 也就是說，當您今天規劃服務管理以支援 Teams 時，您或許可以擴充目前的程式。

服務管理包含管理 Teams 端對端的所有活動與程式。 如先前所述，Microsoft 365 或 Office 365 服務本身所組成的基礎結構，是服務管理的某些元件，由 Microsoft 負責，而客戶則負責管理 Teams、網路和您提供的端點的各個層面。

本指南中的工作和活動會分成八個類別，如下圖所示。 以下各節將展開這些類別。

![描述工作與活動類別清單的圖表](media/operate-my-service-image1.png "描述 Teams 服務管理所組成之工作與活動的類別清單的圖表。圖表也說明服務管理主要是客戶工作。")


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>決策點</td><td><ul><li>決定如何針對 Teams 執行作業。</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td><td><ul><li>完整閱覽作業指南。</li><li>執行符合貴組織目標的操作策略，以提供雲端語音工作負載的品質和可靠性。</li><li>檢 [閱監控通話品質](monitor-call-quality-qos.md)。</li><li> 執行營運策略，定期執行體驗品質檢閱，以確保您的雲端語音部署以最佳功能運作。</li></ul></td></tr>
</table>


### <a name="operational-role-mapping"></a>操作角色映射

在構想階段期間，您針對作業所進行規劃至關重要，因為當第一個試驗使用者啟用時，作業活動即會開始。 本指南列出必須每天、每週、每月或需要執行的活動和工作，以維護高品質的 Teams 部署。 本指南提供如何執行這些重要活動和工作的知識與指引。

成功部署的其中一個至關重要的元件，是確保您在構想階段早期進行的計畫包括決定負責執行特定活動的人。 在您找出哪些工作和活動適用于您的部署之後，您必須瞭解並遵循您指派給這些工作與活動的群組或個人。

您識別的每個小組都必須審查並同意所識別的工作與職責，並開始準備。 這可能包括訓練和準備、提供人員配置計畫更新，或確保外部提供者準備好提供。

本指南中定義的活動和角色在大部分情況下應該都有效，但每個 Teams 部署都是唯一的;因此，您可以使用本指南做為起點來自訂活動和預設角色，以滿足您的需求。

確保每個負責的團隊都瞭解執行服務所需的活動。 第一個試驗開始之前，每個小組必須接受並簽署貴組織的責任。

在簽訂合約之後，對應的團隊應該開始執行其角色。

<table>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>後續步驟</td>
<td><ul><li>使用這份檔來協助操作角色的繪圖作業。</li><li>與各自的支援小組開會，將名稱指派給所需活動清單中的每個專案。</li><li>取得已指派角色的接受或簽收。</li><li>請確定對應的團隊擁有適當的訓練、準備狀態和資源，以完成所需的活動。</li></ul></td></table>

### <a name="teams-service-dependencies"></a>Teams 服務相依性

Microsoft Teams 將 Microsoft 365 或 Office 365 的技術彙集在一起，提供團隊合作的中心。 範例包括：

-   Azure Active Directory (Azure AD) 提供 Teams 的驗證和授權服務。

-   Exchange Online 提供進一步功能，例如法律保留與電子探索。

-   SharePoint Online 提供在頻道中共用檔案的能力，而商務用 OneDrive 提供在私人聊天中共用檔案的機制。

組織也可以利用內部部署基礎結構的現有投資。 例如，現有的內部部署 Active Directory 帳戶可以使用 Azure AD Connect 進行驗證。 某些版本的 Exchange Server 可用於更換 Exchange Online。

這些技術彙集在一起，為使用者提供豐富、共同合作且智慧型通訊套件。 這種緊密整合是 Teams 的一大優點，但也推動跨這些技術的服務管理需求。

本指南涵蓋管理 Teams 服務的主要焦點區域。 最有可能的是，您針對 Teams 所依賴的支援技術，有一些服務管理計畫。 如果沒有，您也需要為內部部署和線上 (技術元件建立) 方案。 這可協助確保您的使用者在 Teams 中享有高品質、可靠的體驗。

#### <a name="references"></a>引用 

[Microsoft Teams 概觀](teams-overview.md)

[Exchange 和 Microsoft Teams 如何互動](exchange-teams-interact.md)

[SharePoint Online 和商務用 OneDrive 如何與 Microsoft Teams 互動](sharepoint-onedrive-interact.md)

[Microsoft Teams 與商務用 Skype 共存與互通性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

<!--ENDOFSECTION-->

## <a name="operations-guide-activities"></a>作業指南活動

下列各節提供成功操作 Microsoft Teams 服務所需的活動概觀。 它們包括參考工具、關係資訊和其他內容，以協助您瞭解活動，並協助進行準備計畫。

<!--ENDOFSECTION-->

## <a name="monitor-service-health"></a>監控服務健康情況

您必須瞭解 Microsoft Teams 服務的整體健康情況，以便主動提醒貴組織中其他人任何影響服務的事件。 如先前所述，Teams 會依賴其他 Microsoft 365 或 Office 365 服務，例如 Azure Active Directory、Exchange Online、SharePoint Online 和商務用 OneDrive。 因此，監控從屬服務的健康情況也相當重要。

將此活動納入您的事件管理程式，以主動通知使用者、技術支援人員及您的營運小組，準備處理使用者升級。

下列各節說明您可以用來監控影響 Teams 服務之[](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#Anchor_1)服務事件的工具。 下表包含每個工具優點的摘要，以及您應該何時使用每個工具。

| 監控工具                       | 優點                                            | 使用時間                                                                                  |
|---------------------------------------|-----------------------------------------------------|----------------------------------------------------------------------------------------------|
| Microsoft 365 系統管理中心                     | 可從任何具有支援瀏覽器的裝置使用。 | 當您不需要即時通知時，請使用。                                          |
| Microsoft 365 或 Office 365 系統管理應用程式                  | 提供推入通知至您的行動裝置。  | 當您在外時需要收到服務事件通知時，請使用。                  |
| Microsoft System Center               | 與 Microsoft System Center 整合。           | 當您需要進一級的監控功能和通知支援時，請使用。                       |
| Microsoft 365 或 Office 365 服務通訊 API | 以程式化方式存取 Microsoft 365 或 Office 365 服務健康狀態。   | 當您需要整合協力廠商監控工具或想要建立您自己的解決方案時，請使用。 |

> [!NOTE]
> 只有指派全域系統管理員或服務系統管理員 **角色的個人才能** 查看服務健康狀態。

### <a name="monitoring-with-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心監控

[Microsoft 365 系統](https://portal.office.com/)管理中心提供服務健康情況[儀表板](https://portal.office.com/adminportal/home#/servicehealth)，除了從屬服務之外，您還可以在這裡查看 Teams 服務目前的健康情況。

### <a name="monitoring-with-the-mobile-app"></a>使用行動應用程式監控

Microsoft 365 或 Office 365 系統管理應用程式可在 Apple iOS、Android 和 Windows (PC 和行動) 。 應用程式會提供服務系統管理員有關服務健康情況及近期變更的資訊。 應用程式支援推入通知，可在公告發布後立即提醒您。 這可協助您隨時瞭解服務的狀態、健康情況，以及任何即將進行的變更。 通知支援使它成為建議系統管理員的監控工具。 詳細資訊，請參閱：

[Office 365 系統管理行動應用程式](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a)

[下載 Office 365 系統管理行動應用程式](https://products.office.com/business/manage-office-365-admin-app)

### <a name="monitoring-with-microsoft-system-center"></a>使用 Microsoft System Center 監控

Microsoft System Center 是一個整合式管理平臺，可協助您管理資料中心、用戶端裝置和混合式雲端 IT 環境。 使用 System Center 的 Office 365 系統管理員現在可以選擇輸入 Office 365 管理套件，讓他們在系統中心中的 Operations Manager 中查看所有服務通訊。 使用此工具，您可以存取訂閱服務的狀態、使用中和已解決的服務事件，以及訊息中心通訊 (變更) 。 若要詳細資訊，請參閱下列 [部落格文章](https://blogs.office.com/2014/07/29/new-office-365-admin-tools/?eu=true)。

如果您利用 System Center 監控 Teams 服務健康情況 (和從屬服務) ，您可以進一步自訂管理套件，以提醒或通知已識別為回應事件的特定群組或個人。
這些群組可以包含貴組織中服務擁有者、技術支援人員、第二層和第三層支援群組，以及事件管理員。

### <a name="monitoring-for-advanced-scenarios"></a>監控進位案例

您可以利用 Office 365 服務通訊 API 以程式化方式存取 Office 365 服務健康情況及變更，以監控服務健康情況及即將到來的變更。 使用此 API 建立您自己的監控工具，或將現有的監控工具連接到 Office 365 服務通訊，可能簡化您監控環境的方法。 詳細資訊，請參閱企業版 [Office 365 開發人員](https://developer.microsoft.com/office)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動               | 說明                                                                                                                                                                                                               | 節奏   | 已指派團隊 |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 監控服務健康情況 | 使用可用的工具，主動 (Microsoft Teams 服務健康情況、) 和從屬服務。 從屬服務包括：Exchange Online、SharePoint Online、商務用 OneDrive、Azure Active Directory。 | 即時 |               |
| 事件通知  | 將影響 Teams 服務的事件通知內部專案關係人。 內部關係人可以包含使用者、技術支援人員及事件管理員。                                                                          | 需要時 |               |

### <a name="references"></a>引用 

[如何檢查 Office 365 服務健康狀態](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)

[驗證 Microsoft Teams 的服務健康狀態](service-health.md)

[服務健康與持續性](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)

<!--ENDOFSECTION-->

## <a name="manage-organizational-change"></a>管理組織變更

Microsoft Teams 是雲端式服務。 有了這項功能，您才能快速提供新功能。 持續創新為組織帶來明顯的好處，但貴組織內部必須妥善管理這些變更，以避免使用者對技術支援人員造成阻力或升級。

Teams 更新會自動推出給使用者。 您的使用者將一直擁有 Teams 服務中的最新用戶端和功能。 無法管理 Teams 更新的推出給使用者，因此透過有效的通訊、訓練和採用計畫來管理變更非常重要。 如果您的使用者已經瞭解這項變更、瞭解其優點，並有權運用新功能，就能更快速地進行調整，並歡迎 &mdash; 這項變更。

### <a name="monitoring-for-change"></a>監控變更

變更管理的第一個步驟是監控 Teams 規劃的變更。 監控這些變更的最佳來源是 Office [365 藍圖](https://products.office.com/business/office-365-roadmap)，其中列出目前正在開發、正在推出給客戶或已完全啟動的功能。 您可以使用提供的篩選來搜尋 Teams 特定功能，也可以將藍圖下載至 Excel 檔案以進一步分析。 藍圖會針對每項功能提供簡短描述，以及預期的發行日期。

在 [Microsoft Teams 部落](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)格中，您可以瞭解 Teams 產品更新的最佳作法、趨勢和新聞。 預期會在這裡找到 Teams 的主要功能更新。 您也可以透過 RSS 提要訂閱部落格。 接著，您可以將 [RSS 提](https://techcommunity.microsoft.com/gxcuf89792/rss/board?board.id=MicrosoftTeamsBlog) 要直接新增到 Teams 頻道，讓所有重要消息直接在 Teams 內傳遞。

所有發行的功能會記錄在 Microsoft Teams 的發行 [資訊中](https://support.office.com/article/Release-notes-for-Microsoft-Teams-d7092a6d-c896-424c-b362-a472d5f105de)。
您可以在這裡找到針對桌面、Web 和行動裝置所發行的功能清單。 同一組版本資訊也可在說明的新增功能選項卡[上找到](get-help-in-microsoft-teams.md)。

熟悉可用的資源，並確保您指派適用的擁有者來監控變更。

### <a name="planning-for-change"></a>規劃變更

現在，您已經發現 Teams 服務即將進行變更，下一個步驟就是準備並據此進行規劃。 評估每個變更，以判斷哪些變更需要與使用者溝通、認知活動、支援小組或使用者的訓練，或功能評估與採用活動。 這是貴組織中變更管理團隊的主要角色。 以下是可協助規劃變更之範例資料表集合。

#### <a name="feature-cloud-recording-release-date-january-2018"></a>功能：雲端錄製 (發行日期：2018 年 1 月) 

**一般追蹤**

| 變更準備狀態 | 地位   | 附注/下一個步驟 | 擁有者 |
|----|----|----|-----|
| 法律評論   | 完成     | 這項功能是加入訓練小組的先決條件。 | 專案小組  |

**技術變更管理**

|       變更準備狀態       | 地位 |                      附注/下一個步驟                      |    擁有者     |
|------------------------------|--------|------------------------------------------------------------|--------------|
|     IT 變更為必填專案      |  是   | 系統管理員只需要為識別的使用者啟用錄製。 | 支援小組 |
| 技術整備完成 |  是   |                                                            | 支援小組 |
|                              |        |                                                            |              |

**使用者變更管理** 

| 變更準備狀態 | 地位   | 附注/下一個步驟 | 擁有者 |
|----|----|----|-----|
| 使用者影響                  | 低                  |                                                                 |                        |
| 需要使用者準備狀態      | 是                  |                                                                 |                        |
| 通訊就緒         | 否                   | 通訊電子郵件已草擬，待審查。            | 通訊小組    |
| 訓練就緒               | 是                  | 訓練會運用現有的 Microsoft 影片。                | 訓練小組          |

**狀態追蹤**

| 變更準備狀態 | 地位   | 附注/下一個步驟 | 擁有者 |
|----|----|----|-----|
| 發行狀態               | 進行中          | 等待執行贊助人審查。               | 變更管理團隊 |
| 發行登出             |                      |                                                                 |                        |
| 發行日期                 |                      |                                                                 |                        |

有關使用 Teams 規劃變更管理的資訊，請參閱為 Microsoft Teams 建立 [變更管理策略](change-management-strategy.md)。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動               | 說明                                                                                                                                                                                                                | 節奏   | 已指派團隊 |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 監控變更     | 監控 Microsoft Teams 服務即將進行的變更。                                                                                                                                                                   | 日常     |               |
| 規劃變更    | 評估及規劃新功能和功能，包括通訊計畫、認知活動及訓練。                                                                                                     | 需要時 |               |
| 使用者準備狀態             | 執行目標通訊、認知或訓練活動，以確保使用者準備好進行即將到來的變更。                                                                                                        | 需要時 |               |
| 支援小組準備狀態 | 執行目標通訊、認知或訓練活動，以確保支援小組準備就緒。 支援小組可以包括「白手套」小組、技術支援人員、第 2 層或第 3 層支援、外部合作夥伴等等。 | 需要時 |               |

<!--ENDOFSECTION-->

## <a name="assess-teams-usage"></a>評估 Teams 使用方式

初始試驗開始之後，建立一般步頻以測量實際的 Teams 使用量至關重要。 這可讓貴組織深入瞭解實際使用量如何與在構想階段預測的使用量保持一致。 雖然本節著重于 Teams 使用方式，但此部分應成為衡量及評估整體 Office 365 使用方式之較廣泛工作的一部分。

在部署早期經常檢查使用方式，讓您有機會：

-   驗證使用者是否正在使用 Teams。

-   找出潛在的採用挑戰，再在整個組織中造成重大問題。

-   瞭解構想階段需求與實際使用量之間是否有差異。

如果使用量與預期不同，這可能是因為部署問題、採用計畫未正確執行或其他問題。 根據低使用量背後的實際原因，服務系統管理員必須與相關的小組共同合作，協助移除使用障礙。

### <a name="measuring-usage-with-the-microsoft-365-admin-center"></a>使用 Microsoft 365 系統管理中心測量使用方式

Teams 的使用狀況資料可在報告儀表板中提供。 Teams 使用方式資料可在三個不同的報告中找到。 第一份報告提供使用者使用 Office 365 中各種服務進行通訊和共同合作的方式的跨產品視圖。 此報告可在這裡找到 [：Office 365 使用中使用者報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Active-Users-FC1CF1D0-CD84-43FD-ADB7-A4C4DFA8112D)

其他兩個報表是 Teams 專用報表，它們從使用者和裝置的角度提供 Teams 使用方式的進一步詳細資料。 這兩個報告都可以在這裡找到：

[Microsoft Teams 裝置使用方式報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-device-usage-917b3e1d-203e-4439-8539-634e80196687)

[Microsoft Teams 使用者活動報告](https://support.office.com/article/Office-365-Reports-in-the-Admin-Center-Microsoft-Teams-user-activity-07f67fc4-c0a4-4d3f-ad20-f40c7f6db524)

#### <a name="required-permissions"></a>必要的許可權

系統管理中心中的使用方式報告可由已指派全域系統管理員角色或產品特定系統管理員角色的人員存取 (**Exchange** 系統管理員、**商務** 用 Skype 系統管理員 **、SharePoint** 系統管理員) 。

此外，報表 **讀取** 者角色可供需要報表存取權，但不執行任何需要系統管理員層級許可權的工作的使用者使用。 您可以指派此角色，以向任何關係人提供使用方式報告，以監控和推動採用。 有關可用不同角色的資訊，請參閱 [關於 Office 365 系統管理員角色](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。

### <a name="assessing-usage"></a>評估使用量

使用報告儀表板測量使用量之後，比較測量使用量與專案構想階段期間定義的任何關鍵成功 (KSIs) 非常重要。 您可以定義可定義為作用中使用量的 KSI，或間接連結至作用中使用量的 KSI。

在繼續向其他網站或使用者推出之前，必須找出實際使用量和計畫使用量之間的任何差異。 您很可能會將組織學習識別為此活動的一部分，您可以利用這項活動，以確保下一批網站或使用者不會遇到相同的問題。

首先，找出這是採用還是技術問題。 首先調查下列專案，以便判斷問題所在位置。

1.  若要驗證品質，請執行體驗品質檢閱 (請參閱改善及監控 [Teams](monitor-call-quality-qos.md) 的通話品質，以) 。

2.  與技術服務小組合作，檢查是否有導致使用者無法存取或使用服務的熱門技術問題。 如果問題趨勢存在，請使用本文稍後[](#endpoint-troubleshooting)的端點疑難排解區段，在吸引支援之前嘗試解決問題。

3.  請與訓練和採用小組合作，收集使用者 [ (請參閱本文](#assess-user-sentiment) 稍後) 評估使用者情緒，並檢查認知和採用活動的有效性。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動                         | 說明                                                                                                                      | 節奏   | 已指派團隊 |
|----------------------------------|----------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 測量啟用 (階段的使用量)  | 當網站在啟用階段持續上移時，測量及評估 Teams 使用量。 按需要解決使用問題。 | 每週    |               |
| 測量使用 (磁碟機值階段)                            | 在部署完成之後，在 (階段測量及評估 Teams 使用量) 。 按需要解決使用問題。 | Biweekly  |               |
| 更新採用計畫             | 根據測量使用量與規劃目標的比較，更新您的採用計畫。                                         | 需要時 |               |

### <a name="references"></a>引用 

[關於 Microsoft 365 系統管理中心](https://support.office.com/article/About-the-Office-365-admin-center-758befc4-0888-4009-9f14-0d147402fd23)

[Microsoft 365 系統管理中心的活動報告](https://support.office.com/article/Activity-Reports-in-the-Office-365-admin-center-0d6dfb17-8582-4172-a9a9-aed798150263)

<!--ENDOFSECTION-->

## <a name="assess-user-sentiment"></a>評估使用者情緒

瞭解使用者情緒可做為衡量 Teams 部署成功與否的重要指示器。 使用者的意見回饋可以推動貴組織的變更;這可能包括變更通訊計畫、訓練計畫，或您為使用者提供支援的方式。

及早取得意見回饋並持續評估專案整個生命週期及以後的使用者情緒非常重要。 請使用下列指南來判斷貴組織尋求意見回饋的時間間隔：

-   **專案開始時**：在專案開始時評估使用者情緒，您可以提早瞭解使用者對於 Teams 體驗的感受。

-   **重大里程碑之後**：收集整個專案週期的意見回饋，您可以持續評估使用者情緒，並根據需要進行變更。 在重大里程碑之後，這項功能特別有用。

-   **專案結束**：在專案結束時評估使用者情緒會告訴您完成得有多好，以及工作還需要在哪裡完成，並讓您比較結果與上一次問卷。

-   **進行** 中：繼續無限期測量使用者情緒。 使用者情緒的變化可能是因為貴組織環境的變化，或是 Teams 服務中的變更。 您可以定期測量使用者情緒，瞭解服務管理團隊的績效，以及貴組織如何回應 Teams 服務中的變更。

使用者情緒可以透過許多不同的方法進行評估。 這些可能包括電子郵件問卷、個人或電話式面試，或直接在 Teams 或 Yammer 中建立意見回饋通道。 詳細資訊請參閱 Microsoft [Teams 中的使用者意見回饋方法最佳做法](best-practices-feedback.md)。

您也可以使用全產業的方法，評估稱為 NPS (淨) 的使用者情緒，如下一節所述。

### <a name="nps"></a>Nps 

NPS (淨) 分數是一項全產業的客戶效度度量，也是評估使用者情緒的一個好方法。 NPS 的計算方式有兩個問題：「您建議同事使用 Teams 的可能性為何？」，後面接著「為什麼？

NPS 是一種從 –100 到 100 的索引，可測量客戶建議公司產品或服務的意願。 NPS 是以透過電子郵件或其他電子方式傳送給使用者的匿名問卷為基礎。 NPS 會測量提供者與消費者之間的滿意度。 它只包含一個問題，要求使用者從 1 到 10 評等其體驗，並提供其他批註的選項。 然後根據下列評等來將使用者分類：

-   9 或 10 是促銷者：會宣傳您的服務和為他人提供動力的效心愛好者。

-   7 或 8 為被動式：滿意但無法接受，容易受到其他服務或方案的影響。

-   從 1 到 6 是破壞者：不滿意的客戶可能會破壞您的服務並阻礙成長。

![顯示 NPS 刻度的圖表](media/operate-my-service-image2.png "此圖表示範 NPS 刻度。這表示 0 到 6 的排名是誹謗者，7 到 8 是被動排名，而 9 到 10 是宣傳者。")

雖然基本 NPS 數位很有用，但分析使用者批註會獲得最大的值。 它們可協助您瞭解使用者為何會 (建議) Teams 給其他人。 這些批註可以提供寶貴的意見，協助專案或服務管理團隊瞭解提供高品質服務所需的調整。

若要提供 NPS 問卷給貴組織，您可以利用您最喜愛的線上問卷工具。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/如果需要的工作

| 活動              | 說明                                                                                                                                                                         | 節奏   | 已指派團隊 |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 評估使用者情緒 | 使用問卷或面談，或透過 Teams 或 Yammer 的意見回饋通道來收集及評估使用者情緒。                                                                 | 需要時 |               |
| 更新採用計畫 | 根據使用者的意見回饋，推動貴組織中發生變更;這可能包括變更您的通訊計畫、訓練計畫，或您為使用者提供支援的方式。 | 需要時 |               |

### <a name="references"></a>引用 

[淨啟動者分數](https://en.wikipedia.org/wiki/Net_Promoter)

[使用 Yammer 收集意見](https://techcommunity.microsoft.com/t5/Yammer-Blog/The-Microsoft-Teams-team-uses-Yammer/ba-p/55210)

[使用者意見回饋的最佳作法](best-practices-feedback.md)

<!--ENDOFSECTION-->

## <a name="manage-network-quality"></a>管理網路品質

許多核心規劃元素會進入優化、正確調整大小及補救您的網路基礎結構，以確保 Microsoft Teams 服務有高品質且有效率的路徑。 我們的網路準備指南涵蓋規劃工作 [與](3-envision-evaluate-my-environment.md#network-readiness) 需求。 由於升級、擴充或其他商務需求，網路通常會隨著時間而演進。 您必須在網路規劃活動中，針對 Teams 的需求進行說明。

雖然網路規劃是 Teams 部署的重要一面，但根據業務或技術需求的變化，確保網路保持健康並維持最新狀態也相當重要。

為了確保網路健康，需要定期執行一些作業活動。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動                                                       | 說明                                                                                                                                                                                                                                                                                                                                                                 | 節奏                | 已指派團隊 |
|----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------|---------------|
| 監控 Office 365 IP 和 URL                                | 使用提供的 RSS 提要來監控[Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges) URL 和[](https://go.microsoft.com/fwlink/p/?linkid=236301)IP 位址範圍的任何變更，並針對適用的網路群組提出變更要求。                                                                                                                                | 日常                  |               |
| 根據 Office 365 IP 和 URL 的變更更新網路 | 更新適用的網路元件 (防火牆、Proxy 伺服器、VPN、用戶端防火牆等) 以反映 [Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)URL 和 IP 位址範圍的變更。                                                                                                                                                              | 需要時              |               |
| 提供建築物資料                                          | 提供更新的子網資訊給品質 (或相關的關係人) 以確保 [CQD](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 中的建築物定義保持在最新狀態。 | 需要時              |               |
| 執行變更                                               | 在網路上執行變更，以支援變更 Teams 商務與技術需求。 網路元素可以包括：<ul><li>防火牆</li><li>Vpn</li><li>有線Wi-Fi網路</li><li>網際網路連接和 ExpressRoute</li><li>DNS</li></ul>     | 需要時              |               |
| 網路監控與報告                               | 使用網路提供者提供的現有協力廠商網路管理工具和報告功能，以端對端監控網路的可用性、使用方式和容量趨勢。 使用趨勢資料進行網路容量規劃。                                                                                                            | 每日、每週、每月 |               |
| 容量規劃                                              | 與 Teams 服務擁有者共同合作，以瞭解可能推動其他容量變更的變更業務和技術需求。                                | 需要時              |               |
| 網路疑難排解和補救                        | 協助 Teams 支援人員、服務擁有者和重要專案關係人疑難排解和補救與 Teams 連接、可靠性或品質相關的問題。 網路元素可以包括：<ul><li>防火牆</li><li>Vpn</li><li>有線Wi-Fi網路</li><li>網際網路連接和 ExpressRoute</li><li>DNS</li></ul>    | 需要時              |               |
| 災害復原和高可用性測試                | 在網路基礎結構上執行一般高可用性和災害復原測試，以確保它符合針對 Teams 服務所 (SLOs) 或服務等級協定 (SLA) 的已規定服務等級目標。                                                                                                                                                  | 每月                |               |


### <a name="references"></a>引用 

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[建立資料架構](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#tenant-data-file-format-and-building-data-file-structure)

<!--ENDOFSECTION-->

## <a name="assess-and-ensure-quality"></a>評估及確保品質 

所有組織都需要一個群組或個人對品質負責。 這是服務管理中最重要的角色。 品質保護者角色會指派給對使用者體驗充滿熱忱的人或群組。
這個角色需要識別環境趨勢的技能，以及與其他團隊合作推動補救的贊助。 品質優等者的最佳候選人通常是客戶服務擁有者。 根據組織的規模和複雜度，這可能是任何一位對確保高品質的使用者體驗充滿熱忱的人或群組。

品質支援者利用現有工具和檔化程式 ，例如通話品質儀表板 (CQD) ，以監控使用者體驗、識別品質趨勢，並視需要推動補救。
品質促進者應該與各自的小組合作，推動補救動作，並報告進度和任何未解決問題的監督委員會。

請閱讀 [改善及](monitor-call-quality-qos.md)監控 Teams 的通話品質，其中說明評估活動，並提供對改善使用者體驗影響最大的重要地區的補救指引。 本文所提供的指引著重于使用 CQD 做為報告及調查每個區域的主要工具，並著重于音訊，以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接轉換成改善視像和桌面共用。

我們強烈建議您及早提名品質優等獎得主。 被提名後，他們應開始熟悉 [監控通話品質](monitor-call-quality-qos.md) 內容和相關的訓練教材。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動                               | 說明                                                                                                                                                                                                                                                                                                 | 節奏                             | 已指派團隊 |
|----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------|---------------|
| 提名並訓練品質 ()  | 提名並訓練品質優等獎得主。                                                                                                                                                                                                                                                                   | 需要時                           |               |
| 在 QERs (品質檢閱)      | 執行 QER 以找出品質和可靠性的趨勢、針對已定義的目標檢閱，以及向組織的重要專案關係人報告。                                                                                                                            | 部署 (每週一次)  |               |
| 雲端硬碟修復                      | 根據 QER 評定和結果，協調整個組織的補救工作。                                                                                                                                                                                                           | 需要時                           |               |
| 更新 CQD 中的建築物資料            | 當網路變更時，更新或新增 CQD 中的新建築物定義 [ (請參閱上傳](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard#upload-building-information) 建築物) 。 | 需要時                           |               |
| 填寫品質冠軍角色      | 組織中品質的端對端責任。 這包括：<ul><li>確保定期進行 QER。</li><li>向重要專案關係人報告品質狀態。</li><li>確定建築物資料定義是最新的。</li><li>協調整個組織的補救工作，以確保使用者在 Teams 中擁有高品質的體驗。</li></ul>          | 日常                               |               |



### <a name="references"></a>引用 


[在 CQD 中上傳租使用者和建築物資料](CQD-upload-tenant-building-data.md)

[改善及監控 Teams 的通話品質](monitor-call-quality-qos.md)

<!--ENDOFSECTION-->

## <a name="manage-endpoints"></a>管理端點

Microsoft Teams 端點可以定義為任何電腦、Mac、平板電腦或行動裝置 (或執行 Teams 用戶端) 裝置。 端點一詞不僅包含裝置本身，也包含使用者如何連接到裝置，例如，使用裝置內建的麥克風或喇叭、耳塞或優化的耳機。 部署端點之後，不得忘記端點。 Teams 端點需要持續保養和維護。 下列各節說明要專注的特定區域。

### <a name="endpoint-requirements"></a>端點需求

Teams 的主要優點之一是用戶端會自動保持在最新狀態。 PC 和 Mac 上的用戶端會使用背景程式進行更新，此程式會檢查新建立，並下載應用程式閒置時的新用戶端。 Teams 行動應用程式會透過各自的 App Store 保持最新狀態。

Teams 用戶端對基礎軟體平臺的最低需求。 這些要求可能會隨著時間而變更，因此您必須監控這些需求以檢查變更。 例如，Teams 用戶端具有最小 iOS 版本。 如果用戶端使用網際網路瀏覽器，瀏覽器也需要保持最新狀態。 您可以在取得 Microsoft Teams 的用戶端中找到支援 [的平臺清單](get-clients.md)。

### <a name="endpoint-firewalls"></a>端點防火牆

用戶端防火牆會對使用者體驗有重大的影響。
用戶端防火牆可能會影響通話品質，甚至防止建立通話。 在用戶端防火牆上已配置適當的排除專案之後，必須依據 [Office 365](/microsoft-365/enterprise/urls-and-ip-address-ranges)URL 和 IP 位址範圍的資訊來保持最新狀態。 您的協力廠商廠商將擁有如何更新排除專案的特定指引。

### <a name="wi-fi-drivers"></a>Wi-Fi驅動程式

Wi-Fi驅動程式可能有問題。 例如，驅動程式在訪問點之間可能有非常積極的漫遊行為，這會造成不必要的訪問點切換，導致通話品質不佳。 如果驅動程式Wi-Fi品質檢閱，可能會發現品質不佳 (請參閱改善及監控 [Teams](monitor-call-quality-qos.md) 的通話品質以) 。 必須執行品質導向程式，監控新的Wi-Fi驅動程式，並確保在部署到一般使用者之前先測試這些驅動程式。

### <a name="endpoint-management"></a>端點管理

支援端點和介面裝置 (例如耳機) 應該可供使用及維護。 此目錄會包含已選取並驗證為構想和板載階段一部分的核准裝置清單。 一般來說，會針對貴組織中每個人員類型選取特定裝置，以滿足該人員屬性的需求。 所有端點都有生命週期，您需要管理與這些裝置相關聯的廠商合約、保固、更換、發佈及維修政策。

### <a name="endpoint-troubleshooting"></a>端點疑難排解

即使您遵循了先前的指引，貴組織中使用者仍可能會遇到 Teams 問題。 雖然問題可能並不存在於端點本身，但問題症狀通常會透過用戶端向使用者顯示。 下列指南旨在提供您可以採取之一般步驟以解決問題;這不一定只是一份完整的疑難排解指南。 這些步驟會以特定順序提供，但不必明確遵循，且可能不適用，視問題的性質而不同。

1.  **驗證服務健康狀態：** 使用者可能會遇到的問題可能與事件有關，而該事件會對 Teams 服務及其從屬服務造成負面影響。 首先，建議您確認沒有使用中服務問題。 請參閱 [如何檢查 Office 365 服務健康狀態](https://support.office.com/article/How-to-check-Office-365-service-health-932AD3AD-533C-418A-B938-6E44E8BC33B0)。
    請記得檢查從屬服務的狀態 (例如 Exchange、SharePoint、商務用 OneDrive) 。 在上一節的監控服務健康情況中，會更詳細的討論服務 [健康情況監控](#monitor-service-health)。

2.  **驗證用戶端連接：** 連接問題會造成 Teams 中的功能或登錄問題。 我們建議您 (新網站或位置，) 驗證服務的連接。 確保每個網站都遵循下列 [Office 365 URL](/microsoft-365/enterprise/urls-and-ip-address-ranges) 和 IP 位址範圍指南。 您可以利用 [Microsoft 網路評定工具](https://www.microsoft.com/download/details.aspx?id=53885) 執行連接測試，驗證媒體埠已正確開啟雲端語音功能。 網路準備指南提供如何執行連接測試 [的詳細](3-envision-evaluate-my-environment.md#network-readiness) 步驟。

3.  **檢查已知問題清單：** 請參閱 [Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams) ，判斷使用者是否受到這些問題之一的不良影響。 如果有一個 (，請遵循) 以解決問題。

4.  **流覽 Microsoft Teams 社群：**[Microsoft Teams 社群提供](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)Teams 專用空間。 Teams 社群提供以 Teams 為中心的討論清單、部落格文章和公告。 您可以張貼問題或搜尋先前的討論，以尋找問題的解決方案。

5.  **請聯絡 Microsoft 支援服務：** 如需 Teams 線上或電話的問題，您可以與 Microsoft 支援服務聯繫。 如需詳細資訊，請參閱 [與商務產品的支援人員聯繫](/microsoft-365/admin/contact-support-for-business-products)。
    針對頂級客戶，支援要求可以遵循 Microsoft Teams 與頂級客戶或頂級客戶的連絡人支援 (提出[) 。](https://support.microsoft.com/premier/contacts)

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動                 | 說明                                                                                                                                                                                                                                                                                                                                                                     | 節奏   | 已指派團隊 |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 端點需求    | 請確保 Teams 端點繼續符合取得 Microsoft Teams 用戶端中列出的 Teams [的所有軟體需求](get-clients.md)。                                                                                                                                                                                       | 每月   |               |
| 端點防火牆       | 根據 Office [365](/microsoft-365/enterprise/urls-and-ip-address-ranges)URL 和 IP 位址範圍的資訊，在端點防火牆上維持適當的排除。 您的協力廠商廠商將擁有如何維護排除專案的特定指引。 訂閱 [RSS 提要](https://support.office.com/o365ip/rss) ，以自動收到變更的通知。 | 需要時 |               |
| Wi-Fi驅動程式            | 測試並Wi-Fi PC 上的驅動程式。 使用 CQD (改善及監控 [Teams](monitor-call-quality-qos.md) 通話品質以驗證) 。                                                                                                                                                                                                                                                                   | 需要時 |               |
| 端點管理      | 維護支援的端點和介面裝置目錄，例如 (耳機) 。 管理廠商合約、保固、分配、更換及維修政策。                                                                                                                                                                                                        | 每月   |               |
| 端點疑難排解 | 疑難排解工作可能包括驗證連接、諮詢已知問題清單、記錄收集、分析，以及升級至 Microsoft 支援服務或協力廠商廠商。                                                                                                                                                                                               | 需要時 |               |

### <a name="references"></a>引用 

[Office 365 URL 與 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)

[取得 Microsoft Teams 用戶端](get-clients.md)

[Microsoft Teams 社群](https://techcommunity.microsoft.com/t5/Microsoft-Teams/ct-p/MicrosoftTeams)

[Teams 疑難排解](/MicrosoftTeams/troubleshoot/teams)

[驗證 Microsoft Teams 的服務健康狀態](service-health.md)

[連絡商務產品的客戶支援 - 系統管理說明](/microsoft-365/admin/contact-support-for-business-products)

[與頂級支援人員聯繫](https://support.microsoft.com/premier/contacts)

[Teams 影片疑難排解](https://www.youtube.com/watch?v=4O4d_7uZTQY)

<!--ENDOFSECTION-->

## <a name="manage-teams"></a>管理 Teams

部署 Microsoft Teams 服務之後，您必須執行數個與系統管理相關的活動。 活動範圍從管理服務和個別使用者，到容量規劃與供應授權和電話號碼。 下列各節涵蓋這些常見的管理工作。

### <a name="service-administration"></a>服務管理

Teams 服務有多個可設定整個租使用者範圍的設定。
對租使用者設定進行變更會影響已啟用 Teams 的所有使用者。 有關這些設定的詳細清單，請參閱 [管理貴組織的 Microsoft Teams 設定](enable-features-office-365.md)。

### <a name="user-administration"></a>使用者管理

若要支援使用者，組織可能需要任何數目的相關工作，而特定工作會因組織而異。 最終，這些工作必須由已指派這些營運職責的支援小組管理。 在 Teams 中支援使用者時，一般需要執行下列工作。

#### <a name="general-tasks"></a>一般工作

[管理 Microsoft Teams 的使用者存取權](user-access.md)

#### <a name="common-tasks-for-phone-system"></a>電話系統的常見工作

[指派、變更或移除使用者的電話號碼](./assign-change-or-remove-a-phone-number-for-a-user.md)

[指派或變更使用者的緊急位址](/skypeforbusiness/what-are-calling-plans-in-office-365/assign-or-change-an-emergency-address-for-a-user)

[新增、變更或移除貴組織的緊急位置](/skypeforbusiness/what-are-calling-plans-in-office-365/add-change-or-remove-an-emergency-location-for-your-organization)

[建立和管理撥號對應表](create-and-manage-dial-plans.md)

#### <a name="common-tasks-for-audio-conferencing"></a>音訊會議的常見工作

[變更音訊會議橋接器的設定](change-the-settings-for-an-audio-conferencing-bridge.md)

[變更音訊會議橋接器的電話號碼](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

[管理使用者的音訊會議設定](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

[重設音訊會議 PIN 碼](reset-the-audio-conferencing-pin-in-teams.md)

### <a name="license-management"></a>授權管理

隨著貴組織成長或合約，您必須針對目前和未來的需求規劃授權。 除了授權雲端語音功能外，還有基本 Teams 授權 ([電話](here-s-what-you-get-with-phone-system.md)系統與音訊[會議) 。](https://products.office.com/skype-for-business/audio-conferencing)

對於 Teams，電話系統授權需要相關聯的 [通話方案](calling-plan-landing-page.md) 授權。 通話方案授權可讓您撥打及接聽國內和/或國際電話。 這些方案是以使用量為基礎，而且有相關聯的分鐘數庫。 撥 [備通訊信用額度](what-are-communications-credits.md) 可確保您永遠不會用完服務。

音訊會議可讓您使用付費電話撥入式會議和國內撥出式會議服務。 免付費電話撥入式會議或非國內撥出案例可能會導致您產生額外的費用，而 [必須支付通訊](what-are-communications-credits.md) 額度。

通訊信用額度可以同時補充通話方案與音訊會議授權。 通話方案授權和通訊信用額度都是以使用量為基礎，因此需要監控並針對此進行配置。

您可以利用 [PSTN 使用方式報告](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) ，協助監控通話方案通話分鐘數和通訊額度的使用方式。 根據此活動的結果，您可以調整授權。 我們即將推出 [PSTN 分鐘數庫](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 報告，以更有效地協助這項工作。

### <a name="telephone-number-management"></a>電話號碼管理

在 Teams 中取得號碼的方法有兩種：您可以從另一個提供者埠電話號碼，或直接從 Microsoft 的數位庫存中配置號碼。 這兩種方法在取得 [使用者的電話號碼中都有說明](getting-phone-numbers-for-your-users.md)。

您可以從 Microsoft 的號碼庫存中撥備的電話號碼數量有限制。 限制是由一些詳細因素所決定，詳細資料如下：您可以取得多少[電話號碼？。](how-many-phone-numbers-can-you-get.md)
限制取決於號碼類型：免付費服務號碼、付費服務號碼，以及訂閱者 (使用者) 號碼。 每個都有各自的限制，而且必須獨立管理。 如果您接近限制 (或已達到限制) ，您可以申請增加限制。 上一個段落中的一文說明此程式。

有時候，在服務可用的地區可能無法提供號碼。 有關要求號碼程式的資訊，請參閱 [管理貴組織的電話號碼](/skypeforbusiness/what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)。

### <a name="team-creation-optional"></a>小組建立 (選) 

根據預設，在 Exchange Online 中擁有信箱的所有使用者都有權在 Microsoft Teams 中建立 Microsoft 365 群組，因此也有權建立團隊。 如果您想要更嚴密地控制並限制建立新團隊 [ (](assign-roles-permissions.md#permissions-to-create-teams) 並因此建立新的 Microsoft 365 群組) ，您可以將群組的建立和管理許可權委派給一組系統管理員。 如果貴組織想要執行此選項，請參閱本文所述的程式，以允許使用者提交指派的團隊處理的要求。

### <a name="dailyweeklymonthlyas-needed-tasks"></a>每日/每週/每月/需要的工作

| 活動                    | 說明                                                                                                                                                                                                                                                                                                                                                                                                             | 節奏   | 已指派團隊 |
|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|---------------|
| 服務管理      | 管理租使用者範圍的 Teams 設定。                                                                                                                                                                                                                                                                                                                                                                           | 需要時 |               |
| 使用者管理         | 在 Teams 中管理使用者型設定和授權。                                                                                                                                                                                                                                                                                                                                                           | 需要時 |               |
| 授權管理          | 利用 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-usage-report) 使用方式報表和 [PSTN](/skypeforbusiness/skype-for-business-online-reporting/pstn-minute-pools-report) 分鐘數庫報告，規劃使用者和消費型授權 (通話方案與通訊) 目前和未來的需求。 | 每週    |               |
| 電話號碼管理 | 管理未來成長所需的電話號碼，並調整庫存量以滿足組織需求。                                                                                                                                                                                                                                                                                                | 每週    |               |
| 小組建立 (選)     | 審查並處理建立小組的要求。                                                                                                                                                                                                                                                                                                                                                                          | 需要時 |               |

<!--ENDOFSECTION-->

## <a name="improve-and-monitor-call-quality"></a>改善及監控通話品質

[改善及監控 Teams](monitor-call-quality-qos.md) 的通話品質包括一組活動，可評估對改善使用者體驗有最大影響的重要領域，並提供補救指引，如下圖所示。

![體驗品質檢閱期間要檢查的區域圖表](media/plan-my-service-management-image2.png "在體驗品質檢閱期間要檢查的主要領域：音訊、可靠性及使用者問卷結果。")

您可以持續評估及補救指南所述區域，以降低其潛在性，對使用者體驗造成負面影響。 部署中遇到的大多數使用者體驗問題可以分成下列類別：

-   不完整的防火牆或 Proxy 組

-   低Wi-Fi覆蓋

-   頻寬不足

-   Vpn

-   使用非初始化或內建的音訊裝置

-   有問題的子網或網路裝置

改善及監控 [Teams](monitor-call-quality-qos.md) 通話品質所提供的指引，著重于使用通話品質儀表板 (CQD) Online 做為報告及調查所述每個區域的主要工具，並著重于音訊，以最大化採用和影響。 對網路進行的任何優化以改善音訊體驗，也會直接轉換成改善視像和桌面共用。

我們強烈建議您及早提名品質優等獎得主。 被提名後，他們應開始熟悉改善及監控 Teams 通話 [品質中的內容](monitor-call-quality-qos.md)。

<!--ENDOFSECTION-->