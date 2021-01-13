---
title: 設定商務用 Skype Server 的封存原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 摘要：閱讀此主題以瞭解如何為商務用 Skype 伺服器使用者設定初始封存原則。
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820853"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="57cee-103">設定商務用 Skype Server 的封存原則</span><span class="sxs-lookup"><span data-stu-id="57cee-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="57cee-104">**摘要：** 閱讀此主題以瞭解如何為商務用 Skype 伺服器使用者設定初始封存原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="57cee-105">在商務用 Skype Server 中，您可以使用原則為位於商務用 Skype Server 上的使用者啟用和停用內部通訊和外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="57cee-106">其中包括下列項目：</span><span class="sxs-lookup"><span data-stu-id="57cee-106">This includes the following:</span></span>
  
- <span data-ttu-id="57cee-107">當您部署商務用 Skype Server 時，預設會建立全域原則</span><span class="sxs-lookup"><span data-stu-id="57cee-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="57cee-108">選用的網站層級原則，指定如何為特定網站實施封存</span><span class="sxs-lookup"><span data-stu-id="57cee-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="57cee-109">選用的使用者層級原則，指定如何為特定使用者執行封存</span><span class="sxs-lookup"><span data-stu-id="57cee-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="57cee-110">您在部署封存時，最初會設定封存原則，但您可以在部署後變更、新增和刪除原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="57cee-111">在商務用 Skype Server 控制台中，您可以使用 [封存 **與監控**] 群組的 [封存 **原則**] 頁面，以管理全域、網站及使用者層級的原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="57cee-112">若要控制封存的實施，您必須指定選項，例如是否封存 IM 或會議、使用重要模式，以及清除選項。</span><span class="sxs-lookup"><span data-stu-id="57cee-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="57cee-113">根據預設，全域封存設定或任何網站或集區封存設定中未啟用任何選項。</span><span class="sxs-lookup"><span data-stu-id="57cee-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="57cee-114">您應該先指定所有適當的選項，才能啟用內部或外部通訊的封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="57cee-115">如需詳細資訊，請參閱 [設定商務用 Skype Server 的封存選項](configure-archiving-options.md)。</span><span class="sxs-lookup"><span data-stu-id="57cee-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="57cee-116">如果您為部署啟用 Microsoft Exchange 整合，Exchange In-Place 保留原則會控制是否為位於 Exchange 上的使用者啟用封存，並將其信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="57cee-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="57cee-117">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [在商務用 Skype Server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="57cee-118">如需如何在部署後管理原則的詳細資訊，請參閱 [管理商務用 Skype Server 中](../../manage/archiving/policies.md)的封存原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="57cee-119">全域原則</span><span class="sxs-lookup"><span data-stu-id="57cee-119">Global policy</span></span>

<span data-ttu-id="57cee-120">當您部署前端伺服器時，商務用 Skype 伺服器會建立封存的全域原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="57cee-121">預設會停用全域原則中的封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="57cee-122">「全域」原則會控制是否對整個部署啟用內部和外部通訊的封存，除非您設定網站或使用者原則，以覆寫全域原則，或您針對部分或所有使用者使用 Microsoft Exchange 整合。</span><span class="sxs-lookup"><span data-stu-id="57cee-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="57cee-123">如果您使用 Microsoft Exchange 整合，全域原則不會套用到所有位於 Exchange 上的使用者，並將信箱置於 In-Place 保留狀態。</span><span class="sxs-lookup"><span data-stu-id="57cee-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="57cee-124">為商務用 Skype Server 封存資料庫設定封存的全域原則</span><span class="sxs-lookup"><span data-stu-id="57cee-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="57cee-125">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="57cee-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57cee-126">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="57cee-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="57cee-127">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="57cee-128">在 **[封存原則]** 頁面上，依序按一下 **[通用]** 和 **[編輯]**，然後按一下 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="57cee-129">在 [編輯封存原則 - 通用] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57cee-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="57cee-130">如果您不想要使用此預設全域名稱，請在 **[名稱]** 中指定全域原則的新名稱。</span><span class="sxs-lookup"><span data-stu-id="57cee-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="57cee-131">在 [ **描述**] 中，提供 (原則的相關資訊（例如，  *divisionName*  的全域原則）。</span><span class="sxs-lookup"><span data-stu-id="57cee-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="57cee-132">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的內部通訊封存，請選取或清除 **[封存內部通訊]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="57cee-133">若要控制未特別透過網站原則或使用者原則控制之所有網站及使用者的外部通訊封存，請選取或清除 [封存外部通訊] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="57cee-134">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="57cee-135">網站原則</span><span class="sxs-lookup"><span data-stu-id="57cee-135">Site policies</span></span>

