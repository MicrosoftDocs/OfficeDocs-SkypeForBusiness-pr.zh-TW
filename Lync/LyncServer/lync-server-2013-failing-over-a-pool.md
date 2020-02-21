---
title: Lync Server 2013： 容錯移轉集區
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
ms.openlocfilehash: 93f6aadd6cde7f09d7c6bdde118055cde8a56de5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-pool-in-lync-server-2013"></a><span data-ttu-id="3fc60-102">容錯移轉集區中 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3fc60-102">Failing over a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fc60-103">_**上次修改主題：** 2014年-10-10_</span><span class="sxs-lookup"><span data-stu-id="3fc60-103">_**Topic Last Modified:** 2014-10-10_</span></span>

<span data-ttu-id="3fc60-p101">如果單一前端集區失敗，而需要容錯移轉，請使用下列程序。在此程序中，Datacenter1 包含 Pool1，而 Pool1 失敗了。您要容錯移轉至位在 Datacenter2 的 Pool2。</span><span class="sxs-lookup"><span data-stu-id="3fc60-p101">If a single Front End pool has failed and needs to be failed over, use the following procedure. In this procedure, Datacenter1 contains Pool1, and Pool1 has failed. You are failing over to Pool2 located in Datacenter2.</span></span>

<span data-ttu-id="3fc60-107">大部分的集區容錯移轉的工作牽涉到容錯移轉的中央管理存放區中，如果需要的話。</span><span class="sxs-lookup"><span data-stu-id="3fc60-107">Most of the work for the pool failover involves failing over the Central Management store, if it is required.</span></span> <span data-ttu-id="3fc60-108">這是很重要，因為當集區的使用者容錯移轉時，中央管理存放區必須在正常運作。</span><span class="sxs-lookup"><span data-stu-id="3fc60-108">This is important because the Central Management store must be functional when the pool’s users are failed over.</span></span>

<span data-ttu-id="3fc60-p103">此外，如果前端集區失敗，但位在該網站的 Edge 集區仍在執行中，您就必須知道 Edge 集區是否使用失敗的集區作為下一個躍點集區。如果是，則必須先變更 Edge 集區為使用不同的前端集區，再容錯移轉至失敗的前端集區。變更下一個躍點設定的方式，取決於 Edge 將要使用的集區是位在與 Edge 集區相同的網站，還是不同網站。</span><span class="sxs-lookup"><span data-stu-id="3fc60-p103">Additionally, if a Front End pool fails but the Edge pool at that site is still running, you must know whether the Edge pool uses the failed pool as a next hop pool. If it does, you must change the Edge pool to use a different Front End pool before failing over the failed Front End pool. How you change the next hop setting depends on whether the Edge will use a pool at the same site as the Edge pool, or a different site.</span></span>

<span data-ttu-id="3fc60-112">**將 Edge 集區設定為使用位在相同網站的下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="3fc60-112">**To Set an Edge Pool to Use a Next Hop Pool at the Same Site**</span></span>

1.  <span data-ttu-id="3fc60-113">開啟拓撲產生器，以滑鼠右鍵按一下 Edge 集區，必須變更，並按一下 [**編輯內容]**。</span><span class="sxs-lookup"><span data-stu-id="3fc60-113">Open Topology Builder, right-click the Edge pool that needs to be changed, and click **Edit Properties**.</span></span>

2.  <span data-ttu-id="3fc60-p104">按 [下一個躍點]\*\*\*\*。從 [下一個躍點集區:]\*\*\*\* 清單中，選取現在要作為下一個躍點集區的集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-p104">Click **Next Hop**. From the **Next hop pool:** list, select the pool which will now serve as the next hop pool.</span></span>

3.  <span data-ttu-id="3fc60-116">按一下 [確定]\*\*\*\*，然後發行變更。</span><span class="sxs-lookup"><span data-stu-id="3fc60-116">Click **OK**, and then publish the changes.</span></span>

<span data-ttu-id="3fc60-117">**將 Edge 集區設定為使用位在不同網站的下一個躍點集區**</span><span class="sxs-lookup"><span data-stu-id="3fc60-117">**To Set an Edge Pool to Use a Next Hop Pool at a Different Site**</span></span>

1.  <span data-ttu-id="3fc60-118">開啟 Lync Server 管理命令介面視窗，並輸入下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3fc60-118">Open a Lync Server Management Shell window and type the following cmdlet:</span></span>
    
        Set-CsEdgeServer -Identity EdgeServer:<Edge Server pool FQDN> -Registrar Registrar:<NextHopPoolFQDN>

<span data-ttu-id="3fc60-119">**在發生災害時容錯移轉集區**</span><span class="sxs-lookup"><span data-stu-id="3fc60-119">**To Fail Over a Pool in a Disaster**</span></span>

