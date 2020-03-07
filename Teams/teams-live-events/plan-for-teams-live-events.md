---
title: 規劃 Microsoft 團隊中的即時事件
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
localization_priority: Normal
ms.collection:
- M365-collaboration
search.appverid: MET150
description: 瞭解在 Microsoft 團隊中設定即時事件之前要考慮的因素。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f0c141751a9b67a47640ba5210c3cb7aeeadbb2
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558563"
---
# <a name="plan-for-live-events-in-microsoft-teams"></a>規劃 Microsoft 團隊中的即時事件

當您規劃團隊即時事件以在貴組織中舉行大型會議時，必須先考慮幾個因素，才能開始設定。 

## <a name="who-can-create-and-schedule-live-events"></a>誰可以建立及排程即時事件？ 
使用者必須具備下列先決條件，才能排程小組即時事件。

以下是必須指派的授權：  
- Office 365 企業版 E1、E3 或 E5 授權或 Office 365 A3 或 A5 授權
- Microsoft 團隊授權
- Microsoft 串流授權

> [!IMPORTANT]
> 使用者建立及排程即時事件必須有 Exchange Online 信箱。

請務必瞭解，必須有 Office 365 授權，才能以驗證的使用者身分參與即時事件，但這項需求視使用的生產方法而定：

- **針對團隊中產生的活動** 使用者必須獲指派團隊授權。
- **針對使用外部應用程式或裝置產生的事件**使用者必須獲指派串流授權。

> [!NOTE]
> 團隊即時事件現已提供給美國政府雲端社區（GCC）組織使用。

如需授權的詳細資訊，請參閱[Microsoft 團隊附加元件授權](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

使用者必須具備：
- 已啟用團隊中的私人會議排程（*TeamsMeetingPolicy-AllowPrivateMeetingScheduling 參數 = True*）。
- 在團隊會議中啟用影片共用（*TeamsMeetingPolicy-AllowIPVideo 參數 = True*）。
- 在團隊會議中啟用螢幕共用（*TeamsMeetingPolicy-ScreenSharingMode 參數 = EntireScreen*）。
- 已啟用團隊中的即時事件排程（*TeamsMeetingBroadcastPolicy-AllowBroadcastScheduling 參數 = True*）。
- 在串流中建立即時事件的許可權（適用于外部 app 或裝置生產）。

> [!IMPORTANT]
> 未驗證的匿名使用者無法在團隊即時事件中受邀成為發生器或簡報者。 
 
## <a name="who-can-watch-live-events"></a>誰可以觀看即時事件？

|**出席者可視性**       |**團隊生產**  |**外部 app 或裝置生產**  |
|------------------------------|-----------------|----------------------|
|公用（匿名使用者）      |  是            |  否                  |
|來賓使用者                   |  無<sup>1</sup> |  否                  |
|聯盟公司中的所有人 |  無<sup>2</sup> |  否                  |
|公司中的每個人           |  是            |  是                 |
|特定群組/人員      |  是            |  是                 |

如果即時事件是使用**組織範圍**選項設定， <sup>1</sup>就能監視即時事件。<br>
<sup>2</sup>只能將即時事件監視為匿名使用者。

 
## <a name="teams-live-events-and-skype-meeting-broadcast"></a>團隊即時活動與 Skype 會議廣播

下表重點說明即時事件中提供的核心功能與功能，以及它們與 Skype 會議廣播有何不同。 

|**功能**   |**Skype 會議廣播** |**小組中產生的事件** |**在外部 app 或裝置中產生的事件** |
|---------|---------|---------|---------|
|最大物件大小 |10,000 位出席者 |10000出席者<sup>1</sup> |10000出席者<sup>1</sup> |
|即時事件的最長持續時間 |4 小時 |4 小時 |4 小時 |
|每個 Office 365 租使用者的併發即時事件數量上限 |工資  | 工資  | 工資  |
|即時事件建立 |   Skype 會議廣播入口網站 |團隊，透過團隊進行 Yammer | 團隊、Yammer 透過團隊、資料流程 |
|物件參與– Yammer |&#x2714; |&#x2714; （整合式體驗） |&#x2714; （整合式體驗） |
|觀眾合作– & 的審查問題 |&#x2714;  |&#x2714; |&#x2714; |
|Windows 上的製造者用戶端 |&#x2714; （商務用 Skype） |&#x2714; （團隊） |&#x2714; （資料流程、透過資料流程內嵌的團隊） |
|Mac 上的製造者用戶端 |X  | &#x2714; （團隊） |&#x2714; （資料流程、透過資料流程內嵌的團隊） |
|製造者 UI 中的出席者計數 |X  |&#x2714; （團隊） |&#x2714; （資料流程、透過資料流程內嵌的團隊） |
|允許多重簡報者 |&#x2714; （商務用 Skype） |&#x2714; （團隊） |不適用  |
|在會議期間邀請簡報者 |&#x2714; （商務用 Skype） |X |不適用 |
|簡報者加入網頁和行動裝置 |&#x2714; （商務用 Skype）  |X |不適用 |
|聯盟 & 來賓簡報者/出席者 |&#x2714; （商務用 Skype）  | （即將推出） |不適用 |
|簡報者-PSTN 存取 |X |&#x2714; （團隊） |不適用 |
|展示畫面 |X |&#x2714; （團隊） |不適用 |
|展示 PowerPoint （PPT 共用） |&#x2714; |X （透過螢幕共用減輕） |不適用 |
|以雲端為基礎的會議錄製 |&#x2714; |&#x2714; |&#x2714; |
|自動發行錄製至串流 |X |X |&#x2714; |
|即時輔助字幕和字幕 |&#x2714; |&#x2714; |X |
|即時事件錄製中的標題 |&#x2714; |&#x2714; |&#x2714; |
|出席者的 DVR 控制項（暫停，倒帶） |&#x2714; |&#x2714; |&#x2714; |
|合作夥伴 eCDN 支援 |&#x2714; （Hive、Kollective、斜坡） |&#x2714; （Hive、Kollective、斜坡） |&#x2714; （Hive、Kollective、斜坡） |
|提供給發生器的廣播後出席報告 |&#x2714; |&#x2714; |X |
|物件觀點分析-即時投票 & 投票 |&#x2714; （Microsoft 脈衝） |X |X |

<sup>1</sup>設定的限制可能會變更。

## <a name="regional-availability"></a>地區可用性
您可以在世界各地的多個區域中使用團隊即時事件。 下列資訊顯示事件小組成員和出席者的可用性。 

> [!IMPORTANT]
> 系統會自動選取事件的地區，視召集人和 Office 365 組織而定。

**在這些區域中提供**
- 地區
- 歐洲/非洲
- 亞太地區
- 當地地區加拿大、印度、澳大利亞、日本、英國

**排除及考慮**
- **移至 [區域變數]：** 目前不支援小組 [從上面所列以外的區域變數] 到 [局部]。
- **中國：** 事件小組成員和出席者將無法使用團隊即時事件，因為 Azure CDN 在中國無法存取。 解決方法是使用公司 VPN 連線，透過客戶的公司網路來取得連接至 CDN 的用戶端。

## <a name="next-steps"></a>後續步驟
移至[設定小組即時事件](set-up-for-teams-live-events.md)。

### <a name="related-topics"></a>相關主題
- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
- [在團隊中設定即時事件設定](configure-teams-live-events.md)

