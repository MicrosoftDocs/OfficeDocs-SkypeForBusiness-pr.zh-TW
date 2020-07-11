---
title: 前端集區高可用性和管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 深入瞭解商務用 Skype Server 中的前端集區管理，包括管理集區、仲裁遺失，以及僅有兩部前端伺服器的集區的特殊步驟。
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098431"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="0ec77-103">前端集區高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="0ec77-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="0ec77-104">深入瞭解商務用 Skype Server 中的前端集區管理，包括管理集區、仲裁遺失，以及僅有兩部前端伺服器的集區的特殊步驟。</span><span class="sxs-lookup"><span data-stu-id="0ec77-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="0ec77-105">在商務用 Skype Server 中，前端集區的架構使用分散式系統模型，而每個使用者的資料在集區中的最多數目會保留三部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="0ec77-106">建議您的所有 Enterprise Edition 前端集區至少包含三部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="0ec77-107">商務用 Skype Server 2019 不支援 Enterprise Edition 前端集區與兩部前端伺服器，也不允許在該案例中發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="0ec77-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="0ec77-108">規劃前端集區的管理</span><span class="sxs-lookup"><span data-stu-id="0ec77-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="0ec77-109">商務用 Skype Server 使用以 Windows Fabric 為基礎的分散式系統模型。</span><span class="sxs-lookup"><span data-stu-id="0ec77-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="0ec77-110">在此模型中，每個使用者和會議的重要資料會儲存在前端集區中的三部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="0ec77-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="0ec77-111">這三個伺服器儲存一組特定的資料是 calledreplicas。</span><span class="sxs-lookup"><span data-stu-id="0ec77-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="0ec77-112">使用前端集區的分散式模型時，集區的伺服器必須執行某些數目的集區，集區才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="0ec77-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="0ec77-113">集區有兩個遺失模式。</span><span class="sxs-lookup"><span data-stu-id="0ec77-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="0ec77-114">路由群組層級仲裁遺失，因為特定路由群組的副本伺服器不足。</span><span class="sxs-lookup"><span data-stu-id="0ec77-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="0ec77-115">路由群組是駐留在集區中的一組使用者。</span><span class="sxs-lookup"><span data-stu-id="0ec77-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="0ec77-116">每個路由群組在集區中有三個複本：一個主要複本和兩個次要複本。</span><span class="sxs-lookup"><span data-stu-id="0ec77-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="0ec77-117">集區層級仲裁遺失，因為集區中沒有足夠的 seed 伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="0ec77-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="0ec77-118">路由群組層級仲裁遺失</span><span class="sxs-lookup"><span data-stu-id="0ec77-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="0ec77-119">第一次啟動新的前端集區時，85% 的伺服器已啟動且正在執行，這一點很重要，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="0ec77-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="0ec77-120">如果有較少的伺服器正在執行，服務可能會停滯在啟動狀態，而且集區可能無法啟動。</span><span class="sxs-lookup"><span data-stu-id="0ec77-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="0ec77-121">集區中的伺服器總數</span><span class="sxs-lookup"><span data-stu-id="0ec77-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="0ec77-122">第一次啟動集區時必須執行的伺服器數目</span><span class="sxs-lookup"><span data-stu-id="0ec77-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="0ec77-123">2 </span><span class="sxs-lookup"><span data-stu-id="0ec77-123">2</span></span>  <br/> |<span data-ttu-id="0ec77-124">1 </span><span class="sxs-lookup"><span data-stu-id="0ec77-124">1</span></span>  <br/> |
|<span data-ttu-id="0ec77-125">3 </span><span class="sxs-lookup"><span data-stu-id="0ec77-125">3</span></span>  <br/> |<span data-ttu-id="0ec77-126">3 </span><span class="sxs-lookup"><span data-stu-id="0ec77-126">3</span></span>  <br/> |
|<span data-ttu-id="0ec77-127">4 </span><span class="sxs-lookup"><span data-stu-id="0ec77-127">4</span></span>  <br/> |<span data-ttu-id="0ec77-128">3 </span><span class="sxs-lookup"><span data-stu-id="0ec77-128">3</span></span>  <br/> |
|<span data-ttu-id="0ec77-129">5 </span><span class="sxs-lookup"><span data-stu-id="0ec77-129">5</span></span>  <br/> |<span data-ttu-id="0ec77-130">4 </span><span class="sxs-lookup"><span data-stu-id="0ec77-130">4</span></span>  <br/> |
|<span data-ttu-id="0ec77-131">6 </span><span class="sxs-lookup"><span data-stu-id="0ec77-131">6</span></span>  <br/> |<span data-ttu-id="0ec77-132">5 </span><span class="sxs-lookup"><span data-stu-id="0ec77-132">5</span></span>  <br/> |
|<span data-ttu-id="0ec77-133">7 </span><span class="sxs-lookup"><span data-stu-id="0ec77-133">7</span></span>  <br/> |<span data-ttu-id="0ec77-134">5 </span><span class="sxs-lookup"><span data-stu-id="0ec77-134">5</span></span>  <br/> |
|<span data-ttu-id="0ec77-135">8 </span><span class="sxs-lookup"><span data-stu-id="0ec77-135">8</span></span>  <br/> |<span data-ttu-id="0ec77-136">6 </span><span class="sxs-lookup"><span data-stu-id="0ec77-136">6</span></span>  <br/> |
|<span data-ttu-id="0ec77-137">9 </span><span class="sxs-lookup"><span data-stu-id="0ec77-137">9</span></span>  <br/> |<span data-ttu-id="0ec77-138">7 </span><span class="sxs-lookup"><span data-stu-id="0ec77-138">7</span></span>  <br/> |
|<span data-ttu-id="0ec77-139">10 </span><span class="sxs-lookup"><span data-stu-id="0ec77-139">10</span></span>  <br/> |<span data-ttu-id="0ec77-140">8 </span><span class="sxs-lookup"><span data-stu-id="0ec77-140">8</span></span>  <br/> |
|<span data-ttu-id="0ec77-141">11 </span><span class="sxs-lookup"><span data-stu-id="0ec77-141">11</span></span>  <br/> |<span data-ttu-id="0ec77-142">9 </span><span class="sxs-lookup"><span data-stu-id="0ec77-142">9</span></span>  <br/> |
|<span data-ttu-id="0ec77-143">12 </span><span class="sxs-lookup"><span data-stu-id="0ec77-143">12</span></span>  <br/> |<span data-ttu-id="0ec77-144">10 </span><span class="sxs-lookup"><span data-stu-id="0ec77-144">10</span></span>  <br/> |
|<span data-ttu-id="0ec77-145">**適用于商務用 Skype Server 2019 的**16</span><span class="sxs-lookup"><span data-stu-id="0ec77-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="0ec77-146">12 </span><span class="sxs-lookup"><span data-stu-id="0ec77-146">12</span></span>  <br/> |


   
<span data-ttu-id="0ec77-147">每次後續的集區啟動時，應啟動85% 的伺服器 (，如上表) 所示。</span><span class="sxs-lookup"><span data-stu-id="0ec77-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="0ec77-148">若無法啟動此伺服器數目 (但是可以啟動足夠的伺服器，以致于您不會在集區層級仲裁遺失) 中，您可以使用 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` Cmdlet 來啟用集區以從此路由群組層級仲裁遺失中復原，並進行進展。</span><span class="sxs-lookup"><span data-stu-id="0ec77-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="0ec77-149">如需如何使用此 Cmdlet 的詳細資訊，請參閱[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="0ec77-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0ec77-150">在具有偶數伺服器數目的集區中，商務用 Skype 伺服器使用主要 SQL 資料庫作為見證。</span><span class="sxs-lookup"><span data-stu-id="0ec77-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="0ec77-151">在此像這樣的集區中，如果您關閉主資料庫並切換至鏡像副本，並關閉足夠的前端伺服器，以便根據上表的情況執行足夠的前端伺服器，則整個集區將會停止運作。</span><span class="sxs-lookup"><span data-stu-id="0ec77-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="0ec77-152">如需詳細資訊，請參閱[資料庫鏡像見證](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="0ec77-152">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="0ec77-153">集區層級仲裁遺失</span><span class="sxs-lookup"><span data-stu-id="0ec77-153">Pool-level quorum loss</span></span>

<span data-ttu-id="0ec77-154">若要讓前端集區能夠運作，它無法在集區層級仲裁遺失。</span><span class="sxs-lookup"><span data-stu-id="0ec77-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="0ec77-155">如果執行中的伺服器數目低於功能層級，如下表所示，集區中的剩餘伺服器將停止所有商務用 Skype Server 服務。</span><span class="sxs-lookup"><span data-stu-id="0ec77-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="0ec77-156">請注意，下表中的數位會假定集區中的後端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="0ec77-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="0ec77-157">集區中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="0ec77-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="0ec77-158">集區執行運作所需的伺服器數目</span><span class="sxs-lookup"><span data-stu-id="0ec77-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="0ec77-159">2 </span><span class="sxs-lookup"><span data-stu-id="0ec77-159">2</span></span>  <br/> |<span data-ttu-id="0ec77-160">1 </span><span class="sxs-lookup"><span data-stu-id="0ec77-160">1</span></span>  <br/> |
|<span data-ttu-id="0ec77-161">3-4</span><span class="sxs-lookup"><span data-stu-id="0ec77-161">3-4</span></span>  <br/> |<span data-ttu-id="0ec77-162">任何2</span><span class="sxs-lookup"><span data-stu-id="0ec77-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="0ec77-163">5-6</span><span class="sxs-lookup"><span data-stu-id="0ec77-163">5-6</span></span>  <br/> |<span data-ttu-id="0ec77-164">任何3</span><span class="sxs-lookup"><span data-stu-id="0ec77-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="0ec77-165">7 </span><span class="sxs-lookup"><span data-stu-id="0ec77-165">7</span></span>  <br/> |<span data-ttu-id="0ec77-166">任何4</span><span class="sxs-lookup"><span data-stu-id="0ec77-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="0ec77-167">8-9</span><span class="sxs-lookup"><span data-stu-id="0ec77-167">8-9</span></span>  <br/> |<span data-ttu-id="0ec77-168">前7部伺服器的任何4個</span><span class="sxs-lookup"><span data-stu-id="0ec77-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="0ec77-169">10-12</span><span class="sxs-lookup"><span data-stu-id="0ec77-169">10-12</span></span>  <br/> |<span data-ttu-id="0ec77-170">前9部伺服器的任意5個</span><span class="sxs-lookup"><span data-stu-id="0ec77-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="0ec77-171">**適用于商務用 Skype Server 2019 的**12-16</span><span class="sxs-lookup"><span data-stu-id="0ec77-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="0ec77-172">前12部伺服器的任何7個</span><span class="sxs-lookup"><span data-stu-id="0ec77-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="0ec77-173">在上表中，第一次啟動集區時，"first servers" 是第一次啟動的伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="0ec77-174">若要判斷這些伺服器，您可以使用 `Get-CsComputer` Cmdlet 搭配 `-PoolFqdn` 選項。</span><span class="sxs-lookup"><span data-stu-id="0ec77-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="0ec77-175">此 Cmdlet 會以拓撲中顯示的順序顯示伺服器，而位於清單頂端的伺服器是第一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ec77-176">[商務用 Skype Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)中的前端伺服器數目上限已增加至16</span><span class="sxs-lookup"><span data-stu-id="0ec77-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="0ec77-177">確定集區運作的其他步驟</span><span class="sxs-lookup"><span data-stu-id="0ec77-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="0ec77-178">您應注意其他一些因素，以確保前端集區仍可運作。</span><span class="sxs-lookup"><span data-stu-id="0ec77-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="0ec77-179">當您第一次將使用者移至集區時，請確定至少有三部前端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="0ec77-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="0ec77-180">如果您在此集區與其他集區之間建立配對關係，以進行嚴重損壞修復，則必須確定此集區在一段時間內有三部前端伺服器同時執行，才能正確地同步處理資料與備份組區。</span><span class="sxs-lookup"><span data-stu-id="0ec77-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="0ec77-181">如需有關集區配對和嚴重損壞修復功能的詳細資訊，請參閱[在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec77-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="0ec77-182">具有兩部前端伺服器的前端集區</span><span class="sxs-lookup"><span data-stu-id="0ec77-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="0ec77-183">建議您不要部署只包含兩部前端伺服器的前端集區。</span><span class="sxs-lookup"><span data-stu-id="0ec77-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="0ec77-184">這個小型集區不會提供強健的高可用性解決方案，像是較大的集區，也需要在管理時格外小心。</span><span class="sxs-lookup"><span data-stu-id="0ec77-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="0ec77-185">此外，如果兩部伺服器集區的後端伺服器已關機，則整個集區本身可能也會很快停機。</span><span class="sxs-lookup"><span data-stu-id="0ec77-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="0ec77-186">如果您只想要部署一部或兩部執行商務用 Skype Server 的伺服器，建議您將其部署為 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="0ec77-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="0ec77-187">如果您曾經需要部署兩部前端伺服器的集區，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="0ec77-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="0ec77-188">如果兩部前端伺服器之一停機，您應該盡可能將失敗的伺服器重新備份。</span><span class="sxs-lookup"><span data-stu-id="0ec77-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="0ec77-189">同樣地，如果您需要升級兩部伺服器中的其中一部，請在升級完成後立即將其移回線上。</span><span class="sxs-lookup"><span data-stu-id="0ec77-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="0ec77-190">若由於某些原因，您必須同時讓這兩部伺服器停機，請在完成集區的停機時間時，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="0ec77-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="0ec77-191">最佳作法是同時重新開機這兩部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="0ec77-192">若兩部伺服器不能同時重新開機，您應該以相反順序重新開機它們。</span><span class="sxs-lookup"><span data-stu-id="0ec77-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="0ec77-193">如果您無法以該順序重新備份，請在備份組區之前，先使用下列 Cmdlet：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="0ec77-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="0ec77-194">前端集區設定失敗及變更</span><span class="sxs-lookup"><span data-stu-id="0ec77-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="0ec77-195">如果前端伺服器失敗且不太可能取代一天以上，請從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="0ec77-196">將新的前端伺服器新增至拓撲，當它再次可用時。</span><span class="sxs-lookup"><span data-stu-id="0ec77-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="0ec77-197">當您對前端集區進行設定變更（例如新增或移除伺服器）時，必須遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="0ec77-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="0ec77-198">發行新的拓撲之後，您必須重新開機集區中的每一部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="0ec77-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="0ec77-199">一次重新開機一個。</span><span class="sxs-lookup"><span data-stu-id="0ec77-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="0ec77-200">如果在設定變更期間整個集區都已停機，請在發佈新的拓撲之後，執行下列 Cmdlet：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="0ec77-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

