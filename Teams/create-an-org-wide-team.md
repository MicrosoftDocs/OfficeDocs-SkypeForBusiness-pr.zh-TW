---
title: 在 Microsoft 團隊中建立組織範圍的小組
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在團隊中建立和管理組織範圍的團隊。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5c9c0986053fbfa5df2369205f75718abf5f114a
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/19/2019
ms.locfileid: "36184986"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>在 Microsoft 團隊中建立組織範圍的小組

組織範圍的小組為一個中小型組織中的每個人提供自動方法, 讓他們成為單一小組共同作業的一部分。

有了組織範圍的小組, 全域管理員就能輕鬆地建立一份公開小組, 在組織中的每位使用者都能拉入, 並在使用者加入並離開組織時, 將成員資格保持在最新狀態。 只有全域管理員才能建立整個組織的團隊, 而且目前組織範圍的小組僅限於5000使用者以外的組織。 此外, 每個租使用者最多隻能有五個組織範圍的團隊。 如果符合這些需求, 全域系統管理員會在建立小組時, 看到**組織外**的選項, 讓他們選取 [**從頭開始建立小組**]。 

![[組織範圍] 選項的螢幕擷取畫面, 可用於建立整個組織的小組](media/create-org-wide-team.png "[組織範圍] 選項的螢幕擷取畫面, 可用於建立整個組織的小組")

建立組織範圍的小組後, 所有全域管理員都會新增為團隊擁有者, 而所有作用中的使用者都會新增為小組成員。 未授權的使用者也會新增至小組。 未授權的使用者第一次登入小組時, 系統會為該使用者指派 Microsoft 團隊商業雲端試用版授權。 若要深入瞭解試用版授權, 請參閱[管理團隊商業雲端試用版優惠](iw-trial-teams.md)。 

這些類型的帳戶不會新增至您的組織內小組:

- 已封鎖登入的帳戶
- 來賓使用者
- 服務帳戶
- 會議室或設備帳戶
- 受共用信箱支援的帳戶

隨著貴組織的目錄已更新, 以包含新的作用中使用者, 或者如果使用者不在貴公司且其小組授權已停用, 變更會自動同步處理, 並在團隊中新增或移除使用者。 小組成員無法離開組織範圍的小組。 在小組擁有者中, 您可以視需要手動新增或移除使用者。

> [!NOTE]
> - 如果您在建立小組時沒有看到**組織範圍**選項, 且您是全域系統管理員, 則該功能可能仍在推出, 或貴組織可能超出5000成員的目前大小限制。 我們正在想要在未來增加此限制。
> - 不屬於會議室清單、裝置和資源帳戶的會議室, 可能會新增或同步處理到整個組織的小組。 小組擁有者可以輕鬆地將這些帳戶從小組中移除。

## <a name="best-practices"></a>最佳做法

若要充分發揮整個組織的小組, 我們建議小組擁有者執行下列操作。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>僅允許團隊擁有者張貼至 [一般] 頻道

只要將小組擁有者張貼到 [一般] 頻道, 即可減少通道噪音。 移至團隊, 然後按一下 [ **̇̇̇其他選項** > [**管理團隊**]。 按一下 [**設定**] 索引標籤上的 [**成員許可權**] > 選取 [**只有擁有者可以張貼郵件**]。

### <a name="turn-off-team-and-team-name-mentions"></a>關閉 @team 和 @ [團隊名稱] 提及

 減少 @mentions 讓他們避免整個組織超載。 移至團隊, 然後按一下 [ **̇̇̇其他選項** > [**管理團隊**]。 按一下 [**設定**] 索引標籤上的 [ <strong>@mentions</strong> ] > 關閉 **[顯示成員] 選項以 @team 或 @ [團隊名稱]]**。 

### <a name="automatically-favorite-important-channels"></a>自動將重要頻道設為最愛

我最愛的重要頻道, 以確保貴組織中的每個人都參與特定交談。 若要深入瞭解, 請參閱[適用于整個團隊的自動最愛頻道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。

### <a name="set-up-channel-moderation"></a>設定頻道裁決

考慮設定頻道裁決, 並向特定小組成員提供仲裁者的功能。 (設定裁決後, 系統會自動為團隊擁有者提供仲裁者的功能。)版主可以控制誰可以在頻道中開始新文章、新增及移除版主、控制小組成員是否可以回復現有的頻道訊息, 以及控制機器人與連接器是否可以提交頻道訊息。 如需詳細資訊, 請參閱[在 Microsoft 團隊中設定和管理 [頻道裁決](manage-channel-moderation-in-teams.md)]。

### <a name="remove-accounts-that-might-not-belong"></a>移除可能不屬於的帳戶

即使成員不能離開組織內的小組 (作為小組擁有者), 您還是可以移除不屬於的帳戶來管理團隊名單。 請確定您使用團隊從組織範圍的小組中移除使用者。 如果您使用另一個方法來移除使用者 (例如 Microsoft 365 系統管理中心或 Outlook 中的群組), 使用者可能會新增回組織範圍的小組。

## <a name="faq"></a>常見問題

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>是否有任何方式可以使用團隊用戶端來建立組織範圍以外的團隊？

全域管理員只能使用 [團隊用戶端] 來建立組織範圍的小組。 如果您的組織限制建立團隊使用 PowerShell, 建議的解決方法是將您的全域管理員新增至可建立小組的使用者安全性群組。 如需詳細資訊, 請參閱[管理可建立 Office 365 群組的人員](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。

如果這不是選項, 您可以使用 PowerShell 建立公開團隊, 並將全域管理員新增為團隊擁有者。 接著, 讓全域管理員按一下團隊名稱旁的 [**更多選項**], 按一下 [**編輯團隊**], 然後將隱私權變更為 [**全組織性]-您組織中的所有人都會自動新增**。 請注意, 只有團隊擁有者可以存取 [**編輯團隊**] 選項, 而且只有全域管理員才能看到**整個組織**的選項。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>是否有任何方式可將現有團隊轉換為組織範圍的團隊？

全域管理員可以在團隊用戶端中編輯現有的團隊, 將其轉換為組織範圍的團隊。 移至團隊名稱, 按一下 [**更多選項** > [**編輯團隊**]。
