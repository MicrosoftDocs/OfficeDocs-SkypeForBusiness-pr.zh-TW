---
title: 在 Microsoft Teams 中建立整個組織的團隊
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Teams 中建立和管理整個組織的團隊，為中小型組織中的每個人提供自動共同作業的方式。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee527a457f7852bb9a6e7e6595754f1a64d2efd3
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562222"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>在 Microsoft Teams 中建立整個組織的團隊

全組織的團隊可自動讓中小型組織中的每個人成為單一和共同作業團隊的一員。

透過全組織的團隊，全域系統管理員可以輕鬆建立具有下列特性的公開團隊：
- 拉入組織中的每個使用者
- 當使用者加入並離開組織時，使用 Active Directory 讓成員資格保持在最新狀態。

只有全域系統管理員可以建立整個組織的團隊。 目前，整個組織的小組僅限於不超過 10，000 個使用者的組織。 每個租使用者也限制五個整個組織的團隊。 建立團隊時，如果符合這些需求，全域系統管理員會在 **選取 [從頭開始建立團隊**]**時，將** 整個組織視為一個選項。

![建立全組織團隊之全組織選項的螢幕擷取畫面。](media/create-org-wide-team.png "建立全組織團隊之全組織選項的螢幕擷取畫面")

建立整個組織的團隊時，所有全域系統管理員和 Teams 服務系統管理員都會新增為團隊擁有者，且所有作用中的使用者都會新增為團隊成員。 未授權的使用者也會新增至小組。 當未授權的使用者第一次登入 Teams 時，使用者會獲派 Microsoft Teams 探索授權。 若要深入瞭解探索授權，請參閱 [管理 Microsoft Teams Exploratory 授權](teams-exploratory.md)。

下列類型的帳戶不會新增至整個組織的小組：

- 封鎖不登入的帳戶
- 來賓使用者
- 資源或服務帳戶 (例如，與自動語音應答相關聯的帳戶和通話佇列) 
- 會議室或設備帳戶
- 共用信箱支援的帳戶

由於貴組織的目錄已更新為包含新的作用中使用者，或停用不再在貴公司工作的使用者帳戶，系統會自動同步處理變更，並從小組新增或移除使用者。 團隊成員無法離開整個組織的團隊。 如果您是小組擁有者，可以視需要手動新增或移除使用者。

> [!NOTE]
>
> - 如果您在建立團隊時沒有看到 **[整個** 組織] 選項，而且您是全域系統管理員，您可能已達到五個全組織的團隊限制，或者貴組織可能超過目前 10，000 個成員的大小限制。 我們預計在未來增加這個限制。 Teams 教育版目前無法使用全組織小組。
> - 不屬於會議室清單、設備和資源帳戶的會議室可能會新增或同步處理至整個組織的小組。 小組擁有者可輕鬆地從小組移除這些帳戶。
> - 系統新增或移除成員的所有動作會張貼在 [一般] 頻道。 頻道也會標示為在 Teams 用戶端中有新的活動。
> - 如果您的組織是 Teams 的新使用者且使用者不超過 5，000 人，我們將會自動為您的組織建立整個組織的團隊。 小組名稱會反映租用戶名稱，並擁有 [一般] 頻道。 全域系統管理員可以像其他任何小組一樣編輯這個小組。

## <a name="best-practices"></a>最佳做法

若要充分發揮整個組織的團隊，建議團隊擁有者執行下列工作：

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>只允許小組擁有者張貼到 [一般] 頻道

只允許小組擁有者張貼到 [一般] 頻道，以減少頻道「紛擾」。

1. 移至團隊，找出 [一般] 頻道，然後選取 **[...]。其他選項**  >  **管理頻道**。
2. 在 [ **頻道設定] 索引** 標籤上，按一下 [ **許可權]**，然後選取 [ **只有擁有者可以張貼訊息]**。

### <a name="turn-off-team-and-team-name-mentions"></a>關閉 @team 和 @[小組名稱] 提及項目

降低 @mentions 使其不會讓整個組織超載。

1. 移至團隊，然後按一下 **[...][管理團隊] 的更多選項** \> 。****
2. 在 [ **設定] 索引** 標籤上，按一下 **[@mentions** \> 關閉 **[顯示成員@team或 @[團隊名稱] 的選項**。

### <a name="automatically-show-important-channels"></a>自動顯示重要頻道

顯示重要的頻道以確保組織中的所有人都參與特定交談。 如需深入了解，請參閱[自動將頻道加入我的最愛方便整個團隊使用](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。

### <a name="set-up-channel-moderation"></a>設定頻道裁決

請考量設定頻道裁決，並為特定小組成員提供仲裁者功能。  (設定仲裁時，系統會自動提供團隊擁有者許可權。) 仲裁者可以：

- 控制誰可以在頻道中開始新文章
- 新增和移除仲裁者
- 控制小組成員是否可以回復現有的頻道訊息
- 控制 Bot 和連接器是否可以提交頻道訊息。

如需詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>移除可能不屬於的帳戶

即使成員無法離開整個組織的團隊，身為團隊擁有者，您還是可以移除不屬於的帳戶來管理團隊名單。 **請確認您使用 Teams 移除全組織小組中的使用者**。 如果您使用其他方式移除使用者，例如 Outlook 中的Microsoft 365 系統管理中心或群組，使用者可能會被新增回整個組織的小組。

## <a name="faq"></a>常見問題集

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>除了使用 Teams 用戶端之外，是否有其他方法可以建立整個組織的團隊？

只有全域系統管理員可以使用 Teams 用戶端建立整個組織的團隊。 如果貴組織將建立小組限制為使用 PowerShell，建議的因應措施是將您的全域系統管理員新增至可建立小組的使用者安全性群組。

如需詳細資訊，請參閱 [管理誰可以建立群組](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

如果這個因應措施不是選項，您可以使用 PowerShell 來建立公開團隊，並將全域系統管理員新增為團隊擁有者。 然後，讓全域系統管理員按一下小組名稱旁的 [更多選項]，按一下 [編輯小組]，然後將隱私權變更為 [全組織 - 貴組織中的所有人都會自動新增]。

> [!NOTE]
> 只有團隊擁有者可以存取 **[編輯團隊** ] 選項，而且只有全域系統管理員才能看到 [ **整個組織** ] 選項。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>是否有方法可將現有團隊轉換為整個組織的團隊？

全域系統管理員可以在 Teams 用戶端中編輯，將現有團隊轉換為整個組織的團隊。 移至小組名稱，按一下 [更多選項]  >  [編輯小組]。

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>我可以使用團隊範本建立整個組織的團隊嗎？

團隊範本無法用來建立整個組織的團隊。 此功能的工作目前正在進行中。

## <a name="see-also"></a>另請參閱

觀看有關 [如何在 Microsoft Teams 中建立全組織團隊的](https://www.youtube.com/watch?v=x3qGlwwCz_w)影片。
