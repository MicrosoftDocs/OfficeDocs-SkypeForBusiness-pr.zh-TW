---
title: 政府團隊原則套件
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
description: 瞭解如何使用及管理您的政府組織的小組原則套件。
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909077"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="f41d5-103">政府團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="f41d5-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="f41d5-104">原則套件目前無法在 Microsoft 365 政府版 GCC 或 DoD 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="f41d5-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="f41d5-105">概觀</span><span class="sxs-lookup"><span data-stu-id="f41d5-105">Overview</span></span>

<span data-ttu-id="f41d5-106">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="f41d5-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f41d5-107">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="f41d5-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="f41d5-108">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="f41d5-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="f41d5-109">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="f41d5-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="f41d5-110">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="f41d5-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="f41d5-111">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="f41d5-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="f41d5-112">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="f41d5-112">Messaging</span></span>
- <span data-ttu-id="f41d5-113">會議</span><span class="sxs-lookup"><span data-stu-id="f41d5-113">Meetings</span></span>
- <span data-ttu-id="f41d5-114">通話</span><span class="sxs-lookup"><span data-stu-id="f41d5-114">Calling</span></span>
- <span data-ttu-id="f41d5-115">App 設定</span><span class="sxs-lookup"><span data-stu-id="f41d5-115">App setup</span></span>
- <span data-ttu-id="f41d5-116">即時事件</span><span class="sxs-lookup"><span data-stu-id="f41d5-116">Live events</span></span>

<span data-ttu-id="f41d5-117">團隊目前包含適用于政府的下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="f41d5-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="f41d5-118">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="f41d5-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="f41d5-119">最適合用於</span><span class="sxs-lookup"><span data-stu-id="f41d5-119">Best used for</span></span>|<span data-ttu-id="f41d5-120">描述</span><span class="sxs-lookup"><span data-stu-id="f41d5-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="f41d5-121">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="f41d5-121">Public safety officer</span></span>  |<span data-ttu-id="f41d5-122">政府組織中的公用安全官員</span><span class="sxs-lookup"><span data-stu-id="f41d5-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="f41d5-123">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="f41d5-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="f41d5-124">第一線管理員</span><span class="sxs-lookup"><span data-stu-id="f41d5-124">Frontline manager</span></span>  |<span data-ttu-id="f41d5-125">第一線政府組織中的經理</span><span class="sxs-lookup"><span data-stu-id="f41d5-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="f41d5-126">建立一組原則，並將這些設定套用到貴組織中的第一線管理員。</span><span class="sxs-lookup"><span data-stu-id="f41d5-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="f41d5-127">第一線 worker</span><span class="sxs-lookup"><span data-stu-id="f41d5-127">Frontline worker</span></span>  |<span data-ttu-id="f41d5-128">在您的政府組織中第一線工人</span><span class="sxs-lookup"><span data-stu-id="f41d5-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="f41d5-129">建立一組原則，並將這些設定套用到貴組織中的第一線工作人員。</span><span class="sxs-lookup"><span data-stu-id="f41d5-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

<span data-ttu-id="f41d5-131">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="f41d5-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="f41d5-132">例如，當您將公用安全專員原則套件指派給貴組織中的使用者時，會針對套件中的每個原則，建立一個名為 PublicSafety_Officer 的原則。</span><span class="sxs-lookup"><span data-stu-id="f41d5-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="f41d5-134">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="f41d5-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="f41d5-135">檢視</span><span class="sxs-lookup"><span data-stu-id="f41d5-135">View</span></span>

<span data-ttu-id="f41d5-136">在指派套件之前，請查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="f41d5-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="f41d5-137">在 Microsoft Teams 系統管理中心的左側流覽中，選取 **[原則套件]**，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="f41d5-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="f41d5-138">决定預先定義的值是否適合貴組織，或者您是否需要根據組織的需求將它們自訂為更嚴格或更寬鬆的值。</span><span class="sxs-lookup"><span data-stu-id="f41d5-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="f41d5-139">自訂</span><span class="sxs-lookup"><span data-stu-id="f41d5-139">Customize</span></span>

<span data-ttu-id="f41d5-140">視需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="f41d5-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="f41d5-141">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="f41d5-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="f41d5-142">要編輯原則套件中原則的設定，請在 Microsoft Teams 系統管理中心，選取該原則套件，選取要編輯的原則名稱，然後選取 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="f41d5-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="f41d5-143">請記住，您可以在指派原則套件之後變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f41d5-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="f41d5-144">若要深入了解，請參閱 [自訂原則套件中的原則](manage-policy-packages.md#customize-policies-in-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="f41d5-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="f41d5-145">指派</span><span class="sxs-lookup"><span data-stu-id="f41d5-145">Assign</span></span>

<span data-ttu-id="f41d5-146">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="f41d5-146">Assign the policy package to users.</span></span> <span data-ttu-id="f41d5-147">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="f41d5-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="f41d5-148">將原則套件指派給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="f41d5-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="f41d5-149">若要將原則套件指派給一或多個使用者，請在 Microsoft Teams 系統管理中心的左側流覽窗格中，移至 **原則套件**，然後選取 **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="f41d5-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="f41d5-151">若要深入了解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="f41d5-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="f41d5-152">如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。</span><span class="sxs-lookup"><span data-stu-id="f41d5-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="f41d5-153">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="f41d5-153">Assign a policy package to a group</span></span>

<span data-ttu-id="f41d5-154">**這項功能在私人預覽中**</span><span class="sxs-lookup"><span data-stu-id="f41d5-154">**This feature is in private preview**</span></span>

<span data-ttu-id="f41d5-155">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="f41d5-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="f41d5-156">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="f41d5-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="f41d5-157">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="f41d5-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="f41d5-158">此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="f41d5-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="f41d5-159">若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="f41d5-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="f41d5-160">為一大組 (批) 使用者指派原則套件</span><span class="sxs-lookup"><span data-stu-id="f41d5-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="f41d5-161">使用批次原則套件指派，將原則套件一次性指派給大組使用者組。</span><span class="sxs-lookup"><span data-stu-id="f41d5-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="f41d5-162">您可以使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="f41d5-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="f41d5-163">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="f41d5-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="f41d5-164">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="f41d5-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="f41d5-165">您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="f41d5-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="f41d5-166">若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="f41d5-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f41d5-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="f41d5-167">Related topics</span></span>

[<span data-ttu-id="f41d5-168">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="f41d5-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="f41d5-169">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="f41d5-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
