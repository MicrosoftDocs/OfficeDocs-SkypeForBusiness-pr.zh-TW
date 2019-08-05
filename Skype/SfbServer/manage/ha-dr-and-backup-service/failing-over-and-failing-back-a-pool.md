---
title: 容錯移轉並重新失敗
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: .
ms.openlocfilehash: 2848261164ac568d3db4dd05160b7e50ec3981d3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193587"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="b8626-103">在商務用 Skype Server 中進行容錯移轉及重新失敗</span><span class="sxs-lookup"><span data-stu-id="b8626-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="b8626-104">如果單一前端池已失敗且需要進行容錯移轉, 或者遇到災難的池已重新連線, 則請使用下列程式, 您需要將您的部署還原為一般的工作狀態。</span><span class="sxs-lookup"><span data-stu-id="b8626-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="b8626-105">另請參閱如何進行容錯移轉, 並將用於商務用 Skype 同盟或 XMPP 同盟的邊緣池切換回故障, 或變更與前端池相關聯的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="b8626-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="b8626-106">容錯移轉到前臺端池</span><span class="sxs-lookup"><span data-stu-id="b8626-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="b8626-107">容錯回復池</span><span class="sxs-lookup"><span data-stu-id="b8626-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="b8626-108">針對商務用 Skype Server federation 所使用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="b8626-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="b8626-109">在商務用 Skype Server 中針對 XMPP 同盟使用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="b8626-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="b8626-110">容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的邊緣池</span><span class="sxs-lookup"><span data-stu-id="b8626-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="b8626-111">變更與前端池相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="b8626-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="b8626-112">容錯移轉到前臺端池</span><span class="sxs-lookup"><span data-stu-id="b8626-112">Fail over a Front End pool</span></span>

