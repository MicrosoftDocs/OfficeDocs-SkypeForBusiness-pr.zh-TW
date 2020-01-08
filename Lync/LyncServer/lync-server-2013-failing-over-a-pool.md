---
title: Lync Server 2013：容錯移轉集區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 512d7bc09d40d7b99cc66970cdd2a5584030fea9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="818fd-102">在 Lync Server 2013 中容錯移轉集區</span><span class="sxs-lookup"><span data-stu-id="818fd-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="818fd-103">_**主題上次修改日期：** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="818fd-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="818fd-104">如果單一前端池已失敗且需要進行容錯移轉，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="818fd-104">If a single Front End pool has failed and needs to be failed over, use the following procedure.</span></span> <span data-ttu-id="818fd-105">在此程式中，Datacenter1 包含 Pool1，而 Pool1 失敗。</span><span class="sxs-lookup"><span data-stu-id="818fd-105">In this procedure, Datacenter1 contains Pool1, and Pool1 has failed.</span></span> <span data-ttu-id="818fd-106">您正在進行容錯移轉至 Pool2，並在 Datacenter2 中找到。</span><span class="sxs-lookup"><span data-stu-id="818fd-106">You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="818fd-107">大部分的 [彙集] 容錯移轉作業都會涉及中央管理儲存區的故障（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="818fd-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="818fd-108">這很重要，因為集中管理儲存在池的使用者進行容錯移轉時必須正常運作。</span><span class="sxs-lookup"><span data-stu-id="818fd-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="818fd-109">此外，如果前端池發生故障，但該網站上的邊緣池仍在執行，您必須知道邊緣池是否會使用失敗的資源池做為下一個躍點池。</span><span class="sxs-lookup"><span data-stu-id="818fd-109">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool.</span></span> <span data-ttu-id="818fd-110">如果有的話，您必須先將 Edge 池變更為使用不同的前端池，才能失敗轉移失敗的前臺端池。</span><span class="sxs-lookup"><span data-stu-id="818fd-110">If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool.</span></span> <span data-ttu-id="818fd-111">變更下一個躍點的設定的方式，取決於邊緣是在與邊緣池相同的網站上使用資源庫，還是其他網站。</span><span class="sxs-lookup"><span data-stu-id="818fd-111">How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="818fd-112">**若要將邊緣池設定為在相同的網站使用下一個躍點池**</span><span class="sxs-lookup"><span data-stu-id="818fd-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="818fd-113">開啟拓撲建立器，以滑鼠右鍵按一下需要變更的邊緣池，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="818fd-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="818fd-114">按一下 **[下一個躍點]**。</span><span class="sxs-lookup"><span data-stu-id="818fd-114">Click **Next Hop**.</span></span> <span data-ttu-id="818fd-115">從**下一個 [躍點] 池：** 清單中，選取現在將充當下一個躍點池的池。</span><span class="sxs-lookup"><span data-stu-id="818fd-115">From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="818fd-116">按一下 **[確定]**，然後發佈所做的變更。</span><span class="sxs-lookup"><span data-stu-id="818fd-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="818fd-117">**若要將邊緣池設定為在不同的網站使用下一個躍點池**</span><span class="sxs-lookup"><span data-stu-id="818fd-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="818fd-118">開啟 Lync Server 管理命令介面視窗，然後輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="818fd-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="818fd-119">**在災難中容錯移轉池**</span><span class="sxs-lookup"><span data-stu-id="818fd-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="818fd-120">在 Pool2 的前端伺服器上輸入下列 Cmdlet，以找出哪個池是中央管理伺服器的主機：</span><span class="sxs-lookup"><span data-stu-id="818fd-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="818fd-121">這個 Cmdlet 的結果會顯示目前由哪個池託管中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="818fd-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="818fd-122">在此程式的其餘部分中，此池稱為 CMS\_池。</span><span class="sxs-lookup"><span data-stu-id="818fd-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="818fd-123">使用拓撲建立器找出在 CMS\_池中執行的 Lync Server 版本。</span><span class="sxs-lookup"><span data-stu-id="818fd-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="818fd-124">如果它正在執行 Lync Server 2013，請使用下列 Cmdlet 來尋找 Pool 1 的備份池。</span><span class="sxs-lookup"><span data-stu-id="818fd-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="818fd-125">讓備份\_池成為備份池。</span><span class="sxs-lookup"><span data-stu-id="818fd-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="818fd-126">使用下列 Cmdlet 檢查中央管理儲存區的狀態：</span><span class="sxs-lookup"><span data-stu-id="818fd-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="818fd-127">這個 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS\_池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="818fd-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="818fd-128">如果它們是空的，則中央管理伺服器無法使用，而且您必須將它容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="818fd-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="818fd-129">如果中央管理儲存體無法使用，或中央管理儲存在 Pool1 上執行（也就是已失敗的 pool），您必須先將中央管理伺服器容錯移轉，才能失敗轉移池。</span><span class="sxs-lookup"><span data-stu-id="818fd-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="818fd-130">如果您需要容錯移轉在執行 Lync Server 2013 的 pool 上託管的中央管理伺服器，請使用此程式步驟5中的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="818fd-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="818fd-131">如果您需要容錯移轉在執行 Lync Server 2010 的 pool 上託管的中央管理伺服器，請使用此程式步驟6中的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="818fd-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="818fd-132">如果您不需要將中央管理伺服器容錯移轉，請跳至此程式的步驟7。</span><span class="sxs-lookup"><span data-stu-id="818fd-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="818fd-133">若要在執行 Lync Server 2013 的池中容錯移轉中央管理儲存體，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="818fd-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="818fd-134">首先，請輸入下列內容，以檢查\_備份池中哪一個後端伺服器執行中央管理儲存區的主要實例：</span><span class="sxs-lookup"><span data-stu-id="818fd-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="818fd-135">如果 [備份\_] 池中的主要後端伺服器是 [主體]，請輸入：</span><span class="sxs-lookup"><span data-stu-id="818fd-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="818fd-136">如果 [備份\_] 池中的 [鏡像後端伺服器] 是 [主體]，請輸入：</span><span class="sxs-lookup"><span data-stu-id="818fd-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="818fd-137">驗證中央管理伺服器容錯移轉已完成。</span><span class="sxs-lookup"><span data-stu-id="818fd-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="818fd-138">輸入下列內容：</span><span class="sxs-lookup"><span data-stu-id="818fd-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="818fd-139">確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="818fd-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="818fd-140">最後，請輸入下列內容來檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="818fd-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="818fd-141">檢查所有複本的值是否為 True。</span><span class="sxs-lookup"><span data-stu-id="818fd-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="818fd-142">跳至此程式中的步驟7。</span><span class="sxs-lookup"><span data-stu-id="818fd-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="818fd-143">在備份\_池的後端伺服器上安裝中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="818fd-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="818fd-144">首先，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="818fd-144">First, run the following command:</span></span>
        
        ``` 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="818fd-145">在備份\_池的其中一個前端伺服器上執行下一個命令，以強制移動中央管理存儲：</span><span class="sxs-lookup"><span data-stu-id="818fd-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="818fd-146">驗證移動已完成：</span><span class="sxs-lookup"><span data-stu-id="818fd-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="818fd-147">確認 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 [備份\_] 池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="818fd-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="818fd-148">輸入下列專案，以檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="818fd-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="818fd-149">檢查所有複本的值是否為 True。</span><span class="sxs-lookup"><span data-stu-id="818fd-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="818fd-150">在備份\_池中的其他前端伺服器上，安裝中央管理伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="818fd-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="818fd-151">若要這樣做，請在所有前端伺服器上執行下列命令，除了您強制集中式管理儲存在此程式中較早移動時所使用的那一種。</span><span class="sxs-lookup"><span data-stu-id="818fd-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="818fd-152">在 Lync Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 到 Pool2 進行容錯移轉：</span><span class="sxs-lookup"><span data-stu-id="818fd-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="818fd-153">因為在這個程式的前幾部分中所採取的步驟來檢查中央管理儲存狀態不是通用的，所以這個 Cmdlet 可能會因為中央管理儲存體尚未完全容錯移轉而失敗。</span><span class="sxs-lookup"><span data-stu-id="818fd-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="818fd-154">在這種情況下，您必須根據所看到的錯誤訊息來修正中央管理儲存區，然後再次執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="818fd-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="818fd-155">如果您看到下列錯誤訊息，則您需要變更此網站上的 Edge 池，以便在該池進行容錯移轉前，使用不同的池作為其下一個躍點。</span><span class="sxs-lookup"><span data-stu-id="818fd-155">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool.</span></span> <span data-ttu-id="818fd-156">如需詳細資訊，請參閱本主題開頭的程式。</span><span class="sxs-lookup"><span data-stu-id="818fd-156">For details, see the procedures at the beginning of this topic.</span></span>
    
        Invoke-CsPoolFailOver : This Front-end pool "pool1.contoso.com" is specified in
        topology as the next hop for the Edge server. Failing over this pool may cause External
        access/Federation/Split-domain/XMPP features to stop working. Please use Topology Builder to
        change the Edge internal next hop setting to point to a different Front-end pool,  before you
        proceed.

</div>

<span> </span>

</div>

</div>

</div>

