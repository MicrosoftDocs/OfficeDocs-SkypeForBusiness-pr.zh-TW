---
title: 管理管理中心的團隊範本
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在系統管理中心管理團隊範本
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125878"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a>在系統管理中心建立及管理團隊範本

[!INCLUDE [preview-feature](includes/preview-feature.md)]

在系統管理中心建立範本原則，以管理您的最終使用者所顯示的團隊範本。 在每個範本原則中，您可以指定要顯示或隱藏哪些範本。
將不同的使用者指派給不同的範本原則，讓您的使用者只能查看指定的小組範本子集。

## <a name="create-template-policies-and-assign-available-templates"></a>建立範本原則並指派可用的範本

1. 登入團隊系統管理中心。

2. 展開 **團隊**  >  **範本原則**。

3. 選取 [新增 **]**。

    ![已選取範本原則，且醒目提示 [新增]](media/template-policies-1.png)

1. 在 [ **範本原則設定** ] 區段中，填寫下欄欄位：

    - 範本原則名稱

    - 範本原則簡短描述

2. 在 [可 **查看範本** ] 表格中，選取您要隱藏的範本，然後選取 [ **隱藏**]。

    ![選取的範本，並醒目提示 [隱藏]](media/template-policies-2.png)

    您可以在 [ **隱藏範本** ] 表格中查看您已選取隱藏的範本。

1. 若要取消隱藏某些範本，請滾動至 [ **隱藏範本** ] 表格。

1. 選取要取消隱藏的範本，然後選取 [ **顯示**]。

   ![選取的範本，並醒目提示 [隱藏]](media/template-policies-3.png)

   選取的範本會出現在您的可 **查看範本** 表格中。
3. 選取 [ **儲存**]。

   您的新範本原則會顯示在 [ **範本原則** ] 清單中。

## <a name="assign-users-to-the-template-policies"></a>將使用者指派給範本原則

指派給原則的使用者將只能在該原則中查看可查看的範本。

1. 從 [ **範本原則**]，選取原則，然後選取 [ **管理使用者**]。

2. 輸入要指派給此原則的使用者。

   ![選取的範本，並醒目提示 [隱藏]](media/template-policies-4.png)

3. 選取 **[** 套用]。

> [!Note]
> 最多可能需要24小時才能讓新原則生效給使用者。

## <a name="size-limits-for-template-policies"></a>範本原則的大小限制

您可以針對每個原則隱藏100範本的最大值。 如果指定原則已隱藏100範本，則會停用 [ **隱藏** ] 按鈕。

## <a name="frequently-asked-questions"></a>常見問題集

**問：我可以將使用者成批指派給小組範本原則嗎？**
  
答：是的，我們支援 PowerShell 中範本原則的批次作業。 此動作的原則類型是 [TeamsTemplatePermissionPolicy]。 [瞭解更多資訊](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

**問：您可以將群組指派給小組範本原則嗎？**

答：目前沒有。 此功能將于未來推出。

**問：如果建立新的範本，範本會包含在 [我的原則] 中嗎？**

答：預設會顯示任何新的範本。 您可以在系統管理中心的 [範本原則] 區段中，選擇隱藏範本。

**問：如果範本遭到刪除，會發生什麼情況？**

答：任何已刪除的範本，都不會再出現在任何範本原則中。

**問：我可以在團隊系統管理中心將多個使用者指派給範本原則嗎？**

答：是的。

1. 在系統管理中心中，移至 [ **使用者**]。
1. 在 [使用者清單] 表格中，選取您要指派給特定範本原則的使用者。
1. 選取 [編輯設定]，然後變更 [範本原則] 欄位。
1. 選取 [套用]。
   深入瞭解 [Microsoft 團隊中的使用者指派原則-Microsoft 團隊 \| microsoft 文檔](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)。

**問：如何查看指派給特定原則的所有使用者？**

答：在系統管理中心：

1. 移至 [ **使用者** ] 區段。
2. 選取 [使用者清單] 資料表中的篩選，然後篩選團隊範本原則。
3. 選取 **[** 套用]。

![選取的範本，並醒目提示 [隱藏]](media/template-policies-5.png)

**問：我可以透過 PowerShell 管理範本原則嗎？**

答：不行，不支援這種情況。

**問：是否有適用于 EDU 的範本原則？**

答：不行，不支援這種情況。

## <a name="related-topics"></a>相關主題

- [在系統管理中心開始使用團隊範本](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [建立自訂團隊範本](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [從現有團隊建立範本](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [從現有的小組範本建立小組範本](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [在 Microsoft 團隊中將原則指派給使用者-microsoft 團隊 \| Microsoft 文檔](https://docs.microsoft.com/microsoftteams/assign-policies)

- [TeamsTemplatePermissionPolicy](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)