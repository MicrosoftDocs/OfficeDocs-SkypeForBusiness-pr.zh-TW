---
title: 使用來賓存取和外部存取與組織外的人員共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: vinbel, luises
ms.topic: article
ms.service: msteams
audience: admin
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
description: 了解如何使用外部存取 (同盟) 和來賓存取在 Microsoft Teams 中通話、聊天、尋找和新增來自組織外部的使用者。
ms.openlocfilehash: db5d29a9d7afd121c3cecc47aa3ce717bb815f54
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592738"
---
# <a name="use-guest-access-and-external-access-to-collaborate-with-people-outside-your-organization"></a>使用來賓存取和外部存取與組織外的人員共同作業

當您需要與組織外部的人員通訊和共同作業時，Microsoft Teams 提供您兩個選項：

- **外部存取** - 一種同盟類型，可讓使用者尋找、通話及與其他組織中的人員聊天。 除非他們受邀成為來賓，否則無法將這些人新增至小組。
- **來賓存取** - 來賓存取可讓您邀請組織外部的人員加入小組。 受邀的人員會在 Azure Active Directory 中取得一個來賓帳戶。

請注意，Teams 允許您邀請組織外部的人員參加會議。 這不需要設定外部或來賓存取。

## <a name="external-access-federation"></a>外部存取 (同盟)

如果您需要尋找、通話、聊天以及設定與使用 Teams、商務用 Skype (線上或內部部署) 或 Skype 的組織外部人員的會議，請設定外部存取。 

預設會對所有網域啟用外部存取。 您可以透過允許或封鎖特定網域來限制外部存取，或將它關閉。

![外部存取設定的螢幕擷取畫面。](media/external-access-federation-settings.png)

若要設定外部存取，請參閱[管理外部存取](manage-external-access.md)。 

>[!NOTE]
> [Microsoft Teams (傳統) 免費](https://support.microsoft.com/office/welcome-to-microsoft-teams-free-classic-6d79a648-6913-4696-9237-ed13de64ae3c)授權不支援外部存取。

## <a name="guest-access"></a>來賓存取

使用來賓存取將來自組織外部的人員新增至小組，他們可在其中聊天、通話、開會及就檔案共同作業。 來賓幾乎擁有與原生小組成員相同的所有 Teams 功能。 如需詳細資訊，請參閱 [Teams 中的來賓體驗](guest-experience.md)。

來賓會以 B2B 使用者的身分新增至組織的 Azure Active Directory 中，且必須使用其來賓帳戶登入 Teams。 這表示他們可能必須登出自己的組織，才能登入您的組織。

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
<sup>4</sup> 依預設，外部參與者無法查看撥入的參與者電話號碼。如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型] 的 [音調] (這可避免 Teams 將號碼朗讀出來)。若要深入了解，請參閱 [開啟或關閉 Microsoft Teams 中會議的進入和退出宣告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。<br>
<sup>5</sup> 預設會允許，但可以由 Teams 系統管理員關閉

## <a name="related-topics"></a>相關主題

[Teams 中的外部存取](manage-external-access.md)

[Teams 中的來賓存取](guest-access.md)
