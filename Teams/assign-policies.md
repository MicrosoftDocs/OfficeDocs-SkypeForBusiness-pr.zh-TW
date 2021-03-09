---
title: 在 Microsoft Teams 中將原則指派給使用者
author: cichur
ms.author: v-cichur
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
description: 瞭解在 Microsoft Teams 中指派策略給使用者的不同方式。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 50d0ddf3da73addde36cb045a3d61eb9a5618e8c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568989"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="35590-103">在 Microsoft Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="35590-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="35590-104">做為系統管理員，您可以使用策略來控制組織中使用者可用的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="35590-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="35590-105">例如，通話政策、會議政策及傳訊策略只是幾個。</span><span class="sxs-lookup"><span data-stu-id="35590-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="35590-106">組織擁有不同類型的使用者，具有獨特的需求。</span><span class="sxs-lookup"><span data-stu-id="35590-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="35590-107">您建立並指派的自訂策略，讓您根據這些需求量身訂做不同的使用者群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="35590-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="35590-108">為了輕鬆管理貴組織內的政策，Teams 提供數種指派策略給使用者的方法。</span><span class="sxs-lookup"><span data-stu-id="35590-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="35590-109">直接指派一個策略給使用者，無論是個別指派或透過批次指派來縮放，或是指派給使用者是成員的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="35590-110">您也可以使用策略套件，為組織中具有類似角色的使用者指派一組預先設定好的政策集合。</span><span class="sxs-lookup"><span data-stu-id="35590-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="35590-111">您選擇的選項取決於您所管理之策略的數量，以及您指派之策略的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="35590-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="35590-112">全域 (全組織的預設) 原則會適用于貴組織中數量最多的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="35590-113">您只需要將策略指派給需要特殊策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="35590-114">本文將說明您可以指派策略給使用者的不同方式，以及使用方法的建議案例。</span><span class="sxs-lookup"><span data-stu-id="35590-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="35590-115">哪一個優先？</span><span class="sxs-lookup"><span data-stu-id="35590-115">Which policy takes precedence?</span></span>

<span data-ttu-id="35590-116">使用者針對每一種政策類型都有一個有效政策。</span><span class="sxs-lookup"><span data-stu-id="35590-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="35590-117">使用者有可能直接被指派一個策略，也是一或多個指派相同類型之策略的群組成員。</span><span class="sxs-lookup"><span data-stu-id="35590-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="35590-118">在這類情況下，哪一個策略會優先？</span><span class="sxs-lookup"><span data-stu-id="35590-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="35590-119">使用者的有效原則是根據優先順序規則決定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="35590-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="35590-120">如果使用者是個別或透過批次指派 (指派，該) 優先。</span><span class="sxs-lookup"><span data-stu-id="35590-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="35590-121">在下列視覺化範例中，使用者的有效政策是直接指派給使用者的長方形會議政策。</span><span class="sxs-lookup"><span data-stu-id="35590-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![顯示直接指派之策略的優先順序圖表](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="35590-123">如果使用者未直接指派指定類型的策略，則指派給使用者為成員之群組的規則會優先。</span><span class="sxs-lookup"><span data-stu-id="35590-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="35590-124">如果使用者是多個群組的成員，則具有指定之策略類型最高群組指派排名[](#group-assignment-ranking)的規則會優先。</span><span class="sxs-lookup"><span data-stu-id="35590-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="35590-125">在此視覺化範例中，使用者的有效原則是 Exec Teams 和 HD 策略，其工作分派排名相對於使用者成員的其他群組最高，而且也會被指派相同政策類型的策略。</span><span class="sxs-lookup"><span data-stu-id="35590-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![圖表顯示繼承自群組之策略的優先順序](media/assign-policies-example-group.png)

<span data-ttu-id="35590-127">如果使用者未直接指派一個策略，或不是任何已指派策略之群組的成員，該使用者會取得該政策類型的全域 (組織) 預設) 策略。</span><span class="sxs-lookup"><span data-stu-id="35590-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="35590-128">以下是視覺化範例。</span><span class="sxs-lookup"><span data-stu-id="35590-128">Here's a visual example.</span></span>

![顯示全域原則如何優先的圖表](media/assign-policies-example-global.png)

