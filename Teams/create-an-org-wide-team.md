---
title: 在 Microsoft Teams 中建立全組織小組
author: cichur
ms.author: v-cichur
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在組織中建立及管理全組織Teams，為中小型企業中的每個人提供自動共同合作的方式。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28a03f045aa6db2567feb8990b9b9267706c7e8d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111159"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>在 Microsoft Teams 中建立全組織小組

全組織小組提供自動化方式，讓中小型組織中的每個人都成為單一小組的一部分來進行共同作業。

透過全組織小組，全域系統管理員可以輕鬆建立一個公開的小組，將組織中的每個使用者都拉入，當使用者加入和離開組織時，讓成員資格能隨著 Active Directory 保持在最新狀態。 只有全域系統管理員可以建立全組織團隊，而目前全組織團隊僅限於使用者不超過 10，000 個的組織。 另外還有一個限制是，每個租用戶只能有五個全組織小組。 如果符合這些需求，在建立小組時，全域系統管理員選取 [從頭建置小組] 時會看到 [全組織] 這個選項。 

![建立全組織小組的全組織選項螢幕擷取畫面](media/create-org-wide-team.png "建立全組織小組的全組織選項螢幕擷取畫面")

建立全組織團隊時，所有全域系統管理員Teams服務系統管理員會新增為團隊擁有者，所有使用中的使用者會新增為小組成員。 未授權的使用者也會新增至小組。 未授權使用者第一次登Teams時，會指派使用者Microsoft Teams探索授權。 若要深入瞭解探索授權，請查看管理探索Microsoft Teams[授權](teams-exploratory.md)。 

您的全組織小組將不會新增下列帳戶類型：

- 被封鎖而無法登入的帳戶
- 來賓使用者
- 例如，資源 (服務帳戶，例如與自動電話機和通話佇列相關聯的) 
- 會議室或設備帳戶
- 共用信箱支援的帳戶

當貴組織的目錄更新為包含新的作用中使用者，或如果使用者已經不在您的公司工作，且已停用其帳戶時，則會自動同步處理變更，將使用者新增到小組中或從小組中移除。 小組成員不能離開全組織小組。 如果您是小組擁有者，可以視需要手動新增或移除使用者。

> [!NOTE]
> - 如果您在建立團隊時沒看到全組織選項，而您是全域系統管理員，表示您可能已達到五個全組織團隊限制，或者貴組織可能超過目前 10，000 個成員的大小限制。 我們預計在未來增加這個限制。 Teams 教育版目前無法使用全組織小組。
> - 您可能將不屬於會議室清單、設備和資源帳戶的會議室新增或同步處理到全組織小組。 小組擁有者可輕鬆地從小組移除這些帳戶。
> - 系統新增或移除成員的所有動作會張貼在 [一般] 頻道。 頻道也會標示為在 Teams 用戶端中有新的活動。
> - 如果貴組織是新使用者，且使用者不超過 10，000 人Teams我們會自動為貴組織建立全組織小組。 小組名稱會反映租用戶名稱，並擁有 [一般] 頻道。 全域系統管理員可以像其他任何小組一樣編輯這個小組。 

## <a name="best-practices"></a>最佳做法

為了充分發揮您的全組織小組功能，我們建議小組擁有者執行下列動作。

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>只允許小組擁有者張貼到 [一般] 頻道

只允許小組擁有者張貼到 [一般] 頻道，以減少頻道「紛擾」。 請前往小組，找出一般頻道，然後選取 **1 100 1000 1000 1000 1000 2013 -2013**-2013-201331331133113311  >   在 [**頻道設定」** 選項卡上，按一下 **[許可權**」，然後選取 [只有 **擁有者可以張貼訊息。**

### <a name="turn-off-team-and-team-name-mentions"></a>關閉 @team 和 @[小組名稱] 提及項目

 降低 @mentions 使其不會讓整個組織超載。 移至小組，然後按一下 [更多選項]  >  [管理小組]。 在 [設定] 索引標籤上，按一下 [@mentions]<strong></strong> > 關閉 [向成員顯示 @team 或 @[小組名稱] 選項]。 

### <a name="automatically-show-important-channels"></a>自動顯示重要頻道

顯示重要的頻道以確保組織中的所有人都參與特定交談。 如需深入了解，請參閱[自動將頻道加入我的最愛方便整個團隊使用](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。 

### <a name="set-up-channel-moderation"></a>設定頻道裁決

請考量設定頻道裁決，並為特定小組成員提供仲裁者功能。 (設定仲裁時，會自動將仲裁者功能提供給小組擁有者。) 仲裁者能控制頻道中誰可以開始新文章、新增和移除仲裁者、控制小組成員是否可以回覆現有的頻道訊息，以及控制 Bot 和連接器是否可以提交頻道訊息。 如需詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

### <a name="remove-accounts-that-might-not-belong"></a>移除可能不屬於的帳戶

即使成員無法離開整個組織團隊，但做為團隊擁有者，您可以移除不屬於的帳戶來管理小組名冊。 **請確認您使用 Teams 移除全組織小組中的使用者**。 如果您使用其他方法 (例如 Microsoft 365 系統管理中心或從 Outlook 中的群組) 移除使用者，有可能會不小心將該使用者新增回全組織小組。

## <a name="faq"></a>常見問題集

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>有沒有使用 Teams 用戶端以外的建立全組織小組方法？

全域系統管理員只能使用 Teams 用戶端建立全組織小組。 如果貴組織將建立小組限制為使用 PowerShell，建議的因應措施是將您的全域系統管理員新增至可建立小組的使用者安全性群組。 詳細資訊，請參閱管理 [誰可以建立群組](/microsoft-365/admin/create-groups/manage-creation-of-groups)。

如果這不是選項，您可以使用 PowerShell 來建立公用小組，並將全域系統管理員新增為小組擁有者。 然後，讓全域系統管理員按一下小組名稱旁的 [更多選項]，按一下 [編輯小組]，然後將隱私權變更為 [全組織 - 貴組織中的所有人都會自動新增]。 請注意，只有小組擁有者可以存取 [編輯小組] 選項，而且只有全域系統管理員才能查看 [全組織] 選項。

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>有沒有方法可以將現有的小組轉換成全組織小組？

全域系統管理員可以在 Teams 用戶端中編輯現有的小組，將其轉換成全組織小組。 移至小組名稱，按一下 [更多選項]  >  [編輯小組]。

### <a name="can-i-create-an-org-wide-team-using-a-team-template"></a>我可以使用小組範本建立全組織團隊嗎？

小組範本無法用來建立全組織團隊。 此功能目前正在使用中。 

## <a name="see-also"></a>另請參閱

觀看影片，瞭解在 Microsoft Teams 中[建立全公司Microsoft Teams。](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)