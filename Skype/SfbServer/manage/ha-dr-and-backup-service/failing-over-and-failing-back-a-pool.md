---
title: 對集區進行容錯移轉及容錯回復
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: .
ms.openlocfilehash: 1ebd4e8110b8783c869530d95eda0646a895b88e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826563"
---
# <a name="failing-over-and-failing-back-a-pool-in-skype-for-business-server"></a><span data-ttu-id="c9453-103">在商務用 Skype Server 中容錯移轉和失敗回復集區</span><span class="sxs-lookup"><span data-stu-id="c9453-103">Failing over and failing back a pool in Skype for Business Server</span></span> 

<span data-ttu-id="c9453-104">使用下列程式如果單一前端集區失敗且需要容錯移轉，或發生災難的集區傳回線上，您必須將部署還原為一般的工作狀態。</span><span class="sxs-lookup"><span data-stu-id="c9453-104">Use the following procedures if a single Front End pool has failed and needs to be failed over, or the pool that experienced the disaster is back online and you need to restore your deployment to regular working status.</span></span> <span data-ttu-id="c9453-105">此外，還會瞭解如何容錯移轉及容錯回復用於商務用 Skype 同盟或 XMPP 同盟的 Edge 集區，或是變更與前端集區相關聯的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-105">Also  learn how to fail over and fail back the Edge pool used for Skype for Business federation or XMPP federation, or change the Edge pool associated with a Front End pool.</span></span>

