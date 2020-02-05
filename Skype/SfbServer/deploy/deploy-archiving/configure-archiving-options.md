---
title: 設定商務用 Skype Server 的存檔選項
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: 摘要：請閱讀本主題，以瞭解如何設定商務用 Skype Server 的初始封存選項。 您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769196"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="2c5f0-104">設定商務用 Skype Server 的存檔選項</span><span class="sxs-lookup"><span data-stu-id="2c5f0-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="2c5f0-105">**摘要：** 若要瞭解如何設定商務用 Skype Server 的初始封存選項，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="2c5f0-106">您最初是在部署封存時設定封存配置，但您可以在部署之後變更、新增及刪除配置。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="2c5f0-107">若要設定初始封存配置，您可以使用商務用 Skype Server 的 [控制台] 來指定下列專案：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="2c5f0-108">部署商務用 Skype Server 時預設建立的全域層級設定</span><span class="sxs-lookup"><span data-stu-id="2c5f0-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="2c5f0-109">選擇性網站層級設定，指定如何針對特定網站執行歸檔</span><span class="sxs-lookup"><span data-stu-id="2c5f0-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="2c5f0-110">指定如何針對特定的資料庫池實施歸檔的選用池層級設定</span><span class="sxs-lookup"><span data-stu-id="2c5f0-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="2c5f0-111">您將需要設定下列選項：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="2c5f0-112">是否要啟用或停用封存</span><span class="sxs-lookup"><span data-stu-id="2c5f0-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="2c5f0-113">是否要封存 IM 會話</span><span class="sxs-lookup"><span data-stu-id="2c5f0-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="2c5f0-114">是否要封存網路會議會話</span><span class="sxs-lookup"><span data-stu-id="2c5f0-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="2c5f0-115">存檔無法使用時是否封鎖活動</span><span class="sxs-lookup"><span data-stu-id="2c5f0-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="2c5f0-116">是否要使用 Exchange 整合</span><span class="sxs-lookup"><span data-stu-id="2c5f0-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="2c5f0-117">如何設定清除及匯出資料</span><span class="sxs-lookup"><span data-stu-id="2c5f0-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="2c5f0-118">啟用封存前，您應該先指定所有適當的選項。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="2c5f0-119">如需有關如何實施封存配置的詳細資料，包括您可以指定哪些選項，以及歸檔設定的階層，請參閱[在商務用 Skype Server 中進行封存規劃](../../plan-your-deployment/archiving/archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="2c5f0-120">如需有關如何使用 [控制台] 或 [使用 Windows PowerShell] 部署之後管理設定的詳細資訊，請參閱[管理商務用 Skype Server 中](../../manage/archiving/options.md)的封存選項。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="2c5f0-121">設定全域層級存檔選項</span><span class="sxs-lookup"><span data-stu-id="2c5f0-121">Configure global level archiving options</span></span>

<span data-ttu-id="2c5f0-122">當您在拓撲中新增封存併發布拓撲時，商務用 Skype 伺服器會建立一個全域設定以供存檔。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="2c5f0-123">根據預設，全域配置中不會啟用任何存檔選項。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="2c5f0-124">全域設定會控制為整個部署啟用哪些選項，除非您設定網站或池設定，而這會覆寫全域配置。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="2c5f0-125">若要在全域層級設定封存選項：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="2c5f0-126">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c5f0-127">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2c5f0-128">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2c5f0-129">在 [**存檔**設定] 頁面上，按一下 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2c5f0-130">在 [**編輯封存設定-全域**] 中的 [**存檔設定**] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="2c5f0-131">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="2c5f0-132">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="2c5f0-133">**封存 IM 與 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="2c5f0-134">此外，在 [**編輯封存設定-全域**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="2c5f0-135">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-136">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-137">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2c5f0-138">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2c5f0-139">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="2c5f0-140">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="2c5f0-141">設定網站層級封存選項</span><span class="sxs-lookup"><span data-stu-id="2c5f0-141">Configure site level archiving options</span></span>

<span data-ttu-id="2c5f0-142">您可以指定特定網站的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="2c5f0-143">網站設定會覆寫全域配置，但僅適用于網站設定中指定的網站。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="2c5f0-144">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c5f0-145">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2c5f0-146">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2c5f0-147">在 [**存檔**設定] 頁面上，按一下 [**新增**]，然後按一下 [**網站**設定]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="2c5f0-148">在 [**選取網站**] 中，選取要設定為要存檔的網站。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="2c5f0-149">在 [**新增封存設定**] 的 [**存檔設定**] 下拉式清單方塊中，執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="2c5f0-150">若要只針對立即訊息（IM）會話啟用封存，請按一下 [封存**IM 會話**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="2c5f0-151">若要在 IM 會話與會議中啟用封存功能，請按一下 [封存**im 和網路會議會話**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="2c5f0-152">若要停用原則封存，請按一下 [**停**用封存]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="2c5f0-153">此外，在 [新增封存]**設定**中，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="2c5f0-154">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-155">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-156">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2c5f0-157">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2c5f0-158">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="2c5f0-159">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="2c5f0-160">設定池層級的存檔選項</span><span class="sxs-lookup"><span data-stu-id="2c5f0-160">Configure pool level archiving options</span></span>

<span data-ttu-id="2c5f0-161">您可以指定特定池的存檔選項。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="2c5f0-162">池設定會覆寫全域配置和網站設定，但僅適用于在池設定中指定的池。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="2c5f0-163">從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2c5f0-164">開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2c5f0-165">在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**配置**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2c5f0-166">**在 [封存**設定] 頁面上，按一下 [**新增**]，然後按一下 [**池配置**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="2c5f0-167">在 [**選取服務**] 中，選取要設定為要存檔的池。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="2c5f0-168">在 [新增封存]**設定**的 [封存**設定**] 下拉式清單中，選取下列其中一個封存選項：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="2c5f0-169">**停用封存**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="2c5f0-170">**封存 IM 工作階段**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="2c5f0-171">**封存 IM 與 Web 會議工作階段**</span><span class="sxs-lookup"><span data-stu-id="2c5f0-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="2c5f0-172">此外，在 [**新增封存設定**] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="2c5f0-173">若要在封存無法使用時封鎖活動，請選取 [**如果封存失敗，封鎖立即訊息（IM）或 web 會議會話**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-174">若要使用 Microsoft Exchange Server 儲存存檔資料，請按一下 [ **Microsoft exchange 整合**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2c5f0-175">若要啟用資料清除，請選取 [**啟用 [清除封存資料**] 核取方塊，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2c5f0-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2c5f0-176">若要指定在特定天數後進行清除，請按一下 **[清除匯出的存檔資料]，並儲存在最長持續時間（天數）之後的儲存封存資料**，然後指定天數。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2c5f0-177">若要限制清除以封存已匯出的資料，請按一下 [**僅清除匯出的存檔資料**]。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="2c5f0-178">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2c5f0-178">Click **Commit**.</span></span>
    

