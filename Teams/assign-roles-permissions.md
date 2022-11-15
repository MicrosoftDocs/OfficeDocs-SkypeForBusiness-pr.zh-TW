---
title: 在 Microsoft Teams 系統管理中心中指派團隊擁有者和成員
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中指派小組擁有者和成員角色及權限，包括建立小組的權限。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0f259a7a24552988d4eca503deeb9151dde144d
ms.sourcegitcommit: 0760416ee0bead3ada93f4d37f8aebc74222bd3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2022
ms.locfileid: "69019409"
---
# <a name="assign-team-owners-and-members-in-microsoft-teams-admin-center"></a>在 Microsoft Teams 系統管理中心中指派團隊擁有者和成員

**擁有者** 和 **成員** 是 Microsoft Teams 中的兩個使用者角色。 根據預設，建立新團隊的使用者會獲得擁有者狀態。 擁有者和成員在與團隊及其頻道互動時，具有不同類型的許可權和功能。 請參閱 [Microsoft Teams 中的團隊和頻道概觀](teams-channels-overview.md) ，以深入瞭解 Teams 中的角色。

> [!NOTE]
> 如果團隊是從現有的 Microsoft 365 群組建立，則會繼承許可權。

## <a name="assign-a-user-role-in-teams-admin-center"></a>在 Teams 系統管理中心中指派使用者角色

1. 在 Teams 系統管理中心中，展開 **[團隊]** ，然後選取 **[管理團隊]**。
2. 選取顯示名稱欄底下的團隊名稱。
3. 在 [成員] 索引標籤中，您可以新增或移除成員，並將擁有者和仲裁者角色指派給成員。

## <a name="restrict-permission-to-create-teams"></a>限制建立團隊的許可權

在 Exchange Online 中擁有信箱的所有使用者都有權在 Microsoft Teams 中建立 Microsoft 365 群組和團隊。 藉由將群組建立及管理許可權委派給一組使用者，以限制使用者建立新團隊和 Microsoft 365 群組。 如果這項限制為使用中，團隊擁有者或成員都無法建立新的團隊。 如需詳細資訊，請參閱[管理能建立 Microsoft 365 群組的使用者](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618) (部分機器翻譯)。

## <a name="user-permissions-based-on-assigned-roles"></a>根據指派角色的使用者許可權

下表顯示擁有者和成員之間的權限差異。

### <a name="teams"></a>Teams

|Teams 工作| 小組擁有者 | 小組成員 |
|---------|---------|---------|
|建立/刪除團隊  |    是     |     否    |
|編輯團隊名稱/描述   |     是    |     否     |
|將成員新增至私人團隊    |     是    |  否 |
|將成員新增至公開團隊    |     是    |     是   |
|要求新增成員   |     不適用    |    是   |
|升階/降級使用者狀態 | 是 | 否 |
|離開團隊  |    是     |     是    |
|新增/移除應用程式   |     是    |     是的，如果已由團隊擁有者啟用     |

### <a name="channels"></a>頻道

|***標準通道工作** _ | _ *Team Owner** | **小組成員**|
|----|----|----|
|建立/刪除頻道  |     是    |    是的，如果已由團隊擁有者啟用      |
|編輯頻道名稱/描述    |    是     |     是的，如果已由團隊擁有者啟用    |
|***私人頻道工作***|
|建立頻道    |    是     |    是的，如果已由團隊擁有者啟用      |
|刪除頻道    |    是     |    否     |
|編輯頻道名稱/描述 |     否    |    不適用     |
|***共用頻道工作***
|建立頻道    |    是     |     否    |
|刪除頻道 | 是 | 否 |
|編輯頻道名稱/描述    |    否     |     否    |
