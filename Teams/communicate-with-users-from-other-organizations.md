---
title: 使用來賓存取和外部存取與組織外的人員共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
ms.custom: chat-teams-channels-revamp
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
description: 了解如何使用外部存取和來賓存取在 Microsoft Teams 中通話、聊天、尋找和新增來自組織外部的使用者。
ms.openlocfilehash: f416453a93c07945f9df55c863f76cbb8b736a78
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198315"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>使用來賓存取和外部存取與組織外的人員共同作業

此文章描述與貴組織外部人員共同作業的兩個選項：

- **外部存取** - 一種同盟類型，可讓使用者尋找、通話及與其他組織中的人員聊天。 除非他們受邀成為來賓，否則無法將這些人新增至小組。
- **來賓存取** - 來賓存取可讓您邀請組織外部的人員加入小組。 受邀的人員會在 Azure Active Directory 中取得一個來賓帳戶。

如需 Microsoft 365 外部共同作業的完整概觀，請參閱[Microsoft 365 中的外部共同作業選項概觀](/microsoft-365/enterprise/external-guest-access)。

## <a name="external-access-external-chat-and-meetings"></a>外部存取 (外部聊天和會議)

如果您需要尋找、通話、聊天以及設定與使用 Teams、商務用 Skype (線上或內部部署) 或 Skype 的組織外部人員的會議，請設定外部存取。 

預設會對所有網域啟用外部存取。 您可以透過允許或封鎖特定網域來限制外部存取，或將它關閉。

![外部存取設定的螢幕擷取畫面。](media/external-access-federation-settings.png)

下列租用戶可使用外部存取:
- 受管理的企業帳戶
     - 僅限商業之間
     - 僅限 GCC 之間
     - 僅限 GCC High 之間
     - 僅限 DOD 之間
- 未受管理的 (個人) 帳戶
     - 僅限商業和個人帳戶之間
- 商務用 Skype interop
     - 在商業、GCC、GCC High 和 DoD 之間和跨地區
- Skype interop
     - 僅限商業與 Skype 之間

若要設定外部存取，請參閱[管理外部存取](manage-external-access.md)。 

>[!NOTE]
> [Microsoft Teams (傳統) 免費](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c)授權不支援外部存取。

## <a name="guest-access"></a>來賓存取

使用來賓存取將來自組織外部的人員新增至小組，他們可在其中聊天、通話、開會及就檔案共同作業。 來賓幾乎擁有與原生小組成員相同的所有 Teams 功能。 如需詳細資訊，請參閱 [Teams 中的來賓體驗](guest-experience.md)。

來賓會新增到貴組織的 Azure Active Directory 成為 B2B 共同作業使用者，而且必須使用他們的來賓帳戶登入 Teams。 這表示他們可能必須登出自己的組織，才能登入您的組織。

來賓存取權適用於下列租用戶:

- 橫跨和介於商用與 GCC
- 僅限 GCC High 之間
- 僅限 DOD 之間

若要為 Teams 設定來賓存取，請參閱[在小組中與來賓共同作業](/microsoft-365/solutions/collaborate-as-team)。

## <a name="compare-external-and-guest-access"></a>比較外部和來賓存取

下表顯示使用外部存取 (同盟) 和來賓之間的差異。 在這兩個情況下，系統會將組織外部的人員向您的使用者識別為外部。

### <a name="things-your-users-can-do"></a>您的使用者可以執行的動作

| 使用者可以 | 外部存取使用者 | 來賓 |
|---------|-----------------------|--------------------|
| 與其他組織中的人員聊天 | 是 | 是 |
| 與另一個組織中的人員通話 | 是 | 是 |
| 查看來自另一個組織的人員是否可以通話或聊天 | 是 | 是<sup>1</sup> |
| 搜尋其他組織中的人員 | 是<sup>2</sup> | 否 |
| 共用檔案 | 否 | 是 |
| 查看另一個組織中某人的外出訊息 | 否 | 是 |
| 封鎖另一個組織的某人  | 否 | 是 |
| 使用 @ 提及 | 是<sup>3</sup> | 是 |

### <a name="things-people-outside-your-organization-can-do"></a>組織外部的人員可以執行的動作

| 組織外部的人員可以 | 外部存取使用者 | 來賓 |
|---------|-----------------------|--------------------|
| 存取 Teams 資源 | 否 | 是 |
| 被新增至群組聊天 | 是 | 是 |
| 受邀參加會議 | 是 | 是 |
| 可進行私人通話 | 是 | 是<sup>5</sup> |
| 檢視撥入會議參與者的電話號碼 | 否<sup>4</sup> | 是 |
| 使用 IP 視訊 | 是 | 是<sup>5</sup> |
| 使用螢幕畫面分享 | 是<sup>3</sup> | 是<sup>5</sup> |
| 使用立即開會 | 否 | 是<sup>5</sup> |
| 編輯已傳送的訊息 | 是<sup>3</sup> | 是<sup>5</sup> |
| 刪除已傳送的訊息 | 是<sup>3</sup> | 是<sup>5</sup> |
| 在交談中使用 Giphy | 是<sup>3</sup> | 是<sup>5</sup> |
| 在交談中使用 Meme | 是<sup>3</sup> | 是<sup>5</sup> |
| 在交談中使用貼圖 | 是<sup>3</sup> | 是<sup>5</sup> |
| 會顯示目前狀態 | 是 | 是 |
| 使用 @ 提及 | 是<sup>3</sup> | 是 |

<br>

<sup>1</sup> 前提是已將使用者新增為來賓，並使用來賓帳戶登入。<br>
<sup>2</sup> 僅透過電子郵件或工作階段初始通訊協定 (SIP) 位址。<br>
<sup>3</sup> 支援來自兩個不同組織的僅 Teams 到僅 Teams 使用者的一對一聊天。 <br>
<sup>4</sup> By default, external participants can't see the phone numbers of dialed-in participants. If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams). To learn more, read [Turn on or off entry and exit announcements for meetings in Microsoft Teams](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md). <br>
<sup>5</sup> 預設會允許，但可以由 Teams 系統管理員關閉

## <a name="related-topics"></a>相關主題

[Teams 中的外部存取](manage-external-access.md)

[Teams 中的來賓存取](guest-access.md)