<span data-ttu-id="b8626-113">在此程式中, Datacenter1 包含 Pool1, 而 Pool1 失敗。</span><span class="sxs-lookup"><span data-stu-id="b8626-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="b8626-114">您正在進行容錯移轉至 Pool2, 並在 Datacenter2 中找到。</span><span class="sxs-lookup"><span data-stu-id="b8626-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="b8626-115">大部分的 [彙集] 容錯移轉作業都會涉及中央管理儲存區的故障 (如果需要的話)。</span><span class="sxs-lookup"><span data-stu-id="b8626-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="b8626-116">這很重要, 因為集中管理儲存在池的使用者進行容錯移轉時必須正常運作。</span><span class="sxs-lookup"><span data-stu-id="b8626-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="b8626-117">此外, 如果前端池發生故障, 但該網站上的邊緣池仍在執行, 您必須知道邊緣池是否會使用失敗的資源池做為下一個躍點池。</span><span class="sxs-lookup"><span data-stu-id="b8626-117">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="b8626-118">如果有的話, 您必須先將 Edge 池變更為使用不同的前端池, 才能失敗轉移失敗的前臺端池。</span><span class="sxs-lookup"><span data-stu-id="b8626-118">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="b8626-119">變更下一個躍點的設定的方式, 取決於邊緣是在與邊緣池相同的網站上使用資源庫, 還是其他網站。</span><span class="sxs-lookup"><span data-stu-id="b8626-119">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="b8626-120">**若要將邊緣池設定為在相同的網站使用下一個躍點池**</span><span class="sxs-lookup"><span data-stu-id="b8626-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="b8626-121">開啟拓撲建立器, 以滑鼠右鍵按一下需要變更的邊緣池, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="b8626-122">按一下 **[下一個躍點]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-122">Click **Next Hop**.</span></span> <span data-ttu-id="b8626-123">從**下一個 [躍點] 池:** 清單中, 選取現在將充當下一個躍點池的池。</span><span class="sxs-lookup"><span data-stu-id="b8626-123">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="b8626-124">按一下 **[確定]**, 然後發佈所做的變更。</span><span class="sxs-lookup"><span data-stu-id="b8626-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="b8626-125">**若要將邊緣池設定為在不同的網站使用下一個躍點池**</span><span class="sxs-lookup"><span data-stu-id="b8626-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="b8626-126">開啟商務用 Skype Server 管理命令介面視窗, 然後輸入下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b8626-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="b8626-127">**在災難中容錯移轉池**</span><span class="sxs-lookup"><span data-stu-id="b8626-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="b8626-128">在 Pool2 的前端伺服器上輸入下列 Cmdlet, 以找出哪個池是中央管理伺服器的主機:</span><span class="sxs-lookup"><span data-stu-id="b8626-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="b8626-129">這個 Cmdlet 的結果會顯示目前由哪個池託管中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="b8626-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="b8626-130">在此程式的其餘部分中, 此池稱為 CMS\_池。</span><span class="sxs-lookup"><span data-stu-id="b8626-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="b8626-131">使用拓撲建立器, 找出在 CMS\_池中執行的商務用 Skype 伺服器版本。</span><span class="sxs-lookup"><span data-stu-id="b8626-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="b8626-132">如果它正在執行商務用 Skype Server, 請使用下列 Cmdlet 來尋找 Pool 1 的備份池。</span><span class="sxs-lookup"><span data-stu-id="b8626-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="b8626-133">讓備份\_池成為備份池。</span><span class="sxs-lookup"><span data-stu-id="b8626-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="b8626-134">使用下列 Cmdlet 檢查中央管理儲存區的狀態:</span><span class="sxs-lookup"><span data-stu-id="b8626-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="b8626-135">這個 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8626-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="b8626-136">如果它們是空的, 則中央管理伺服器無法使用, 而且您必須將它容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="b8626-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="b8626-137">如果中央管理儲存體無法使用, 或中央管理儲存在 Pool1 上執行 (也就是已失敗的 pool), 您必須先將中央管理伺服器容錯移轉, 才能失敗轉移池。</span><span class="sxs-lookup"><span data-stu-id="b8626-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="b8626-138">如果您需要容錯移轉在執行商務用 Skype Server 的池中所託管的中央管理伺服器, 請使用此程式步驟5中的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8626-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="b8626-139">如果您不需要將中央管理伺服器容錯移轉, 請跳至此程式的步驟7。</span><span class="sxs-lookup"><span data-stu-id="b8626-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="b8626-140">若要在執行商務用 Skype Server 的池上容錯移轉中央管理存放區, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="b8626-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="b8626-141">首先, 請輸入下列內容, 以檢查\_備份池中哪一個後端伺服器執行中央管理儲存區的主要實例:</span><span class="sxs-lookup"><span data-stu-id="b8626-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="b8626-142">如果 [備份\_] 池中的主要後端伺服器是 [主體], 請輸入:</span><span class="sxs-lookup"><span data-stu-id="b8626-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="b8626-143">如果 [備份\_] 池中的 [鏡像後端伺服器] 是 [主體], 請輸入:</span><span class="sxs-lookup"><span data-stu-id="b8626-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="b8626-144">驗證中央管理伺服器容錯移轉已完成。</span><span class="sxs-lookup"><span data-stu-id="b8626-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="b8626-145">輸入下列內容:</span><span class="sxs-lookup"><span data-stu-id="b8626-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="b8626-146">確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8626-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b8626-147">最後, 請輸入下列內容來檢查所有前端伺服器的複本狀態:</span><span class="sxs-lookup"><span data-stu-id="b8626-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="b8626-148">檢查所有複本的值是否為 True。</span><span class="sxs-lookup"><span data-stu-id="b8626-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="b8626-149">跳至此程式中的步驟7。</span><span class="sxs-lookup"><span data-stu-id="b8626-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="b8626-150">在備份\_池的後端伺服器上安裝中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="b8626-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b8626-151">首先, 請執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="b8626-151">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="b8626-152">在備份\_池的其中一個前端伺服器上執行下一個命令, 以強制移動中央管理存儲:</span><span class="sxs-lookup"><span data-stu-id="b8626-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="b8626-153">驗證移動已完成:</span><span class="sxs-lookup"><span data-stu-id="b8626-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="b8626-154">確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8626-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="b8626-155">輸入下列專案, 以檢查所有前端伺服器的複本狀態:</span><span class="sxs-lookup"><span data-stu-id="b8626-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="b8626-156">檢查所有複本的值是否為 True。</span><span class="sxs-lookup"><span data-stu-id="b8626-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="b8626-157">在備份\_池中的其他前端伺服器上, 安裝中央管理伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="b8626-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="b8626-158">若要這樣做, 請在所有前端伺服器上執行下列命令, 除了您強制集中式管理儲存在此程式中較早移動時所使用的那一種。</span><span class="sxs-lookup"><span data-stu-id="b8626-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="b8626-159">在商務用 Skype Server Management 命令介面視窗中執行下列 Cmdlet, 將使用者從 Pool1 中容錯移轉至 Pool2:</span><span class="sxs-lookup"><span data-stu-id="b8626-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="b8626-160">因為在這個程式的前幾部分中所採取的步驟來檢查中央管理儲存狀態不是通用的, 所以這個 Cmdlet 可能會因為中央管理儲存體尚未完全容錯移轉而失敗。</span><span class="sxs-lookup"><span data-stu-id="b8626-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="b8626-161">在這種情況下, 您必須根據所看到的錯誤訊息來修正中央管理儲存區, 然後再次執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b8626-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="b8626-162">如果您看到下列錯誤訊息, 則您需要變更此網站上的 Edge 池, 以便在該池進行容錯移轉前, 使用不同的池作為其下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="b8626-162">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="b8626-163">如需詳細資訊, 請參閱本主題開頭的程式。</span><span class="sxs-lookup"><span data-stu-id="b8626-163">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="b8626-164">容錯回復池</span><span class="sxs-lookup"><span data-stu-id="b8626-164">Fail back a pool</span></span>

