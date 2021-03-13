---
title: 從使用者移除 RestrictedAnonymousAccess Teams 會議政策
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 瞭解如何從貴組織的使用者移除 RestrictedAnonymousAccess Teams 會議政策。
ms.openlocfilehash: 16158be1c0550cf1753d8984f8760e267ab4af5c
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756209"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>從使用者移除 RestrictedAnonymousAccess Teams 會議政策

Microsoft Teams[中的會議](meeting-policies-in-teams.md)政策可用來控制組織中使用者排程之會議的會議參與者可以使用的功能。 

Teams 包含名為 RestrictedAnonymousAccess 的內建策略，其中包含預先定義的設定，包括限制匿名使用者啟動會議。  (匿名使用者是尚未通過驗證的使用者。) 系統管理員無法編輯或變更會議政策中的預先定義設定。

本文將說明如何使用 PowerShell 從指派此政策的使用者移除 RestrictedAnonymousAccess 會議政策。 若要深入瞭解如何使用 PowerShell 管理 Teams，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。

## <a name="before-you-start"></a>在您開始之前

安裝並連接到商務 [用 Skype PowerShell 模組](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。 有關逐步指引，請參閱安裝 Microsoft [Teams PowerShell。](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>取得組織的 Teams 會議政策指派

執行下列操作以取得組織的 Teams 會議政策指派。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

在此範例中，會返回下列輸出，這表示有兩個使用者被指派了 RestrictedAnonymousAccess 會議政策。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>取消使用者對 RestrictedAnonymous 會議策略的未指定

若要從使用者移除 RestrictedAnonymous 會議政策，如果您有少數使用者 (例如，少於 100 個使用者，您可以使用 [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet) 。 如果您擁有大量使用者 (例如，超過 100 個使用者) ，使用  [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) 提交批次作業會更有效率。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用Grant-CsTeamsMeeting Cmdlet

執行下列操作以從使用者移除 RestrictedAnonymous 會議政策。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 New-CsBatchPolicyAssignmentOperation Cmdlet

使用 [批次策略指派](assign-policies.md#assign-a-policy-to-a-batch-of-users)時，您可以移除或更新策略的使用者數量上限為一次 5，000 個。 例如，如果您的使用者超過 5，000 個，您必須提交多個批次。 為獲得最佳結果，請勿一次提交多個批次。 提交更多批次之前，允許批次完成處理。

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)位於 Teams PowerShell 模組中。 在您遵循這些步驟之前，請安裝並連接到 [Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 有關逐步指引，請參閱安裝 Microsoft [Teams PowerShell。](teams-powershell-install.md)

執行下列命令，從一批使用者移除 RestrictedAnonymousAccess 會議政策。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>取得批次指派的狀態

每個批次指派會回一個作業識別碼，您可以使用它來追蹤工作分派的進度和狀態，並識別任何可能會發生的失敗。 例如，執行下列操作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

請確定 **ErrorCount** 為 0 (**0**) **且完成 OverallStatus。** 

## <a name="related-topics"></a>相關主題

- [管理 Teams 中的會議原則](meeting-policies-in-teams.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](assign-policies.md)
