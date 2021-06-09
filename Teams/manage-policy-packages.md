---
title: 在中管理Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: 瞭解如何在管理使用者群組Microsoft Teams，以簡化、簡化及協助提供一致性。
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810182"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="6a69a-103">在中管理Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6a69a-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="6a69a-104">Microsoft Teams 中的 原則套件 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="6a69a-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="6a69a-105">我們建立了策略套件，以簡化、簡化，並有助於在管理貴組織使用者群組時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="6a69a-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="6a69a-106">您可以使用包含在其中[的政策套件Teams](#policy-packages-included-in-teams)[或建立您自己的自訂策略套件](#custom-policy-packages)。</span><span class="sxs-lookup"><span data-stu-id="6a69a-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心中策略套件頁面的螢幕擷取畫面":::

<span data-ttu-id="6a69a-108">您可以自訂策略套件中之策略的設定，以適合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="6a69a-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="6a69a-109">當您變更套件中之策略的設定時，指派給該套件的所有使用者會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="6a69a-110">您可以使用系統管理中心或 PowerShell 管理Microsoft Teams套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="6a69a-111">每個使用者都需要進一步通訊附加元件，才能接收自訂策略套件指派。</span><span class="sxs-lookup"><span data-stu-id="6a69a-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="6a69a-112">若要詳細資訊，請參閱適用于 Microsoft Teams[的 Advanced Communications 附加Microsoft Teams。](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="6a69a-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="6a69a-113">什麼是策略套件？</span><span class="sxs-lookup"><span data-stu-id="6a69a-113">What is a policy package?</span></span>

<span data-ttu-id="6a69a-114">策略套件可Teams貴組織特定人員集合所允許或限制的功能。</span><span class="sxs-lookup"><span data-stu-id="6a69a-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="6a69a-115">每個策略套件Teams使用者角色所設計，並包含預先定義的策略和策略設定，可支援該角色常見的共同合作與通訊活動。</span><span class="sxs-lookup"><span data-stu-id="6a69a-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="6a69a-116">策略套件支援下列Teams類型：</span><span class="sxs-lookup"><span data-stu-id="6a69a-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="6a69a-117">訊息原則</span><span class="sxs-lookup"><span data-stu-id="6a69a-117">Messaging policy</span></span>
- <span data-ttu-id="6a69a-118">會議原則</span><span class="sxs-lookup"><span data-stu-id="6a69a-118">Meeting policy</span></span>
- <span data-ttu-id="6a69a-119">應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="6a69a-119">App setup policy</span></span>
- <span data-ttu-id="6a69a-120">通話原則</span><span class="sxs-lookup"><span data-stu-id="6a69a-120">Calling policy</span></span>
- <span data-ttu-id="6a69a-121">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="6a69a-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="6a69a-122">包含在 Teams</span><span class="sxs-lookup"><span data-stu-id="6a69a-122">Policy packages included in Teams</span></span>

<span data-ttu-id="6a69a-123">Teams目前包含下列策略套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="6a69a-124">套件名稱</span><span class="sxs-lookup"><span data-stu-id="6a69a-124">Package name</span></span> | <span data-ttu-id="6a69a-125">說明</span><span class="sxs-lookup"><span data-stu-id="6a69a-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="6a69a-126">教育 (高教學生) </span><span class="sxs-lookup"><span data-stu-id="6a69a-126">Education (Higher education student)</span></span>    |<span data-ttu-id="6a69a-127">建立套用至高教學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="6a69a-128">教育 (中學生) </span><span class="sxs-lookup"><span data-stu-id="6a69a-128">Education (Primary school student)</span></span>   |<span data-ttu-id="6a69a-129">建立套用至主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="6a69a-130">教育 (中學生) </span><span class="sxs-lookup"><span data-stu-id="6a69a-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="6a69a-131">建立套用至中學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="6a69a-132">教育 (教師) </span><span class="sxs-lookup"><span data-stu-id="6a69a-132">Education (Teacher)</span></span>    |<span data-ttu-id="6a69a-133">建立套用至教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="6a69a-134">使用 (遠端學習工具的小學教師) </span><span class="sxs-lookup"><span data-stu-id="6a69a-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="6a69a-135">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="6a69a-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="6a69a-136">使用 (遠端學習的中學生) </span><span class="sxs-lookup"><span data-stu-id="6a69a-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="6a69a-137">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="6a69a-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="6a69a-138">前線管理員</span><span class="sxs-lookup"><span data-stu-id="6a69a-138">Frontline manager</span></span> |<span data-ttu-id="6a69a-139">建立一組原則，並套用這些設定給貴組織的前線管理員。</span><span class="sxs-lookup"><span data-stu-id="6a69a-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="6a69a-140">前線工作人員</span><span class="sxs-lookup"><span data-stu-id="6a69a-140">Frontline worker</span></span> |<span data-ttu-id="6a69a-141">建立一組原則，並套用這些設定給貴組織的前線員工。</span><span class="sxs-lookup"><span data-stu-id="6a69a-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="6a69a-142">醫療保健臨床工作者</span><span class="sxs-lookup"><span data-stu-id="6a69a-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="6a69a-143">建立一組原則與原則設定，讓臨床工作者 (例如註冊的護士、護士長、醫生和社會工作者) 能完整存取聊天、通話、班次管理和會議。</span><span class="sxs-lookup"><span data-stu-id="6a69a-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="6a69a-144">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="6a69a-144">Healthcare information worker</span></span>  |<span data-ttu-id="6a69a-145">建立一組原則與原則設定，讓資訊工作者 (例如 IT 人員、資訊人員、財務人員及法規人員) 能夠完整存取聊天、通話和會議。</span><span class="sxs-lookup"><span data-stu-id="6a69a-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="6a69a-146">醫療保健病房</span><span class="sxs-lookup"><span data-stu-id="6a69a-146">Healthcare patient room</span></span>  |<span data-ttu-id="6a69a-147">建立一組原則與原則設定，適用於貴醫療保健組織的病房。</span><span class="sxs-lookup"><span data-stu-id="6a69a-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="6a69a-148">中小企業使用者 (商務語音) </span><span class="sxs-lookup"><span data-stu-id="6a69a-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="6a69a-149">建立包含商務語音體驗應用程式的應用程式設定策略。</span><span class="sxs-lookup"><span data-stu-id="6a69a-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="6a69a-150">中小企業使用者無需商務 (語音) </span><span class="sxs-lookup"><span data-stu-id="6a69a-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="6a69a-151">建立與中小型企業相關的應用程式設定Teams使用者 (商務語音體驗) 。</span><span class="sxs-lookup"><span data-stu-id="6a69a-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="6a69a-152">公共安全專員</span><span class="sxs-lookup"><span data-stu-id="6a69a-152">Public safety officer</span></span>   |<span data-ttu-id="6a69a-153">建立一組套套用至貴組織的公安人員之原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="6a69a-154">我們會在未來發行新版中新增更多Teams套件，因此請回來查看最新資訊。</span><span class="sxs-lookup"><span data-stu-id="6a69a-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="6a69a-155">每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="6a69a-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="6a69a-156">例如，當您將教育 (教師) 政策套件指派給學校中的教師時，會針對套件中每個策略建立名為 Education_Teacher 的策略。</span><span class="sxs-lookup"><span data-stu-id="6a69a-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育與教師 (政策套件) 螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="6a69a-158">自訂策略套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-158">Custom policy packages</span></span>

<span data-ttu-id="6a69a-159">**系統尚未提供自訂政府社群雲端 (GCC)**</span><span class="sxs-lookup"><span data-stu-id="6a69a-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="6a69a-160">自訂策略套件讓您針對組織中具有類似角色的使用者，將您自己的一群組原則組合在一起。</span><span class="sxs-lookup"><span data-stu-id="6a69a-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="6a69a-161">新增所需的策略類型與策略，以建立您自己的策略套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="6a69a-162">若要建立新的自訂策略套件：</span><span class="sxs-lookup"><span data-stu-id="6a69a-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="6a69a-163">在系統管理中心的左側導Microsoft Teams，選取 [政策 **套件**，然後按一下 [**新增**> 。</span><span class="sxs-lookup"><span data-stu-id="6a69a-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心之策略套件頁面上的新增按鈕螢幕擷取畫面":::

2. <span data-ttu-id="6a69a-165">輸入套件的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="6a69a-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::

3. <span data-ttu-id="6a69a-167">選取要納入套件中的策略類型和策略名稱。</span><span class="sxs-lookup"><span data-stu-id="6a69a-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="6a69a-168">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="6a69a-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="6a69a-169">如何使用策略套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-169">How to use policy packages</span></span>

<span data-ttu-id="6a69a-170">以下概述如何在貴組織中使用策略套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-170">The following outlines how to use policy packages in your organization.</span></span>

![如何使用策略套件概觀](media/manage-policy-packages-overview.png)

- <span data-ttu-id="6a69a-172">**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在策略套件中查看策略。</span><span class="sxs-lookup"><span data-stu-id="6a69a-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="6a69a-173">接著，在指派套件之前，先查看套件中每個策略的設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="6a69a-174">請確定您瞭解每個設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="6a69a-175">根據貴組織的需求，決定預先定義的值是否適合貴組織，或是否需要將它們變更為較嚴格或寬鬆。</span><span class="sxs-lookup"><span data-stu-id="6a69a-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="6a69a-176">如果刪除一個策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="6a69a-177">當您指派策略套件時，會使用預先定義的設定重新建立已刪除的策略。</span><span class="sxs-lookup"><span data-stu-id="6a69a-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="6a69a-178">**[自訂](#customize-policies-in-a-policy-package)**：自訂策略套件中的策略設定，以配合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="6a69a-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="6a69a-179">**[指派](#assign-a-policy-package)**：將策略套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="6a69a-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="6a69a-180">您也可以在指派套件之後，變更策略套件中的策略設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="6a69a-181">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="6a69a-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="6a69a-182">以下是如何在系統管理中心中查看、指派及自訂Microsoft Teams套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="6a69a-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="6a69a-183">在策略套件中查看策略設定</span><span class="sxs-lookup"><span data-stu-id="6a69a-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="6a69a-184">在系統管理中心的左側導Microsoft Teams，選取策略套件，然後按一下套件名稱左側以選取策略套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="6a69a-185">按一下您想要查看的政策。</span><span class="sxs-lookup"><span data-stu-id="6a69a-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="6a69a-186">自訂策略套件中的策略</span><span class="sxs-lookup"><span data-stu-id="6a69a-186">Customize policies in a policy package</span></span>

<span data-ttu-id="6a69a-187">您可以透過策略套件頁面或直接到系統管理中心中的Microsoft Teams設定。</span><span class="sxs-lookup"><span data-stu-id="6a69a-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="6a69a-188">在系統管理中心的左側導Microsoft Teams，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="6a69a-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="6a69a-189">按一下 **[策略套件**，然後按一下套件名稱左側以選取該策略套件。</span><span class="sxs-lookup"><span data-stu-id="6a69a-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="6a69a-190">按一下策略類型。</span><span class="sxs-lookup"><span data-stu-id="6a69a-190">Click the policy type.</span></span>  <span data-ttu-id="6a69a-191">例如，按一下 **[訊息策略**> 。</span><span class="sxs-lookup"><span data-stu-id="6a69a-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="6a69a-192">選取您想要編輯的政策。</span><span class="sxs-lookup"><span data-stu-id="6a69a-192">Select the policy you want to edit.</span></span> <span data-ttu-id="6a69a-193">連結至策略套件的策略與策略套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="6a69a-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="6a69a-194">進行您想要的變更，然後按一下 [ **儲存**。</span><span class="sxs-lookup"><span data-stu-id="6a69a-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="6a69a-195">指派策略套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-195">Assign a policy package</span></span>

<span data-ttu-id="6a69a-196">您可以將策略套件指派給個別使用者、群組或一批使用者。</span><span class="sxs-lookup"><span data-stu-id="6a69a-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="6a69a-197">若要瞭解如何指派策略套件，請參閱指派策略 [套件給使用者和群組](assign-policy-packages.md)。</span><span class="sxs-lookup"><span data-stu-id="6a69a-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6a69a-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="6a69a-198">Related topics</span></span>

- [<span data-ttu-id="6a69a-199">指派策略套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="6a69a-200">Teams EDU 系統管理員使用的政策套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="6a69a-201">適用於醫療保健的 Teams 原則套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="6a69a-202">Teams政府政策套件</span><span class="sxs-lookup"><span data-stu-id="6a69a-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
