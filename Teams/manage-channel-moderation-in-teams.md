---
title: 設定及管理頻道模式
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jotaing
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在頻道中設定仲裁Microsoft Teams，包括如何將小組成員新增為頻道仲裁者。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4441eea880b5dcf1d71ca11f0ad32cf148f90cf4
ms.sourcegitcommit: eb5fadedacbf4651ed5b05f1b0d6abf57e9eda2d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "62960005"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>在頻道中設定及管理頻道Microsoft Teams

在 Microsoft Teams中，團隊擁有者可以開啟標準頻道的審核，以控制誰可以開始新文章，以及回復該頻道中的文章。

團隊擁有者也可以將小組成員新增為仲裁者。 團隊擁有者可能沒有頻道層級的主題專業知識，因此無法提供最佳支援通道管理。 允許特定小組成員管理頻道，讓團隊擁有者和頻道仲裁者分擔管理頻道內容與內容的責任。 例如，團隊擁有者可以將企業擁有者或內容擁有者新增為仲裁者，讓他們控制該頻道的資訊共用。

> [!NOTE]
> 頻道模式適用于標準頻道。 不適用於一般頻道或私人頻道。

## <a name="what-can-a-channel-moderator-do"></a>頻道仲裁者可以做什麼？

頻道仲裁者可以：

- 在頻道中開始新文章。 當頻道開啟仲裁時，只有仲裁者可以在該頻道中啟動新文章。
- 將小組成員新增並移除為仲裁者至頻道。 請記住，根據預設，團隊擁有者是頻道仲裁者，無法移除。
- 控制小組成員是否可以回復現有的頻道訊息，以及 Bot 和連接器是否可以提交頻道訊息。

## <a name="scenarios"></a>案例

以下範例說明貴組織如何在 Teams 中使用通道Teams。

### <a name="use-a-channel-as-an-announcement-channel"></a>使用頻道做為公告頻道

行銷小組使用特定頻道來共用重要的專案公告和交付專案。 有時候小組成員會張貼內容至其他頻道中較適當的頻道。 團隊擁有者想要將頻道中的資訊共用限制為只有公告，讓小組成員可以使用該頻道，隨時瞭解重要內容。

在此情境中，團隊擁有者會將行銷潛在客戶新增為仲裁者，這樣他們就可以在頻道中張貼公告，並關閉小組成員回復該頻道中的訊息的能力。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>使用頻道在 Teams 教育版

在 Teams 教育版中，科學教師想要使用頻道讓學生參與特定課堂主題的專注討論。

在此情境中，教師允許其教學助理管理頻道。 然後，教學助理可以建立新文章，以啟動和推動與學生的討論。

## <a name="manage-channel-moderation"></a>管理頻道模式

在 Teams，請前往頻道，按一下 [**更多選項...**  > **管理頻道**。 您可以在這裡開啟並關閉仲裁、將小組成員新增為仲裁者，以及設定喜好設定。

通道模式是每個頻道的設定。 頻道模式沒有租使用者層級設定。 如果您想要我們新增租使用者層級通道管理設定，請于意見Teams[入口網站索取](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472)。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![管理 -channel-moderation-in-teams 的喜好設定。](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>開啟或關閉頻道的頻道模式

根據預設，模式設定為關閉，這表示一般頻道設定會適用于團隊擁有者和小組成員。 例如，您可以將新文章限制為只有小組成員，或允許每個人 ，包括來賓，開始新文章。

若要開啟頻道的頻道模式，請在 [頻道模式模式 **> 下，** 按一下 **[開啟**。 頻道仲裁為啟用時，只有仲裁者可以開始新的文章。 

### <a name="add-or-remove-channel-moderators"></a>新增或移除頻道仲裁者

在 **神秘是仲裁者嗎？**，按一下 [管理，然後新增或移除小組成員為仲裁者。 團隊擁有者和仲裁者可以新增和移除其他仲裁者。  

### <a name="set-team-member-permissions"></a>設定團隊成員許可權

在 **團隊成員許可權下**，選取您想要允許的活動旁的核取方塊。

## <a name="related-topics"></a>相關主題

- [Teams 的小組和頻道概觀](teams-channels-overview.md)
