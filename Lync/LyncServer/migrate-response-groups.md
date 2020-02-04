---
title: 移轉回應群組
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate response groups
ms:assetid: 43741ae7-c871-4573-b660-f2f5febc0856
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204854(v=OCS.15)
ms:contentKeyID: 48184020
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23ef26b86b1de3fa7f9656cdb2ea82bb7a220948
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-response-groups"></a><span data-ttu-id="0e718-102">移轉回應群組</span><span class="sxs-lookup"><span data-stu-id="0e718-102">Migrate response groups</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e718-103">_**主題上次修改日期：** 2013-09-23_</span><span class="sxs-lookup"><span data-stu-id="0e718-103">_**Topic Last Modified:** 2013-09-23_</span></span>

<span data-ttu-id="0e718-104">將使用者移至 Lync Server 2013 池之後，您就可以遷移回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-104">After your users are moved to Lync Server 2013 pools, you can migrate your response groups.</span></span> <span data-ttu-id="0e718-105">遷移回應群組包括複製代理群組、佇列、工作流程、音訊檔案，以及將回應群組連絡人物件從舊版部署移至 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="0e718-105">Migrating response groups includes copying agent groups, queues, workflows, audio files, and moving Response Group contact objects from the legacy deployment to the Lync Server 2013 pool.</span></span> <span data-ttu-id="0e718-106">在您遷移舊版回應群組之後，就會透過 Lync Server 2013 池中的回應群組應用程式來處理回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e718-106">After you migrate your legacy response groups, calls to the response groups are handled by the Response Group application in the Lync Server 2013 pool.</span></span> <span data-ttu-id="0e718-107">舊版池已不再處理回應群組的呼叫。</span><span class="sxs-lookup"><span data-stu-id="0e718-107">Calls to response groups are no longer handled by the legacy pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e718-108">雖然您可以在將所有使用者移至 Lync Server 2013 池之前先遷移回應群組，但我們建議您先移動所有使用者。</span><span class="sxs-lookup"><span data-stu-id="0e718-108">Although you can migrate response groups before you move all users to the Lync Server 2013 pool, we recommend that you move all users first.</span></span> <span data-ttu-id="0e718-109">特別是，回應群組代理的使用者在移至 Lync Server 2013 池之前，將不會有新功能的完整功能。</span><span class="sxs-lookup"><span data-stu-id="0e718-109">In particular, users who are response group agents will not have full functionality of new features until they are moved to the Lync Server 2013 pool.</span></span>



</div>

<span data-ttu-id="0e718-110">在您遷移回應群組之前，您必須先部署包含回應群組應用程式的 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="0e718-110">Before you migrate response groups, you must have deployed a Lync Server 2013 pool that includes the Response Group application.</span></span> <span data-ttu-id="0e718-111">當您部署企業語音時，系統會預設安裝並啟用回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="0e718-111">The Response Group application is installed and activated by default when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0e718-112">您可以執行**CsService – ApplicationServer** Cmdlet，以確保已安裝回應群組應用程式。</span><span class="sxs-lookup"><span data-stu-id="0e718-112">You can ensure that the Response Group application is installed by running the **Get-CsService –ApplicationServer** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e718-113">在您遷移舊版回應群組之前，您可以在 Lync Server 2013 池中建立新的 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-113">You can create new Lync Server 2013 response groups in the Lync Server 2013 pool before you migrate your legacy response groups.</span></span>



</div>

<span data-ttu-id="0e718-114">若要將回應群組從舊版池遷移至 Lync Server 2013，請執行**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0e718-114">To migrate response groups from a legacy pool to the Lync Server 2013, you run the **Move-CsRgsConfiguration** cmdlet.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e718-115">回應群組遷移 Cmdlet 會移動整個池的回應群組設定。</span><span class="sxs-lookup"><span data-stu-id="0e718-115">The Response Group migration cmdlet moves the Response Group configuration for the entire pool.</span></span> <span data-ttu-id="0e718-116">您無法選取要遷移的特定群組、佇列或工作流程。</span><span class="sxs-lookup"><span data-stu-id="0e718-116">You cannot select specific groups, queues, or workflows to migrate.</span></span>



</div>

<span data-ttu-id="0e718-117">在您遷移回應群組之後，您必須使用 Lync Server 的 [控制台] 或 [Lync Server 管理命令介面] Cmdlet，確認所有的代理程式群組、佇列和工作流程已順利移動。</span><span class="sxs-lookup"><span data-stu-id="0e718-117">After you migrate the response groups, you need to use Lync Server Control Panel or Lync Server Management Shell cmdlets to verify that all agent groups, queues, and workflows moved successfully.</span></span>

