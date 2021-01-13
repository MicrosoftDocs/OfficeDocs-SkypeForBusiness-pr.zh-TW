---
title: 醫療保健的團隊原則套件
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
description: 瞭解如何使用及管理您的保健組織的小組原則套件。
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812853"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="1df86-103">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="1df86-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="1df86-104">概觀</span><span class="sxs-lookup"><span data-stu-id="1df86-104">Overview</span></span>

<span data-ttu-id="1df86-105">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="1df86-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="1df86-106">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="1df86-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="1df86-107">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="1df86-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="1df86-108">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="1df86-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="1df86-109">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="1df86-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="1df86-110">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="1df86-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="1df86-111">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="1df86-111">Messaging</span></span>
- <span data-ttu-id="1df86-112">會議</span><span class="sxs-lookup"><span data-stu-id="1df86-112">Meetings</span></span>
- <span data-ttu-id="1df86-113">通話</span><span class="sxs-lookup"><span data-stu-id="1df86-113">Calling</span></span>
- <span data-ttu-id="1df86-114">App 設定</span><span class="sxs-lookup"><span data-stu-id="1df86-114">App setup</span></span>
- <span data-ttu-id="1df86-115">即時事件</span><span class="sxs-lookup"><span data-stu-id="1df86-115">Live events</span></span>

<span data-ttu-id="1df86-116">團隊目前包含下列醫療保健原則封裝。</span><span class="sxs-lookup"><span data-stu-id="1df86-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="1df86-117">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="1df86-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="1df86-118">最適合用於</span><span class="sxs-lookup"><span data-stu-id="1df86-118">Best used for</span></span>|<span data-ttu-id="1df86-119">描述</span><span class="sxs-lookup"><span data-stu-id="1df86-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1df86-120">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="1df86-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="1df86-121">您的保健組織中的臨床工作者</span><span class="sxs-lookup"><span data-stu-id="1df86-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="1df86-122">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="1df86-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="1df86-123">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="1df86-123">Healthcare information worker</span></span>  |<span data-ttu-id="1df86-124">您的保健組織中的資訊工作者</span><span class="sxs-lookup"><span data-stu-id="1df86-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="1df86-125">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="1df86-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="1df86-126">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="1df86-126">Healthcare patient room</span></span>  |<span data-ttu-id="1df86-127">患者房間裝置</span><span class="sxs-lookup"><span data-stu-id="1df86-127">Patient room devices</span></span>|<span data-ttu-id="1df86-128">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="1df86-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

<span data-ttu-id="1df86-130">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="1df86-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="1df86-131">例如，當您將醫療保健臨床工人原則套件指派給您組織中的臨床醫師時，會針對套件中的每個原則，建立一個名為 Healthcare_ClinicalWorker 的原則。</span><span class="sxs-lookup"><span data-stu-id="1df86-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="1df86-133">開始使用原則套件</span><span class="sxs-lookup"><span data-stu-id="1df86-133">Get started with policy packages</span></span>

<span data-ttu-id="1df86-134">若要開始使用醫療保健原則套件，請在 Microsoft 系統管理中心加入中樞上，選取 [ **保健**]，然後選取 [ **依角色指派原則設定**]。</span><span class="sxs-lookup"><span data-stu-id="1df86-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="1df86-135">準備好開始使用之後，請決定您要將組織中的個別人指派給哪個原則套件。</span><span class="sxs-lookup"><span data-stu-id="1df86-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="1df86-136">選取 [ **查看原則詳細資料** ]，進一步瞭解套件中的特定原則及其各自的設定。</span><span class="sxs-lookup"><span data-stu-id="1df86-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="1df86-137">在團隊系統管理中心中作業分派之後， [就可以自訂](manage-policy-packages.md#customize-policies-in-a-policy-package) 這些功能。</span><span class="sxs-lookup"><span data-stu-id="1df86-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="1df86-138">選擇一或多個要指派的套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1df86-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="1df86-139">您可以搜尋並將人員新增至最適合自己角色的原則套件中。</span><span class="sxs-lookup"><span data-stu-id="1df86-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="1df86-140">一次無法將一個人指派給多個原則套件。</span><span class="sxs-lookup"><span data-stu-id="1df86-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="1df86-141">將人員新增至正確的原則套件後，請 **完成** 您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="1df86-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="1df86-142">您可以繼續自訂及管理 Microsoft 團隊系統管理中心的原則套件。</span><span class="sxs-lookup"><span data-stu-id="1df86-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="1df86-143">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="1df86-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="1df86-144">檢視</span><span class="sxs-lookup"><span data-stu-id="1df86-144">View</span></span>

<span data-ttu-id="1df86-145">在指派套件之前，請查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="1df86-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="1df86-146">在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件**]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="1df86-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="1df86-147">决定預先定義的值是否適合貴組織，或者您是否需要根據組織的需求將它們自訂為更嚴格或更寬鬆的值。</span><span class="sxs-lookup"><span data-stu-id="1df86-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="1df86-148">自訂</span><span class="sxs-lookup"><span data-stu-id="1df86-148">Customize</span></span>

<span data-ttu-id="1df86-149">視需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="1df86-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="1df86-150">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="1df86-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="1df86-151">若要編輯原則套件中原則的設定，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件**]，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="1df86-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="1df86-152">請記住，您可以在指派原則套件之後變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="1df86-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="1df86-153">若要深入了解，請參閱 [自訂原則套件中的原則](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="1df86-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="1df86-154">指派</span><span class="sxs-lookup"><span data-stu-id="1df86-154">Assign</span></span>

<span data-ttu-id="1df86-155">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="1df86-155">Assign the policy package to users.</span></span> <span data-ttu-id="1df86-156">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="1df86-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="1df86-157">將原則套件指派給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="1df86-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="1df86-158">若要將原則套件指派給一或多個使用者，請在 Microsoft Teams 系統管理中心的左側流覽窗格中，移至 **原則套件**，然後選取 **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="1df86-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="1df86-160">若要深入了解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="1df86-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="1df86-161">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="1df86-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="1df86-162">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="1df86-162">Assign a policy package to a group</span></span>

<span data-ttu-id="1df86-163">**這項功能在私人預覽中**</span><span class="sxs-lookup"><span data-stu-id="1df86-163">**This feature is in private preview**</span></span>

<span data-ttu-id="1df86-164">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="1df86-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="1df86-165">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="1df86-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="1df86-166">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="1df86-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="1df86-167">此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="1df86-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="1df86-168">若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="1df86-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="1df86-169">為一大組 (批) 使用者指派原則套件</span><span class="sxs-lookup"><span data-stu-id="1df86-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="1df86-170">使用批次原則套件指派，將原則套件一次性指派給大組使用者組。</span><span class="sxs-lookup"><span data-stu-id="1df86-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="1df86-171">您可以使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="1df86-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="1df86-172">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="1df86-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="1df86-173">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="1df86-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="1df86-174">您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="1df86-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="1df86-175">若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="1df86-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="1df86-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="1df86-176">Related topics</span></span>

[<span data-ttu-id="1df86-177">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="1df86-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="1df86-178">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="1df86-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
