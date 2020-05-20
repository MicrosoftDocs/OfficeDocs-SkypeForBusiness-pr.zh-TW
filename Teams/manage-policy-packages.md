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
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理 Microsoft 團隊中的原則套件，以簡化、簡化及協助在管理使用者群組原則時提供一致性。
ms.openlocfilehash: 6927e2efae60370c0622f38570fc961794734f35
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322278"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="25081-103">管理 Microsoft 團隊中的原則套件</span><span class="sxs-lookup"><span data-stu-id="25081-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="25081-104">Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="25081-105">我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="25081-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="25081-106">當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中原則的設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="25081-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="25081-107">我們的政府雲端社區（GCC）組織無法使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="25081-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="25081-108">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="25081-108">What is a policy package?</span></span>

<span data-ttu-id="25081-109">[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。</span><span class="sxs-lookup"><span data-stu-id="25081-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="25081-110">團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。</span><span class="sxs-lookup"><span data-stu-id="25081-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="25081-111">團隊目前包含下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="25081-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="25081-112">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="25081-112">**Package name**</span></span>  |<span data-ttu-id="25081-113">**描述**</span><span class="sxs-lookup"><span data-stu-id="25081-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="25081-114">教育版（高等教育學生）</span><span class="sxs-lookup"><span data-stu-id="25081-114">Education (Higher education student)</span></span>    |<span data-ttu-id="25081-115">建立一組可套用至較高教育學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="25081-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="25081-116">教育版（主要學校學生）</span><span class="sxs-lookup"><span data-stu-id="25081-116">Education (Primary school student)</span></span>   |<span data-ttu-id="25081-117">建立適用于主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="25081-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="25081-118">教育版（副學校學生）</span><span class="sxs-lookup"><span data-stu-id="25081-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="25081-119">建立一組可套用至副學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="25081-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="25081-120">教育版（教師）</span><span class="sxs-lookup"><span data-stu-id="25081-120">Education (Teacher)</span></span>    |<span data-ttu-id="25081-121">建立適用于教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="25081-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="25081-122">教育版（使用遠端學習的主要學校老師）（預覽版）</span><span class="sxs-lookup"><span data-stu-id="25081-122">Education (Primary school teacher using remote learning) (Preview)</span></span>   |<span data-ttu-id="25081-123">建立一組原則，適用于主要老師，以在使用遠端學習時最大化學生的安全性與共同作業。</span><span class="sxs-lookup"><span data-stu-id="25081-123">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="25081-124">教育版（使用遠端學習的主要學校學生）（預覽版本）</span><span class="sxs-lookup"><span data-stu-id="25081-124">Education (Primary school student using remote learning) (Preview)</span></span>    |<span data-ttu-id="25081-125">建立一組原則，以套用到主要學生，在使用遠端教學時最大化學生的安全性與共同作業。</span><span class="sxs-lookup"><span data-stu-id="25081-125">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="25081-126">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="25081-126">Healthcare clinical worker</span></span>  |<span data-ttu-id="25081-127">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="25081-127">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="25081-128">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="25081-128">Healthcare information worker</span></span>  |<span data-ttu-id="25081-129">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="25081-129">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="25081-130">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="25081-130">Healthcare patient room</span></span>  |<span data-ttu-id="25081-131">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="25081-131">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="25081-132">中小型企業使用者（商務語音）</span><span class="sxs-lookup"><span data-stu-id="25081-132">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="25081-133">建立應用程式設定原則，其中包含商務語音體驗的 app。</span><span class="sxs-lookup"><span data-stu-id="25081-133">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="25081-134">中小型企業使用者（無需商務用語音）</span><span class="sxs-lookup"><span data-stu-id="25081-134">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="25081-135">建立一組原則與原則設定，適用于不含任何商務語音功能的中小型企業使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-135">Creates a set of policies and policy settings that apply to small and medium sized business users without any Business Voice features.</span></span>|
|<span data-ttu-id="25081-136">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="25081-136">Public safety officer</span></span>   |<span data-ttu-id="25081-137">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="25081-137">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|



> [!NOTE]
> <span data-ttu-id="25081-138">我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。</span><span class="sxs-lookup"><span data-stu-id="25081-138">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="25081-139">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="25081-139">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="25081-140">例如，當您將教育版（教師）原則套件指派給學校的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="25081-140">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版（教師）原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="25081-142">如何使用原則套件</span><span class="sxs-lookup"><span data-stu-id="25081-142">How to use policy packages</span></span>

<span data-ttu-id="25081-143">下列概要說明如何在您的組織中使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="25081-143">The following outlines how to use policy packages in your organization.</span></span>

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- <span data-ttu-id="25081-145">[**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在指派套件前，請先查看原則套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="25081-145">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="25081-146">請確定您已瞭解每個設定，然後決定預先定義的值是否適合您的組織，或者您是否需要根據貴組織的需求將它們變更為更具限制性或 lenient。</span><span class="sxs-lookup"><span data-stu-id="25081-146">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="25081-147">如果刪除策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="25081-147">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="25081-148">當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。</span><span class="sxs-lookup"><span data-stu-id="25081-148">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="25081-149">**[指派](#assign-a-policy-package)**：將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-149">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="25081-150">請記住，在您指派套件前，不會建立原則套件中的原則，在您指派套件之前，您可以變更套件中個別原則的設定。</span><span class="sxs-lookup"><span data-stu-id="25081-150">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="25081-151">**[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="25081-151">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="25081-152">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-152">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="25081-153">以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="25081-153">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="25081-154">在原則套件中查看原則的設定</span><span class="sxs-lookup"><span data-stu-id="25081-154">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="25081-155">在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="25081-155">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="25081-156">按一下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="25081-156">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="25081-157">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="25081-157">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="25081-158">指派原則套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="25081-158">Assign a policy package to one user</span></span>

1. <span data-ttu-id="25081-159">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-159">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="25081-160">在使用者的頁面上，按一下 [**原則**]，然後按一下 [**原則封裝**] 旁的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="25081-160">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="25081-161">在 [**指派原則套件**] 窗格中，選取您要指派的套件，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="25081-161">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="25081-162">指派原則套件給多位使用者</span><span class="sxs-lookup"><span data-stu-id="25081-162">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="25081-163">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="25081-163">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="25081-164">按一下 [**管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="25081-164">Click **Manage users**.</span></span>
3. <span data-ttu-id="25081-165">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="25081-165">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="25081-166">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="25081-166">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="25081-167">完成新增使用者後，請按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="25081-167">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="25081-168">將原則套件指派給大型使用者組（批次）</span><span class="sxs-lookup"><span data-stu-id="25081-168">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="25081-169">使用批次原則套件指派來一次將原則套件指派給大型的使用者組。</span><span class="sxs-lookup"><span data-stu-id="25081-169">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="25081-170">您使用[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="25081-170">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="25081-171">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="25081-171">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="25081-172">批次最多可包含20000個使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-172">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="25081-173">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-173">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="25081-174">若要深入瞭解，請參閱[將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="25081-174">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="25081-175">我們目前建議您逐一指派原則，以批次5000使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-175">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="25081-176">在這些時間增加需求期間，您可能會遇到處理時間的延遲。</span><span class="sxs-lookup"><span data-stu-id="25081-176">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="25081-177">為了將這些增加的處理時間的影響降至最低，我們建議您提交較小至5000個使用者的批次，並在前一個帳戶完成後提交每個批次。</span><span class="sxs-lookup"><span data-stu-id="25081-177">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="25081-178">在一般的商務時間以外提交批次也會有所説明。</span><span class="sxs-lookup"><span data-stu-id="25081-178">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="25081-179">在原則套件中自訂策略</span><span class="sxs-lookup"><span data-stu-id="25081-179">Customize policies in a policy package</span></span>

<span data-ttu-id="25081-180">您可以透過 [**原則套件**] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="25081-180">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="25081-181">在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="25081-181">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="25081-182">按一下 [**原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="25081-182">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="25081-183">按一下原則類型。</span><span class="sxs-lookup"><span data-stu-id="25081-183">Click the policy type.</span></span>  <span data-ttu-id="25081-184">例如，按一下 [**訊息原則**]。</span><span class="sxs-lookup"><span data-stu-id="25081-184">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="25081-185">按一下您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="25081-185">Click the policy you want to edit.</span></span> <span data-ttu-id="25081-186">連結至原則套件的原則與原則套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="25081-186">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="25081-187">進行您想要的變更，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="25081-187">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="25081-188">疑難排解</span><span class="sxs-lookup"><span data-stu-id="25081-188">Troubleshooting</span></span>

<span data-ttu-id="25081-189">**當您指派原則套件時，收到錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="25081-189">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="25081-190">如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="25081-190">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="25081-191">將原則套件重新指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="25081-191">Reassign the policy package to your users.</span></span> <span data-ttu-id="25081-192">重試此操作通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="25081-192">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25081-193">相關主題</span><span class="sxs-lookup"><span data-stu-id="25081-193">Related topics</span></span>

[<span data-ttu-id="25081-194">適用於教育界管理員的 Microsoft Teams 原則套件</span><span class="sxs-lookup"><span data-stu-id="25081-194">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