<span data-ttu-id="b8626-165">當發生災難的池回到線上 (也就是在這個範例中 Pool1) 之後, 請執行下列步驟, 將您的部署還原為一般的工作狀態。</span><span class="sxs-lookup"><span data-stu-id="b8626-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="b8626-166">請注意, 容錯回復程式需要幾分鐘的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="b8626-166">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="b8626-167">針對參考, 對於20000使用者, 預期會需要最多60分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="b8626-167">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="b8626-168">您可以輸入下列 Cmdlet, 以容錯回復傳回 Pool1 且已容錯移轉至 Pool2 的使用者:</span><span class="sxs-lookup"><span data-stu-id="b8626-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="b8626-169">不需要其他步驟。</span><span class="sxs-lookup"><span data-stu-id="b8626-169">No other steps are necessary.</span></span> <span data-ttu-id="b8626-170">如果您未通過中央管理伺服器進行容錯移轉, 您可以將它留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="b8626-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="b8626-171">針對商務用 Skype Server federation 所使用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="b8626-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="b8626-172">如果您已將商務用 Skype Server federation 的邊緣池設定為向下, 則您必須變更同盟, 才能使用不同的邊緣池來運作。</span><span class="sxs-lookup"><span data-stu-id="b8626-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="b8626-173">在前端伺服器上, 開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="b8626-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="b8626-174">展開 [**邊緣池**], 然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="b8626-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="b8626-175">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="b8626-176">在 [**編輯屬性**] 底下的 **[一般**] 底下, 清除 **[針對此 Edge 池啟用同盟 (埠 5061)**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b8626-177">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8626-177">Click **OK**.</span></span>

3.  <span data-ttu-id="b8626-178">展開 [**邊緣池**], 然後以滑鼠右鍵按一下您要用於同盟的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="b8626-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="b8626-179">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="b8626-180">在 [**編輯屬性**] 底下的 **[一般**] 底下, 選取 **[針對此 Edge 池啟用同盟 (埠 5061)**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-180">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b8626-181">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8626-181">Click **OK**.</span></span>

