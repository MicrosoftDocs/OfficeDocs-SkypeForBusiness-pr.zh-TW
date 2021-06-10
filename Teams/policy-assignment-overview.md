---
title: 在 Teams
author: KarliStites
ms.author: kastites
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
description: 瞭解在 Microsoft Teams 中將策略和策略套件指派給使用者和群組的不同Microsoft Teams。
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 00f78b3b134c6741a89c0d7b3f43d32a11c182cc
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574302"
---
# <a name="assign-policies-in-teams--getting-started"></a><span data-ttu-id="2673e-103">在 Teams 中指派Teams – 開始使用</span><span class="sxs-lookup"><span data-stu-id="2673e-103">Assign policies in Teams – getting started</span></span>

<span data-ttu-id="2673e-104">做為系統管理員，您可以使用Teams，控制貴組織使用者可使用的功能。</span><span class="sxs-lookup"><span data-stu-id="2673e-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="2673e-105">例如，有通話策略、會議策略和傳訊策略，僅舉幾例。</span><span class="sxs-lookup"><span data-stu-id="2673e-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="2673e-106">組織有不同類型的使用者，具有獨特的需求。</span><span class="sxs-lookup"><span data-stu-id="2673e-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="2673e-107">您建立及指派的自訂策略，讓您根據這些需求，為不同的使用者量身訂做策略設定。</span><span class="sxs-lookup"><span data-stu-id="2673e-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="2673e-108">若要輕鬆管理貴組織的政策，Teams提供數種指派策略給使用者的方法。</span><span class="sxs-lookup"><span data-stu-id="2673e-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="2673e-109">直接指派一個策略給使用者，無論是個別指派，或是透過批次工作分派來縮放，或是指派給使用者是成員的群組。</span><span class="sxs-lookup"><span data-stu-id="2673e-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="2673e-110">您也可以使用策略套件，為組織中具有類似角色的使用者指派一組預先設定的策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="2673e-111">您選擇的選項取決於您管理的策略數量，以及您指派策略的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="2673e-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="2673e-112">全域 (全組織的預設) 原則會適用于貴組織中人數最多的使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="2673e-113">您只需要將策略指派給需要特殊策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="2673e-114">本文將說明您可以指派策略給使用者的不同方式，以及使用方法的建議案例。</span><span class="sxs-lookup"><span data-stu-id="2673e-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

<span data-ttu-id="2673e-115">若要瞭解如何指派策略 **給使用者** 和群組的詳細資訊，請參閱 [指派策略給使用者和群組](assign-policies-users-and-groups.md)。</span><span class="sxs-lookup"><span data-stu-id="2673e-115">For details on how to **assign policies to users and groups**, see [assigning policies to users and groups](assign-policies-users-and-groups.md).</span></span> <span data-ttu-id="2673e-116">若要瞭解如何指派策略 **套件的詳細資訊，** 請參閱 [指派策略套件](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="2673e-116">For details on how to **assign policy packages**, see [assign policy packages](assign-policy-packages.md).</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="2673e-117">哪一個策略優先？</span><span class="sxs-lookup"><span data-stu-id="2673e-117">Which policy takes precedence?</span></span>

<span data-ttu-id="2673e-118">使用者針對每個策略類型有一個有效原則。</span><span class="sxs-lookup"><span data-stu-id="2673e-118">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="2673e-119">使用者有可能或甚至有可能被直接指派一個策略，而且也是指派相同類型之策略的一或多個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2673e-119">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="2673e-120">在這類情況下，哪一個策略會優先？</span><span class="sxs-lookup"><span data-stu-id="2673e-120">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="2673e-121">使用者的有效原則是根據優先順序規則所決定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="2673e-121">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="2673e-122">如果使用者是個別或透過批次指派 (指派給使用者，該) 優先。</span><span class="sxs-lookup"><span data-stu-id="2673e-122">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="2673e-123">在下列視覺化範例中，使用者的有效政策是直接指派給使用者的林肯平方會議政策。</span><span class="sxs-lookup"><span data-stu-id="2673e-123">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![顯示直接指派之策略優先順序的圖表](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="2673e-125">如果使用者未直接指派指定類型之策略，則指派給該使用者為成員之群組的策略會優先使用。</span><span class="sxs-lookup"><span data-stu-id="2673e-125">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="2673e-126">如果使用者是多個群組的成員，則針對指定 (指派排名) 優先順序最高的策略優先。 [](assign-policies-users-and-groups.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="2673e-126">If a user is a member of multiple groups, the policy that has the highest ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for the given policy type takes precedence.</span></span>

<span data-ttu-id="2673e-127">在此視覺化範例中，使用者的有效原則是 Exec Teams 和 HD 策略，其指派排名相對於使用者是成員之其他群組最高，而且也會指派相同策略類型的策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-127">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![顯示從群組繼承之策略的優先順序圖表](media/assign-policies-example-group.png)

<span data-ttu-id="2673e-129">如果使用者未直接指派策略，或不是任何指派策略之群組的成員，該使用者會取得該策略類型的全域 (組織) 預設) 策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-129">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="2673e-130">以下是一個視覺化範例。</span><span class="sxs-lookup"><span data-stu-id="2673e-130">Here's a visual example.</span></span>

