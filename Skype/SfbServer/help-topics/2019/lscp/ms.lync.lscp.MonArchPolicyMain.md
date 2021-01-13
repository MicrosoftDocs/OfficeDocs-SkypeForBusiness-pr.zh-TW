---
title: 封存原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以使用封存原則來啟用及停用駐留在商務用 Skype Server 上之使用者的封存功能。 在每個封存原則中，您可以啟用或停用下列其中一項或兩項的封存：
ms.openlocfilehash: 041fc71da18ff38b14e82ce9d2ab14f366326b29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833613"
---
# <a name="archiving-policy"></a><span data-ttu-id="a1fe7-104">封存原則</span><span class="sxs-lookup"><span data-stu-id="a1fe7-104">Archiving Policy</span></span>
 
<span data-ttu-id="a1fe7-105">您可以使用封存原則來啟用及停用駐留在商務用 Skype Server 上之使用者的封存功能。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="a1fe7-106">在每個封存原則中，您可以啟用或停用下列其中一項或兩項的封存：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="a1fe7-107">內部通訊</span><span class="sxs-lookup"><span data-stu-id="a1fe7-107">Internal communications</span></span>
    
- <span data-ttu-id="a1fe7-108">在內部網路以外至少包含一位使用者的外部通訊 (通訊) </span><span class="sxs-lookup"><span data-stu-id="a1fe7-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="a1fe7-109">封存原則包含全域原則，並選擇性地包含一或多個網站與使用者封存原則：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="a1fe7-110">**全域原則** 預設會在所有部署中建立全域原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="a1fe7-111">您可以編輯全域原則，但無法刪除此原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="a1fe7-112">若嘗試將其刪除，所有選項都會重設為預設值。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="a1fe7-113">**網站原則 (選用)** 您可以指定一或多個網站封存原則，每個網站封存原則都可以設定為啟用和停用單一網站的內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="a1fe7-114">網站原則會覆寫全域原則，但僅限於您的封存網站原則中所指定的網站。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="a1fe7-115">您可以編輯或刪除網站原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="a1fe7-116">**使用者原則 (選用)** 您可以指定一或多個使用者封存原則，每個使用者封存原則都可以設定為啟用及停用特定使用者或使用者群組的內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="a1fe7-117">使用者原則會覆寫全域原則及網站原則，但僅限於您指派使用者層級封存原則的使用者和使用者群組。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="a1fe7-118">您可以編輯或刪除使用者原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a1fe7-119">封存原則只適用于駐留在商務用 Skype Server 上的使用者。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="a1fe7-120">如果您使用 Exchange 整合將封存資料儲存在 Microsoft Exchange 中，則 Exchange 原則會控制位於 Exchange 上之使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="a1fe7-121">若要為這些使用者啟用封存，使用者的信箱必須置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="a1fe7-122">「封存 **原則** 」頁面會列出為您的部署設定的每個封存原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-122">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment.</span></span> <span data-ttu-id="a1fe7-123">它也會顯示原則名稱、範圍 (全域、網站或使用者) ，以及針對每個封存原則啟用的封存選項。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-123">It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy.</span></span> <span data-ttu-id="a1fe7-124">在 [封存 **原則** ] 頁面上，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-124">From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="a1fe7-125">**新** 您可以新增一或多個下列選用的封存原則：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="a1fe7-126">網站原則</span><span class="sxs-lookup"><span data-stu-id="a1fe7-126">Site policy</span></span>
    
  - <span data-ttu-id="a1fe7-127">使用者原則</span><span class="sxs-lookup"><span data-stu-id="a1fe7-127">User policy</span></span>
    
- <span data-ttu-id="a1fe7-128">**編輯** 您可以變更頁面上所列之任何封存原則的選項。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="a1fe7-129">使用此選項，您可以執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="a1fe7-130">**顯示詳細資料** 此選項會開啟一個對話方塊，您可以在其中變更封存原則的封存選項。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="a1fe7-131">**全選** 此選項會選取清單中的所有封存原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="a1fe7-132">**Delete** 此選項會刪除所有選取的封存原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="a1fe7-133">**動作** 您可以使用此選項，在頁面上所列的任何原則中快速啟用或停用內部或外部通訊的封存，而不是編輯原則。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="a1fe7-134">[ **動作** ] 下的可用選項取決於封存原則中目前指定的選項。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="a1fe7-135">所有選項均可使用，但目前對封存原則有效的選項除外。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="a1fe7-136">選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a1fe7-136">Options include the following:</span></span>
    
  - <span data-ttu-id="a1fe7-137">**啟用內部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="a1fe7-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="a1fe7-138">**停用內部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="a1fe7-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="a1fe7-139">**啟用外部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="a1fe7-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="a1fe7-140">**停用外部通訊的封存**</span><span class="sxs-lookup"><span data-stu-id="a1fe7-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="a1fe7-141">**Refresh** 您可以重新整理「封存 **原則** 」頁面，以確認所有封存原則選項的狀態。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="a1fe7-142">如需有關封存功能及功能（包括 Exchange 整合）的詳細資訊，請參閱 [在商務用 Skype server 中規劃](../../../plan-your-deployment/archiving/archiving.md)封存、 [部署商務用 skype 伺服器](../../../deploy/deploy-archiving/deploy-archiving.md)的封存，以及 [管理商務用 skype server 中](../../../manage/archiving/archiving.md)的封存。</span><span class="sxs-lookup"><span data-stu-id="a1fe7-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

