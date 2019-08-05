---
title: 封存原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用 [封存原則] 來啟用和停用駐留在商務用 Skype Server 上的使用者的封存。 在每個封存原則中，您可以從下列項目擇一或兩者皆啟用或停用封存：
ms.openlocfilehash: bdeb7925256e47ac61d0210e1be36e28dbdfc0d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192296"
---
# <a name="archiving-policy"></a><span data-ttu-id="9cc43-104">封存原則</span><span class="sxs-lookup"><span data-stu-id="9cc43-104">Archiving Policy</span></span>
 
<span data-ttu-id="9cc43-105">您可以使用 [封存原則] 來啟用和停用駐留在商務用 Skype Server 上的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="9cc43-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="9cc43-106">在每個封存原則中，您可以從下列項目擇一或兩者皆啟用或停用封存：</span><span class="sxs-lookup"><span data-stu-id="9cc43-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="9cc43-107">內部通訊</span><span class="sxs-lookup"><span data-stu-id="9cc43-107">Internal communications</span></span>
    
- <span data-ttu-id="9cc43-108">外部通訊 (此通訊至少包含一位在您內部網路外的使用者)</span><span class="sxs-lookup"><span data-stu-id="9cc43-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="9cc43-109">封存原則包含全域原則以及選用的一或多個網站與使用者封存原則：</span><span class="sxs-lookup"><span data-stu-id="9cc43-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="9cc43-110">**全域原則**全域原則預設是在所有部署中建立。</span><span class="sxs-lookup"><span data-stu-id="9cc43-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="9cc43-111">您可以編輯全域原則，但無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="9cc43-112">如果嘗試刪除此原則，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="9cc43-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="9cc43-113">**網站原則 (選用)** 您可以指定一或多個網站封存策略, 每個原則都可以設定為啟用和停用單一網站的內部或外部通訊的歸檔。</span><span class="sxs-lookup"><span data-stu-id="9cc43-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="9cc43-114">網站原則將覆寫全域原則，但僅限於該封存網站原則中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="9cc43-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="9cc43-115">您可以編輯或刪除網站原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="9cc43-116">**使用者原則 (選用)** 您可以指定一或多個使用者存檔原則, 每個策略都可以設定為啟用和停用特定使用者或使用者群組的內部或外部通訊的歸檔。</span><span class="sxs-lookup"><span data-stu-id="9cc43-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="9cc43-117">使用者原則會覆寫全域原則及網站原則，但僅限於獲得您指派使用者等級封存原則的使用者及使用者群組。</span><span class="sxs-lookup"><span data-stu-id="9cc43-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="9cc43-118">您可以編輯或刪除使用者原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9cc43-119">存檔原則只適用于駐留在商務用 Skype Server 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="9cc43-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="9cc43-120">如果您使用 Exchange 整合來儲存 Microsoft Exchange 中的存檔資料, 則 Exchange 原則會控制駐留在 Exchange 的使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="9cc43-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="9cc43-121">若要為這些使用者啟用存檔, 使用者的信箱必須放在就地保留中。</span><span class="sxs-lookup"><span data-stu-id="9cc43-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="9cc43-p107">「封存原則」\*\*\*\* 頁面列出針對您部署所設定的每個封存原則。該頁面也會顯示原則名稱、範圍 (全域、網站或使用者)，以及已針對每個封存原則啟用的封存選項。您可從「封存原則」\*\*\*\* 頁面執行下列選項：</span><span class="sxs-lookup"><span data-stu-id="9cc43-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="9cc43-125">**新增**您可以新增下列其中一或多個選用的存檔原則:</span><span class="sxs-lookup"><span data-stu-id="9cc43-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="9cc43-126">網站原則</span><span class="sxs-lookup"><span data-stu-id="9cc43-126">Site policy</span></span>
    
  - <span data-ttu-id="9cc43-127">使用者原則</span><span class="sxs-lookup"><span data-stu-id="9cc43-127">User policy</span></span>
    
- <span data-ttu-id="9cc43-128">[**編輯**]您可以變更頁面上所列之任何存檔策略的選項。</span><span class="sxs-lookup"><span data-stu-id="9cc43-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="9cc43-129">使用此選項, 您可以執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="9cc43-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9cc43-130">**顯示詳細資料** 此選項會開啟對話方塊供您變更封存原則的封存選項。</span><span class="sxs-lookup"><span data-stu-id="9cc43-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="9cc43-131">**全選** 此選項會選取清單中的所有封存原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="9cc43-132">**刪除** 此選項會刪除所有選取的封存原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="9cc43-133">**動作**您可以使用這個選項, 在頁面上所列的任何原則中快速啟用或停用內部或外部通訊的封存, 而不是編輯原則。</span><span class="sxs-lookup"><span data-stu-id="9cc43-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="9cc43-134">[**動作**] 底下的可用選項, 取決於 [存檔原則] 中目前指定的選項。</span><span class="sxs-lookup"><span data-stu-id="9cc43-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="9cc43-135">除了目前對存檔原則有效的選項之外, 所有選項皆可使用。</span><span class="sxs-lookup"><span data-stu-id="9cc43-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="9cc43-136">選項包括下列各項:</span><span class="sxs-lookup"><span data-stu-id="9cc43-136">Options include the following:</span></span>
    
  - <span data-ttu-id="9cc43-137">**啟用內部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="9cc43-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9cc43-138">**停用內部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="9cc43-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="9cc43-139">**啟用外部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="9cc43-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="9cc43-140">**停用外部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="9cc43-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="9cc43-141">**更新**您可以重新整理 [封存**原則**] 頁面, 驗證所有存檔原則的選項狀態。</span><span class="sxs-lookup"><span data-stu-id="9cc43-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="9cc43-142">如需有關存檔功能和功能 (包括 Exchange 整合) 的詳細資料, 請參閱[在商務用 Skype server 中進行](../../../plan-your-deployment/archiving/archiving.md)封存、[部署商務](../../../deploy/deploy-archiving/deploy-archiving.md)用 skype server 的封存, 以及[管理商務用 skype 中的封存伺服器](../../../manage/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="9cc43-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

