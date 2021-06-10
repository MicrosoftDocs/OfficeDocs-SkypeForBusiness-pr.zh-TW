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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="865f0-103">從使用者移除 RestrictedAnonymousAccess Teams 會議原則</span><span class="sxs-lookup"><span data-stu-id="865f0-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="865f0-104">[會議Microsoft Teams](meeting-policies-in-teams.md)用來控制貴組織中使用者排程會議的會議參與者可用的功能。</span><span class="sxs-lookup"><span data-stu-id="865f0-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="865f0-105">Teams包含名為 RestrictedAnonymousAcces 的內建策略，其中包含預先定義的設定，包括限制匿名使用者啟動會議。</span><span class="sxs-lookup"><span data-stu-id="865f0-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="865f0-106"> (匿名使用者是尚未通過驗證的使用者。) 系統管理員無法編輯或變更會議策略中的預先定義設定。</span><span class="sxs-lookup"><span data-stu-id="865f0-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="865f0-107">本文將說明如何使用 PowerShell 從指派此策略的使用者移除 RestrictedAnonymousAccess 會議政策。</span><span class="sxs-lookup"><span data-stu-id="865f0-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="865f0-108">若要深入瞭解如何使用 PowerShell 管理Teams，請參閱 PowerShell Teams[概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="865f0-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="865f0-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="865f0-109">Before you start</span></span>

<span data-ttu-id="865f0-110">安裝並連接到[powerShell 商務用 Skype模組](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="865f0-110">Install and connect to the [Skype for Business PowerShell module](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="865f0-111">有關逐步指南，請參閱在[PowerShell Microsoft Teams安裝](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="865f0-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="865f0-112">取得Teams的會議策略指派</span><span class="sxs-lookup"><span data-stu-id="865f0-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="865f0-113">請執行下列操作，以取得Teams組織的會議策略指派。</span><span class="sxs-lookup"><span data-stu-id="865f0-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="865f0-114">在此範例中，會返回下列輸出，這表示兩個使用者被指派了 RestrictedAnonymousAccess 會議策略。</span><span class="sxs-lookup"><span data-stu-id="865f0-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="865f0-115">從使用者取消分配 RestrictedAnonymous 會議策略</span><span class="sxs-lookup"><span data-stu-id="865f0-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="865f0-116">若要從使用者移除 RestrictedAnonymous 會議政策，如果您有少數使用者 (例如少於 100 個使用者) ，您可以使用 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="865f0-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="865f0-117">如果您有大量使用者 (例如超過 100 個使用者) ，使用  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 提交批次處理作業會更有效率。</span><span class="sxs-lookup"><span data-stu-id="865f0-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="865f0-118">使用 Grant-CsTeamsMeeting Cmdlet</span><span class="sxs-lookup"><span data-stu-id="865f0-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="865f0-119">執行下列操作，從使用者移除 RestrictedAnonymous 會議政策。</span><span class="sxs-lookup"><span data-stu-id="865f0-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="865f0-120">使用 New-CsBatchPolicyAssignmentOperation Cmdlet</span><span class="sxs-lookup"><span data-stu-id="865f0-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="865f0-121">使用 [批次策略指派](assign-policies.md#assign-a-policy-to-a-batch-of-users)時，您可以移除或更新策略的使用者數量上限為一次 5，000 個。</span><span class="sxs-lookup"><span data-stu-id="865f0-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="865f0-122">例如，如果您有超過 5，000 個使用者，您必須提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="865f0-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="865f0-123">為了獲得最佳結果，請勿一次提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="865f0-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="865f0-124">在提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="865f0-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="865f0-125">[New-CsBatchPolicyAssignmentOperation Cmdlet](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)位於 PowerShell 模組Teams中。</span><span class="sxs-lookup"><span data-stu-id="865f0-125">The [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="865f0-126">在您遵循這些步驟之前，請安裝並連接到[powerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組Teams模組。</span><span class="sxs-lookup"><span data-stu-id="865f0-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="865f0-127">有關逐步指南，請參閱在[PowerShell Microsoft Teams安裝](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="865f0-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="865f0-128">執行下列命令，從一批使用者移除 RestrictedAnonymousAccess 會議策略。</span><span class="sxs-lookup"><span data-stu-id="865f0-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="865f0-129">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="865f0-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="865f0-130">每個批次作業會返回作業識別碼，您可以使用此識別碼來追蹤工作分派的進度和狀態，並找出任何可能會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="865f0-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="865f0-131">例如，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="865f0-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="865f0-132">請確定 **ErrorCount** 為 0 (**0**) **完成 。** </span><span class="sxs-lookup"><span data-stu-id="865f0-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="865f0-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="865f0-133">Related topics</span></span>

- [<span data-ttu-id="865f0-134">管理 Teams 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="865f0-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="865f0-135">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="865f0-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="865f0-136">將原則指派給 Teams 中的使用者</span><span class="sxs-lookup"><span data-stu-id="865f0-136">Assign policies to your users in Teams</span></span>](assign-policies.md)