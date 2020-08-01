---
title: 在 Microsoft Teams 中將原則指派給使用者
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
description: 瞭解在 Microsoft 團隊中將原則指派給使用者的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 9d6253645e674d680f86d0b6f89a62968e6c21ba
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533940"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="609ba-103">在 Microsoft Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="609ba-104">身為系統管理員，您可以使用原則來控制貴組織中的使用者可以使用的小組功能。</span><span class="sxs-lookup"><span data-stu-id="609ba-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="609ba-105">例如，有一些通話原則、會議原則和訊息原則，只會為您命名。</span><span class="sxs-lookup"><span data-stu-id="609ba-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="609ba-106">組織擁有不同類型的使用者，而且您可以建立並指派您所建立及指派的規則，讓您根據這些需求，將原則設定量身定制給不同的使用者組。</span><span class="sxs-lookup"><span data-stu-id="609ba-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="609ba-107">為了讓您更容易管理貴組織中的原則，小組提供了幾種指派原則給使用者的方法。</span><span class="sxs-lookup"><span data-stu-id="609ba-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="609ba-108">您可以將原則直接指派給使用者、個別或在批次作業中縮放，或指派給使用者是其成員的群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="609ba-109">您也可以使用 [原則套件]，將預設的原則集合指派給組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="609ba-110">您選擇的選項取決於您所管理的原則數量，以及您要指派的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="609ba-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="609ba-111">您可以設定全域（組織範圍預設值）原則，讓其套用到貴組織中的最大使用者數，您只需將原則指派給需要特殊原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="609ba-112">本文說明您可以將原則指派給使用者的不同方式，以及使用方式的建議案例。</span><span class="sxs-lookup"><span data-stu-id="609ba-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="609ba-113">優先使用哪種原則？</span><span class="sxs-lookup"><span data-stu-id="609ba-113">Which policy takes precedence?</span></span>

