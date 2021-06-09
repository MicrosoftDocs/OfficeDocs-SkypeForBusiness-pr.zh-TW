---
title: 指派策略套件給使用者和群組
author: KarliStites
ms.author: kastites
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解在 Microsoft Teams 中將策略套件指派給使用者和群組的不同Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: e70d5e2bf0db6cb7dfd93e35a8207fce61fa75fd
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796827"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="a98b3-103">指派策略套件給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="a98b3-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="a98b3-104">本文將審查將策略套件指派給使用者和群組的不同Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="a98b3-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="a98b3-105">閱讀前，請確定您閱讀過在 Teams[中指派策略 - 開始使用](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a98b3-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a98b3-106">每個使用者都需要進一步通訊附加元件才能接收自訂策略套件指派。</span><span class="sxs-lookup"><span data-stu-id="a98b3-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="a98b3-107">若要詳細資訊，請參閱適用于 Microsoft Teams[的 Advanced Communications 附加Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="a98b3-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="a98b3-108">指派策略套件給使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-108">Assign a policy package to users</span></span>

<span data-ttu-id="a98b3-109">Teams中的策略套件是預先定義的策略和設定集合，您可以指派給組織中具有相同或類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="a98b3-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="a98b3-110">每個策略套件都是針對使用者角色設計，並包含預先定義的策略和策略設定，可支援該角色的一般活動。</span><span class="sxs-lookup"><span data-stu-id="a98b3-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="a98b3-111">一些政策套件範例包括教育 (教師) 方案，以及醫療保健 (診所) 套件。</span><span class="sxs-lookup"><span data-stu-id="a98b3-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="a98b3-112">若要深入瞭解，請參閱在 Teams[中管理Teams。](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="a98b3-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="a98b3-113">將策略套件指派給一個使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="a98b3-114">在系統管理中心的左側導Microsoft Teams，請前往 **使用者，然後** 選取使用者。</span><span class="sxs-lookup"><span data-stu-id="a98b3-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="a98b3-115">在使用者的頁面上，**選取策略**，然後在策略套件 **旁邊，選取\*\*\*\*編輯**。</span><span class="sxs-lookup"><span data-stu-id="a98b3-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="a98b3-116">在指派 **策略套件窗格中** ，選取您想要指派的套件， **然後選取** 儲存 。</span><span class="sxs-lookup"><span data-stu-id="a98b3-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams系統管理中心螢幕擷取畫面，以將策略套件指派給使用者](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="a98b3-118">指派策略套件給多個使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="a98b3-119">在系統管理中心的左側導Microsoft Teams，前往策略套件，然後按一下套件名稱左側，選取您想要指派的政策套件。</span><span class="sxs-lookup"><span data-stu-id="a98b3-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a98b3-120">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="a98b3-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="a98b3-121">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="a98b3-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a98b3-122">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="a98b3-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a98b3-123">新增使用者完成後，請選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a98b3-123">When you're finished adding users, select **Save**.</span></span>

