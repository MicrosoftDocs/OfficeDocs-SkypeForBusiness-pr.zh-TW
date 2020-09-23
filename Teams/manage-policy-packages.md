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
ms.openlocfilehash: bdbfed095cf522702f55963ba7e46d79b765d59c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/23/2020
ms.locfileid: "48220231"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="34449-103">管理 Microsoft 團隊中的原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="34449-104">本文中討論的其中一個功能， [自訂原則套件](#custom-policy-packages)尚未發佈。</span><span class="sxs-lookup"><span data-stu-id="34449-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), hasn't been released yet.</span></span> <span data-ttu-id="34449-105">我們即將推出私人預覽版。</span><span class="sxs-lookup"><span data-stu-id="34449-105">It's coming soon to private preview.</span></span>

<span data-ttu-id="34449-106">Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-106">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="34449-107">我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。</span><span class="sxs-lookup"><span data-stu-id="34449-107">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="34449-108">您可以使用 [小組所包含的原則套件](#policy-packages-included-in-teams) ，或 [建立您自己的自訂原則套件](#custom-policy-packages) (即將推出私人預覽版) 。</span><span class="sxs-lookup"><span data-stu-id="34449-108">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (coming soon to private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心 [原則套件] 頁面的螢幕擷取畫面":::

<span data-ttu-id="34449-110">您可以自訂原則套件中原則的設定，以符合您的使用者需求。</span><span class="sxs-lookup"><span data-stu-id="34449-110">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="34449-111">當您變更套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。</span><span class="sxs-lookup"><span data-stu-id="34449-111">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="34449-112">您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來管理原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-112">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="34449-113">什麼是原則套件？</span><span class="sxs-lookup"><span data-stu-id="34449-113">What is a policy package?</span></span>

<span data-ttu-id="34449-114">[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。</span><span class="sxs-lookup"><span data-stu-id="34449-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="34449-115">團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。</span><span class="sxs-lookup"><span data-stu-id="34449-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="34449-116">原則套件支援下列團隊原則類型：</span><span class="sxs-lookup"><span data-stu-id="34449-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="34449-117">訊息原則</span><span class="sxs-lookup"><span data-stu-id="34449-117">Messaging policy</span></span>
- <span data-ttu-id="34449-118">會議原則</span><span class="sxs-lookup"><span data-stu-id="34449-118">Meeting policy</span></span>
- <span data-ttu-id="34449-119">App 設定原則</span><span class="sxs-lookup"><span data-stu-id="34449-119">App setup policy</span></span>
- <span data-ttu-id="34449-120">通話原則</span><span class="sxs-lookup"><span data-stu-id="34449-120">Calling policy</span></span>
- <span data-ttu-id="34449-121">即時活動原則</span><span class="sxs-lookup"><span data-stu-id="34449-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="34449-122">團隊中包含的原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-122">Policy packages included in Teams</span></span>

<span data-ttu-id="34449-123">團隊目前包含下列原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-123">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="34449-124">**套件名稱**</span><span class="sxs-lookup"><span data-stu-id="34449-124">**Package name**</span></span>  |<span data-ttu-id="34449-125">**描述**</span><span class="sxs-lookup"><span data-stu-id="34449-125">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="34449-126">教育版 (高等教育學生) </span><span class="sxs-lookup"><span data-stu-id="34449-126">Education (Higher education student)</span></span>    |<span data-ttu-id="34449-127">建立一組可套用至較高教育學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="34449-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="34449-128">教育 (主要學校學生) </span><span class="sxs-lookup"><span data-stu-id="34449-128">Education (Primary school student)</span></span>   |<span data-ttu-id="34449-129">建立適用于主要學生的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="34449-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="34449-130">課程 (副學校學生) </span><span class="sxs-lookup"><span data-stu-id="34449-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="34449-131">建立一組可套用至副學生的原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="34449-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="34449-132">教育版 (教師) </span><span class="sxs-lookup"><span data-stu-id="34449-132">Education (Teacher)</span></span>    |<span data-ttu-id="34449-133">建立適用于教師的一組原則與原則設定。</span><span class="sxs-lookup"><span data-stu-id="34449-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="34449-134">使用遠端學習 (主要學校老師的教育版) </span><span class="sxs-lookup"><span data-stu-id="34449-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="34449-135">建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="34449-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="34449-136">使用遠端學習) 的主要學校學生 (教育版</span><span class="sxs-lookup"><span data-stu-id="34449-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="34449-137">建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。</span><span class="sxs-lookup"><span data-stu-id="34449-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="34449-138">第一線員工管理員</span><span class="sxs-lookup"><span data-stu-id="34449-138">Firstline manager</span></span> |<span data-ttu-id="34449-139">建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。</span><span class="sxs-lookup"><span data-stu-id="34449-139">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="34449-140">第一線員工 worker</span><span class="sxs-lookup"><span data-stu-id="34449-140">Firstline worker</span></span> |<span data-ttu-id="34449-141">建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。</span><span class="sxs-lookup"><span data-stu-id="34449-141">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="34449-142">醫療保健臨床工人</span><span class="sxs-lookup"><span data-stu-id="34449-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="34449-143">建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。</span><span class="sxs-lookup"><span data-stu-id="34449-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="34449-144">醫療保健資訊工作者</span><span class="sxs-lookup"><span data-stu-id="34449-144">Healthcare information worker</span></span>  |<span data-ttu-id="34449-145">建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。</span><span class="sxs-lookup"><span data-stu-id="34449-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="34449-146">醫療保健患者機房</span><span class="sxs-lookup"><span data-stu-id="34449-146">Healthcare patient room</span></span>  |<span data-ttu-id="34449-147">建立一組原則與原則設定，適用于您的保健組織中的患者會議室。</span><span class="sxs-lookup"><span data-stu-id="34449-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="34449-148">中小型企業使用者 (商務語音) </span><span class="sxs-lookup"><span data-stu-id="34449-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="34449-149">建立應用程式設定原則，其中包含商務語音體驗的 app。</span><span class="sxs-lookup"><span data-stu-id="34449-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="34449-150">中小型企業使用者 (沒有商務用語音) </span><span class="sxs-lookup"><span data-stu-id="34449-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="34449-151">建立與中小型企業團隊使用者 (非商務語音體驗) 相關的 app 設定原則。</span><span class="sxs-lookup"><span data-stu-id="34449-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="34449-152">公開安全官員</span><span class="sxs-lookup"><span data-stu-id="34449-152">Public safety officer</span></span>   |<span data-ttu-id="34449-153">建立一組原則與原則設定，適用于貴組織中的公用安全主管。</span><span class="sxs-lookup"><span data-stu-id="34449-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="34449-154">我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。</span><span class="sxs-lookup"><span data-stu-id="34449-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="34449-155">系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。</span><span class="sxs-lookup"><span data-stu-id="34449-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="34449-156">例如，當您將「教育 (教師) 原則套件指派給學校中的教師時，會針對套件中的每個原則建立名為 Education_Teacher 的原則。</span><span class="sxs-lookup"><span data-stu-id="34449-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![教育版 (教師) 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="34449-158">自訂原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-158">Custom policy packages</span></span>

<span data-ttu-id="34449-159">**此功能即將推出至私人預覽版**</span><span class="sxs-lookup"><span data-stu-id="34449-159">**This feature is coming soon to private preview**</span></span>

<span data-ttu-id="34449-160">自訂原則套件可讓您將自己的一組原則與組織中相似角色的使用者捆綁。</span><span class="sxs-lookup"><span data-stu-id="34449-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="34449-161">新增您所需的原則類型和原則，建立您自己的原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="34449-162">若要建立新的自訂策略套件：</span><span class="sxs-lookup"><span data-stu-id="34449-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="34449-163">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="34449-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心 [原則套件] 頁面上的 [新增] 按鈕的螢幕擷取畫面":::
2. <span data-ttu-id="34449-165">輸入套件的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="34449-165">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. <span data-ttu-id="34449-167">選取要包含在套件中的原則類型和原則名稱。</span><span class="sxs-lookup"><span data-stu-id="34449-167">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="34449-168">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34449-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="34449-169">如何使用原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-169">How to use policy packages</span></span>

<span data-ttu-id="34449-170">下列概要說明如何在您的組織中使用原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-170">The following outlines how to use policy packages in your organization.</span></span>

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- <span data-ttu-id="34449-172">[**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在原則套件中查看原則。</span><span class="sxs-lookup"><span data-stu-id="34449-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="34449-173">然後，在指派套件之前，先查看套件中每個原則的設定。</span><span class="sxs-lookup"><span data-stu-id="34449-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="34449-174">請務必瞭解每個設定。</span><span class="sxs-lookup"><span data-stu-id="34449-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="34449-175">決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其變更為更具限制或 lenient。</span><span class="sxs-lookup"><span data-stu-id="34449-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="34449-176">如果刪除策略，您仍然可以查看設定，但無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="34449-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="34449-177">當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。</span><span class="sxs-lookup"><span data-stu-id="34449-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="34449-178">**[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="34449-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="34449-179">**[指派](#assign-a-policy-package)**：將原則套件指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="34449-180">您也可以在指派套件後，變更原則套件中的原則設定。</span><span class="sxs-lookup"><span data-stu-id="34449-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="34449-181">您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="34449-182">以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="34449-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="34449-183">在原則套件中查看原則的設定</span><span class="sxs-lookup"><span data-stu-id="34449-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="34449-184">在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="34449-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="34449-185">按一下您要查看的原則。</span><span class="sxs-lookup"><span data-stu-id="34449-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="34449-186">在原則套件中自訂策略</span><span class="sxs-lookup"><span data-stu-id="34449-186">Customize policies in a policy package</span></span>

<span data-ttu-id="34449-187">您可以透過 [ **原則套件** ] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。</span><span class="sxs-lookup"><span data-stu-id="34449-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="34449-188">在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="34449-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="34449-189">按一下 [ **原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。</span><span class="sxs-lookup"><span data-stu-id="34449-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="34449-190">按一下原則類型。</span><span class="sxs-lookup"><span data-stu-id="34449-190">Click the policy type.</span></span>  <span data-ttu-id="34449-191">例如，按一下 [ **訊息原則**]。</span><span class="sxs-lookup"><span data-stu-id="34449-191">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="34449-192">選取您要編輯的原則。</span><span class="sxs-lookup"><span data-stu-id="34449-192">Select the policy you want to edit.</span></span> <span data-ttu-id="34449-193">連結至原則套件的原則與原則套件的名稱相同。</span><span class="sxs-lookup"><span data-stu-id="34449-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="34449-194">進行您想要的變更，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="34449-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="34449-195">指派原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-195">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="34449-196">指派原則套件給一個使用者</span><span class="sxs-lookup"><span data-stu-id="34449-196">Assign a policy package to one user</span></span>

1. <span data-ttu-id="34449-197">在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]\*\*\*\*，然後按一下該使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-197">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="34449-198">在使用者的頁面上，按一下 [ **原則**]，然後按一下 [ **原則封裝**] 旁的 [ **編輯**]。</span><span class="sxs-lookup"><span data-stu-id="34449-198">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="34449-199">在 [ **指派原則套件** ] 窗格中，選取您要指派的套件，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="34449-199">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="34449-200">指派原則套件給多位使用者</span><span class="sxs-lookup"><span data-stu-id="34449-200">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="34449-201">在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-201">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="34449-202">按一下 [ **管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="34449-202">Click **Manage users**.</span></span>
3. <span data-ttu-id="34449-203">在 [管理使用者]\*\*\*\* 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34449-203">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="34449-204">針對要新增的每一個使用者重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="34449-204">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="34449-205">完成新增使用者後，請按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="34449-205">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="34449-206">將原則套件指派給大型集 (批次) 使用者</span><span class="sxs-lookup"><span data-stu-id="34449-206">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="34449-207">使用批次原則套件指派來一次將原則套件指派給大型的使用者組。</span><span class="sxs-lookup"><span data-stu-id="34449-207">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="34449-208">您使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。</span><span class="sxs-lookup"><span data-stu-id="34449-208">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="34449-209">作業會處理為背景作業，並會針對每個批次產生操作 ID。</span><span class="sxs-lookup"><span data-stu-id="34449-209">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="34449-210">批次最多可包含5000個使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-210">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="34449-211">您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-211">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="34449-212">若要深入瞭解，請參閱 [將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="34449-212">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="34449-213">疑難排解</span><span class="sxs-lookup"><span data-stu-id="34449-213">Troubleshooting</span></span>

<span data-ttu-id="34449-214">**當您指派原則套件時，收到錯誤訊息**</span><span class="sxs-lookup"><span data-stu-id="34449-214">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="34449-215">如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="34449-215">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="34449-216">將原則套件重新指派給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="34449-216">Reassign the policy package to your users.</span></span> <span data-ttu-id="34449-217">重試此操作通常會修正此問題。</span><span class="sxs-lookup"><span data-stu-id="34449-217">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="34449-218">相關主題</span><span class="sxs-lookup"><span data-stu-id="34449-218">Related topics</span></span>

[<span data-ttu-id="34449-219">指派策略給小組中的使用者</span><span class="sxs-lookup"><span data-stu-id="34449-219">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="34449-220">EDU 管理員的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-220">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="34449-221">醫療保健的團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-221">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="34449-222">政府團隊原則套件</span><span class="sxs-lookup"><span data-stu-id="34449-222">Teams policy packages for government</span></span>](policy-packages-gov.md)
