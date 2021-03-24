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
ms.openlocfilehash: db28d1fa3c84210c3f1e2d80e74a59252f922258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093923"
---
# <a name="manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="a772e-103">在系統管理中心管理 Teams 範本</span><span class="sxs-lookup"><span data-stu-id="a772e-103">Manage Teams templates in the admin center</span></span>

<span data-ttu-id="a772e-104">在系統管理中心建立範本政策，管理使用者看到的 Teams 範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="a772e-105">在每個範本策略中，您可以指定顯示或隱藏哪些範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="a772e-106">將不同的使用者指派給不同的範本策略，讓使用者只查看指定的 Teams 範本子集。</span><span class="sxs-lookup"><span data-stu-id="a772e-106">Assign different users to different template policies so that your users view only the subset of Teams templates specified.</span></span>

<span data-ttu-id="a772e-107">請觀看這段短片，瞭解如何管理範本策略。</span><span class="sxs-lookup"><span data-stu-id="a772e-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="a772e-108">建立範本策略並指派可用的範本</span><span class="sxs-lookup"><span data-stu-id="a772e-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="a772e-109">登入 Teams 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="a772e-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="a772e-110">展開 **Teams**  >  **範本政策**。</span><span class="sxs-lookup"><span data-stu-id="a772e-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="a772e-111">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="a772e-111">Select **Add**.</span></span>

    ![已選取範本策略，且已強調新增](media/template-policies-1.png)

1. <span data-ttu-id="a772e-113">在範本 **策略設定區** 段，完成下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="a772e-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="a772e-114">範本策略名稱</span><span class="sxs-lookup"><span data-stu-id="a772e-114">Templates Policy name</span></span>

    - <span data-ttu-id="a772e-115">範本策略簡短描述</span><span class="sxs-lookup"><span data-stu-id="a772e-115">Templates Policy short description</span></span>

2. <span data-ttu-id="a772e-116">在可 **查看的範本資料** 表中，選取您想要隱藏的範本， **然後選取** 隱藏 。</span><span class="sxs-lookup"><span data-stu-id="a772e-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![已選取的範本，並突顯隱藏](media/template-policies-2.png)

    <span data-ttu-id="a772e-118">您可以在隱藏範本資料表中看到您選取要 **隱藏的** 範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="a772e-119">若要取消隱藏特定範本，請卷起至隱藏 **範本** 資料表。</span><span class="sxs-lookup"><span data-stu-id="a772e-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

2. <span data-ttu-id="a772e-120">選取要取消隱藏的範本， **然後選取** 顯示 。</span><span class="sxs-lookup"><span data-stu-id="a772e-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![未隱藏的所選範本](media/template-policies-3.png)

   <span data-ttu-id="a772e-122">選取的範本會顯示在可查看 **的範本資料** 表中。</span><span class="sxs-lookup"><span data-stu-id="a772e-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="a772e-123">選取 **儲存**。</span><span class="sxs-lookup"><span data-stu-id="a772e-123">Select **Save**.</span></span>

   <span data-ttu-id="a772e-124">您的新範本策略會顯示在範本 **策略清單中** 。</span><span class="sxs-lookup"><span data-stu-id="a772e-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="a772e-125">將使用者指派給範本策略</span><span class="sxs-lookup"><span data-stu-id="a772e-125">Assign users to the template policies</span></span>

<span data-ttu-id="a772e-126">指派給策略的使用者只能查看該策略內的可查看範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="a772e-127">從 **範本政策** 中，選取一個策略，然後選取管理 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="a772e-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="a772e-128">輸入要指派給此策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="a772e-128">Type the users to assign to this policy.</span></span>

   ![將使用者指派給範本策略](media/template-policies-4.png)

3. <span data-ttu-id="a772e-130">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="a772e-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="a772e-131">您的新政策最多可能需要 24 小時，才能對使用者生效。</span><span class="sxs-lookup"><span data-stu-id="a772e-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="a772e-132">範本政策的大小限制</span><span class="sxs-lookup"><span data-stu-id="a772e-132">Size limits for Template policies</span></span>

<span data-ttu-id="a772e-133">每個策略最多可以隱藏 100 個範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="a772e-134">如果 **已** 隱藏 100 個範本，則停用了隱藏按鈕。</span><span class="sxs-lookup"><span data-stu-id="a772e-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a772e-135">常見問題集</span><span class="sxs-lookup"><span data-stu-id="a772e-135">Frequently asked questions</span></span>

