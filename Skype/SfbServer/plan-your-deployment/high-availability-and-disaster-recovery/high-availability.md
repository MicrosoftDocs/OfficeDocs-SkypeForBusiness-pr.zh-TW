---
title: 前端池高可用性與管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 瞭解商務用 Skype Server 中的前端池管理, 包括管理池、仲裁損失, 以及僅有兩個前端伺服器的池之特殊步驟。
ms.openlocfilehash: 719a6099ac4bd54d82a833548b2438d0e9d8cc2d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193957"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="f1eea-103">前端池高可用性與管理</span><span class="sxs-lookup"><span data-stu-id="f1eea-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="f1eea-104">瞭解商務用 Skype Server 中的前端池管理, 包括管理池、仲裁損失, 以及僅有兩個前端伺服器的池之特殊步驟。</span><span class="sxs-lookup"><span data-stu-id="f1eea-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="f1eea-105">在商務用 Skype Server 中, 前端池的架構會使用分散式系統模型, 且每個使用者的資料在池中都保留為多達三個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool.</span></span> <span data-ttu-id="f1eea-106">我們建議您所有的企業版前端池都包含至少三個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> 
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="f1eea-107">規劃頂層端池的管理</span><span class="sxs-lookup"><span data-stu-id="f1eea-107">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="f1eea-108">商務用 Skype 伺服器使用以 Windows Fabric 為基礎的分散式系統模型。</span><span class="sxs-lookup"><span data-stu-id="f1eea-108">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="f1eea-109">在這個模型中, 每個使用者與會議的重要資料都儲存在前端池中的三個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f1eea-109">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="f1eea-110">這三個伺服器儲存特定的資料集是 calledreplicas。</span><span class="sxs-lookup"><span data-stu-id="f1eea-110">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="f1eea-111">在前端池的分散式模型中, 必須執行池伺服器的特定編號, 才能讓該池正常運作。</span><span class="sxs-lookup"><span data-stu-id="f1eea-111">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="f1eea-112">有兩種池的遺失模式。</span><span class="sxs-lookup"><span data-stu-id="f1eea-112">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="f1eea-113">路由群組層級仲裁損失, 因為特定路由群組沒有足夠的複本伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-113">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="f1eea-114">路由群組是駐留在池中的一組使用者。</span><span class="sxs-lookup"><span data-stu-id="f1eea-114">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="f1eea-115">每個路由群組在該池中都有三個複本: 一個主要複本和兩個次要複本。</span><span class="sxs-lookup"><span data-stu-id="f1eea-115">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="f1eea-116">當池中沒有足夠的種子伺服器執行時, 會導致池層級仲裁遺失。</span><span class="sxs-lookup"><span data-stu-id="f1eea-116">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="f1eea-117">路由群組層級仲裁損失</span><span class="sxs-lookup"><span data-stu-id="f1eea-117">Routing Group Level quorum loss</span></span>