- [<span data-ttu-id="c9453-106">容錯移轉前端集區</span><span class="sxs-lookup"><span data-stu-id="c9453-106">Fail over a Front End pool</span></span>](#fail-over-a-front-end-pool)
- [<span data-ttu-id="c9453-107">容錯回復集區</span><span class="sxs-lookup"><span data-stu-id="c9453-107">Fail back a pool</span></span>](#fail-back-a-pool)
- [<span data-ttu-id="c9453-108">容錯移轉用於商務用 Skype 伺服器同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-108">Fail over the Edge pool used for Skype for Business Server federation</span></span>](#fail-over-the-edge-pool-used-for-skype-for-business-server-federation)
- [<span data-ttu-id="c9453-109">容錯移轉用於商務用 Skype Server 中用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-109">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span>](#fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server)
- [<span data-ttu-id="c9453-110">容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-110">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span>](#fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation)
- [<span data-ttu-id="c9453-111">變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-111">Change the Edge pool associated with a Front End pool</span></span>](#change-the-edge-pool-associated-with-a-front-end-pool)

## <a name="fail-over-a-front-end-pool"></a><span data-ttu-id="c9453-112">容錯移轉前端集區</span><span class="sxs-lookup"><span data-stu-id="c9453-112">Fail over a Front End pool</span></span>

<span data-ttu-id="c9453-113">在此程序中，Datacenter1 包含 Pool1，而 Pool1 失敗了。</span><span class="sxs-lookup"><span data-stu-id="c9453-113">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="c9453-114">您要容錯移轉至位在 Datacenter2 的 Pool2。</span><span class="sxs-lookup"><span data-stu-id="c9453-114">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="c9453-115">如果需要，集區容錯移轉的大部分工作會包括容錯移轉中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="c9453-115">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="c9453-116">這一點很重要，因為中央管理存放區在集區使用者容錯移轉時必須正常運作。</span><span class="sxs-lookup"><span data-stu-id="c9453-116">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="c9453-p104">此外，如果前端集區失敗，但位在該網站的 Edge 集區仍在執行中，您就必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。如果是，則必須先變更 Edge 集區為使用不同的前端集區，再容錯移轉至失敗的前端集區。變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。</span><span class="sxs-lookup"><span data-stu-id="c9453-p104">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="c9453-120">**將 Edge 集區設定為在相同的網站使用下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="c9453-120">**To set an Edge pool to use a next hop pool at the same site**</span></span>

1.  <span data-ttu-id="c9453-121">開啟拓撲產生器，以滑鼠右鍵按一下需要變更的 Edge 集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="c9453-121">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c9453-p105">按 [下一個躍點]。從 [下一個躍點集區:] 清單中，選取現在要作為下一個躍點集區的集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-p105">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="c9453-124">按一下 [確定]，然後發行變更。</span><span class="sxs-lookup"><span data-stu-id="c9453-124">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="c9453-125">**將 Edge 集區設定為在不同的網站使用下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="c9453-125">**To set an Edge pool to use a next hop pool at a different site**</span></span>

1.  <span data-ttu-id="c9453-126">開啟商務用 Skype Server 管理命令介面視窗，並輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9453-126">Open a Skype for Business Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="c9453-127">**在發生嚴重損壞集區時進行容錯移轉**</span><span class="sxs-lookup"><span data-stu-id="c9453-127">**To fail over a pool in a disaster**</span></span>

1.  <span data-ttu-id="c9453-128">在 Pool2 中的前端伺服器上輸入下列 Cmdlet，以尋找哪一個集區是中央管理伺服器的主機：</span><span class="sxs-lookup"><span data-stu-id="c9453-128">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="c9453-129">此 Cmdlet 的結果會顯示目前主控中央管理伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-129">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="c9453-130">在此程式的其餘部分中，此集區稱為 CMS \_ 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-130">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="c9453-131">使用拓撲產生器來尋找在 CMS 集區上執行之商務用 Skype Server 的版本 \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-131">Use Topology Builder to find the version of Skype for Business Server running on the CMS\_Pool.</span></span> <span data-ttu-id="c9453-132">若執行商務用 Skype Server，請使用下列 Cmdlet 來尋找集區1的備份組區。</span><span class="sxs-lookup"><span data-stu-id="c9453-132">If it is running Skype for Business Server, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="c9453-133">讓備份 \_ 集區成為備份組區。</span><span class="sxs-lookup"><span data-stu-id="c9453-133">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="c9453-134">使用下列 Cmdlet 檢查中央管理存放區的狀態：</span><span class="sxs-lookup"><span data-stu-id="c9453-134">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="c9453-135">此 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 集區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-135">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="c9453-136">如果它們是空的，則中央管理伺服器無法使用，而且您必須進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="c9453-136">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="c9453-137">若中央管理存放區無法使用，或者中央管理存放區正在 Pool1 上執行 (也就是) 失敗的集區，則必須先容錯移轉中央管理伺服器，再進行集區容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="c9453-137">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="c9453-138">如果您需要容錯移轉中央管理伺服器（位於執行商務用 Skype Server 的集區上），請使用此程式步驟5的指令程式。</span><span class="sxs-lookup"><span data-stu-id="c9453-138">If you need to fail over the Central Management Server that was hosted on a pool running Skype for Business Server, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="c9453-139">如果您不需要透過中央管理伺服器進行容錯移轉，請跳至此程式的步驟7。</span><span class="sxs-lookup"><span data-stu-id="c9453-139">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="c9453-140">若要在執行商務用 Skype 伺服器的集區上容錯移轉中央管理存放區，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c9453-140">To fail over the Central Management store on a pool running Skype for Business Server, do the following:</span></span>
    
      - <span data-ttu-id="c9453-141">首先，請輸入下列命令，檢查備份組區中的哪一部後端伺服器 \_ 執行中央管理存放區的主體實例：</span><span class="sxs-lookup"><span data-stu-id="c9453-141">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="c9453-142">如果備份組區中的主要後端伺服器 \_ 是主體，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c9453-142">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="c9453-143">如果備份組區中的鏡像後端伺服器 \_ 是主體，請輸入：</span><span class="sxs-lookup"><span data-stu-id="c9453-143">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="c9453-144">驗證中央管理伺服器容錯移轉是否已完成。</span><span class="sxs-lookup"><span data-stu-id="c9453-144">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="c9453-145">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9453-145">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c9453-146">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-146">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c9453-147">最後，輸入下列命令，檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="c9453-147">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c9453-148">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="c9453-148">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="c9453-149">跳到此程序的步驟 7。</span><span class="sxs-lookup"><span data-stu-id="c9453-149">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="c9453-150">在備份組區的後端伺服器上安裝中央管理存放區 \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-150">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c9453-151">首先，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="c9453-151">First, run the following command:</span></span>
        ```PowerShell
         
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="c9453-152">在其中一個備份組區的前端伺服器上執行下一個命令 \_ ，以強制移動中央管理存放區：</span><span class="sxs-lookup"><span data-stu-id="c9453-152">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="c9453-153">驗證移動完成：</span><span class="sxs-lookup"><span data-stu-id="c9453-153">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="c9453-154">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-154">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="c9453-155">輸入下列命令，檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="c9453-155">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="c9453-156">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="c9453-156">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="c9453-157">在備份組區中的其他前端伺服器上安裝中央管理伺服器服務 \_ 。</span><span class="sxs-lookup"><span data-stu-id="c9453-157">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="c9453-158">若要這麼做，請在所有前端伺服器上執行下列命令，除了強制您在此程式中強制執行中央管理存放區時所使用的伺服器之外：</span><span class="sxs-lookup"><span data-stu-id="c9453-158">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="c9453-159">在商務用 Skype Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 容錯移轉至 Pool2：</span><span class="sxs-lookup"><span data-stu-id="c9453-159">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Skype for Business Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="c9453-160">因為在此程式的先前部分中，檢查中央管理存放區狀態所採取的步驟並不是通用的，所以此 Cmdlet 仍然會失敗，因為中央管理存放區尚未完全容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="c9453-160">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="c9453-161">在此情況下，您必須根據所看到的錯誤訊息修正中央管理存放區，然後再次執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c9453-161">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="c9453-p113">如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。</span><span class="sxs-lookup"><span data-stu-id="c9453-p113">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.


## <a name="fail-back-a-pool"></a><span data-ttu-id="c9453-164">容錯回復集區</span><span class="sxs-lookup"><span data-stu-id="c9453-164">Fail back a pool</span></span>

<span data-ttu-id="c9453-165">在發生災難的集區重新連線後 (如此範例中的 Pool1)，請採取下列步驟將部署還原至正常運作狀態。</span><span class="sxs-lookup"><span data-stu-id="c9453-165">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="c9453-166">請注意，容錯回復程序需要數分鐘才能完成。</span><span class="sxs-lookup"><span data-stu-id="c9453-166">Note that the failback process takes several minute to complete.</span></span>  <span data-ttu-id="c9453-167">僅供參考：對於有 20,000 個使用者的集區，預計會花上 60 分鐘。</span><span class="sxs-lookup"><span data-stu-id="c9453-167">For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="c9453-168">若要容錯回復原來位於 Pool1 而容錯移轉至 Pool2 的使用者，請鍵入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9453-168">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
    Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="c9453-169">無需其他步驟。</span><span class="sxs-lookup"><span data-stu-id="c9453-169">No other steps are necessary.</span></span> <span data-ttu-id="c9453-170">如果您已對中央管理伺服器進行容錯移轉，您可以將它保留在 Pool2 中。</span><span class="sxs-lookup"><span data-stu-id="c9453-170">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

## <a name="fail-over-the-edge-pool-used-for-skype-for-business-server-federation"></a><span data-ttu-id="c9453-171">容錯移轉用於商務用 Skype 伺服器同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-171">Fail over the Edge pool used for Skype for Business Server federation</span></span> 

<span data-ttu-id="c9453-172">如果您已設定商務用 Skype Server 同盟的 Edge 集區中斷，您必須將同盟變更為使用不同的 Edge 集區，同盟才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c9453-172">If the Edge pool where you have Skype for Business Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

1.  <span data-ttu-id="c9453-173">在前端伺服器上，開啟 [拓撲產生器]。</span><span class="sxs-lookup"><span data-stu-id="c9453-173">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="c9453-174">展開 [ **edge** 集區]，然後在目前針對同盟設定的 edge Server 或 edge server 集區上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="c9453-174">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="c9453-175">選取 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-175">Select **Edit properties**.</span></span>

2.  <span data-ttu-id="c9453-176">在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。</span><span class="sxs-lookup"><span data-stu-id="c9453-176">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="c9453-177">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c9453-177">Click **OK**.</span></span>

3.  <span data-ttu-id="c9453-178">展開 [ **edge** 集區]，然後在您現在想要用於同盟的 edge Server 或 edge server 集區上按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="c9453-178">Expand **Edge pools**, and then right-click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="c9453-179">選取 [編輯內容]。</span><span class="sxs-lookup"><span data-stu-id="c9453-179">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="c9453-p119">在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-p119">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="c9453-p120">按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-p120">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="c9453-185">在 Edge server 上，開啟商務用 Skype 伺服器部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="c9453-185">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="c9453-186">按一下 [ **安裝或更新商務用 Skype Server 系統**]，然後按一下 [ **設定] 或 [移除商務用 skype server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="c9453-186">Click **Install or Update Skype for Business Server System**, and then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="c9453-187">按一下 **[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-187">Click **Run Again**.</span></span>

7.  <span data-ttu-id="c9453-188">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-188">Click **Next**.</span></span> <span data-ttu-id="c9453-189">摘要畫面會隨著動作的執行顯示各個動作。</span><span class="sxs-lookup"><span data-stu-id="c9453-189">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="c9453-190">部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c9453-190">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="c9453-191">按一下 **[完成]** 完成部署。</span><span class="sxs-lookup"><span data-stu-id="c9453-191">Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="c9453-192">如果失敗 Edge 集區所在的網站包含仍在執行的前端伺服器，則必須更新在這些前端集區上的 Web 會議服務及 A/V 會議服務，以使用遠端網站上仍在執行的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-192">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> 

 ## <a name="fail-over-the-edge-pool-used-for-xmpp-federation-in-skype-for-business-server"></a><span data-ttu-id="c9453-193">容錯移轉用於商務用 Skype Server 中用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-193">Fail over the Edge pool used for XMPP federation in Skype for Business Server</span></span> 

<span data-ttu-id="c9453-p123">在您的組織中，有一個指定的 Edge 集區是用於 XMPP 同盟的集區。如果此集區失效，您必須先容錯移轉 XMPP 同盟以使用不同的 Edge 集區，讓 XMPP 同盟可以再次運作。</span><span class="sxs-lookup"><span data-stu-id="c9453-p123">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="c9453-196">當您第一次安裝 Edge 集區並啟用 XMPP 同盟時，可以藉由為所有適用於 XMPP 同盟的 Edge 集區 (而不是只針對其中一個) 設定外部 DNS SRV 記錄，來簡化災害復原程序。</span><span class="sxs-lookup"><span data-stu-id="c9453-196">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="c9453-197">其中的每一個 SRV 記錄都必須設定不同的優先順序。</span><span class="sxs-lookup"><span data-stu-id="c9453-197">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="c9453-198">所有的 XMPP 同盟流量都會通過優先順序最高且含有 SRV 記錄的集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-198">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> 

<span data-ttu-id="c9453-199">在下列程序中，EdgePool1 是原本裝載 XMPP 同盟的集區，而 EdgePool2 是現在裝載 XMPP 同盟的集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-199">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>


### <a name="to-fail-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="c9453-200">容錯移轉用於 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-200">To fail over the Edge pool used for XMPP federation</span></span>

1.  <span data-ttu-id="c9453-201">如果您尚未部署其他 Edge 集區 (除了目前中斷的這一個集區)，請部署該集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-201">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> 

2.  <span data-ttu-id="c9453-202">在現在將裝載 XMPP 同盟之新 Edge 集區 (EdgePool2) 中的每個 Edge Server 上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c9453-202">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="c9453-203">執行下列 Cmdlet，將 XMPP 同盟路由重新指向 EdgePool2：</span><span class="sxs-lookup"><span data-stu-id="c9453-203">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="c9453-204">在此範例中，Site2 為包含現在將裝載 XMPP 同盟路由之 Edge 集區的網站，而 EdgeServer2.contoso.com 為該集區中 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c9453-204">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="c9453-205">在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c9453-205">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="c9453-p125">如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。</span><span class="sxs-lookup"><span data-stu-id="c9453-p125">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="c9453-208">確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。</span><span class="sxs-lookup"><span data-stu-id="c9453-208">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="c9453-209">在現在將裝載 XMPP 同盟之 Edge 集區中的所有 Edge Server 上啟動服務：</span><span class="sxs-lookup"><span data-stu-id="c9453-209">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService


## <a name="fail-back-the-edge-pool-used-for-skype-for-business-server-federation-or-xmpp-federation"></a><span data-ttu-id="c9453-210">容錯回復用於商務用 Skype Server 同盟或 XMPP 同盟的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-210">Fail back the Edge pool used for Skype for Business Server federation or XMPP federation</span></span> 

<span data-ttu-id="c9453-211">在用來主控同盟的失敗 Edge 集區回到線上後，請使用此程式來回複商務用 Skype Server federation route 和/或 XMPP 同盟路由，以再次使用此還原的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-211">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Skype for Business Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

1.  <span data-ttu-id="c9453-212">在現在可以使用的 Edge 集區上，啟動 Edge Services。</span><span class="sxs-lookup"><span data-stu-id="c9453-212">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="c9453-213">如果您想要容錯回復商務用 Skype Server 同盟路由以使用還原的 Edge Server，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c9453-213">If you want to fail back the Skype for Business Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="c9453-p126">在前端伺服器上，開啟拓撲產生器。展開 **[Edge 集區]**，然後在目前設定用於同盟的 Edge Server 或 Edge Server 集區上按一下滑鼠右鍵。選取 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-p126">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="c9453-p127">在 **[編輯內容]** 中，清除 **[一般]** 下的 [啟用此 Edge 集區的同盟 (連接埠 5061)]。按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c9453-p127">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="c9453-219">展開 [ **Edge** 集區]，然後以滑鼠右鍵按一下原始 Edge Server 或 Edge server 集區，以供同盟使用。</span><span class="sxs-lookup"><span data-stu-id="c9453-219">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="c9453-220">選取 [編輯內容]。</span><span class="sxs-lookup"><span data-stu-id="c9453-220">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="c9453-p129">在 [編輯內容]中，選取 [一般] 下的 **[啟用此 Edge 集區的同盟 (連接埠 5061)]**。按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-p129">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="c9453-p130">按一下 **[動作]**，依序選取 **[拓撲]** 和 **[發行]**。在 **[發行拓撲]** 出現提示時，按 **[下一步]**。發行完成時，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-p130">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="c9453-226">在 Edge server 上，開啟商務用 Skype 伺服器部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="c9453-226">On the Edge server, open the Skype for Business Server Deployment wizard.</span></span> <span data-ttu-id="c9453-227">按一下 [ **安裝或更新商務用 Skype 伺服器系統**]，然後按一下 [ **設定] 或 [移除商務用 skype server 元件**]。</span><span class="sxs-lookup"><span data-stu-id="c9453-227">Click **Install or Update Skype for Business Server System**, then click **Setup or Remove Skype for Business Server Components**.</span></span> <span data-ttu-id="c9453-228">按一下 **[再執行一次]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-228">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="c9453-229">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-229">Click **Next**.</span></span> <span data-ttu-id="c9453-230">摘要畫面會隨著動作的執行顯示各個動作。</span><span class="sxs-lookup"><span data-stu-id="c9453-230">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="c9453-231">部署完成後，按一下 **[檢視記錄檔]** 檢視可用的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="c9453-231">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="c9453-232">按一下 **[完成]** 完成部署。</span><span class="sxs-lookup"><span data-stu-id="c9453-232">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="c9453-233">如果您想要容錯回復 XMPP 同盟路由以使用還原的 Edge Server，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c9453-233">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="c9453-234">執行下列 Cmdlet，將 XMPP 同盟路由 repoint 至 Edge 集區，該集區現在會主控 XMPP 同盟 (在此範例中，EdgeServer1) ：</span><span class="sxs-lookup"><span data-stu-id="c9453-234">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="c9453-235">在此範例中，Site1 是包含 Edge 集區的網站，它現在會主控 XMPP 同盟路由，而且 EdgeServer1.contoso.com 是該集區中 Edge Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c9453-235">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="c9453-p133">如果您尚未擁有 XMPP 同盟的 DNS SRV 記錄 (其可解析為現在將裝載 XMPP 同盟的 Edge 集區)，則您必須新增該記錄，如下列範例所示。此 SRV 記錄的連接埠值必須為 5269。</span><span class="sxs-lookup"><span data-stu-id="c9453-p133">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="c9453-238">在外部 DNS 伺服器上，變更 XMPP 同盟的 DNS A 記錄以指向 EdgeServer2.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c9453-238">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="c9453-239">確認現在將裝載 XMPP 同盟的 Edge 集區已在外部開放連接埠 5269。</span><span class="sxs-lookup"><span data-stu-id="c9453-239">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="c9453-240">如果前端集區仍在包含失敗且已還原之 Edge 集區的網站中執行，您應該更新這些前端集區上的 Web 會議服務和 A/V 會議服務，以再次使用本機網站上的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-240">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span>

5.  <span data-ttu-id="c9453-241">如果與失敗 Edge 集區位於相同網站的前端集區也失敗，您現在可以使用 Invoke–CsPoolFailback 來容錯回前端集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-241">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>


## <a name="change-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="c9453-242">變更與前端集區相關聯的 Edge 集區</span><span class="sxs-lookup"><span data-stu-id="c9453-242">Change the Edge pool associated with a Front End pool</span></span>

<span data-ttu-id="c9453-243">如果 Edge 集區失效但相同網站上的前端集區仍在執行，您將需要設定前端集區來使用其他網站上的 Edge 集區，直到失敗的 Edge 集區還原為止。</span><span class="sxs-lookup"><span data-stu-id="c9453-243">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

1.  <span data-ttu-id="c9453-244">在拓撲產生器中，瀏覽至您需要變更的前端集區名稱。</span><span class="sxs-lookup"><span data-stu-id="c9453-244">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="c9453-245">以滑鼠右鍵按一下集區，然後按一下 **[編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="c9453-245">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="c9453-246">在 **[關聯]** 區段的 **[關聯 Edge 集區 (適用於媒體元件)]** 下方，使用下拉式方塊來選取您要與此前端集區產生關聯的 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="c9453-246">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="c9453-247">按一下 [確定]。</span><span class="sxs-lookup"><span data-stu-id="c9453-247">Click **OK**.</span></span>
