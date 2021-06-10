---
title: 什麼是Microsoft Teams活動？
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
description: 瞭解即時活動如何讓使用者在 Teams、Yammer和 Stream 中廣播視像和內容。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 8f196e1539085966c22a775a784913ced417c9cb
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506720"
---
# <a name="what-are-microsoft-teams-live-events"></a>即時Microsoft Teams活動是什麼

## <a name="overview"></a>概觀

有了Teams活動，貴組織的使用者就可以將視像和會議內容廣播給大型線上觀眾。

Microsoft 365即時活動將即時視音訊串流新高。 即時活動可在整個參與週期內鼓勵與出席者在即時活動之前、期間和之後建立連線。 您可以使用 Microsoft Stream、Teams或Yammer。  

Teams聊天式共同合作、通話、會議和即時活動，以便擴大會議物件。 Teams活動是會議Teams延伸功能，讓使用者將視像和會議內容廣播給大型線上觀眾。 即時活動適用于由活動主持人主導互動的一對多通訊，而觀眾參與主要是為了查看主機共用的內容。 出席者可以在 Yammer、Teams 或 Stream 中觀看即時或錄製的活動，並可以使用主持的 Q & A 或 Yammer 交談與簡報者互動。

Teams活動被視為會議廣播的下一Skype版本，最終會取代會議廣播Skype功能。 此時，Microsoft 會繼續支援Skype組織中使用會議廣播商務用 Skype，不會中斷新事件或未來活動的服務。 不過，我們鼓勵您試用Teams活動，以使用所有全新且令人振奮的功能，包括螢幕畫面分享，以及支援外部硬體/軟體編碼器。

因此，讓我們開始吧。 首先，請看一下下列圖表，其中顯示即時Microsoft 365中涉及的高層級元件，以及它們如何連接。

![即時活動的關鍵元件](../media/live-event-flow-diagram.png  "即時活動、排程、生產、Stream 平臺、通過認證的協力廠商 eCDN 提供者的重要元件")

> [!Note]
> 我們要強調，由於廣播技術Teams，即時活動通常超過一般 (會議) 一般。
>
> 就像其他較大型的媒體廣播服務一樣，我們仰賴內容傳遞網路將即時活動的內容傳送給收件者。 此內容受加密方法保護，並受僅根據即時活動會議組組發給收件者的存取權杖所授權。
>
> 請格外小心確保會議內容適合如此龐大的物件，或適當減少物件以用於敏感性內容。  
>
> 和業界一樣，對人員或基礎結構等安全性其他元素的入侵可能會影響即時活動的安全性。 組織應考慮在安全性規劃與練習中包含即時活動和其他廣播服務。

### <a name="event-group-roles"></a>事件群組角色

即時活動Teams讓 (、製作人、簡報者和出席者) 角色，以成功廣播及參與活動。 若要深入瞭解，請參閱 [事件群組角色](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)。

## <a name="key-components"></a>關鍵元件

從上圖中，您可以看見有五個與即時活動一起使用的重要Teams。

> [!NOTE]
> 若要概觀如何設定即時活動與出席者體驗，請查看[這些短片。](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)

### <a name="scheduling"></a>調度

Teams，召集人可以建立具有適當出席者許可權的活動、指定活動小組成員、選取生產方法，以及邀請出席者。 如果即時活動是從Yammer群組中建立，即時活動出席者可以使用Yammer交談與活動中的人員互動。

![新的即時活動畫面](../media/teams-live-events-schedule.png "顯示新即時活動畫面的螢幕擷取畫面，以建立及排程新的即時活動")

> [!IMPORTANT]
> 當使用者離線或以有限頻寬執行時，Teams 不會讓使用者排程會議或即時活動。

### <a name="production"></a>生產

