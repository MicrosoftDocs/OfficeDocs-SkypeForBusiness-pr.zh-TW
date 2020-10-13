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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理您的保健組織的小組原則套件。
ms.openlocfilehash: e55102e07f7ffc77dc67c5d6697cb754c398cc40
ms.sourcegitcommit: a043bde507a9f6747fdd2063dd085edb3c1d6c3c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "48427168"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="b2d8c-103">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="b2d8c-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="b2d8c-104">概觀</span><span class="sxs-lookup"><span data-stu-id="b2d8c-104">Overview</span></span>

<span data-ttu-id="b2d8c-105">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b2d8c-106">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="b2d8c-107">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="b2d8c-108">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b2d8c-109">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="b2d8c-110">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="b2d8c-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="b2d8c-111">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="b2d8c-111">Messaging</span></span>
- <span data-ttu-id="b2d8c-112">會議</span><span class="sxs-lookup"><span data-stu-id="b2d8c-112">Meetings</span></span>
- <span data-ttu-id="b2d8c-113">通話</span><span class="sxs-lookup"><span data-stu-id="b2d8c-113">Calling</span></span>
- <span data-ttu-id="b2d8c-114">App 設定</span><span class="sxs-lookup"><span data-stu-id="b2d8c-114">App setup</span></span>
- <span data-ttu-id="b2d8c-115">即時活動</span><span class="sxs-lookup"><span data-stu-id="b2d8c-115">Live events</span></span>

<span data-ttu-id="b2d8c-116">團隊目前包含下列醫療保健原則封裝。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="b2d8c-117">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="b2d8c-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="b2d8c-118">最適合用於</span><span class="sxs-lookup"><span data-stu-id="b2d8c-118">Best used for</span></span>|<span data-ttu-id="b2d8c-119">描述</span><span class="sxs-lookup"><span data-stu-id="b2d8c-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="b2d8c-120">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="b2d8c-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="b2d8c-121">您的保健組織中的臨床工作者</span><span class="sxs-lookup"><span data-stu-id="b2d8c-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="b2d8c-122">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b2d8c-123">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="b2d8c-123">Healthcare information worker</span></span>  |<span data-ttu-id="b2d8c-124">您的保健組織中的資訊工作者</span><span class="sxs-lookup"><span data-stu-id="b2d8c-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="b2d8c-125">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b2d8c-126">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="b2d8c-126">Healthcare patient room</span></span>  |<span data-ttu-id="b2d8c-127">患者房間裝置</span><span class="sxs-lookup"><span data-stu-id="b2d8c-127">Patient room devices</span></span>|<span data-ttu-id="b2d8c-128">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

<span data-ttu-id="b2d8c-130">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="b2d8c-131">例如，當您將醫療保健臨床工人原則套件指派給您組織中的臨床醫師時，會針對套件中的每個原則，建立一個名為 Healthcare_ClinicalWorker 的原則。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="b2d8c-133">開始使用原則套件</span><span class="sxs-lookup"><span data-stu-id="b2d8c-133">Get started with policy packages</span></span>

<span data-ttu-id="b2d8c-134">若要開始使用醫療保健原則套件，請在 Microsoft 系統管理中心加入中樞上，選取 [ **醫療保健基礎**產品]，然後選取 [ **依角色指派原則設定**]。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare basics**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="b2d8c-135">準備好開始使用之後，請決定您要將組織中的個別人指派給哪個原則套件。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="b2d8c-136">選取 [ **查看原則詳細資料** ]，進一步瞭解套件中的特定原則及其各自的設定。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="b2d8c-137">在團隊系統管理中心中作業分派之後， [就可以自訂](manage-policy-packages.md#customize-policies-in-a-policy-package) 這些功能。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="b2d8c-138">選擇一或多個要指派的套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="b2d8c-139">您可以搜尋並將人員新增至最適合自己角色的原則套件中。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="b2d8c-140">一次無法將一個人指派給多個原則套件。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="b2d8c-141">將人員新增至正確的原則套件後，請 **完成** 您的選取專案。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="b2d8c-142">您可以繼續自訂及管理 Microsoft 團隊系統管理中心的原則套件。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="b2d8c-143">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="b2d8c-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="b2d8c-144">檢視</span><span class="sxs-lookup"><span data-stu-id="b2d8c-144">View</span></span>

<span data-ttu-id="b2d8c-145">在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="b2d8c-146">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-146">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="b2d8c-147">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="b2d8c-148">自訂</span><span class="sxs-lookup"><span data-stu-id="b2d8c-148">Customize</span></span>

<span data-ttu-id="b2d8c-149">根據需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="b2d8c-150">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="b2d8c-151">若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-151">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="b2d8c-152">請記住，在指派原則套件之後，您也可以變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="b2d8c-153">若要深入瞭解，請參閱 [在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="b2d8c-154">為</span><span class="sxs-lookup"><span data-stu-id="b2d8c-154">Assign</span></span>

<span data-ttu-id="b2d8c-155">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-155">Assign the policy package to users.</span></span> <span data-ttu-id="b2d8c-156">若要將原則套件指派給一或多個使用者，請按一下 [ **管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-156">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="b2d8c-157">您也可以 [使用 PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 將原則套件指派給大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-157">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="b2d8c-158">如需如何使用 Microsoft 團隊系統管理中心或 PowerShell 指派原則套件的步驟，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-158">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="b2d8c-160">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="b2d8c-160">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b2d8c-161">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2d8c-161">Related topics</span></span>

[<span data-ttu-id="b2d8c-162">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="b2d8c-162">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="b2d8c-163">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="b2d8c-163">Assign policies to your users in Teams</span></span>](assign-policies.md)
