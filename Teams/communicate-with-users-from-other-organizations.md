---
title: 在 Microsoft Teams 中與其他組織的使用者通訊
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何使用外部存取 (同盟)和來賓存取在 Microsoft Teams 中與其他組織的使用者進行通訊。
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 5f493643ede3fda0eab0791d5195d749f20eb7ad
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761379"
---
<a name="communicate-with-users-from-other-organizations-in-microsoft-teams"></a>在 Microsoft Teams 中與其他組織的使用者通訊
======================================================

當您需要與組織外部人的員通訊和共同作業時，Microsoft Teams 提供您兩種不同的方式。 第一個：**外部存取** (同盟) - 可讓您尋找、通話並與其他網域 (如 contoso.com) 中的使用者聊天。 第二個：**來賓存取** – 可讓您使用對方的電子郵件地址，將其新增到您的團隊。 您可以像與組織中的任何其他使用者一樣與來賓共同作業。

您可以同時使用外部存取和來賓存取，兩者不互相牴觸。

以下是更進階的選擇方法 (如需詳細比較，請跳至[比較外部與和來賓存取](#compare-external-and-guest-access))：

## <a name="external-access"></a>外部存取

當您需要可讓其他網域中的外部使用者尋找、通話、聊天和設定會議的解決方案時，可以使用**外部存取** (同盟)。 外部使用者不能存取組織的團隊或團隊資源。 當您要與仍在商務用 Skype (線上或內部部署) 或 Skype (2020 年年初推出) 中的外部使用者通訊時，請選擇外部存取。 

在 Teams 中預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。 Teams 系統管理員可以將其關閉或指定要包含 (或排除) 的網域。 若要深入了解，請閱讀[管理外部存取](manage-external-access.md) (英文)。 

如果您想讓外部使用者存取團隊和頻道，[來賓存取](#guest-access)可能是更好的作法。 


## <a name="guest-access"></a>來賓存取

使用 [來賓存取]**** 將個別使用者 (不論網域) 新增至團隊，讓他們可以使用 Microsoft 365 或 Office 365 應用程式 (例如 Word、Excel 或 PowerPoint) 來聊天、通話、開會及共同處理組織檔案(儲存在 SharePoint 或商務用 OneDrive 中)。 來賓使用者幾乎擁有與原生團隊成員相同的 Teams 功能。 若要深入了解，請閱讀 [Teams 中的來賓存取](guest-access.md) (英文)。

- 來賓會新增至組織的 Active Directory。
- 若要與來賓通訊，來賓必須使用其來賓帳戶登入 Teams。 這表示來賓可能必須登出自己的 Teams 帳戶，才能登入您的 Teams 帳戶，或者如果是相同帳戶，才能切換組織。
- 來賓使用者可以比外部存取 (同盟) 使用者存取 Teams 中的更多資源，例如檔案、團隊和頻道。
- Teams 系統管理員會控制來賓可以 (或無法) 在 Teams 系統管理中心執行的動作。 若要深入了解，請閱讀[管理來賓存取](manage-guests.md) (英文)。

如果您已在組織中開啟來賓存取，請從[小組中與來賓共同作業](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team)開始。


## <a name="compare-external-and-guest-access"></a>比較外部和來賓存取

| 功能 | 外部存取使用者 | 來賓存取使用者 |
|---------|-----------------------|--------------------|
| 使用者可以與其他公司的人員聊天 | 是 |是 |
| 使用者可以與其他公司的人員通話 | 是 | 是 |
| 使用者可以查看其他公司的人員是否可以通話或交談 | 是 | 是<sup>1</sup> |
| 使用者可以在外部租用戶中搜尋使用者 | 是<sup>2</sup> | 否 |
| 使用者可以共用檔案 | 否 | 是 |
| 使用者可以存取 Teams 資源 | 否 | 是 |
| 可將使用者新增至群組聊天 | 否 | 是 |
| 使用者可以受邀參加會議 | 是 | 是 |
| 可將其他使用者新增至與外部使用者的聊天 | 否<sup>3</sup> | 不適用 |
| 將使用者視為外部對象 | 是 | 是 |
| 會顯示目前狀態 | 是 | 是 |
| 會顯示不在辦公室訊息 | 否 | 是 |
| 可以封鎖個別使用者 | 否 | 是 |
| 支援以 @ 提及 | 是<sup>4</sup> | 是 |
| 可進行私人通話 | 是 | 是 |
| 查看撥入會議參與者的電話號碼 | 否<sup>5</sup> | 是 |
| 允許 IP 視訊 | 是 | 是 |
| 螢幕畫面分享模式 | 是<sup>4</sup> | 是 |
| 允許立即開會 | 否 | 是 |
| 編輯已傳送的訊息 | 是<sup>4</sup> | 是 |
| 可以刪除已傳送的訊息 | 是<sup>4</sup> | 是 |
| 在交談中使用 Giphy | 是<sup>4</sup> | 是 |
| 在交談中使用 Meme | 是<sup>4</sup> | 是 |
| 在交談中使用貼圖 | 是<sup>4</sup> | 是 |
||||

<sup>1</sup>前提是已將使用者新增為來賓，且使用者以來賓身分登入來賓租用戶。<br>
<sup>2</sup>僅透過電子郵件或工作階段初始通訊協定 (SIP) 位址。<br>
<sup>3</sup>外部 (同盟) 聊天僅限一對一聊天。<br>
<sup>4</sup>針對來自兩個不同組織的僅限 Teams 對僅限 Teams 使用者，支援一對一聊天。 <br>
<sup>5</sup> 依預設，外部參與者無法查看撥入的參與者電話號碼。 如果您想要維護這些電話號碼的隱私權，請選取 [進入/退出宣告類型]**** 的 [音調]**** (這可避免 Teams 將號碼朗讀出來)。 若要深入了解，請參閱[開啟或關閉 Microsoft Teams 中會議的進入和退出宣告](turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams.md)。

## <a name="related-topics"></a>相關主題

[Teams 中的外部存取](manage-external-access.md)

[Teams 中的來賓存取](guest-access.md)