視像輸入是即時活動的基礎，從單一網路攝影機到多相機專業影片製作，視音訊輸入可能會有所不同。 Microsoft 365即時事件支援各種生產案例，包括使用網路Teams或外部 App 或裝置所產生事件在 Teams 中產生的事件。 您可以根據專案需求和預算選擇這些選項。 產生事件的方法有兩種：

- **Teams：** 此製作方法可讓使用者使用網路Teams或使用會議室系統的 A/V Teams即時活動。 如果您想要使用連接到電腦的音訊和視像裝置，或邀請遠端簡報者參與活動，則此選項是最佳且最快的選項。 此選項可讓使用者輕鬆使用網路網路，並分享螢幕作為活動中的輸入。

- **外部應用程式或裝置**：外部編碼器可讓使用者直接從外部硬體或軟體型編碼器使用 Stream 來產生 [即時事件](https://stream.microsoft.com)。 如果您已經有工作室品質設備 (例如媒體混合器) ，支援串流至即時傳訊通訊協定 (RTMP) 服務時，這個選項是最佳選擇。 這類製作通常會用於大型活動，例如高官會堂 ，其中媒體混合器中的單一串流會廣播給觀眾。

    ![使用外部 App 或裝置產生的即時活動](../media/teams-live-events-external-encoder.png "螢幕擷取畫面顯示使用外部 App 或裝置生產方法產生的即時活動")

>[!Note]
> 從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](../tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。

### <a name="streaming-platform"></a>串流平臺

即時活動串流平臺由下列專案所決定：

- **Azure 媒體服務：Azure 媒體服務** 提供廣播 [](/azure/media-services/previous/)品質的視訊串流服務，讓您在現今最熱門的行動裝置上，接觸更多觀眾。 媒體服務增強協助工具、發佈和擴充性，並輕鬆且經濟地將內容串流到您當地或全球的觀眾，這一切同時保護您的內容。
- **Azure 內容傳遞網路 (CDN) ：** 您的串流一旦上電，就會透過 [Azure](/azure/cdn/)內容傳遞網路 (CDN) 。 Azure 媒體服務整合式CDN串流端點。 這樣一來，系統無需緩衝，就能夠在全球範圍中查看資料流程。

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise 內容傳遞網路 (eCDN) 

eCDN 的目標是從網際網路拍攝視像內容，並在整個企業發佈內容，而不會影響網路績效。 您可以使用下列其中一個通過認證的 eCDN 合作夥伴，針對貴組織內舉辦的即時活動優化您的網路：

- [蜂巢](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [斜坡](https://rampecdn.com)
- [河床](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>出席者體驗

出席者體驗是即時活動最重要的一面，出席者必須能參與即時活動，而沒有任何問題。 出席者體驗使用 Stream Player (用於在 Teams) 和 Azure Media Player (中產生的活動，用於在外部 App 或裝置) 中產生的事件，並且可跨桌面、瀏覽器和行動裝置 (iOS、Android) 運作。 Microsoft 365和Office 365兩Yammer Teams，即時出席者體驗會整合到這些共同合作工具中。

![即時活動出席者體驗範例](../media/teams-live-events-attendee.png "顯示即時活動出席者體驗的螢幕擷取畫面")

### <a name="live-event-usage-report"></a>即時活動使用方式報告

租使用者系統管理員可以在系統管理中心查看即時Microsoft Teams分析。  即時 [活動使用方式報告](../teams-analytics-and-reports/teams-live-event-usage-report.md) 會顯示組織中即時活動的活動概觀。  管理員可以查看事件使用方式資訊，包括事件狀態、開始時間、視圖及生產類型。  

## <a name="next-steps"></a>後續步驟

請前往[規劃Teams活動](plan-for-teams-live-events.md)。

### <a name="related-topics"></a>相關主題

- [在 Microsoft 365、Yammer 和 Microsoft Stream Microsoft Teams即時活動](/stream/live-event-m365)
- [從 Microsoft Teams 五場即時活動開始](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [在 Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream 中的即時活動](/stream/live-event-overview)