<span data-ttu-id="609ba-114">使用者針對每種原則類型都有一個有效原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="609ba-115">您可能也有可能是使用者直接指派了原則，也是指派了相同類型之原則之一或多個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="609ba-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="609ba-116">在這種情況下，哪個原則優先？</span><span class="sxs-lookup"><span data-stu-id="609ba-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="609ba-117">根據優先順序規則來決定使用者的有效原則，如下所示。</span><span class="sxs-lookup"><span data-stu-id="609ba-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="609ba-118">如果使用者是直接指派原則（個別或透過批次工作指派），則該原則會優先取得優先順序。</span><span class="sxs-lookup"><span data-stu-id="609ba-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="609ba-119">在下列範例中，使用者的有效原則是 Lincoln 方形會議原則，可直接指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![顯示直接指派的原則優先的圖表](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="609ba-121">如果使用者未直接指派指定類型的原則，則指派給該使用者所屬群組的原則優先。</span><span class="sxs-lookup"><span data-stu-id="609ba-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="609ba-122">如果使用者是多個群組的成員，則具有指定原則類型之最高[群組指派排名](#group-assignment-ranking)的原則優先。</span><span class="sxs-lookup"><span data-stu-id="609ba-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="609ba-123">在這個範例中，使用者的有效原則是 Exec 小組和 HD 原則，其指派優先順序最高為與使用者所屬的其他群組相關，而且也指派有相同原則類型的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![圖表顯示如何從群組繼承原則優先](media/assign-policies-example-group.png)

<span data-ttu-id="609ba-125">如果使用者未直接指派原則，或是不是指派策略的任何群組的成員，使用者就會取得該原則類型的全域（組織範圍預設值）原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="609ba-126">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="609ba-126">Here's an example.</span></span>

![圖表顯示全域原則優先的方式](media/assign-policies-example-global.png)

<span data-ttu-id="609ba-128">若要深入瞭解，請參閱[優先順序規則](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="609ba-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="609ba-129">指派原則的方法</span><span class="sxs-lookup"><span data-stu-id="609ba-129">Ways to assign policies</span></span>

<span data-ttu-id="609ba-130">以下是您可以將原則指派給使用者的方式，以及每個方案的建議案例的概覽。</span><span class="sxs-lookup"><span data-stu-id="609ba-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="609ba-131">按一下連結以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="609ba-131">Click the links to learn more.</span></span>

<span data-ttu-id="609ba-132">在將原則指派給個別的使用者或群組之前，請先[設定全域（組織範圍預設值）原則](#set-the-global-policies)，讓其套用到貴組織中的最大使用者數。</span><span class="sxs-lookup"><span data-stu-id="609ba-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="609ba-133">全域原則設定之後，您只需將原則指派給需要特殊原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="609ba-134">請這麼做</span><span class="sxs-lookup"><span data-stu-id="609ba-134">Do this</span></span>  |<span data-ttu-id="609ba-135">If .。。</span><span class="sxs-lookup"><span data-stu-id="609ba-135">If...</span></span>  | <span data-ttu-id="609ba-136">使用 .。。</span><span class="sxs-lookup"><span data-stu-id="609ba-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="609ba-137">指派原則給個別使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="609ba-138">您是團隊新手，剛開始使用，或只需要指派一或幾個原則給少數使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="609ba-139">商務用 Skype Online PowerShell 模組中的 Microsoft 團隊管理員中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="609ba-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="609ba-140">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="609ba-140">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="609ba-141">您需要將多個原則指派給貴組織中擁有相同或相似角色的特定使用者組。</span><span class="sxs-lookup"><span data-stu-id="609ba-141">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="609ba-142">例如，將教育版（教師）原則套件指派給學校的教師，讓他們能完全存取聊天、通話及會議，以及將教育（次要學校學生）原則封裝到次要學生，以限制私人電話等特定功能。</span><span class="sxs-lookup"><span data-stu-id="609ba-142">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="609ba-143">團隊 PowerShell 模組中的 Microsoft 團隊系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="609ba-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="609ba-144">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="609ba-145">您必須將原則指派給大型使用者組。</span><span class="sxs-lookup"><span data-stu-id="609ba-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="609ba-146">例如，您想要一次將原則指派給組織中的成百上千位使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="609ba-147">團隊 PowerShell 模組中的 Microsoft 團隊系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="609ba-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="609ba-148">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="609ba-148">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="609ba-149">您必須根據使用者的群組成員資格指派原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-149">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="609ba-150">例如，您想要將原則指派給安全性群組或通訊群組清單中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-150">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="609ba-151">團隊 PowerShell 模組中的 Microsoft 團隊系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="609ba-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="609ba-152">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-152">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="609ba-153">您需要將多個原則指派給組織中擁有相同或相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-153">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="609ba-154">例如，您可以使用批次作業將教育版（教師）原則套件指派給學校中的所有教師，讓他們能完全存取聊天、通話及會議，並將教育（次要學校學生）原則套件指派給一批次要學生，以限制私人通話等特定功能。</span><span class="sxs-lookup"><span data-stu-id="609ba-154">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="609ba-155">團隊 PowerShell 模組中的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="609ba-155">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="609ba-156">將原則套件指派給群組（即將推出）</span><span class="sxs-lookup"><span data-stu-id="609ba-156">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="609ba-157">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="609ba-157">Set the global policies</span></span>

<span data-ttu-id="609ba-158">請依照下列步驟，為每個原則類型設定全域（組織範圍預設值）原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-158">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="609ba-159">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="609ba-159">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="609ba-160">在 Microsoft 團隊系統管理中心的左導覽中，移至您要更新之原則類型的原則頁面。</span><span class="sxs-lookup"><span data-stu-id="609ba-160">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="609ba-161">例如，**小組**  >  **團隊原則**、**會議**  >  **會議原則**、**訊息策略**或**語音**  >  **通話原則**。</span><span class="sxs-lookup"><span data-stu-id="609ba-161">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="609ba-162">選取**全域（組織範圍預設值）** 原則，以查看目前的設定。</span><span class="sxs-lookup"><span data-stu-id="609ba-162">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="609ba-163">視需要更新原則，**然後選取 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="609ba-163">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="609ba-164">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="609ba-164">Using PowerShell</span></span>

<span data-ttu-id="609ba-165">若要使用 PowerShell 來設定全域原則，請使用全域識別碼。</span><span class="sxs-lookup"><span data-stu-id="609ba-165">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="609ba-166">首先，查看目前的全域原則，以判斷您要變更的設定。</span><span class="sxs-lookup"><span data-stu-id="609ba-166">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="609ba-167">接著，視需要更新全域原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-167">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="609ba-168">您只需要指定您想要變更之設定的值。</span><span class="sxs-lookup"><span data-stu-id="609ba-168">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="609ba-169">指派原則給個別使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-169">Assign a policy to individual users</span></span>

<span data-ttu-id="609ba-170">請按照下列步驟，將原則指派給個別的使用者或一次少數的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-170">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="609ba-171">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="609ba-171">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="609ba-172">若要將原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="609ba-172">To assign a policy to a user:</span></span>

1. <span data-ttu-id="609ba-173">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-173">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="609ba-174">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="609ba-174">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="609ba-175">選取您要指派的原則，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="609ba-175">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="609ba-176">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="609ba-176">Or, you can also do the following:</span></span>

1. <span data-ttu-id="609ba-177">在 Microsoft 團隊系統管理中心的左導覽中，移至 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="609ba-177">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="609ba-178">按一下原則名稱左邊的，選取您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-178">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="609ba-179">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="609ba-179">Select **Manage users**.</span></span>
4. <span data-ttu-id="609ba-180">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="609ba-180">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="609ba-181">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="609ba-181">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="609ba-182">完成新增使用者後，**請選取 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="609ba-182">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="609ba-183">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="609ba-183">Using PowerShell</span></span>

<span data-ttu-id="609ba-184">每個原則類型都有自己的一組 Cmdlet 來管理它。</span><span class="sxs-lookup"><span data-stu-id="609ba-184">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="609ba-185">使用 ```Grant-``` 指定原則類型的 Cmdlet 來指派原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-185">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="609ba-186">例如，使用 ```Grant-CsTeamsMeetingPolicy``` Cmdlet 將團隊會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-186">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="609ba-187">這些 Cmdlet 包含在商務用 Skype Online PowerShell 模組中，且已記錄在[商務用 skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。</span><span class="sxs-lookup"><span data-stu-id="609ba-187">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="609ba-188">下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)（如果您尚未這麼做），然後執行下列動作以連線至商務用 skype online 並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="609ba-188">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="609ba-189">在這個範例中，我們會將名為 Student 會議原則的小組會議原則指派給名為 Reda 的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-189">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="609ba-190">若要深入瞭解，請透過[PowerShell 閱讀管理原則](teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="609ba-190">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="609ba-191">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="609ba-191">Assign a policy package</span></span>

<span data-ttu-id="609ba-192">小組中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在貴組織中擁有相同或相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-192">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="609ba-193">每個原則套件都是圍繞使用者角色來設計，其中包含支援該角色典型活動的預先定義原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="609ba-193">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="609ba-194">策略套件的一些範例是教育版（教師）套件和醫療保健（臨床工作者）封裝。</span><span class="sxs-lookup"><span data-stu-id="609ba-194">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="609ba-195">當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中每個原則的設定，以符合使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="609ba-195">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="609ba-196">若要深入瞭解原則套件，包括如何指派及管理它們的逐步指導方針，請參閱[管理團隊中的原則套件](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="609ba-196">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="609ba-197">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-197">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="609ba-198">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="609ba-198">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="609ba-199">若要將原則大量指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="609ba-199">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="609ba-200">在 Microsoft [團隊管理中心] 的左導覽中，選取 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="609ba-200">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="609ba-201">搜尋您要指派原則的使用者，或篩選視圖以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-201">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="609ba-202">在 [&#x2713;]\*\*\*\* (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-202">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="609ba-203">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="609ba-203">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="609ba-204">按一下 [編輯設定]\*\*\*\*，進行所需的變更，然後按一下 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="609ba-204">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="609ba-205">若要查看原則指派的狀態，在您按一下 [套用] 以提交原則指派之後，在 [**使用者**] 頁面頂端出現的橫幅中 **，按一下 [** **活動記錄**]。</span><span class="sxs-lookup"><span data-stu-id="609ba-205">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="609ba-206">或者，在 Microsoft [團隊管理中心] 的左導覽中，移至 [**儀表板**]，然後按一下 [**活動記錄**] 下的 [**查看詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="609ba-206">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="609ba-207">活動記錄會顯示在過去30天內，透過 Microsoft [小組系統管理中心] 向超過20名使用者批次的原則作業。</span><span class="sxs-lookup"><span data-stu-id="609ba-207">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="609ba-208">若要深入瞭解，請參閱[在活動記錄中查看您的原則分派](activity-log.md)。</span><span class="sxs-lookup"><span data-stu-id="609ba-208">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="609ba-209">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="609ba-209">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="609ba-210">目前，使用 PowerShell 的批原則指派不適用於所有團隊原則類型。</span><span class="sxs-lookup"><span data-stu-id="609ba-210">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="609ba-211">如需支援的原則類型清單，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。</span><span class="sxs-lookup"><span data-stu-id="609ba-211">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="609ba-212">使用批次原則指派，您可以一次將原則指派給大型的使用者組，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="609ba-212">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="609ba-213">您可以使用 ```New-CsBatchPolicyAssignmentOperation``` Cmdlet 來提交一批使用者和您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-213">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="609ba-214">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="609ba-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="609ba-215">然後，您就可以使用此 ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="609ba-215">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="609ba-216">您可以依其物件識別碼或會話初始通訊協定（SIP）位址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-216">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="609ba-217">請注意，使用者的 SIP 位址通常會有與使用者主體名稱（UPN）或電子郵件地址相同的值，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="609ba-217">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="609ba-218">如果使用者是使用其 UPN 或電子郵件指定的，但其值不是其 SIP 位址，則使用者的原則指派將會失敗。</span><span class="sxs-lookup"><span data-stu-id="609ba-218">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="609ba-219">如果批次包含重複的使用者，則會在處理前從批次中移除重複專案，且狀態將只提供給批次中剩餘的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-219">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="609ba-220">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-220">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="609ba-221">若要獲得最佳結果，請不要一次提交超過幾個批次。</span><span class="sxs-lookup"><span data-stu-id="609ba-221">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="609ba-222">允許批次完成處理，然後再提交更多批次。</span><span class="sxs-lookup"><span data-stu-id="609ba-222">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="609ba-223">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="609ba-223">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="609ba-224">請執行下列動作來安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="609ba-224">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="609ba-225">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="609ba-225">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="609ba-226">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="609ba-226">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="609ba-227">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="609ba-227">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="609ba-228">安裝並連接至 Azure AD PowerShell for Graph 模組（選用）</span><span class="sxs-lookup"><span data-stu-id="609ba-228">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="609ba-229">您可能也想要[下載並安裝適用于圖形模組的 AZURE AD PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （如果您尚未這麼做）並聯機至 azure ad，以便在您的組織中取得使用者清單。</span><span class="sxs-lookup"><span data-stu-id="609ba-229">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="609ba-230">執行下列動作以連線至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="609ba-230">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="609ba-231">出現提示時，請使用您用來連線至團隊的相同管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="609ba-231">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="609ba-232">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-232">Assign a policy to a batch of users</span></span>

<span data-ttu-id="609ba-233">在這個範例中，我們會使用 ```New-CsBatchPolicyAssignmentOperation``` Cmdlet，將名為 HR App 設定原則的 app 設定原則指派給 Users_ids 文字檔中所列的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-233">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="609ba-234">在這個範例中，我們會連線至 Azure AD 來取得使用者集合，然後將名為「新員工訊息」的訊息策略指派給使用其 SIP 位址指定的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-234">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="609ba-235">若要深入瞭解，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="609ba-235">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="609ba-236">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="609ba-236">Get the status of a batch assignment</span></span>

<span data-ttu-id="609ba-237">執行下列操作以取得批次工作的狀態，其中 OperationId 是由 ```New-CsBatchPolicyAssignmentOperation``` Cmdlet 針對指定批次傳回的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="609ba-237">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="609ba-238">如果輸出顯示發生錯誤，請執行下列動作，以取得有關屬性中錯誤的詳細資訊 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="609ba-238">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="609ba-239">若要深入瞭解，請參閱[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="609ba-239">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="609ba-240">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="609ba-240">Assign a policy to a group</span></span>

<span data-ttu-id="609ba-241">[群組原則指派] 可讓您將原則指派給使用者群組，例如安全群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="609ba-241">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="609ba-242">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="609ba-242">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="609ba-243">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="609ba-243">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="609ba-244">建議將原則指派給群組，以適用于最多50000個使用者的群組，但也適用于較大的群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-244">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="609ba-245">指派原則時，它會立即指派給群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-245">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="609ba-246">不過，請注意，原則指派對群組成員的傳播是作為背景作業執行，可能需要一些時間，視群組的大小而定。</span><span class="sxs-lookup"><span data-stu-id="609ba-246">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="609ba-247">如果沒有從群組中取消指派原則，或是在群組中新增或移除某個原則，就是如此。</span><span class="sxs-lookup"><span data-stu-id="609ba-247">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="609ba-248">針對群組的原則指派所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="609ba-248">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="609ba-249">在您開始之前，請務必瞭解優先規則與群組指派排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-249">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="609ba-250">優先規則</span><span class="sxs-lookup"><span data-stu-id="609ba-250">Precedence rules</span></span>

<span data-ttu-id="609ba-251">針對特定原則類型，根據下列專案來決定使用者的有效原則：</span><span class="sxs-lookup"><span data-stu-id="609ba-251">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="609ba-252">直接指派給使用者的原則，優先于任何其他指派給群組之相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-252">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="609ba-253">換句話說，如果使用者是直接指派給特定類型的原則，該使用者就不會從群組繼承相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-253">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="609ba-254">這也表示如果使用者具有直接指派給他們的特定類型的原則，您必須先移除使用者的原則，才能從群組繼承相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-254">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="609ba-255">如果使用者沒有直接指派的原則，且是兩個或多個群組的成員，且每個群組都有指派相同類型的原則，則使用者會繼承最高排名的群組指派原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-255">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="609ba-256">如果使用者不是指派原則的任何群組的成員，該原則類型的全域（組織範圍預設值）原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-256">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="609ba-257">在已指派原則的群組中新增或移除使用者時，會根據這些規則來更新使用者的有效原則、將原則指派給群組，或直接指派給該使用者的原則也會被移除。</span><span class="sxs-lookup"><span data-stu-id="609ba-257">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="609ba-258">群組指派排名</span><span class="sxs-lookup"><span data-stu-id="609ba-258">Group assignment ranking</span></span>
 
<span data-ttu-id="609ba-259">當您將原則指派給群組時，請指定群組指派的排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-259">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="609ba-260">這是用來判斷，如果使用者是兩個或多個群組的成員，且每個群組都指派相同類型的原則，使用者應該繼承為其有效原則的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-260">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="609ba-261">群組指派排名是相對於相同類型的其他群組分派。</span><span class="sxs-lookup"><span data-stu-id="609ba-261">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="609ba-262">例如，如果您要將通話原則指派給兩個群組，請將一個指派的等級設定為1，而另一個指派給2，1為最高排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-262">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="609ba-263">[群組指派排名] 會指出哪些群組成員資格比繼承更重要，或比其他群組成員資格更相關。</span><span class="sxs-lookup"><span data-stu-id="609ba-263">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="609ba-264">例如，您有兩個群組，請儲存 [員工] 和 [書店管理員]。</span><span class="sxs-lookup"><span data-stu-id="609ba-264">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="609ba-265">兩個群組都會獲指派團隊通話原則，分別將員工撥打電話給原則和商店管理員呼叫原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-265">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="609ba-266">對於在這兩個群組中的書店管理員而言，其角色會與員工的角色更相關，所以指派給商店管理員群組的呼叫原則應該有較高的排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-266">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="609ba-267">群組</span><span class="sxs-lookup"><span data-stu-id="609ba-267">Group</span></span> |<span data-ttu-id="609ba-268">小組通話原則名稱</span><span class="sxs-lookup"><span data-stu-id="609ba-268">Teams calling policy name</span></span>  |<span data-ttu-id="609ba-269">排名</span><span class="sxs-lookup"><span data-stu-id="609ba-269">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="609ba-270">商店管理員</span><span class="sxs-lookup"><span data-stu-id="609ba-270">Store Managers</span></span>   |<span data-ttu-id="609ba-271">商店管理員通話原則</span><span class="sxs-lookup"><span data-stu-id="609ba-271">Store Managers Calling Policy</span></span>         |<span data-ttu-id="609ba-272">1</span><span class="sxs-lookup"><span data-stu-id="609ba-272">1</span></span>|
|<span data-ttu-id="609ba-273">儲存員工</span><span class="sxs-lookup"><span data-stu-id="609ba-273">Store Employees</span></span>    |<span data-ttu-id="609ba-274">儲存員工的通話原則</span><span class="sxs-lookup"><span data-stu-id="609ba-274">Store Employees Calling Policy</span></span>      |<span data-ttu-id="609ba-275">2</span><span class="sxs-lookup"><span data-stu-id="609ba-275">2</span></span>|

<span data-ttu-id="609ba-276">如果您沒有指定排名，則會給予原則指派最低等級。</span><span class="sxs-lookup"><span data-stu-id="609ba-276">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="609ba-277">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="609ba-277">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="609ba-278">目前，使用 Microsoft 團隊系統管理中心群組的原則指派只適用于小組呼叫原則、小組通話寄存原則、團隊原則、團隊即時事件原則、團隊會議原則和團隊訊息原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-278">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="609ba-279">針對其他原則類型，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="609ba-279">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="609ba-280">在 Microsoft 團隊系統管理中心的左導覽中，移至 [原則類型] 頁面。</span><span class="sxs-lookup"><span data-stu-id="609ba-280">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="609ba-281">例如，移至 [**會議**  >  **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="609ba-281">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="609ba-282">選取 [**群組原則指派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="609ba-282">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="609ba-283">選取 [**新增群組**]，然後在 [**將原則指派給群組**] 窗格中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="609ba-283">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="609ba-284">搜尋並新增您要指派原則的群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-284">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="609ba-285">設定群組指派的排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-285">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="609ba-286">選取您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-286">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="609ba-287">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="609ba-287">Select **Apply**.</span></span>

<span data-ttu-id="609ba-288">若要移除群組原則指派，請在 [原則] 頁面的 [**群組原則指派**] 索引標籤上，選取 [群組指派]，然後選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="609ba-288">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="609ba-289">若要變更群組指派的排名，您必須先移除 [群組原則指派]。</span><span class="sxs-lookup"><span data-stu-id="609ba-289">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="609ba-290">然後，按照上述步驟，將原則指派給群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-290">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="609ba-291">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="609ba-291">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="609ba-292">目前，對於所有團隊原則類型，使用 PowerShell 的群組的原則指派都無法使用。</span><span class="sxs-lookup"><span data-stu-id="609ba-292">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="609ba-293">如需支援的原則類型清單，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="609ba-293">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="609ba-294">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="609ba-294">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="609ba-295">如需逐步指導方針，請參閱[安裝團隊 PowerShell](teams-powershell-install.md)。</span><span class="sxs-lookup"><span data-stu-id="609ba-295">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="609ba-296">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="609ba-296">Assign a policy to a group</span></span>

<span data-ttu-id="609ba-297">您使用 ```New-CsGroupPolicyAssignment``` Cmdlet 將原則指派給群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-297">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="609ba-298">您可以使用 [物件識別碼]、[SIP 位址] 或 [電子郵件地址] 來指定群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-298">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="609ba-299">在這個範例中，我們會使用 ```New-CsGroupPolicyAssignment``` Cmdlet，將名為「零售經理」會議原則的小組會議原則指派給作業排名為1的群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-299">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="609ba-300">若要深入瞭解，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="609ba-300">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="609ba-301">取得群組的原則指派</span><span class="sxs-lookup"><span data-stu-id="609ba-301">Get policy assignments for a group</span></span>

<span data-ttu-id="609ba-302">使用 ```Get-CsGroupPolicyAssignment``` Cmdlet 來取得指派給群組的所有原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-302">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="609ba-303">請注意，即使其 SIP 位址或電子郵件地址是用來指派原則，群組也永遠會依其群組識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="609ba-303">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="609ba-304">在這個範例中，我們會檢索指派給特定群組的所有原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-304">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="609ba-305">在這個範例中，我們會傳回指派給「團隊」會議原則的所有群組。</span><span class="sxs-lookup"><span data-stu-id="609ba-305">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="609ba-306">若要深入瞭解，請參閱[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="609ba-306">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="609ba-307">從群組中移除原則</span><span class="sxs-lookup"><span data-stu-id="609ba-307">Remove a policy from a group</span></span>

<span data-ttu-id="609ba-308">使用 ```Remove-CsGroupPolicyAssignment``` Cmdlet 從群組中移除原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-308">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="609ba-309">當您從群組中移除原則時，會更新指派給該群組之相同類型之其他原則的優先順序，並更新較低排名的專案。</span><span class="sxs-lookup"><span data-stu-id="609ba-309">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="609ba-310">例如，如果您移除等級為2的原則，就會更新等級為3和4的原則，以反映其新的排名。</span><span class="sxs-lookup"><span data-stu-id="609ba-310">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="609ba-311">下列兩個數據表顯示這個範例。</span><span class="sxs-lookup"><span data-stu-id="609ba-311">The following two tables show this example.</span></span>

<span data-ttu-id="609ba-312">以下是團隊會議原則的原則指派與優先順序清單。</span><span class="sxs-lookup"><span data-stu-id="609ba-312">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="609ba-313">組名</span><span class="sxs-lookup"><span data-stu-id="609ba-313">Group name</span></span>  |<span data-ttu-id="609ba-314">原則名稱</span><span class="sxs-lookup"><span data-stu-id="609ba-314">Policy name</span></span>  |<span data-ttu-id="609ba-315">排名</span><span class="sxs-lookup"><span data-stu-id="609ba-315">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="609ba-316">銷售</span><span class="sxs-lookup"><span data-stu-id="609ba-316">Sales</span></span>    |<span data-ttu-id="609ba-317">銷售原則</span><span class="sxs-lookup"><span data-stu-id="609ba-317">Sales policy</span></span>       | <span data-ttu-id="609ba-318">1</span><span class="sxs-lookup"><span data-stu-id="609ba-318">1</span></span>        |
|<span data-ttu-id="609ba-319">西部地區</span><span class="sxs-lookup"><span data-stu-id="609ba-319">West Region</span></span>     |<span data-ttu-id="609ba-320">西部地區原則</span><span class="sxs-lookup"><span data-stu-id="609ba-320">West Region policy</span></span>         |<span data-ttu-id="609ba-321">2</span><span class="sxs-lookup"><span data-stu-id="609ba-321">2</span></span>         |
|<span data-ttu-id="609ba-322">除以</span><span class="sxs-lookup"><span data-stu-id="609ba-322">Division</span></span>    |<span data-ttu-id="609ba-323">部門原則</span><span class="sxs-lookup"><span data-stu-id="609ba-323">Division policy</span></span>         |<span data-ttu-id="609ba-324">3</span><span class="sxs-lookup"><span data-stu-id="609ba-324">3</span></span>         |
|<span data-ttu-id="609ba-325">附屬</span><span class="sxs-lookup"><span data-stu-id="609ba-325">Subsidiary</span></span>   |<span data-ttu-id="609ba-326">附屬原則</span><span class="sxs-lookup"><span data-stu-id="609ba-326">Subsidiary policy</span></span>        |<span data-ttu-id="609ba-327">4</span><span class="sxs-lookup"><span data-stu-id="609ba-327">4</span></span>         |

<span data-ttu-id="609ba-328">如果我們移除 [西部區域] 群組中的 [西部區域原則]，原則指派與優先順序會更新為以下所示。</span><span class="sxs-lookup"><span data-stu-id="609ba-328">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="609ba-329">組名</span><span class="sxs-lookup"><span data-stu-id="609ba-329">Group name</span></span>  |<span data-ttu-id="609ba-330">原則名稱</span><span class="sxs-lookup"><span data-stu-id="609ba-330">Policy name</span></span>  |<span data-ttu-id="609ba-331">排名</span><span class="sxs-lookup"><span data-stu-id="609ba-331">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="609ba-332">銷售</span><span class="sxs-lookup"><span data-stu-id="609ba-332">Sales</span></span>    |<span data-ttu-id="609ba-333">銷售原則</span><span class="sxs-lookup"><span data-stu-id="609ba-333">Sales policy</span></span>       | <span data-ttu-id="609ba-334">1</span><span class="sxs-lookup"><span data-stu-id="609ba-334">1</span></span>        |
|<span data-ttu-id="609ba-335">除以</span><span class="sxs-lookup"><span data-stu-id="609ba-335">Division</span></span>    |<span data-ttu-id="609ba-336">部門原則</span><span class="sxs-lookup"><span data-stu-id="609ba-336">Division policy</span></span>         |<span data-ttu-id="609ba-337">2</span><span class="sxs-lookup"><span data-stu-id="609ba-337">2</span></span>         |
|<span data-ttu-id="609ba-338">附屬</span><span class="sxs-lookup"><span data-stu-id="609ba-338">Subsidiary</span></span>   |<span data-ttu-id="609ba-339">附屬原則</span><span class="sxs-lookup"><span data-stu-id="609ba-339">Subsidiary policy</span></span>        |<span data-ttu-id="609ba-340">3</span><span class="sxs-lookup"><span data-stu-id="609ba-340">3</span></span>        |

<span data-ttu-id="609ba-341">在這個範例中，我們會從群組中移除團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-341">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="609ba-342">若要深入瞭解，請參閱[移除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="609ba-342">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="609ba-343">變更群組的原則指派</span><span class="sxs-lookup"><span data-stu-id="609ba-343">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="609ba-344">此 ```Set-CsGroupPolicyAssignment``` Cmdlet 即將提供。</span><span class="sxs-lookup"><span data-stu-id="609ba-344">The ```Set-CsGroupPolicyAssignment``` cmdlet will be available soon.</span></span> <span data-ttu-id="609ba-345">在這種情況下，若要變更群組原則指派，您可以從群組中移除目前的原則指派，然後新增指派的原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-345">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="609ba-346">將原則指派給群組之後，您可以使用 ```Set-CsGroupPolicyAssignment``` Cmdlet 來變更該群組的原則指派，如下所示：</span><span class="sxs-lookup"><span data-stu-id="609ba-346">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="609ba-347">變更排名</span><span class="sxs-lookup"><span data-stu-id="609ba-347">Change the ranking</span></span>
- <span data-ttu-id="609ba-348">變更指定原則類型的原則</span><span class="sxs-lookup"><span data-stu-id="609ba-348">Change the policy of a given policy type</span></span>
- <span data-ttu-id="609ba-349">變更指定原則類型和排名的原則</span><span class="sxs-lookup"><span data-stu-id="609ba-349">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="609ba-350">在這個範例中，我們會將群組的小組通話駐留原則給名為 SupportCallPark 的原則，並將作業排名等級設為3。</span><span class="sxs-lookup"><span data-stu-id="609ba-350">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="609ba-351">若要深入瞭解，請參閱[設定 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="609ba-351">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>



#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="609ba-352">變更使用者的有效原則</span><span class="sxs-lookup"><span data-stu-id="609ba-352">Change the effective policy for a user</span></span>

<span data-ttu-id="609ba-353">以下範例說明如何變更直接指派原則的使用者的有效原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-353">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="609ba-354">首先，我們會將 ```Get-CsUserPolicyAssignment``` Cmdlet 與參數搭配使用， ```PolicySource``` 以取得與使用者相關聯之小組會議廣播原則的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="609ba-354">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="609ba-355">若要深入瞭解，請參閱[CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="609ba-355">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="609ba-356">輸出顯示使用者是直接指派給員工事件的小組會議廣播原則，其優先順序高於指派給該使用者所屬群組的「提供者即時事件」原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-356">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="609ba-357">現在，我們移除使用者的員工活動原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-357">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="609ba-358">這表示使用者已不再將團隊會議廣播原則直接指派給他們，並將繼承指派給該使用者所屬群組的供應商即時事件原則。</span><span class="sxs-lookup"><span data-stu-id="609ba-358">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="609ba-359">在商務用 Skype PowerShell 模組中使用下列 Cmdlet 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="609ba-359">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="609ba-360">您可以在團隊 PowerShell 模組中使用下列 Cmdlet，透過批次原則指派來執行這項作業，其中 $users 是您指定的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="609ba-360">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="609ba-361">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-361">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="609ba-362">使用批次原則套件指派，您可以一次將原則套件指派給大型的使用者組，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="609ba-362">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="609ba-363">您可以使用 ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet 來提交一批使用者，以及您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="609ba-363">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="609ba-364">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="609ba-364">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="609ba-365">然後，您就可以使用此 ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="609ba-365">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="609ba-366">您可以依其物件識別碼或會話初始通訊協定（SIP）位址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-366">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="609ba-367">請注意，使用者的 SIP 位址通常會有與使用者主體名稱（UPN）或電子郵件地址相同的值，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="609ba-367">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="609ba-368">如果使用者是使用其 UPN 或電子郵件指定的，但其值不是其 SIP 位址，則使用者的原則指派將會失敗。</span><span class="sxs-lookup"><span data-stu-id="609ba-368">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="609ba-369">如果批次包含重複的使用者，則會在處理前從批次中移除重複專案，且狀態將只提供給批次中剩餘的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-369">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="609ba-370">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-370">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="609ba-371">若要獲得最佳結果，請不要一次提交超過幾個批次。</span><span class="sxs-lookup"><span data-stu-id="609ba-371">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="609ba-372">允許批次完成處理，然後再提交更多批次。</span><span class="sxs-lookup"><span data-stu-id="609ba-372">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="609ba-373">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="609ba-373">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="609ba-374">執行下列動作以安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="609ba-374">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="609ba-375">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="609ba-375">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="609ba-376">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="609ba-376">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="609ba-377">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="609ba-377">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="609ba-378">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="609ba-378">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="609ba-379">在這個範例中，我們使用 ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet 將 Education_PrimaryStudent 原則套件指派給一批使用者。</span><span class="sxs-lookup"><span data-stu-id="609ba-379">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="609ba-380">若要深入瞭解，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="609ba-380">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="609ba-381">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="609ba-381">Get the status of a batch assignment</span></span>

<span data-ttu-id="609ba-382">執行下列操作以取得批次工作的狀態，其中 OperationId 是由 ```New-CsBatchPolicyAssignmentOperation``` Cmdlet 針對指定批次傳回的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="609ba-382">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="609ba-383">如果輸出顯示發生錯誤，請執行下列動作，以取得有關屬性中錯誤的詳細資訊 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="609ba-383">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="609ba-384">若要深入瞭解，請參閱[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="609ba-384">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="609ba-385">相關主題</span><span class="sxs-lookup"><span data-stu-id="609ba-385">Related topics</span></span>

[<span data-ttu-id="609ba-386">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="609ba-386">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
