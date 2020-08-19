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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804013"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="2e5c4-103">政府團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="2e5c4-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="2e5c4-104">原則套件目前無法在 Microsoft 365 政府版 GCC 或 DoD 部署中使用。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="2e5c4-105">概觀</span><span class="sxs-lookup"><span data-stu-id="2e5c4-105">Overview</span></span>

<span data-ttu-id="2e5c4-106">Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="2e5c4-107">原則套件可簡化原則管理，並有助於達到一致性。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="2e5c4-108">您可以自訂套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="2e5c4-109">當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="2e5c4-110">您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="2e5c4-111">原則套件根據套件預先定義下列各項原則：</span><span class="sxs-lookup"><span data-stu-id="2e5c4-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="2e5c4-112">訊息傳送</span><span class="sxs-lookup"><span data-stu-id="2e5c4-112">Messaging</span></span>
- <span data-ttu-id="2e5c4-113">會議</span><span class="sxs-lookup"><span data-stu-id="2e5c4-113">Meetings</span></span>
- <span data-ttu-id="2e5c4-114">通話</span><span class="sxs-lookup"><span data-stu-id="2e5c4-114">Calling</span></span>
- <span data-ttu-id="2e5c4-115">App 設定</span><span class="sxs-lookup"><span data-stu-id="2e5c4-115">App setup</span></span>
- <span data-ttu-id="2e5c4-116">即時活動</span><span class="sxs-lookup"><span data-stu-id="2e5c4-116">Live events</span></span>

<span data-ttu-id="2e5c4-117">團隊目前包含適用于政府的下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="2e5c4-118">Microsoft 團隊系統管理中心中的套件名稱</span><span class="sxs-lookup"><span data-stu-id="2e5c4-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="2e5c4-119">最適合用於</span><span class="sxs-lookup"><span data-stu-id="2e5c4-119">Best used for</span></span>|<span data-ttu-id="2e5c4-120">描述</span><span class="sxs-lookup"><span data-stu-id="2e5c4-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2e5c4-121">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="2e5c4-121">Public safety officer</span></span>  |<span data-ttu-id="2e5c4-122">政府組織中的公用安全官員</span><span class="sxs-lookup"><span data-stu-id="2e5c4-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="2e5c4-123">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="2e5c4-124">第一線員工管理員</span><span class="sxs-lookup"><span data-stu-id="2e5c4-124">Firstline manager</span></span>  |<span data-ttu-id="2e5c4-125">第一線員工政府組織中的經理</span><span class="sxs-lookup"><span data-stu-id="2e5c4-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="2e5c4-126">建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="2e5c4-127">第一線員工 worker</span><span class="sxs-lookup"><span data-stu-id="2e5c4-127">Firstline worker</span></span>  |<span data-ttu-id="2e5c4-128">在您的政府組織中第一線員工工人</span><span class="sxs-lookup"><span data-stu-id="2e5c4-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="2e5c4-129">建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

<span data-ttu-id="2e5c4-131">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="2e5c4-132">例如，當您將公用安全專員原則套件指派給貴組織中的使用者時，會針對套件中的每個原則，建立一個名為 PublicSafety_Officer 的原則。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="2e5c4-134">管理原則套件</span><span class="sxs-lookup"><span data-stu-id="2e5c4-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="2e5c4-135">檢視</span><span class="sxs-lookup"><span data-stu-id="2e5c4-135">View</span></span>

<span data-ttu-id="2e5c4-136">在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="2e5c4-137">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，選取套件名稱，然後選取原則名稱。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="2e5c4-138">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="2e5c4-139">自訂</span><span class="sxs-lookup"><span data-stu-id="2e5c4-139">Customize</span></span>

<span data-ttu-id="2e5c4-140">根據需要自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="2e5c4-141">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="2e5c4-142">若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="2e5c4-143">請記住，在指派原則套件之後，您也可以變更套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="2e5c4-144">若要深入瞭解，請參閱 [在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="2e5c4-145">為</span><span class="sxs-lookup"><span data-stu-id="2e5c4-145">Assign</span></span>

<span data-ttu-id="2e5c4-146">將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-146">Assign the policy package to users.</span></span> <span data-ttu-id="2e5c4-147">若要將原則套件指派給一或多個使用者，請按一下 [ **管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="2e5c4-148">您也可以 [使用 PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 將原則套件指派給大量的使用者。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="2e5c4-149">如需如何使用 Microsoft 團隊系統管理中心或 PowerShell 指派原則套件的步驟，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-gov-assign.png)

<span data-ttu-id="2e5c4-151">如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。</span><span class="sxs-lookup"><span data-stu-id="2e5c4-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2e5c4-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="2e5c4-152">Related topics</span></span>

[<span data-ttu-id="2e5c4-153">在 Teams 中管理原則套件</span><span class="sxs-lookup"><span data-stu-id="2e5c4-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="2e5c4-154">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="2e5c4-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
