---
title: 從使用者移除 RestrictedAnonymousAccess 團隊會議原則
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
description: 瞭解如何從貴組織中的使用者移除 RestrictedAnonymousAccess 小組會議原則。
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806253"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="b794f-103">從使用者移除 RestrictedAnonymousAccess 團隊會議原則</span><span class="sxs-lookup"><span data-stu-id="b794f-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="b794f-104">Microsoft 團隊中的[會議原則](meeting-policies-in-teams.md)可用來控制會議參與者針對您組織中的使用者排程之會議所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="b794f-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="b794f-105">團隊包含名為 RestrictedAnonymousAccess 的內建原則，其中包含預先定義的設定，包括限制匿名使用者開始會議。</span><span class="sxs-lookup"><span data-stu-id="b794f-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="b794f-106">[ (匿名使用者] 是尚未驗證的使用者。 ) 無法由管理員編輯或變更會議原則中的預先定義設定。</span><span class="sxs-lookup"><span data-stu-id="b794f-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="b794f-107">本文說明如何使用 PowerShell 來從獲指派此原則的使用者，移除 RestrictedAnonymousAccess 會議原則。</span><span class="sxs-lookup"><span data-stu-id="b794f-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="b794f-108">若要深入瞭解如何使用 PowerShell 管理團隊，請參閱 [團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b794f-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="b794f-109">開始之前</span><span class="sxs-lookup"><span data-stu-id="b794f-109">Before you start</span></span>

<span data-ttu-id="b794f-110">安裝並連接到 [商務用 Skype PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="b794f-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="b794f-111">如需逐步指導方針，請參閱 [安裝 Microsoft 團隊 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="b794f-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="b794f-112">為您的組織取得小組會議原則指派</span><span class="sxs-lookup"><span data-stu-id="b794f-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="b794f-113">執行下列動作，取得貴組織的小組會議原則指派。</span><span class="sxs-lookup"><span data-stu-id="b794f-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="b794f-114">在這個範例中，會傳回下列輸出，這表示兩位使用者已獲指派 RestrictedAnonymousAccess 會議原則。</span><span class="sxs-lookup"><span data-stu-id="b794f-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="b794f-115">從使用者取消指派 RestrictedAnonymous 會議原則</span><span class="sxs-lookup"><span data-stu-id="b794f-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="b794f-116">若要移除使用者的 RestrictedAnonymous 會議原則，您可以使用授與 [CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet （如果您有少量使用者 (例如，少於100個使用者) ）。</span><span class="sxs-lookup"><span data-stu-id="b794f-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="b794f-117">如果您有大量的使用者 (例如，100個以上的使用者) ，使用  [新的 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 來提交批次作業會更有效率。</span><span class="sxs-lookup"><span data-stu-id="b794f-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="b794f-118">使用 Grant-CsTeamsMeeting 原則 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b794f-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="b794f-119">執行下列動作，以移除使用者的 RestrictedAnonymous 會議原則。</span><span class="sxs-lookup"><span data-stu-id="b794f-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="b794f-120">使用 New-CsBatchPolicyAssignmentOperation Cmdlet</span><span class="sxs-lookup"><span data-stu-id="b794f-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="b794f-121">在 [批次原則作業](assign-policies.md#assign-a-policy-to-a-batch-of-users)中，您可以移除或更新原則的使用者數目上限為5000一次。</span><span class="sxs-lookup"><span data-stu-id="b794f-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="b794f-122">例如，如果您的使用者超過5000個，您將需要提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="b794f-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="b794f-123">若要獲得最佳結果，請不要一次提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="b794f-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="b794f-124">允許批次完成處理，然後再提交更多批次。</span><span class="sxs-lookup"><span data-stu-id="b794f-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="b794f-125">[新的-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet 位於團隊 PowerShell 模組中。</span><span class="sxs-lookup"><span data-stu-id="b794f-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="b794f-126">在您執行這些步驟之前，請先安裝並連接至 [團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="b794f-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="b794f-127">如需逐步指導方針，請參閱 [安裝 Microsoft 團隊 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="b794f-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="b794f-128">執行下列命令，以從一批使用者中移除 RestrictedAnonymousAccess 會議原則。</span><span class="sxs-lookup"><span data-stu-id="b794f-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="b794f-129">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="b794f-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="b794f-130">每個批次指派都會傳回一個作業識別碼，您可以用來追蹤作業的進度和狀態，並找出可能發生的任何失敗。</span><span class="sxs-lookup"><span data-stu-id="b794f-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="b794f-131">例如，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="b794f-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="b794f-132">請確定 **ErrorCount** 是 **0** (零) 且 **OverallStatus** 已 **完成**。</span><span class="sxs-lookup"><span data-stu-id="b794f-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b794f-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="b794f-133">Related topics</span></span>

- [<span data-ttu-id="b794f-134">在團隊中管理會議原則</span><span class="sxs-lookup"><span data-stu-id="b794f-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="b794f-135">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="b794f-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b794f-136">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="b794f-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
