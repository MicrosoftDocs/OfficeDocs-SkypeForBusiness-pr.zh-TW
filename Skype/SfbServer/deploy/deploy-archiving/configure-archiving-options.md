---
title: 設定商務用 Skype Server 的封存選項
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
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 摘要：閱讀此主題以瞭解如何設定商務用 Skype Server 的初始封存選項。 您在部署封存時，您必須先設定封存設定，但是您可以在部署後變更、新增和刪除設定。
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815533"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="641c4-104">設定商務用 Skype Server 的封存選項</span><span class="sxs-lookup"><span data-stu-id="641c4-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="641c4-105">**摘要：** 閱讀此主題以瞭解如何為商務用 Skype 伺服器設定初始封存選項。</span><span class="sxs-lookup"><span data-stu-id="641c4-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="641c4-106">您在部署封存時，您必須先設定封存設定，但是您可以在部署後變更、新增和刪除設定。</span><span class="sxs-lookup"><span data-stu-id="641c4-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="641c4-107">若要設定初始封存設定，您可以使用商務用 Skype Server 控制台指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="641c4-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="641c4-108">當您部署商務用 Skype Server 時，預設會建立全域層級設定</span><span class="sxs-lookup"><span data-stu-id="641c4-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="641c4-109">選用的網站層級設定，指定如何為特定網站實施封存</span><span class="sxs-lookup"><span data-stu-id="641c4-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="641c4-110">選用集區層級設定，指定如何為特定集區實施封存</span><span class="sxs-lookup"><span data-stu-id="641c4-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="641c4-111">您將需要為下列專案設定選項：</span><span class="sxs-lookup"><span data-stu-id="641c4-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="641c4-112">是否要啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="641c4-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="641c4-113">是否要封存 IM 會話</span><span class="sxs-lookup"><span data-stu-id="641c4-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="641c4-114">是否要封存 web 會議會話</span><span class="sxs-lookup"><span data-stu-id="641c4-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="641c4-115">封存無法使用時是否封鎖活動</span><span class="sxs-lookup"><span data-stu-id="641c4-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="641c4-116">是否使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="641c4-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="641c4-117">如何設定資料的清除和匯出</span><span class="sxs-lookup"><span data-stu-id="641c4-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="641c4-118">您應該先指定所有適當的選項，才能啟用封存。</span><span class="sxs-lookup"><span data-stu-id="641c4-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="641c4-119">如需如何執行封存設定的詳細資訊，包括您可以指定哪些選項及封存設定的階層，請參閱 [在商務用 Skype Server 中規劃](../../plan-your-deployment/archiving/archiving.md)封存。</span><span class="sxs-lookup"><span data-stu-id="641c4-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="641c4-120">如需如何使用控制台或使用 Windows PowerShell 來管理設定的詳細資訊，請參閱 [manage 封存 options In 商務用 Skype Server](../../manage/archiving/options.md)。</span><span class="sxs-lookup"><span data-stu-id="641c4-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="641c4-121">設定全域層級封存選項</span><span class="sxs-lookup"><span data-stu-id="641c4-121">Configure global level archiving options</span></span>

<span data-ttu-id="641c4-122">當您將封存新增至拓撲併發行拓撲時，商務用 Skype 伺服器會建立通用設定進行封存。</span><span class="sxs-lookup"><span data-stu-id="641c4-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="641c4-123">根據預設，全域設定中不會啟用任何封存選項。</span><span class="sxs-lookup"><span data-stu-id="641c4-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="641c4-124">全域設定會控制針對整個部署啟用哪些選項，除非您設定的網站或集區設定會覆寫全域設定。</span><span class="sxs-lookup"><span data-stu-id="641c4-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="641c4-125">若要在全域層級設定封存選項：</span><span class="sxs-lookup"><span data-stu-id="641c4-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="641c4-126">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="641c4-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="641c4-127">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="641c4-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="641c4-128">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="641c4-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="641c4-129">**在 [封存** 設定] 頁面上，依序按一下 [**全域**]、[**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="641c4-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="641c4-130">在 [ **編輯封存設定-全域**] 的 [封存 **設定** ] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="641c4-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="641c4-131">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="641c4-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="641c4-132">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="641c4-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="641c4-133">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="641c4-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="641c4-134">此外，在 [ **編輯封存設定-通用** ] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="641c4-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="641c4-135">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="641c4-136">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="641c4-137">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="641c4-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="641c4-138">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="641c4-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="641c4-139">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="641c4-140">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="641c4-141">設定網站層級的封存選項</span><span class="sxs-lookup"><span data-stu-id="641c4-141">Configure site level archiving options</span></span>

