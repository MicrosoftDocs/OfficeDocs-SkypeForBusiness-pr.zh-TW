---
title: 適用於醫療保健的 Teams 原則套件
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 瞭解如何使用和管理適用于貴醫療保健組織的 Teams 原則套件。
ms.openlocfilehash: 830b8fc5f6938f84f188f5f5d732a3ecfd6eb5b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117761"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="0a6b4-103">適用於醫療保健的 Teams 原則套件</span><span class="sxs-lookup"><span data-stu-id="0a6b4-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="0a6b4-104">概觀</span><span class="sxs-lookup"><span data-stu-id="0a6b4-104">Overview</span></span>

<span data-ttu-id="0a6b4-105">Microsoft Teams 中的 [原則套件](manage-policy-packages.md) 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="0a6b4-106">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="0a6b4-107">您可以自訂套件中的原則之設定，以符合使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="0a6b4-108">當您變更原則套件中的原則設定時，指派給該套件的所有使用者會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="0a6b4-109">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="0a6b4-110">以下項目的預先定義原則之原則套件，依套件而訂：</span><span class="sxs-lookup"><span data-stu-id="0a6b4-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="0a6b4-111">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="0a6b4-111">Messaging</span></span>
- <span data-ttu-id="0a6b4-112">會議</span><span class="sxs-lookup"><span data-stu-id="0a6b4-112">Meetings</span></span>
- <span data-ttu-id="0a6b4-113">通話</span><span class="sxs-lookup"><span data-stu-id="0a6b4-113">Calling</span></span>
- <span data-ttu-id="0a6b4-114">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="0a6b4-114">App setup</span></span>
- <span data-ttu-id="0a6b4-115">即時活動</span><span class="sxs-lookup"><span data-stu-id="0a6b4-115">Live events</span></span>

<span data-ttu-id="0a6b4-116">Teams 目前包含下列醫療保健原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="0a6b4-117">Microsoft Teams 系統管理中心所列的套件名稱</span><span class="sxs-lookup"><span data-stu-id="0a6b4-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="0a6b4-118">最適合用於</span><span class="sxs-lookup"><span data-stu-id="0a6b4-118">Best used for</span></span>|<span data-ttu-id="0a6b4-119">描述</span><span class="sxs-lookup"><span data-stu-id="0a6b4-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="0a6b4-120">醫療保健臨床工作者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="0a6b4-121">貴醫療保健組織的臨床工作者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="0a6b4-122">建立一組原則與原則設定，讓臨床工作者 (例如註冊的護士、護士長、醫生和社會工作者) 能完整存取聊天、通話、班次管理和會議。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="0a6b4-123">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-123">Healthcare information worker</span></span>  |<span data-ttu-id="0a6b4-124">貴醫療保健組織的資訊工作者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="0a6b4-125">建立一組原則與原則設定，讓資訊工作者 (例如 IT 人員、資訊人員、財務人員及法規人員) 能夠完整存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="0a6b4-126">醫療保健病房</span><span class="sxs-lookup"><span data-stu-id="0a6b4-126">Healthcare patient room</span></span>  |<span data-ttu-id="0a6b4-127">病房裝置</span><span class="sxs-lookup"><span data-stu-id="0a6b4-127">Patient room devices</span></span>|<span data-ttu-id="0a6b4-128">建立一組原則與原則設定，適用於貴醫療保健組織的病房。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

<span data-ttu-id="0a6b4-130">每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="0a6b4-131">例如，當您將醫療保健臨床工作者原則套件指派給貴組織的臨床醫生時，便會為套件中的每個原則建立名為 Healthcare_ClinicalWorker 的原則。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![醫療保健臨床工作者套件中的原則螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="0a6b4-133">開始使用原則套件</span><span class="sxs-lookup"><span data-stu-id="0a6b4-133">Get started with policy packages</span></span>

<span data-ttu-id="0a6b4-134">若要開始使用醫療保健原則套件，請在 Microsoft Admin Center 上線中心選取 **醫療保健**，然後選取 **根據角色指派原則設定**。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="0a6b4-135">當您準備好開始後，請決定要指派給組織中的個人哪些原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="0a6b4-136">選取 **檢視原則詳細資料** 以深入瞭解套件中的特定原則及其相應的設定。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="0a6b4-137">指派後，您可以在 Teams 系統管理中心 [自訂](manage-policy-packages.md#customize-policies-in-a-policy-package) 這些設定。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="0a6b4-138">選擇要指派的一或多個套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="0a6b4-139">您可以搜尋人員，並新增人員至最適合其角色的套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="0a6b4-140">無法一次將一個人員指派給多個原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="0a6b4-141">一旦將人員新增到正確的原則套件，請點選 **完成** 以完成您的選取項目。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="0a6b4-142">您可以繼續在 Microsoft Teams 系統管理中心自訂和管理原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="0a6b4-143">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="0a6b4-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="0a6b4-144">檢視</span><span class="sxs-lookup"><span data-stu-id="0a6b4-144">View</span></span>

<span data-ttu-id="0a6b4-145">在指派套件之前，請查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="0a6b4-146">在 Microsoft Teams 系統管理中心的左側瀏覽中，請移至 **[原則套件]**，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="0a6b4-147">决定預先定義的值是否適合貴組織，或者您是否需要根據組織的需求將它們自訂為更嚴格或更寬鬆的值。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="0a6b4-148">自訂</span><span class="sxs-lookup"><span data-stu-id="0a6b4-148">Customize</span></span>

<span data-ttu-id="0a6b4-149">視需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="0a6b4-150">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="0a6b4-151">要編輯原則套件中原則的設定，請在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 **原則套件**，選取原則套件，選取要編輯的原則名稱，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="0a6b4-152">請記住，您可以在指派原則套件之後變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="0a6b4-153">若要深入了解，請參閱 [自訂原則套件中的原則](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="0a6b4-154">指派</span><span class="sxs-lookup"><span data-stu-id="0a6b4-154">Assign</span></span>

<span data-ttu-id="0a6b4-p110">將原則套件指派給使用者。如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-p110">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="0a6b4-157">將原則套件指派給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="0a6b4-158">若要將原則套件指派給一或多個使用者，請在 Microsoft Teams 系統管理中心的左側流覽窗格中，移至 **原則套件**，然後選取 **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="0a6b4-160">若要深入了解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="0a6b4-161">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="0a6b4-162">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="0a6b4-162">Assign a policy package to a group</span></span>

<span data-ttu-id="0a6b4-163">**這項功能在私人預覽中**</span><span class="sxs-lookup"><span data-stu-id="0a6b4-163">**This feature is in private preview**</span></span>

<span data-ttu-id="0a6b4-164">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="0a6b4-165">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="0a6b4-166">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="0a6b4-167">此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="0a6b4-168">若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="0a6b4-169">為一大組 (批) 使用者指派原則套件</span><span class="sxs-lookup"><span data-stu-id="0a6b4-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="0a6b4-170">使用批次原則套件指派，將原則套件一次性指派給大組使用者組。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="0a6b4-171">您可以使用 [CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="0a6b4-172">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="0a6b4-173">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="0a6b4-174">您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="0a6b4-175">若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="0a6b4-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0a6b4-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="0a6b4-176">Related topics</span></span>

[<span data-ttu-id="0a6b4-177">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="0a6b4-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="0a6b4-178">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="0a6b4-178">Assign policies to your users in Teams</span></span>](assign-policies.md)