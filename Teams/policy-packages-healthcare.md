---
title: 醫療保健的團隊原則套件
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
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908512"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="b51bd-103">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="b51bd-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="b51bd-104">概觀</span><span class="sxs-lookup"><span data-stu-id="b51bd-104">Overview</span></span>

<span data-ttu-id="b51bd-105">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="b51bd-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b51bd-106">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="b51bd-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="b51bd-107">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="b51bd-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="b51bd-108">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="b51bd-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b51bd-109">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="b51bd-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="b51bd-110">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="b51bd-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="b51bd-111">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="b51bd-111">Messaging</span></span>
- <span data-ttu-id="b51bd-112">會議</span><span class="sxs-lookup"><span data-stu-id="b51bd-112">Meetings</span></span>
- <span data-ttu-id="b51bd-113">通話</span><span class="sxs-lookup"><span data-stu-id="b51bd-113">Calling</span></span>
- <span data-ttu-id="b51bd-114">App 設定</span><span class="sxs-lookup"><span data-stu-id="b51bd-114">App setup</span></span>
- <span data-ttu-id="b51bd-115">即時活動</span><span class="sxs-lookup"><span data-stu-id="b51bd-115">Live events</span></span>

<span data-ttu-id="b51bd-116">團隊目前包含下列醫療保健原則封裝。</span><span class="sxs-lookup"><span data-stu-id="b51bd-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="b51bd-117">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="b51bd-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="b51bd-118">最適合用於</span><span class="sxs-lookup"><span data-stu-id="b51bd-118">Best used for</span></span>|<span data-ttu-id="b51bd-119">描述</span><span class="sxs-lookup"><span data-stu-id="b51bd-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b51bd-120">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="b51bd-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="b51bd-121">您的保健組織中的臨床工作者</span><span class="sxs-lookup"><span data-stu-id="b51bd-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="b51bd-122">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="b51bd-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b51bd-123">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="b51bd-123">Healthcare information worker</span></span>  |<span data-ttu-id="b51bd-124">您的保健組織中的資訊工作者</span><span class="sxs-lookup"><span data-stu-id="b51bd-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="b51bd-125">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="b51bd-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b51bd-126">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="b51bd-126">Healthcare patient room</span></span>  |<span data-ttu-id="b51bd-127">患者房間裝置</span><span class="sxs-lookup"><span data-stu-id="b51bd-127">Patient room devices</span></span>|<span data-ttu-id="b51bd-128">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="b51bd-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

<span data-ttu-id="b51bd-130">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="b51bd-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="b51bd-131">例如，當您將醫療保健臨床工人原則套件指派給您組織中的臨床醫師時，會針對套件中的每個原則，建立一個名為 Healthcare_ClinicalWorker 的原則。</span><span class="sxs-lookup"><span data-stu-id="b51bd-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="b51bd-133">開始使用原則套件</span><span class="sxs-lookup"><span data-stu-id="b51bd-133">Get started with policy packages</span></span>

<span data-ttu-id="b51bd-134">若要開始使用醫療保健原則套件，請在 Microsoft 系統管理中心加入中樞上，選取 [ **保健** ]，然後選取 [ **依角色指派原則設定** ]。</span><span class="sxs-lookup"><span data-stu-id="b51bd-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="b51bd-135">準備好開始使用之後，請決定您要將組織中的個別人指派給哪個原則套件。</span><span class="sxs-lookup"><span data-stu-id="b51bd-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="b51bd-136">選取 [ **查看原則詳細資料** ]，進一步瞭解套件中的特定原則及其各自的設定。</span><span class="sxs-lookup"><span data-stu-id="b51bd-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="b51bd-137">在團隊系統管理中心中作業分派之後， [就可以自訂](manage-policy-packages.md#customize-policies-in-a-policy-package) 這些功能。</span><span class="sxs-lookup"><span data-stu-id="b51bd-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="b51bd-138">選擇一或多個要指派的套件，然後按一下 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="b51bd-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="b51bd-139">您可以搜尋並將人員新增至最適合自己角色的原則套件中。</span><span class="sxs-lookup"><span data-stu-id="b51bd-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="b51bd-140">一次無法將一個人指派給多個原則套件。</span><span class="sxs-lookup"><span data-stu-id="b51bd-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="b51bd-141">將人員新增至正確的原則套件後，請 **完成** 您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="b51bd-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="b51bd-142">您可以繼續自訂及管理 Microsoft 團隊系統管理中心的原則套件。</span><span class="sxs-lookup"><span data-stu-id="b51bd-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="b51bd-143">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="b51bd-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="b51bd-144">檢視</span><span class="sxs-lookup"><span data-stu-id="b51bd-144">View</span></span>

<span data-ttu-id="b51bd-145">在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="b51bd-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b51bd-146">在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件** ]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="b51bd-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="b51bd-147">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="b51bd-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="b51bd-148">自訂</span><span class="sxs-lookup"><span data-stu-id="b51bd-148">Customize</span></span>

<span data-ttu-id="b51bd-149">根據需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b51bd-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="b51bd-150">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="b51bd-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="b51bd-151">若要編輯原則套件中原則的設定，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件** ]，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="b51bd-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="b51bd-152">請記住，在指派原則套件之後，您也可以變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="b51bd-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="b51bd-153">若要深入瞭解，請參閱 [在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。</span><span class="sxs-lookup"><span data-stu-id="b51bd-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="b51bd-154">為</span><span class="sxs-lookup"><span data-stu-id="b51bd-154">Assign</span></span>

<span data-ttu-id="b51bd-155">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b51bd-155">Assign the policy package to users.</span></span> <span data-ttu-id="b51bd-156">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="b51bd-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="b51bd-157">指派原則套件給一或多個使用者</span><span class="sxs-lookup"><span data-stu-id="b51bd-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="b51bd-158">若要將原則套件指派給一或多個使用者，請在 [Microsoft 團隊管理中心] 的左導覽中，移至 [ **原則套件** ]，然後選取 [ **管理使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="b51bd-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="b51bd-160">若要深入瞭解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="b51bd-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="b51bd-161">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="b51bd-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="b51bd-162">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="b51bd-162">Assign a policy package to a group</span></span>

<span data-ttu-id="b51bd-163">**此功能是私人預覽**</span><span class="sxs-lookup"><span data-stu-id="b51bd-163">**This feature is in private preview**</span></span>

<span data-ttu-id="b51bd-164">[原則套件指派給群組] 可讓您將多個原則指派給使用者群組，例如安全群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="b51bd-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="b51bd-165">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b51bd-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b51bd-166">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="b51bd-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="b51bd-167">建議將此方法用於最多50000個使用者的群組，但也會搭配較大的群組使用。</span><span class="sxs-lookup"><span data-stu-id="b51bd-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="b51bd-168">若要深入瞭解，請參閱 [將原則套件指派給群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="b51bd-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="b51bd-169">將原則套件指派給大型集 (批次) 使用者</span><span class="sxs-lookup"><span data-stu-id="b51bd-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="b51bd-170">使用批次原則套件指派來一次將原則套件指派給大型的使用者組。</span><span class="sxs-lookup"><span data-stu-id="b51bd-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="b51bd-171">您使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="b51bd-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b51bd-172">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="b51bd-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="b51bd-173">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="b51bd-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b51bd-174">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="b51bd-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="b51bd-175">若要深入瞭解，請參閱 [將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="b51bd-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b51bd-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="b51bd-176">Related topics</span></span>

[<span data-ttu-id="b51bd-177">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="b51bd-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="b51bd-178">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="b51bd-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