1.  <span data-ttu-id="3fc60-120">找出哪個集區是中央管理伺服器的主機在 Pool2 中的前端伺服器上輸入下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3fc60-120">Find which pool is the host for the Central Management Server by typing the following cmdlet on a Front End server in Pool2:</span></span>
    
        Invoke-CsManagementServerFailover -Whatif
    
    <span data-ttu-id="3fc60-121">目前所在的集區的中央管理伺服器此指令程式顯示的結果。</span><span class="sxs-lookup"><span data-stu-id="3fc60-121">The results of this cmdlet show which pool currently hosts the Central Management Server.</span></span> <span data-ttu-id="3fc60-122">此程序的其餘部分，在此集區稱為 CMS\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-122">In the rest of this procedure, this pool is known as CMS\_Pool.</span></span>

2.  <span data-ttu-id="3fc60-123">使用拓撲產生器找到 CMS 上執行的 Lync Server 的版本\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-123">Use Topology Builder to find the version of Lync Server running on the CMS\_Pool.</span></span> <span data-ttu-id="3fc60-124">如果它執行 Lync Server 2013 中，使用下列 cmdlet 來尋找集區 1 的備份集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-124">If it is running Lync Server 2013, use the following cmdlet to find the backup pool of Pool 1.</span></span>
    
        Get-CsPoolBackupRelationship -PoolFQDN <CMS_Pool FQDN>
    
    <span data-ttu-id="3fc60-125">讓備份\_集區是備份集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-125">Let Backup\_Pool be the backup pool.</span></span>

3.  <span data-ttu-id="3fc60-126">請檢查下列 cmdlet 的中央管理存放區的狀態：</span><span class="sxs-lookup"><span data-stu-id="3fc60-126">Check the status of the Central Management store with the following cmdlet:</span></span>
    
        Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
    
    <span data-ttu-id="3fc60-127">此 cmdlet 應會顯示 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 CMS FQDN\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-127">This cmdlet should show that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of CMS\_Pool.</span></span> <span data-ttu-id="3fc60-128">如果他們是空的中央管理伺服器不提供，您必須將它容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3fc60-128">If they are empty, the Central Management Server is not available and you must fail it over.</span></span>

4.  <span data-ttu-id="3fc60-129">如果沒有可用的中央管理存放區，或 Pool1 上執行的中央管理存放區 （亦即的集區失敗），您必須對集區容錯移轉前失敗中央管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="3fc60-129">If the Central Management store is not available or if the Central Management store was running on Pool1 (that is, the pool that has failed), you must fail over the Central Management Server before failing over the pool.</span></span> <span data-ttu-id="3fc60-130">如果您需要容錯移轉中央管理伺服器所架設在執行 Lync Server 2013 的集區上，請在此程序的步驟 5 中使用指令程式。</span><span class="sxs-lookup"><span data-stu-id="3fc60-130">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2013, use the cmdlet in step 5 of this procedure.</span></span> <span data-ttu-id="3fc60-131">如果您需要容錯移轉中央管理伺服器所架設在執行 Lync Server 2010 集區上，請在此程序的步驟 6 中使用指令程式。</span><span class="sxs-lookup"><span data-stu-id="3fc60-131">If you need to fail over the Central Management Server that was hosted on a pool running Lync Server 2010, use the cmdlet in step 6 of this procedure.</span></span> <span data-ttu-id="3fc60-132">如果您不需要容錯移轉中央管理伺服器，請跳到此程序的步驟 7。</span><span class="sxs-lookup"><span data-stu-id="3fc60-132">If you do not need to fail over the Central Management Server, skip to step 7 of this procedure.</span></span>

5.  <span data-ttu-id="3fc60-133">若要容錯移轉執行 Lync Server 2013 的集區上的中央管理存放區，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3fc60-133">To fail over the Central Management store on a pool running Lync Server 2013, do the following:</span></span>
    
      - <span data-ttu-id="3fc60-134">首先，檢查哪些中後端伺服器備份\_集區執行中央管理存放區的主體執行個體輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fc60-134">First, check which Back End Server in Backup\_Pool runs the principal instance of the Central Management store by typing the following:</span></span>
        
            Get-CsDatabaseMirrorState -DatabaseType Centralmgmt -PoolFqdn <Backup_Pool Fqdn>
    
      - <span data-ttu-id="3fc60-135">如果主要後端伺服器在備份\_集區是主體，類型：</span><span class="sxs-lookup"><span data-stu-id="3fc60-135">If the primary Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -BackupSQLServerFqdn <Backup_Pool Primary BackEnd Server FQDN> -BackupSQLInstanceName <Backup_Pool Primary SQL Instance Name>
        
        <span data-ttu-id="3fc60-136">如果鏡像後端伺服器在備份\_集區是主體，類型：</span><span class="sxs-lookup"><span data-stu-id="3fc60-136">If the mirror Back End Server in Backup\_Pool is the principal, type:</span></span>
        
            Invoke-CSManagementServerFailover -MirrorSQLServerFqdn <Backup_Pool Mirror BackEnd Server FQDN> -MirrorSQLInstanceName <Backup_Pool Mirror SQL Instance Name>
    
      - <span data-ttu-id="3fc60-137">驗證過的中央管理伺服器容錯移轉已完成。</span><span class="sxs-lookup"><span data-stu-id="3fc60-137">Validate that the Central Management Server failover is complete.</span></span> <span data-ttu-id="3fc60-138">輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fc60-138">Type the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3fc60-139">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 FQDN 的備份\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-139">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3fc60-140">最後，檢查所有前端伺服器的複本狀態輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fc60-140">Finally, check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3fc60-141">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="3fc60-141">Check that all replicas have a value of True.</span></span>
        
        <span data-ttu-id="3fc60-142">跳到此程序的步驟 7。</span><span class="sxs-lookup"><span data-stu-id="3fc60-142">Skip to step 7 in this procedure.</span></span>

