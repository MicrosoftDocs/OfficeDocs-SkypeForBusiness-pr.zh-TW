---
title: 管理 Microsoft 團隊中的原則套件
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用及管理原則套件。
ms.openlocfilehash: 87fda86d1dbe09858c3850dc92ee5085666d8ba7
ms.sourcegitcommit: 52d924e654909a2017ce42ba9d1b4bbc3efa9262
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2020
ms.locfileid: "41205290"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="652d9-103">管理 Microsoft 團隊中的原則套件</span><span class="sxs-lookup"><span data-stu-id="652d9-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="652d9-104">Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="652d9-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="652d9-105">我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="652d9-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="652d9-106">當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中原則的設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="652d9-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="652d9-107">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="652d9-107">What is a policy package?</span></span>

<span data-ttu-id="652d9-108">[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。</span><span class="sxs-lookup"><span data-stu-id="652d9-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="652d9-109">團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。</span><span class="sxs-lookup"><span data-stu-id="652d9-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="652d9-110">團隊目前包含下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="652d9-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="652d9-111">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="652d9-111">**Package name**</span></span>  |<span data-ttu-id="652d9-112">**描述**</span><span class="sxs-lookup"><span data-stu-id="652d9-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="652d9-113">教育版（高等教育學生）</span><span class="sxs-lookup"><span data-stu-id="652d9-113">Education (Higher education student)</span></span>    |<span data-ttu-id="652d9-114">建立一組可套用至較高教育學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="652d9-115">教育版（主要學校學生）</span><span class="sxs-lookup"><span data-stu-id="652d9-115">Education (Primary school student)</span></span>   |<span data-ttu-id="652d9-116">建立適用于主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="652d9-117">教育版（副學校學生）</span><span class="sxs-lookup"><span data-stu-id="652d9-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="652d9-118">建立一組可套用至副學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="652d9-119">教育版（教師）</span><span class="sxs-lookup"><span data-stu-id="652d9-119">Education (Teacher)</span></span>    |<span data-ttu-id="652d9-120">建立適用于教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="652d9-121">商務語音</span><span class="sxs-lookup"><span data-stu-id="652d9-121">Business voice</span></span> |<span data-ttu-id="652d9-122">建立應用程式設定原則，其中包含商務語音體驗的 app。</span><span class="sxs-lookup"><span data-stu-id="652d9-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="652d9-123">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="652d9-123">Public safety officer</span></span>   |<span data-ttu-id="652d9-124">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="652d9-124">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="652d9-125">我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。</span><span class="sxs-lookup"><span data-stu-id="652d9-125">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="652d9-126">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="652d9-126">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="652d9-127">例如，當您將教育版（教師）原則套件指派給學校的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="652d9-127">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版（教師）原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="652d9-129">如何使用原則套件</span><span class="sxs-lookup"><span data-stu-id="652d9-129">How to use policy packages</span></span>

<span data-ttu-id="652d9-130">下列概要說明如何在您的組織中使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="652d9-130">The following outlines how to use policy packages in your organization.</span></span>

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- <span data-ttu-id="652d9-132">[**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-132">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="652d9-133">請確定您已瞭解每個設定，然後決定預先定義的值是否適合您的組織，或者您是否需要根據貴組織的需求將它們變更為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="652d9-133">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="652d9-134">如果刪除策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-134">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="652d9-135">當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。</span><span class="sxs-lookup"><span data-stu-id="652d9-135">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="652d9-136">**[指派](#assign-a-policy-package)**：將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="652d9-136">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="652d9-137">請記住，在您指派套件前，不會建立原則套件中的原則，在您指派套件之前，您可以變更套件中個別原則的設定。</span><span class="sxs-lookup"><span data-stu-id="652d9-137">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="652d9-138">**[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="652d9-138">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="652d9-139">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="652d9-139">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="652d9-140">以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="652d9-140">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="652d9-141">在原則套件中查看原則的設定</span><span class="sxs-lookup"><span data-stu-id="652d9-141">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="652d9-142">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="652d9-142">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="652d9-143">按一下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="652d9-143">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="652d9-144">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="652d9-144">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="652d9-145">指派原則套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="652d9-145">Assign a policy package to one user</span></span>

1. <span data-ttu-id="652d9-146">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="652d9-146">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="652d9-147">在使用者的頁面上，按一下 [**原則**]，然後按一下 [**原則封裝**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-147">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="652d9-148">在 [**指派原則套件**] 窗格中，選取您要指派的套件，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-148">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="652d9-149">指派原則套件給多位使用者</span><span class="sxs-lookup"><span data-stu-id="652d9-149">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="652d9-150">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="652d9-150">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="652d9-151">按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-151">Click **Manage users**.</span></span>
3. <span data-ttu-id="652d9-152">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="652d9-153">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="652d9-153">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="652d9-154">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-154">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="652d9-155">在原則套件中自訂策略</span><span class="sxs-lookup"><span data-stu-id="652d9-155">Customize policies in a policy package</span></span>

<span data-ttu-id="652d9-156">您可以透過 [**原則套件**] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="652d9-156">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="652d9-157">在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="652d9-157">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="652d9-158">按一下 [**原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="652d9-158">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="652d9-159">按一下原則類型。</span><span class="sxs-lookup"><span data-stu-id="652d9-159">Click the policy type.</span></span>  <span data-ttu-id="652d9-160">例如，按一下 [**訊息原則**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-160">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="652d9-161">按一下您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="652d9-161">Click the policy you want to edit.</span></span> <span data-ttu-id="652d9-162">連結至原則套件的原則與原則套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="652d9-162">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="652d9-163">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="652d9-163">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="652d9-164">疑難排解</span><span class="sxs-lookup"><span data-stu-id="652d9-164">Troubleshooting</span></span>

<span data-ttu-id="652d9-165">**當您指派原則套件時，收到錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="652d9-165">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="652d9-166">如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="652d9-166">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="652d9-167">將原則套件重新指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="652d9-167">Reassign the policy package to your users.</span></span> <span data-ttu-id="652d9-168">重試此操作通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="652d9-168">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="652d9-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="652d9-169">Related topics</span></span>

[<span data-ttu-id="652d9-170">適用於教育界管理員的 Microsoft Teams 原則套件</span><span class="sxs-lookup"><span data-stu-id="652d9-170">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
