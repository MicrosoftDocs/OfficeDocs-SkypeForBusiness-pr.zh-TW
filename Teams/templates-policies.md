---
title: 在系統管理中心管理 Teams 範本
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在系統管理中心管理 Teams 範本
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507966"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="a1ca5-103">在系統管理中心建立及管理 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="a1ca5-104">在系統管理中心建立範本策略，來管理使用者看到的 Teams 範本。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="a1ca5-105">在每個範本策略中，您可以指定顯示或隱藏哪些範本。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="a1ca5-106">將不同的使用者指派給不同的範本策略，這樣您的使用者就只會查看指定的 Teams 範本子集。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="a1ca5-107">建立範本策略並指派可用的範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="a1ca5-108">請登出 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="a1ca5-109">展開 **Teams**  >  **範本政策**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="a1ca5-110">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-110">Select **Add**.</span></span>

    ![已選取範本策略，且已強調顯示新增](media/template-policies-1.png)

1. <span data-ttu-id="a1ca5-112">在範本 **策略設定區** 段，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="a1ca5-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="a1ca5-113">範本政策名稱</span><span class="sxs-lookup"><span data-stu-id="a1ca5-113">Templates Policy name</span></span>

    - <span data-ttu-id="a1ca5-114">範本政策簡短描述</span><span class="sxs-lookup"><span data-stu-id="a1ca5-114">Templates Policy short description</span></span>

2. <span data-ttu-id="a1ca5-115">在可 **視圖範本資料** 表中，選取要隱藏的範本， **然後選取隱藏**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![已選取的範本，已強調顯示隱藏](media/template-policies-2.png)

    <span data-ttu-id="a1ca5-117">您可以在隱藏範本資料表中看到您選取要 **隱藏的範本。**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="a1ca5-118">若要取消隱藏特定範本，請卷卷至隱藏 **範本** 資料表。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="a1ca5-119">選取要取消隱藏的範本， **然後選取顯示**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![選取的未隱藏範本](media/template-policies-3.png)

   <span data-ttu-id="a1ca5-121">選取的範本會顯示在可觀看的 **範本資料** 表中。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="a1ca5-122">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-122">Select **Save**.</span></span>

   <span data-ttu-id="a1ca5-123">新的範本策略會顯示在範本策略 **清單中** 。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="a1ca5-124">將使用者指派給範本策略</span><span class="sxs-lookup"><span data-stu-id="a1ca5-124">Assign users to the template policies</span></span>

<span data-ttu-id="a1ca5-125">指派給該政策的使用者只能查看該政策內可查看的範本。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="a1ca5-126">從 **範本策略中**，選取一個策略，然後選取 **管理使用者**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="a1ca5-127">輸入要指派給此策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-127">Type the users to assign to this policy.</span></span>

   ![指派使用者至範本策略](media/template-policies-4.png)

3. <span data-ttu-id="a1ca5-129">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="a1ca5-130">您的新政策最多可能需要 24 小時，才能對使用者生效。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="a1ca5-131">範本策略的大小限制</span><span class="sxs-lookup"><span data-stu-id="a1ca5-131">Size limits for Template policies</span></span>

<span data-ttu-id="a1ca5-132">每個策略最多可以隱藏 100 個範本。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="a1ca5-133">如果 **已** 隱藏 100 個範本，則停用的隱藏按鈕。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a1ca5-134">常見問題集</span><span class="sxs-lookup"><span data-stu-id="a1ca5-134">Frequently asked questions</span></span>

<span data-ttu-id="a1ca5-135">**問：我可以批次指派使用者至小組範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="a1ca5-136">答：是，我們支援 PowerShell 中範本策略的批次指派。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="a1ca5-137">此動作的策略類型為 TeamsTemplatePermissionPolicy。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="a1ca5-138">瞭解更多資訊</span><span class="sxs-lookup"><span data-stu-id="a1ca5-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="a1ca5-139">**問：群組可以指派給小組範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="a1ca5-140">答：目前否。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-140">A: Currently no.</span></span> <span data-ttu-id="a1ca5-141">這項功能將于未來提供。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="a1ca5-142">**問：如果已建立新範本，該範本會包含在我的政策中嗎？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="a1ca5-143">答：根據預設，任何新的範本都會顯示。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="a1ca5-144">您可以選擇隱藏系統管理中心的範本，位於範本政策區段。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="a1ca5-145">**問：刪除範本時會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="a1ca5-146">答：任何已刪除的範本將不再存在於任何範本策略中。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="a1ca5-147">**問：我可以在 Teams 系統管理中心指派多個使用者至範本策略嗎？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="a1ca5-148">答：是。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-148">A: Yes.</span></span>

1. <span data-ttu-id="a1ca5-149">在系統管理中心，請前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="a1ca5-150">在使用者清單資料表中，選取要指派給特定範本策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="a1ca5-151">選取編輯設定，然後變更範本策略欄位。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="a1ca5-152">選取適用。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-152">Select apply.</span></span>
   <span data-ttu-id="a1ca5-153">深入瞭解在 Microsoft Teams 中指派[政策給使用者 - Microsoft Teams \| Microsoft Docs。](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="a1ca5-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="a1ca5-154">**問：如何查看指派給特定策略的所有使用者？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="a1ca5-155">答：在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="a1ca5-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="a1ca5-156">前往 **使用者區** 段。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="a1ca5-157">在使用者清單資料表中選取篩選，並篩選團隊範本策略。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="a1ca5-158">選取Apply 。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-158">Select **Apply**.</span></span>

![選取的範本策略和查看使用者](media/template-policies-5.png)

<span data-ttu-id="a1ca5-160">**問：我可以透過 PowerShell 管理範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="a1ca5-161">答：不支援在 PowerShell 中管理範本。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="a1ca5-162">**問：範本政策是否適用于 EDU？**</span><span class="sxs-lookup"><span data-stu-id="a1ca5-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="a1ca5-163">答：否，不支援 EDU 的範本策略。</span><span class="sxs-lookup"><span data-stu-id="a1ca5-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a1ca5-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="a1ca5-164">Related topics</span></span>

- [<span data-ttu-id="a1ca5-165">在系統管理中心開始使用小組範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="a1ca5-166">建立自訂小組範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="a1ca5-167">從現有小組建立範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="a1ca5-168">從現有的小組範本建立小組範本</span><span class="sxs-lookup"><span data-stu-id="a1ca5-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="a1ca5-169">在 Microsoft Teams 中指派策略給使用者 - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="a1ca5-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="a1ca5-170">批次指派使用者至策略</span><span class="sxs-lookup"><span data-stu-id="a1ca5-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
