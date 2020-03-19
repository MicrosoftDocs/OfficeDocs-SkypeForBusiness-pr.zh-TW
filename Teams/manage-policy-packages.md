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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用及管理原則套件。
ms.openlocfilehash: d7c0ded990225b969579f50ea5f87a32efebe388
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2020
ms.locfileid: "42857992"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="a9f52-103">管理 Microsoft 團隊中的原則套件</span><span class="sxs-lookup"><span data-stu-id="a9f52-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="a9f52-104">Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9f52-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a9f52-105">我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="a9f52-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="a9f52-106">當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中原則的設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="a9f52-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="a9f52-107">我們的政府雲端社區（GCC）組織無法使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="a9f52-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="a9f52-108">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="a9f52-108">What is a policy package?</span></span>

<span data-ttu-id="a9f52-109">[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。</span><span class="sxs-lookup"><span data-stu-id="a9f52-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="a9f52-110">團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。</span><span class="sxs-lookup"><span data-stu-id="a9f52-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="a9f52-111">團隊目前包含下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="a9f52-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="a9f52-112">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="a9f52-112">**Package name**</span></span>  |<span data-ttu-id="a9f52-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="a9f52-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="a9f52-114">教育版（高等教育學生）</span><span class="sxs-lookup"><span data-stu-id="a9f52-114">Education (Higher education student)</span></span>    |<span data-ttu-id="a9f52-115">建立一組可套用至較高教育學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="a9f52-116">教育版（主要學校學生）</span><span class="sxs-lookup"><span data-stu-id="a9f52-116">Education (Primary school student)</span></span>   |<span data-ttu-id="a9f52-117">建立適用于主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="a9f52-118">教育版（副學校學生）</span><span class="sxs-lookup"><span data-stu-id="a9f52-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="a9f52-119">建立一組可套用至副學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="a9f52-120">教育版（教師）</span><span class="sxs-lookup"><span data-stu-id="a9f52-120">Education (Teacher)</span></span>    |<span data-ttu-id="a9f52-121">建立適用于教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="a9f52-122">商務語音</span><span class="sxs-lookup"><span data-stu-id="a9f52-122">Business voice</span></span> |<span data-ttu-id="a9f52-123">建立應用程式設定原則，其中包含商務語音體驗的 app。</span><span class="sxs-lookup"><span data-stu-id="a9f52-123">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="a9f52-124">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="a9f52-124">Public safety officer</span></span>   |<span data-ttu-id="a9f52-125">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="a9f52-125">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="a9f52-126">醫療保健（臨床員工）</span><span class="sxs-lookup"><span data-stu-id="a9f52-126">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="a9f52-127">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="a9f52-127">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="a9f52-128">醫療保健（資訊工作者）</span><span class="sxs-lookup"><span data-stu-id="a9f52-128">Healthcare (Information worker)</span></span>  |<span data-ttu-id="a9f52-129">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="a9f52-129">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="a9f52-130">我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。</span><span class="sxs-lookup"><span data-stu-id="a9f52-130">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="a9f52-131">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="a9f52-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="a9f52-132">例如，當您將教育版（教師）原則套件指派給學校的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="a9f52-132">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版（教師）原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="a9f52-134">如何使用原則套件</span><span class="sxs-lookup"><span data-stu-id="a9f52-134">How to use policy packages</span></span>

<span data-ttu-id="a9f52-135">下列概要說明如何在您的組織中使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="a9f52-135">The following outlines how to use policy packages in your organization.</span></span>

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- <span data-ttu-id="a9f52-137">[**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-137">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a9f52-138">請確定您已瞭解每個設定，然後決定預先定義的值是否適合您的組織，或者您是否需要根據貴組織的需求將它們變更為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="a9f52-138">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="a9f52-139">如果刪除策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-139">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="a9f52-140">當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。</span><span class="sxs-lookup"><span data-stu-id="a9f52-140">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="a9f52-141">**[指派](#assign-a-policy-package)**：將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="a9f52-141">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="a9f52-142">請記住，在您指派套件前，不會建立原則套件中的原則，在您指派套件之前，您可以變更套件中個別原則的設定。</span><span class="sxs-lookup"><span data-stu-id="a9f52-142">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="a9f52-143">**[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="a9f52-143">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="a9f52-144">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9f52-144">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="a9f52-145">以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="a9f52-145">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="a9f52-146">在原則套件中查看原則的設定</span><span class="sxs-lookup"><span data-stu-id="a9f52-146">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="a9f52-147">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-147">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a9f52-148">按一下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="a9f52-148">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="a9f52-149">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="a9f52-149">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="a9f52-150">指派原則套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="a9f52-150">Assign a policy package to one user</span></span>

1. <span data-ttu-id="a9f52-151">在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。</span><span class="sxs-lookup"><span data-stu-id="a9f52-151">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a9f52-152">在使用者的頁面上，按一下 [**原則**]，然後按一下 [**原則封裝**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-152">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="a9f52-153">在 [**指派原則套件**] 窗格中，選取您要指派的套件，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-153">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="a9f52-154">指派原則套件給多位使用者</span><span class="sxs-lookup"><span data-stu-id="a9f52-154">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="a9f52-155">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="a9f52-155">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a9f52-156">按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-156">Click **Manage users**.</span></span>
3. <span data-ttu-id="a9f52-157">在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a9f52-158">針對您要新增的每個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="a9f52-158">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a9f52-159">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-159">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="a9f52-160">在原則套件中自訂策略</span><span class="sxs-lookup"><span data-stu-id="a9f52-160">Customize policies in a policy package</span></span>

<span data-ttu-id="a9f52-161">您可以透過 [**原則套件**] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a9f52-161">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="a9f52-162">在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a9f52-162">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="a9f52-163">按一下 [**原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-163">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="a9f52-164">按一下原則類型。</span><span class="sxs-lookup"><span data-stu-id="a9f52-164">Click the policy type.</span></span>  <span data-ttu-id="a9f52-165">例如，按一下 [**訊息原則**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-165">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="a9f52-166">按一下您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="a9f52-166">Click the policy you want to edit.</span></span> <span data-ttu-id="a9f52-167">連結至原則套件的原則與原則套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="a9f52-167">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="a9f52-168">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a9f52-168">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a9f52-169">疑難排解</span><span class="sxs-lookup"><span data-stu-id="a9f52-169">Troubleshooting</span></span>

<span data-ttu-id="a9f52-170">**當您指派原則套件時，收到錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="a9f52-170">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="a9f52-171">如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="a9f52-171">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="a9f52-172">將原則套件重新指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="a9f52-172">Reassign the policy package to your users.</span></span> <span data-ttu-id="a9f52-173">重試此操作通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="a9f52-173">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a9f52-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="a9f52-174">Related topics</span></span>

[<span data-ttu-id="a9f52-175">適用於教育界管理員的 Microsoft Teams 原則套件</span><span class="sxs-lookup"><span data-stu-id="a9f52-175">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
