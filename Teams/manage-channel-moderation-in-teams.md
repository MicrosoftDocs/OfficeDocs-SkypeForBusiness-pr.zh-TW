---
title: 設定及管理頻道仲裁
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: 瞭解如何在 Microsoft Teams 中設定仲裁頻道，包括如何將團隊成員新增為頻道仲裁者。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52fb88d6371c033713c5b14d96ecf2a9211420b0
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562362"
---
# <a name="set-up-and-manage-channel-moderation-in-microsoft-teams"></a>在 Microsoft Teams 中設定及管理頻道仲裁

在 Microsoft Teams 中，團隊擁有者可以開啟標準頻道的仲裁，以控制誰能在該頻道中開始新文章及回復文章。

團隊擁有者也可以新增團隊成員做為仲裁者。 團隊擁有者可能沒有頻道層級的主題專長，以獲得最佳的通道仲裁支援。 透過允許特定團隊成員管理頻道，在頻道內管理內容和內容的責任會由團隊擁有者和頻道仲裁者共用。 例如，團隊擁有者可以將企業擁有者或內容擁有者新增為仲裁者，讓他們能控制該頻道中的資訊共用。

> [!NOTE]
> 標準通道可使用通道仲裁。 不適用於一般頻道或私人或共用頻道。

## <a name="what-can-a-channel-moderator-do"></a>頻道仲裁者可以做什麼？

頻道仲裁者可以：

- 在頻道中開始新文章。 當頻道開啟仲裁時，只有仲裁者可以在該頻道中開始新的文章。
- 新增並移除團隊成員做為頻道的仲裁者。 請記住，根據預設，團隊擁有者是頻道仲裁者，無法移除。
- 控制小組成員是否可以回復現有的頻道訊息，以及 Bot 和連接器是否可以提交頻道訊息。

## <a name="scenarios"></a>案例

以下是您的組織如何在 Teams 中使用頻道仲裁的一些範例。

### <a name="use-a-channel-as-an-announcement-channel"></a>使用頻道做為宣告頻道

行銷小組會使用特定頻道來分享重要的專案公告和交付專案。 有時候團隊成員會將內容張貼到其他頻道中較為適當的頻道。 團隊擁有者想要將頻道中的資訊共用限制為僅限公告，讓團隊成員可以使用該頻道掌握重要資訊。

在此案例中，團隊擁有者會將「行銷」潛在客戶新增為仲裁者，讓他們可以在頻道中張貼公告，並關閉團隊成員回復該頻道訊息的功能。

### <a name="use-a-channel-for-class-discussions-in-teams-for-education"></a>在 Teams 教育版 中使用頻道進行班級討論

在Teams 教育版中，科學教師想要使用頻道讓學生參與特定課堂主題的焦點討論。

在此案例中，教師允許其助教管理頻道。 助教接著可以建立新文章，以開始和學生進行討論。

## <a name="manage-channel-moderation"></a>管理頻道仲裁

在 Teams 中，移至頻道，按一下 [**更多選項...**  > **管理頻道**。 您可以在這裡開啟和關閉仲裁、將小組成員新增為仲裁者，以及設定喜好設定。

頻道仲裁是每個頻道的設定。 頻道仲裁沒有租使用者層級設定。 如果您希望我們新增租使用者層級通道仲裁設定，請在 Teams 意見反應 [入口網站](https://feedbackportal.microsoft.com/feedback/forum/ad198462-1c1c-ec11-b6e7-0022481f8472)提出要求。

[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

![管理-channel-moderation-in-teams 的喜好設定。](media/manage-channel-moderation-in-teams-preferences.png)

### <a name="turn-on-or-turn-off-moderation-for-a-channel"></a>開啟或關閉頻道的仲裁

根據預設，仲裁為關閉，這表示一般的頻道設定會套用至團隊擁有者和團隊成員。 例如，您可以將新文章限制為僅限小組成員，或允許包括來賓在內的所有人開始新文章。

若要開啟頻道的仲裁，請在 [ **頻道仲裁**] 底下，按一下 [ **開啟]**。 當頻道仲裁開啟時，只有仲裁者可以開始新的文章。 

### <a name="add-or-remove-channel-moderators"></a>新增或移除頻道仲裁者

在 [ **誰是仲裁者？**] 底下，按一下 [ **管理**]，然後新增或移除小組成員做為仲裁者。 團隊擁有者和仲裁者可以新增和移除其他仲裁者。  

### <a name="set-team-member-permissions"></a>設定小組成員許可權

在 **[小組成員許可權] 底** 下，選取您要允許的活動旁邊的核取方塊。

## <a name="related-topics"></a>相關主題

- [Teams 的小組和頻道概觀](teams-channels-overview.md)
