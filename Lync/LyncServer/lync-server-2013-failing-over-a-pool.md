---
title: Lync Server 2013：容錯移轉集區
description: Lync Server 2013：容錯移轉集區。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a pool
ms:assetid: 10b13732-bc80-4cb2-a71c-56b1d6cb5bbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204678(v=OCS.15)
ms:contentKeyID: 48183432
ms.date: 10/10/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 819137c1277c5058f4e5d36ef5dbe71e672e8641
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554979"
---
# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="ea983-103">在 Lync Server 2013 中容錯移轉集區</span><span class="sxs-lookup"><span data-stu-id="ea983-103">Failing over a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea983-104">_**主題上次修改日期：** 2014-10-10_</span><span class="sxs-lookup"><span data-stu-id="ea983-104">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="ea983-p101">如果單一前端集區失敗，而需要容錯移轉，請使用下列程序。在此程序中，Datacenter1 包含 Pool1，而 Pool1 失敗了。您要容錯移轉至位在 Datacenter2 的 Pool2。</span><span class="sxs-lookup"><span data-stu-id="ea983-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="ea983-108">如果需要，集區容錯移轉的大部分工作會包括容錯移轉中央管理存放區。</span><span class="sxs-lookup"><span data-stu-id="ea983-108">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="ea983-109">這一點很重要，因為中央管理存放區在集區使用者容錯移轉時必須正常運作。</span><span class="sxs-lookup"><span data-stu-id="ea983-109">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="ea983-p103">此外，如果前端集區失敗，但位在該網站的 Edge 集區仍在執行中，您就必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。如果是，則必須先變更 Edge 集區為使用不同的前端集區，再容錯移轉至失敗的前端集區。變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。</span><span class="sxs-lookup"><span data-stu-id="ea983-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="ea983-113">**將 Edge 集區設定為使用位在相同網站的下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="ea983-113">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="ea983-114">開啟拓撲產生器，以滑鼠右鍵按一下需要變更的 Edge 集區，然後按一下 [ **編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="ea983-114">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="ea983-p104">按 [下一個躍點]\*\*\*\*。從 [下一個躍點集區:]\*\*\*\* 清單中，選取現在要作為下一個躍點集區的集區。</span><span class="sxs-lookup"><span data-stu-id="ea983-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="ea983-117">按一下 [確定]\*\*\*\*，然後發行變更。</span><span class="sxs-lookup"><span data-stu-id="ea983-117">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="ea983-118">**將 Edge 集區設定為使用位在不同網站的下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="ea983-118">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="ea983-119">開啟 Lync Server 管理命令介面視窗，並輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ea983-119">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="ea983-120">**在發生災害時容錯移轉集區**</span><span class="sxs-lookup"><span data-stu-id="ea983-120">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="ea983-121">在 Pool2 中的前端伺服器上輸入下列 Cmdlet，以尋找哪一個集區是中央管理伺服器的主機：</span><span class="sxs-lookup"><span data-stu-id="ea983-121">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="ea983-122">此 Cmdlet 的結果會顯示目前主控中央管理伺服器的集區。</span><span class="sxs-lookup"><span data-stu-id="ea983-122">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="ea983-123">在此程式的其餘部分中，此集區稱為 CMS \_ 集區。</span><span class="sxs-lookup"><span data-stu-id="ea983-123">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="ea983-124">使用拓撲產生器來尋找在 CMS 集區上執行之 Lync Server 的版本 \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-124">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="ea983-125">如果執行的是 Lync Server 2013，請使用下列 Cmdlet 來尋找集區1的備份組區。</span><span class="sxs-lookup"><span data-stu-id="ea983-125">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="ea983-126">讓備份 \_ 集區成為備份組區。</span><span class="sxs-lookup"><span data-stu-id="ea983-126">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="ea983-127">使用下列 Cmdlet 檢查中央管理存放區的狀態：</span><span class="sxs-lookup"><span data-stu-id="ea983-127">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="ea983-128">此 Cmdlet 應該會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 都指向 CMS 集區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-128">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="ea983-129">如果它們是空的，則中央管理伺服器無法使用，而且您必須進行容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="ea983-129">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="ea983-130">若中央管理存放區無法使用，或者中央管理存放區正在 Pool1 上執行 (也就是) 失敗的集區，則必須先容錯移轉中央管理伺服器，再進行集區容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="ea983-130">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="ea983-131">如果您需要容錯移轉位於執行 Lync Server 2013 之集區上的中央管理伺服器，請使用此程式步驟5的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea983-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="ea983-132">如果您需要容錯移轉位於執行 Lync Server 2010 之集區上的中央管理伺服器，請在此程式的步驟6中使用 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea983-132">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="ea983-133">如果您不需要透過中央管理伺服器進行容錯移轉，請跳至此程式的步驟7。</span><span class="sxs-lookup"><span data-stu-id="ea983-133">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="ea983-134">若要在執行 Lync Server 2013 的集區上容錯移轉中央管理存放區，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ea983-134">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="ea983-135">首先，請輸入下列命令，檢查備份組區中的哪一部後端伺服器 \_ 執行中央管理存放區的主體實例：</span><span class="sxs-lookup"><span data-stu-id="ea983-135">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="ea983-136">如果備份組區中的主要後端伺服器 \_ 是主體，請輸入：</span><span class="sxs-lookup"><span data-stu-id="ea983-136">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="ea983-137">如果備份組區中的鏡像後端伺服器 \_ 是主體，請輸入：</span><span class="sxs-lookup"><span data-stu-id="ea983-137">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="ea983-138">驗證中央管理伺服器容錯移轉是否已完成。</span><span class="sxs-lookup"><span data-stu-id="ea983-138">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="ea983-139">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="ea983-139">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="ea983-140">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-140">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="ea983-141">最後，輸入下列命令，檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="ea983-141">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="ea983-142">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="ea983-142">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="ea983-143">跳到此程序的步驟 7。</span><span class="sxs-lookup"><span data-stu-id="ea983-143">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="ea983-144">在備份組區的後端伺服器上安裝中央管理存放區 \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-144">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="ea983-145">首先，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ea983-145">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="ea983-146">在其中一個備份組區的前端伺服器上執行下一個命令 \_ ，以強制移動中央管理存放區：</span><span class="sxs-lookup"><span data-stu-id="ea983-146">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="ea983-147">驗證移動完成：</span><span class="sxs-lookup"><span data-stu-id="ea983-147">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="ea983-148">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 是否都指向備份組區的 FQDN \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-148">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="ea983-149">輸入下列命令，檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="ea983-149">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="ea983-150">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="ea983-150">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="ea983-151">在備份組區中的其他前端伺服器上安裝中央管理伺服器服務 \_ 。</span><span class="sxs-lookup"><span data-stu-id="ea983-151">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="ea983-152">若要這麼做，請在所有前端伺服器上執行下列命令，除了強制您在此程式中強制執行中央管理存放區時所使用的伺服器之外：</span><span class="sxs-lookup"><span data-stu-id="ea983-152">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="ea983-153">在 Lync Server 管理命令介面視窗中執行下列 Cmdlet，將使用者從 Pool1 容錯移轉至 Pool2：</span><span class="sxs-lookup"><span data-stu-id="ea983-153">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="ea983-154">因為在此程式的先前部分中，檢查中央管理存放區狀態所採取的步驟並不是通用的，所以此 Cmdlet 仍然會失敗，因為中央管理存放區尚未完全容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="ea983-154">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="ea983-155">在此情況下，您必須根據所看到的錯誤訊息修正中央管理存放區，然後再次執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ea983-155">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="ea983-p112">如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。</span><span class="sxs-lookup"><span data-stu-id="ea983-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
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