<span data-ttu-id="57cee-136">您可以為每個網站建立封存原則，以啟用或停用特定網站的封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="57cee-137">網站原則會覆寫全域原則，但使用者原則會覆寫網站原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="57cee-138">封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 上，且其信箱置於 In-Place 保留狀態時，則僅適用。</span><span class="sxs-lookup"><span data-stu-id="57cee-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="57cee-139">建立網站的封存原則</span><span class="sxs-lookup"><span data-stu-id="57cee-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="57cee-140">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="57cee-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57cee-141">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="57cee-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="57cee-142">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="57cee-143">如需有關封存原則如何運作（包括全域、網站及使用者原則的階層）的詳細資訊，請參閱 [在商務用 Skype Server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="57cee-144">按一下 [新增]，然後按一下 [站台原則]。</span><span class="sxs-lookup"><span data-stu-id="57cee-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="57cee-145">在 [ **選取網站**] 中，按一下要套用原則的網站。</span><span class="sxs-lookup"><span data-stu-id="57cee-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="57cee-146">在 **[新增封存原則]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57cee-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="57cee-147">在 [ **名稱**] 中，指定網站原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="57cee-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="57cee-148">在 [ **描述**] 中，提供網站原則 (的相關資訊（例如，Redmond) 的網站原則）。</span><span class="sxs-lookup"><span data-stu-id="57cee-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="57cee-149">若要控制指定網站的內部通訊封存，請選取或清除 [封存 **內部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="57cee-150">若要控制指定網站的外部通訊封存，請選取或清除 [封存 **外部通訊** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="57cee-151">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="57cee-152">使用者原則</span><span class="sxs-lookup"><span data-stu-id="57cee-152">User policies</span></span>

<span data-ttu-id="57cee-153">您可以為使用者建立和設定封存原則，然後將原則套用至特定的使用者或使用者群組，來啟用或停用特定使用者的封存。</span><span class="sxs-lookup"><span data-stu-id="57cee-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="57cee-154">使用者原則會覆寫任何全域原則或網站原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="57cee-155">封存原則只有在您未使用 Microsoft Exchange 整合時才會套用，否則，如果您使用 Microsoft Exchange 整合，但有部分使用者未位於 Exchange 上，且其信箱置於 In-Place 保留狀態時，則僅適用。</span><span class="sxs-lookup"><span data-stu-id="57cee-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="57cee-156">為駐留在商務用 Skype Server 上的使用者設定封存原則</span><span class="sxs-lookup"><span data-stu-id="57cee-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="57cee-157">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="57cee-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57cee-158">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="57cee-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="57cee-159">在左側導覽列中，依序按一下 **[監控和封存]** 和 **[封存原則]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="57cee-160">依序按一下 **[新增]** 和 **[使用者原則]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="57cee-161">在 [新增封存原則] 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="57cee-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="57cee-162">在 [名稱] 中，指定使用者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="57cee-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="57cee-163">在 [描述] 中，提供何謂使用者原則的相關資訊 (例如，適用於法務部門的使用者原則)。</span><span class="sxs-lookup"><span data-stu-id="57cee-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="57cee-164">若要控制使用者原則的內部通訊封存，請選取或清除 [封存內部通訊] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="57cee-165">若要控制使用者原則的外部通訊封存，請選取或清除 [封存外部通訊] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="57cee-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="57cee-166">按一下 [認可]。</span><span class="sxs-lookup"><span data-stu-id="57cee-166">Click **Commit**.</span></span>
    
<span data-ttu-id="57cee-167">使用者原則僅會套用至您指派該原則的使用者。</span><span class="sxs-lookup"><span data-stu-id="57cee-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="57cee-168">將商務用 Skype Server 封存原則套用至使用者</span><span class="sxs-lookup"><span data-stu-id="57cee-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="57cee-169">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="57cee-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="57cee-170">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="57cee-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="57cee-171">在左導覽列中，按一下 **[使用者]**，然後搜尋想要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="57cee-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="57cee-172">在列出搜尋結果的表格中，按一下使用者帳戶，並依序按一下 **[編輯]** 及 **[顯示詳細資料]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="57cee-173">在 [封存 **原則**] 下的 [**編輯商務用 Skype Server 使用者**] 中，選取您要套用的封存使用者原則。</span><span class="sxs-lookup"><span data-stu-id="57cee-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="57cee-174">**\<Automatic\>** 設定將套用預設伺服器安裝設定。</span><span class="sxs-lookup"><span data-stu-id="57cee-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="57cee-175">伺服器會自動套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="57cee-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="57cee-176">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="57cee-176">Click **Commit**.</span></span>
    

