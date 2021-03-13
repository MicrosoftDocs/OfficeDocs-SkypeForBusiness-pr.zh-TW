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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="a3bfa-103">從使用者移除 RestrictedAnonymousAccess Teams 會議政策</span><span class="sxs-lookup"><span data-stu-id="a3bfa-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="a3bfa-104">Microsoft Teams[中的會議](meeting-policies-in-teams.md)政策可用來控制組織中使用者排程之會議的會議參與者可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="a3bfa-105">Teams 包含名為 RestrictedAnonymousAccess 的內建策略，其中包含預先定義的設定，包括限制匿名使用者啟動會議。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="a3bfa-106"> (匿名使用者是尚未通過驗證的使用者。) 系統管理員無法編輯或變更會議政策中的預先定義設定。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="a3bfa-107">本文將說明如何使用 PowerShell 從指派此政策的使用者移除 RestrictedAnonymousAccess 會議政策。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="a3bfa-108">若要深入瞭解如何使用 PowerShell 管理 Teams，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a3bfa-109">在您開始之前</span><span class="sxs-lookup"><span data-stu-id="a3bfa-109">Before you start</span></span>

<span data-ttu-id="a3bfa-110">安裝並連接到商務 [用 Skype PowerShell 模組](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-110">Install and connect to the [Skype for Business PowerShell module](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell).</span></span> <span data-ttu-id="a3bfa-111">有關逐步指引，請參閱安裝 Microsoft [Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a3bfa-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="a3bfa-112">取得組織的 Teams 會議政策指派</span><span class="sxs-lookup"><span data-stu-id="a3bfa-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="a3bfa-113">執行下列操作以取得組織的 Teams 會議政策指派。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="a3bfa-114">在此範例中，會返回下列輸出，這表示有兩個使用者被指派了 RestrictedAnonymousAccess 會議政策。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="a3bfa-115">取消使用者對 RestrictedAnonymous 會議策略的未指定</span><span class="sxs-lookup"><span data-stu-id="a3bfa-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="a3bfa-116">若要從使用者移除 RestrictedAnonymous 會議政策，如果您有少數使用者 (例如，少於 100 個使用者，您可以使用 [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet) 。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="a3bfa-117">如果您擁有大量使用者 (例如，超過 100 個使用者) ，使用  [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) 提交批次作業會更有效率。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="a3bfa-118">使用Grant-CsTeamsMeeting Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a3bfa-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="a3bfa-119">執行下列操作以從使用者移除 RestrictedAnonymous 會議政策。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="a3bfa-120">使用 New-CsBatchPolicyAssignmentOperation Cmdlet</span><span class="sxs-lookup"><span data-stu-id="a3bfa-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="a3bfa-121">使用 [批次策略指派](assign-policies.md#assign-a-policy-to-a-batch-of-users)時，您可以移除或更新策略的使用者數量上限為一次 5，000 個。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="a3bfa-122">例如，如果您的使用者超過 5，000 個，您必須提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="a3bfa-123">為獲得最佳結果，請勿一次提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="a3bfa-124">提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="a3bfa-125">[New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)位於 Teams PowerShell 模組中。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="a3bfa-126">在您遵循這些步驟之前，請安裝並連接到 [Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="a3bfa-127">有關逐步指引，請參閱安裝 Microsoft [Teams PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a3bfa-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="a3bfa-128">執行下列命令，從一批使用者移除 RestrictedAnonymousAccess 會議政策。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="a3bfa-129">取得批次指派的狀態</span><span class="sxs-lookup"><span data-stu-id="a3bfa-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="a3bfa-130">每個批次指派會回一個作業識別碼，您可以使用它來追蹤工作分派的進度和狀態，並識別任何可能會發生的失敗。</span><span class="sxs-lookup"><span data-stu-id="a3bfa-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="a3bfa-131">例如，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a3bfa-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="a3bfa-132">請確定 **ErrorCount** 為 0 (**0**) **且完成 OverallStatus。** </span><span class="sxs-lookup"><span data-stu-id="a3bfa-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a3bfa-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3bfa-133">Related topics</span></span>

- [<span data-ttu-id="a3bfa-134">管理 Teams 中的會議原則</span><span class="sxs-lookup"><span data-stu-id="a3bfa-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="a3bfa-135">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="a3bfa-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a3bfa-136">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="a3bfa-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
