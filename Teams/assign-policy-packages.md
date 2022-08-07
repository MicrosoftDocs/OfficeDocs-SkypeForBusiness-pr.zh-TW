---
title: 將原則套件指派給使用者和群組
author: mkbond007
ms.author: mabond
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解在 Microsoft Teams 中將原則套件指派給使用者和群組的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: cd6cbaab900ce1e9e5f4a2bd19731573c66ab7eb
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2022
ms.locfileid: "67272048"
---
# <a name="assign-policy-packages-to-users-and-groups"></a>將原則套件指派給使用者和群組

本文將檢閱在 Microsoft Teams 中將原則套件指派給使用者和群組的不同方式。 閱讀之前，請確定您已閱讀 [Teams 中的指派原則 - 開始使用](policy-assignment-overview.md)。

> [!NOTE]
> 每位使用者都需要 [進階通訊] 附加元件，才能接收自訂原則套件指派。 如需詳細資訊，請參閱 [Microsoft Teams 的進階通訊附加元件](/microsoftteams/teams-add-on-licensing/advanced-communications) (部分機器翻譯)。

## <a name="assign-a-policy-package-to-users"></a>指派原則套件給使用者

Teams 中的原則套件是預先定義的原則和原則設定集合，您可以將這些設定指派給組織中具有相同或相似角色的使用者。 每個原則套件都是針對使用者角色而設計，並包含預先定義的原則和原則設定，可支援該角色的一般活動。 一些原則套件範例包括教育 (教師) 套件和醫療保健 (醫療工作者) 套件。 若要深入瞭解，請參閱 [管理 Teams 中的原則套件](manage-policy-packages.md)。

### <a name="assign-a-policy-package-to-one-user"></a>指派原則套件給一個使用者

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [ **使用者**]，然後選取該使用者。

2. 在使用者的頁面上，選取 [ **原則**]，然後選取 [ **原則套** 件] 旁邊的 [ **編輯]**。

3. 在 [ **指派原則套** 件] 窗格中，選取您要指派的套件，然後選取 [ **套用]**。

    :::image type="content" source="media/assign-policy-package-one-user.png" alt-text="顯示 Teams 系統管理中心將原則套件指派給使用者的螢幕擷取畫面。" lightbox="media/assign-policy-package-one-user-expanded.png":::

### <a name="assign-a-policy-package-to-multiple-users"></a>指派原則套件給多位使用者

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 [ **原則套件**]，然後按一下套件名稱左側，選取您要指派的原則套件。

2. 選取 [管理使用者]。

3. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。

4. 當您完成新增使用者時，選取 [ **套用]**。

    :::image type="content" source="media/assign-policy-package-multiple-users.png" alt-text="顯示 Teams 系統管理中心原則套件指派給多位使用者的螢幕擷取畫面。" lightbox="media/assign-policy-package-multiple-users-expanded.png":::

## <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。

最多 50，000 個使用者的群組建議將原則套件指派給群組，但也適用于較大的群組。

當您指派原則套件時，系統會立即指派給該群組。 不過，原則指派給群組成員的傳播會做為背景作業，而且可能需要一些時間，視群組的大小而定。 當原則未指派給群組，或成員從群組新增或移除時，也是如此。

> [!IMPORTANT]
> 開始之前，請務必先瞭解 ([優先順序規則](assign-policies-users-and-groups.md#precedence-rules)) 和 ([群組作業排名](assign-policies-users-and-groups.md#group-assignment-ranking)) 。 請務必閱讀並瞭解本文稍早所 () [組的原則指派須知](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups) 事項。

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>在系統管理中心將原則套件指派給一組使用者

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [ **原則套件** ] 頁面。

2. 選取 [ **群組套件指派] 索引** 標籤。

3. 選取 **[新增**]，然後在 [ **指派原則套件至群組** ] 窗格中，執行下列動作：

    1. 搜尋並新增您要指派原則套件的群組。

    1. 選取原則套件。

    1. 設定每個原則類型的排名。

    1. 選取 [ **套用]**。

       :::image type="content" source="media/assign-policy-package-group.png" alt-text="將原則套件指派給群組窗格的螢幕擷取畫面。" lightbox="media/assign-policy-package-group-expanded.png":::

4. 若要管理特定原則類型的排名，請流覽至特定的原則頁面。

5. 若要將原則套件重新指派給群組，請先移除群組原則指派。 然後，依照上述步驟將原則套件指派給群組。

### <a name="work-with-powershell"></a>使用 PowerShell

#### <a name="get-the-teams-powershell-module"></a>取得 Teams PowerShell 模組

如需逐步指引，請參閱 [安裝 Teams PowerShell](teams-powershell-install.md)。

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>指派原則套件給一組使用者

使用 [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) Cmdlet 將原則套件指派給群組。 您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。 當您指派原則套件時，為原則套件中的每種原則類型指定 ([組分派排名](assign-policies-users-and-groups.md#group-assignment-ranking)) 。

在此範例中，我們會將Education_Teacher原則套件指派給一個團隊指派排名為 1 的群組：TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy，以及 TeamsMeetingPolicy 的排名為 2。

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>指派原則套件給一批使用者

透過批次處理原則套件指派，您可以一次指派原則套件給大量使用者，而不需要使用腳本。 您可以使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。 接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) Cmdlet 來追蹤批次中作業的進度和狀態。

依使用者的物件識別碼或會話初始通訊協定 (SIP) 位址指定使用者。 使用者的 SIP 位址的值通常與 UPN) 或電子郵件地址 (使用者主體名稱相同，但並非必要。 如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者的原則指派將會失敗。 如果批次包含重複的使用者，則重複專案會從批次中移除，然後再處理，而且只有批次中剩餘的唯一使用者才會提供狀態。

批次包含最多 5，000 個使用者。 為獲得最佳結果，請不要一次提交多個批次。 允許批次完成處理，然後再提交更多批次。

### <a name="use-the-teams-powershell-module"></a>使用 Teams PowerShell 模組

如果您尚未) ，請執行下列步驟來安裝 [Microsoft Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams) (。 請確定您已安裝版本 1.0.5 或更新版本。

```powershell
Install-Module -Name MicrosoftTeams
```

執行下列動作以連線至 Teams 並開始會話。

```powershell
Connect-MicrosoftTeams
```

出現提示時，請使用您的系統管理員認證登入。

### <a name="assign-policy-packages-to-a-batch-of-users"></a>指派原則套件給一批使用者

在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) Cmdlet 將Education_PrimaryStudent原則套件指派給一批使用者。

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>查看批次處理作業的狀態

執行下列動作以取得批次處理作業的狀態，其中 OperationId 是指定批次 Cmdlet 所傳 `New-CsBatchPolicyAssignmentOperation` 回的作業識別碼。

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

如果輸出顯示發生錯誤，請執行下列動作以取得有關錯誤的詳細資訊，錯誤位於屬性中 `UserState` 。

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

若要深入瞭解，請參閱 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation)。

## <a name="related-topics"></a>相關主題

- [使用原則管理 Teams](manage-teams-with-policies.md)
- [在 Microsoft Teams 中管理原則套件](manage-policy-packages.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中指派原則 - 快速入門](policy-assignment-overview.md)
