---
title: 在 Microsoft Teams 中規劃即時活動
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 08/19/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: sonua
f1.keywords:
- NOCSH
localization_priority: Priority
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 在本文中，您將了解在 Microsoft Teams 中設定即時活動之前需考量的因素。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 51c81bb5c9ec945d7a7c47021a6a0af705c98883
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/05/2020
ms.locfileid: "44042850"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>在 Microsoft Teams 中規劃即時活動

當您規劃 Teams 即時活動來舉辦貴組織大型會議時，必須先考量幾個因素，再開始進行設定。

## <a name="who-can-attend-create-and-schedule-live-events"></a>哪些人可以參加、建立及排定即時活動？

任何人都可以在沒有授權的情況下參加即時活動。 請閱讀[系統管理員快速入門 - 會議與即時活動](../quick-start-meetings-live-events.md)。

使用者需要具備下列必要條件，才能排定 Teams 即時活動。

以下是必須指派的授權：  

- Office 365 企業版 E1、E3 或 E5 授權，或 Office 365 A3 或 A5 授權
- Microsoft Teams 授權
- Microsoft Stream 授權

> [!IMPORTANT]
> 建立和排程即時活動的使用者必須擁有 Exchange Online 信箱。

請務必知道，若要以已驗證的使用者身分參與即時活動，必須要具備 Office 365 授權，但這項需求視使用的生產方法而定：

- **針對 Teams 中產生的活動**，使用者必須取得指派的 Teams 授權。
- **針對外部應用程式或裝置所產生的活動**，使用者必須取得指派的 Stream 授權。

> [!NOTE]
> Teams 即時活動現在適用於美國政府社群雲端 (GCC) 組織。

