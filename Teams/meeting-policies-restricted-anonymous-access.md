---
title: 從使用者移除 RestrictedAnonymousAccess Teams 會議原則
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
description: 瞭解如何從貴組織Teams移除 RestrictedAnonymousAccesss 或會議政策。
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121341"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>從使用者移除 RestrictedAnonymousAccess Teams 會議原則

[會議Microsoft Teams](meeting-policies-in-teams.md)用來控制貴組織中使用者排程會議的會議參與者可用的功能。 

Teams包含名為 RestrictedAnonymousAcces 的內建策略，其中包含預先定義的設定，包括限制匿名使用者啟動會議。  (匿名使用者是尚未通過驗證的使用者。) 系統管理員無法編輯或變更會議策略中的預先定義設定。

本文將說明如何使用 PowerShell 從指派此策略的使用者移除 RestrictedAnonymousAccess 會議政策。 若要深入瞭解如何使用 PowerShell 管理Teams，請參閱 PowerShell Teams[概觀](teams-powershell-overview.md)。

## <a name="before-you-start"></a>在您開始之前

安裝並連接到[powerShell 商務用 Skype模組](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。 有關逐步指南，請參閱在[PowerShell Microsoft Teams安裝](teams-powershell-install.md)。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>取得Teams的會議策略指派

請執行下列操作，以取得Teams組織的會議策略指派。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

在此範例中，會返回下列輸出，這表示兩個使用者被指派了 RestrictedAnonymousAccess 會議策略。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>從使用者取消分配 RestrictedAnonymous 會議策略

若要從使用者移除 RestrictedAnonymous 會議政策，如果您有少數使用者 (例如少於 100 個使用者) ，您可以使用 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet。 如果您有大量使用者 (例如超過 100 個使用者) ，使用  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 提交批次處理作業會更有效率。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用 Grant-CsTeamsMeeting Cmdlet

執行下列操作，從使用者移除 RestrictedAnonymous 會議政策。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 New-CsBatchPolicyAssignmentOperation Cmdlet

使用 [批次策略指派](assign-policies.md#assign-a-policy-to-a-batch-of-users)時，您可以移除或更新策略的使用者數量上限為一次 5，000 個。 例如，如果您有超過 5，000 個使用者，您必須提交多個批次。 為了獲得最佳結果，請勿一次提交多個批次。 在提交更多批次之前，允許批次完成處理。

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation Cmdlet](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)位於 PowerShell 模組Teams中。 在您遵循這些步驟之前，請安裝並連接到[powerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組Teams模組。 有關逐步指南，請參閱在[PowerShell Microsoft Teams安裝](teams-powershell-install.md)。

執行下列命令，從一批使用者移除 RestrictedAnonymousAccess 會議策略。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>取得批次作業的狀態

每個批次作業會返回作業識別碼，您可以使用此識別碼來追蹤工作分派的進度和狀態，並找出任何可能會發生的失敗。 例如，執行下列操作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

請確定 **ErrorCount** 為 0 (**0**) **完成 。** 

## <a name="related-topics"></a>相關主題

- [管理 Teams 中的會議原則](meeting-policies-in-teams.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)