<span data-ttu-id="35590-130">若要深入瞭解，請參閱優先順序 [規則](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="35590-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="35590-131">指派政策的方法</span><span class="sxs-lookup"><span data-stu-id="35590-131">Ways to assign policies</span></span>

<span data-ttu-id="35590-132">以下是您可以指派策略給使用者的方法概觀，以及每個使用者的建議案例。</span><span class="sxs-lookup"><span data-stu-id="35590-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="35590-133">選取連結以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="35590-133">Select the links to learn more.</span></span>

<span data-ttu-id="35590-134">在指派原則給個別使用者或群組之前，請從設定全域 [ (全組織](#set-the-global-policies) 的預設) 原則開始，以將原則適用于貴組織中數量最多的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="35590-135">設定全域原則之後，您只需要將策略指派給需要特殊策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="35590-136">請這麼做</span><span class="sxs-lookup"><span data-stu-id="35590-136">Do this</span></span>  |<span data-ttu-id="35590-137">如果。。。</span><span class="sxs-lookup"><span data-stu-id="35590-137">If...</span></span>  | <span data-ttu-id="35590-138">使用。。。</span><span class="sxs-lookup"><span data-stu-id="35590-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="35590-139">指派一個策略給個別使用者</span><span class="sxs-lookup"><span data-stu-id="35590-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="35590-140">您剛開始使用 Teams，或者只需要將一或多個策略指派給少數使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="35590-141">Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="35590-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="35590-142">指派一個策略給群組</span><span class="sxs-lookup"><span data-stu-id="35590-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="35590-143">根據使用者的群組成員資格指派策略。</span><span class="sxs-lookup"><span data-stu-id="35590-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="35590-144">例如，將一個策略指派給安全性群組或通訊群組清單中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="35590-145">Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="35590-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="35590-146">指派一個策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="35590-147">指派策略給大量使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="35590-148">例如，一次指派一個策略給貴組織數百或數千個使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="35590-149">Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="35590-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="35590-150">指派一個策略套件給使用者</span><span class="sxs-lookup"><span data-stu-id="35590-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="35590-151">將多個策略指派給組織中具有相同或類似角色的特定使用者集合。</span><span class="sxs-lookup"><span data-stu-id="35590-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="35590-152">例如，將教育 (教師) 套件指派給您學校的教師，讓他們能完全存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="35590-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="35590-153">將教育 (中學生) 套件指派給中學生，以限制某些功能，例如私人通話。</span><span class="sxs-lookup"><span data-stu-id="35590-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="35590-154">Teams PowerShell 模組中的 Microsoft Teams 系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="35590-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="35590-155">[在私人預覽版中將](#assign-a-policy-package-to-a-group) (套件指派給群組) </span><span class="sxs-lookup"><span data-stu-id="35590-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="35590-156">指派多個策略給貴組織中具有相同或類似角色的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="35590-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="35590-157">例如，將策略套件指派給安全性群組或通訊群組清單中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="35590-158">Microsoft Teams 系統管理中心 (Teams PowerShell 模組) 或 PowerShell Cmdlet 即將推出</span><span class="sxs-lookup"><span data-stu-id="35590-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="35590-159">指派一個策略套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="35590-160">指派多個策略給貴組織中具有相同或類似角色的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="35590-161">例如，使用批次 (指派) 指派給學校的所有教師，讓他們能完全存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="35590-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="35590-162">將教育 (中學生) 套件指派給一批中學生，以限制某些功能，例如私人通話。</span><span class="sxs-lookup"><span data-stu-id="35590-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="35590-163">Teams PowerShell 模組中的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="35590-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="35590-164">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="35590-164">Set the global policies</span></span>

<span data-ttu-id="35590-165">請遵循下列步驟，針對每個 (設定整個組織的預設) 規則。</span><span class="sxs-lookup"><span data-stu-id="35590-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="35590-166">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="35590-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="35590-167">在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要更新之政策類型之政策頁面。</span><span class="sxs-lookup"><span data-stu-id="35590-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="35590-168">例如 **，Teams**  >  **Teams 政策**、**會議**  >  **政策**、**傳訊政策** 或 **語音**  >  **通話政策**。</span><span class="sxs-lookup"><span data-stu-id="35590-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="35590-169">選取 **全域 (整個組織的預設)** 來查看目前的設定。</span><span class="sxs-lookup"><span data-stu-id="35590-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="35590-170">請根據需要更新原則，然後選取 **"Apply"。**</span><span class="sxs-lookup"><span data-stu-id="35590-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="35590-171">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35590-171">Using PowerShell</span></span>

<span data-ttu-id="35590-172">若要使用 PowerShell 設定全域原則，請使用全域識別碼。</span><span class="sxs-lookup"><span data-stu-id="35590-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="35590-173">首先，請從檢查目前的全域原則開始，決定要變更的設定。</span><span class="sxs-lookup"><span data-stu-id="35590-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="35590-174">接下來，請根據需要更新全域原則。</span><span class="sxs-lookup"><span data-stu-id="35590-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="35590-175">您只需要指定要變更之設定的值。</span><span class="sxs-lookup"><span data-stu-id="35590-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="35590-176">指派一個策略給個別使用者</span><span class="sxs-lookup"><span data-stu-id="35590-176">Assign a policy to individual users</span></span>

<span data-ttu-id="35590-177">請遵循下列步驟，將一個策略指派給個別使用者，或一次指派給少數使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="35590-178">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="35590-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="35590-179">若要指派一個策略給使用者：</span><span class="sxs-lookup"><span data-stu-id="35590-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="35590-180">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**，然後選取使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="35590-181">按一下使用者名稱左側以選取使用者，然後選取編輯 **設定**。</span><span class="sxs-lookup"><span data-stu-id="35590-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="35590-182">選取您想要指派原則， **然後選取** Apply。</span><span class="sxs-lookup"><span data-stu-id="35590-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="35590-183">或者，您也可以執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35590-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="35590-184">在 Microsoft Teams 系統管理中心的左側流覽中，前往該政策頁面。</span><span class="sxs-lookup"><span data-stu-id="35590-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="35590-185">按一下該策略名稱的左側，選取您想要指派的策略。</span><span class="sxs-lookup"><span data-stu-id="35590-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="35590-186">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="35590-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="35590-187">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="35590-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="35590-188">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="35590-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="35590-189">當您完成新增使用者時， **請選取應用程式**。</span><span class="sxs-lookup"><span data-stu-id="35590-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="35590-190">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35590-190">Use PowerShell</span></span>

<span data-ttu-id="35590-191">每一種策略類型都有一組自己的 Cmdlet 來管理它。</span><span class="sxs-lookup"><span data-stu-id="35590-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="35590-192">使用 ```Grant-``` 指定之策略類型的 Cmdlet 來指派該策略。</span><span class="sxs-lookup"><span data-stu-id="35590-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="35590-193">例如，使用 ```Grant-CsTeamsMeetingPolicy``` Cmdlet 將 Teams 會議政策指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="35590-194">這些 Cmdlet 包含在 Teams PowerShell 模組中，並記錄在商務用 [Skype Cmdlet 參照中](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="35590-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="35590-195">如果您尚未安裝 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) (，請下載並安裝) ，然後執行下列操作以連結。</span><span class="sxs-lookup"><span data-stu-id="35590-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="35590-196">商務用 Skype Online Connector 目前是最新 Teams PowerShell 模組的一部分。</span><span class="sxs-lookup"><span data-stu-id="35590-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="35590-197">如果您使用的是最新的 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)公開發行，則不需要安裝商務用 Skype Online Connector。</span><span class="sxs-lookup"><span data-stu-id="35590-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="35590-198">在此範例中，我們將名為 Student Meeting Policy 的 Teams 會議政策指派給名為 Reda 的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="35590-199">若要深入瞭解，請閱讀透過 [PowerShell 管理原則](teams-powershell-managing-teams.md#manage-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="35590-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="35590-200">指派一個策略給群組</span><span class="sxs-lookup"><span data-stu-id="35590-200">Assign a policy to a group</span></span>

<span data-ttu-id="35590-201">將策略指派給群組可讓您將策略指派給一組使用者，例如安全性群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="35590-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="35590-202">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="35590-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="35590-203">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="35590-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="35590-204">建議最多 50，000 個使用者群組使用指派至群組的策略，但也會與較大的群組一起使用。</span><span class="sxs-lookup"><span data-stu-id="35590-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="35590-205">當您指派該策略時，該策略會立即指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="35590-206">不過，將策略指派傳播給群組成員會做為背景作業執行，視群組大小不同，可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="35590-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="35590-207">當從群組中取消分配一個策略，或將成員新增到群組或移除群組時，也是如此。</span><span class="sxs-lookup"><span data-stu-id="35590-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="35590-208">群組原則指派只會傳播給群組的直接成員。</span><span class="sxs-lookup"><span data-stu-id="35590-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="35590-209">指派不會傳播到巢式群組的成員。</span><span class="sxs-lookup"><span data-stu-id="35590-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="35590-210">關於將策略指派給群組的需知</span><span class="sxs-lookup"><span data-stu-id="35590-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="35590-211">在您開始使用之前，瞭解優先順序規則和群組指派排名非常重要。</span><span class="sxs-lookup"><span data-stu-id="35590-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="35590-212">優先順序規則</span><span class="sxs-lookup"><span data-stu-id="35590-212">Precedence rules</span></span>

<span data-ttu-id="35590-213">針對給定政策類型，使用者的有效政策會依據下列條件判斷：</span><span class="sxs-lookup"><span data-stu-id="35590-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="35590-214">直接指派給使用者的規則會優先于指派給群組之相同類型的其他任何政策。</span><span class="sxs-lookup"><span data-stu-id="35590-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="35590-215">換句話說，如果使用者直接獲指派指定類型的策略，該使用者不會從群組繼承相同類型之策略。</span><span class="sxs-lookup"><span data-stu-id="35590-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="35590-216">這也表示，如果使用者擁有已直接指派給該使用者之指定類型的策略，您必須從使用者移除該策略，他們才能從群組繼承相同類型之策略。</span><span class="sxs-lookup"><span data-stu-id="35590-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="35590-217">如果使用者未直接指派一個策略，而且它是兩個或多個群組的成員，而且每個群組都有指派給該群組的相同類型之策略，則使用者會繼承排名最高的群組指派之策略。</span><span class="sxs-lookup"><span data-stu-id="35590-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="35590-218">如果使用者不是任何指派原則之群組的成員，該原則類型的全域 (組織預設) 原則會適用于該使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="35590-219">使用者的有效原則會根據這些規則更新：</span><span class="sxs-lookup"><span data-stu-id="35590-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="35590-220">將使用者新加入或移除已指派策略的群組時。</span><span class="sxs-lookup"><span data-stu-id="35590-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="35590-221">系統會從群組中取消分配一個策略。</span><span class="sxs-lookup"><span data-stu-id="35590-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="35590-222">直接指派給使用者的政策會移除。</span><span class="sxs-lookup"><span data-stu-id="35590-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="35590-223">群組作業排名</span><span class="sxs-lookup"><span data-stu-id="35590-223">Group assignment ranking</span></span>

<span data-ttu-id="35590-224">當您將策略指派給群組時，您可以指定群組作業的排名。</span><span class="sxs-lookup"><span data-stu-id="35590-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="35590-225">這是用來判斷如果使用者是兩個或多個群組的成員，且每個群組都獲得相同類型之政策，使用者應繼承為有效政策。</span><span class="sxs-lookup"><span data-stu-id="35590-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="35590-226">群組作業排名相對於其他相同類型的群組作業。</span><span class="sxs-lookup"><span data-stu-id="35590-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="35590-227">例如，如果您要將通話策略指派給兩個群組，將一個作業的排名設定為 1，另一個設定為 2，其中 1 為最高排名。</span><span class="sxs-lookup"><span data-stu-id="35590-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="35590-228">群組工作分派排名指出哪些群組成員資格在繼承方面比其他群組成員資格重要或更相關。</span><span class="sxs-lookup"><span data-stu-id="35590-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="35590-229">例如，您擁有兩個群組：Store Employees 和 Store Managers。</span><span class="sxs-lookup"><span data-stu-id="35590-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="35590-230">這兩個群組會分別指派 Teams 通話政策、Store 員工通話政策與市管理員通話政策。</span><span class="sxs-lookup"><span data-stu-id="35590-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="35590-231">對於同時位於這兩個群組中的商店經理，其經理角色比員工角色更相關，因此指派給市管理群組的通話政策應該具有較高的排名。</span><span class="sxs-lookup"><span data-stu-id="35590-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="35590-232">組</span><span class="sxs-lookup"><span data-stu-id="35590-232">Group</span></span> |<span data-ttu-id="35590-233">Teams 通話政策名稱</span><span class="sxs-lookup"><span data-stu-id="35590-233">Teams calling policy name</span></span>  |<span data-ttu-id="35590-234">排名</span><span class="sxs-lookup"><span data-stu-id="35590-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="35590-235">商店管理員</span><span class="sxs-lookup"><span data-stu-id="35590-235">Store Managers</span></span>   |<span data-ttu-id="35590-236">商店管理員通話政策</span><span class="sxs-lookup"><span data-stu-id="35590-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="35590-237">1</span><span class="sxs-lookup"><span data-stu-id="35590-237">1</span></span>|
|<span data-ttu-id="35590-238">儲存員工</span><span class="sxs-lookup"><span data-stu-id="35590-238">Store Employees</span></span>    |<span data-ttu-id="35590-239">儲存員工通話政策</span><span class="sxs-lookup"><span data-stu-id="35590-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="35590-240">2</span><span class="sxs-lookup"><span data-stu-id="35590-240">2</span></span>|

<span data-ttu-id="35590-241">如果您沒有指定排名，則系統會提供最低排名。</span><span class="sxs-lookup"><span data-stu-id="35590-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="35590-242">在 Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="35590-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="35590-243">目前，使用 Microsoft Teams 系統管理中心將政策指派給群組僅適用于 Teams 通話政策、Teams 通話公園政策、Teams 政策、Teams 即時活動政策、Teams 會議政策及 Teams 傳訊政策。</span><span class="sxs-lookup"><span data-stu-id="35590-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="35590-244">針對其他策略類型，請使用 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="35590-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="35590-245">在 Microsoft Teams 系統管理中心的左側流覽中，前往該政策類型頁面。</span><span class="sxs-lookup"><span data-stu-id="35590-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="35590-246">例如，前往 **會議**  >  **會議政策**。</span><span class="sxs-lookup"><span data-stu-id="35590-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="35590-247">選取 **群組原則工作分派的選項卡** 。</span><span class="sxs-lookup"><span data-stu-id="35590-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="35590-248">選取 **新增群組**，然後在指派群組原則 **窗格中** ，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35590-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="35590-249">搜尋並新增要指派該策略的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="35590-250">設定群組作業的排名。</span><span class="sxs-lookup"><span data-stu-id="35590-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="35590-251">選取您想要指派的策略。</span><span class="sxs-lookup"><span data-stu-id="35590-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="35590-252">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="35590-252">Select **Apply**.</span></span>

<span data-ttu-id="35590-253">若要移除群組原則工作分派，請在策略頁面的群組原則工作分派分頁上，選取群組指派，**然後選取移除**。</span><span class="sxs-lookup"><span data-stu-id="35590-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="35590-254">若要變更群組作業的排名，您首先必須移除群組原則工作分派。</span><span class="sxs-lookup"><span data-stu-id="35590-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="35590-255">然後，按照上述步驟，將策略指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="35590-256">使用 PowerShell 選項</span><span class="sxs-lookup"><span data-stu-id="35590-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="35590-257">目前，並非所有 Teams 策略類型都提供使用 PowerShell 將策略指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="35590-258">請參閱 [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 以尋找支援之政策類型的清單。</span><span class="sxs-lookup"><span data-stu-id="35590-258">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="35590-259">安裝並連接到 Microsoft Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35590-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="35590-260">有關逐步指引，請參閱安裝 Teams [PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="35590-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="35590-261">指派一個策略給一組使用者</span><span class="sxs-lookup"><span data-stu-id="35590-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="35590-262">使用 [New-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 將策略指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-262">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="35590-263">您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。</span><span class="sxs-lookup"><span data-stu-id="35590-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="35590-264">在此範例中，我們將名為零售管理員會議策略的 Teams 會議政策指派給工作分派排名為 1 的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="35590-265">取得群組的策略指派</span><span class="sxs-lookup"><span data-stu-id="35590-265">Get policy assignments for a group</span></span>

<span data-ttu-id="35590-266">使用 [Get-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) 取得指派給群組的所有策略。</span><span class="sxs-lookup"><span data-stu-id="35590-266">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="35590-267">請注意，即使使用群組的 SIP 位址或電子郵件地址來指派策略，群組還是會一直以群組識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="35590-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="35590-268">在此範例中，我們會取回指派給特定群組的所有策略。</span><span class="sxs-lookup"><span data-stu-id="35590-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="35590-269">在此範例中，我們會退回所有指派為 Teams 會議策略的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="35590-270">從群組移除策略</span><span class="sxs-lookup"><span data-stu-id="35590-270">Remove a policy from a group</span></span>

<span data-ttu-id="35590-271">使用 [Remove-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) 從群組移除策略。</span><span class="sxs-lookup"><span data-stu-id="35590-271">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="35590-272">當您從群組移除一個策略時，會更新指派給該群組之相同類型且排名較低的其他政策優先順序。</span><span class="sxs-lookup"><span data-stu-id="35590-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="35590-273">例如，如果您移除排名為 2 的策略，則排名為 3 和 4 的策略會更新以反映其新排名。</span><span class="sxs-lookup"><span data-stu-id="35590-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="35590-274">下列兩個表格顯示此範例。</span><span class="sxs-lookup"><span data-stu-id="35590-274">The following two tables show this example.</span></span>

<span data-ttu-id="35590-275">以下是 Teams 會議政策之政策指派和優先順序的清單。</span><span class="sxs-lookup"><span data-stu-id="35590-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="35590-276">組名</span><span class="sxs-lookup"><span data-stu-id="35590-276">Group name</span></span>  |<span data-ttu-id="35590-277">政策名稱</span><span class="sxs-lookup"><span data-stu-id="35590-277">Policy name</span></span>  |<span data-ttu-id="35590-278">排名</span><span class="sxs-lookup"><span data-stu-id="35590-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="35590-279">銷售</span><span class="sxs-lookup"><span data-stu-id="35590-279">Sales</span></span>    |<span data-ttu-id="35590-280">銷售政策</span><span class="sxs-lookup"><span data-stu-id="35590-280">Sales policy</span></span>       | <span data-ttu-id="35590-281">1</span><span class="sxs-lookup"><span data-stu-id="35590-281">1</span></span>        |
|<span data-ttu-id="35590-282">西部地區</span><span class="sxs-lookup"><span data-stu-id="35590-282">West Region</span></span>     |<span data-ttu-id="35590-283">西部地區政策</span><span class="sxs-lookup"><span data-stu-id="35590-283">West Region policy</span></span>         |<span data-ttu-id="35590-284">2</span><span class="sxs-lookup"><span data-stu-id="35590-284">2</span></span>         |
|<span data-ttu-id="35590-285">劃分</span><span class="sxs-lookup"><span data-stu-id="35590-285">Division</span></span>    |<span data-ttu-id="35590-286">部門政策</span><span class="sxs-lookup"><span data-stu-id="35590-286">Division policy</span></span>         |<span data-ttu-id="35590-287">3</span><span class="sxs-lookup"><span data-stu-id="35590-287">3</span></span>         |
|<span data-ttu-id="35590-288">附屬</span><span class="sxs-lookup"><span data-stu-id="35590-288">Subsidiary</span></span>   |<span data-ttu-id="35590-289">子公司政策</span><span class="sxs-lookup"><span data-stu-id="35590-289">Subsidiary policy</span></span>        |<span data-ttu-id="35590-290">4</span><span class="sxs-lookup"><span data-stu-id="35590-290">4</span></span>         |

<span data-ttu-id="35590-291">如果我們從西部區域群組移除西部區域政策，則政策指派和優先順序會更新如下。</span><span class="sxs-lookup"><span data-stu-id="35590-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="35590-292">組名</span><span class="sxs-lookup"><span data-stu-id="35590-292">Group name</span></span>  |<span data-ttu-id="35590-293">政策名稱</span><span class="sxs-lookup"><span data-stu-id="35590-293">Policy name</span></span>  |<span data-ttu-id="35590-294">排名</span><span class="sxs-lookup"><span data-stu-id="35590-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="35590-295">銷售</span><span class="sxs-lookup"><span data-stu-id="35590-295">Sales</span></span>    |<span data-ttu-id="35590-296">銷售政策</span><span class="sxs-lookup"><span data-stu-id="35590-296">Sales policy</span></span>       | <span data-ttu-id="35590-297">1</span><span class="sxs-lookup"><span data-stu-id="35590-297">1</span></span>        |
|<span data-ttu-id="35590-298">劃分</span><span class="sxs-lookup"><span data-stu-id="35590-298">Division</span></span>    |<span data-ttu-id="35590-299">部門政策</span><span class="sxs-lookup"><span data-stu-id="35590-299">Division policy</span></span>         |<span data-ttu-id="35590-300">2</span><span class="sxs-lookup"><span data-stu-id="35590-300">2</span></span>         |
|<span data-ttu-id="35590-301">附屬</span><span class="sxs-lookup"><span data-stu-id="35590-301">Subsidiary</span></span>   |<span data-ttu-id="35590-302">子公司政策</span><span class="sxs-lookup"><span data-stu-id="35590-302">Subsidiary policy</span></span>        |<span data-ttu-id="35590-303">3</span><span class="sxs-lookup"><span data-stu-id="35590-303">3</span></span>        |

<span data-ttu-id="35590-304">在此範例中，我們會從群組移除 Teams 會議政策。</span><span class="sxs-lookup"><span data-stu-id="35590-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="35590-305">變更群組的策略指派</span><span class="sxs-lookup"><span data-stu-id="35590-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="35590-306">[Set-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)即將推出。</span><span class="sxs-lookup"><span data-stu-id="35590-306">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="35590-307">同時，若要變更群組原則工作分派，您可以移除群組中的目前策略工作分派，然後新增新的策略工作分派。</span><span class="sxs-lookup"><span data-stu-id="35590-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="35590-308">指派群組原則之後，您可以使用 [Set-CsGroupPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) 變更該群組的策略指派，如下所示：</span><span class="sxs-lookup"><span data-stu-id="35590-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="35590-309">變更排名</span><span class="sxs-lookup"><span data-stu-id="35590-309">Change the ranking</span></span>
- <span data-ttu-id="35590-310">變更給定政策類型的策略</span><span class="sxs-lookup"><span data-stu-id="35590-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="35590-311">變更給定政策類型和排名</span><span class="sxs-lookup"><span data-stu-id="35590-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="35590-312">在此範例中，我們將群組的 Teams 通話公園政策變更為名為 SupportCallPark 且作業排名為 3 的策略。</span><span class="sxs-lookup"><span data-stu-id="35590-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="35590-313">變更使用者的有效政策</span><span class="sxs-lookup"><span data-stu-id="35590-313">Change the effective policy for a user</span></span>

<span data-ttu-id="35590-314">以下是如何針對直接指派策略的使用者變更有效原則的範例。</span><span class="sxs-lookup"><span data-stu-id="35590-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="35590-315">首先，我們將 [Get-CsUserPolicyAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) 與參數一起使用，以取得與使用者關聯的 ```PolicySource``` Teams 會議廣播政策詳細資料。</span><span class="sxs-lookup"><span data-stu-id="35590-315">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="35590-316">輸出顯示使用者已直接獲指派名為員工事件的 Teams 會議廣播政策，其優先順序會高於指派給使用者所屬群組的廠商即時事件。</span><span class="sxs-lookup"><span data-stu-id="35590-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="35590-317">現在，我們會從使用者移除員工事件政策。</span><span class="sxs-lookup"><span data-stu-id="35590-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="35590-318">這表示使用者不再有直接指派給他們的 Teams 會議廣播政策，而且會繼承指派給使用者所屬群組的廠商即時事件政策。</span><span class="sxs-lookup"><span data-stu-id="35590-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="35590-319">在商務用 Skype PowerShell 模組中使用下列 Cmdlet 執行此工作。</span><span class="sxs-lookup"><span data-stu-id="35590-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="35590-320">在 Teams PowerShell 模組中，使用下列 Cmdlet 可縮放執行此作業，但批次$users指派，其中 $users 是您指定的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="35590-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="35590-321">指派一個策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="35590-322">使用系統管理中心</span><span class="sxs-lookup"><span data-stu-id="35590-322">Use the admin center</span></span>

<span data-ttu-id="35590-323">若要大量指派一個策略給使用者：</span><span class="sxs-lookup"><span data-stu-id="35590-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="35590-324">在 Microsoft Teams 系統管理中心的左側流覽中，選取 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="35590-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="35590-325">搜尋您想要指派該策略的使用者，或篩選該視圖以顯示您想要的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="35590-326">在 [&#x2713;] (核取方塊) 欄中，選取使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="35590-327">若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。</span><span class="sxs-lookup"><span data-stu-id="35590-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="35590-328">選取 **編輯設定**，進行您想要的變更， **然後選取** Apply。</span><span class="sxs-lookup"><span data-stu-id="35590-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="35590-329">若要查看原則工作分派的狀態，請在選取應用程式以提交原則工作分派後，于使用者頁面頂端的橫幅中，選取 **活動記錄**。</span><span class="sxs-lookup"><span data-stu-id="35590-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="35590-330">或者，在 Microsoft Teams 系統管理中心的左側流覽中，前往儀表板，然後在活動記錄下選取查看 **詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="35590-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="35590-331">活動記錄會顯示過去 30 天內透過 Microsoft Teams 系統管理中心分批指派給超過 20 個使用者的策略指派。</span><span class="sxs-lookup"><span data-stu-id="35590-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="35590-332">若要深入瞭解，請參閱 [在活動記錄中查看您的政策指派](activity-log.md)。</span><span class="sxs-lookup"><span data-stu-id="35590-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="35590-333">使用 PowerShell 方法</span><span class="sxs-lookup"><span data-stu-id="35590-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="35590-334">目前，並非所有 Teams 策略類型都提供使用 PowerShell 的批次策略指派。</span><span class="sxs-lookup"><span data-stu-id="35590-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="35590-335">請參閱 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 以尋找支援原則類型的清單。</span><span class="sxs-lookup"><span data-stu-id="35590-335">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="35590-336">有了批次策略指派，您一次可以將一組大組使用者指派一個策略，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="35590-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="35590-337">您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派原則。</span><span class="sxs-lookup"><span data-stu-id="35590-337">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="35590-338">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="35590-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="35590-339">接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="35590-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="35590-340">根據使用者的物件識別碼或會話初始通訊協定或 SIP (指定) 位址。</span><span class="sxs-lookup"><span data-stu-id="35590-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="35590-341">使用者的 SIP 位址通常與 UPN (或電子郵件地址的使用者主體名稱) 相同，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="35590-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="35590-342">如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者無法指派策略。</span><span class="sxs-lookup"><span data-stu-id="35590-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="35590-343">如果批次包含重複的使用者，則重複專案會先從批次中移除，然後再處理，而狀態只會提供給批次中其餘的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="35590-344">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="35590-345">為獲得最佳結果，請勿一次提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="35590-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="35590-346">在提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="35590-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="35590-347">安裝並連接到 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35590-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="35590-348">執行下列操作以安裝 [Microsoft Teams PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="35590-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="35590-349">請務必安裝版本 1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="35590-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="35590-350">執行下列操作以連接到 Teams 並開始會話。</span><span class="sxs-lookup"><span data-stu-id="35590-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="35590-351">當系統提示您時，請用您的系統管理員認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="35590-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="35590-352">安裝並連接到 Azure AD PowerShell for Graph 模組 (選) </span><span class="sxs-lookup"><span data-stu-id="35590-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="35590-353">如果您尚未下載並安裝 [Azure AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 模組 (如果您尚未) 並連接到 Azure AD，以便您可以取回貴組織的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="35590-353">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="35590-354">執行下列操作以連接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="35590-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="35590-355">當系統提示您時，請以您用來連接到 Teams 的相同系統管理員認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="35590-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="35590-356">指派設定策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="35590-357">在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將名為 HR 應用程式設定原則的應用程式設定原則指派給 Users_ids.文字檔中列出的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="35590-358">在此範例中，我們會連接至 Azure AD 以取回使用者集合，然後將名為新進員工傳訊政策的訊息原則指派給一批使用 SIP 位址指定的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="35590-359">取得批次指派的狀態</span><span class="sxs-lookup"><span data-stu-id="35590-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="35590-360">執行下列操作以取得批次指派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="35590-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="35590-361">如果輸出顯示發生錯誤，請執行下列操作以取得屬性中錯誤的詳細資訊 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="35590-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="35590-362">若要深入瞭解，請參閱[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="35590-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="35590-363">指派一個策略套件給使用者</span><span class="sxs-lookup"><span data-stu-id="35590-363">Assign a policy package to users</span></span>

<span data-ttu-id="35590-364">Teams 中的策略套件是預先定義之策略和策略設定的集合，您可以指派給組織中擁有相同或類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="35590-365">每個策略套件都是以使用者角色為設計，並包含預先定義且支援該角色一般活動之政策設定。</span><span class="sxs-lookup"><span data-stu-id="35590-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="35590-366">一些政策套件範例包括教育 (教師) 套件和醫療保健 (員工) 套件。</span><span class="sxs-lookup"><span data-stu-id="35590-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="35590-367">若要深入瞭解，請參閱在 [Teams 中管理原則套件](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="35590-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="35590-368">指派一個策略套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="35590-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="35590-369">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**，然後選取使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="35590-370">在使用者的頁面上，**選取政策，** 然後在策略套件 **旁，選取\*\*\*\*編輯。**</span><span class="sxs-lookup"><span data-stu-id="35590-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="35590-371">在指派 **策略套件窗格中** ，選取要指派的套件， **然後選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="35590-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="35590-372">指派一個策略套件給多個使用者</span><span class="sxs-lookup"><span data-stu-id="35590-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="35590-373">在 Microsoft Teams 系統管理中心的左側流覽中，前往政策套件，然後按一下套件名稱左側，選取您想要指派的套件。</span><span class="sxs-lookup"><span data-stu-id="35590-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="35590-374">選取 [管理使用者]。</span><span class="sxs-lookup"><span data-stu-id="35590-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="35590-375">在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="35590-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="35590-376">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="35590-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="35590-377">完成新增使用者後， **請選取儲存**。</span><span class="sxs-lookup"><span data-stu-id="35590-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="35590-378">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="35590-378">Assign a policy package to a group</span></span>

<span data-ttu-id="35590-379">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="35590-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="35590-380">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="35590-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="35590-381">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="35590-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="35590-382">建議最多 50，000 個使用者群組將策略套件指派給群組，但也適用于較大的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="35590-383">當您指派策略套件時，該套件會立即指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="35590-384">不過，將策略指派傳播給群組成員會做為背景作業執行，視群組大小不同，可能需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="35590-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="35590-385">當從群組中取消分配一個策略，或將成員新增到群組或移除群組時，也是如此。</span><span class="sxs-lookup"><span data-stu-id="35590-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35590-386">在您開始使用之前，瞭解優先順序規則和群組指派排名[非常重要](#group-assignment-ranking)。 [](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="35590-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="35590-387">請確定您閱讀並瞭解本文稍早所[](#what-you-need-to-know-about-policy-assignment-to-groups)說明的關於將政策指派給群組的需知概念。</span><span class="sxs-lookup"><span data-stu-id="35590-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="35590-388">將政策套件指派給系統管理中心的一組使用者</span><span class="sxs-lookup"><span data-stu-id="35590-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="35590-389">請登出 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="35590-389">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="35590-390">在左側流覽中，前往政策套件頁面。</span><span class="sxs-lookup"><span data-stu-id="35590-390">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="35590-391">選取群組原則工作分派的選項卡。</span><span class="sxs-lookup"><span data-stu-id="35590-391">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="35590-392">選取 **新增群組**，然後在指派策略套件至群組窗格中，執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="35590-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="35590-393">a.</span><span class="sxs-lookup"><span data-stu-id="35590-393">a.</span></span> <span data-ttu-id="35590-394">搜尋並新增要指派策略套件的群組。</span><span class="sxs-lookup"><span data-stu-id="35590-394">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="35590-395">b.</span><span class="sxs-lookup"><span data-stu-id="35590-395">b.</span></span> <span data-ttu-id="35590-396">選取一個策略套件。</span><span class="sxs-lookup"><span data-stu-id="35590-396">Select a policy package.</span></span>

    <span data-ttu-id="35590-397">C。</span><span class="sxs-lookup"><span data-stu-id="35590-397">c.</span></span> <span data-ttu-id="35590-398">設定每個策略類型的排名。</span><span class="sxs-lookup"><span data-stu-id="35590-398">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="35590-399">D。</span><span class="sxs-lookup"><span data-stu-id="35590-399">d.</span></span> <span data-ttu-id="35590-400">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="35590-400">Select **Apply**.</span></span>

    ![顯示群組原則指派](media/group-pkg-assignment.png)

5. <span data-ttu-id="35590-402">若要管理特定政策類型的排名，請流覽至特定政策頁面。</span><span class="sxs-lookup"><span data-stu-id="35590-402">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="35590-403">若要將策略套件重新指派給群組，請先移除群組原則指派。</span><span class="sxs-lookup"><span data-stu-id="35590-403">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="35590-404">然後，按照上述步驟，將策略套件指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-404">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="35590-405">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="35590-405">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="35590-406">取得 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35590-406">Get the Teams PowerShell module</span></span>

<span data-ttu-id="35590-407">有關逐步指引，請參閱安裝 Teams [PowerShell。](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="35590-407">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="35590-408">將策略套件指派給一組使用者</span><span class="sxs-lookup"><span data-stu-id="35590-408">Assign a policy package to a group of users</span></span>

<span data-ttu-id="35590-409">使用 [Grant-CsGroupPolicyPackageAssignment Cmdlet](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) 將策略套件指派給群組。</span><span class="sxs-lookup"><span data-stu-id="35590-409">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="35590-410">您可以使用物件識別碼、SIP 位址或電子郵件地址來指定群組。</span><span class="sxs-lookup"><span data-stu-id="35590-410">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="35590-411">當您指派策略套件時 [，請指定](#group-assignment-ranking) 策略套件中每一種策略類型的群組指派排名。</span><span class="sxs-lookup"><span data-stu-id="35590-411">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="35590-412">在此範例中，我們將 Education_Teacher 策略套件指派給一個群組，其中 TeamsAppSetupPolicy 和 TeamsMeetingBroadcastPolicy 的作業排名為 1，而 TeamsMeetingPolicy 的排名為 2。</span><span class="sxs-lookup"><span data-stu-id="35590-412">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="35590-413">指派一個策略套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-413">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="35590-414">有了批次策略套件指派，您一次可以將一組大組使用者指派一個策略套件，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="35590-414">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="35590-415">您可以使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 提交一批使用者和您想要指派原則套件。</span><span class="sxs-lookup"><span data-stu-id="35590-415">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="35590-416">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="35590-416">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="35590-417">接著，您可以使用 [Get-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="35590-417">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="35590-418">根據使用者的物件識別碼或會話初始通訊協定或 SIP (指定) 位址。</span><span class="sxs-lookup"><span data-stu-id="35590-418">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="35590-419">使用者的 SIP 位址通常與 UPN (或電子郵件地址的使用者主體名稱) 相同，但這不是必要的。</span><span class="sxs-lookup"><span data-stu-id="35590-419">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="35590-420">如果使用者是使用 UPN 或電子郵件指定，但其值與 SIP 位址不同，則使用者無法指派策略。</span><span class="sxs-lookup"><span data-stu-id="35590-420">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="35590-421">如果批次包含重複的使用者，則重複專案會先從批次中移除，然後再處理，而狀態只會提供給批次中其餘的唯一使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-421">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="35590-422">批次最多包含 5，000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-422">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="35590-423">為獲得最佳結果，請勿一次提交多個批次。</span><span class="sxs-lookup"><span data-stu-id="35590-423">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="35590-424">在提交更多批次之前，允許批次完成處理。</span><span class="sxs-lookup"><span data-stu-id="35590-424">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="35590-425">使用 Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35590-425">Use the Teams PowerShell module</span></span>

<span data-ttu-id="35590-426">如果您尚未安裝 Microsoft [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 模組， (執行下列) 。</span><span class="sxs-lookup"><span data-stu-id="35590-426">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="35590-427">請務必安裝版本 1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="35590-427">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="35590-428">執行下列操作以連接到 Teams 並開始會話。</span><span class="sxs-lookup"><span data-stu-id="35590-428">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="35590-429">當系統提示您時，請用您的系統管理員認證來登錄。</span><span class="sxs-lookup"><span data-stu-id="35590-429">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="35590-430">指派策略套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="35590-430">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="35590-431">在此範例中，我們使用 [New-CsBatchPolicyAssignmentOperation Cmdlet](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 將 Education_PrimaryStudent 原則套件指派給一批使用者。</span><span class="sxs-lookup"><span data-stu-id="35590-431">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="35590-432">查看批次指派的狀態</span><span class="sxs-lookup"><span data-stu-id="35590-432">See the status of a batch assignment</span></span>

<span data-ttu-id="35590-433">執行下列操作以取得批次指派的狀態，其中 OperationId 是 Cmdlet 針對指定批次所返回 ```New-CsBatchPolicyAssignmentOperation``` 的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="35590-433">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="35590-434">如果輸出顯示發生錯誤，請執行下列操作以取得屬性中錯誤的詳細資訊 ```UserState``` 。</span><span class="sxs-lookup"><span data-stu-id="35590-434">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="35590-435">若要深入瞭解，請參閱[Get-CsBatchPolicyAssignmentOperation。](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="35590-435">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="35590-436">相關主題</span><span class="sxs-lookup"><span data-stu-id="35590-436">Related topics</span></span>

[<span data-ttu-id="35590-437">Teams PowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="35590-437">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
