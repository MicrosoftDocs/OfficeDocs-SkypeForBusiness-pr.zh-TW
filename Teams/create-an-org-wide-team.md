---
title: 在組織中建立全組織Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Teams 中建立及管理全組織團隊，為中小型企業中的每個人提供自動共同合作的方式。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a6faac9e0c04f71bddb69b0a8bd7748072699edb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58589747"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>在組織中建立全組織Microsoft Teams

全組織團隊提供自動方式，讓中小型企業中的每個人都成為單一且共同合作團隊的一員。

使用全組織團隊，全域系統管理員可以輕鬆地建立具有下列特性的公用小組：
- 拉取組織中每個使用者 
- 當使用者加入並離開組織時，使用 Active Directory 保持成員資格最新狀態。

只有全域系統管理員可以建立全組織團隊。 目前，全組織團隊僅限不超過 10，000 個使用者的組織。 每個租使用者也有五個全組織團隊的限制。 建立團隊時，如果符合這些要求，全域系統管理員在選取從頭開始建立團隊時，會看到全組織 **為選項**。 

![建立全組織團隊之全組織選項的螢幕擷取畫面](media/create-org-wide-team.png "建立全組織團隊之全組織選項的螢幕擷取畫面")

建立全組織團隊時，所有全域系統管理員Teams服務系統管理員會新增為團隊擁有者，所有使用中的使用者會新增為小組成員。 未授權的使用者也會新增至小組。 未授權使用者第一次登Teams時，會指派使用者Microsoft Teams探索授權。 若要深入瞭解探索授權，請查看管理探索Microsoft Teams[授權](teams-exploratory.md)。 

下列類型的帳戶不會新加入整個組織的小組：

- 被封鎖而無法登入的帳戶
- 來賓使用者
- 例如，資源 (服務帳戶，例如與自動話務員和通話佇列相關聯的) 
- 會議室或設備帳戶
- 共用信箱支援的帳戶

隨著貴組織的目錄更新為包含新的使用中使用者，或停用不再在貴公司工作的使用者的帳戶，系統會自動同步處理變更，並新增或移除團隊中的使用者。 小組成員無法離開全組織的小組。 如果您是小組擁有者，可以視需要手動新增或移除使用者。

> [!NOTE]
> - 如果您在建立團隊時沒看到全組織選項，而您是全域系統管理員，表示您可能已達到五個全組織團隊限制，或貴組織可能超過目前 10，000 個成員的大小限制。 我們預計在未來增加這個限制。 Teams 教育版目前無法使用全組織小組。
> - 非會議室清單、設備和資源帳戶的一部分，可能會新增或同步到整個組織的小組。 小組擁有者可輕鬆地從小組移除這些帳戶。
> - 系統新增或移除成員的所有動作會張貼在 [一般] 頻道。 頻道也會標示為在 Teams 用戶端中有新的活動。
> - 如果貴組織是新使用者，且使用者不超過 5，000 人Teams我們會自動為貴組織建立全組織團隊。 小組名稱會反映租用戶名稱，並擁有 [一般] 頻道。 全域系統管理員可以像其他任何小組一樣編輯這個小組。

## <a name="best-practices"></a>最佳做法

若要在全組織團隊中取得最大權益，我們建議團隊擁有者執行下列工作：

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>只允許小組擁有者張貼到 [一般] 頻道

只允許小組擁有者張貼到 [一般] 頻道，以減少頻道「紛擾」。 

1. 請前往小組，找出一般頻道，然後選取 **1 100 1000 1000 1000 1000 2013 -2013**-2013-201331331133113311  >   
2. 在 [**頻道設定」** 選項卡上，按一下 **[許可權**」，然後選取 [只有 **擁有者可以張貼訊息。**

### <a name="turn-off-team-and-team-name-mentions"></a>關閉 @team 和 @[小組名稱] 提及項目

降低 @mentions 使其不會讓整個組織超載。 

1. 移至小組，然後按一下 [更多選項]  >  [管理小組]。 
2. 在 [設定] 索引標籤上，按一下 [@mentions]<strong></strong> > 關閉 [向成員顯示 @team 或 @[小組名稱] 選項]。 

### <a name="automatically-show-important-channels"></a>自動顯示重要頻道

顯示重要的頻道以確保組織中的所有人都參與特定交談。 如需深入了解，請參閱[自動將頻道加入我的最愛方便整個團隊使用](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。 

### <a name="set-up-channel-moderation"></a>設定頻道裁決

請考量設定頻道裁決，並為特定小組成員提供仲裁者功能。  (設定仲裁時，團隊擁有者會自動獲得仲裁者功能。) 仲裁者可以：

- 控制誰可以在頻道中開始新文章
- 新增和移除仲裁者
- 控制小組成員是否可以回復現有的頻道訊息
- 控制 Bot 和連接器是否可以提交頻道訊息。

如需詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>移除可能不屬於的帳戶

即使成員無法離開整個組織團隊，但做為團隊擁有者，您可以移除不屬於的帳戶來管理小組名冊。 **請確認您使用 Teams 移除全組織小組中的使用者**。 如果您使用另一種方式移除使用者，例如 Microsoft 365 系統管理中心 或 Outlook 中的群組，使用者可能會重新加入整個組織的團隊。

## <a name="faq"></a>常見問題集

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>除了使用用戶端外，還有其他建立全組織Teams的方法嗎？

全域系統管理員只能使用全域用戶端建立整個Teams團隊。 如果貴組織將建立小組限制為使用 PowerShell，建議的因應措施是將您的全域系統管理員新增至可建立小組的使用者安全性群組。

詳細資訊，請參閱管理 [誰可以建立群組](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

如果這個解決方法不是選項，您可以使用 PowerShell 建立公用小組，並新增全域系統管理員做為團隊擁有者。 然後，讓全域系統管理員按一下小組名稱旁的 [更多選項]，按一下 [編輯小組]，然後將隱私權變更為 [全組織 - 貴組織中的所有人都會自動新增]。 

> [!NOTE]
> 只有團隊擁有者可以存取編輯 **小組** 選項，只有全域系統管理員可以看到整個 **組織** 的選項。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>是否有將現有團隊轉換成全組織團隊的方法？

全域系統管理員可以在用戶端中編輯現有團隊，將其轉換為全組織Teams團隊。 移至小組名稱，按一下 [更多選項]  >  [編輯小組]。

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>我可以使用小組範本建立全組織團隊嗎？

小組範本無法用來建立全組織的小組。 這項功能目前正在使用中。 

## <a name="see-also"></a>另請參閱

觀看影片，瞭解在 Microsoft Teams 中[建立全公司Microsoft Teams。](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)
