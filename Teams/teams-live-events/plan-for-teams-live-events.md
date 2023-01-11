---
title: 在 Microsoft Teams 中規劃即時活動
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
search.appverid: MET150
description: 在本文章中，您將瞭解在 Microsoft Teams 中設定即時活動之前需考量的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cde485a3cf290c105ae475e6f7733787ba6971a2
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767604"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中規劃即時活動

當您規劃使用 Teams 即時活動來舉辦組織中的大型會議時，必須先考量幾個因素，再開始進行設定。

> [!NOTE]
> For details about Teams live events on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3). See [prepare your organization](../prepare-network.md) to learn about bandwidth requirements for Teams live events.

## <a name="who-can-attend-create-and-schedule-live-events"></a>哪些人可以參加、建立及排定即時活動？

Anyone can attend a live event without a license. Read [Admin quick start - Meetings and live events](../quick-start-meetings-live-events.md).

使用者需要具備下列必要條件，才能排定 Teams 即時活動。

若要組織、產生或出席 Teams 即時活動，您必須獲派以下授權：  

- **若要組織：** Microsoft 或 Office 365 企業版 E1、E3 或 E5 授權，**[或]** Microsoft 或 Office 365 教育版 A3 或 A5 授權。
- **To produce or present:** A Microsoft or Office 365 Enterprise E1, E3 or E5 license, **[or]** a Microsoft or Office 365 Education A1, A3 or A5 license. The exception to this requirement is guest users can present without a license if the other criteria for [guest users](plan-for-teams-live-events.md#guest-to-present) is met.
- Microsoft Teams 授權 - 此授權包含在第一個和第二個項目符號列出的授權中。

> [!NOTE]
> 目前，沒有任何 Microsoft 365 小型企業方案可供用來建立及保留 Teams 即時活動。

請務必知道，若要以已驗證的使用者身分參與即時活動，必須要具備 Microsoft 365 或 Office 365 授權，但這項需求視使用的生產方法而定：

- **針對在 Teams 中製作的活動或使用 Teams 支援的編碼器**  使用者必須獲指派 Teams 授權。

> [!NOTE]
> Teams 即時活動現在適用於美國政府社群雲端 (GCC) 組織。

如需授權的詳細資訊，請參閱 [Microsoft Teams 附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

使用者必須：

- 已啟用 Teams 中的私人會議排程 (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 參數 = True*)。
- 在 Teams 會議中啟用影片共用 (*TeamsMeetingPolicy -AllowIPVideo 參數 = True*)。
- 在 Teams 會議中啟用螢幕共用 (*TeamsMeetingPolicy -ScreenSharingMode 參數 = EntireScreen*)。
- 已啟用 Teams 中的即時活動 (*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 參數 = True*)。
- 已設定共存模式，以便排程 Teams 會議 (*孤島、會議優先或僅 Teams*)。

> [!IMPORTANT]
> 未經驗證的匿名使用者無法受邀為 Teams 即時活動製作人或簡報者。

### <a name="guest-to-present"></a>[出席來賓](#guest-to-present)

若要讓來賓在即時活動中簡報，請執行下列工作：

1. [將使用者新增為團隊的來賓](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)。
2. 讓使用者接受來賓邀請並加入團隊。
3. [排程即時活動，並將來賓新增至您的活動群組](https://support.microsoft.com/article/schedule-a-teams-live-event-7a9ce97c-e1cd-470f-acaf-e6dfc179a0e2)。

As a best practice, we recommend that you create a channel for producers and presenters of the live event so they can chat and share information before the event. Guests who don't have Microsoft 365 credentials won't see the Calendar in Teams. To make it easy for them to join the event, producers can post the event link to the channel. Presenters can then open Teams, go to the channel, and then select the link to join the event.

## <a name="who-can-watch-live-events"></a>誰可以觀看即時活動？

| 出席者可見度 | Teams 產生 | 外部應用程式或裝置產生 | Teams 支援的編碼器
|------------------------------|-----------------|----------------------|----------------|
|公用 (匿名使用者)      |  是            |  否                  | 是
|來賓使用者                   |  是<sup>1</sup>            |  否                  |  是            |
|外部存取 (同盟) 公司中的每個人 |  是<sup>1</sup>|  否                  | 是            |
|公司中的每個人           |  是            |  是                 | 是                |
|特定群組/人員      |  是            |  是                 | 是                |

<sup>1</sup> 出席者只能透過人員與群組邀請 <br>

## <a name="teams-live-events"></a>Teams 即時活動

下表醒目提示即時活動中提供的核心功能和功能

> [!IMPORTANT]
> **Microsoft 365 的即時活動限制增加**
>
> **為了繼續支援客戶的需求，我們會將即時活動的暫時限制延長至 2023 年 6 月 30 日，包括：**
>
>- 活動支援最多達 20000 個出席者
>- 不同租用戶可以同時進行 50 個活動
>- 每個廣播的活動持續時間 (16 小時)
>
> Additionally, live events with up to 100,000 attendees can be planned through the Microsoft 365 live events assistance program. The team will assess each request and work with you to determine options that may be available. [Learn more](https://aka.ms/Stream/Blog/LiveEventOptions).

| 功能 | Teams 中產生的活動 | 外部應用程式或裝置中產生的活動 |
|---------|---------|---------|
|對象數目上限 |10,000 位出席者<sup>1</sup> |10,000 位出席者<sup>1</sup> |
|即時活動的持續時間上限 |4 小時 |4 小時 |
|即時活動中簡報者和製作人人數上限 |10 <sup>2</sup> |10 <sup>2</sup> |
|每個 Microsoft 365 或 Office 365 組織的並行即時活動數量上限 | 15  | 15  |
|即時活動建立 |Teams，透過 Teams 的 Yammer | Teams，透過 Teams 的 Yammer，Stream |
|對象參與 – Yammer |&#x2714; (整合式體驗) |&#x2714; (整合式體驗) |
|對象參與 – 仲裁常見問題集 |&#x2714; |&#x2714; |
|Windows 上的製作人用戶端 |&#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|Mac 上的製作人用戶端 |&#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|製作人 UI 中的出席者計數 |&#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|允許多個簡報者 |&#x2714; (Teams) |N/A  |
|在會議期間邀請簡報者 |&#x274C; |N/A |
|網路和行動裝置上的簡報者加入 |&#x274C; |N/A |
|外部存取 (同盟) 和來賓簡報者/出席者 |&#x2714; (Teams) |N/A |
|簡報者 - PSTN 存取 |&#x2714; (Teams) |不適用 |
|展示畫面 |&#x2714; (Teams) |不適用 |
|在 Windows 上共用系統音訊 (僅適用於螢幕共用時)|&#x2714; (Teams) |&#x2714; |
|展示 PowerPoint (PPT 共用) |&#x274C; (透過螢幕畫面分享緩解) |不適用 |
|雲端式會議錄製 |&#x2714; |&#x2714; |
|自動發佈錄製到 Stream |&#x274C; |&#x2714; |
|即時輔助字幕和翻譯字幕 |&#x2714; |&#x274C; |
|即時活動錄製中的輔助字幕 |&#x2714; |&#x2714; |
|出席者 DVR 控制項 (暫停、倒轉) |&#x2714; |&#x2714; |
|Microsoft eCDN |&#x2714; |&#x2714; |
|合作夥伴 eCDN 支援 |&#x2714; (Kollective, Hive, Ramp, Riverbed) |&#x2714; (Hive, Kollective, Ramp, Riverbed) |
|適用於製作人的廣播後出席報告 |&#x2714; |&#x274C; |
|對象人氣分析 - 即時投票與票選 |&#x274C; |&#x274C; |

<sup>1</sup> The limits that are set might be changed. Check [Limits and specifications for Teams](../limits-specifications-teams.md).<br/>
<sup>2</sup> 您最多可以在即時活動中擁有 100 位簡報者和製作人，但只會在清單中顯示最後 10 位發言者。

## <a name="regional-availability"></a>區域可用性

You can use Teams live events in multiple regions across the world. The following information shows availability for event team members and attendees.

> [!IMPORTANT]
> 系統會根據召集人和 Microsoft 365 租用戶位置，自動選取活動的區域。

**可在這些地區資料中心使用**

- 北美
- 中美洲
- 南美洲
- 亞太地區
- 歐洲/非洲

**這些國家/地區的資料位置 (支援)**

- 澳洲
- 巴西
- 加拿大
- 法國
- 德國
- 印度
- 日本
- 挪威
- 新加坡
- 南非
- 南韓
- 瑞士
- 阿拉伯聯合大公國
- 英國

**排除和考量事項**

- **資料位置：** Teams 資料位置，目前不支援上述以外的國家/地區。

## <a name="next-steps"></a>後續步驟

移至[設定 Teams 即時活動](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
