---
title: 移轉回應群組
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 將使用者移至商務用 Skype Server 2019 集區之後，您可以遷移回應群組。 遷移回應群組包括從舊版部署到商務用 Skype Server 2019 集區，將代理群組、佇列、工作流程、音訊檔及移動回應群組連絡人物件。 遷移舊版回應群組之後，回應群組的呼叫會由商務用 Skype Server 2019 集區中的回應群組應用程式來處理。 舊版集區不會再處理對回應群組的通話。
ms.openlocfilehash: bf4087440fb112cb1af906e1a0915531eea08456
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113269"
---
# <a name="migrate-response-groups"></a><span data-ttu-id="292e6-106">移轉回應群組</span><span class="sxs-lookup"><span data-stu-id="292e6-106">Migrate response groups</span></span>

<span data-ttu-id="292e6-107">將使用者移至商務用 Skype Server 2019 集區之後，您可以遷移回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-107">After your users are moved to Skype for Business Server 2019 pools, you can migrate your response groups.</span></span> <span data-ttu-id="292e6-108">遷移回應群組包括從舊版部署到商務用 Skype Server 2019 集區，將代理群組、佇列、工作流程、音訊檔及移動回應群組連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="292e6-108">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="292e6-109">遷移舊版回應群組之後，回應群組的呼叫會由商務用 Skype Server 2019 集區中的回應群組應用程式來處理。</span><span class="sxs-lookup"><span data-stu-id="292e6-109">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="292e6-110">舊版集區不會再處理對回應群組的通話。</span><span class="sxs-lookup"><span data-stu-id="292e6-110">Calls to response groups are no longer handled by the legacy pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="292e6-111">雖然您可以在將所有使用者移至商務用 Skype Server 2019 集區之前遷移回應群組，但建議您先移動所有使用者。</span><span class="sxs-lookup"><span data-stu-id="292e6-111">Although you can migrate response groups before you move all users to the Skype for Business Server 2019 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="292e6-112">特別是，回應群組代理程式的使用者在移至商務用 Skype Server 2019 集區之前，不會有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="292e6-112">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Skype for Business Server 2019 pool.</span></span> 
  
<span data-ttu-id="292e6-113">在遷移回應群組之前，您必須已部署包含回應群組應用程式的商務用 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="292e6-113">Before you migrate response groups, you must have deployed a Skype for Business Server 2019 pool that includes the Response Group application.</span></span> <span data-ttu-id="292e6-114">當您部署企業語音時，預設會安裝及啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="292e6-114">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="292e6-115">您可以執行 **Get-CsService ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="292e6-115">You can ensure that the Response Group application is installed by running the **Get-CsService -ApplicationServer** cmdlet.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="292e6-116">您可以在遷移舊版回應群組之前，先在商務用 Skype Server 2019 集區中建立新的商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-116">You can create new Skype for Business Server 2019 response groups in the Skype for Business Server 2019 pool before you migrate your legacy response groups.</span></span> 
  
<span data-ttu-id="292e6-117">若要將回應群組從舊版集區遷移至商務用 Skype Server 2019，您可以執行 **Move-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="292e6-117">To migrate response groups from a legacy pool to the Skype for Business Server 2019, you run the **Move-CsRgsConfiguration** cmdlet.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="292e6-118">回應群組遷移 Cmdlet 會移動整個集區的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="292e6-118">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="292e6-119">您無法選取要移轉的特定群組、佇列或工作流程。</span><span class="sxs-lookup"><span data-stu-id="292e6-119">You cannot select specific groups, queues, or workflows to migrate.</span></span> 
  
<span data-ttu-id="292e6-120">遷移回應群組之後，您必須使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面 Cmdlet，確認所有代理人群組、佇列和工作流程都已順利移動。</span><span class="sxs-lookup"><span data-stu-id="292e6-120">After you migrate the response groups, you need to use Skype for Business Server Control Panel or Skype for Business Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span> 
  