<span data-ttu-id="f1eea-118">第一次開始新的前端池時, 85% 的伺服器必須正常運作, 如下表所示。</span><span class="sxs-lookup"><span data-stu-id="f1eea-118">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="f1eea-119">如果有較少的伺服器正在執行, 服務可能會停滯在起始狀態, 而且該池可能無法啟動。</span><span class="sxs-lookup"><span data-stu-id="f1eea-119">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="f1eea-120">池中的伺服器總數</span><span class="sxs-lookup"><span data-stu-id="f1eea-120">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="f1eea-121">必須執行才能第一次啟動該池的伺服器數量</span><span class="sxs-lookup"><span data-stu-id="f1eea-121">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="f1eea-122">pplx-2</span><span class="sxs-lookup"><span data-stu-id="f1eea-122">2</span></span>  <br/> |<span data-ttu-id="f1eea-123">sr-1</span><span class="sxs-lookup"><span data-stu-id="f1eea-123">1</span></span>  <br/> |
|<span data-ttu-id="f1eea-124">3</span><span class="sxs-lookup"><span data-stu-id="f1eea-124">3</span></span>  <br/> |<span data-ttu-id="f1eea-125">3</span><span class="sxs-lookup"><span data-stu-id="f1eea-125">3</span></span>  <br/> |
|<span data-ttu-id="f1eea-126">4</span><span class="sxs-lookup"><span data-stu-id="f1eea-126">4</span></span>  <br/> |<span data-ttu-id="f1eea-127">3</span><span class="sxs-lookup"><span data-stu-id="f1eea-127">3</span></span>  <br/> |
|<span data-ttu-id="f1eea-128">500</span><span class="sxs-lookup"><span data-stu-id="f1eea-128">5</span></span>  <br/> |<span data-ttu-id="f1eea-129">4</span><span class="sxs-lookup"><span data-stu-id="f1eea-129">4</span></span>  <br/> |
|<span data-ttu-id="f1eea-130">6</span><span class="sxs-lookup"><span data-stu-id="f1eea-130">6</span></span>  <br/> |<span data-ttu-id="f1eea-131">500</span><span class="sxs-lookup"><span data-stu-id="f1eea-131">5</span></span>  <br/> |
|<span data-ttu-id="f1eea-132">utf-7</span><span class="sxs-lookup"><span data-stu-id="f1eea-132">7</span></span>  <br/> |<span data-ttu-id="f1eea-133">500</span><span class="sxs-lookup"><span data-stu-id="f1eea-133">5</span></span>  <br/> |
|<span data-ttu-id="f1eea-134">型</span><span class="sxs-lookup"><span data-stu-id="f1eea-134">8</span></span>  <br/> |<span data-ttu-id="f1eea-135">6</span><span class="sxs-lookup"><span data-stu-id="f1eea-135">6</span></span>  <br/> |
|<span data-ttu-id="f1eea-136">9</span><span class="sxs-lookup"><span data-stu-id="f1eea-136">9</span></span>  <br/> |<span data-ttu-id="f1eea-137">utf-7</span><span class="sxs-lookup"><span data-stu-id="f1eea-137">7</span></span>  <br/> |
|<span data-ttu-id="f1eea-138">第</span><span class="sxs-lookup"><span data-stu-id="f1eea-138">10</span></span>  <br/> |<span data-ttu-id="f1eea-139">型</span><span class="sxs-lookup"><span data-stu-id="f1eea-139">8</span></span>  <br/> |
|<span data-ttu-id="f1eea-140">11</span><span class="sxs-lookup"><span data-stu-id="f1eea-140">11</span></span>  <br/> |<span data-ttu-id="f1eea-141">9</span><span class="sxs-lookup"><span data-stu-id="f1eea-141">9</span></span>  <br/> |
|<span data-ttu-id="f1eea-142">之間</span><span class="sxs-lookup"><span data-stu-id="f1eea-142">12</span></span>  <br/> |<span data-ttu-id="f1eea-143">第</span><span class="sxs-lookup"><span data-stu-id="f1eea-143">10</span></span>  <br/> |
   