![Teams系統管理中心螢幕擷取畫面，以將策略套件指派給多個使用者](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="a98b3-125">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="a98b3-125">Assign a policy package to a group</span></span>

<span data-ttu-id="a98b3-126">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="a98b3-127">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="a98b3-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a98b3-128">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="a98b3-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="a98b3-129">建議最多 50，000 個使用者群組將策略套件指派給群組，但也會用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="a98b3-130">當您指派策略套件時，系統會立即將其指派給群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="a98b3-131">不過，將策略指派傳播給群組成員是做為背景作業，可能需要一些時間，視群組大小而不同。</span><span class="sxs-lookup"><span data-stu-id="a98b3-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="a98b3-132">當未從群組中未指定策略，或成員新加入群組或從群組中移除時，也是如此。</span><span class="sxs-lookup"><span data-stu-id="a98b3-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a98b3-133">在您開始使用之前，您必須瞭解 (優先順序規則)  ([群組](assign-policies-users-and-groups.md#group-assignment-ranking)作業) 。 [](assign-policies-users-and-groups.md#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="a98b3-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="a98b3-134">請確認您閱讀並瞭解本文 (本文中關於指派給群組[](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)之) 中必須瞭解的概念。</span><span class="sxs-lookup"><span data-stu-id="a98b3-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="a98b3-135">將策略套件指派給系統管理中心的一組使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="a98b3-136">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a98b3-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="a98b3-137">在左側流覽中，前往策略套件頁面。</span><span class="sxs-lookup"><span data-stu-id="a98b3-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="a98b3-138">選取群組原則工作分派選項卡。</span><span class="sxs-lookup"><span data-stu-id="a98b3-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="a98b3-139">選取 **新增群組**，然後在指派策略套件至群組窗格中，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a98b3-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="a98b3-140">a.</span><span class="sxs-lookup"><span data-stu-id="a98b3-140">a.</span></span> <span data-ttu-id="a98b3-141">搜尋並新增要指派策略套件的群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="a98b3-142">b.</span><span class="sxs-lookup"><span data-stu-id="a98b3-142">b.</span></span> <span data-ttu-id="a98b3-143">選取一個策略套件。</span><span class="sxs-lookup"><span data-stu-id="a98b3-143">Select a policy package.</span></span>

    <span data-ttu-id="a98b3-144">C。</span><span class="sxs-lookup"><span data-stu-id="a98b3-144">c.</span></span> <span data-ttu-id="a98b3-145">設定每個策略類型的排名。</span><span class="sxs-lookup"><span data-stu-id="a98b3-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="a98b3-146">D。</span><span class="sxs-lookup"><span data-stu-id="a98b3-146">d.</span></span> <span data-ttu-id="a98b3-147">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="a98b3-147">Select **Apply**.</span></span>

![顯示群組原則指派](media/group-pkg-assignment.png)

5. <span data-ttu-id="a98b3-149">若要管理特定策略類型的排名，請流覽至特定策略頁面。</span><span class="sxs-lookup"><span data-stu-id="a98b3-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="a98b3-150">若要將策略套件重新指派給群組，請先移除群組原則指派。</span><span class="sxs-lookup"><span data-stu-id="a98b3-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="a98b3-151">接著，請遵循上述步驟，將策略套件指派給群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="a98b3-152">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="a98b3-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="a98b3-153">取得 powerShell Teams模組</span><span class="sxs-lookup"><span data-stu-id="a98b3-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="a98b3-154">有關逐步指南，請參閱在[PowerShell Teams安裝](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="a98b3-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="a98b3-155">將策略套件指派給一組使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="a98b3-156">使用 [Grant-CsGroupPolicyPackageAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) 將策略套件指派給群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-156">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="a98b3-157">您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。</span><span class="sxs-lookup"><span data-stu-id="a98b3-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="a98b3-158">當您指派策略套件時，請針對 (中) 類型指定[](assign-policies-users-and-groups.md#group-assignment-ranking)群組分派排名。</span><span class="sxs-lookup"><span data-stu-id="a98b3-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="a98b3-159">在此範例中，我們將 Education_Teacher 策略套件指派給一個群組，其 TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的作業排名為 1，而 TeamsMeetingPolicy 的排名為 2。</span><span class="sxs-lookup"><span data-stu-id="a98b3-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="a98b3-160">將策略套件指派給一批使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="a98b3-161">使用批次策略套件指派，您可以一次指派一群組原則套件給大型使用者，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="a98b3-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="a98b3-162">您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派的政策套件。</span><span class="sxs-lookup"><span data-stu-id="a98b3-162">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="a98b3-163">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="a98b3-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="a98b3-164">接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="a98b3-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="a98b3-165">根據使用者的物件識別碼或會話初始通訊協定 (SIP) 位址。</span><span class="sxs-lookup"><span data-stu-id="a98b3-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="a98b3-166">使用者的 SIP 位址通常與 UPN 或電子郵件地址的使用者主體名稱 (相同) ，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="a98b3-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="a98b3-167">如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者的策略指派將會失敗。</span><span class="sxs-lookup"><span data-stu-id="a98b3-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="a98b3-168">如果批次包含重複的使用者，則重複專案將在處理前從批次中移除，而狀態只會提供給批次中的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="a98b3-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="a98b3-169">批次最多包含 5，000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="a98b3-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="a98b3-170">為了獲得最佳結果，一次不要提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="a98b3-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="a98b3-171">在提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="a98b3-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="a98b3-172">使用 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="a98b3-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="a98b3-173">執行下列操作，Microsoft Teams[安裝 PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams)模組 (如果您尚未安裝) 。</span><span class="sxs-lookup"><span data-stu-id="a98b3-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="a98b3-174">請確定您安裝版本 1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="a98b3-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="a98b3-175">執行下列操作以連接到Teams並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="a98b3-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a98b3-176">系統提示您時，請使用系統管理員認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="a98b3-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="a98b3-177">指派策略套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="a98b3-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="a98b3-178">在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將 Education_PrimaryStudent原則套件指派給一批使用者。</span><span class="sxs-lookup"><span data-stu-id="a98b3-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="a98b3-179">查看批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="a98b3-179">See the status of a batch assignment</span></span>

<span data-ttu-id="a98b3-180">執行下列操作以取得批次工作分派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的操作識別碼。</span><span class="sxs-lookup"><span data-stu-id="a98b3-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="a98b3-181">如果輸出顯示發生錯誤，請執行下列操作以取得有關錯誤的詳細資訊，這些資訊會顯示在 ```UserState``` 屬性中。</span><span class="sxs-lookup"><span data-stu-id="a98b3-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="a98b3-182">若要深入瞭解，請參閱 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="a98b3-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a98b3-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="a98b3-183">Related topics</span></span>

- [<span data-ttu-id="a98b3-184">使用Teams管理</span><span class="sxs-lookup"><span data-stu-id="a98b3-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="a98b3-185">在中管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a98b3-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="a98b3-186">TeamsPowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="a98b3-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a98b3-187">在 Teams 中指派Teams - 開始使用</span><span class="sxs-lookup"><span data-stu-id="a98b3-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
