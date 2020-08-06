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
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578188"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="a0a2c-103">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="a0a2c-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="a0a2c-104">概觀</span><span class="sxs-lookup"><span data-stu-id="a0a2c-104">Overview</span></span>

<span data-ttu-id="a0a2c-105">Microsoft 團隊中的[原則套件](manage-policy-packages.md)是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a0a2c-106">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="a0a2c-107">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="a0a2c-108">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="a0a2c-109">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="a0a2c-110">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="a0a2c-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="a0a2c-111">會議</span><span class="sxs-lookup"><span data-stu-id="a0a2c-111">Meetings</span></span>
- <span data-ttu-id="a0a2c-112">即時活動</span><span class="sxs-lookup"><span data-stu-id="a0a2c-112">Live events</span></span>
- <span data-ttu-id="a0a2c-113">通話</span><span class="sxs-lookup"><span data-stu-id="a0a2c-113">Calling</span></span>
- <span data-ttu-id="a0a2c-114">傳訊</span><span class="sxs-lookup"><span data-stu-id="a0a2c-114">Messaging</span></span>
- <span data-ttu-id="a0a2c-115">Teams</span><span class="sxs-lookup"><span data-stu-id="a0a2c-115">Teams</span></span>
- <span data-ttu-id="a0a2c-116">App 設定</span><span class="sxs-lookup"><span data-stu-id="a0a2c-116">App setup</span></span>

<span data-ttu-id="a0a2c-117">團隊目前包含下列醫療保健原則封裝。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="a0a2c-118">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="a0a2c-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="a0a2c-119">最適合用於</span><span class="sxs-lookup"><span data-stu-id="a0a2c-119">Best used for</span></span>|<span data-ttu-id="a0a2c-120">描述</span><span class="sxs-lookup"><span data-stu-id="a0a2c-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a0a2c-121">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="a0a2c-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="a0a2c-122">您的保健組織中的臨床工作者</span><span class="sxs-lookup"><span data-stu-id="a0a2c-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="a0a2c-123">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="a0a2c-124">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="a0a2c-124">Healthcare information worker</span></span>  |<span data-ttu-id="a0a2c-125">您的保健組織中的資訊工作者</span><span class="sxs-lookup"><span data-stu-id="a0a2c-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="a0a2c-126">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="a0a2c-127">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="a0a2c-127">Healthcare patient room</span></span>  |<span data-ttu-id="a0a2c-128">患者房間裝置</span><span class="sxs-lookup"><span data-stu-id="a0a2c-128">Patient room devices</span></span>|<span data-ttu-id="a0a2c-129">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

<span data-ttu-id="a0a2c-131">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="a0a2c-132">例如，當您將醫療保健臨床工人原則套件指派給您組織中的臨床醫師時，會針對套件中的每個原則，建立一個名為 Healthcare_ClinicalWorker 的原則。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="a0a2c-134">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="a0a2c-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="a0a2c-135">檢視</span><span class="sxs-lookup"><span data-stu-id="a0a2c-135">View</span></span>

<span data-ttu-id="a0a2c-136">在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a0a2c-137">在 Microsoft [團隊管理中心] 的左導覽中，選取 [**原則套件**]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="a0a2c-138">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="a0a2c-139">自訂</span><span class="sxs-lookup"><span data-stu-id="a0a2c-139">Customize</span></span>

<span data-ttu-id="a0a2c-140">根據需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="a0a2c-141">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="a0a2c-142">若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="a0a2c-143">請記住，在指派原則套件之後，您也可以變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="a0a2c-144">若要深入瞭解，請參閱[在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="a0a2c-145">為</span><span class="sxs-lookup"><span data-stu-id="a0a2c-145">Assign</span></span>

<span data-ttu-id="a0a2c-146">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-146">Assign the policy package to users.</span></span> <span data-ttu-id="a0a2c-147">若要將原則套件指派給一或多個使用者，請按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="a0a2c-148">您也可以使用 PowerShell 將原則套件指派給大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="a0a2c-149">如需如何指派原則套件的步驟，請參閱[指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="a0a2c-151">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="a0a2c-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0a2c-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="a0a2c-152">Related topics</span></span>

[<span data-ttu-id="a0a2c-153">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="a0a2c-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="a0a2c-154">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="a0a2c-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