<span data-ttu-id="f1eea-144">每次啟動該池之後, 伺服器的 85% 應該會啟動 (如前面的資料表所示)。</span><span class="sxs-lookup"><span data-stu-id="f1eea-144">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="f1eea-145">如果此伺服器數無法啟動 (但可以啟動足夠的伺服器, 因此您不是在池層級的仲裁遺失), 您可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` Cmdlet 來讓該池從路由群組層級仲裁遺失中復原, 並產生進度。</span><span class="sxs-lookup"><span data-stu-id="f1eea-145">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="f1eea-146">如需如何使用此 Cmdlet 的詳細資訊, 請<link Reset-CsPoolRegistrarState>參閱。</span><span class="sxs-lookup"><span data-stu-id="f1eea-146">For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f1eea-147">在有偶數個伺服器的 [pool] 中, 商務用 Skype 伺服器使用主要的 SQL 資料庫作為見證。</span><span class="sxs-lookup"><span data-stu-id="f1eea-147">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="f1eea-148">在像這樣的池子中, 如果您關閉主資料庫並切換到鏡像複本, 然後關閉足夠的前端伺服器, 以使其根據前面的資料表執行時, 整個池都會向下移動。</span><span class="sxs-lookup"><span data-stu-id="f1eea-148">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="f1eea-149">如需詳細資訊, 請參閱[資料庫鏡像見證](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="f1eea-149">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="f1eea-150">池層級仲裁損失</span><span class="sxs-lookup"><span data-stu-id="f1eea-150">Pool-level quorum loss</span></span>

<span data-ttu-id="f1eea-151">若要讓前臺端池完全正常運作, 它不能在 pool 階層的仲裁遺失中。</span><span class="sxs-lookup"><span data-stu-id="f1eea-151">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="f1eea-152">如果執行中的伺服器數目低於功能層級, 如下表所示, 池中剩餘的伺服器將停止所有商務用 Skype Server 服務。</span><span class="sxs-lookup"><span data-stu-id="f1eea-152">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="f1eea-153">請注意, 下表中的數位假設池中的後端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="f1eea-153">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="f1eea-154">池中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="f1eea-154">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="f1eea-155">必須執行才能供擁有池中運作的伺服器數量</span><span class="sxs-lookup"><span data-stu-id="f1eea-155">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="f1eea-156">pplx-2</span><span class="sxs-lookup"><span data-stu-id="f1eea-156">2</span></span>  <br/> |<span data-ttu-id="f1eea-157">sr-1</span><span class="sxs-lookup"><span data-stu-id="f1eea-157">1</span></span>  <br/> |
|<span data-ttu-id="f1eea-158">3-4</span><span class="sxs-lookup"><span data-stu-id="f1eea-158">3-4</span></span>  <br/> |<span data-ttu-id="f1eea-159">任何2</span><span class="sxs-lookup"><span data-stu-id="f1eea-159">Any 2</span></span>  <br/> |
|<span data-ttu-id="f1eea-160">5-6</span><span class="sxs-lookup"><span data-stu-id="f1eea-160">5-6</span></span>  <br/> |<span data-ttu-id="f1eea-161">任何3</span><span class="sxs-lookup"><span data-stu-id="f1eea-161">Any 3</span></span>  <br/> |
|<span data-ttu-id="f1eea-162">utf-7</span><span class="sxs-lookup"><span data-stu-id="f1eea-162">7</span></span>  <br/> |<span data-ttu-id="f1eea-163">任何4</span><span class="sxs-lookup"><span data-stu-id="f1eea-163">Any 4</span></span>  <br/> |
|<span data-ttu-id="f1eea-164">8-9</span><span class="sxs-lookup"><span data-stu-id="f1eea-164">8-9</span></span>  <br/> |<span data-ttu-id="f1eea-165">前7個伺服器中的任何4個</span><span class="sxs-lookup"><span data-stu-id="f1eea-165">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="f1eea-166">10-12</span><span class="sxs-lookup"><span data-stu-id="f1eea-166">10-12</span></span>  <br/> |<span data-ttu-id="f1eea-167">前9個伺服器中的任何5個</span><span class="sxs-lookup"><span data-stu-id="f1eea-167">Any 5 of the first 9 servers</span></span>  <br/> |
   
<span data-ttu-id="f1eea-168">在前一個表格中, 「第一台伺服器」是指第一次啟動該池時所發生的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-168">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="f1eea-169">若要判斷這些伺服器, 您可以將`Get-CsComputer` Cmdlet 與`-PoolFqdn`選項搭配使用。</span><span class="sxs-lookup"><span data-stu-id="f1eea-169">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="f1eea-170">這個 Cmdlet 會以拓撲結構中出現的順序顯示伺服器, 而清單頂端的是第一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-170">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="f1eea-171">確定池運作的其他步驟</span><span class="sxs-lookup"><span data-stu-id="f1eea-171">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="f1eea-172">您應該留意幾個其他因素, 以確保您的前端池仍能正常運作。</span><span class="sxs-lookup"><span data-stu-id="f1eea-172">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="f1eea-173">當您第一次將使用者移至該池時, 請確定至少有三個前端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="f1eea-173">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="f1eea-174">如果您在這個池與另一個用來進行災害復原的池之間建立配對關係, 則必須確定此池中有三個前端伺服器同時執行, 才能正確同步處理包含備份池的資料。</span><span class="sxs-lookup"><span data-stu-id="f1eea-174">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="f1eea-175">如需有關池配對及災害復原功能的詳細資訊, 請參閱[在商務用 Skype 伺服器中規劃高可用性和災難](high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="f1eea-175">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="f1eea-176">具有兩個前端伺服器的 [前端] 池</span><span class="sxs-lookup"><span data-stu-id="f1eea-176">Front End pool with two Front End servers</span></span>

<span data-ttu-id="f1eea-177">我們不建議您部署只包含兩個前端伺服器的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="f1eea-177">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="f1eea-178">這個小型 pool 不會提供強大的高可用性方案 (例如較大的池), 而且在管理時需要格外小心。</span><span class="sxs-lookup"><span data-stu-id="f1eea-178">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="f1eea-179">此外, 如果兩個伺服器池的後端伺服器已關閉, 整個池本身可能很快就會發生。</span><span class="sxs-lookup"><span data-stu-id="f1eea-179">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="f1eea-180">如果您只想部署一或兩台執行商務用 Skype Server 的伺服器, 我們建議您將它們部署為標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-180">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="f1eea-181">如果您需要部署具有兩個前端伺服器的 pool, 請遵循下列指導方針:</span><span class="sxs-lookup"><span data-stu-id="f1eea-181">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="f1eea-182">如果兩個前端伺服器中有一個是關閉的, 您應該儘快將失敗的伺服器移回原位。</span><span class="sxs-lookup"><span data-stu-id="f1eea-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="f1eea-183">同樣地, 如果您需要升級兩個伺服器的其中一個, 請在升級完成後立即將它重新連線。</span><span class="sxs-lookup"><span data-stu-id="f1eea-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="f1eea-184">如果您出於某種原因, 您需要同時將兩個伺服器移至一段時間, 請在池的停機時間結束時, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="f1eea-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="f1eea-185">最佳做法是同時重新開機這兩個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-185">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="f1eea-186">如果兩個伺服器不能同時重新開機, 您應該以相反順序將這些伺服器放回它們的順序。</span><span class="sxs-lookup"><span data-stu-id="f1eea-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="f1eea-187">如果您無法以這種順序傳回它們, 請先使用下列 Cmdlet, 然後再重新開機該池:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="f1eea-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="f1eea-188">前端池配置失敗與變更</span><span class="sxs-lookup"><span data-stu-id="f1eea-188">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="f1eea-189">如果前端伺服器發生故障, 且不太可能被取代數天以上, 請從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-189">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="f1eea-190">當新的前端伺服器再次可用時, 將它新增到拓撲。</span><span class="sxs-lookup"><span data-stu-id="f1eea-190">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="f1eea-191">每當您對前端池進行設定變更時 (例如新增或移除伺服器), 您必須遵循下列指導方針:</span><span class="sxs-lookup"><span data-stu-id="f1eea-191">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="f1eea-192">發佈新拓撲之後, 您必須重新開機池中的每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="f1eea-192">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="f1eea-193">一次重新開機一個。</span><span class="sxs-lookup"><span data-stu-id="f1eea-193">Restart them one at a time.</span></span>
    
- <span data-ttu-id="f1eea-194">如果在設定變更期間, 整個池都已停機, 請在發佈新拓撲之後, 執行下列 Cmdlet:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="f1eea-194">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