<span data-ttu-id="0e718-118">當您遷移回應群組時，不會移除 Lync Server 2010 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-118">When you migrate response groups, the Lync Server 2010 response groups are not removed.</span></span> <span data-ttu-id="0e718-119">當您使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 遷移之後管理回應群組之後，您可以看到 Lync Server 2010 回應群組和 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-119">When you manage response groups after migration by using either Lync Server Control Panel or Lync Server Management Shell, you can see both the Lync Server 2010 response groups and the Lync Server 2013 response groups.</span></span> <span data-ttu-id="0e718-120">您應該只將更新套用至 Lync Server 2013 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-120">You should apply updates only to the Lync Server 2013 response groups.</span></span> <span data-ttu-id="0e718-121">Lync Server 2010 回應群組只會保留以供回滾之用。</span><span class="sxs-lookup"><span data-stu-id="0e718-121">The Lync Server 2010 response groups are retained only for rollback purposes.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0e718-122">完成遷移並建立新的回應群組之後，Lync server 的 [控制台] 和 [Lync Server 管理命令介面] 會顯示每個回應群組的 Lync Server 2010 和 Lync Server 2013 版本。</span><span class="sxs-lookup"><span data-stu-id="0e718-122">After the migration has been completed and the new response groups have been created, the Lync Server Control Panel and the Lync Server Management Shell will display the Lync Server 2010 and Lync Server 2013 versions of each response group.</span></span> <span data-ttu-id="0e718-123">請勿使用 Lync Server [控制台] 或 [Lync Server 管理命令介面] 來移除 Lync Server 2010 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-123">Do not use Lync Server Control Panel or Lync Server Management Shell to remove the Lync Server 2010 response groups.</span></span> <span data-ttu-id="0e718-124">如果您移除其中一個專案，則在遷移期間建立的對應回應群組就會停止運作。</span><span class="sxs-lookup"><span data-stu-id="0e718-124">If you do remove one, the corresponding response group that was created during migration will stop working.</span></span> <span data-ttu-id="0e718-125">當您解除 Lync Server 2010 池的授權時，將會移除 Lync Server 2010 回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-125">The Lync Server 2010 response groups will be removed when you decommission the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0e718-126">我們建議您不要從先前的部署移除任何資料，除非您解除該池。</span><span class="sxs-lookup"><span data-stu-id="0e718-126">We recommend that you do not remove any data from your previous deployment until you decommission the pool.</span></span> <span data-ttu-id="0e718-127">此外，我們強烈建議您在遷移後立即匯出回應群組。</span><span class="sxs-lookup"><span data-stu-id="0e718-127">In addition, we strongly recommend that you export response groups immediately after you migrate.</span></span> <span data-ttu-id="0e718-128">如果 Lync Server 2010 回應群組應該被移除，您可以從備份還原回應群組，讓 Lync Server 2013 回應群組再次執行。</span><span class="sxs-lookup"><span data-stu-id="0e718-128">If a Lync Server 2010 response group should get removed, you can then restore your response groups from the backup to get Lync Server 2013 response groups running again.</span></span>



</div>

<span data-ttu-id="0e718-129">Lync Server 2013 引入了稱為「**工作流程類型**」的新回應群組功能。</span><span class="sxs-lookup"><span data-stu-id="0e718-129">Lync Server 2013 introduces a new Response Group feature called **Workflow Type**.</span></span> <span data-ttu-id="0e718-130">**工作流程類型**可以是**託管**或**非託管**。</span><span class="sxs-lookup"><span data-stu-id="0e718-130">**Workflow Type** can be **Managed** or **Unmanaged**.</span></span> <span data-ttu-id="0e718-131">[所有回應群組] 都將 [**工作流程類型**] 設定為 [**非託管**]，並使用空的管理員清單進行遷移</span><span class="sxs-lookup"><span data-stu-id="0e718-131">All response groups are migrated with **Workflow Type** set to **Unmanaged** and with an empty Manager list.</span></span>

<span data-ttu-id="0e718-132">當您執行**CsRgsConfiguration** Cmdlet 時，系統會在舊版池中保留代理群組、佇列、工作流程和音訊檔案，以供回滾之用。</span><span class="sxs-lookup"><span data-stu-id="0e718-132">When you run the **Move-CsRgsConfiguration** cmdlet, the agent groups, queues, workflows, and audio files remain in the legacy pool for rollback purposes.</span></span> <span data-ttu-id="0e718-133">不過，如果您需要回滾到舊版池，您必須執行**CsApplicationEndpoint** Cmdlet，以將連絡人物件移回舊版資源區。</span><span class="sxs-lookup"><span data-stu-id="0e718-133">If you do need to roll back to the legacy pool, however, you need to run the **Move-CsApplicationEndpoint** cmdlet to move contact objects back to the legacy pool.</span></span>

<span data-ttu-id="0e718-134">下列程式適用于遷移回應群組設定的程式，假設您的舊版池與 Lync Server 2013 池之間有一對一關聯性。</span><span class="sxs-lookup"><span data-stu-id="0e718-134">The following procedure for migrating Response Group configurations assumes that you have a one-to-one relationship between your legacy pools and the Lync Server 2013 pools.</span></span> <span data-ttu-id="0e718-135">如果您打算在您的遷移和部署期間合併或分割池，您需要規劃哪些舊版池會對應到哪個 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="0e718-135">If you plan to consolidate or split up pools during your migration and deployment, you need to plan which legacy pool maps to which Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-response-group-configurations"></a><span data-ttu-id="0e718-136">若要遷移回應群組設定</span><span class="sxs-lookup"><span data-stu-id="0e718-136">To migrate Response Group configurations</span></span>

