---
title: 商務用 Skype Server 的後端伺服器高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 瞭解商務用 Skype Server 支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像，以及 SQL 容錯移轉叢集。
ms.openlocfilehash: 3a92c7ee8cbada8ce678e53e3aacff0aa562fca5
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991488"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="faba1-103">商務用 Skype Server 的後端伺服器高可用性</span><span class="sxs-lookup"><span data-stu-id="faba1-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="faba1-104">瞭解商務用 Skype Server 支援的後端伺服器高可用性選項，包括 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例、資料庫鏡像，以及 SQL 容錯移轉叢集。</span><span class="sxs-lookup"><span data-stu-id="faba1-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="faba1-105">若要提升後端伺服器的高可用性，您有四個選項：</span><span class="sxs-lookup"><span data-stu-id="faba1-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="faba1-106">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="faba1-106">Database mirroring</span></span>
    
- <span data-ttu-id="faba1-107">AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="faba1-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="faba1-108">AlwaysOn 容錯移轉叢集實例（FCI）</span><span class="sxs-lookup"><span data-stu-id="faba1-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="faba1-109">SQL 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="faba1-109">SQL failover clustering</span></span>
    
<span data-ttu-id="faba1-110">使用其中一個解決方案是選用的，但建議維持貴組織的業務連續性。</span><span class="sxs-lookup"><span data-stu-id="faba1-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="faba1-111">否則，只有單一資料庫伺服器會出現問題，才能導致大量的商務用 Skype 伺服器資料遺失。</span><span class="sxs-lookup"><span data-stu-id="faba1-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="faba1-112">您可以使用 [拓撲產生器] 來設定資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="faba1-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="faba1-113">針對 AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例或 SQL 容錯移轉叢集，您可以使用 SQL Server 建立高可用性方案，然後您就可以使用拓撲產生器將它與前端池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="faba1-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="faba1-114">如果您在與其他用於災難復原的前端池搭配使用後端伺服器高可用性，您應該在兩個池中使用相同的後端高可用性方案。</span><span class="sxs-lookup"><span data-stu-id="faba1-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="faba1-115">資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="faba1-115">Database mirroring</span></span>

<span data-ttu-id="faba1-116">商務用 Skype 伺服器支援使用下列資料庫軟體進行鏡像：</span><span class="sxs-lookup"><span data-stu-id="faba1-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="faba1-117">SQL Server 2019 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-118">SQL Server 2017 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-119">SQL Server 2016 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-120">SQL Server 2014 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="faba1-121">SQL Server 2012 SP2 與 CU2 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="faba1-122">在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="faba1-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="faba1-123">使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。</span><span class="sxs-lookup"><span data-stu-id="faba1-123">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="faba1-124">商務用 Skype Server 的後端伺服器高可用性不支援非同步資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="faba1-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="faba1-125">在本檔的其餘部分中，資料庫鏡像代表同步資料庫鏡像，除非明確指出。</span><span class="sxs-lookup"><span data-stu-id="faba1-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="faba1-126">當您在前臺文件庫中部署資料庫鏡像時，會對池中的所有商務用 Skype 伺服器資料庫進行鏡像，包括中央管理儲存體（如果它位於此池中），以及回應群組應用程式資料庫及通話駐留應用程式資料庫（如果那些應用程式正在池中執行）。</span><span class="sxs-lookup"><span data-stu-id="faba1-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="faba1-127">使用資料庫鏡像，您不需要針對伺服器使用共用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="faba1-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="faba1-128">每個伺服器都會在本機儲存空間中保留自己的資料庫複本。</span><span class="sxs-lookup"><span data-stu-id="faba1-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="faba1-129">您可以選擇部署含或不含見證的資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="faba1-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="faba1-130">我們建議使用見證，因為它可讓後端伺服器的容錯移轉自動進行。</span><span class="sxs-lookup"><span data-stu-id="faba1-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="faba1-131">否則，系統管理員必須手動喚醒呼叫容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="faba1-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="faba1-132">請注意，即使已部署見證，系統管理員也可以在必要時手動呼叫後端伺服器容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="faba1-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="faba1-133">如果您使用見證，您可以針對多對後端伺服器使用單一見證。</span><span class="sxs-lookup"><span data-stu-id="faba1-133">If you use a witness, you can use a single witness for multiple pairs of Back End Servers.</span></span> <span data-ttu-id="faba1-134">Witnesses 和對後端伺服器之間沒有嚴格的1:1 對應。</span><span class="sxs-lookup"><span data-stu-id="faba1-134">There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers.</span></span> <span data-ttu-id="faba1-135">針對多對後端伺服器使用單一見證伺服器的部署，不具彈性，因為每個後端伺服器對都有單獨的見證。</span><span class="sxs-lookup"><span data-stu-id="faba1-135">Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="faba1-136">規劃後端伺服器鏡像的指導方針</span><span class="sxs-lookup"><span data-stu-id="faba1-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="faba1-137">一般來說，在具有見證的兩台後端伺服器之間設定 SQL 鏡像需要下列事項：</span><span class="sxs-lookup"><span data-stu-id="faba1-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="faba1-138">主伺服器版本的 SQL Server 必須支援 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="faba1-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="faba1-139">[主要]、[鏡像] 和 [見證伺服器] （如果已部署）必須有相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="faba1-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="faba1-140">主要和鏡像必須擁有相同版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="faba1-140">The primary and the mirror must have the same edition of SQL Server.</span></span> <span data-ttu-id="faba1-141">見證可能會有不同的版本。</span><span class="sxs-lookup"><span data-stu-id="faba1-141">The witness may have a different edition.</span></span>
    
