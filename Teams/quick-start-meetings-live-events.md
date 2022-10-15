---
title: 會議、網路研討會與即時活動
ms.reviewer: ''
description: 系統管理員推出在 Microsoft Teams 中設定會議、網路研討會和即時事活動的指南。
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5961e05ac1ec927fbaca31dc24279eca27ce0f9d
ms.sourcegitcommit: 50ae550b738424b35df1636590831e6c124ca0c1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2022
ms.locfileid: "68576409"
---
# <a name="meetings-webinars-and-live-events"></a>會議、網路研討會與即時活動

Microsoft Teams 有多種開會方式 - 會議、網路研討會和即時活動。

本文適用於系統管理員和 IT 專業人員，說明會議、網路研討會和即時活動之間的差異。 然後它會提供您快速為使用者推出此功能所需的資訊連結。

[Meetings](#meetings), [webinars](#webinars), and [live events](#live-events) are all types of meetings, but webinars and live events provide additional control for the organizer over the conversation and participants. Webinars provide two-way interaction while live events provide a managed Q&A experience. 

不同類型的會議也有不同的參與者限制和參與者功能。 

下表摘要說明三種會議類型、建議的參與者數目，以及參與者如何在會議中互動。 有關每種會議類型的詳細資訊章節，請參閱下列表格。 本文也包含有關 [大型會議的最佳作法](#best-practices-for-large-meetings) 一節。

| 會議類型 | 參與者的數量 | 互動 | 支援註冊 |
|----------|--------|--------|-----|
| 會議  | 最多 20,000* 位 | - 最多 1,000 位參與者具有完整的互動式平等會議功能。 <br> - 超過 1,000 位參與者 (最多 20,000 位) 具有[僅供檢視](view-only-meeting-experience.md)功能。  | 否 |
| 網路研討會 | - 最多 1,000 位<br>- 增加[僅供檢視](view-only-meeting-experience.md)功能的限制即將推出。 |- 最多 1,000 位參與者具有完整的互動式功能。<br> - 可設定的觀眾互動。<br> - 可以指定簡報者。 | 是 |
| 即時活動 | 最多 20,000** 位 |- 向大批觀眾廣播。 <br>- 觀眾互動的仲裁問與答。 <br> - 能夠指定製作者和簡報者，包括外部簡報者。<br>- 支援更進階的生產功能。 | 否 |

*到 2022 年 12 月 31 日，由一般的 10,000 位增加到 20,000 位。

**到 2022 年 12 月 31 日，由一般的 10,000 位增加到 20,000 位。 您可以在 Yammer 和/或 Microsoft Stream 中排程更多即時活動。 如需詳細資訊，請參閱[跨 Microsoft 365 的即時活動](/stream/live-event-m365)。 請注意，超過 20,000 位出席者需要[即時活動協助計畫](/stream/live-events-assistance)。

Note that NDI is fully supported in meetings, webinars, and live events, allowing you to produce the broadcast by using tools such as OBS and Wirecast. For more information, see [Use NDI® technology in Microsoft Teams](use-ndi-in-meetings.md).

> [!NOTE]
> 如需其他資訊，並取得使用 Microsoft Teams 提供線上活動之角色的指引，請參閱 [虛擬事件播放簿](https://aka.ms/VirtualEventPlaybook)。 您也可以加入Microsoft Tech Community上的[虛擬活動論壇](https://aka.ms/VirtualEventForum)。

> [!NOTE]
> 如需有關快速設定不同平台上 Teams 會議和活動的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="meetings"></a>會議

Teams 中的 **會議** 包括音訊、視訊，且螢幕畫面分享人數最多可達 1,000 人，以及最多 1,000 位參與者的 [僅供檢視](view-only-meeting-experience.md)功能。 參與者不需要具備組織的成員資格 (或擁有 Teams 帳戶) 就能加入 Teams 會議。 他們可以透過加入會議連結直接從行事曆邀請加入，或透過音訊通話 (如果有)。  

作為系統管理員，您將設定會議設定，並指定會議原則來控制貴組織啟用哪些會議功能。  

除了定期排程的會議，您的使用者可以建立頻道會議。 使用頻道會議，小組中的每個人都可以看到會議、加入會議，以及使用會議聊天。 頻道會議是一種快速邀請小組中所有人員參加會議的方式。 如需使用者如何排定會議的相關資訊，請參閱[排程會議](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)。

有關僅供檢視會議體驗的資訊，請參閱 [Teams 僅供檢視會議體驗](view-only-meeting-experience.md)。

### <a name="articles-for-administrators"></a>針對系統管理員的文章

下表重點說明您想要檢閱的重要文章：

| 文章 | 描述 |
|----------|--------|
| [會議設定](meeting-settings-in-teams.md) |  說明如何設定匿名使用者、會議邀請和媒體流量的會議設定。  |
| [會議原則](meeting-policies-overview.md)  | 說明如何建立和管理決定會議參與者可以使用哪些功能之原則。 | 
| [管理 Teams 雲端會議錄製](cloud-recording.md) | 說明如何管理會議錄製。 |
| [管理貴組織的裝置](device-management.md)| 說明如何管理貴組織的裝置，例如手機和 Teams 會議室。 |
| [使用即時遙測來疑難排解會議品質不佳的問題](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | 描述如何使用 Real-Time 分析 (RTA) 疑難排解個別使用者 Microsoft Teams 會議品質不佳的問題。|

### <a name="key-training-for-end-users"></a>針對終端使用者的重要訓練

下表列出可供貴組織使用者使用的訓練：

| 訓練 | 描述 |
|----------|--------|
| [管理會議](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | 適用於首次使用 Teams 會議之使用者的快速訓練影片。 |
| [排定會議](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | 說明如何排程不同類型會議的文章。 |
| [使用 Teams 有效執行會議](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | 免費導學型課程，了解如何讓會議更吸引人、具生產力且有意義。 |
| [變更 Teams 會議的參與者設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)。 | 管理會議選項的文章。 |

## <a name="webinars"></a>網路研討會

**網路研討會** 是結構化會議，其中簡報者和參與者具有清楚的角色。 網路研討會與 Teams 會議的主要差異在於網路研討會支援註冊並提供出席者參與資料。 若要在組織中啟用網路研討會，請參閱[在 Teams 中設定網路研討會](set-up-webinars.md)。

### <a name="key-training-for-end-users"></a>針對終端使用者的重要訓練

下表列出可供貴組織使用者使用的訓練：

| 訓練 | 描述 | 
|----------|--------|
| [開始使用 Teams 網路研討會](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | 適用於首次使用 Teams 網路研討會之使用者的快速訓練影片。 |
| [視覺化快速入門手冊](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | 可下載的視覺化手冊，說明如何開始排程網路研討會。 |


## <a name="live-events"></a>即時活動

**即時活動** 是結構化的會議，可讓貴組織排程並產生活動，向大批線上觀眾串流播放，最多可讓 20,000 人參與。 使用即時活動時，觀眾互動是受管理的問與答體驗。

### <a name="articles-for-administrators"></a>針對系統管理員的文章

下表重點說明您想要檢閱的重要文章：

| 文章 | 描述 |
|----------|--------|
| [什麼是 Teams 即時活動？](teams-live-events/what-are-teams-live-events.md)  | 即時活動的快速簡介。 |
| [Teams 即時活動的規劃](teams-live-events/plan-for-teams-live-events.md) | 在設定即時活動之前，您需要知道哪些資訊。 |
| [設定 Teams 即時活動](teams-live-events/set-up-for-teams-live-events.md) | 說明先決條件，例如網路規劃。 |
| [設定即時活動](teams-live-events/configure-teams-live-events.md) | 設定即時活動的步驟。|

### <a name="key-training-for-end-users"></a>針對終端使用者的重要訓練

下表列出可供貴組織使用者使用的訓練：

| 訓練 | 描述 |
|:----------|:--------|
| [開始使用即時活動](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | 即時活動的簡介，以及如何開始使用。 |
| [Teams 即時活動影片訓練](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | 說明如何規劃及排程即時活動的影片。  |

若要產生較大規模的虛擬活動，請查閱[虛擬事件指南](https://adoption.microsoft.com/virtual-event-guidance/)，其中提供活動召集人、技術製作人、IT 專業人員和內容創作者的指引。

## <a name="apps-for-meetings"></a>會議應用程式

Microsoft enables you to enhance meeting experiences by integrating and using meeting apps. For example, whiteboard integration in Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

您可以使用隨著 Teams 提供的應用程式、使用認證的協力廠商應用程式和範本，以及透過建立您自己的自訂應用程式，將會議應用程式新增到您的 Teams 部署。

如需詳細資訊，請參閱下表列出的文章：

| 文章 | 描述 |
|----------|--------|
| [Teams 應用程式概觀](deploy-apps-microsoft-teams-landing-page.md) | 應用程式簡介，以及如何為貴組織部署應用程式。 |
| [Teams 會議應用程式](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | 會議應用程式擴充性、API 參考，以及如何啟用和設定會議應用程式的概觀。 |
| [管理 Teams 中的白板](manage-whiteboard.md) | 說明白板功能，以及如何為貴組織啟用和停用。 |

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>會議、網路研討會和即時活動的授權需求

任何人都可以免費參加 Teams 會議、網路研討會或即時活動 -- 無需任何授權。

對於召集、排程和舉辦會議、網路研討會或即時活動的人員，這些人員需要 [Microsoft Teams 服務描述](/office365/servicedescriptions/teams-service-description)中所列的 Microsoft 365 授權之一。 如果您已經在使用 Teams，您可能已經擁有召集和舉辦會議、網路研討會和即時活動所需的授權。

若要允許人員使用電話撥入會議，您必須設定音訊會議。 如需音訊會議的詳細資訊，請參閱 [Teams 中的音訊會議](deploy-audio-conferencing-teams-landing-page.md)。

## <a name="best-practices-for-large-meetings"></a>大型會議的最佳做法

本節提供系統管理員指南，以及系統管理員可以與簡報者和召集人分享的秘訣。

若要成功舉辦活動，請遵循以下所列的做法：

- 若要在大型會議、網路研討會和即時活動中獲得最佳體驗，Microsoft 建議使用最新版的 Teams 桌面用戶端或 Teams 行動裝置用戶端。

- 確保內部部署和遠端使用者都遵循所有 Microsoft [網路連線原則](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)。
- 使用 [即時資料遙測](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146) 來監控活動並找出任何可能的問題及其來源。
  - 指定會議監視器以 [分析](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) 使用者因計量超過閥值而導致面臨體驗不佳的遙測。
  - 將會議監視器設定為簡報者，以停用惡意視音訊流、將意外的即時麥克風設為靜音，並視需要移除出席者。

### <a name="guidelines-for-your-end-users"></a>使用者指導方針

您的召集人和簡報者應執行下列建議：

- 對於 10 人以上的會議，請使用 [問與答](/MicrosoftTeams/manage-qna-for-teams) 讓參與者有機會正式提問並取得問題的答案，以及參與結構化討論。

- 若要建立順暢的會議，活動召集人可以設定預先定義的簡報者。 會議開始之後，簡報者也可以將其他出席者升級為簡報者角色。

- 透過會議選項定義共同召集人 (公開預覽) 

- 預先設定影片和麥克風設定，以控制出席者的體驗。
  - 停用出席者麥克風以避免干擾。 如果有人需要在會議期間互動，請允許他們在舉手時取消靜音。
  - 停用出席者影片，以避免視覺干擾。 在會議的適當時間，所有出席者或特定人員都可以觀看影片。

- 在會議期間使用 [問與答]。

- 使用大廳控制項以控制會議進入或大廳保留。

- 執行 [Microsoft 365 網路連線測試](https://connectivity.office.com/)，以在在事件發生的前幾天及之後，驗證網路適用性。

- 如果從家裡進行簡報，請確認其他裝置並未使用高頻寬 (串流服務、線上遊戲、大量下載)。

- 使用有線連接從端點進行簡報，以進行更可靠的音訊、影片和螢幕分享。

- 確保使用者在傳統型應用程式或行動裝置上使用最新的 Teams 應用程式。

- 使用膝上型電腦時，請檢查是否擁有高網路連線能力和足夠的電力。

- 在活動之前排程幹執行，以識別裝置、光源或網路問題。 這也會確保召集人/簡報者熟悉他們將會使用的功能。
  - 如果發生問題，排程其他練習執行，以確保補救工作成功。
  
- 利用精選、PowerPoint Live、會議錄製、即時輔助字幕和文字記錄等功能，提升參與度和效率。

- 簡報者和參與者應該使用 Teams 傳統型應用程式來提供最佳體驗。

- 參與者應在大型會議期間關閉聊天通知，以避免分心。

- 如需主持大型會議的更多秘訣，請參閱[大型 Teams 會議的最佳做法](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)。

## <a name="related-topics"></a>相關主題

[Teams 的會議和召集會議](deploy-meetings-microsoft-teams-landing-page.md)

[在 Teams 中設定網路研討會](set-up-webinars.md)

[Teams 的即時活動](teams-live-events/what-are-teams-live-events.md)

[Teams 僅供檢視會議體驗](view-only-meeting-experience.md)

[Teams 的限制和規格](limits-specifications-teams.md)

