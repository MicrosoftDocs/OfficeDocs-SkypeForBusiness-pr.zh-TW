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
ms.openlocfilehash: 986d64b11420877e146abc68f9f65c0503f49ff0
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918653"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="ee805-103">管理 Microsoft 團隊中的原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ee805-104">此文章中所討論的其中一個功能（ [自訂原則套件](#custom-policy-packages)）目前是私人預覽。</span><span class="sxs-lookup"><span data-stu-id="ee805-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="ee805-105">Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ee805-106">我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="ee805-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="ee805-107">您可以使用 [ [小組] 中所包含的原則套件](#policy-packages-included-in-teams) ，或 [建立您自己的自訂原則套件](#custom-policy-packages) (在私人預覽) 中。</span><span class="sxs-lookup"><span data-stu-id="ee805-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心 [原則套件] 頁面的螢幕擷取畫面":::

<span data-ttu-id="ee805-109">您可以自訂原則套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="ee805-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="ee805-110">當您變更套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="ee805-111">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來管理原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="ee805-112">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="ee805-112">What is a policy package?</span></span>

<span data-ttu-id="ee805-113">[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。</span><span class="sxs-lookup"><span data-stu-id="ee805-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="ee805-114">團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。</span><span class="sxs-lookup"><span data-stu-id="ee805-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="ee805-115">原則套件支援下列團隊原則類型：</span><span class="sxs-lookup"><span data-stu-id="ee805-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="ee805-116">訊息原則</span><span class="sxs-lookup"><span data-stu-id="ee805-116">Messaging policy</span></span>
- <span data-ttu-id="ee805-117">會議原則</span><span class="sxs-lookup"><span data-stu-id="ee805-117">Meeting policy</span></span>
- <span data-ttu-id="ee805-118">App 設定原則</span><span class="sxs-lookup"><span data-stu-id="ee805-118">App setup policy</span></span>
- <span data-ttu-id="ee805-119">通話原則</span><span class="sxs-lookup"><span data-stu-id="ee805-119">Calling policy</span></span>
- <span data-ttu-id="ee805-120">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="ee805-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="ee805-121">團隊中包含的原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-121">Policy packages included in Teams</span></span>

<span data-ttu-id="ee805-122">團隊目前包含下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="ee805-123">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="ee805-123">**Package name**</span></span>  |<span data-ttu-id="ee805-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="ee805-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="ee805-125">教育版 (高等教育學生) </span><span class="sxs-lookup"><span data-stu-id="ee805-125">Education (Higher education student)</span></span>    |<span data-ttu-id="ee805-126">建立一組可套用至較高教育學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="ee805-127">教育 (主要學校學生) </span><span class="sxs-lookup"><span data-stu-id="ee805-127">Education (Primary school student)</span></span>   |<span data-ttu-id="ee805-128">建立適用于主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="ee805-129">課程 (副學校學生) </span><span class="sxs-lookup"><span data-stu-id="ee805-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="ee805-130">建立一組可套用至副學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="ee805-131">教育版 (教師) </span><span class="sxs-lookup"><span data-stu-id="ee805-131">Education (Teacher)</span></span>    |<span data-ttu-id="ee805-132">建立適用于教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="ee805-133">使用遠端學習 (主要學校老師的教育版) </span><span class="sxs-lookup"><span data-stu-id="ee805-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="ee805-134">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="ee805-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="ee805-135">使用遠端學習) 的主要學校學生 (教育版</span><span class="sxs-lookup"><span data-stu-id="ee805-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="ee805-136">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="ee805-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="ee805-137">第一線員工管理員</span><span class="sxs-lookup"><span data-stu-id="ee805-137">Firstline manager</span></span> |<span data-ttu-id="ee805-138">建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。</span><span class="sxs-lookup"><span data-stu-id="ee805-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="ee805-139">第一線員工 worker</span><span class="sxs-lookup"><span data-stu-id="ee805-139">Firstline worker</span></span> |<span data-ttu-id="ee805-140">建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="ee805-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="ee805-141">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="ee805-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="ee805-142">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="ee805-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="ee805-143">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="ee805-143">Healthcare information worker</span></span>  |<span data-ttu-id="ee805-144">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="ee805-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="ee805-145">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="ee805-145">Healthcare patient room</span></span>  |<span data-ttu-id="ee805-146">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="ee805-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="ee805-147">中小型企業使用者 (商務語音) </span><span class="sxs-lookup"><span data-stu-id="ee805-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="ee805-148">建立應用程式設定原則，其中包含商務語音體驗的 app。</span><span class="sxs-lookup"><span data-stu-id="ee805-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="ee805-149">中小型企業使用者 (沒有商務用語音) </span><span class="sxs-lookup"><span data-stu-id="ee805-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="ee805-150">建立與中小型企業團隊使用者 (非商務語音體驗) 相關的 app 設定原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="ee805-151">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="ee805-151">Public safety officer</span></span>   |<span data-ttu-id="ee805-152">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="ee805-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="ee805-153">我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。</span><span class="sxs-lookup"><span data-stu-id="ee805-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="ee805-154">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="ee805-155">例如，當您將「教育 (教師) 原則套件指派給學校中的教師時，會針對套件中的每個原則建立名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版 (教師) 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="ee805-157">自訂原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-157">Custom policy packages</span></span>

<span data-ttu-id="ee805-158">**此功能是私人預覽**</span><span class="sxs-lookup"><span data-stu-id="ee805-158">**This feature is in private preview**</span></span>

<span data-ttu-id="ee805-159">自訂原則套件可讓您將自己的一組原則與組織中相似角色的使用者捆綁。</span><span class="sxs-lookup"><span data-stu-id="ee805-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="ee805-160">新增您所需的原則類型和原則，建立您自己的原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="ee805-161">若要建立新的自訂策略套件：</span><span class="sxs-lookup"><span data-stu-id="ee805-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="ee805-162">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件** ]，然後按一下 [ **新增** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages** , and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心 [原則套件] 頁面上的 [新增] 按鈕的螢幕擷取畫面":::
2. <span data-ttu-id="ee805-164">輸入套件的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="ee805-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. <span data-ttu-id="ee805-166">選取要包含在套件中的原則類型和原則名稱。</span><span class="sxs-lookup"><span data-stu-id="ee805-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="ee805-167">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="ee805-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="ee805-168">如何使用原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-168">How to use policy packages</span></span>

<span data-ttu-id="ee805-169">下列概要說明如何在您的組織中使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-169">The following outlines how to use policy packages in your organization.</span></span>

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- <span data-ttu-id="ee805-171">[ **[查看](#view-the-settings-of-a-policy-in-a-policy-package)** ]：在原則套件中查看原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)** : View the policies in a policy package.</span></span> <span data-ttu-id="ee805-172">然後，在指派套件之前，先查看套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="ee805-173">請務必瞭解每個設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="ee805-174">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其變更為更具限制或 lenient。</span><span class="sxs-lookup"><span data-stu-id="ee805-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="ee805-175">如果刪除策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="ee805-176">當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="ee805-177">**[自訂](#customize-policies-in-a-policy-package)** ：自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ee805-177">**[Customize](#customize-policies-in-a-policy-package)** : Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="ee805-178">**[指派](#assign-a-policy-package)** ：將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-178">**[Assign](#assign-a-policy-package)** : Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="ee805-179">您也可以在指派套件後，變更原則套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="ee805-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="ee805-180">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="ee805-181">以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="ee805-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="ee805-182">在原則套件中查看原則的設定</span><span class="sxs-lookup"><span data-stu-id="ee805-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="ee805-183">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件** ]，然後按一下套件名稱左邊的，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="ee805-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ee805-184">按一下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="ee805-185">在原則套件中自訂策略</span><span class="sxs-lookup"><span data-stu-id="ee805-185">Customize policies in a policy package</span></span>

<span data-ttu-id="ee805-186">您可以透過 [ **原則套件** ] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ee805-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ee805-187">在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ee805-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="ee805-188">按一下 [ **原則套件** ]，然後按一下套件名稱左方，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="ee805-188">Click **Policy packages** , and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="ee805-189">按一下原則類型。</span><span class="sxs-lookup"><span data-stu-id="ee805-189">Click the policy type.</span></span>  <span data-ttu-id="ee805-190">例如，按一下 [ **訊息原則** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="ee805-191">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="ee805-191">Select the policy you want to edit.</span></span> <span data-ttu-id="ee805-192">連結至原則套件的原則與原則套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="ee805-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="ee805-193">進行您想要的變更，然後按一下 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="ee805-194">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="ee805-195">指派原則套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="ee805-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="ee805-196">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-196">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="ee805-197">在使用者的頁面上，按一下 [ **原則** ]，然後按一下 [ **原則封裝** ] 旁的 [ **編輯** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-197">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="ee805-198">在 [ **指派原則套件** ] 窗格中，選取您要指派的套件，然後按一下 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="ee805-199">指派原則套件給多位使用者</span><span class="sxs-lookup"><span data-stu-id="ee805-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="ee805-200">在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件** ]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ee805-201">按一下 [ **管理使用者** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="ee805-202">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="ee805-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="ee805-203">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="ee805-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="ee805-204">完成新增使用者後，請按一下 [ **儲存** ]。</span><span class="sxs-lookup"><span data-stu-id="ee805-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="ee805-205">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="ee805-205">Assign a policy package to a group</span></span>

<span data-ttu-id="ee805-206">**此功能是私人預覽**</span><span class="sxs-lookup"><span data-stu-id="ee805-206">**This feature is in private preview**</span></span>

<span data-ttu-id="ee805-207">[原則套件指派給群組] 可讓您將多個原則指派給使用者群組，例如安全群組或通訊群組清單。</span><span class="sxs-lookup"><span data-stu-id="ee805-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="ee805-208">原則指派會根據優先順序規則傳播到群組的成員。</span><span class="sxs-lookup"><span data-stu-id="ee805-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ee805-209">在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。</span><span class="sxs-lookup"><span data-stu-id="ee805-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="ee805-210">建議將此方法用於最多50000個使用者的群組，但也會搭配較大的群組使用。</span><span class="sxs-lookup"><span data-stu-id="ee805-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="ee805-211">若要深入瞭解，請參閱 [將原則套件指派給群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="ee805-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="ee805-212">將原則套件指派給大型集 (批次) 使用者</span><span class="sxs-lookup"><span data-stu-id="ee805-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="ee805-213">使用批次原則套件指派來一次將原則套件指派給大型的使用者組。</span><span class="sxs-lookup"><span data-stu-id="ee805-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="ee805-214">您使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="ee805-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="ee805-215">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="ee805-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="ee805-216">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ee805-217">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="ee805-218">若要深入瞭解，請參閱 [將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="ee805-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ee805-219">疑難排解</span><span class="sxs-lookup"><span data-stu-id="ee805-219">Troubleshooting</span></span>

<span data-ttu-id="ee805-220">**當您指派原則套件時，收到錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="ee805-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="ee805-221">如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="ee805-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="ee805-222">將原則套件重新指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="ee805-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="ee805-223">重試此操作通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="ee805-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee805-224">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee805-224">Related topics</span></span>

[<span data-ttu-id="ee805-225">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="ee805-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="ee805-226">EDU 管理員的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="ee805-227">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="ee805-228">政府團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="ee805-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
