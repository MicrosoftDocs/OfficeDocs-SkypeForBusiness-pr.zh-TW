---
title: 在 Microsoft Teams 中管理政策套件
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
description: 瞭解如何在 Microsoft Teams 中使用及管理原則套件，以簡化、簡化及協助在管理使用者群組之策略時提供一致性。
ms.openlocfilehash: 07e2712db52d79e8db66789fe062c8ab46854e5b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50585689"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="ec3d7-103">在 Microsoft Teams 中管理政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="ec3d7-104">本文探討的其中一項功能，自訂 [策略套件](#custom-policy-packages)目前處於私人預覽。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="ec3d7-105">Microsoft Teams 中的一個策略套件是預先定義之策略和策略設定的集合，您可以指派給組織中具有類似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ec3d7-106">我們建建了簡化、簡化及協助管理貴組織使用者群組之策略時一致性的套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="ec3d7-107">您可以使用 Teams[中包含的政策](#policy-packages-included-in-teams)套件，或在私人[](#custom-policy-packages)預覽版中 (自訂) 。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心中之政策套件頁面的螢幕擷取畫面":::

<span data-ttu-id="ec3d7-109">您可以自訂策略套件中之策略的設定，以滿足您的需求。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="ec3d7-110">當您變更套件中之策略的設定時，指派給該套件的所有使用者會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="ec3d7-111">您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理政策套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="ec3d7-112">什麼是政策套件？</span><span class="sxs-lookup"><span data-stu-id="ec3d7-112">What is a policy package?</span></span>

<span data-ttu-id="ec3d7-113">策略套件讓您控制您想要允許或限制貴組織特定人員集合的 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="ec3d7-114">Teams 中每個策略套件都是以使用者角色為設計基礎，並包含預先定義且支援該角色一般共同合作和通訊活動之政策設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="ec3d7-115">策略套件支援下列 Teams 策略類型：</span><span class="sxs-lookup"><span data-stu-id="ec3d7-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="ec3d7-116">訊息原則</span><span class="sxs-lookup"><span data-stu-id="ec3d7-116">Messaging policy</span></span>
- <span data-ttu-id="ec3d7-117">會議原則</span><span class="sxs-lookup"><span data-stu-id="ec3d7-117">Meeting policy</span></span>
- <span data-ttu-id="ec3d7-118">應用程式設定政策</span><span class="sxs-lookup"><span data-stu-id="ec3d7-118">App setup policy</span></span>
- <span data-ttu-id="ec3d7-119">通話原則</span><span class="sxs-lookup"><span data-stu-id="ec3d7-119">Calling policy</span></span>
- <span data-ttu-id="ec3d7-120">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="ec3d7-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="ec3d7-121">Teams 中包含的政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-121">Policy packages included in Teams</span></span>

<span data-ttu-id="ec3d7-122">Teams 目前包含下列政策套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="ec3d7-123">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="ec3d7-123">**Package name**</span></span>  |<span data-ttu-id="ec3d7-124">**描述**</span><span class="sxs-lookup"><span data-stu-id="ec3d7-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="ec3d7-125">教育 (學生) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-125">Education (Higher education student)</span></span>    |<span data-ttu-id="ec3d7-126">建立套用至高教學生一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="ec3d7-127">教育 (中學生) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-127">Education (Primary school student)</span></span>   |<span data-ttu-id="ec3d7-128">建立套用至主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="ec3d7-129">教育 (中學生) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="ec3d7-130">建立套用至中學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="ec3d7-131">教育 (教師) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-131">Education (Teacher)</span></span>    |<span data-ttu-id="ec3d7-132">建立套用至教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="ec3d7-133">使用 (學習工具) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="ec3d7-134">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="ec3d7-135">使用 (學習課程的中學生) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="ec3d7-136">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="ec3d7-137">前線管理員</span><span class="sxs-lookup"><span data-stu-id="ec3d7-137">Frontline manager</span></span> |<span data-ttu-id="ec3d7-138">建立一組原則，並套用這些設定給貴組織的前線管理員。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-138">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="ec3d7-139">第一線員工</span><span class="sxs-lookup"><span data-stu-id="ec3d7-139">Frontline worker</span></span> |<span data-ttu-id="ec3d7-140">建立一組原則，並套用這些設定給貴組織的前線工作人員。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-140">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="ec3d7-141">醫療保健專業人員</span><span class="sxs-lookup"><span data-stu-id="ec3d7-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="ec3d7-142">建立一組政策與政策設定，讓醫療工作者 ，例如註冊的護士、護士、醫師和社交工作者，能完全存取聊天、通話、輪班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="ec3d7-143">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="ec3d7-143">Healthcare information worker</span></span>  |<span data-ttu-id="ec3d7-144">建立一組政策與政策設定，讓資訊工作者 ，例如 IT 人員、資訊人員、財務人員和法規遵循人員，以及完整的聊天、通話和會議存取權。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="ec3d7-145">醫療保健病患室</span><span class="sxs-lookup"><span data-stu-id="ec3d7-145">Healthcare patient room</span></span>  |<span data-ttu-id="ec3d7-146">建立一組套用至醫療保健組織中病患室的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="ec3d7-147">中小型企業使用者 (商務語音) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="ec3d7-148">建立包含商務語音體驗應用程式的應用程式設定政策。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="ec3d7-149">沒有 Business Voice (的中小型企業) </span><span class="sxs-lookup"><span data-stu-id="ec3d7-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="ec3d7-150">建立與中小型企業 Teams 使用者相關的應用程式設定 (非商務語音體驗) 。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="ec3d7-151">公共安全人員</span><span class="sxs-lookup"><span data-stu-id="ec3d7-151">Public safety officer</span></span>   |<span data-ttu-id="ec3d7-152">建立一組套用至貴組織中公共安全人員的政策與原則設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="ec3d7-153">我們會在未來 Teams 版本中新增更多政策套件，因此請返回查看最新資訊。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="ec3d7-154">每一個個別策略會提供一個策略套件的名稱，好方便您識別連結至該政策套件的政策。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="ec3d7-155">例如，當您將教育 (教師) 政策套件指派給學校中的教師時，會針對套件中的每個政策建立名為 Education_Teacher 的一個策略。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育與教師 (政策套件) 螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="ec3d7-157">自訂策略套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-157">Custom policy packages</span></span>

<span data-ttu-id="ec3d7-158">**這項功能在私人預覽中**</span><span class="sxs-lookup"><span data-stu-id="ec3d7-158">**This feature is in private preview**</span></span>

<span data-ttu-id="ec3d7-159">自訂策略套件可針對組織中具有類似角色的使用者，將您自己的一群組原則組合在一起。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="ec3d7-160">新增所需的策略類型與策略，以建立您自己的策略套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="ec3d7-161">若要建立新的自訂策略套件：</span><span class="sxs-lookup"><span data-stu-id="ec3d7-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="ec3d7-162">在 Microsoft Teams 系統管理中心的左側流覽中，選取 [政策 **套件**，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心之政策套件頁面上的新增按鈕螢幕擷取畫面":::
2. <span data-ttu-id="ec3d7-164">輸入套件的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. <span data-ttu-id="ec3d7-166">選取要納入套件中的策略類型和策略名稱。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="ec3d7-167">按一下 [儲存 **]**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="ec3d7-168">如何使用政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-168">How to use policy packages</span></span>

<span data-ttu-id="ec3d7-169">以下概述如何在貴組織中使用政策套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-169">The following outlines how to use policy packages in your organization.</span></span>

![如何使用政策套件概觀](media/manage-policy-packages-overview.png)

- <span data-ttu-id="ec3d7-171">**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在策略套件中查看策略。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="ec3d7-172">然後，在指派套件之前，先查看套件中每個策略的設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="ec3d7-173">請確定您瞭解每個設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="ec3d7-174">決定預先定義的值是否適合貴組織，或是否需要根據貴組織的需求，將它們變更為更具限制性或寬限性。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="ec3d7-175">如果已刪除某個政策，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="ec3d7-176">當您指派該策略套件時，會使用預先定義的設定重新建立已刪除的策略。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="ec3d7-177">**[自訂](#customize-policies-in-a-policy-package)**：自訂策略套件中之策略的設定，以配合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="ec3d7-178">**[指派](#assign-a-policy-package)**：指派策略套件給使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="ec3d7-179">您也可以在指派套件之後，變更策略套件中之策略的設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="ec3d7-180">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="ec3d7-181">以下是如何在 Microsoft Teams 系統管理中心中查看、指派及自訂政策套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="ec3d7-182">在策略套件中查看策略的設定</span><span class="sxs-lookup"><span data-stu-id="ec3d7-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="ec3d7-183">在 Microsoft Teams 系統管理中心的左側流覽中，選取政策 **套件**，然後按一下套件名稱左側以選取一個策略套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ec3d7-184">按一下您想要查看的策略。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="ec3d7-185">自訂策略套件中的策略</span><span class="sxs-lookup"><span data-stu-id="ec3d7-185">Customize policies in a policy package</span></span>

<span data-ttu-id="ec3d7-186">您可以透過政策套件頁面或直接進入 Microsoft  Teams 系統管理中心中的政策頁面，編輯該政策設定。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="ec3d7-187">在 Microsoft Teams 系統管理中心的左側流覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="ec3d7-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="ec3d7-188">按一下 **[策略套件**，然後按一下套件名稱左側以選取該策略套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="ec3d7-189">按一下該策略類型。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-189">Click the policy type.</span></span>  <span data-ttu-id="ec3d7-190">例如，按一下 **[傳訊策略**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="ec3d7-191">選取您想要編輯的策略。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-191">Select the policy you want to edit.</span></span> <span data-ttu-id="ec3d7-192">連結至策略套件之策略與策略套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="ec3d7-193">進行您想要的變更，然後按一下 **[儲存**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="ec3d7-194">指派策略套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="ec3d7-195">指派一個策略套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="ec3d7-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="ec3d7-196">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="ec3d7-197">在使用者的頁面上，按一下 **[政策**」，然後按一下 [政策套件旁的編輯 **。**</span><span class="sxs-lookup"><span data-stu-id="ec3d7-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="ec3d7-198">在 [ **指派策略套件窗格** > 中，選取要指派的套件，然後按一下 **[儲存**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="ec3d7-199">指派一個策略套件給多個使用者</span><span class="sxs-lookup"><span data-stu-id="ec3d7-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="ec3d7-200">在 Microsoft Teams 系統管理中心的左側流覽中，前往政策套件，然後按一下套件名稱左側，選取您想要指派的套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="ec3d7-201">按一下 **[管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="ec3d7-202">在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="ec3d7-203">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="ec3d7-204">完成新增使用者後，請按一下 **[儲存**。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="ec3d7-205">將原則套件指派給群組</span><span class="sxs-lookup"><span data-stu-id="ec3d7-205">Assign a policy package to a group</span></span>

<span data-ttu-id="ec3d7-206">透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-206">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="ec3d7-207">原則指派將根據優先順序規則傳播到群組成員。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-207">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="ec3d7-208">在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-208">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="ec3d7-209">此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-209">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="ec3d7-210">若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-210">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="ec3d7-211">為一大組 (批) 使用者指派原則套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-211">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="ec3d7-212">使用批次原則套件指派，將原則套件一次性指派給大組使用者組。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-212">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="ec3d7-213">您可以使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-213">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="ec3d7-214">系統會將工作處理為背景作業，並為每個批次產生作業識別碼。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-214">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="ec3d7-215">批次最多可包含 5000 個使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-215">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="ec3d7-216">您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-216">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="ec3d7-217">若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-217">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="ec3d7-218">疑難排解</span><span class="sxs-lookup"><span data-stu-id="ec3d7-218">Troubleshooting</span></span>

<span data-ttu-id="ec3d7-219">**當您指派策略套件時收到錯誤**</span><span class="sxs-lookup"><span data-stu-id="ec3d7-219">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="ec3d7-220">如果未成功建立或套用套件中的一或多個原則，就可能會發生此情況。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-220">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="ec3d7-221">將策略套件重新指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-221">Reassign the policy package to your users.</span></span> <span data-ttu-id="ec3d7-222">重試作業通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="ec3d7-222">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ec3d7-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="ec3d7-223">Related topics</span></span>

[<span data-ttu-id="ec3d7-224">在 Teams 中將原則指派給使用者</span><span class="sxs-lookup"><span data-stu-id="ec3d7-224">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="ec3d7-225">適用于 EDU 系統管理員的 Teams 政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-225">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="ec3d7-226">醫療保健的 Teams 政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-226">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="ec3d7-227">政府用 Teams 政策套件</span><span class="sxs-lookup"><span data-stu-id="ec3d7-227">Teams policy packages for government</span></span>](policy-packages-gov.md)
