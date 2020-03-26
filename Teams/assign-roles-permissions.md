---
title: 在 Microsoft 團隊中指派小組擁有者和成員
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中指派小組擁有者和成員角色及許可權，包括建立小組的許可權。
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f411de7f0c373e82b450cd41b828fd591777311b
ms.sourcegitcommit: 4d376449a75928282373598647f2b82127909c4f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/26/2020
ms.locfileid: "42978455"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a>在 Microsoft 團隊中指派小組擁有者和成員
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

在 Microsoft 團隊中，有兩個使用者角色： [**擁有**者] 和 [**成員**]。 根據預設，會將建立新團隊的使用者授與擁有者狀態。 此外，擁有者和成員也可以擁有頻道的仲裁者功能（前提是已設定裁決）。 如果您是從現有的 Office 365 群組建立團隊，則會繼承許可權。

下表顯示擁有者和成員之間許可權的差異。


|                                   | 小組擁有者 | 小組成員 |
|-----------------------------------|------------|-------------|
|          **建立小組**          |    是<sup>1</sup>     |     否      |
|          **離開團隊**           |    是     |     是     |
|  **編輯團隊名稱/描述**   |    是     |     否      |
|          **刪除團隊**          |    是     |     否      |
|          **新增標準頻道**          |    是     |    是<sup>2</sup>|
| **編輯標準頻道名稱/描述** |    是     |    是<sup>2</sup>|
|        **刪除標準頻道**         |    是     |    是<sup>2</sup>|
|          ***新增私人頻道**          |    是     |    是<sup>2</sup>|
| ***編輯私人頻道名稱/描述** |    否     |    不適用|
|        ***刪除私人頻道**         |    是     |    否|
|          **新增成員**          |  是<sup>3</sup>   |     無<sup>4</sup>    |
|          **要求新增成員**          |  不適用   |     是<sup>5</sup>     |
|           **新增應用程式**            |    是     |    是<sup>2</sup>|

<sup>1</sup>小組擁有者可以建立團隊，除非他們受到限制。 [建立小組的許可權](#permissions-to-create-teams)。<br>
<sup>2</sup>擁有者可以在小組層級關閉這些專案，在這種情況下，成員將無法存取它們。<br>
<sup>3</sup>將成員新增至團隊之後，擁有者也可以將成員升級為擁有者狀態。 您也可以讓擁有者將自己的狀態降級為成員。<br>
<sup>4 個</sup>小組成員可以將其他成員新增至公用小組。<br>
<sup>5</sup>當小組成員無法直接將成員新增到私人小組時，他們可以要求將某人新增至他們已成為其成員的小組。 當成員要求將某人新增至小組時，小組擁有者會收到一則通知，提醒他們有可接受或拒絕的待定要求。

* 若要深入瞭解私人頻道的許可權，請參閱[小組中的私人頻道](private-channels.md)。

> [!NOTE]
> 擁有者可以在 [**查看小組**] 選項中讓其他成員擁有者。 團隊最多可以有100個擁有者。 我們建議您至少有幾個擁有者協助管理團隊;這也會防止孤立的群組（如果擁有者離開您的組織）。 如需孤立群組的詳細資訊，請參閱[將新擁有者指派給孤立的群組](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。

## <a name="moderator-capabilities"></a>版主功能

除了其他功能之外，小組擁有者和成員還可以擁有頻道的仲裁者功能（前提是針對團隊開啟裁決）。 版主可以在頻道中開始新的文章，並控制小組成員是否可以回復現有的頻道訊息。 他們也可以控制機器人與連接器是否能提交頻道訊息。

版主功能是在頻道層級指派。 小組擁有者預設具有仲裁者的功能。 小組成員預設會關閉仲裁者的功能，但小組擁有者可以為小組成員提供頻道的仲裁者功能。 頻道內的版主者可以在該頻道中新增及移除其他版主。

如需有關版主功能的詳細資訊，請參閱[在 Microsoft 團隊中設定及管理頻道裁決](manage-channel-moderation-in-teams.md)。

## <a name="assign-a-user-role"></a>指派使用者角色

若要指派使用者角色，請在 [團隊] 中選取團隊名稱，然後按一下 [**更多選項** > **管理團隊**]。 您可以在 [**成員**] 索引標籤上新增成員，然後選擇 [擁有人] 和 [版主] （如果您有足夠的許可權）。 如需詳細資訊，請參閱[變更團隊中的團隊設定](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)。

## <a name="permissions-to-create-teams"></a>建立小組的許可權

根據預設，所有在 Exchange Online 中擁有信箱的使用者，都有權建立 Office 365 群組，進而成為 Microsoft 團隊內的小組。 您可以透過將群組建立與管理許可權委派給一組使用者，讓您更嚴密地控制和限制新團隊的建立，進而建立新的 Office 365 群組。 如需相關指示，請參閱[管理可建立 Office 365 群組的人員](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。


||||
|---------|---------|---------|
| ![代表決策點的圖示](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |決策點         |所有 Microsoft 團隊使用者都可以建立小組（建議使用）嗎？         |
| ![代表後續步驟的圖示](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |後續步驟         |修改誰能建立 Office 365 群組的預設許可權（如果您需要限制誰可以建立團隊）         |