6.  <span data-ttu-id="3fc60-143">在後端伺服器的備份上安裝中央管理存放區\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-143">Install the Central Management store on the Back End Server of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3fc60-144">首先，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3fc60-144">First, run the following command:</span></span>
        
        ```PowerShell 
        Install-CsDatabase -CentralManagementDatabase -Clean -SqlServerFqdn <Backup_Pool Back End Server FQDN> -SqlInstanceName rtc  
        ```
    
      - <span data-ttu-id="3fc60-145">執行下一個命令上的 Front End 伺服器備份的其中一個\_以強制移動中央管理存放區的集區：</span><span class="sxs-lookup"><span data-stu-id="3fc60-145">Run the next command on one of the Front End Servers of Backup\_Pool to force the move of the Central Management store:</span></span>
        
            Move-CsManagementServer -ConfigurationFileName c:\CsConfigurationFile.zip -LisConfigurationFileName c:\CsLisConfigurationFile.zip -Force 
    
      - <span data-ttu-id="3fc60-146">驗證移動完成：</span><span class="sxs-lookup"><span data-stu-id="3fc60-146">Validate the move is complete:</span></span>
        
            Get-CsManagementStoreReplicationStatus -CentralManagementStoreStatus 
        
        <span data-ttu-id="3fc60-147">檢查 ActiveMasterFQDN 和 ActiveFileTransferAgents 指向 FQDN 的備份\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-147">Check that both ActiveMasterFQDN and ActiveFileTransferAgents are pointing to the FQDN of Backup\_Pool.</span></span>
    
      - <span data-ttu-id="3fc60-148">輸入下列命令，檢查所有前端伺服器的複本狀態：</span><span class="sxs-lookup"><span data-stu-id="3fc60-148">Check the replica status for all Front End Servers by typing the following:</span></span>
        
            Get-CsManagementStoreReplicationStatus 
        
        <span data-ttu-id="3fc60-149">檢查所有複本的值為 True。</span><span class="sxs-lookup"><span data-stu-id="3fc60-149">Check that all replicas have a value of True.</span></span>
    
      - <span data-ttu-id="3fc60-150">在其餘的備份中前端伺服器上安裝中央管理伺服器服務\_集區。</span><span class="sxs-lookup"><span data-stu-id="3fc60-150">Install the Central Management Server service on the rest of the Front End Servers in Backup\_Pool.</span></span> <span data-ttu-id="3fc60-151">若要這麼做，請在所有前端伺服器上執行下列命令，那一時強制中央管理存放區移動稍早在此程序：</span><span class="sxs-lookup"><span data-stu-id="3fc60-151">To do so, run the following command on all the Front End Servers, except the one you used when forcing the Central Management store move earlier in this procedure:</span></span>
        
            Bootstrapper /Setup 

7.  <span data-ttu-id="3fc60-152">容錯移轉至 Pool2 的使用者從 Pool1 Lync Server 管理命令介面] 視窗中執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="3fc60-152">Fail over the users from Pool1 to Pool2 by running the following cmdlet in a Lync Server Management Shell window:</span></span>
    
        Invoke-CsPoolFailover -PoolFQDN <Pool1 FQDN> -DisasterMode -Verbose
    
    <span data-ttu-id="3fc60-153">若要檢查的中央管理存放區狀態採取此程序的前一組件中的步驟不是通用的因為仍有的機會，此 cmdlet 會失敗，因為中央管理存放區不尚未完全容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="3fc60-153">Because the steps taken in the previous parts of this procedure to check the Central Management store status are not universal, there is still a chance this cmdlet will fail because the Central Management store is not yet fully failed over.</span></span> <span data-ttu-id="3fc60-154">在此情況下，您必須修正您看到錯誤訊息為基礎的中央管理存放區，然後再次執行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3fc60-154">In this case, you must fix the Central Management store based on the error messages that you see, and then run this cmdlet again.</span></span>
    
    <span data-ttu-id="3fc60-p112">如果您看到下列錯誤訊息，則需要先變更位在此網站的 Edge 集區，以使用不同集區作為其下一個躍點，再容錯移轉集區。如需詳細資訊，請參閱本主題一開始的程序。</span><span class="sxs-lookup"><span data-stu-id="3fc60-p112">If you see the following error message, then you need to change the Edge pool at this site to use a different pool as its next hop before failing over the pool. For details, see the procedures at the beginning of this topic.</span></span>
    
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

