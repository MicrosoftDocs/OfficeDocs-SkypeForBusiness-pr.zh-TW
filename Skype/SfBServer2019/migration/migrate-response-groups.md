---
title: 遷移回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 當您的使用者移至商務用 Skype Server 2019 池之後, 您就可以遷移您的回應群組。 遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案, 以及將回應群組連絡人物件從舊版部署移至商務用 Skype Server 2019 池。 在您遷移舊版回應群組之後, 回應群組的呼叫會由商務用 Skype Server 2019 池中的回應群組應用程式來處理。 舊版池已不再處理回應群組的呼叫。
ms.openlocfilehash: cba50526748ca15c04513013e484b0e279410c1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193066"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="b5fc3-106">遷移回應群組</span><span class="sxs-lookup"><span data-stu-id="b5fc3-106">Migrate response groups</span></span>

<span data-ttu-id="b5fc3-107">當您的使用者移至商務用 Skype Server 2019 池之後, 您就可以遷移您的回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="b5fc3-108">遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案, 以及將回應群組連絡人物件從舊版部署移至商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b5fc3-109">在您遷移舊版回應群組之後, 回應群組的呼叫會由商務用 Skype Server 2019 池中的回應群組應用程式來處理。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b5fc3-110">舊版池已不再處理回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b5fc3-111">雖然您可以在將所有使用者移至商務用 Skype Server 2019 池之前先遷移回應群組, 但我們建議您先移動所有使用者。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="b5fc3-112">特別是, 回應群組代理的使用者在移至商務用 Skype Server 2019 池之前, 將不會有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="b5fc3-113">在您遷移回應群組之前, 您必須已部署包含回應群組應用程式的商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="b5fc3-114">當您部署企業語音時, 系統會預設安裝並啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="b5fc3-115">您可以執行**CsService-ApplicationServer** Cmdlet, 以確保已安裝回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b5fc3-116">在您遷移舊版回應群組之前, 您可以在商務用 Skype Server 2019 池中建立新的商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="b5fc3-117">若要將回應群組從舊版池遷移到商務用 Skype Server 2019, 您可以執行**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5fc3-118">回應群組遷移 Cmdlet 會移動整個池的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="b5fc3-119">您無法選取要遷移的特定群組、佇列或工作流程。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="b5fc3-120">在您遷移回應群組之後, 您必須使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面 Cmdlet], 確認所有代理群組、佇列和工作流程已順利移動。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="b5fc3-121">當您遷移回應群組時, 不會移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="b5fc3-122">如果您是使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面, 在遷移之後管理回應群組, 您可以看到舊版回應群組和商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b5fc3-123">您只能將更新套用到商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="b5fc3-124">舊版回應群組只會保留供回滾之用。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="b5fc3-125">完成遷移並建立新的回應群組之後, 商務用 Skype Server 的 [控制台] 和 [商務用 skype 伺服器] 管理命令介面會顯示舊版及商務用 Skype server 的2019版本。群組.</span><span class="sxs-lookup"><span data-stu-id="b5fc3-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="b5fc3-126">請勿使用商務用 Skype Server 的 [控制台] 或 [商務用 Skype 伺服器管理命令介面] 來移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="b5fc3-127">如果您移除其中一個專案, 則在遷移期間建立的對應回應群組就會停止運作。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="b5fc3-128">當您解除授權舊版池時, 會移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b5fc3-129">我們建議您不要從先前的部署移除任何資料, 除非您解除該池。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="b5fc3-130">此外, 我們強烈建議您在遷移後立即匯出回應群組。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="b5fc3-131">如果傳統回應群組應該被移除, 您可以從備份還原回應群組, 以取得商務用 Skype Server 2019 回應群組再次執行。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="b5fc3-132">商務用 Skype Server 2019 引入了稱為「**工作流程類型**」的新回應群組功能。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="b5fc3-133">**工作流程類型**可以是**託管**或**非託管**。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="b5fc3-134">[所有回應群組] 都將 [**工作流程類型**] 設定為 [**非託管**], 並使用空的管理員清單進行遷移</span><span class="sxs-lookup"><span data-stu-id="b5fc3-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="b5fc3-135">當您執行**CsRgsConfiguration** Cmdlet 時, 系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案, 以供回滾之用。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="b5fc3-136">不過, 如果您需要回滾到舊版池, 您必須執行**CsApplicationEndpoint** Cmdlet, 以將連絡人物件移回舊版資源區。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="b5fc3-137">下列程式適用于遷移回應群組設定, 假設您的舊版池與商務用 Skype Server 2019 池之間有一對一關聯性。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="b5fc3-138">如果您打算在您的遷移和部署期間合併或分割池, 您需要規劃哪些舊版池會對應到哪個商務用 Skype Server 2019 池。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="b5fc3-139">若要遷移回應群組設定</span><span class="sxs-lookup"><span data-stu-id="b5fc3-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="b5fc3-140">以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦, 或擁有同等的系統管理員許可權和許可權。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="b5fc3-141">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="b5fc3-142">用盡</span><span class="sxs-lookup"><span data-stu-id="b5fc3-142">Run:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="b5fc3-143">例如：</span><span class="sxs-lookup"><span data-stu-id="b5fc3-143">For example:</span></span>
    
   ```
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="b5fc3-144">在您將回應群組和代理程式遷移到商務用 Skype Server 2019 文件庫之後, 代理程式用來登入和登出的 URL 就是商務用 Skype Server 2019 URL, 且可從 [**工具**] 功能表取得。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="b5fc3-145">提醒代理程式將任何參照 (例如書簽) 更新為新的 URL。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b5fc3-146">使用商務用 Skype Server [控制台] 驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="b5fc3-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b5fc3-147">使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦, 或最少是 CsViewOnlyAdministrator 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b5fc3-148">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="b5fc3-149">如需可用於啟動商務用 Skype Server 控制台的不同方法的詳細資訊, 請參閱[開啟商務用 Skype server 2019 系統管理工具](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx)。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](https://technet.microsoft.com/en-us/library/gg195741(v=ocs.15).aspx).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="b5fc3-150">在左側功能窗格中, 按一下 [**回應群組**]。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="b5fc3-151">在 [**工作流程**] 索引標籤上, 確認您的舊版環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="b5fc3-152">按一下 [**佇列**] 索引標籤, 並確認您的舊版環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="b5fc3-153">按一下 [**群組**] 索引標籤, 並確認您的舊版環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b5fc3-154">使用商務用 Skype Server Management Shell 驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="b5fc3-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b5fc3-155">使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦, 或最少是 CsViewOnlyAdministrator 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="b5fc3-156">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [ **Microsoft 商務用 skype server 2019**], 然後按一下 [**商務用 skype server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="b5fc3-157">如需有關下列 Cmdlet 的詳細資訊, 請執行:</span><span class="sxs-lookup"><span data-stu-id="b5fc3-157">For details about the following cmdlets, run:</span></span>
    
   ```
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="b5fc3-158">用盡</span><span class="sxs-lookup"><span data-stu-id="b5fc3-158">Run:</span></span>
    
   ```
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="b5fc3-159">確認您舊版環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="b5fc3-160">用盡</span><span class="sxs-lookup"><span data-stu-id="b5fc3-160">Run:</span></span>
    
   ```
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="b5fc3-161">確認您的舊版環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="b5fc3-162">用盡</span><span class="sxs-lookup"><span data-stu-id="b5fc3-162">Run:</span></span>
    
   ```
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="b5fc3-163">確認您的舊版環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="b5fc3-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
    

