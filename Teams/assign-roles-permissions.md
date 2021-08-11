---
title: 在 Microsoft Teams 中指派 Teams 擁有者和成員
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中指派小組擁有者和成員角色及權限，包括建立小組的權限。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b574c04acdf466f2ad8a46401dd347ff2a82b876eaa61815d0d3ea07d7d9cb8b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331095"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams"></a>在 Microsoft Teams 中指派 Teams 擁有者和成員

Microsoft Teams 內有兩個使用者角色：**擁有者** 和 **成員**。 根據預設，建立新小組的使用者會取得擁有者狀態。 此外，則小組擁有者和成員都可以有頻道的仲裁者功能 (如果已設定仲裁功能)。 如果小組是從現有的 Microsoft 365 群組建立的，則會繼承權限。

下表顯示擁有者和成員之間的權限差異。


|    工作                               | 小組擁有者 | 小組成員 |
|-----------------------------------|------------|-------------|
|          **建立團隊**          |    是<sup>1</sup>     |     否      |
|          **離開團隊**           |    是     |     是     |
|  **編輯團隊名稱/描述**   |    是     |     否      |
|          **刪除團隊**          |    是     |     否      |
|          **添加標準通道**          |    是     |    是<sup>2</sup>|
| **編輯標準頻道名稱/描述** |    是     |    是<sup>2</sup>|
|        **刪除標準通道**         |    是     |    是<sup>2</sup>|
|          ***新增私人頻道**          |    是     |    是<sup>2</sup>|
| ***編輯私人頻道名稱/描述** |    否     |    不適用|
|        ***刪除私人頻道**         |    是     |    否|
|          **新增成員**          |  是<sup>3</sup>   |     否<sup>4</sup>    |
|          **要求新增成員**          |  不適用   |     是<sup>5</sup>     |
|           **新增應用程式**            |    是     |    是<sup>2</sup>|

<sup>1</sup>團隊擁有者可以建立團隊，除非受到限制。 下方[建立團隊的權限](#permissions-to-create-teams)。<br>
<sup>2</sup> 擁有者可以在團隊層級關閉這些項，在這種情況下，成員將無法存取它們。<br>
<sup>3</sup> 將成員添加到團隊後，擁有者還可以將成員提升為擁有者狀態。 擁有者也可以將自己的狀態降階為成員。<br>
<sup>4</sup> 小組成員可以向公開小組新增其他成員。<br>
<sup>5</sup> 雖然小組成員不能直接向私人小組新增成員，但他們可以要求將人員新增到其已經是成員的小組中。 當成員要求將某人新增到小組時，小組擁有者會收到表示他們有可以接受或拒絕的擱置的要求的警示。

*若要了解有關私人頻道權限的詳細資訊，請參閱[小組中的私人頻道](private-channels.md)。

> [!NOTE]
> 擁有者可以在 **[檢視成員]** 選項中使其他成員成為擁有者。 一個小組最多可以有 100 個擁有者。 我們建議您至少有幾個擁有者來協助管理小組；這還可以防止在唯一擁有者離開組織時出現孤立群組。 有關孤立群組的詳細資訊，請參閲[為孤立群組指派新擁有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。

## <a name="moderator-capabilities"></a>仲裁者功能

除了其他功能外，小組擁有者和成員還可以擁有頻道的 [仲裁者] 功能 (前提是為小組開啟了 [仲裁])。 仲裁者可在頻道中開始新的文章，並控制團隊成員是否可以回覆現有的頻道訊息。 他們也可以控制 Bot 和連接器是否可以提交頻道訊息。

仲裁者功能是在頻道層級指派。 團隊擁有者預設會有仲裁者功能。 團隊成員的仲裁者功能預設會關閉，但團隊擁有者可為團隊成員提供頻道的仲裁者功能。 頻道內的仲裁者可以新增和移除該頻道內的其他仲裁者。

如需有關仲裁者功能的詳細資訊，請參閱[在 Microsoft Teams 中設定和管理頻道仲裁](manage-channel-moderation-in-teams.md)。

## <a name="assign-a-user-role"></a>指派使用者角色

要指派使用者角色，請在 Teams 中選取小組名稱，然後按一下 **[更多選項]** > **[管理小組]**。 在 **[成員]** 索引標籤上，可以新增成員並選擇擁有者和仲裁者 (如果您有足够的權限)。 如需詳細資訊，請參閱[在 Teams 中變更小組設定](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)。

## <a name="permissions-to-create-teams"></a>建立小組的權限

根據預設，在 Exchange Online 中具有郵箱的所有使用者都有權建立 Microsoft 365 群組，因此有權在 Microsoft Teams 中建立小組。 透過將群組建立和管理權限委派給一組使用者，您可以更嚴格地控制和限制新小組的建立，從而建立新的 Microsoft 365 群組。 如需詳細指示，請參閱[管理能建立 Microsoft 365 群組的使用者](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。