<span data-ttu-id="faba1-142">如需針對見證角色支援哪些 SQL 版本的 SQL 最佳做法，請參閱 MSDN 文件庫中的「[資料庫鏡像見證](https://go.microsoft.com/fwlink/p/?LinkId=247345)」。</span><span class="sxs-lookup"><span data-stu-id="faba1-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="faba1-143">在佈建服務器鏡像之前，您必須先正確設定 SQL 資料庫許可權。</span><span class="sxs-lookup"><span data-stu-id="faba1-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="faba1-144">如需詳細資訊，請參閱[設定資料庫鏡像或 AlwaysOn 可用性群組的登入帳戶（SQL Server）](https://go.microsoft.com/fwlink/p/?LinkId=268454)」。</span><span class="sxs-lookup"><span data-stu-id="faba1-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="faba1-145">有了 SQL 鏡像，資料庫復原模式永遠都設為**Full**，這表示您必須密切監視事務日誌大小，並定期備份事務日誌，以免在後端伺服器上耗盡磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="faba1-145">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers.</span></span> <span data-ttu-id="faba1-146">事務記錄備份的頻率取決於記錄的增長率，而這取決於前端池中使用者活動所產生的資料庫事務。</span><span class="sxs-lookup"><span data-stu-id="faba1-146">The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool.</span></span> <span data-ttu-id="faba1-147">我們建議您決定 Lync 部署工作負載預期的事務日誌增長量，讓您可以據此進行規劃。</span><span class="sxs-lookup"><span data-stu-id="faba1-147">We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly.</span></span> <span data-ttu-id="faba1-148">下列文章提供有關 SQL 備份與記錄管理的其他資訊：</span><span class="sxs-lookup"><span data-stu-id="faba1-148">The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="faba1-149">只有在主要、鏡像和見證（如果需要）伺服器都屬於同一個網域時，才支援使用拓撲建立器或 Cmdlet 來設定及移除 SQL 鏡像。</span><span class="sxs-lookup"><span data-stu-id="faba1-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="faba1-150">如果您想要在不同網域中的伺服器之間設定 SQL 鏡像，請參閱您的 SQL Server 檔。</span><span class="sxs-lookup"><span data-stu-id="faba1-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="faba1-151">在商務用 Skype Server 2015 中提供 SQL 鏡像，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="faba1-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="faba1-152">使用商務用 Skype Server 2019 時，AlwaysOn 可用性群組、AlwaysOn 容錯移轉叢集實例（FCI）和 SQL 容錯移轉叢集方法都是可取的。</span><span class="sxs-lookup"><span data-stu-id="faba1-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="faba1-153">自動後端伺服器容錯移轉與資料庫鏡像的恢復時間</span><span class="sxs-lookup"><span data-stu-id="faba1-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="faba1-154">針對資料庫鏡像的自動後端容錯移轉，「恢復時間目標」工程目標（RTO）是5分鐘。</span><span class="sxs-lookup"><span data-stu-id="faba1-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="faba1-155">由於同步處理資料庫鏡像，我們不會在回退端伺服器失敗期間預計資料遺失，除非當前端伺服器和後端伺服器在伺服器間移動資料時，在一般情況下，不會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="faba1-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="faba1-156">針對復原點目標（RPO）的工程目標是5分鐘。</span><span class="sxs-lookup"><span data-stu-id="faba1-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="faba1-157">在後端伺服器失敗時使用資料庫鏡像的使用者體驗</span><span class="sxs-lookup"><span data-stu-id="faba1-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="faba1-158">故障期間的使用者體驗取決於失敗的性質，以及拓撲。</span><span class="sxs-lookup"><span data-stu-id="faba1-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="faba1-159">如果您使用資料庫鏡像且已設定見證伺服器，則主體會失敗，後端伺服器容錯移轉會自動及快速進行。</span><span class="sxs-lookup"><span data-stu-id="faba1-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="faba1-160">作用中的使用者不應該注意到他們的日常會話會有太大的中斷。</span><span class="sxs-lookup"><span data-stu-id="faba1-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="faba1-161">如果沒有設定見證，系統會在管理員手動呼叫容錯移轉時需要一些時間。</span><span class="sxs-lookup"><span data-stu-id="faba1-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="faba1-162">在這段時間內，作用中的使用者可能會受到影響。</span><span class="sxs-lookup"><span data-stu-id="faba1-162">During that time, active users may be affected.</span></span> <span data-ttu-id="faba1-163">它們會在大約30分鐘內繼續正常的會話。</span><span class="sxs-lookup"><span data-stu-id="faba1-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="faba1-164">如果主版仍未還原，或系統管理員沒有失敗轉移至備份，則使用者會切換到復原模式，這表示他們無法執行需要 Lync 伺服器上的永久變更的工作（例如新增連絡人）。</span><span class="sxs-lookup"><span data-stu-id="faba1-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="faba1-165">如果主體和鏡像後端伺服器失敗，或其中一個伺服器與見證伺服器發生故障，後端伺服器將變為無法使用（即使是仍在運作的主體）。</span><span class="sxs-lookup"><span data-stu-id="faba1-165">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working).</span></span> <span data-ttu-id="faba1-166">在這種情況下，作用中的使用者會在一段時間後切換為復原模式。</span><span class="sxs-lookup"><span data-stu-id="faba1-166">In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="faba1-167">AlwaysOn 可用性群組與 AlwaysOn 容錯移轉叢集實例</span><span class="sxs-lookup"><span data-stu-id="faba1-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="faba1-168">商務用 Skype 伺服器支援 AlwaysOn 可用性群組，只能作為主動/被動群組，非作用中/作用中。</span><span class="sxs-lookup"><span data-stu-id="faba1-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="faba1-169">若要使用 AlwaysOn 可用性群組或 AlwaysOn 容錯移轉叢集實例，您必須先使用 SQL Server 來設定及設定高可用性方案。</span><span class="sxs-lookup"><span data-stu-id="faba1-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="faba1-170">然後，您就可以使用 [拓撲建立器]，將它與 [前端] 池建立關聯。</span><span class="sxs-lookup"><span data-stu-id="faba1-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="faba1-171">商務用 Skype 伺服器支援使用下列資料庫軟體的 AlwaysOn：</span><span class="sxs-lookup"><span data-stu-id="faba1-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="faba1-172">SQL Server 2019 企業版</span><span class="sxs-lookup"><span data-stu-id="faba1-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="faba1-173">SQL Server 2019 標準版有限制，請參閱下方的注意事項</span><span class="sxs-lookup"><span data-stu-id="faba1-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="faba1-174">SQL Server 2017 企業版</span><span class="sxs-lookup"><span data-stu-id="faba1-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="faba1-175">SQL Server 2017 標準版有限制，請參閱下方的注意事項</span><span class="sxs-lookup"><span data-stu-id="faba1-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="faba1-176">SQL Server 2016 企業版</span><span class="sxs-lookup"><span data-stu-id="faba1-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="faba1-177">SQL Server 2016 標準版有限制，請參閱下方的注意事項</span><span class="sxs-lookup"><span data-stu-id="faba1-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="faba1-178">SQL Server 2014 企業版</span><span class="sxs-lookup"><span data-stu-id="faba1-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="faba1-179">SQL Server 2012 SP2 及 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="faba1-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="faba1-180">SQL Server 2019、2017和2016是商務用 Skype Server 2019 所支援的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="faba1-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="faba1-181">在 SQL 2016、2017和2019標準版中**不**支援 Alwayson 可用性群組，但您可以使用 [永不在容錯移轉叢集] 實例。</span><span class="sxs-lookup"><span data-stu-id="faba1-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="faba1-182">若要深入瞭解，請參閱[SQL Server 2016 的版本和支援的功能](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)。</span><span class="sxs-lookup"><span data-stu-id="faba1-182">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="faba1-183">多個 AlwaysOn 可用性群組實例的實例名稱必須相同。</span><span class="sxs-lookup"><span data-stu-id="faba1-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="faba1-184">如需部署 AlwaysOn 可用性群組的步驟，請參閱[在商務用 Skype server 的後端伺服器上部署 AlwaysOn 可用性群組](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="faba1-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="faba1-185">SQL Server 容錯移轉叢集</span><span class="sxs-lookup"><span data-stu-id="faba1-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="faba1-186">商務用 Skype 伺服器支援使用下列資料庫軟體的 SQL Server 容錯移轉叢集：</span><span class="sxs-lookup"><span data-stu-id="faba1-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="faba1-187">SQL Server 2019 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-188">SQL Server 2017 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-189">SQL Server 2016 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="faba1-190">SQL Server 2014 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="faba1-191">SQL Server 2012 SP2 與 CU2 （企業版和標準版）</span><span class="sxs-lookup"><span data-stu-id="faba1-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="faba1-192">若要使用 SQL 容錯移轉叢集，您應該先設定並設定 SQL Server 群集，然後再部署您的前臺端池。</span><span class="sxs-lookup"><span data-stu-id="faba1-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="faba1-193">如需 SQL Server 2012 中容錯移轉叢集的最佳做法及設定指示[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="faba1-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="faba1-194">SQL Server 2019、2017和 SQL Server 2016 是商務用 Skype Server 2019 所支援的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="faba1-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="faba1-195">若要使用 SQL 容錯移轉叢集，您應該先設定並設定 SQL Server 群集，然後再部署您的前臺端池。</span><span class="sxs-lookup"><span data-stu-id="faba1-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="faba1-196">如需 SQL Server 2014 和2016中容錯移轉叢集的最佳做法及設定指示[https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="faba1-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](https://technet.microsoft.com/library/hh231721.aspx).</span></span> <span data-ttu-id="faba1-197">針對 SQL Server 2008 中的容錯移轉叢集[https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx)，請參閱。</span><span class="sxs-lookup"><span data-stu-id="faba1-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="faba1-198">當您安裝 SQL Server 時，您應該安裝 SQL Server Management Studio 來管理資料庫及記錄檔位置的位置。</span><span class="sxs-lookup"><span data-stu-id="faba1-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="faba1-199">當您安裝 SQL Server 時，系統會將 SQL Server Management Studio 作為選用元件進行安裝。</span><span class="sxs-lookup"><span data-stu-id="faba1-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  