<span data-ttu-id="292e6-121">當您遷移回應群組時，不會移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-121">When you migrate response groups, the legacy response groups are not removed.</span></span> <span data-ttu-id="292e6-122">當您使用商務用 Skype Server 控制台或商務用 skype Server 管理命令介面來管理遷移之後的回應群組時，您可以看到舊版回應群組和商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-122">When you manage response groups after migration by using either Skype for Business Server Control Panel or Skype for Business Server Management Shell, you can see both the legacy response groups and the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="292e6-123">您應該只將更新套用至商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-123">You should apply updates only to the Skype for Business Server 2019 response groups.</span></span> <span data-ttu-id="292e6-124">舊版回應群組只會保留以供復原之用。</span><span class="sxs-lookup"><span data-stu-id="292e6-124">The legacy response groups are retained only for rollback purposes.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="292e6-125">完成遷移並建立新的回應群組之後，商務用 Skype Server 控制台和商務用 skype server 管理命令介面會顯示每個回應群組的舊版和商務用 Skype Server 2019 版本。</span><span class="sxs-lookup"><span data-stu-id="292e6-125">After the migration has been completed and the new response groups have been created, the Skype for Business Server Control Panel and the Skype for Business Server Management Shell will display the legacy and Skype for Business Server 2019 versions of each response group.</span></span> <span data-ttu-id="292e6-126">請勿使用商務用 Skype Server 控制台或商務用 Skype Server 管理命令介面來移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-126">Do not use Skype for Business Server Control Panel or Skype for Business Server Management Shell to remove the legacy response groups.</span></span> <span data-ttu-id="292e6-127">如果您確實移除其中一個，則在遷移期間所建立的對應回應群組將停止運作。</span><span class="sxs-lookup"><span data-stu-id="292e6-127">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="292e6-128">當您解除委任舊版集區時，將會移除舊版回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-128">The legacy response groups will be removed when you decommission the legacy pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="292e6-129">建議集區解除委任之後，再移除先前部署的各項資料。</span><span class="sxs-lookup"><span data-stu-id="292e6-129">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="292e6-130">此外，強烈建議移轉後立即匯出回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-130">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="292e6-131">如果舊版回應群組應該被移除，您可以從備份還原回應群組，以取得商務用 Skype Server 2019 回應群組。</span><span class="sxs-lookup"><span data-stu-id="292e6-131">If a legacy response group should get removed, you can then restore your response groups from the backup to get Skype for Business Server 2019 response groups running again.</span></span> 
  
<span data-ttu-id="292e6-132">商務用 Skype Server 2019 引進新的回應群組功能，稱為 **工作流程類型**。</span><span class="sxs-lookup"><span data-stu-id="292e6-132">Skype for Business Server 2019 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="292e6-133">**[工作流程類型]** 可以是 **[已管理]** 或 **[未管理]**。</span><span class="sxs-lookup"><span data-stu-id="292e6-133">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="292e6-134">移轉後的所有回應群組 **[工作流程類型]** 都會設為 **[未管理]**，並附有一份空白的管理員清單。</span><span class="sxs-lookup"><span data-stu-id="292e6-134">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span> 
  
<span data-ttu-id="292e6-135">執行 **Move-CsRgsConfiguration** Cmdlet 時，代理人群組、佇列、工作流程及音訊檔案都會保留在舊版集區供復原作業使用。</span><span class="sxs-lookup"><span data-stu-id="292e6-135">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="292e6-136">如果確實有必要復原舊版集區，必須執行 **Move-CsApplicationEndpoint** Cmdlet 才能將連絡人物件移動到舊版集區。</span><span class="sxs-lookup"><span data-stu-id="292e6-136">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span> 
  
<span data-ttu-id="292e6-137">下列遷移回應群組設定的程式假設您的舊版集區與商務用 Skype Server 2019 集區之間具有一對一的關聯性。</span><span class="sxs-lookup"><span data-stu-id="292e6-137">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Skype for Business Server 2019 pools.</span></span> <span data-ttu-id="292e6-138">如果您想要在遷移和部署期間整合或分割集區，您必須規劃哪些舊版集區對應至哪一個 Skype Server 2019 集區。</span><span class="sxs-lookup"><span data-stu-id="292e6-138">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Skype for Business Server 2019 pool.</span></span>
  
## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="292e6-139">遷移回應群組設定</span><span class="sxs-lookup"><span data-stu-id="292e6-139">To migrate Response Group configurations</span></span>

1. <span data-ttu-id="292e6-140">使用 RTCUniversalServerAdmins 群組的成員帳戶，或具有等同於系統管理員權限的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="292e6-140">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>
    
