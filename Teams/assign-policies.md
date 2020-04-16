---
title: 在 Microsoft Teams 中將原則指派給使用者
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
f1keywords: ''
ms.openlocfilehash: 5c46b74519520950d31f01d4c86ae2a5002ae279
ms.sourcegitcommit: df4dde0fe6ce9e26cb4b3da4e4b878538d31decc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2020
ms.locfileid: "43521619"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="6446a-103">在 Microsoft Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="6446a-104">**本文中討論的其中一個 Microsoft 團隊功能，目前只有私人預覽提供的[原則指派給群組](#assign-a-policy-to-a-group)。此功能的 Powershell Cmdlet 位於預發行團隊 PowerShell 模組中。**</span><span class="sxs-lookup"><span data-stu-id="6446a-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="6446a-105">若要掌握此功能的發行狀態，請參閱[Microsoft 365 藍圖](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)。</span><span class="sxs-lookup"><span data-stu-id="6446a-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="6446a-106">身為系統管理員，您可以使用原則來控制貴組織中的使用者可以使用的小組功能。</span><span class="sxs-lookup"><span data-stu-id="6446a-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="6446a-107">例如，有一些通話原則、會議原則和訊息原則，只會為您命名。</span><span class="sxs-lookup"><span data-stu-id="6446a-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="6446a-108">組織擁有不同類型的使用者，而且您可以建立並指派您所建立及指派的規則，讓您根據這些需求，將原則設定量身定制給不同的使用者組。</span><span class="sxs-lookup"><span data-stu-id="6446a-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="6446a-109">為了讓您更容易管理貴組織中的原則，小組提供了幾種指派原則給使用者的方法。</span><span class="sxs-lookup"><span data-stu-id="6446a-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="6446a-110">您可以將原則直接指派給使用者、個別或在批次作業中縮放，或指派給使用者所屬的群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="6446a-111">您也可以使用 [原則套件]，將預設的原則集合指派給組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="6446a-112">您選擇的選項取決於您所管理的原則數量，以及您要指派的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="6446a-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="6446a-113">本文說明您可以將原則指派給使用者的不同方式，以及使用方式的建議案例。</span><span class="sxs-lookup"><span data-stu-id="6446a-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="6446a-114">優先使用哪種原則？</span><span class="sxs-lookup"><span data-stu-id="6446a-114">Which policy takes precedence?</span></span>

<span data-ttu-id="6446a-115">使用者針對每種原則類型都有一個有效原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="6446a-116">您可能也有可能是使用者直接指派了原則，也是指派了相同類型之原則之一或多個群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6446a-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="6446a-117">在這種情況下，哪個原則優先？</span><span class="sxs-lookup"><span data-stu-id="6446a-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="6446a-118">根據優先順序規則來決定使用者的有效原則，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6446a-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="6446a-119">如果使用者是直接指派原則（個別或透過批次工作指派），則該原則會優先取得優先順序。</span><span class="sxs-lookup"><span data-stu-id="6446a-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6446a-120">在下列範例中，使用者的有效原則是 Lincoln 方形會議原則，可直接指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![顯示直接指派的原則優先的圖表](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="6446a-122">如果使用者未直接指派指定類型的原則，則指派給該使用者所屬群組的原則優先。</span><span class="sxs-lookup"><span data-stu-id="6446a-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="6446a-123">如果使用者是多個群組的成員，則具有指定原則類型之最高[群組指派排名](#group-assignment-ranking)的原則優先。</span><span class="sxs-lookup"><span data-stu-id="6446a-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="6446a-124">在這個範例中，使用者的有效原則是 Exec 小組和 HD 原則，其指派優先順序最高為與使用者所屬的其他群組相關，而且也指派有相同原則類型的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![圖表顯示如何從群組繼承原則優先](media/assign-policies-example-group.png)

<span data-ttu-id="6446a-126">如果使用者未直接指派原則，或是不是指派策略的任何群組的成員，使用者就會取得該原則類型的全域（組織範圍預設值）原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="6446a-127">以下是範例。</span><span class="sxs-lookup"><span data-stu-id="6446a-127">Here's an example.</span></span>

![圖表顯示全域原則優先的方式](media/assign-policies-example-global.png)

<span data-ttu-id="6446a-129">若要深入瞭解，請參閱[優先順序規則](#precedence-rules)。</span><span class="sxs-lookup"><span data-stu-id="6446a-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="6446a-130">指派原則的方法</span><span class="sxs-lookup"><span data-stu-id="6446a-130">Ways to assign policies</span></span>

<span data-ttu-id="6446a-131">以下是您可以將原則指派給使用者的方式，以及每個方案的建議案例的概覽。</span><span class="sxs-lookup"><span data-stu-id="6446a-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="6446a-132">按一下連結以深入瞭解。</span><span class="sxs-lookup"><span data-stu-id="6446a-132">Click the links to learn more.</span></span>

|<span data-ttu-id="6446a-133">請這麼做</span><span class="sxs-lookup"><span data-stu-id="6446a-133">Do this</span></span>  |<span data-ttu-id="6446a-134">If .。。</span><span class="sxs-lookup"><span data-stu-id="6446a-134">If...</span></span>  | <span data-ttu-id="6446a-135">使用 .。。</span><span class="sxs-lookup"><span data-stu-id="6446a-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="6446a-136">指派原則給個別使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="6446a-137">您是團隊新手，剛開始使用，或只需要指派一或幾個原則給少數使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="6446a-138">商務用 Skype Online PowerShell 模組中的 Microsoft 團隊管理員中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6446a-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="6446a-139">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="6446a-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="6446a-140">您需要將多個原則指派給貴組織中擁有相同或相似角色的特定使用者組。</span><span class="sxs-lookup"><span data-stu-id="6446a-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6446a-141">例如，將教育版（教師）原則套件指派給學校的教師，讓他們能完全存取聊天、通話及會議，以及將教育（次要學校學生）原則封裝到次要學生，以限制私人電話等特定功能。</span><span class="sxs-lookup"><span data-stu-id="6446a-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="6446a-142">團隊 PowerShell 模組中的 Microsoft 團隊系統管理中心或 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6446a-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="6446a-143">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="6446a-144">您必須將原則指派給大型使用者組。</span><span class="sxs-lookup"><span data-stu-id="6446a-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="6446a-145">例如，您想要一次將原則指派給組織中的成百上千位使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="6446a-146">團隊 PowerShell 模組中的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6446a-146">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="6446a-147">[將原則指派給群組](#assign-a-policy-to-a-group)（在預覽中）</span><span class="sxs-lookup"><span data-stu-id="6446a-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="6446a-148">您必須根據使用者的群組成員資格指派原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="6446a-149">例如，您想要將原則指派給安全性群組或組織單位中的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="6446a-150">團隊 PowerShell 模組中的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6446a-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="6446a-151">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="6446a-152">您需要將多個原則指派給組織中擁有相同或相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6446a-153">例如，您可以使用批次作業將教育版（教師）原則套件指派給學校中的所有教師，讓他們能完全存取聊天、通話及會議，並將教育（次要學校學生）原則套件指派給一批次要學生，以限制私人通話等特定功能。</span><span class="sxs-lookup"><span data-stu-id="6446a-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="6446a-154">團隊 PowerShell 模組中的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6446a-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="6446a-155">將原則套件指派給群組（即將推出）</span><span class="sxs-lookup"><span data-stu-id="6446a-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="6446a-156">指派原則給個別使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-156">Assign a policy to individual users</span></span>

<span data-ttu-id="6446a-157">請按照下列步驟，將原則指派給個別的使用者或一次少數的使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6446a-158">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="6446a-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="6446a-159">若要將原則指派給使用者：</span><span class="sxs-lookup"><span data-stu-id="6446a-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="6446a-160">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="6446a-161">按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6446a-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="6446a-162">選取您要指派的原則，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="6446a-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="6446a-163">若要一次指派一項原則給20位使用者，請參閱[大量編輯團隊使用者設定](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="6446a-163">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="6446a-164">或者，您也可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6446a-164">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6446a-165">在 Microsoft 團隊系統管理中心的左導覽中，移至 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6446a-165">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="6446a-166">按一下原則名稱左邊的，選取您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-166">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6446a-167">選取 [管理使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6446a-167">Select **Manage users**.</span></span>
4. <span data-ttu-id="6446a-168">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="6446a-168">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6446a-169">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="6446a-169">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6446a-170">完成新增使用者後，請選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="6446a-170">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6446a-171">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="6446a-171">Using PowerShell</span></span>

<span data-ttu-id="6446a-172">每個原則類型都有自己的一組用來管理的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6446a-172">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="6446a-173">使用指定```Grant-```原則類型的 Cmdlet 來指派原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-173">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="6446a-174">例如，使用```Grant-CsTeamsMeetingPolicy``` Cmdlet 將團隊會議原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-174">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="6446a-175">這些 Cmdlet 包含在商務用 Skype Online PowerShell 模組中，且已記錄在[商務用 skype Cmdlet 參考](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)中。</span><span class="sxs-lookup"><span data-stu-id="6446a-175">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="6446a-176">下載並安裝[商務用 Skype Online PowerShell 模組](https://www.microsoft.com/en-us/download/details.aspx?id=39366)（如果您尚未這麼做），然後執行下列動作以連線至商務用 skype online 並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="6446a-176">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="6446a-177">在這個範例中，我們會將名為 Student 會議原則的小組會議原則指派給名為 Reda 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-177">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="6446a-178">若要深入瞭解，請參閱透過[PowerShell 管理原則](teams-powershell-overview.md#managing-policies-via-powershell)。</span><span class="sxs-lookup"><span data-stu-id="6446a-178">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="6446a-179">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="6446a-179">Assign a policy package</span></span>

<span data-ttu-id="6446a-180">小組中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在貴組織中擁有相同或相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-180">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="6446a-181">每個原則套件都是圍繞使用者角色來設計，其中包含支援該角色典型活動的預先定義原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6446a-181">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="6446a-182">策略套件的一些範例是教育版（教師）套件和醫療保健（臨床工作者）封裝。</span><span class="sxs-lookup"><span data-stu-id="6446a-182">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="6446a-183">當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中每個原則的設定，以符合使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="6446a-183">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="6446a-184">若要深入瞭解原則套件，包括如何指派及管理它們的逐步指導方針，請參閱[管理團隊中的原則套件](manage-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="6446a-184">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6446a-185">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-185">Assign a policy to a batch of users</span></span>
 
<span data-ttu-id="6446a-186">使用批次原則指派，您可以一次將原則指派給大型的使用者組，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="6446a-186">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="6446a-187">您可以使用```New-CsBatchPolicyAssignmentOperationd``` Cmdlet 來提交一批使用者和您要指派的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-187">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="6446a-188">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="6446a-188">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="6446a-189">然後，您就可以```Get-CsBatchPolicyAssignmentOperation```使用此 Cmdlet 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="6446a-189">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="6446a-190">批次最多可包含20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-190">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="6446a-191">您可以依物件識別碼、使用者主體名稱（UPN）、會話初始通訊協定（SIP）位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-191">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6446a-192">我們目前建議您逐一指派原則，以批次5000使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-192">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="6446a-193">在這些時間增加需求期間，您可能會遇到處理時間的延遲。</span><span class="sxs-lookup"><span data-stu-id="6446a-193">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="6446a-194">為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。</span><span class="sxs-lookup"><span data-stu-id="6446a-194">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="6446a-195">在一般的商務時間以外提交批次也會有所説明。</span><span class="sxs-lookup"><span data-stu-id="6446a-195">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="6446a-196">目前，所有團隊原則類型都無法使用批次原則分派。</span><span class="sxs-lookup"><span data-stu-id="6446a-196">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="6446a-197">如需支援的原則類型清單，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 。</span><span class="sxs-lookup"><span data-stu-id="6446a-197">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6446a-198">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="6446a-198">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6446a-199">請執行下列動作來安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)。</span><span class="sxs-lookup"><span data-stu-id="6446a-199">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="6446a-200">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6446a-200">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6446a-201">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="6446a-201">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6446a-202">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="6446a-202">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="6446a-203">安裝並連接至 Azure AD PowerShell for Graph 模組（選用）</span><span class="sxs-lookup"><span data-stu-id="6446a-203">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="6446a-204">您可能也想要[下載並安裝適用于圖形模組的 AZURE AD PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （如果您尚未這麼做）並聯機至 azure ad，以便在您的組織中取得使用者清單。</span><span class="sxs-lookup"><span data-stu-id="6446a-204">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="6446a-205">執行下列動作以連線至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6446a-205">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="6446a-206">出現提示時，請使用您用來連線至團隊的相同管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="6446a-206">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6446a-207">指派原則給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-207">Assign a policy to a batch of users</span></span>

<span data-ttu-id="6446a-208">在這個範例中，我們會```New-CsBatchPolicyAssignmentOperation```使用 Cmdlet，將名為 HR App 設定原則的 app 設定原則指派給 Users_ids 文字檔中所列的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-208">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="6446a-209">在這個範例中，我們會連線至 Azure AD 以取得使用者集合，然後將名為「新員工訊息」的訊息策略指派給使用其 Upn 指定的一批使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-209">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="6446a-210">若要深入瞭解，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="6446a-210">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="6446a-211">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="6446a-211">Get the status of a batch assignment</span></span>

<span data-ttu-id="6446a-212">執行下列操作以取得批次工作的狀態，其中 OperationId 是由```New-CsBatchPolicyAssignmentOperation``` Cmdlet 針對指定批次傳回的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="6446a-212">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="6446a-213">如果輸出顯示發生錯誤，請執行下列動作，以取得有關```UserState```屬性中錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6446a-213">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="6446a-214">若要深入瞭解，請參閱[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="6446a-214">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6446a-215">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="6446a-215">Assign a policy to a group</span></span>

<span data-ttu-id="6446a-216">**目前只有私人預覽才能使用群組的原則指派功能。此功能的 Cmdlet 位於預發行團隊 PowerShell 模組中。**</span><span class="sxs-lookup"><span data-stu-id="6446a-216">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="6446a-217">[群組原則指派] 可讓您將原則指派給使用者群組，例如安全性群組或組織單位。</span><span class="sxs-lookup"><span data-stu-id="6446a-217">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="6446a-218">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6446a-218">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6446a-219">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="6446a-219">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="6446a-220">您使用```New-CsGroupPolicyAssignment``` Cmdlet 將原則指派給群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-220">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="6446a-221">您可以使用 [物件識別碼]、[SIP 位址] 或 [電子郵件地址] 來指定群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-221">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="6446a-222">指派原則時，它會立即指派給群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-222">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="6446a-223">不過，請注意，原則指派對群組成員的傳播是作為背景作業執行，可能需要一些時間，視群組的大小而定。</span><span class="sxs-lookup"><span data-stu-id="6446a-223">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="6446a-224">如果沒有從群組中取消指派原則，或是在群組中新增或移除某個原則，就是如此。</span><span class="sxs-lookup"><span data-stu-id="6446a-224">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="6446a-225">目前，對於所有團隊原則類型，將無法將原則指派給群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-225">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="6446a-226">如需支援的原則類型清單，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 。</span><span class="sxs-lookup"><span data-stu-id="6446a-226">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="6446a-227">針對群組的原則指派所需注意的事項</span><span class="sxs-lookup"><span data-stu-id="6446a-227">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="6446a-228">在您開始之前，請務必瞭解優先規則與群組指派排名。</span><span class="sxs-lookup"><span data-stu-id="6446a-228">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="6446a-229">優先規則</span><span class="sxs-lookup"><span data-stu-id="6446a-229">Precedence rules</span></span>

<span data-ttu-id="6446a-230">針對特定原則類型，根據下列專案來決定使用者的有效原則：</span><span class="sxs-lookup"><span data-stu-id="6446a-230">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="6446a-231">直接指派給使用者的原則，優先于任何其他指派給群組之相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-231">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="6446a-232">換句話說，如果使用者是直接指派給特定類型的原則，該使用者就不會從群組繼承相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-232">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="6446a-233">這也表示如果使用者具有直接指派給他們的特定類型的原則，您必須先移除使用者的原則，才能從群組繼承相同類型的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-233">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="6446a-234">如果使用者沒有直接指派的原則，且是兩個或多個群組的成員，且每個群組都有指派相同類型的原則，則使用者會繼承最高排名的群組指派原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-234">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="6446a-235">如果使用者不是指派原則的任何群組的成員，該原則類型的全域（組織範圍預設值）原則會套用至使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-235">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="6446a-236">在已指派原則的群組中新增或移除使用者時，會根據這些規則來更新使用者的有效原則、將原則指派給群組，或直接指派給該使用者的原則也會被移除。</span><span class="sxs-lookup"><span data-stu-id="6446a-236">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="6446a-237">群組指派排名</span><span class="sxs-lookup"><span data-stu-id="6446a-237">Group assignment ranking</span></span>
 
<span data-ttu-id="6446a-238">當您將原則指派給群組時，請指定群組指派的排名。</span><span class="sxs-lookup"><span data-stu-id="6446a-238">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="6446a-239">這是用來判斷，如果使用者是兩個或多個群組的成員，且每個群組都指派相同類型的原則，使用者應該繼承為其有效原則的原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-239">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="6446a-240">群組指派排名是相對於相同類型的其他群組分派。</span><span class="sxs-lookup"><span data-stu-id="6446a-240">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="6446a-241">例如，如果您要將通話原則指派給兩個群組，請將一個指派的等級設定為1，而另一個指派給2，1為最高排名。</span><span class="sxs-lookup"><span data-stu-id="6446a-241">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="6446a-242">[群組指派排名] 會指出哪些群組成員資格比繼承更重要，或比其他群組成員資格更相關。</span><span class="sxs-lookup"><span data-stu-id="6446a-242">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="6446a-243">例如，您有兩個群組，請儲存 [員工] 和 [書店管理員]。</span><span class="sxs-lookup"><span data-stu-id="6446a-243">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="6446a-244">兩個群組都會獲指派團隊通話原則，分別將員工撥打電話給原則和商店管理員呼叫原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-244">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="6446a-245">對於在這兩個群組中的書店管理員而言，其角色會與員工的角色更相關，所以指派給商店管理員群組的呼叫原則應該有較高的排名。</span><span class="sxs-lookup"><span data-stu-id="6446a-245">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="6446a-246">群組</span><span class="sxs-lookup"><span data-stu-id="6446a-246">Group</span></span> |<span data-ttu-id="6446a-247">小組通話原則名稱</span><span class="sxs-lookup"><span data-stu-id="6446a-247">Teams calling policy name</span></span>  |<span data-ttu-id="6446a-248">排名</span><span class="sxs-lookup"><span data-stu-id="6446a-248">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="6446a-249">商店管理員</span><span class="sxs-lookup"><span data-stu-id="6446a-249">Store Managers</span></span>   |<span data-ttu-id="6446a-250">商店管理員通話原則</span><span class="sxs-lookup"><span data-stu-id="6446a-250">Store Managers Calling Policy</span></span>         |<span data-ttu-id="6446a-251">1</span><span class="sxs-lookup"><span data-stu-id="6446a-251">1</span></span>|
|<span data-ttu-id="6446a-252">儲存員工</span><span class="sxs-lookup"><span data-stu-id="6446a-252">Store Employees</span></span>    |<span data-ttu-id="6446a-253">儲存員工的通話原則</span><span class="sxs-lookup"><span data-stu-id="6446a-253">Store Employees Calling Policy</span></span>      |<span data-ttu-id="6446a-254">pplx-2</span><span class="sxs-lookup"><span data-stu-id="6446a-254">2</span></span>|

<span data-ttu-id="6446a-255">如果您沒有指定排名，則會給予原則指派最低等級。</span><span class="sxs-lookup"><span data-stu-id="6446a-255">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6446a-256">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="6446a-256">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="6446a-257">Cmdlet 位於團隊 PowerShell 模組的預發行版本本中。</span><span class="sxs-lookup"><span data-stu-id="6446a-257">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="6446a-258">請依照下列步驟，先卸載「通用」團隊 PowerShell 模組（如果已安裝），然後從 PowerShell 測試圖庫安裝該模組最新的預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="6446a-258">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="6446a-259">如果您尚未安裝，請執行下列動作，將 PowerShell 測試圖庫註冊為受信任的來源。</span><span class="sxs-lookup"><span data-stu-id="6446a-259">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="6446a-260">如果您已安裝「通用」的小組 PowerShell 模組版本，請執行下列動作加以卸載。</span><span class="sxs-lookup"><span data-stu-id="6446a-260">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="6446a-261">執行下列動作，從 PowerShell 測試圖庫安裝最新的 Microsoft 團隊 PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="6446a-261">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="6446a-262">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="6446a-262">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6446a-263">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="6446a-263">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6446a-264">指派原則給群組</span><span class="sxs-lookup"><span data-stu-id="6446a-264">Assign a policy to a group</span></span>

<span data-ttu-id="6446a-265">在這個範例中，我們會```New-CsGroupPolicyAssignment```使用 Cmdlet，將名為「零售經理」會議原則的小組會議原則指派給作業排名為1的群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-265">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="6446a-266">若要深入瞭解，請參閱[新-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="6446a-266">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="6446a-267">取得群組的原則指派</span><span class="sxs-lookup"><span data-stu-id="6446a-267">Get policy assignments for a group</span></span>

<span data-ttu-id="6446a-268">使用```Get-CsGroupPolicyAssignment``` Cmdlet 來取得指派給群組的所有原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-268">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="6446a-269">請注意，即使其 SIP 位址或電子郵件地址是用來指派原則，群組也永遠會依其群組識別碼列出。</span><span class="sxs-lookup"><span data-stu-id="6446a-269">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="6446a-270">在這個範例中，我們會檢索指派給特定群組的所有原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-270">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="6446a-271">在這個範例中，我們會傳回指派給「團隊」會議原則的所有群組。</span><span class="sxs-lookup"><span data-stu-id="6446a-271">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="6446a-272">若要深入瞭解，請參閱[CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="6446a-272">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="6446a-273">從群組中移除原則</span><span class="sxs-lookup"><span data-stu-id="6446a-273">Remove a policy from a group</span></span>

<span data-ttu-id="6446a-274">使用```Remove-CsGroupPolicyAssignment``` Cmdlet 從群組中移除原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-274">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="6446a-275">當您從群組中移除原則時，會更新指派給該群組之相同類型之其他原則的優先順序，並更新較低排名的專案。</span><span class="sxs-lookup"><span data-stu-id="6446a-275">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="6446a-276">例如，如果您移除等級為2的原則，就會更新等級為3和4的原則，以反映其新的排名。</span><span class="sxs-lookup"><span data-stu-id="6446a-276">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="6446a-277">下列兩個數據表顯示這個範例。</span><span class="sxs-lookup"><span data-stu-id="6446a-277">The following two tables show this example.</span></span>

<span data-ttu-id="6446a-278">以下是團隊會議原則的原則指派與優先順序清單。</span><span class="sxs-lookup"><span data-stu-id="6446a-278">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="6446a-279">組名</span><span class="sxs-lookup"><span data-stu-id="6446a-279">Group name</span></span>  |<span data-ttu-id="6446a-280">原則名稱</span><span class="sxs-lookup"><span data-stu-id="6446a-280">Policy name</span></span>  |<span data-ttu-id="6446a-281">排名</span><span class="sxs-lookup"><span data-stu-id="6446a-281">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6446a-282">銷售</span><span class="sxs-lookup"><span data-stu-id="6446a-282">Sales</span></span>    |<span data-ttu-id="6446a-283">銷售原則</span><span class="sxs-lookup"><span data-stu-id="6446a-283">Sales policy</span></span>       | <span data-ttu-id="6446a-284">1</span><span class="sxs-lookup"><span data-stu-id="6446a-284">1</span></span>        |
|<span data-ttu-id="6446a-285">西部地區</span><span class="sxs-lookup"><span data-stu-id="6446a-285">West Region</span></span>     |<span data-ttu-id="6446a-286">西部地區原則</span><span class="sxs-lookup"><span data-stu-id="6446a-286">West Region policy</span></span>         |<span data-ttu-id="6446a-287">pplx-2</span><span class="sxs-lookup"><span data-stu-id="6446a-287">2</span></span>         |
|<span data-ttu-id="6446a-288">除以</span><span class="sxs-lookup"><span data-stu-id="6446a-288">Division</span></span>    |<span data-ttu-id="6446a-289">部門原則</span><span class="sxs-lookup"><span data-stu-id="6446a-289">Division policy</span></span>         |<span data-ttu-id="6446a-290">3</span><span class="sxs-lookup"><span data-stu-id="6446a-290">3</span></span>         |
|<span data-ttu-id="6446a-291">附屬</span><span class="sxs-lookup"><span data-stu-id="6446a-291">Subsidiary</span></span>   |<span data-ttu-id="6446a-292">附屬原則</span><span class="sxs-lookup"><span data-stu-id="6446a-292">Subsidiary policy</span></span>        |<span data-ttu-id="6446a-293">4</span><span class="sxs-lookup"><span data-stu-id="6446a-293">4</span></span>         |

<span data-ttu-id="6446a-294">如果我們移除 [西部區域] 群組中的 [西部區域原則]，原則指派與優先順序會更新為以下所示。</span><span class="sxs-lookup"><span data-stu-id="6446a-294">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="6446a-295">組名</span><span class="sxs-lookup"><span data-stu-id="6446a-295">Group name</span></span>  |<span data-ttu-id="6446a-296">原則名稱</span><span class="sxs-lookup"><span data-stu-id="6446a-296">Policy name</span></span>  |<span data-ttu-id="6446a-297">排名</span><span class="sxs-lookup"><span data-stu-id="6446a-297">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6446a-298">銷售</span><span class="sxs-lookup"><span data-stu-id="6446a-298">Sales</span></span>    |<span data-ttu-id="6446a-299">銷售原則</span><span class="sxs-lookup"><span data-stu-id="6446a-299">Sales policy</span></span>       | <span data-ttu-id="6446a-300">1</span><span class="sxs-lookup"><span data-stu-id="6446a-300">1</span></span>        |
|<span data-ttu-id="6446a-301">除以</span><span class="sxs-lookup"><span data-stu-id="6446a-301">Division</span></span>    |<span data-ttu-id="6446a-302">部門原則</span><span class="sxs-lookup"><span data-stu-id="6446a-302">Division policy</span></span>         |<span data-ttu-id="6446a-303">pplx-2</span><span class="sxs-lookup"><span data-stu-id="6446a-303">2</span></span>         |
|<span data-ttu-id="6446a-304">附屬</span><span class="sxs-lookup"><span data-stu-id="6446a-304">Subsidiary</span></span>   |<span data-ttu-id="6446a-305">附屬原則</span><span class="sxs-lookup"><span data-stu-id="6446a-305">Subsidiary policy</span></span>        |<span data-ttu-id="6446a-306">3</span><span class="sxs-lookup"><span data-stu-id="6446a-306">3</span></span>        |

<span data-ttu-id="6446a-307">在這個範例中，我們會從群組中移除團隊會議原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-307">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="6446a-308">若要深入瞭解，請參閱[移除-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="6446a-308">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="6446a-309">變更群組的原則指派</span><span class="sxs-lookup"><span data-stu-id="6446a-309">Change a policy assignment for a group</span></span>

<span data-ttu-id="6446a-310">將原則指派給群組之後，您可以使用```Set-CsGroupPolicyAssignmentd``` Cmdlet 來變更該群組的原則指派，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6446a-310">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="6446a-311">變更排名</span><span class="sxs-lookup"><span data-stu-id="6446a-311">Change the ranking</span></span>
- <span data-ttu-id="6446a-312">變更指定原則類型的原則</span><span class="sxs-lookup"><span data-stu-id="6446a-312">Change the policy of a given policy type</span></span>
- <span data-ttu-id="6446a-313">變更指定原則類型和排名的原則</span><span class="sxs-lookup"><span data-stu-id="6446a-313">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="6446a-314">在這個範例中，我們會將群組的小組通話駐留原則給名為 SupportCallPark 的原則，並將作業排名等級設為3。</span><span class="sxs-lookup"><span data-stu-id="6446a-314">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="6446a-315">若要深入瞭解，請參閱[設定 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="6446a-315">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="6446a-316">變更使用者的有效原則</span><span class="sxs-lookup"><span data-stu-id="6446a-316">Change the effective policy for a user</span></span>

<span data-ttu-id="6446a-317">以下範例說明如何變更直接指派原則的使用者的有效原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-317">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="6446a-318">首先，我們會將```Get-CsUserPolicyAssignment``` Cmdlet 與```PolicySource```參數搭配使用，以取得與使用者相關聯之小組會議廣播原則的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6446a-318">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="6446a-319">若要深入瞭解，請參閱[CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)。</span><span class="sxs-lookup"><span data-stu-id="6446a-319">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="6446a-320">輸出顯示使用者是直接指派給員工事件的小組會議廣播原則，其優先順序高於指派給該使用者所屬群組的「提供者即時事件」原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-320">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="6446a-321">現在，我們移除使用者的員工活動原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-321">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="6446a-322">這表示使用者已不再將團隊會議廣播原則直接指派給他們，並將繼承指派給該使用者所屬群組的供應商即時事件原則。</span><span class="sxs-lookup"><span data-stu-id="6446a-322">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="6446a-323">在商務用 Skype PowerShell 模組中使用下列 Cmdlet 來執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="6446a-323">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="6446a-324">您可以在團隊 Powershell 模組中使用下列 Cmdlet，透過批次原則指派來執行這項作業，其中 $users 是您指定的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="6446a-324">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="6446a-325">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-325">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="6446a-326">使用批次原則套件指派，您可以一次將原則套件指派給大型的使用者組，而不需要使用腳本。</span><span class="sxs-lookup"><span data-stu-id="6446a-326">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="6446a-327">您可以使用```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet 來提交一批使用者，以及您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="6446a-327">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="6446a-328">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="6446a-328">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="6446a-329">然後，您就可以```Get-CsBatchPolicyAssignmentOperation```使用此 Cmdlet 來追蹤批次中作業的進度和狀態。</span><span class="sxs-lookup"><span data-stu-id="6446a-329">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="6446a-330">批次最多可包含20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-330">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="6446a-331">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-331">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6446a-332">我們目前建議您一次將原則套件指派給一批5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-332">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="6446a-333">在這些時間增加需求期間，您可能會遇到處理時間的延遲。</span><span class="sxs-lookup"><span data-stu-id="6446a-333">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="6446a-334">為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。</span><span class="sxs-lookup"><span data-stu-id="6446a-334">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="6446a-335">在一般的商務時間以外提交批次也會有所説明。</span><span class="sxs-lookup"><span data-stu-id="6446a-335">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6446a-336">安裝並連接至 Microsoft 團隊 PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="6446a-336">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6446a-337">執行下列動作以安裝[Microsoft 團隊 PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftTeams)（如果您尚未這麼做）。</span><span class="sxs-lookup"><span data-stu-id="6446a-337">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="6446a-338">請確定您已安裝版本1.0.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6446a-338">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6446a-339">執行下列動作以連線至團隊並啟動會話。</span><span class="sxs-lookup"><span data-stu-id="6446a-339">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6446a-340">出現提示時，請使用您的系統管理員認證登入。</span><span class="sxs-lookup"><span data-stu-id="6446a-340">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="6446a-341">指派原則套件給一批使用者</span><span class="sxs-lookup"><span data-stu-id="6446a-341">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="6446a-342">在這個範例中，我們使用```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet 將 Education_PrimaryStudent 原則套件指派給一批使用者。</span><span class="sxs-lookup"><span data-stu-id="6446a-342">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="6446a-343">若要深入瞭解，請參閱[新-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="6446a-343">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="6446a-344">取得批次作業的狀態</span><span class="sxs-lookup"><span data-stu-id="6446a-344">Get the status of a batch assignment</span></span>

<span data-ttu-id="6446a-345">執行下列操作以取得批次工作的狀態，其中 OperationId 是由```New-CsBatchPolicyAssignmentOperation``` Cmdlet 針對指定批次傳回的作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="6446a-345">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="6446a-346">如果輸出顯示發生錯誤，請執行下列動作，以取得有關```UserState```屬性中錯誤的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6446a-346">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="6446a-347">若要深入瞭解，請參閱[CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)。</span><span class="sxs-lookup"><span data-stu-id="6446a-347">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="6446a-348">相關主題</span><span class="sxs-lookup"><span data-stu-id="6446a-348">Related topics</span></span>

- [<span data-ttu-id="6446a-349">團隊 PowerShell 概覽</span><span class="sxs-lookup"><span data-stu-id="6446a-349">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)