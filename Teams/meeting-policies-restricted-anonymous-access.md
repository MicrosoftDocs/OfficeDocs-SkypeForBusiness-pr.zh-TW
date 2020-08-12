---
title: 從使用者移除 RestrictedAnonymousAccess 團隊會議原則
author: LanaChin
ms.author: v-lanac
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
description: 瞭解如何從貴組織中的使用者移除 RestrictedAnonymousAccess 小組會議原則。
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640975"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>從使用者移除 RestrictedAnonymousAccess 團隊會議原則

Microsoft 團隊中的[會議原則](meeting-policies-in-teams.md)可用來控制會議參與者針對您組織中的使用者排程之會議所提供的功能。 

團隊包含名為 RestrictedAnonymousAccess 的內建原則，其中包含預先定義的設定，包括限制匿名使用者開始會議。 [ (匿名使用者] 是尚未驗證的使用者。 ) 無法由管理員編輯或變更會議原則中的預先定義設定。

本文說明如何使用 PowerShell 來從獲指派此原則的使用者，移除 RestrictedAnonymousAccess 會議原則。 若要深入瞭解如何使用 PowerShell 管理團隊，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。

## <a name="before-you-start"></a>開始之前

安裝並連接到[商務用 Skype PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。 如需逐步指導方針，請參閱[安裝 Microsoft 團隊 PowerShell](teams-powershell-install.md)。

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>為您的組織取得小組會議原則指派

執行下列動作，取得貴組織的小組會議原則指派。

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

在這個範例中，會傳回下列輸出，這表示兩位使用者已獲指派 RestrictedAnonymousAccess 會議原則。

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>從使用者取消指派 RestrictedAnonymous 會議原則

若要移除使用者的 RestrictedAnonymous 會議原則，您可以使用授與[CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet （如果您有少量使用者 (例如，少於100個使用者) ）。 如果您有大量的使用者 (例如，100個以上的使用者) ，使用[新的 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 來提交批次作業會更有效率。

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>使用授與 CsTeamsMeeting 原則 Cmdlet

執行下列動作，以移除使用者的 RestrictedAnonymous 會議原則。

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>使用 CsBatchPolicyAssignmentOperation Cmdlet

在[批次原則作業](assign-policies.md#assign-a-policy-to-a-batch-of-users)中，您可以移除或更新原則的使用者數目上限為5000一次。 例如，如果您的使用者超過5000個，您將需要提交多個批次。 若要獲得最佳結果，請不要一次提交多個批次。 允許批次完成處理，然後再提交更多批次。

> [!NOTE]
> [新的-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 位於團隊 PowerShell 模組中。 在您執行這些步驟之前，請先安裝並連接至[團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。 如需逐步指導方針，請參閱[安裝 Microsoft 團隊 PowerShell](teams-powershell-install.md)。

執行下列命令，以從一批使用者中移除 RestrictedAnonymousAccess 會議原則。

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>取得批次作業的狀態

每個批次指派都會傳回一個作業識別碼，您可以用來追蹤作業的進度和狀態，並找出可能發生的任何失敗。 例如，執行下列動作：

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

請確定**ErrorCount**是**0** (零) 且**OverallStatus**已**完成**。

## <a name="related-topics"></a>相關主題

- [在團隊中管理會議原則](meeting-policies-in-teams.md)
- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [指派策略給小組中的使用者](assign-policies.md)
