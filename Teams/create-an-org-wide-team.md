---
title: 在 Microsoft Teams 中使用整個組織的團隊來協助每個人共同作業
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何在 Teams 中建立和管理整個組織的團隊，為中小型組織中的每個人提供共同作業的方式。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- EngageScoreOct2022
- ContentEnagagementFY23
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee17d482c311a4bdd92ebad55e29058104a89b98
ms.sourcegitcommit: e5f5a1a164576b317e89340e233c9b67f082d19c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/09/2022
ms.locfileid: "68890052"
---
# <a name="use-organization-wide-teams-in-microsoft-teams-to-help-everyone-collaborate"></a>在 Microsoft Teams 中使用整個組織的團隊來協助每個人共同作業

全域系統管理員可以建立整個組織的團隊，讓中小型組織中的每個人成為單一共同作業團隊的一員。 全組織的團隊會自動包含組織中的每個使用者，並在使用者加入並離開組織時，讓成員資格保持在最新狀態。

如果您的組織是 Teams 的新使用者，且使用者不超過 5，000 人，則會自動建立整個組織的團隊。 整個組織的團隊僅限於使用者不超過 10，000 名的組織。 您最多可以有五個整個組織的團隊。 

## <a name="create-an-organization-wide-team"></a>建立整個組織的團隊

建立全組織團隊的方法有兩種：

- 將現有團隊轉換為整個組織的團隊。 移至團隊名稱，然後按一下 [**更多選項**  >  **編輯團隊]**。

- [從頭開始建立新團隊](https://support.microsoft.com/office/174adf5f-846b-4780-b765-de1a0a737e2b) ，然後選擇 **全組織** 選項。

    ![建立全組織團隊之全組織選項的螢幕擷取畫面。](media/create-org-wide-team.png "建立全組織團隊之全組織選項的螢幕擷取畫面")

## <a name="types-of-users-in-an-organization-wide-team"></a>整個組織團隊中的使用者類型

建立整個組織的團隊時，所有全域系統管理員和 Teams 系統管理員都會新增為團隊擁有者，且所有作用中的使用者都會新增為團隊成員。 團隊成員無法離開整個組織的團隊，但團隊擁有者可以視需要手動新增或移除使用者。 當 Teams 自動新增或移除某人時，通知會傳送至 [一般] 頻道。

未授權的使用者也會新增至小組。 當未授權的使用者第一次登入 Teams 時，系統會指派 Microsoft Teams 探索授權。 若要深入瞭解探索授權，請參閱 [管理 Microsoft Teams Exploratory 授權](teams-exploratory.md)。

下列類型的帳戶不會新增至整個組織的小組：

- 封鎖不登入的帳戶
- 來賓
- 資源或服務帳戶 (例如，與自動語音應答相關聯的帳戶和通話佇列) 
- 會議室或設備帳戶
- 共用信箱支援的帳戶

> [!NOTE]
> 不屬於會議室清單、設備和資源帳戶的會議室可能會新增或同步處理至整個組織的小組。 小組擁有者可輕鬆地從小組移除這些帳戶。

## <a name="options-to-get-the-most-out-of-an-organization-wide-team"></a>讓整個組織團隊充分發揮功能的選項

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

## <a name="related-topics"></a>相關主題

觀看有關 [如何在 Microsoft Teams 中建立全組織團隊的](https://www.youtube.com/watch?v=x3qGlwwCz_w)影片。