5.  <span data-ttu-id="b8626-182">按一下 [**動作**], 選取 [**拓撲**], 選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-182">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="b8626-183">**發佈拓撲**時出現提示時, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-183">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="b8626-184">發佈完成後, 請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-184">When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="b8626-185">在邊緣伺服器上, 開啟 [商務用 Skype Server 部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="b8626-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="b8626-186">按一下 [**安裝或更新商務用 Skype Server System**], 然後按一下 [**設定] 或 [移除商務用 skype server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="b8626-187">再次按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="b8626-188">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-188">Click **Next**.</span></span> <span data-ttu-id="b8626-189">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="b8626-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b8626-190">完成部署之後, 按一下 [**查看記錄**] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b8626-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="b8626-191">按一下 **[完成]** 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="b8626-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="b8626-192">如果包含失敗的邊緣池的網站包含仍在執行的前端伺服器, 您必須更新這些前端池的 Web 會議服務和 A/V 會議服務, 才能在仍在執行的遠端網站中使用 Edge 池。</span><span class="sxs-lookup"><span data-stu-id="b8626-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="b8626-193">在商務用 Skype Server 中針對 XMPP 同盟使用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="b8626-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="b8626-194">在您的組織中, 有一個 Edge 池指定為要用於 XMPP 同盟的池。</span><span class="sxs-lookup"><span data-stu-id="b8626-194">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="b8626-195">如果此池向下移動, 您必須容錯移轉 XMPP 同盟, 才能使用不同的邊緣池, 然後 XMPP 同盟才能再次運作。</span><span class="sxs-lookup"><span data-stu-id="b8626-195">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="b8626-196">當您第一次安裝 Edge 池並啟用 XMPP 同盟時, 您可以針對所有的邊緣池設定外部 DNS SRV 記錄 (而不只是一個), 來簡化災害復原程式。</span><span class="sxs-lookup"><span data-stu-id="b8626-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="b8626-197">這些 SRV 記錄中的每一個都必須設定不同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="b8626-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="b8626-198">所有 XMPP 聯盟流量都是透過擁有最高優先順序的 SRV 記錄的池中進行。</span><span class="sxs-lookup"><span data-stu-id="b8626-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="b8626-199">在下列程式中, EdgePool1 是最初託管 XMPP 同盟的池, 而 EdgePool2 是該池, 現在將託管 XMPP 同盟。</span><span class="sxs-lookup"><span data-stu-id="b8626-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="b8626-200">若要針對 XMPP 同盟使用的邊緣池進行容錯移轉</span><span class="sxs-lookup"><span data-stu-id="b8626-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="b8626-201">如果您還沒有部署另一個 Edge 池 (除了目前已停機), 請部署該池。</span><span class="sxs-lookup"><span data-stu-id="b8626-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="b8626-202">在新 Edge 池中的每個 Edge 伺服器上, 現在將會主控 XMPP 同盟 (EdgePool2), 請執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b8626-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="b8626-203">執行下列 Cmdlet, 以 repoint XMPP 同盟路由至 EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="b8626-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="b8626-204">在這個範例中, Site2 是包含邊緣池的網站, 現在將託管 XMPP 同盟路由, 而 EdgeServer2.contoso.com 是該池中的邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8626-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="b8626-205">在外部 DNS 伺服器上, 將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b8626-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="b8626-206">如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄, 而該內容現在將託管 XMPP 同盟, 您必須新增該記錄, 如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="b8626-206">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="b8626-207">這個 SRV 記錄的埠值必須是5269。</span><span class="sxs-lookup"><span data-stu-id="b8626-207">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="b8626-208">確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。</span><span class="sxs-lookup"><span data-stu-id="b8626-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="b8626-209">在邊緣池中的所有邊緣伺服器上啟動服務, 現在將會託管 XMPP federation:</span><span class="sxs-lookup"><span data-stu-id="b8626-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="b8626-210">容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的邊緣池</span><span class="sxs-lookup"><span data-stu-id="b8626-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="b8626-211">當您用來主持同盟的邊緣池已重新連線之後, 請使用此程式, 將商務用 Skype Server 同盟路由和/或 XMPP 同盟路由重新進行容錯回復, 以再次使用此已還原的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="b8626-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="b8626-212">在現在可以再次使用的邊緣池中, 啟動 Edge 服務。</span><span class="sxs-lookup"><span data-stu-id="b8626-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="b8626-213">如果您想要將商務用 Skype Server 同盟路由容錯回復到使用已還原的邊緣伺服器, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="b8626-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b8626-214">在前端伺服器上, 開啟 [拓撲建立器]。</span><span class="sxs-lookup"><span data-stu-id="b8626-214">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="b8626-215">展開 [**邊緣池**], 然後以滑鼠右鍵按一下目前針對同盟設定的邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="b8626-215">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="b8626-216">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-216">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b8626-217">在 [**編輯屬性**] 底下的 **[一般**] 底下, 清除 **[針對此 Edge 池啟用同盟 (埠 5061)**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-217">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b8626-218">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8626-218">Click **OK**.</span></span>
    
      - <span data-ttu-id="b8626-219">展開 [**邊緣池**], 然後以滑鼠右鍵按一下您想要用於同盟的原始邊緣伺服器或 edge 伺服器池。</span><span class="sxs-lookup"><span data-stu-id="b8626-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="b8626-220">選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b8626-221">在 [**編輯屬性**] 底下的 **[一般**] 底下, 選取 **[針對此 Edge 池啟用同盟 (埠 5061)**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-221">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="b8626-222">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8626-222">Click **OK**.</span></span>
    
      - <span data-ttu-id="b8626-223">按一下 [**動作**], 選取 [**拓撲**], 選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-223">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="b8626-224">**發佈拓撲**時出現提示時, 請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-224">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="b8626-225">發佈完成後, 請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-225">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="b8626-226">在邊緣伺服器上, 開啟 [商務用 Skype Server 部署] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="b8626-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="b8626-227">按一下 [**安裝或更新商務用 Skype Server 系統**], 然後按一下 [**設定] 或 [移除商務用 skype server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="b8626-228">再次按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="b8626-229">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b8626-229">Click **Next**.</span></span> <span data-ttu-id="b8626-230">[摘要] 畫面會在執行時顯示動作。</span><span class="sxs-lookup"><span data-stu-id="b8626-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b8626-231">完成部署之後, 按一下 [**查看記錄**] 以查看可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b8626-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="b8626-232">按一下 **[完成]** 以完成部署。</span><span class="sxs-lookup"><span data-stu-id="b8626-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="b8626-233">如果您想要將 XMPP 同盟路由容錯回復到使用已還原的邊緣伺服器, 請執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="b8626-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b8626-234">執行下列 Cmdlet, 將 XMPP 同盟路由 repoint 到 Edge 池中, 這將會立即託管 XMPP 同盟 (在此範例中為 EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="b8626-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="b8626-235">在這個範例中, Site1 是包含邊緣池的網站, 現在將託管 XMPP 同盟路由, 而 EdgeServer1.contoso.com 是該池中的邊緣伺服器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b8626-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="b8626-236">如果您還沒有可解析到 Edge 池的 XMPP 同盟的 DNS SRV 記錄, 而該內容現在將託管 XMPP 同盟, 您必須新增該記錄, 如下列範例所示。</span><span class="sxs-lookup"><span data-stu-id="b8626-236">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="b8626-237">這個 SRV 記錄的埠值必須是5269。</span><span class="sxs-lookup"><span data-stu-id="b8626-237">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="b8626-238">在外部 DNS 伺服器上, 將 XMPP 同盟的 DNS A 記錄變更為指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="b8626-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="b8626-239">確認現在將由 XMPP 同盟託管的邊緣池已在外部開啟埠5269。</span><span class="sxs-lookup"><span data-stu-id="b8626-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="b8626-240">如果前端池仍在包含已失敗且已還原的邊緣池的網站中執行, 您應該在這些前端池上更新網路會議服務和 A/V 會議服務, 以再次使用其本機網站上的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="b8626-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="b8626-241">如果與失敗的邊緣池位於同一網站的前端池也失敗, 您現在可以使用 Invoke-CsPoolFailback 來容錯回復前端池。</span><span class="sxs-lookup"><span data-stu-id="b8626-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="b8626-242">變更與前端池相關聯的邊緣池</span><span class="sxs-lookup"><span data-stu-id="b8626-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="b8626-243">如果邊緣池向下移動, 但位於相同網站的前端池仍在執行, 則您必須將前端池設定為在不同的網站上使用 Edge 池, 直到失敗的邊緣池已復原為止。</span><span class="sxs-lookup"><span data-stu-id="b8626-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="b8626-244">在 [拓撲建立器] 中, 流覽至您需要變更的前端池名稱。</span><span class="sxs-lookup"><span data-stu-id="b8626-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="b8626-245">以滑鼠右鍵按一下該池子, 然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="b8626-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="b8626-246">在 [**關聯**性] 區段的 [**關聯邊緣池 (適用于媒體元件)**] 底下, 使用下拉式方塊來選取您要與此前端池建立關聯的邊緣池。</span><span class="sxs-lookup"><span data-stu-id="b8626-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="b8626-247">按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b8626-247">Click **OK**.</span></span>
