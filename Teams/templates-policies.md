---
title: 管理管理中心的團隊範本
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
description: 瞭解如何在系統管理中心管理團隊範本
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9704fdb92689031d44fa692383c701ec47877fc6
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145880"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="ba6b1-103">在系統管理中心建立及管理團隊範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-103">Create and manage Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="ba6b1-104">在系統管理中心建立範本原則，以管理您的最終使用者所顯示的團隊範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-104">Manage the Teams templates that are shown to your end users by creating templates policies in the admin center.</span></span> <span data-ttu-id="ba6b1-105">在每個範本原則中，您可以指定要顯示或隱藏哪些範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="ba6b1-106">將不同的使用者指派給不同的範本原則，讓您的使用者只能查看指定的小組範本子集。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="ba6b1-107">建立範本原則並指派可用的範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="ba6b1-108">登入團隊系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="ba6b1-109">展開 **團隊**  >  **範本原則**。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="ba6b1-110">選取 [新增 **]**。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-110">Select **Add**.</span></span>

    ![已選取範本原則，且醒目提示 [新增]](media/template-policies-1.png)

1. <span data-ttu-id="ba6b1-112">在 [ **範本原則設定** ] 區段中，填寫下欄欄位：</span><span class="sxs-lookup"><span data-stu-id="ba6b1-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="ba6b1-113">範本原則名稱</span><span class="sxs-lookup"><span data-stu-id="ba6b1-113">Templates Policy name</span></span>

    - <span data-ttu-id="ba6b1-114">範本原則簡短描述</span><span class="sxs-lookup"><span data-stu-id="ba6b1-114">Templates Policy short description</span></span>

2. <span data-ttu-id="ba6b1-115">在 [可 **查看範本** ] 表格中，選取您要隱藏的範本，然後選取 [ **隱藏**]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![選取的範本，並醒目提示 [隱藏]](media/template-policies-2.png)

    <span data-ttu-id="ba6b1-117">您可以在 [ **隱藏範本** ] 表格中查看您已選取隱藏的範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="ba6b1-118">若要取消隱藏某些範本，請滾動至 [ **隱藏範本** ] 表格。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="ba6b1-119">選取要取消隱藏的範本，然後選取 [ **顯示**]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![選取的範本，並醒目提示 [隱藏]](media/template-policies-3.png)

   <span data-ttu-id="ba6b1-121">選取的範本會出現在您的可 **查看範本** 表格中。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="ba6b1-122">選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-122">Select **Save**.</span></span>

   <span data-ttu-id="ba6b1-123">您的新範本原則會顯示在 [ **範本原則** ] 清單中。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="ba6b1-124">將使用者指派給範本原則</span><span class="sxs-lookup"><span data-stu-id="ba6b1-124">Assign users to the template policies</span></span>

<span data-ttu-id="ba6b1-125">指派給原則的使用者將只能在該原則中查看可查看的範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="ba6b1-126">從 [ **範本原則**]，選取原則，然後選取 [ **管理使用者**]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="ba6b1-127">輸入要指派給此原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-127">Type the users to assign to this policy.</span></span>

   ![選取的範本，並醒目提示 [隱藏]](media/template-policies-4.png)

3. <span data-ttu-id="ba6b1-129">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="ba6b1-130">最多可能需要24小時才能讓新原則生效給使用者。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="ba6b1-131">範本原則的大小限制</span><span class="sxs-lookup"><span data-stu-id="ba6b1-131">Size limits for Template policies</span></span>

<span data-ttu-id="ba6b1-132">您可以針對每個原則隱藏100範本的最大值。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="ba6b1-133">如果指定原則已隱藏100範本，則會停用 [ **隱藏** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="ba6b1-134">常見問題集</span><span class="sxs-lookup"><span data-stu-id="ba6b1-134">Frequently asked questions</span></span>

<span data-ttu-id="ba6b1-135">**問：我可以將使用者成批指派給小組範本原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="ba6b1-136">答：是的，我們支援 PowerShell 中範本原則的批次作業。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="ba6b1-137">此動作的原則類型是 [TeamsTemplatePermissionPolicy]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="ba6b1-138">瞭解更多資訊</span><span class="sxs-lookup"><span data-stu-id="ba6b1-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="ba6b1-139">**問：您可以將群組指派給小組範本原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="ba6b1-140">答：目前沒有。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-140">A: Currently no.</span></span> <span data-ttu-id="ba6b1-141">此功能將于未來推出。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="ba6b1-142">**問：如果建立新的範本，範本會包含在 [我的原則] 中嗎？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="ba6b1-143">答：預設會顯示任何新的範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="ba6b1-144">您可以在系統管理中心的 [範本原則] 區段中，選擇隱藏範本。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="ba6b1-145">**問：如果範本遭到刪除，會發生什麼情況？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="ba6b1-146">答：任何已刪除的範本，都不會再出現在任何範本原則中。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="ba6b1-147">**問：我可以在團隊系統管理中心將多個使用者指派給範本原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="ba6b1-148">答：是的。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-148">A: Yes.</span></span>

1. <span data-ttu-id="ba6b1-149">在系統管理中心中，移至 [ **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="ba6b1-150">在 [使用者清單] 表格中，選取您要指派給特定範本原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="ba6b1-151">選取 [編輯設定]，然後變更 [範本原則] 欄位。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="ba6b1-152">選取 [套用]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-152">Select apply.</span></span>
   <span data-ttu-id="ba6b1-153">深入瞭解 [Microsoft 團隊中的使用者指派原則-Microsoft 團隊 \| microsoft 文檔](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="ba6b1-154">**問：如何查看指派給特定原則的所有使用者？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="ba6b1-155">答：在系統管理中心：</span><span class="sxs-lookup"><span data-stu-id="ba6b1-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="ba6b1-156">移至 [ **使用者** ] 區段。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="ba6b1-157">選取 [使用者清單] 資料表中的篩選，然後篩選團隊範本原則。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="ba6b1-158">選取 **[** 套用]。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-158">Select **Apply**.</span></span>

![選取的範本，並醒目提示 [隱藏]](media/template-policies-5.png)

<span data-ttu-id="ba6b1-160">**問：我可以透過 PowerShell 管理範本原則嗎？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="ba6b1-161">答：不行，不支援這種情況。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-161">A: No, this isn't supported.</span></span>

<span data-ttu-id="ba6b1-162">**問：是否有適用于 EDU 的範本原則？**</span><span class="sxs-lookup"><span data-stu-id="ba6b1-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="ba6b1-163">答：不行，不支援這種情況。</span><span class="sxs-lookup"><span data-stu-id="ba6b1-163">A: No, this isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ba6b1-164">相關主題</span><span class="sxs-lookup"><span data-stu-id="ba6b1-164">Related topics</span></span>

- [<span data-ttu-id="ba6b1-165">在系統管理中心開始使用團隊範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="ba6b1-166">建立自訂團隊範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="ba6b1-167">從現有團隊建立範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="ba6b1-168">從現有的小組範本建立小組範本</span><span class="sxs-lookup"><span data-stu-id="ba6b1-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="ba6b1-169">在 Microsoft 團隊中將原則指派給使用者-microsoft 團隊 \| Microsoft 文檔</span><span class="sxs-lookup"><span data-stu-id="ba6b1-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="ba6b1-170">將使用者成批指派給原則</span><span class="sxs-lookup"><span data-stu-id="ba6b1-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
