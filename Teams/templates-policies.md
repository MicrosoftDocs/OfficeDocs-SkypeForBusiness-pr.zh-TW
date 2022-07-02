---
title: 在系統管理中心管理小組範本
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在系統管理中心管理小組範本
ms.openlocfilehash: 9f2044f059414f9afe1ff335f8204cd26861164b
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605902"
---
# <a name="manage-team-templates-in-the-admin-center"></a>在系統管理中心管理小組範本

在系統管理中心建立範本原則，以管理使用者看到的小組範本。 在每個範本原則中，您可以指定要顯示或隱藏哪些範本。
將不同的使用者指派給不同的範本原則，讓您的使用者只檢視指定的小組範本子集。

請觀看這段短片，瞭解如何管理範本原則。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-templates-policies-and-assign-available-templates"></a>建立範本原則並指派可用的範本

1. 登入 Teams 系統管理中心。

2. 移至 **Teams**  >  **範本原則**。

3. 選擇 **[新增]**。

    ![已選取範本原則，並醒目提示 [新增]。](media/template-policies-1.png)

1. 為原則命名並新增簡短描述。

2. 在 [ **可檢視的範本** ] 清單中，選取您要隱藏的範本，然後選取 [ **隱藏]**。

    ![已選取且醒目提示隱藏的範本。](media/template-policies-2.png)

    您可以在 [隱藏的範本] 清單中看到您選擇隱藏 **的範本** 。

1. 若要取消隱藏特定範本，請移至 **[隱藏的範本]** 清單。

2. 選取要取消隱藏的範本，然後選取 [ **顯示]**。

   ![未隱藏的選取範本。](media/template-policies-3.png)

   選取的範本會顯示在 **[可檢視的範本] 清單中** 。
3. 選擇 [ **儲存]**。

   新的範本原則會顯示在 **[範本原則** ] 清單中。

## <a name="assign-templates-policies-to-users"></a>指派範本原則給使用者

您可以直接指派範本原則給使用者，不論是個別或透過批次指派來縮放比例。 請記住，新原則可能需要長達 24 小時，才會對使用者生效。

> [!Note]
> 目前不支援根據群組成員資格將範本原則指派給使用者，例如指派給安全性群組中的所有使用者。 這項功能未來將會提供使用。

如需 Teams 中指派原則的概觀，請參閱 [在 Teams 中指派原則](policy-assignment-overview.md)。

### <a name="assign-a-templates-policy-to-individual-users"></a>指派範本原則給個別使用者

您可以使用 Teams 系統管理中心或 PowerShell，一次指派範本原則給個別使用者或少數使用者。 若要深入瞭解，請參閱 [指派原則給個別使用者](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)。

### <a name="assign-a-templates-policy-to-a-batch-of-users"></a>指派範本原則給一批使用者

您可以使用 PowerShell 一次指派範本原則給大量使用者。 若要這麼做，請使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) Cmdlet 搭配 TeamsTemplatePermissionPolicy 來 ```PolicyType``` 提交一批使用者，以及您要指派的範本原則。 例如：

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName <Any operation name> -PolicyType TeamsTemplatePermissionPolicy -PolicyName <policy name> -Identity <users identity | list of user identities>
```

系統會將工作處理為背景作業，並為每個批次產生作業識別碼。 接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) Cmdlet 來追蹤批次中作業的進度和狀態。

若要深入瞭解，請參閱 [使用 PowerShell 指派原則給一批使用者](assign-policies-users-and-groups.md#use-powershell-method)。

## <a name="size-limits-for-templates-policies"></a>範本原則的大小限制

您可以隱藏每個原則最多 100 個範本。 如果指定的原則已經隱藏了 100 個範本，[ **隱藏** ] 按鈕就會停用。

## <a name="frequently-asked-questions"></a>常見問題集

**問：如果建立新的範本，範本會包含在我的原則中嗎？**

答：預設會顯示任何新範本。 您可以選擇在 [範本原則] 區段中隱藏系統管理中心的範本。

**問：如果已刪除範本，會發生什麼情況？**

答：任何已刪除的範本將不再出現在任何範本原則中。

**問：我可以將多個使用者指派給 Teams 系統管理中心的範本原則嗎？**

答：是。

1. 在 Teams 系統管理中心，移至 **[使用者**  >  **管理使用者]**。
1. 在使用者清單中，選取您要指派給範本原則的使用者。
1. 選取 **[編輯設定]**，然後在 **[範本原則**] 底下，選擇您要指派的原則。
1. 選擇 [ **套用]**。

若要深入瞭解，請參閱 [指派原則給個別使用者](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)。

**問：如何?檢視指派給特定原則的所有使用者嗎？**

答：在 Teams 系統管理中心：

1. 移至 **[使用者**  >  **管理使用者]**。
2. 選 **取 [篩選**]，設定範本原則的篩選，然後選擇 [ **套用]**。

    ![選取的範本原則並檢視使用者。](media/template-policies-5.png)

**問：我可以透過 PowerShell 管理範本原則嗎？**

答：不支援在 PowerShell 中管理範本原則。 不過，您可以使用 PowerShell [將範本原則指派給](#assign-templates-policies-to-users) 使用者。

**問：範本原則是否適用于 EDU？**

答：不支援 EDU 的範本原則。

## <a name="related-articles"></a>相關文章

- [在系統管理中心開始使用團隊範本](./get-started-with-teams-templates-in-the-admin-console.md)

- [建立自訂團隊範本](./create-a-team-template.md)

- [從現有團隊建立範本](./create-template-from-existing-team.md)

- [從現有的團隊範本建立團隊範本](./create-template-from-existing-template.md)

- [在 Microsoft Teams 中指派原則給您的使用者 - Microsoft Teams \| Microsoft Docs](./policy-assignment-overview.md)

- [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)
