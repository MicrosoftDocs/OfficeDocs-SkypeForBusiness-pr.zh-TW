---
title: 商務用 Skype Server 中的後端伺服器高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 深入瞭解商務用 Skype Server 中支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像及 SQL 容錯移轉叢集。
ms.openlocfilehash: bbb55ded0d5ce1127f5dcab829907c533cc6316e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802923"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="f29cc-103">商務用 Skype Server 中的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="f29cc-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="f29cc-104">深入瞭解商務用 Skype Server 中支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="f29cc-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="f29cc-105">為增強後端伺服器的高可用性，您有四個選項：</span><span class="sxs-lookup"><span data-stu-id="f29cc-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="f29cc-106">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="f29cc-106">Database mirroring</span></span>
    
- <span data-ttu-id="f29cc-107">AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="f29cc-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="f29cc-108">AlwaysOn (FCI 的容錯移轉叢集實例) </span><span class="sxs-lookup"><span data-stu-id="f29cc-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="f29cc-109">SQL 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="f29cc-109">SQL failover clustering</span></span>
    
<span data-ttu-id="f29cc-110">使用其中一種解決方案是選用的，但建議維護貴組織的業務持續性。</span><span class="sxs-lookup"><span data-stu-id="f29cc-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="f29cc-111">否則，擁有單一資料庫伺服器會導致大量商務用 Skype Server 資料遺失。</span><span class="sxs-lookup"><span data-stu-id="f29cc-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="f29cc-112">您可以使用 [拓撲產生器] 來設定資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="f29cc-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="f29cc-113">針對 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例或 SQL 容錯移轉叢集，您可以使用 SQL Server 建立高可用性解決方案，然後您就可以使用拓撲產生器，將其與前端集區建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f29cc-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="f29cc-114">如果您在與另一個前端集區配對的前端集區上使用後端伺服器高可用性，以進行嚴重損壞修復，您應該在兩個集區中使用相同的後端高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="f29cc-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="f29cc-115">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="f29cc-115">Database mirroring</span></span>