![顯示全域原則如何優先的圖表](media/assign-policies-example-global.png)

<span data-ttu-id="2673e-132">若要深入瞭解，請參閱 ([優先順序) 。](assign-policies-users-and-groups.md#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="2673e-132">To learn more, see ([Precedence rules](assign-policies-users-and-groups.md#precedence-rules)).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="2673e-133">指派策略的方法</span><span class="sxs-lookup"><span data-stu-id="2673e-133">Ways to assign policies</span></span>

<span data-ttu-id="2673e-134">以下概述您可以指派策略給使用者的方式，以及每個使用者的建議案例。</span><span class="sxs-lookup"><span data-stu-id="2673e-134">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="2673e-135">選取連結以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="2673e-135">Select the links to learn more.</span></span>

<span data-ttu-id="2673e-136">在將原則指派給個別使用者或群組之前，首先請設定全域 (組織) 預設 [) 原則](#set-the-global-policies) ，讓原則適用于貴組織中人數最多的使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-136">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="2673e-137">設定全域原則之後，您只需要將策略指派給需要特殊策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-137">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="2673e-138">執行此</span><span class="sxs-lookup"><span data-stu-id="2673e-138">Do this</span></span>  |<span data-ttu-id="2673e-139">如果。。。</span><span class="sxs-lookup"><span data-stu-id="2673e-139">If...</span></span>  | <span data-ttu-id="2673e-140">使用。。。</span><span class="sxs-lookup"><span data-stu-id="2673e-140">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="2673e-141">指派策略給個別使用者</span><span class="sxs-lookup"><span data-stu-id="2673e-141">Assign a policy to individual users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)   | <span data-ttu-id="2673e-142">您剛開始使用Teams才剛開始使用，或者您只需要指派一或多個策略給少數使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-142">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="2673e-143">PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2673e-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="2673e-144">將策略指派給群組</span><span class="sxs-lookup"><span data-stu-id="2673e-144">Assign a policy to a group</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-group) |<span data-ttu-id="2673e-145">根據使用者的群組成員資格指派策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-145">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="2673e-146">例如，將策略指派給安全性群組或通訊群組清單中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-146">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="2673e-147">PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2673e-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="2673e-148">指派一個策略給一批使用者</span><span class="sxs-lookup"><span data-stu-id="2673e-148">Assign a policy to a batch of users</span></span>](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="2673e-149">指派策略給大量使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-149">Assign policies to large sets of users.</span></span> <span data-ttu-id="2673e-150">例如，一次指派一個策略給貴組織中數百或數千個使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-150">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="2673e-151">PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2673e-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="2673e-152">指派策略套件給使用者</span><span class="sxs-lookup"><span data-stu-id="2673e-152">Assign a policy package to users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-users)  |<span data-ttu-id="2673e-153">為貴組織中具有相同或類似角色的特定使用者組指派多個策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-153">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="2673e-154">例如，將教育 (教師) 方案套件指派給學校的教師，讓他們能完全存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="2673e-154">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="2673e-155">將教育 (中) 方案套件指派給中學生，以限制某些功能，例如私人通話。</span><span class="sxs-lookup"><span data-stu-id="2673e-155">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="2673e-156">PowerShell Microsoft Teams中的系統管理中心或 PowerShell Teams Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2673e-156">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="2673e-157">[在私人預覽中將](assign-policy-packages.md#assign-a-policy-package-to-a-group) (套件指派給群組) </span><span class="sxs-lookup"><span data-stu-id="2673e-157">[Assign a policy package to a group](assign-policy-packages.md#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="2673e-158">將多個策略指派給貴組織中具有相同或類似角色的一組使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-158">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="2673e-159">例如，將策略套件指派給安全性群組或通訊群組清單中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-159">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="2673e-160">系統Microsoft Teams系統管理中心 (PowerShell 模組) PowerShell Cmdlet 即將推出Teams Cmdlet</span><span class="sxs-lookup"><span data-stu-id="2673e-160">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="2673e-161">將策略套件指派給一批使用者</span><span class="sxs-lookup"><span data-stu-id="2673e-161">Assign a policy package to a batch of users</span></span>](assign-policy-packages.md#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="2673e-162">將多個策略指派給貴組織中具有相同或類似角色的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="2673e-162">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="2673e-163">例如，使用批次作業將 (教師) 教師策略套件指派給學校的所有教師，讓他們能完全存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="2673e-163">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="2673e-164">將教育 (中學生) 套件指派給一批中學生，以限制某些功能，例如私人通話。</span><span class="sxs-lookup"><span data-stu-id="2673e-164">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="2673e-165">PowerShell 模組中的 PowerShell Cmdlet Teams PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="2673e-165">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="2673e-166">設定全域原則</span><span class="sxs-lookup"><span data-stu-id="2673e-166">Set the global policies</span></span>

<span data-ttu-id="2673e-167">請遵循下列步驟，針對每個 (設定整個組織的預設) 策略。</span><span class="sxs-lookup"><span data-stu-id="2673e-167">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="2673e-168">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="2673e-168">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="2673e-169">在系統管理中心的左側導Microsoft Teams，請前往您想要更新之策略類型的政策頁面。</span><span class="sxs-lookup"><span data-stu-id="2673e-169">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="2673e-170">例如 **，Teams Teams、**  >  \*\*\*\*\*\*會議\*\*  >  **政策**、**傳** 訊政策或 **語音**  >  **通話政策**。</span><span class="sxs-lookup"><span data-stu-id="2673e-170">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="2673e-171">選取全域 **(全組織的預設)** 來查看目前的設定。</span><span class="sxs-lookup"><span data-stu-id="2673e-171">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="2673e-172">請根據需要更新原則， **然後選取** Apply 。</span><span class="sxs-lookup"><span data-stu-id="2673e-172">Update the policy as needed, and then select **Apply**.</span></span>

![更新系統管理中心Teams全域原則](media/assign-globalpolicy.png)

### <a name="using-powershell"></a><span data-ttu-id="2673e-174">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="2673e-174">Using PowerShell</span></span>

<span data-ttu-id="2673e-175">若要使用 PowerShell 設定全域原則，請使用全域識別碼。</span><span class="sxs-lookup"><span data-stu-id="2673e-175">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="2673e-176">首先，請審查目前的全域原則，決定要變更的設定。</span><span class="sxs-lookup"><span data-stu-id="2673e-176">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="2673e-177">接下來，請根據需要更新全域原則。</span><span class="sxs-lookup"><span data-stu-id="2673e-177">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="2673e-178">您只需要為要變更的設定指定值。</span><span class="sxs-lookup"><span data-stu-id="2673e-178">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="view-your-policy-assignments-in-the-activity-log"></a><span data-ttu-id="2673e-179">在活動記錄中查看您的策略指派</span><span class="sxs-lookup"><span data-stu-id="2673e-179">View your policy assignments in the Activity log</span></span>

<span data-ttu-id="2673e-180">當您在系統管理中心指派Microsoft Teams，您可以在活動記錄中查看那些策略指派的狀態。</span><span class="sxs-lookup"><span data-stu-id="2673e-180">When you assign policies to users in the Microsoft Teams admin center, you can view the status of those policy assignments in the Activity log.</span></span> <span data-ttu-id="2673e-181">活動記錄會顯示過去 30 天內透過系統管理中心Microsoft Teams超過 20 個使用者批次的策略指派。</span><span class="sxs-lookup"><span data-stu-id="2673e-181">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="2673e-182">請記住，活動記錄不會顯示策略套件指派、透過 Microsoft Teams 系統管理中心將策略指派給少於 20 位使用者的批次，或透過 PowerShell 進行策略指派。</span><span class="sxs-lookup"><span data-stu-id="2673e-182">Keep in mind that the Activity log doesn't show policy package assignments, policy assignments to batches of less than 20 users through the Microsoft Teams admin center, or policy assignments through PowerShell.</span></span>

![活動記錄頁面的螢幕擷取畫面](media/activity-log.png)

## <a name="view-your-policy-assignment-activities-in-the-activity-log"></a><span data-ttu-id="2673e-184">在活動記錄中查看您的策略作業活動</span><span class="sxs-lookup"><span data-stu-id="2673e-184">View your policy assignment activities in the Activity log</span></span>

<span data-ttu-id="2673e-185">若要在活動記錄中查看您的策略指派：</span><span class="sxs-lookup"><span data-stu-id="2673e-185">To view your policy assignments in the Activity log:</span></span>

1. <span data-ttu-id="2673e-186">在系統管理中心的左側導Microsoft Teams，前往 **儀表板，然後在** 活動記錄 **下，選取** 查看 **詳細資料**。</span><span class="sxs-lookup"><span data-stu-id="2673e-186">In the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity Log**, select **View details**.</span></span>
2. <span data-ttu-id="2673e-187">您可以查看所有策略指派，或根據狀態篩選清單，只顯示尚未開始、進行中或 **已完成的作業**。 </span><span class="sxs-lookup"><span data-stu-id="2673e-187">You can view all policy assignments or filter the list by status to show only assignments that are **Not started**, **In progress**, or **Completed**.</span></span> <span data-ttu-id="2673e-188">您會看到每個作業的下列資訊：</span><span class="sxs-lookup"><span data-stu-id="2673e-188">You'll see the following information about each assignment:</span></span>
    - <span data-ttu-id="2673e-189">**名稱**：策略指派的名稱。</span><span class="sxs-lookup"><span data-stu-id="2673e-189">**Name**: The name of the policy assignment.</span></span> <span data-ttu-id="2673e-190">按一下連結以查看更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2673e-190">Click the link to view more details.</span></span> <span data-ttu-id="2673e-191">這包括已指派策略的使用者數目，以及已完成、進行中及尚未開始的指派數目。</span><span class="sxs-lookup"><span data-stu-id="2673e-191">This includes the number of users the policy was assigned to and the number of assignments completed, in progress, and not started.</span></span> <span data-ttu-id="2673e-192">您也會看到批次中的使用者清單，以及每個使用者的狀態和結果。</span><span class="sxs-lookup"><span data-stu-id="2673e-192">You'll also see the list of users in the batch, and the status and result for each user.</span></span> <span data-ttu-id="2673e-193">以下是範例：</span><span class="sxs-lookup"><span data-stu-id="2673e-193">Here's an example:</span></span>

        ![螢幕擷取畫面](media/activity-log-policy-assignment-detail.png)

    - <span data-ttu-id="2673e-195">**提交日期**：已提交政策分派的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="2673e-195">**Submitted**: Date and time the policy assignment was submitted.</span></span>
    - <span data-ttu-id="2673e-196">**完成時間**：完成策略作業的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="2673e-196">**Completion time**: Date and time the policy assignment was completed.</span></span>
    - <span data-ttu-id="2673e-197">**影響：** 批次中的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="2673e-197">**Impact on**: Number of users in the batch.</span></span>
    - <span data-ttu-id="2673e-198">**整體狀態**：策略工作分派的狀態。</span><span class="sxs-lookup"><span data-stu-id="2673e-198">**Overall status**: Status of the policy assignment.</span></span>

> [!NOTE]
> <span data-ttu-id="2673e-199">您也可以從使用者頁面取得 **活動記錄。**</span><span class="sxs-lookup"><span data-stu-id="2673e-199">You can also get to the Activity log from the **Users** page.</span></span> <span data-ttu-id="2673e-200">按一下 [ **申請** 以提交大量原則作業後，就會在頁面頂端看到橫幅。</span><span class="sxs-lookup"><span data-stu-id="2673e-200">After you click **Apply** to submit a bulk policy assignment, you'll see a banner at the top of the page.</span></span> <span data-ttu-id="2673e-201">按一下 **橫幅中的** [活動記錄連結。</span><span class="sxs-lookup"><span data-stu-id="2673e-201">Click the **Activity log** link in the banner.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2673e-202">相關主題</span><span class="sxs-lookup"><span data-stu-id="2673e-202">Related topics</span></span>

- [<span data-ttu-id="2673e-203">指派策略給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="2673e-203">Assign policies to users and groups</span></span>](assign-policies-users-and-groups.md)
- [<span data-ttu-id="2673e-204">指派策略套件給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="2673e-204">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="2673e-205">使用Teams管理</span><span class="sxs-lookup"><span data-stu-id="2673e-205">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="2673e-206">TeamsPowerShell 概觀</span><span class="sxs-lookup"><span data-stu-id="2673e-206">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)