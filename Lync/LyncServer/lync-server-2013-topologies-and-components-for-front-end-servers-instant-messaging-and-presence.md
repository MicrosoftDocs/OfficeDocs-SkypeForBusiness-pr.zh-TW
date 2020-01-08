---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bc44790fc9584676cdd10305085b23bd5e99299
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="47b38-102">Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="47b38-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47b38-103">_**主題上次修改日期：** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="47b38-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="47b38-104">立即訊息（IM）與目前狀態所需的元件如下：</span><span class="sxs-lookup"><span data-stu-id="47b38-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="47b38-105">貴組織的前端伺服器或標準版伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="47b38-106">在這些伺服器上，系統永遠都能啟用 IM 和目前狀態功能。</span><span class="sxs-lookup"><span data-stu-id="47b38-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="47b38-107">[負載平衡器] （如果您有企業版的 [前端] 池）。</span><span class="sxs-lookup"><span data-stu-id="47b38-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="47b38-108">如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="47b38-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="47b38-109">規劃頂層端池的部署</span><span class="sxs-lookup"><span data-stu-id="47b38-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="47b38-110">在 Lync Server 2013 中，前端池架構已變更，這些變更會影響您應該如何規劃及維護您的前端池。</span><span class="sxs-lookup"><span data-stu-id="47b38-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="47b38-111">我們建議您所有的企業版前端池都包含至少三個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="47b38-112">在 Lync Server 中，前端池的架構使用分散式系統模型，每個使用者的資料都會保留在池中的三個前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="47b38-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="47b38-113">如需此新架構的詳細資訊，請參閱[Lync Server 2013 中的拓撲變更](lync-server-2013-topology-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="47b38-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="47b38-114">如果您不想部署三個企業版前端伺服器並想要進行災難復原，我們建議您使用 Lync Server 標準版，並建立具有成對備份關聯的兩個池。</span><span class="sxs-lookup"><span data-stu-id="47b38-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="47b38-115">這將會提供只包含兩個伺服器的災害復原方案。</span><span class="sxs-lookup"><span data-stu-id="47b38-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="47b38-116">如需詳細資訊，請參閱高可用性與災害復原拓撲及功能，請參閱[在 Lync Server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="47b38-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="47b38-117">規劃頂層端池的管理</span><span class="sxs-lookup"><span data-stu-id="47b38-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="47b38-118">針對 [前端] 池，請遵循本節中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="47b38-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="47b38-119">確保池運作正常</span><span class="sxs-lookup"><span data-stu-id="47b38-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="47b38-120">使用新的 [前端] 池分散式模型，必須執行一些池伺服器的特定編號，才能讓該池正常運作。</span><span class="sxs-lookup"><span data-stu-id="47b38-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="47b38-121">有兩種池的遺失模式</span><span class="sxs-lookup"><span data-stu-id="47b38-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="47b38-122">路由群組層級仲裁損失，因為特定路由群組沒有足夠的複本伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="47b38-123">路由群組是駐留在池中的一組使用者集合。</span><span class="sxs-lookup"><span data-stu-id="47b38-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="47b38-124">每個路由群組在該池中都有三個複本：一個主要和兩個次要資料庫。</span><span class="sxs-lookup"><span data-stu-id="47b38-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="47b38-125">當池中沒有足夠的種子伺服器執行時，會導致池層級仲裁遺失。</span><span class="sxs-lookup"><span data-stu-id="47b38-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="47b38-126">路由群組層級仲裁損失</span><span class="sxs-lookup"><span data-stu-id="47b38-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="47b38-127">第一次開始新的前端池時，85% 的伺服器必須正常運作，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="47b38-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="47b38-128">如果有較少的伺服器正在執行，服務可能會停滯在起始狀態，而且該池可能無法啟動。</span><span class="sxs-lookup"><span data-stu-id="47b38-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b38-129">池中的伺服器總數</span><span class="sxs-lookup"><span data-stu-id="47b38-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="47b38-130">必須執行才能第一次啟動該池的伺服器數量</span><span class="sxs-lookup"><span data-stu-id="47b38-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b38-131">pplx-2</span><span class="sxs-lookup"><span data-stu-id="47b38-131">2</span></span></p></td>
<td><p><span data-ttu-id="47b38-132">1</span><span class="sxs-lookup"><span data-stu-id="47b38-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-133">3</span><span class="sxs-lookup"><span data-stu-id="47b38-133">3</span></span></p></td>
<td><p><span data-ttu-id="47b38-134">3</span><span class="sxs-lookup"><span data-stu-id="47b38-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-135">4</span><span class="sxs-lookup"><span data-stu-id="47b38-135">4</span></span></p></td>
<td><p><span data-ttu-id="47b38-136">3</span><span class="sxs-lookup"><span data-stu-id="47b38-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-137">500</span><span class="sxs-lookup"><span data-stu-id="47b38-137">5</span></span></p></td>
<td><p><span data-ttu-id="47b38-138">4</span><span class="sxs-lookup"><span data-stu-id="47b38-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-139">6</span><span class="sxs-lookup"><span data-stu-id="47b38-139">6</span></span></p></td>
<td><p><span data-ttu-id="47b38-140">500</span><span class="sxs-lookup"><span data-stu-id="47b38-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-141">utf-7</span><span class="sxs-lookup"><span data-stu-id="47b38-141">7</span></span></p></td>
<td><p><span data-ttu-id="47b38-142">500</span><span class="sxs-lookup"><span data-stu-id="47b38-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-143">型</span><span class="sxs-lookup"><span data-stu-id="47b38-143">8</span></span></p></td>
<td><p><span data-ttu-id="47b38-144">6</span><span class="sxs-lookup"><span data-stu-id="47b38-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-145">9</span><span class="sxs-lookup"><span data-stu-id="47b38-145">9</span></span></p></td>
<td><p><span data-ttu-id="47b38-146">utf-7</span><span class="sxs-lookup"><span data-stu-id="47b38-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-147">第</span><span class="sxs-lookup"><span data-stu-id="47b38-147">10</span></span></p></td>
<td><p><span data-ttu-id="47b38-148">型</span><span class="sxs-lookup"><span data-stu-id="47b38-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-149">11</span><span class="sxs-lookup"><span data-stu-id="47b38-149">11</span></span></p></td>
<td><p><span data-ttu-id="47b38-150">9</span><span class="sxs-lookup"><span data-stu-id="47b38-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-151">之間</span><span class="sxs-lookup"><span data-stu-id="47b38-151">12</span></span></p></td>
<td><p><span data-ttu-id="47b38-152">第</span><span class="sxs-lookup"><span data-stu-id="47b38-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="47b38-153">每次啟動該池之後，伺服器的85% 應該會啟動（如前面的資料表所示）。</span><span class="sxs-lookup"><span data-stu-id="47b38-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="47b38-154">如果此伺服器數無法啟動（但可以啟動足夠的伺服器，因此您不在池層級的仲裁遺失），您可以使用**Reset-CsPoolRegistrarState-ResetType QuorumLossRecovery** Cmdlet，讓該池能夠從這種路由群組層級的仲裁遺失中復原並產生進度。</span><span class="sxs-lookup"><span data-stu-id="47b38-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="47b38-155">如需如何使用此 Cmdlet 的詳細資訊，請參閱[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。</span><span class="sxs-lookup"><span data-stu-id="47b38-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47b38-156">因為 Lync Server 會使用主要的 SQL 資料庫做為見證，所以如果您關閉主資料庫並切換到鏡像複本，然後關閉足夠的前端伺服器，以使其根據前面的資料表執行時，整個池都會向下移動。</span><span class="sxs-lookup"><span data-stu-id="47b38-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="47b38-157">如需詳細資訊，請參閱<A href="http://go.microsoft.com/fwlink/?linkid=393672">資料庫鏡像見證</A>。</span><span class="sxs-lookup"><span data-stu-id="47b38-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="47b38-158">池層級仲裁損失</span><span class="sxs-lookup"><span data-stu-id="47b38-158">Pool-level quorum loss</span></span>

<span data-ttu-id="47b38-159">若要讓前臺端池完全正常運作，它不能在 pool 階層的仲裁遺失中。</span><span class="sxs-lookup"><span data-stu-id="47b38-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="47b38-160">如果執行中的伺服器數目低於功能層級，如下表所示，池中剩餘的伺服器將停止所有 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="47b38-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="47b38-161">請注意，下表中的數位假設池中的後端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="47b38-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47b38-162">池中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="47b38-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="47b38-163">必須執行才能供擁有池中運作的伺服器數量</span><span class="sxs-lookup"><span data-stu-id="47b38-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47b38-164">pplx-2</span><span class="sxs-lookup"><span data-stu-id="47b38-164">2</span></span></p></td>
<td><p><span data-ttu-id="47b38-165">1</span><span class="sxs-lookup"><span data-stu-id="47b38-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-166">3-4</span><span class="sxs-lookup"><span data-stu-id="47b38-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="47b38-167">任何2</span><span class="sxs-lookup"><span data-stu-id="47b38-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-168">5-6</span><span class="sxs-lookup"><span data-stu-id="47b38-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="47b38-169">任何3</span><span class="sxs-lookup"><span data-stu-id="47b38-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-170">utf-7</span><span class="sxs-lookup"><span data-stu-id="47b38-170">7</span></span></p></td>
<td><p><span data-ttu-id="47b38-171">任何4</span><span class="sxs-lookup"><span data-stu-id="47b38-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47b38-172">8-9</span><span class="sxs-lookup"><span data-stu-id="47b38-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="47b38-173">前7個伺服器中的任何4個</span><span class="sxs-lookup"><span data-stu-id="47b38-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47b38-174">10-12</span><span class="sxs-lookup"><span data-stu-id="47b38-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="47b38-175">前9個伺服器中的任何5個</span><span class="sxs-lookup"><span data-stu-id="47b38-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="47b38-176">在前一個表格中，「第一台伺服器」是指第一次啟動該池時所發生的伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="47b38-177">若要判斷這些伺服器，您可以使用**CsComputer** Cmdlet 和 **– PoolFqdn**選項。</span><span class="sxs-lookup"><span data-stu-id="47b38-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="47b38-178">這個 Cmdlet 會以拓撲結構中出現的順序顯示伺服器，而清單頂端的是第一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="47b38-179">具有兩個前端伺服器的前端池</span><span class="sxs-lookup"><span data-stu-id="47b38-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="47b38-180">我們不建議您部署只包含兩個前端伺服器的 [前端] 池。</span><span class="sxs-lookup"><span data-stu-id="47b38-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="47b38-181">如果您需要部署此類池，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="47b38-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="47b38-182">如果兩個前端伺服器中有一個是關閉的，您應該儘快將失敗的伺服器移回原位。</span><span class="sxs-lookup"><span data-stu-id="47b38-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="47b38-183">同樣地，如果您需要升級兩個伺服器的其中一個，請在升級完成後立即將它重新連線。</span><span class="sxs-lookup"><span data-stu-id="47b38-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="47b38-184">如果您出於某種原因，您需要同時將兩個伺服器移至一段時間，請在池的停機時間結束時，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="47b38-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="47b38-185">最佳做法是同時重新開機這兩個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="47b38-186">如果兩個伺服器不能同時重新開機，您應該以相反順序將這些伺服器放回它們的順序。</span><span class="sxs-lookup"><span data-stu-id="47b38-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="47b38-187">如果您無法以這種順序傳回它們，請先使用下列 Cmdlet，然後再重新開機該池：。</span><span class="sxs-lookup"><span data-stu-id="47b38-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="47b38-188">確定池運作的其他步驟</span><span class="sxs-lookup"><span data-stu-id="47b38-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="47b38-189">您應該留意幾個其他因素，以確保您的前端池仍能正常運作。</span><span class="sxs-lookup"><span data-stu-id="47b38-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="47b38-190">當您第一次將使用者移至該池時，請確定至少有三個前端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="47b38-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="47b38-191">如果您在這個池與另一個用來進行災害復原的池之間建立配對關係，則必須確定此池中有三個前端伺服器同時執行，才能正確同步處理包含備份池的資料。</span><span class="sxs-lookup"><span data-stu-id="47b38-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="47b38-192">如需有關池配對及災害復原功能的詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和災難](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)復原。</span><span class="sxs-lookup"><span data-stu-id="47b38-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="47b38-193">改善池升級的可靠性</span><span class="sxs-lookup"><span data-stu-id="47b38-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="47b38-194">當您需要升級或修補前端池中的伺服器時，請遵循在[Lync Server 2013 升級或更新前端伺服器中](lync-server-2013-upgrade-or-update-front-end-servers.md)顯示的工作流程，以及下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="47b38-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="47b38-195">當您從一個升級網域移到另一個升級網域進行升級時（遵循在[Lync Server 2013 中升級或更新前端伺服器](lync-server-2013-upgrade-or-update-front-end-servers.md)的工作流程），您將會使用**CsPoolUpgradeReadinessState** Cmdlet 並檢查 [就緒] 的狀態。</span><span class="sxs-lookup"><span data-stu-id="47b38-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="47b38-196">在每個升級網域達到 [就緒] 後，在每個升級網域之間加上20分鐘的等待，即可使升級更加可靠。</span><span class="sxs-lookup"><span data-stu-id="47b38-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="47b38-197">如果在此20分鐘內**未準備好**，請重新開機20分鐘計時器。</span><span class="sxs-lookup"><span data-stu-id="47b38-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="47b38-198">此外，您可以在啟動20分鐘間隔之前和之後執行**CsPoolFabricState** Cmdlet，並確定路由群組的 primaries 和輔助副本沒有任何變更。</span><span class="sxs-lookup"><span data-stu-id="47b38-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="47b38-199">如果在最後一次補丁的升級網域中有任何伺服器停滯或未重新開機，請勿移至下一個升級網域。</span><span class="sxs-lookup"><span data-stu-id="47b38-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="47b38-200">如果升級中的任何伺服器無法啟動，這也適用。</span><span class="sxs-lookup"><span data-stu-id="47b38-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="47b38-201">請執行**CsPoolFabricState** ，確定所有路由群組都有主要及至少一個副，這將會確認所有使用者是否都有服務。</span><span class="sxs-lookup"><span data-stu-id="47b38-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="47b38-202">如果有些使用者有服務且其他人不具備，請執行**CsPoolFabricState**與-Verbose 選項，以檢查是否有遺失複本的路由群組。</span><span class="sxs-lookup"><span data-stu-id="47b38-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="47b38-203">請勿重新開機整個池做為第一個疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="47b38-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="47b38-204">如需此 Cmdlet 的詳細資訊，請參閱[CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。</span><span class="sxs-lookup"><span data-stu-id="47b38-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="47b38-205">請確定已關閉事件檢視器或效能監視器視窗的所有實例，以供 windows fabric 安裝/卸載。</span><span class="sxs-lookup"><span data-stu-id="47b38-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="47b38-206">變更前端池的設定</span><span class="sxs-lookup"><span data-stu-id="47b38-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="47b38-207">每當您將前端伺服器新增到某個池，或從池中移除該伺服器，然後發佈新的拓撲時，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="47b38-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="47b38-208">發佈新拓撲之後，您必須重新開機池中的每個前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="47b38-209">一次重新開機一個。</span><span class="sxs-lookup"><span data-stu-id="47b38-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="47b38-210">如果在設定變更期間，整個池都已停機，請在發佈新拓撲之後，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="47b38-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="47b38-211">如果前端伺服器發生故障，且不太可能被取代數天以上，請從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="47b38-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="47b38-212">當新的前端伺服器再次可用時，將它新增到拓撲。</span><span class="sxs-lookup"><span data-stu-id="47b38-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