2. <span data-ttu-id="292e6-141">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="292e6-141">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="292e6-142">執行：</span><span class="sxs-lookup"><span data-stu-id="292e6-142">Run:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
   ```

    <span data-ttu-id="292e6-143">例如：</span><span class="sxs-lookup"><span data-stu-id="292e6-143">For example:</span></span>
    
   ```PowerShell
   Move-CsRgsConfiguration -Source skype-old.contoso.net -Destination skype-new.contoso.net
   ```

4. <span data-ttu-id="292e6-144">將回應群組和代理程式遷移至商務用 Skype Server 2019 集區之後，代理人用來登入和登出的 URL 就是商務用 Skype Server 2019 URL，而且可從 [ **工具** ] 功能表中取得。</span><span class="sxs-lookup"><span data-stu-id="292e6-144">After you migrate response groups and agents to the Skype for Business Server 2019 pool, the URL that agents use to sign in and sign out is a Skype for Business Server 2019 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="292e6-145">請提醒代理人將書籤等任何參照更新到新的 URL。</span><span class="sxs-lookup"><span data-stu-id="292e6-145">Remind agents to update any references, such as bookmarks, to the new URL.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="292e6-146">使用商務用 Skype Server 控制台驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="292e6-146">To verify Response Group migration by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="292e6-147">使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="292e6-147">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="292e6-148">開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="292e6-148">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="292e6-149">如需您可以用來啟動商務用 Skype Server 控制台之不同方法的詳細資訊，請參閱 [開放式商務用 Skype server 2019 系統管理工具](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。</span><span class="sxs-lookup"><span data-stu-id="292e6-149">For details about the different methods you can use to start Skype for Business Server Control Panel, see [Open Skype for Business Server 2019 administrative tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools).</span></span> 
    <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
3. <span data-ttu-id="292e6-150">在左導覽列中，按一下 **[回應群組]**。</span><span class="sxs-lookup"><span data-stu-id="292e6-150">In the left navigation pane, click **Response Groups**.</span></span>
    
4. <span data-ttu-id="292e6-151">在 [ **工作流程** ] 索引標籤上，確認您的舊版環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="292e6-151">On the **Workflow** tab, verify that all the workflows in your legacy environment are included in the list.</span></span> 
    
5. <span data-ttu-id="292e6-152">按一下 [ **佇列** ] 索引標籤，確認清單中包含舊版環境中的所有佇列。</span><span class="sxs-lookup"><span data-stu-id="292e6-152">Click the **Queue** tab, and verify that all the queues in your legacy environment are included in the list.</span></span> 
    
6. <span data-ttu-id="292e6-153">按一下 [ **群組** ] 索引標籤，並確認您的舊版環境中的所有代理程式群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="292e6-153">Click the **Group** tab, and verify that all the agent groups in your legacy environment are included in the list.</span></span> 
    
## <a name="to-verify-response-group-migration-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="292e6-154">使用商務用 Skype Server 管理命令介面來驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="292e6-154">To verify Response Group migration by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="292e6-155">使用 RTCUniversalReadOnlyAdmins 群組的成員帳戶，或至少必須是 CsViewOnlyAdministrator 角色之成員的帳戶登入電腦。</span><span class="sxs-lookup"><span data-stu-id="292e6-155">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>
    
2. <span data-ttu-id="292e6-156">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft 商務用 skype server 2019**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="292e6-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
    <span data-ttu-id="292e6-157">如需下列 Cmdlet 的詳細資料，請執行：</span><span class="sxs-lookup"><span data-stu-id="292e6-157">For details about the following cmdlets, run:</span></span>
    
   ```PowerShell
   Get-Help <cmdlet name> -Detailed
   ```

3. <span data-ttu-id="292e6-158">執行：</span><span class="sxs-lookup"><span data-stu-id="292e6-158">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsAgentGroup
   ```

4. <span data-ttu-id="292e6-159">確認您的舊版環境中的所有代理程式群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="292e6-159">Verify that all the agent groups in your legacy environment are included in the list.</span></span>
    
5. <span data-ttu-id="292e6-160">執行：</span><span class="sxs-lookup"><span data-stu-id="292e6-160">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsQueue
   ```

6. <span data-ttu-id="292e6-161">確認您的舊版環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="292e6-161">Verify that all the queues in your legacy environment are included in the list.</span></span>
    
7. <span data-ttu-id="292e6-162">執行：</span><span class="sxs-lookup"><span data-stu-id="292e6-162">Run:</span></span>
    
   ```PowerShell
   Get-CsRgsWorkflow
   ```

8. <span data-ttu-id="292e6-163">確認您的舊版環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="292e6-163">Verify that all the workflows in your legacy environment are included in the list.</span></span>
