---
title: 政府團隊原則套件
author: lanachin
ms.author: v-lanac
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
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908592"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="5f982-103">政府團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="5f982-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="5f982-104">原則套件目前無法在 Microsoft 365 政府版 GCC 或 DoD 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="5f982-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="5f982-105">概觀</span><span class="sxs-lookup"><span data-stu-id="5f982-105">Overview</span></span>

<span data-ttu-id="5f982-106">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="5f982-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="5f982-107">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="5f982-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="5f982-108">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="5f982-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="5f982-109">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="5f982-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="5f982-110">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="5f982-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="5f982-111">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="5f982-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="5f982-112">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="5f982-112">Messaging</span></span>
- <span data-ttu-id="5f982-113">會議</span><span class="sxs-lookup"><span data-stu-id="5f982-113">Meetings</span></span>
- <span data-ttu-id="5f982-114">通話</span><span class="sxs-lookup"><span data-stu-id="5f982-114">Calling</span></span>
- <span data-ttu-id="5f982-115">App 設定</span><span class="sxs-lookup"><span data-stu-id="5f982-115">App setup</span></span>
- <span data-ttu-id="5f982-116">即時活動</span><span class="sxs-lookup"><span data-stu-id="5f982-116">Live events</span></span>

<span data-ttu-id="5f982-117">團隊目前包含適用于政府的下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="5f982-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="5f982-118">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="5f982-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="5f982-119">最適合用於</span><span class="sxs-lookup"><span data-stu-id="5f982-119">Best used for</span></span>|<span data-ttu-id="5f982-120">描述</span><span class="sxs-lookup"><span data-stu-id="5f982-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="5f982-121">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="5f982-121">Public safety officer</span></span>  |<span data-ttu-id="5f982-122">政府組織中的公用安全官員</span><span class="sxs-lookup"><span data-stu-id="5f982-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="5f982-123">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="5f982-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="5f982-124">第一線員工管理員</span><span class="sxs-lookup"><span data-stu-id="5f982-124">Firstline manager</span></span>  |<span data-ttu-id="5f982-125">第一線員工政府組織中的經理</span><span class="sxs-lookup"><span data-stu-id="5f982-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="5f982-126">建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。</span><span class="sxs-lookup"><span data-stu-id="5f982-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="5f982-127">第一線員工 worker</span><span class="sxs-lookup"><span data-stu-id="5f982-127">Firstline worker</span></span>  |<span data-ttu-id="5f982-128">在您的政府組織中第一線員工工人</span><span class="sxs-lookup"><span data-stu-id="5f982-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="5f982-129">建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="5f982-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

<span data-ttu-id="5f982-131">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="5f982-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="5f982-132">例如，當您將公用安全專員原則套件指派給貴組織中的使用者時，會針對套件中的每個原則，建立一個名為 PublicSafety_Officer 的原則。</span><span class="sxs-lookup"><span data-stu-id="5f982-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="5f982-134">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="5f982-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="5f982-135">檢視</span><span class="sxs-lookup"><span data-stu-id="5f982-135">View</span></span>

<span data-ttu-id="5f982-136">在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="5f982-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="5f982-137">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件** ]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="5f982-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="5f982-138">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="5f982-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="5f982-139">自訂</span><span class="sxs-lookup"><span data-stu-id="5f982-139">Customize</span></span>

<span data-ttu-id="5f982-140">根據需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="5f982-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="5f982-141">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="5f982-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="5f982-142">若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="5f982-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="5f982-143">請記住，在指派原則套件之後，您也可以變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="5f982-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="5f982-144">若要深入瞭解，請參閱 [在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。</span><span class="sxs-lookup"><span data-stu-id="5f982-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="5f982-145">為</span><span class="sxs-lookup"><span data-stu-id="5f982-145">Assign</span></span>

<span data-ttu-id="5f982-146">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="5f982-146">Assign the policy package to users.</span></span> <span data-ttu-id="5f982-147">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="5f982-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="5f982-148">指派原則套件給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="5f982-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="5f982-149">若要將原則套件指派給一或多個使用者，請在 [Microsoft 團隊管理中心] 的左導覽中，移至 [ **原則套件** ]，然後選取 [ **管理使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="5f982-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="5f982-151">若要深入瞭解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="5f982-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="5f982-152">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="5f982-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="5f982-153">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="5f982-153">Assign a policy package to a group</span></span>

<span data-ttu-id="5f982-154">**此功能是私人預覽**</span><span class="sxs-lookup"><span data-stu-id="5f982-154">**This feature is in private preview**</span></span>

<span data-ttu-id="5f982-155">[原則套件指派給群組] 可讓您將多個原則指派給使用者群組，例如安全群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="5f982-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="5f982-156">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="5f982-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="5f982-157">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="5f982-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="5f982-158">建議將此方法用於最多50000個使用者的群組，但也會搭配較大的群組使用。</span><span class="sxs-lookup"><span data-stu-id="5f982-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="5f982-159">若要深入瞭解，請參閱 [將原則套件指派給群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="5f982-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="5f982-160">將原則套件指派給大型集 (批次) 使用者</span><span class="sxs-lookup"><span data-stu-id="5f982-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="5f982-161">使用批次原則套件指派來一次將原則套件指派給大型的使用者組。</span><span class="sxs-lookup"><span data-stu-id="5f982-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="5f982-162">您使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="5f982-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="5f982-163">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="5f982-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="5f982-164">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="5f982-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="5f982-165">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="5f982-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="5f982-166">若要深入瞭解，請參閱 [將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="5f982-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5f982-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="5f982-167">Related topics</span></span>

[<span data-ttu-id="5f982-168">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="5f982-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="5f982-169">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="5f982-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