1.  <span data-ttu-id="0e718-137">以 RTCUniversalServerAdmins 群組成員的帳戶登入電腦，或擁有同等的系統管理員許可權和許可權。</span><span class="sxs-lookup"><span data-stu-id="0e718-137">Log on to the computer with an account that is a member of the RTCUniversalServerAdmins group or has equivalent administrator rights and permissions.</span></span>

2.  <span data-ttu-id="0e718-138">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="0e718-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0e718-139">用盡</span><span class="sxs-lookup"><span data-stu-id="0e718-139">Run:</span></span>
    
        Move-CsRgsConfiguration -Source <source pool FQDN> -Destination <destination pool FQDN>
    
    <span data-ttu-id="0e718-140">例如：</span><span class="sxs-lookup"><span data-stu-id="0e718-140">For example:</span></span>
    
        Move-CsRgsConfiguration -Source lync-old.contoso.net -Destination lync-new.contoso.net

4.  <span data-ttu-id="0e718-141">在您將回應群組和代理程式遷移至 Lync Server 2013 文件庫之後，代理程式用來登入和登出的 URL 就是 Lync Server 2013 URL，且可從 [**工具**] 功能表取得。</span><span class="sxs-lookup"><span data-stu-id="0e718-141">After you migrate response groups and agents to the Lync Server 2013 pool, the URL that agents use to sign in and sign out is a Lync Server 2013 URL and is available from the **Tools** menu.</span></span> <span data-ttu-id="0e718-142">提醒代理程式將任何參照（例如書簽）更新為新的 URL。</span><span class="sxs-lookup"><span data-stu-id="0e718-142">Remind agents to update any references, such as bookmarks, to the new URL.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-control-panel"></a><span data-ttu-id="0e718-143">使用 Lync Server [控制台] 驗證回應群組的遷移</span><span class="sxs-lookup"><span data-stu-id="0e718-143">To verify Response Group migration by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0e718-144">使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦，或最少是 CsViewOnlyAdministrator 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="0e718-144">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="0e718-145">開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="0e718-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0e718-146">如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="0e718-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0e718-147">在左側功能窗格中，按一下 [**回應群組**]。</span><span class="sxs-lookup"><span data-stu-id="0e718-147">In the left navigation pane, click **Response Groups**.</span></span>

4.  <span data-ttu-id="0e718-148">在 [**工作流程**] 索引標籤上，確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-148">On the **Workflow** tab, verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="0e718-149">按一下 [**佇列**] 索引標籤，並確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-149">Click the **Queue** tab, and verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

6.  <span data-ttu-id="0e718-150">按一下 [**群組**] 索引標籤，並確認您的 Lync Server 2010 環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-150">Click the **Group** tab, and verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

</div>

<div>

## <a name="to-verify-response-group-migration-by-using-lync-server-management-shell"></a><span data-ttu-id="0e718-151">使用 Lync Server 管理命令介面驗證回應群組遷移</span><span class="sxs-lookup"><span data-stu-id="0e718-151">To verify Response Group migration by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="0e718-152">使用屬於 RTCUniversalReadOnlyAdmins 群組成員的帳戶登入電腦，或最少是 CsViewOnlyAdministrator 角色的成員。</span><span class="sxs-lookup"><span data-stu-id="0e718-152">Log on to the computer with an account that is a member of RTCUniversalReadOnlyAdmins group or is minimally a member of the CsViewOnlyAdministrator role.</span></span>

2.  <span data-ttu-id="0e718-153">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="0e718-153">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>
    
    <span data-ttu-id="0e718-154">如需有關下列 Cmdlet 的詳細資訊，請執行：</span><span class="sxs-lookup"><span data-stu-id="0e718-154">For details about the following cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed

3.  <span data-ttu-id="0e718-155">用盡</span><span class="sxs-lookup"><span data-stu-id="0e718-155">Run:</span></span>
    
        Get-CsRgsAgentGroup

4.  <span data-ttu-id="0e718-156">確認您的 Lync Server 2010 環境中的所有代理群組都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-156">Verify that all the agent groups in your Lync Server 2010 environment are included in the list.</span></span>

5.  <span data-ttu-id="0e718-157">用盡</span><span class="sxs-lookup"><span data-stu-id="0e718-157">Run:</span></span>
    
        Get-CsRgsQueue

6.  <span data-ttu-id="0e718-158">確認您的 Lync Server 2010 環境中的所有佇列都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-158">Verify that all the queues in your Lync Server 2010 environment are included in the list.</span></span>

7.  <span data-ttu-id="0e718-159">用盡</span><span class="sxs-lookup"><span data-stu-id="0e718-159">Run:</span></span>
    
        Get-CsRgsWorkflow

8.  <span data-ttu-id="0e718-160">確認您的 Lync Server 2010 環境中的所有工作流程都包含在清單中。</span><span class="sxs-lookup"><span data-stu-id="0e718-160">Verify that all the workflows in your Lync Server 2010 environment are included in the list.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