<span data-ttu-id="641c4-142">您可以指定特定網站的封存選項。</span><span class="sxs-lookup"><span data-stu-id="641c4-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="641c4-143">網站設定優先於全域設定，但僅適用於網站設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="641c4-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="641c4-144">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="641c4-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="641c4-145">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="641c4-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="641c4-146">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="641c4-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="641c4-147">在 **[封存組態]** 頁面上，按一下 **[新增]**，然後按一下 **[站台組態]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="641c4-148">在 **[選取站台]** 中，選取要設定封存的網站。</span><span class="sxs-lookup"><span data-stu-id="641c4-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="641c4-149">在 **[建立新的封存設定]** 的 **[封存設定]** 下拉式清單方塊中，執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="641c4-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="641c4-150">若只要啟用立即訊息 (IM) 工作階段的封存，請按一下 **[封存 IM 工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="641c4-151">若要同時啟用 IM 工作階段和會議的封存，請按一下 **[封存 IM 和 Web 會議工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="641c4-152">若要停用原則的封存，請按一下 **[停用封存]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="641c4-153">此外，在 **[建立新的封存設定]** 中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="641c4-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="641c4-154">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="641c4-155">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="641c4-156">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="641c4-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="641c4-157">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="641c4-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="641c4-158">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="641c4-159">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="641c4-160">設定集區層級的封存選項</span><span class="sxs-lookup"><span data-stu-id="641c4-160">Configure pool level archiving options</span></span>

<span data-ttu-id="641c4-161">您可以指定特定集區的封存選項。</span><span class="sxs-lookup"><span data-stu-id="641c4-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="641c4-162">集區設定會覆寫全域設定和網站設定，但僅限於集區設定中所指定的集區。</span><span class="sxs-lookup"><span data-stu-id="641c4-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="641c4-163">使用指派到 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="641c4-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="641c4-164">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="641c4-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="641c4-165">在左導覽列中 **，按一下 [\*\*\*\*監視與** 封存]，然後按一下 [封存設定]。</span><span class="sxs-lookup"><span data-stu-id="641c4-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="641c4-166">**在 [封存** 設定] 頁面上，按一下 [**新增**]，然後按一下 [**集** 區設定]。</span><span class="sxs-lookup"><span data-stu-id="641c4-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="641c4-167">在 [ **選取服務**] 中，選取要設定封存的集區。</span><span class="sxs-lookup"><span data-stu-id="641c4-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="641c4-168">在 [ **新增封存設定**] 的 [封存 **設定** ] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="641c4-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="641c4-169">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="641c4-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="641c4-170">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="641c4-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="641c4-171">**封存 IM 和 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="641c4-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="641c4-172">在 [ **新增封存設定** ] 頁面中，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="641c4-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="641c4-173">若要在封存無法使用時封鎖活動，請選取 **[封存失敗時封鎖立即訊息 (IM) 和 Web 會議工作階段]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="641c4-174">若要使用 Microsoft Exchange Server 儲存封存資料，請按一下 [ **Microsoft exchange 整合** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="641c4-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="641c4-175">若要啟用資料清除，請選取 **[啟用封存資料的清除]** 核取方塊，然後執行下列其中一項作業：</span><span class="sxs-lookup"><span data-stu-id="641c4-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="641c4-176">若要指定在特定天數後進行清除，請按一下 **[在最大持續期限 (天) 後清除匯出的封存資料和儲存的封存資料]**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="641c4-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="641c4-177">若要限制只清除已匯出的封存資料，請按一下 **[只清除匯出的封存資料]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="641c4-178">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="641c4-178">Click **Commit**.</span></span>
    

