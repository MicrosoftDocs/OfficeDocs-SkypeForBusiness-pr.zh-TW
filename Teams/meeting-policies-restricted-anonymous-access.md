---
title: 從使用者移除 RestrictedAnonymousAccess Teams 會議原則
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 瞭解如何從貴組織中的使用者移除 RestrictedAnonymousAccess Teams 會議原則。
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564101"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>從使用者移除 RestrictedAnonymousAccess Teams 會議原則

Microsoft Teams 中的[會議原則](meeting-policies-overview.md)可用來控制組織中使用者排程之會議的會議參與者可用的功能。 

Teams 包含名為 RestrictedAnonymousAccess 的內建原則，其中包含預先定義的設定，包括限制匿名使用者開始會議。  (匿名使用者是尚未驗證的使用者。) 系統管理員無法編輯或變更會議原則中預先定義的設定。

本文將示範如何使用 PowerShell 將 RestrictedAnonymousAccess 會議原則從獲指派此原則的使用者中移除。 若要深入瞭解如何使用 PowerShell 管理 Teams，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。

## <a name="before-you-start"></a>開始之前

安裝並聯機到[商務用 Skype PowerShell 模組](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。 如需逐步指引，請參閱 [安裝 Microsoft Teams PowerShell](teams-powershell-install.md)。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>取得貴組織的 Teams 會議原則指派

執行下列動作以取得貴組織的 Teams 會議原則指派。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

在此範例中，會傳回下列輸出，顯示兩個使用者獲派 RestrictedAnonymousAccess 會議原則。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>取消指派使用者的 RestrictedAnonymous 會議原則

若要從使用者移除 RestrictedAnonymous 會議原則，您可以使用 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet，例如 (少於 100 個使用者) 。 例如，如果您有大量使用者 (，) 超過 100 個使用者，使用  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) Cmdlet 提交批次處理作業會更有效率。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用Grant-CsTeamsMeeting原則 Cmdlet

執行下列動作以移除使用者的 RestrictedAnonymous 會議原則。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 New-CsBatchPolicyAssignmentOperation Cmdlet

透過 [批次處理原則指派](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)，您可以一次移除或更新原則的使用者人數上限為 5，000 人。 例如，如果您有超過 5，000 個使用者，您必須提交多個批次。 為獲得最佳結果，請勿一次提交多個批次。 允許批次完成處理，然後再提交更多批次。

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) Cmdlet 位於 Teams PowerShell 模組中。 依照下列步驟進行之前，請先安裝並聯機到 [Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 如需逐步指引，請參閱 [安裝 Microsoft Teams PowerShell](teams-powershell-install.md)。

執行下列命令以移除一批使用者的 RestrictedAnonymousAccess 會議原則。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>取得批次指派的狀態

每個批次指派都會傳回作業識別碼，可用來追蹤作業的進度和狀態，並識別可能發生的任何失敗。 例如，執行下列動作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

確認 **ErrorCount** 為 **0** (零) 且已 **完成** **OverallStatus**。

## <a name="related-topics"></a>相關主題

- [管理 Teams 中的會議原則](meeting-policies-overview.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](policy-assignment-overview.md)