---
title: 什麼是 Microsoft Teams 即時活動？
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: 瞭解即時活動如何讓使用者在 Teams、Yammer 和 Stream 中將影片和內容廣播給大量線上物件。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 78e2fdb6b205316dfd8a715c12613be1486302f5
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918989"
---
# <a name="what-are-microsoft-teams-live-events"></a>什麼是 Microsoft Teams 即時活動

## <a name="overview"></a>概觀

有了 Teams 即時活動，您組織的使用者就可以將影片和會議內容廣播給大量線上物件。

Microsoft 365 即時活動將即時影片串流功能帶到一個新的層次。 即時活動可促進在即時活動之前、期間及之後與出席者整個互動週期的關聯。 無論您的觀眾、團隊或社群位於何處，都可以使用 Microsoft Stream、Teams 或 Yammer 建立即時活動。  

Teams 提供聊天式共同合作、通話、會議和即時活動，因此您可以擴大會議物件。 Teams 即時活動是 Teams 會議的擴充功能，可讓使用者向大量線上物件廣播視影片和會議內容。 即時活動適用于一對多通訊，活動主持人會引導互動，而觀眾參與主要是為了查看由主機共用的內容。 出席者可以在 Yammer、Teams 和/或 Stream 中觀看即時或錄製的活動，而且可以使用經管理 Q & A 或 Yammer 交談與簡報者互動。

Teams 即時活動視為下一版的 Skype 會議廣播，且最終會取代 Skype 會議廣播中提供的功能。 此時，Microsoft 會繼續為組織中使用商務用 Skype 的使用者支援 Skype 會議廣播，新事件或未來活動不會中斷服務。 不過，我們鼓勵您試用 Teams 即時活動，以運用所有全新且有趣的功能，包括螢幕畫面分享和外部硬體/軟體編碼器的支援。

讓我們開始吧。 首先，請看一下下列圖表，其中顯示與 Microsoft 365 即時活動有關的高層級元件，及其連接方式。

![即時活動的重要元件](../media/live-event-flow-diagram.png  "即時活動、排程、生產、Stream 平臺、通過認證的協力廠商 eCDN 提供者的重要元件")

### <a name="event-group-roles"></a>事件群組角色

Teams 中的即時活動讓多個角色 (、製作人、簡報者及出席者) 成功廣播及參與活動。 若要深入瞭解，請參閱 [活動群組角色](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)。

## <a name="key-components"></a>重要元件

從上方圖片可以看到，有五個與 Teams 即時活動一起使用的重要元件。

> [!NOTE]
> 若要概觀瞭解如何設定即時活動及出席者經驗，請觀看[這些短片。](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)

### <a name="scheduling"></a>調度

Teams 讓召集人能夠建立具有適當出席者許可權的事件、指定活動小組成員、選取生產方法，以及邀請出席者。 如果即時活動是從 Yammer 群組內建立，即時活動出席者將可以使用 Yammer 交談與活動人員互動。

![新即時活動畫面](../media/teams-live-events-schedule.png "顯示新即時活動畫面以建立和排程新即時活動的螢幕擷取畫面")

> [!IMPORTANT]
> Teams 不會讓使用者在離線或以有限的頻寬執行時，排程會議或即時活動。

### <a name="production"></a>生產

視影片輸入是即時活動的基礎，從單一網路攝影機到多部攝影機的專業影片製作，不一樣。 Microsoft 365 中的即時活動支援各種生產案例，包括使用網路相機在 Teams 中舉辦的活動，或外部 App 或裝置中所產生的事件。 您可以根據專案的需求和預算來選擇這些選項。 有兩種方法可以產生事件：

- **Teams：** 這項生產方法可讓使用者在 Teams 中，使用網路相機或 Teams 會議室系統的 A/V 輸入來製作即時活動。 如果您想要使用連接到電腦的音訊和視視裝置，或邀請遠端簡報者參與活動，此選項是最佳且最快速的選項。 此選項可讓使用者輕鬆使用網路相機，並分享螢幕畫面做為活動輸入內容。

- **外部 App 或裝置**：外部編碼器可讓使用者直接從使用 Stream 的外部硬體或軟體型編碼器產生 [即時活動](https://stream.microsoft.com)。 如果您已經有工作室品質設備 (例如媒體混合器) 支援串流至即時傳訊通訊協定 (RTMP) 服務，則此選項最佳。 這種類型的活動通常會用於大型活動，例如高樓大廳，其中媒體混合器的單一串流會廣播給觀眾。

    ![使用外部 App 或裝置舉辦即時活動](../media/teams-live-events-external-encoder.png "螢幕擷取畫面顯示使用外部 App 或裝置生產方法所舉辦即時活動")

>[!Note]
> 從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](../tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。

### <a name="streaming-platform"></a>串流平臺

即時活動串流平臺由下列各部分所決定：

- **Azure 媒體服務**[：Azure 媒體服務](https://docs.microsoft.com/azure/media-services/previous/)提供您廣播品質的視訊串流服務，在現今最熱門的行動裝置上，讓更多人觀看。 媒體服務可增強協助工具、發佈和擴充性，並輕鬆且以成本成本將內容串流至您的當地或全球物件，同時保護您的內容。
- **Azure 內容傳遞網路 (CDN) ：** 一旦串流開始執行，它會透過 Azure 內容傳遞網路或 CDN ([傳遞) 。](https://docs.microsoft.com/azure/cdn/) Azure 媒體服務提供串流端點的整合式 CDN。 這樣可在全球範圍中查看資料流程，而不需要緩衝。

### <a name="enterprise-content-delivery-network-ecdn"></a>企業內容傳遞網路 (eCDN) 

eCDN 的目標是從網際網路拍攝影片內容，並在整個企業中發佈內容，而不會影響網路效果。 您可以使用下列其中一個通過認證的 eCDN 合作夥伴，針對在貴組織中舉辦即時活動優化您的網路：

- [蜂巢](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [斜坡](https://rampecdn.com)
- [河床](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>出席者經驗

出席者經驗是即時活動最重要的部分，出席者必須能參與即時活動，而不需要發生任何問題。 出席者經驗使用 Stream Player (用於在 Teams) 和 Azure Media Player (中舉辦之活動，用於在外部 App 或裝置) 中舉辦的活動，而且可跨電腦、瀏覽器及行動裝置 (iOS、Android) 運作。 Microsoft 365 和 Office 365 提供 Yammer 和 Teams 兩個共同合作中心，而即時出席者的體驗已整合至這些共同處理工具中。

![即時活動出席者體驗範例](../media/teams-live-events-attendee.png "顯示即時活動出席者體驗的螢幕擷取畫面")

### <a name="live-event-usage-report"></a>即時事件使用方式報告

租使用者管理員可以在 Microsoft Teams 系統管理中心中查看即時事件即時使用方式分析。  即時 [活動使用方式報告](../teams-analytics-and-reports/teams-live-event-usage-report.md) 會顯示組織中即時活動的活動概觀。  系統管理員可以查看事件使用資訊，包括事件狀態、開始時間、視圖及生產類型。  

## <a name="next-steps"></a>後續步驟

前往 [Teams 即時活動規劃](plan-for-teams-live-events.md)。

### <a name="related-topics"></a>相關主題

- [Yammer、Microsoft Teams 和 Microsoft Stream 中的 Microsoft 365 即時活動](https://docs.microsoft.com/stream/live-event-m365)
- [從 Microsoft Teams 五場即時活動開始](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer 中的即時活動](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream 中的即時活動](https://docs.microsoft.com/stream/live-event-overview)