如需授權的詳細資訊，請參閱 [Microsoft Teams 附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

使用者必須：

- 已啟用 Teams 中的私人會議排程 (*TeamsMeetingPolicy -AllowPrivateMeetingScheduling 參數 = True*)。
- 在 Teams 會議中啟用影片共用 (*TeamsMeetingPolicy -AllowIPVideo 參數 = True*)。
- 在 Teams 會議中啟用螢幕共用 (*TeamsMeetingPolicy -ScreenSharingMode 參數 = EntireScreen*)。
- 已啟用 Teams 中的即時活動 (*TeamsMeetingBroadcastPolicy -AllowBroadcastScheduling 參數 = True*)。
- 在 Stream 中建立即時活動的權限 (適用於外部應用程式或裝置生產)。
- 已設定共存模式，以便排程 Teams 會議 (*孤島、會議優先或僅 Teams*)。

> [!IMPORTANT]
> 未經驗證的匿名使用者無法受邀為 Teams 即時活動製作人或簡報者。

## <a name="who-can-watch-live-events"></a>誰可以觀看即時活動？

|**出席者可見度**       |**Teams 生產**  |**外部應用程式或裝置生產**  |
|------------------------------|-----------------|----------------------|
|公用 (匿名使用者)      |  是            |  否                  |
|來賓使用者                   |  是            |  否                  |
|外部存取 (同盟) 公司中的每個人 |  是<sup>1</sup>|  否                  |
|公司中的每個人           |  是            |  是                 |
|特定群組/人員      |  是            |  是                 |

<sup>1</sup> 外部存取 (同盟) 的出席者只能透過人員與群組邀請 <br>

## <a name="teams-live-events-and-skype-meeting-broadcast"></a>Teams 即時活動和 Skype 會議廣播

下表醒目提示即時活動中提供的核心功能和功能，以及它們與 Skype 會議廣播有何差異。

|**功能**   |**Skype 會議廣播** |**Teams 中產生的活動** |**在外部應用程式或裝置中生產的活動** |
|---------|---------|---------|---------|
|對象數目上限 |10,000 位出席者 |10,000 位出席者<sup>1</sup> |10,000 位出席者<sup>1</sup> |
|即時活動的持續時間上限 |4 小時 |4 小時 |4 小時 |
|即時活動中簡報者和製作人人數上限 |10 <sup>2</sup> |10 <sup>2</sup> |10 <sup>2</sup> |
|每個 Office 365 組織的並行即時活動數量上限 |15  | 15  | 15  |
|即時活動建立 |   Skype 會議廣播入口網站 |Teams，透過 Teams 的 Yammer | Teams，透過 Teams 的 Yammer，Stream |
|對象參與 – Yammer |&#x2714; |&#x2714; (整合式體驗) |&#x2714; (整合式體驗) |
|對象參與 – 仲裁常見問題集 |&#x2714;  |&#x2714; |&#x2714; |
|Windows 上的製作人用戶端 |&#x2714; (商務用 Skype) |&#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|Mac 上的製作人用戶端 |&#x274C;  | &#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|製作人 UI 中的出席者計數 |&#x274C;  |&#x2714; (Teams) |&#x2714; (Stream，透過內嵌 Stream 的 Teams) |
|允許多個簡報者 |&#x2714; (商務用 Skype) |&#x2714; (Teams) |不適用  |
|在會議期間邀請簡報者 |&#x2714; (商務用 Skype) |&#x274C; |不適用 |
|網路和行動裝置上的簡報者加入 |&#x2714; (商務用 Skype)  |&#x274C; |N/A |
|外部存取 (同盟) 和來賓簡報者/出席者 |&#x2714; (商務用 Skype)  |  &#x2714; (Teams) |不適用 |
|簡報者 - PSTN 存取 |&#x274C; |&#x2714; (Teams) |不適用 |
|展示畫面 |&#x274C; |&#x2714; (Teams) |不適用 |
|在 Windows 上共用系統音訊 (僅適用於螢幕共用時)|&#x274C; |&#x2714; (Teams) |&#x2714; |
|展示 PowerPoint (PPT 共用) |&#x2714; |&#x274C; (透過螢幕畫面分享緩解) |不適用 |
|雲端式會議錄製 |&#x2714; |&#x2714; |&#x2714; |
|自動發佈錄製到 Stream |&#x274C; |&#x274C; |&#x2714; |
|即時輔助字幕和翻譯字幕 |&#x2714; |&#x2714; |&#x274C; |
|即時活動錄製中的輔助字幕 |&#x2714; |&#x2714; |&#x2714; |
|出席者 DVR 控制項 (暫停、倒轉) |&#x2714; |&#x2714; |&#x2714; |
|合作夥伴 eCDN 支援 |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |&#x2714; (Hive、Kollective、Ramp) |
|適用於製作人的廣播後出席報告 |&#x2714; |&#x2714; |&#x274C; |
|對象人氣分析 - 即時投票與票選 |&#x2714; (Microsoft Pulse) |&#x274C; |&#x274C; |

<sup>1</sup> 設定的限制可能會變更。 查看[Teams 的限制和規格](../limits-specifications-teams.md)。<br/>
<sup>2</sup> 您最多可以在即時活動中擁有 250 位簡報者和製作人，但只會在清單中顯示最後 10 位發言者。

## <a name="regional-availability"></a>區域可用性

您可以在世界各地多個區域中使用 Teams 即時活動。 下列資訊顯示事件小組成員和出席者的可用性。

> [!IMPORTANT]
> 系統會根據召集人和 Microsoft 365 租用戶位置，自動選取活動的區域。

**可在這些地區資料中心使用**

- 美洲地區
- 亞太地區
- 歐洲/非洲

**這些國家/地區的資料位置**

- 澳洲
- 加拿大
- 印度
- 日本
- 英國

**排除和考量**

- **資料位置：** Teams 資料位置，目前不支援上述以外的國家/地區。
- **中國：** 活動小組成員和出席者無法使用 Teams 即時活動，因為無法在中國存取 Azure CDN。 因應措施是使用公司 VPN 連線，透過客戶的公司網路，讓用戶端連線到 CDN。

## <a name="next-steps"></a>後續步驟

移至[設定 Teams 即時活動](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相關主題

- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
- [在 Teams 中設定即時活動設定](configure-teams-live-events.md)
