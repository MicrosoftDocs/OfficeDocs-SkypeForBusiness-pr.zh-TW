---
title: Teams政府政策套件
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理Teams組織的政策套件。
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796867"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="00061-103">Teams政府政策套件</span><span class="sxs-lookup"><span data-stu-id="00061-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="00061-104">在政府部署或 DoD 部署Microsoft 365提供GCC套件。</span><span class="sxs-lookup"><span data-stu-id="00061-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="00061-105">概觀</span><span class="sxs-lookup"><span data-stu-id="00061-105">Overview</span></span>

<span data-ttu-id="00061-106">Microsoft Teams 中的 [原則套件](manage-policy-packages.md) 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="00061-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="00061-107">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="00061-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="00061-108">您可以自訂套件中的原則之設定，以符合使用者的需求。</span><span class="sxs-lookup"><span data-stu-id="00061-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="00061-109">當您變更原則套件中的原則設定時，指派給該套件的所有使用者會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="00061-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="00061-110">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理原則套件。</span><span class="sxs-lookup"><span data-stu-id="00061-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="00061-111">以下項目的預先定義原則之原則套件，依套件而訂：</span><span class="sxs-lookup"><span data-stu-id="00061-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="00061-112">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="00061-112">Messaging</span></span>
- <span data-ttu-id="00061-113">會議</span><span class="sxs-lookup"><span data-stu-id="00061-113">Meetings</span></span>
- <span data-ttu-id="00061-114">通話</span><span class="sxs-lookup"><span data-stu-id="00061-114">Calling</span></span>
- <span data-ttu-id="00061-115">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="00061-115">App setup</span></span>
- <span data-ttu-id="00061-116">即時活動</span><span class="sxs-lookup"><span data-stu-id="00061-116">Live events</span></span>

<span data-ttu-id="00061-117">Teams目前包含下列政府政策套件。</span><span class="sxs-lookup"><span data-stu-id="00061-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="00061-118">Microsoft Teams 系統管理中心所列的套件名稱</span><span class="sxs-lookup"><span data-stu-id="00061-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="00061-119">最適合用於</span><span class="sxs-lookup"><span data-stu-id="00061-119">Best used for</span></span>|<span data-ttu-id="00061-120">描述</span><span class="sxs-lookup"><span data-stu-id="00061-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="00061-121">公共安全專員</span><span class="sxs-lookup"><span data-stu-id="00061-121">Public safety officer</span></span>  |<span data-ttu-id="00061-122">貴政府組織的公開安全人員</span><span class="sxs-lookup"><span data-stu-id="00061-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="00061-123">建立一組套套用至貴組織的公安人員之原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="00061-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="00061-124">前線管理員</span><span class="sxs-lookup"><span data-stu-id="00061-124">Frontline manager</span></span>  |<span data-ttu-id="00061-125">您政府組織的前線管理員</span><span class="sxs-lookup"><span data-stu-id="00061-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="00061-126">建立一組原則，並套用這些設定給貴組織的前線管理員。</span><span class="sxs-lookup"><span data-stu-id="00061-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="00061-127">前線工作人員</span><span class="sxs-lookup"><span data-stu-id="00061-127">Frontline worker</span></span>  |<span data-ttu-id="00061-128">您政府組織的前線工作人員</span><span class="sxs-lookup"><span data-stu-id="00061-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="00061-129">建立一組原則，並套用這些設定給貴組織的前線工作人員。</span><span class="sxs-lookup"><span data-stu-id="00061-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

<span data-ttu-id="00061-131">每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="00061-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="00061-132">例如，當您將公用安全人員政策套件指派給貴組織的使用者時，會針對套件中的每個PublicSafety_Officer建立名為 PublicSafety_Officer 的策略。</span><span class="sxs-lookup"><span data-stu-id="00061-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![醫療保健臨床工作者套件中的原則螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="00061-134">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="00061-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="00061-135">檢視</span><span class="sxs-lookup"><span data-stu-id="00061-135">View</span></span>

<span data-ttu-id="00061-136">在指派套件之前，請查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="00061-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="00061-137">在 Microsoft Teams 系統管理中心的左側流覽中，選取 **[原則套件]**，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="00061-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="00061-138">决定預先定義的值是否適合貴組織，或者您是否需要根據組織的需求將它們自訂為更嚴格或更寬鬆的值。</span><span class="sxs-lookup"><span data-stu-id="00061-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="00061-139">自訂</span><span class="sxs-lookup"><span data-stu-id="00061-139">Customize</span></span>

<span data-ttu-id="00061-140">視需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="00061-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="00061-141">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="00061-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="00061-142">要編輯原則套件中原則的設定，請在 Microsoft Teams 系統管理中心，選取該原則套件，選取要編輯的原則名稱，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="00061-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="00061-143">請記住，您可以在指派原則套件之後變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="00061-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="00061-144">若要深入了解，請參閱 [自訂原則套件中的原則](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="00061-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="00061-145">指派</span><span class="sxs-lookup"><span data-stu-id="00061-145">Assign</span></span>

<span data-ttu-id="00061-p106">將原則套件指派給使用者。如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="00061-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="00061-148">每個使用者都需要進一步通訊附加元件，才能接收自訂策略套件指派。</span><span class="sxs-lookup"><span data-stu-id="00061-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="00061-149">若要詳細資訊，請參閱適用于 Microsoft Teams[的 Advanced Communications 附加Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="00061-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="00061-150">將原則套件指派給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="00061-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="00061-151">若要將原則套件指派給一或多個使用者，請在 Microsoft Teams 系統管理中心的左側流覽窗格中，移至 **原則套件**，然後選取 **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="00061-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="00061-153">若要深入了解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="00061-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="00061-154">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="00061-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="00061-155">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="00061-155">Assign a policy package to a group</span></span>

<span data-ttu-id="00061-156">**這項功能在私人預覽中**</span><span class="sxs-lookup"><span data-stu-id="00061-156">**This feature is in private preview**</span></span>

<span data-ttu-id="00061-157">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="00061-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="00061-158">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="00061-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="00061-159">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="00061-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="00061-160">此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="00061-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="00061-161">若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="00061-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="00061-162">為一大組 (批) 使用者指派原則套件</span><span class="sxs-lookup"><span data-stu-id="00061-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="00061-163">使用批次原則套件指派，將原則套件一次性指派給大組使用者組。</span><span class="sxs-lookup"><span data-stu-id="00061-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="00061-164">您可以使用 [CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="00061-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="00061-165">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="00061-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="00061-166">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="00061-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="00061-167">您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="00061-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="00061-168">若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="00061-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="00061-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="00061-169">Related topics</span></span>

[<span data-ttu-id="00061-170">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="00061-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="00061-171">指派策略套件給使用者和群組</span><span class="sxs-lookup"><span data-stu-id="00061-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