<span data-ttu-id="f29cc-116">商務用 Skype 伺服器支援鏡像下列資料庫軟體：</span><span class="sxs-lookup"><span data-stu-id="f29cc-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="f29cc-117">SQL Server 2019，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-118">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-119">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-120">SQL Server 2014，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="f29cc-121">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="f29cc-122">在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="f29cc-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f29cc-123">AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) 及 SQL 容錯移轉叢集方法是商務用 Skype Server 2019 唯一支援的選項。</span><span class="sxs-lookup"><span data-stu-id="f29cc-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="f29cc-124">商務用 Skype Server 中的後端伺服器高可用性不支援非同步資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="f29cc-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="f29cc-125">在本文的其餘部分中，資料庫鏡像是指同步資料庫鏡像，除非明確指出。</span><span class="sxs-lookup"><span data-stu-id="f29cc-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="f29cc-126">當您在前端集區中部署資料庫鏡像時，集區中的所有商務用 Skype Server 資料庫都會進行鏡像，包括中央管理存放區（如果位於此集區中）以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果集區中執行這些應用程式）。</span><span class="sxs-lookup"><span data-stu-id="f29cc-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="f29cc-127">使用資料庫鏡像，您不需要使用伺服器的共用儲存區。</span><span class="sxs-lookup"><span data-stu-id="f29cc-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="f29cc-128">每一部伺服器都會在本機儲存區中保留其資料庫複本。</span><span class="sxs-lookup"><span data-stu-id="f29cc-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="f29cc-129">您可以選擇使用或不使用見證來部署資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="f29cc-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="f29cc-130">我們建議使用見證，因為它可讓後端伺服器的容錯移轉成為自動。</span><span class="sxs-lookup"><span data-stu-id="f29cc-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="f29cc-131">否則，管理員必須手動呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="f29cc-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="f29cc-132">請注意，即使部署見證，管理員也可以手動叫用後端伺服器容錯移轉（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="f29cc-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="f29cc-133">如果您使用見證，您可以對多組的後端伺服器使用單一見證。</span><span class="sxs-lookup"><span data-stu-id="f29cc-133">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="f29cc-134">Witnesses 和後端伺服器對之間沒有嚴格的1:1 對應。</span><span class="sxs-lookup"><span data-stu-id="f29cc-134">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="f29cc-135">對多對後端伺服器使用單一見證的部署，並不像拓撲搭配每一組後端伺服器對具有個別的見證。</span><span class="sxs-lookup"><span data-stu-id="f29cc-135">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="f29cc-136">規劃後端伺服器鏡像的指導方針</span><span class="sxs-lookup"><span data-stu-id="f29cc-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="f29cc-137">一般而言，使用見證伺服器在兩個後端伺服器間設定 SQL 鏡像，需要下列各項：</span><span class="sxs-lookup"><span data-stu-id="f29cc-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="f29cc-138">主伺服器的 SQL Server 版本必須支援 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f29cc-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="f29cc-139">主要、鏡像與見證伺服器 (若已部署) 必須具有相同的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="f29cc-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="f29cc-p108">主要與鏡像伺服器必須具有相同的 SQL Server 版本，見證伺服器可能有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="f29cc-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="f29cc-142">如需有關見證角色支援哪些 SQL 版本的 SQL 最佳作法，請參閱 MSDN Library 中的「  [資料庫鏡像見證](https://go.microsoft.com/fwlink/p/?LinkId=247345) 」。</span><span class="sxs-lookup"><span data-stu-id="f29cc-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="f29cc-143">設定伺服器鏡像之前，必須先正確設定 SQL 資料庫許可權。</span><span class="sxs-lookup"><span data-stu-id="f29cc-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="f29cc-144">如需詳細資訊，請參閱  [設定資料庫鏡像的登入帳戶或 AlwaysOn 可用性群組 (SQL Server) ]](https://go.microsoft.com/fwlink/p/?LinkId=268454)。</span><span class="sxs-lookup"><span data-stu-id="f29cc-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="f29cc-p110">有了 SQL 鏡像，資料庫復原模式會一律設為 **[完整]**，這表示您必須密切監控交易紀錄的大小並定期備份交易紀錄，以避免用盡後端伺服器上的磁碟機空間。交易記錄的備份頻率取決於記錄的成長率，即根據使用者在前端集區上活動所發生的資料庫交易。建議您針對 Lync 部署工作負載判斷交易記錄的預期成長率，以便進行相應的規劃。下列文章提供 SQL 備份以及記錄管理的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="f29cc-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f29cc-149">只有當主要、鏡像及)  (見證伺服器都屬於相同的網域時，才支援使用拓撲產生器或 Cmdlet 來設定及移除 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="f29cc-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="f29cc-150">若要在不同網域的伺服器間設定 SQL 鏡像，請參閱 SQL Server 文件。</span><span class="sxs-lookup"><span data-stu-id="f29cc-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="f29cc-151">在商務用 Skype 2015 Server 中可使用 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="f29cc-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f29cc-152">AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例 (FCI) ，以及使用商務用 Skype Server 2019 的首選 SQL 容錯移轉叢集方法。</span><span class="sxs-lookup"><span data-stu-id="f29cc-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="f29cc-153">使用資料庫鏡像的自動後端伺服器容錯移轉的復原時間</span><span class="sxs-lookup"><span data-stu-id="f29cc-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="f29cc-154">若要使用資料庫鏡像進行自動後端容錯移轉，恢復時間目標的工程目標 (RTO) 為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="f29cc-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="f29cc-155">由於同步資料庫鏡像，在後端伺服器失敗的情況下，不會預見到資料遺失，但在伺服器間移動資料時，一般情況下，當前端伺服器和後端伺服器都同時停機時，並不會發生很少的情況。</span><span class="sxs-lookup"><span data-stu-id="f29cc-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="f29cc-156">復原點目標的工程目標 (RPO) 為5分鐘。</span><span class="sxs-lookup"><span data-stu-id="f29cc-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="f29cc-157">使用資料庫鏡像的後端伺服器失敗期間的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="f29cc-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="f29cc-158">失敗期間的使用者經驗取決於失敗的性質和拓撲。</span><span class="sxs-lookup"><span data-stu-id="f29cc-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="f29cc-159">如果您使用資料庫鏡像並已設定見證，但主體失敗，則後端伺服器容錯移轉會自動且快速地進行。</span><span class="sxs-lookup"><span data-stu-id="f29cc-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="f29cc-160">作用中使用者應該不會注意到其持續進行的會話中斷很大的狀態。</span><span class="sxs-lookup"><span data-stu-id="f29cc-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="f29cc-161">若未設定見證，系統管理員必須花一些時間來手動呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="f29cc-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="f29cc-162">在這段時間內，作用中的使用者可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="f29cc-162">During that time, active users may be affected.</span></span> <span data-ttu-id="f29cc-163">他們會將其會話繼續正常等候30分鐘。</span><span class="sxs-lookup"><span data-stu-id="f29cc-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="f29cc-164">若主伺服器仍未還原，或系統管理員尚未容錯移轉至備份，使用者會切換至復原模式，也就是說，他們無法執行在 Lync Server (（例如新增連絡人) ）上需要持續變更的工作。</span><span class="sxs-lookup"><span data-stu-id="f29cc-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="f29cc-165">如果主體和鏡像的後端伺服器失敗，或其中一個伺服器和見證失敗，則即使是仍在運作) 主體，後端伺服器也會無法使用 (。</span><span class="sxs-lookup"><span data-stu-id="f29cc-165">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="f29cc-166">在此情況下，作用中的使用者會在一段時間後切換至復原模式。</span><span class="sxs-lookup"><span data-stu-id="f29cc-166">In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="f29cc-167">AlwaysOn 可用性群組和 AlwaysOn 容錯移轉叢集實例</span><span class="sxs-lookup"><span data-stu-id="f29cc-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="f29cc-168">商務用 Skype 伺服器僅支援 AlwaysOn 可用性群組為主動/被動，非主動/主動。</span><span class="sxs-lookup"><span data-stu-id="f29cc-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="f29cc-169">若要使用 AlwaysOn 可用性群組或 AlwaysOn 容錯移轉叢集實例，您必須先使用 SQL Server 來設定及設定高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="f29cc-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="f29cc-170">然後您就可以使用拓撲產生器，將它與前端集區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="f29cc-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="f29cc-171">商務用 Skype Server 支援下列資料庫軟體的 AlwaysOn：</span><span class="sxs-lookup"><span data-stu-id="f29cc-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="f29cc-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="f29cc-173">SQL Server 2019 Standard Edition 具有限制，請參閱以下附注</span><span class="sxs-lookup"><span data-stu-id="f29cc-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="f29cc-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="f29cc-175">SQL Server 2017 Standard Edition 具有限制，請參閱以下附注</span><span class="sxs-lookup"><span data-stu-id="f29cc-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="f29cc-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="f29cc-177">SQL Server 2016 Standard Edition 具有限制，請參閱以下附注</span><span class="sxs-lookup"><span data-stu-id="f29cc-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="f29cc-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="f29cc-179">SQL Server 2012 SP2 和 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="f29cc-180">SQL Server 2019、2017及2016是商務用 Skype Server 2019 所支援的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="f29cc-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="f29cc-181">在 SQL 2016、2017及 2019 Standard Edition 中， **不** 支援 Always On 可用性群組，但您可以使用 Always On 容錯移轉叢集實例。</span><span class="sxs-lookup"><span data-stu-id="f29cc-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="f29cc-182">若要深入瞭解，請參閱 [SQL Server 2016 的版本及支援的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 。</span><span class="sxs-lookup"><span data-stu-id="f29cc-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f29cc-183">多個 AlwaysOn 可用性群組實例的實例名稱必須相同。</span><span class="sxs-lookup"><span data-stu-id="f29cc-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="f29cc-184">如需部署 AlwaysOn 可用性群組的步驟，請參閱 [在商務用 Skype server 中的後端伺服器上部署 AlwaysOn 可用性群組](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="f29cc-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="f29cc-185">SQL Server 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="f29cc-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="f29cc-186">商務用 Skype Server 支援具有下列資料庫軟體的 SQL Server 容錯移轉叢集：</span><span class="sxs-lookup"><span data-stu-id="f29cc-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="f29cc-187">SQL Server 2019，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-188">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-189">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="f29cc-190">SQL Server 2014，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="f29cc-191">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="f29cc-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="f29cc-192">若要使用 SQL 容錯移轉叢集，您應該先安裝及設定 SQL Server 叢集，再部署前端集區。</span><span class="sxs-lookup"><span data-stu-id="f29cc-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="f29cc-193">如需 SQL Server 2012 中容錯移轉叢集的最佳作法和設定指示，請參閱 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="f29cc-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="f29cc-194">SQL Server 2019、2017及 SQL Server 2016 是商務用 Skype Server 2019 所支援的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="f29cc-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="f29cc-195">若要使用 SQL 容錯移轉叢集，您應該先安裝及設定 SQL Server 叢集，再部署前端集區。</span><span class="sxs-lookup"><span data-stu-id="f29cc-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="f29cc-196">如需 SQL Server 2014 和2016中容錯移轉叢集的最佳作法和設定指示，請參閱 [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="f29cc-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="f29cc-197">如需 SQL Server 2008 中的容錯移轉叢集，請參閱 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="f29cc-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="f29cc-198">在安裝 SQL Server 時，應安裝 SQL Server Management Studio 以管理資料庫的位置與記錄檔位置。</span><span class="sxs-lookup"><span data-stu-id="f29cc-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="f29cc-199">您在安裝 SQL Server 時，可以選用性元件的形式安裝 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="f29cc-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