<span data-ttu-id="a772e-136">**問：我可以批次將使用者指派給小組範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a772e-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="a772e-137">答：是，我們支援 PowerShell 中範本策略的批次指派。</span><span class="sxs-lookup"><span data-stu-id="a772e-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="a772e-138">此動作的策略類型為 TeamsTemplatePermissionPolicy。</span><span class="sxs-lookup"><span data-stu-id="a772e-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="a772e-139">瞭解更多資訊</span><span class="sxs-lookup"><span data-stu-id="a772e-139">Learn more</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="a772e-140">**問：群組可以指派給小組範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a772e-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="a772e-141">答：目前否。</span><span class="sxs-lookup"><span data-stu-id="a772e-141">A: Currently no.</span></span> <span data-ttu-id="a772e-142">這項功能將在未來提供。</span><span class="sxs-lookup"><span data-stu-id="a772e-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="a772e-143">**問：如果已建立新範本，範本會包含在我的政策中嗎？**</span><span class="sxs-lookup"><span data-stu-id="a772e-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="a772e-144">答：任何新範本預設都會顯示。</span><span class="sxs-lookup"><span data-stu-id="a772e-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="a772e-145">您可以在範本政策區段的系統管理中心選擇隱藏範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="a772e-146">**問：刪除範本時會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="a772e-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="a772e-147">答：任何已刪除的範本將不再存在於任何範本政策中。</span><span class="sxs-lookup"><span data-stu-id="a772e-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="a772e-148">**問：我可以在 Teams 系統管理中心將多個使用者指派給範本策略嗎？**</span><span class="sxs-lookup"><span data-stu-id="a772e-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="a772e-149">答：是。</span><span class="sxs-lookup"><span data-stu-id="a772e-149">A: Yes.</span></span>

1. <span data-ttu-id="a772e-150">在系統管理中心，前往 **使用者**。</span><span class="sxs-lookup"><span data-stu-id="a772e-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="a772e-151">在使用者清單表格中，選取要指派給特定範本策略的使用者。</span><span class="sxs-lookup"><span data-stu-id="a772e-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="a772e-152">選取編輯設定，然後變更範本政策欄位。</span><span class="sxs-lookup"><span data-stu-id="a772e-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="a772e-153">選取 Apply。</span><span class="sxs-lookup"><span data-stu-id="a772e-153">Select apply.</span></span>
   <span data-ttu-id="a772e-154">深入瞭解 [在 Microsoft Teams - Microsoft Teams \| Microsoft Docs 中指派策略給使用者](./assign-policies.md#assign-a-policy-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="a772e-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](./assign-policies.md#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="a772e-155">**問：如何查看指派給特定策略的所有使用者？**</span><span class="sxs-lookup"><span data-stu-id="a772e-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="a772e-156">答：在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="a772e-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="a772e-157">前往 **使用者區** 段。</span><span class="sxs-lookup"><span data-stu-id="a772e-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="a772e-158">在使用者清單資料表中選取篩選，然後針對團隊範本策略進行篩選。</span><span class="sxs-lookup"><span data-stu-id="a772e-158">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="a772e-159">選取 **Apply**。</span><span class="sxs-lookup"><span data-stu-id="a772e-159">Select **Apply**.</span></span>

![選取的範本策略和查看使用者](media/template-policies-5.png)

<span data-ttu-id="a772e-161">**問：我可以透過 PowerShell 管理範本政策嗎？**</span><span class="sxs-lookup"><span data-stu-id="a772e-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="a772e-162">答：否，不支援在 PowerShell 中管理範本。</span><span class="sxs-lookup"><span data-stu-id="a772e-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="a772e-163">**問：範本政策是否適用于 EDU？**</span><span class="sxs-lookup"><span data-stu-id="a772e-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="a772e-164">答：否，不支援 EDU 的範本策略。</span><span class="sxs-lookup"><span data-stu-id="a772e-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a772e-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="a772e-165">Related topics</span></span>

- [<span data-ttu-id="a772e-166">在系統管理中心開始使用小組範本</span><span class="sxs-lookup"><span data-stu-id="a772e-166">Get started with team templates in the admin center</span></span>](./get-started-with-teams-templates-in-the-admin-console.md)

- [<span data-ttu-id="a772e-167">建立自訂小組範本</span><span class="sxs-lookup"><span data-stu-id="a772e-167">Create a custom team template</span></span>](./create-a-team-template.md)

- [<span data-ttu-id="a772e-168">從現有的小組建立範本</span><span class="sxs-lookup"><span data-stu-id="a772e-168">Create a template from an existing team</span></span>](./create-template-from-existing-team.md)

- [<span data-ttu-id="a772e-169">從現有的小組範本建立小組範本</span><span class="sxs-lookup"><span data-stu-id="a772e-169">Create a team template from an existing team template</span></span>](./create-template-from-existing-template.md)

- [<span data-ttu-id="a772e-170">在 Microsoft Teams 中指派策略給使用者 - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="a772e-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](./assign-policies.md)

- [<span data-ttu-id="a772e-171">將使用者批次指派給策略</span><span class="sxs-lookup"><span data-stu-id="a772e-171">Batch assign users to a policy</span></span>](/powershell/module/teams/new-csbatchpolicyassignmentoperation)