---
title: 指派策略給使用者和群組
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
description: 瞭解在 Microsoft Teams 中為使用者和群組指派策略的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574301"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="cd7ca-103">指派策略給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="cd7ca-103">Assign policies to users and groups</span></span>

<span data-ttu-id="cd7ca-104">本文將審查在 Microsoft Teams 中為使用者和群組指派策略的不同方式。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="cd7ca-105">閱讀前，請務必先閱讀 Teams [中的指派政策 - 開始使用](policy-assignment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="cd7ca-106">指派策略給個別使用者</span><span class="sxs-lookup"><span data-stu-id="cd7ca-106">Assign a policy to individual users</span></span>

<span data-ttu-id="cd7ca-107">請遵循下列步驟，一次指派一個策略給個別使用者或少數使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="cd7ca-108">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cd7ca-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="cd7ca-109">若要將策略指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="cd7ca-110">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者，然後** 選取使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="cd7ca-111">按一下使用者名稱左側以選取使用者，然後選取編輯 **設定**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="cd7ca-112">選取您想要指派原則，然後選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![在 Teams 系統管理中心指派策略給使用者](media/assign-policy-user.png)

<span data-ttu-id="cd7ca-114">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="cd7ca-115">在 Microsoft Teams 系統管理中心的左側流覽中，前往政策頁面。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="cd7ca-116">按一下策略名稱左側，選取您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="cd7ca-117">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="cd7ca-118">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="cd7ca-119">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="cd7ca-120">新增使用者完成後，請選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-120">When you're finished adding users, select **Apply**.</span></span>

![透過第二種方法將策略指派給 Teams 系統管理中心的使用者](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="cd7ca-122">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="cd7ca-122">Use PowerShell</span></span>

<span data-ttu-id="cd7ca-123">每個策略類型都有一組自己的 Cmdlet 來管理它。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="cd7ca-124">使用 ```Grant-``` 指定策略類型的 Cmdlet 來指派策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="cd7ca-125">例如，使用 ```Grant-CsTeamsMeetingPolicy``` Cmdlet 將 Teams 會議策略指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="cd7ca-126">這些 Cmdlet 包含在 Teams PowerShell 模組中，並記錄在 [商務用 Skype Cmdlet 參照中](https://docs.microsoft.com/powershell/skype)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype).</span></span>

 <span data-ttu-id="cd7ca-127">如果您尚未安裝，請 (Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 公開發行) ，然後執行下列操作以連接。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="cd7ca-128">商務用 Skype Online Connector 目前是 Teams PowerShell 最新模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="cd7ca-129">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online 連接器。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="cd7ca-130">在此範例中，我們將名為學生會議策略的 Teams 會議策略指派給名為 Reda 的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="cd7ca-131">若要深入瞭解，請參閱透過 [PowerShell 管理原則](teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="cd7ca-132">將策略指派給群組</span><span class="sxs-lookup"><span data-stu-id="cd7ca-132">Assign a policy to a group</span></span>

<span data-ttu-id="cd7ca-133">將策略指派給群組可讓您將策略指派給一組使用者，例如安全性群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cd7ca-134">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cd7ca-135">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="cd7ca-136">建議最多 50，000 個使用者群組使用群組原則指派給群組，但也適用于較大的群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="cd7ca-137">當您指派策略時，系統會立即將其指派給群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="cd7ca-138">不過，將策略指派傳播給群組成員是做為背景作業，可能需要一些時間，視群組大小而不同。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="cd7ca-139">當未從群組中未指定策略，或成員新加入群組或從群組中移除時，也是如此。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="cd7ca-140">群群組原則指派只會傳播給群組的直接成員使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="cd7ca-141">指派不會傳播到巢中群組的成員。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="cd7ca-142">關於指派給群組的策略，您需要知道什麼</span><span class="sxs-lookup"><span data-stu-id="cd7ca-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="cd7ca-143">在您開始使用之前，瞭解優先順序規則和群組作業排名非常重要。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="cd7ca-144">優先順序規則</span><span class="sxs-lookup"><span data-stu-id="cd7ca-144">Precedence rules</span></span>

<span data-ttu-id="cd7ca-145">對於給定的策略類型，使用者的有效政策會依據下列條件決定：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="cd7ca-146">直接指派給使用者的政策優先于指派給群組之相同類型之任何其他政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="cd7ca-147">換句話說，如果使用者直接獲派指定類型的策略，該使用者就不會從群組繼承相同類型的策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="cd7ca-148">這也表示如果使用者有直接指派給該使用者的指定類型之策略，您必須從使用者移除該策略，才能從群組繼承相同類型的策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="cd7ca-149">如果使用者沒有直接指派策略給他們，而且是兩個或多個群組的成員，且每個群組都有指派給該群組的相同類型之策略，則使用者會繼承排名最高的群組指派策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="cd7ca-150">如果使用者不是指派原則之任何群組的成員，則該原則類型的全域 (組織) 預設) 原則會適用于該使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="cd7ca-151">使用者的有效原則會依照以下規則更新：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="cd7ca-152">將使用者新加入或移除已指派策略的群組時。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="cd7ca-153">系統未從群組中未指定一個策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="cd7ca-154">系統會移除直接指派給使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="cd7ca-155">群組作業排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-155">Group assignment ranking</span></span>

<span data-ttu-id="cd7ca-156">當您將策略指派給群組時，您可以為群組作業指定排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="cd7ca-157">這是用來判斷如果使用者是兩個或多個群組的成員，且每個群組被指派了相同類型的策略，使用者應該繼承哪一個策略為其有效原則。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="cd7ca-158">群組作業排名是相對於相同類型的其他群組作業。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="cd7ca-159">例如，如果您要將通話策略指派給兩個群組，請設定一個作業的排名為 1，另一個則設為 2，其中 1 為最高排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="cd7ca-160">群組作業排名會指出哪些群組成員資格在繼承方面比其他群組成員資格重要或更相關。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="cd7ca-161">例如，假設您擁有兩個群組：Store Employees 和 Store 管理員。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="cd7ca-162">這兩個群組分別會指派 Teams 通話策略、Store Employees 通話策略和市售管理員通話政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="cd7ca-163">對於同時在兩個群組中的商店管理員，其主管角色比其員工角色更相關，因此指派給 Store Manager 群組的通話政策應具有較高的排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="cd7ca-164">組</span><span class="sxs-lookup"><span data-stu-id="cd7ca-164">Group</span></span> |<span data-ttu-id="cd7ca-165">Teams 通話策略名稱</span><span class="sxs-lookup"><span data-stu-id="cd7ca-165">Teams calling policy name</span></span>  |<span data-ttu-id="cd7ca-166">排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="cd7ca-167">市管理</span><span class="sxs-lookup"><span data-stu-id="cd7ca-167">Store Managers</span></span>   |<span data-ttu-id="cd7ca-168">市商店管理員通話政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="cd7ca-169">1</span><span class="sxs-lookup"><span data-stu-id="cd7ca-169">1</span></span>|
|<span data-ttu-id="cd7ca-170">儲存員工</span><span class="sxs-lookup"><span data-stu-id="cd7ca-170">Store Employees</span></span>    |<span data-ttu-id="cd7ca-171">儲存員工通話政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="cd7ca-172">2</span><span class="sxs-lookup"><span data-stu-id="cd7ca-172">2</span></span>|

<span data-ttu-id="cd7ca-173">如果您沒有指定排名，則策略作業會獲得最低的排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="cd7ca-174">在 Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cd7ca-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="cd7ca-175">目前，使用 Microsoft Teams 系統管理中心指派給群組的策略僅適用于 Teams 通話政策、Teams 通話停駐政策、Teams 政策、Teams 即時活動政策、Teams 會議策略和 Teams 傳訊政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="cd7ca-176">針對其他策略類型，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="cd7ca-177">在 Microsoft Teams 系統管理中心的左側流覽中，前往策略類型頁面。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="cd7ca-178">例如，請前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="cd7ca-179">選取組 **策略工作分派** 選項卡。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="cd7ca-180">選取 **新增群組**，然後在指派組策略窗格中，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="cd7ca-181">搜尋並新增要指派該策略的群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="cd7ca-182">設定群組作業的排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="cd7ca-183">選取您想要指派的政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="cd7ca-184">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-184">Select **Apply**.</span></span>
    
![將策略指派給 Teams 系統管理中心的群組](media/assign-policy-group.png)

<span data-ttu-id="cd7ca-186">若要移除群組原則作業，請在策略頁面的群組原則工作分派選項卡上，選取群組作業，然後選取 **移除**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="cd7ca-187">若要變更群組作業的排名，您首先必須移除群組原則作業。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="cd7ca-188">接著，請遵循上述步驟，將策略指派給群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="cd7ca-189">使用 PowerShell 選項</span><span class="sxs-lookup"><span data-stu-id="cd7ca-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="cd7ca-190">目前，所有 Teams 策略類型都不適用於使用 PowerShell 的群群組原則指派。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cd7ca-191">請參閱 [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 以尋找支援的策略類型清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-191">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="cd7ca-192">安裝並連接到 Microsoft Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="cd7ca-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="cd7ca-193">有關逐步指南，請參閱安裝 Teams [PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="cd7ca-194">將策略指派給一組使用者</span><span class="sxs-lookup"><span data-stu-id="cd7ca-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="cd7ca-195">使用 [New-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 將策略指派給群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-195">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="cd7ca-196">您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="cd7ca-197">在此範例中，我們將名為零售管理員會議策略的 Teams 會議策略指派給作業排名為 1 的群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="cd7ca-198">取得群組的策略指派</span><span class="sxs-lookup"><span data-stu-id="cd7ca-198">Get policy assignments for a group</span></span>

<span data-ttu-id="cd7ca-199">使用 [Get-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) 取得指派給群組的所有策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-199">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="cd7ca-200">請注意，即使已使用群組的 SIP 位址或電子郵件地址來指派策略，群組一直會以群組識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="cd7ca-201">在此範例中，我們會取回指派給特定群組的所有策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="cd7ca-202">在此範例中，我們會退回所有指派 Teams 會議策略的群組。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="cd7ca-203">從群組移除策略</span><span class="sxs-lookup"><span data-stu-id="cd7ca-203">Remove a policy from a group</span></span>

<span data-ttu-id="cd7ca-204">使用 [Remove-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) 從群組移除策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-204">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="cd7ca-205">當您從群組移除策略時，會更新指派給該群組且排名較低的相同類型其他策略的優先順序。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="cd7ca-206">例如，如果您移除排名為 2 的策略，則排名為 3 和 4 的策略會更新以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="cd7ca-207">下列兩個表格顯示此範例。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-207">The following two tables show this example.</span></span>

<span data-ttu-id="cd7ca-208">以下是 Teams 會議政策的政策指派和優先順序清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="cd7ca-209">群組名稱</span><span class="sxs-lookup"><span data-stu-id="cd7ca-209">Group name</span></span>  |<span data-ttu-id="cd7ca-210">策略名稱</span><span class="sxs-lookup"><span data-stu-id="cd7ca-210">Policy name</span></span>  |<span data-ttu-id="cd7ca-211">排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cd7ca-212">銷售</span><span class="sxs-lookup"><span data-stu-id="cd7ca-212">Sales</span></span>    |<span data-ttu-id="cd7ca-213">銷售政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-213">Sales policy</span></span>       | <span data-ttu-id="cd7ca-214">1</span><span class="sxs-lookup"><span data-stu-id="cd7ca-214">1</span></span>        |
|<span data-ttu-id="cd7ca-215">西部地區</span><span class="sxs-lookup"><span data-stu-id="cd7ca-215">West Region</span></span>     |<span data-ttu-id="cd7ca-216">西部地區政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-216">West Region policy</span></span>         |<span data-ttu-id="cd7ca-217">2</span><span class="sxs-lookup"><span data-stu-id="cd7ca-217">2</span></span>         |
|<span data-ttu-id="cd7ca-218">劃分</span><span class="sxs-lookup"><span data-stu-id="cd7ca-218">Division</span></span>    |<span data-ttu-id="cd7ca-219">部門政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-219">Division policy</span></span>         |<span data-ttu-id="cd7ca-220">3</span><span class="sxs-lookup"><span data-stu-id="cd7ca-220">3</span></span>         |
|<span data-ttu-id="cd7ca-221">附屬</span><span class="sxs-lookup"><span data-stu-id="cd7ca-221">Subsidiary</span></span>   |<span data-ttu-id="cd7ca-222">子公司政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-222">Subsidiary policy</span></span>        |<span data-ttu-id="cd7ca-223">4</span><span class="sxs-lookup"><span data-stu-id="cd7ca-223">4</span></span>         |

<span data-ttu-id="cd7ca-224">如果我們從西部區域群組移除西部區域政策，則策略指派和優先順序會更新如下。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="cd7ca-225">群組名稱</span><span class="sxs-lookup"><span data-stu-id="cd7ca-225">Group name</span></span>  |<span data-ttu-id="cd7ca-226">策略名稱</span><span class="sxs-lookup"><span data-stu-id="cd7ca-226">Policy name</span></span>  |<span data-ttu-id="cd7ca-227">排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="cd7ca-228">銷售</span><span class="sxs-lookup"><span data-stu-id="cd7ca-228">Sales</span></span>    |<span data-ttu-id="cd7ca-229">銷售政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-229">Sales policy</span></span>       | <span data-ttu-id="cd7ca-230">1</span><span class="sxs-lookup"><span data-stu-id="cd7ca-230">1</span></span>        |
|<span data-ttu-id="cd7ca-231">劃分</span><span class="sxs-lookup"><span data-stu-id="cd7ca-231">Division</span></span>    |<span data-ttu-id="cd7ca-232">部門政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-232">Division policy</span></span>         |<span data-ttu-id="cd7ca-233">2</span><span class="sxs-lookup"><span data-stu-id="cd7ca-233">2</span></span>         |
|<span data-ttu-id="cd7ca-234">附屬</span><span class="sxs-lookup"><span data-stu-id="cd7ca-234">Subsidiary</span></span>   |<span data-ttu-id="cd7ca-235">子公司政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-235">Subsidiary policy</span></span>        |<span data-ttu-id="cd7ca-236">3</span><span class="sxs-lookup"><span data-stu-id="cd7ca-236">3</span></span>        |

<span data-ttu-id="cd7ca-237">在此範例中，我們會從群組移除 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="cd7ca-238">變更群組的策略指派</span><span class="sxs-lookup"><span data-stu-id="cd7ca-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="cd7ca-239">[Set-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)即將推出。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-239">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="cd7ca-240">同時，若要變更群組原則指派，您可以移除群組中的目前策略指派，然後新增新的策略指派。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="cd7ca-241">將策略指派給群組之後，您可以使用 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) Cmdlet 變更該群組的策略指派，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="cd7ca-242">變更排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-242">Change the ranking</span></span>
- <span data-ttu-id="cd7ca-243">變更給定策略類型的策略</span><span class="sxs-lookup"><span data-stu-id="cd7ca-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="cd7ca-244">變更給定策略類型的策略和排名</span><span class="sxs-lookup"><span data-stu-id="cd7ca-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="cd7ca-245">在此範例中，我們將群組的 Teams 通話停駐策略變更為名為 SupportCallPark 且作業排名為 3 的策略。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="cd7ca-246">變更使用者的有效政策</span><span class="sxs-lookup"><span data-stu-id="cd7ca-246">Change the effective policy for a user</span></span>

<span data-ttu-id="cd7ca-247">以下是如何變更直接指派策略之使用者之有效原則的範例。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="cd7ca-248">首先，我們使用 [Get-CsUserPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) 與參數一起取得與使用者相關聯的 Teams 會議廣播政策 ```PolicySource``` 詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-248">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="cd7ca-249">輸出顯示使用者已直接獲派名為員工事件的 Teams 會議廣播政策，其優先順序會高於指派給使用者所屬群組的廠商即時事件。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="cd7ca-250">現在，我們會從使用者移除員工事件政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="cd7ca-251">這表示使用者不再有直接指派給他們的 Teams 會議廣播政策，而且會繼承指派給使用者所屬群組的廠商 Live Events 政策。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="cd7ca-252">在商務用 Skype PowerShell 模組中使用下列 Cmdlet 執行此操作。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="cd7ca-253">在 Teams PowerShell 模組中，使用遵循 Cmdlet，以縮放執行此作業，但批次$users指派 ，其中 $users是您指定的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="cd7ca-254">指派一個策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="cd7ca-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="cd7ca-255">使用系統管理中心</span><span class="sxs-lookup"><span data-stu-id="cd7ca-255">Use the admin center</span></span>

<span data-ttu-id="cd7ca-256">若要大量指派策略給使用者：</span><span class="sxs-lookup"><span data-stu-id="cd7ca-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="cd7ca-257">在 Microsoft Teams 系統管理中心的左側流覽中，選取 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="cd7ca-258">搜尋您想要將策略指派給使用者的使用者，或篩選該視圖以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="cd7ca-259">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="cd7ca-260">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="cd7ca-261">選取 **編輯設定**，進行您想要的變更， **然後選取** Apply 。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="cd7ca-262">若要查看原則作業的狀態，請在選取應用程式以提交原則作業後，于使用者頁面頂端出現的橫幅中，選取活動 **記錄**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="cd7ca-263">或者，在 Microsoft Teams 系統管理中心的左側流覽中，前往儀表板，然後在活動 **記錄下，** 選取查看 **詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="cd7ca-264">活動記錄會顯示過去 30 天內透過 Microsoft Teams 系統管理中心分批指派給超過 20 個使用者的策略指派。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="cd7ca-265">若要深入瞭解，請參閱 [在活動記錄中查看您的策略指派](activity-log.md)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="cd7ca-266">使用 PowerShell 方法</span><span class="sxs-lookup"><span data-stu-id="cd7ca-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="cd7ca-267">目前，並非所有 Teams 策略類型都提供使用 PowerShell 的批次策略指派。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="cd7ca-268">請參閱 [New-CsBatchPolicyAssignmentOperation，](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 以尋找支援原則類型的清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-268">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="cd7ca-269">使用批次策略指派，您可以一次指派一個策略給大型使用者組，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="cd7ca-270">您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派原則。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-270">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="cd7ca-271">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="cd7ca-272">接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="cd7ca-273">根據使用者的物件識別碼或會話初始通訊協定 (SIP) 位址。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="cd7ca-274">使用者的 SIP 位址通常與 UPN 或電子郵件地址的使用者主體名稱 (相同) ，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="cd7ca-275">如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者的策略指派將會失敗。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="cd7ca-276">如果批次包含重複的使用者，則重複專案將在處理前從批次中移除，而狀態只會提供給批次中的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="cd7ca-277">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="cd7ca-278">為了獲得最佳結果，一次不要提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="cd7ca-279">在提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="cd7ca-280">安裝並連接到 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="cd7ca-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="cd7ca-281">執行下列操作以安裝 [Microsoft Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="cd7ca-282">請確定您安裝版本 1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="cd7ca-283">執行下列操作以連接到 Teams 並開始會話。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="cd7ca-284">系統提示您時，請使用系統管理員認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="cd7ca-285">安裝並連接到 Azure AD PowerShell for Graph 模組， (選) </span><span class="sxs-lookup"><span data-stu-id="cd7ca-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="cd7ca-286">如果您尚未下載並安裝 [Azure AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 模組 (如果您尚未) 並連接到 Azure AD，以便您可以取回貴組織的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-286">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="cd7ca-287">執行下列操作以連接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="cd7ca-288">系統提示您時，請使用相同的系統管理員認證來登錄，以連接到 Teams。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="cd7ca-289">指派設定策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="cd7ca-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="cd7ca-290">在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將名為 HR App 設定原則的應用程式設定原則指派給 Users_ids.文字檔中列出的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="cd7ca-291">在此範例中，我們會連接到 Azure AD 以取回使用者集合，然後將名為新進員工傳訊政策的訊息原則指派給一批使用 SIP 位址指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="cd7ca-292">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="cd7ca-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="cd7ca-293">執行下列操作以取得批次工作分派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的操作識別碼。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="cd7ca-294">如果輸出顯示發生錯誤，請執行下列操作，以取得有關錯誤的詳細資訊 ，而錯誤則出現在 ```UserState``` 屬性中。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="cd7ca-295">若要深入瞭解，請參閱 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="cd7ca-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd7ca-296">相關主題</span><span class="sxs-lookup"><span data-stu-id="cd7ca-296">Related topics</span></span>

- [<span data-ttu-id="cd7ca-297">使用策略管理 Teams</span><span class="sxs-lookup"><span data-stu-id="cd7ca-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="cd7ca-298">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="cd7ca-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="cd7ca-299">在 Teams 中指派策略 - 開始使用</span><span class="sxs-lookup"><span data-stu-id="cd7ca-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
