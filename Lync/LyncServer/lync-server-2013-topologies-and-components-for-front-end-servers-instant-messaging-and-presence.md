---
title: Lync Server 2013：前端伺服器、立即訊息及顯示狀態的拓撲和元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4abe15d3884bc24d4facb26e2fc0c2df9e31bdcc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="ce056-102">Lync Server 2013 中的前端伺服器、立即訊息及顯示狀態的拓撲和元件</span><span class="sxs-lookup"><span data-stu-id="ce056-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce056-103">_**主題上次修改日期：** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="ce056-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="ce056-104">立即訊息 (IM) 和目前狀態所需的元件包括：</span><span class="sxs-lookup"><span data-stu-id="ce056-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="ce056-105">您組織的前端伺服器或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="ce056-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="ce056-106">IM 和目前狀態功能在這些伺服器上一定會啟用。</span><span class="sxs-lookup"><span data-stu-id="ce056-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="ce056-107">負載平衡器（如果您有 Enterprise Edition 前端集區）。</span><span class="sxs-lookup"><span data-stu-id="ce056-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="ce056-108">如需詳細資訊，請參閱[Lync Server 2013 的負載平衡需求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ce056-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="ce056-109">規劃前端集區的部署</span><span class="sxs-lookup"><span data-stu-id="ce056-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="ce056-110">在 Lync Server 2013 中，前端集區架構已變更，這些變更會影響您應如何規劃及維護前端集區。</span><span class="sxs-lookup"><span data-stu-id="ce056-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="ce056-111">建議您的所有 Enterprise Edition 前端集區至少包含三部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="ce056-112">在 Lync Server 中，前端集區的架構使用分散式系統模型，而每個使用者的資料都保存在集區中的三部前端伺服器上。</span><span class="sxs-lookup"><span data-stu-id="ce056-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="ce056-113">如需此新架構的相關資訊，請參閱[Lync Server 2013 中的拓撲變更](lync-server-2013-topology-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="ce056-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="ce056-114">如果您不想部署三個 Enterprise Edition 前端伺服器並想要進行嚴重損壞修復，建議您使用 Lync Server Standard Edition，並建立具有成對備份關聯的兩個集區。</span><span class="sxs-lookup"><span data-stu-id="ce056-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="ce056-115">這將會提供僅含兩部伺服器的嚴重損壞修復解決方案。</span><span class="sxs-lookup"><span data-stu-id="ce056-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="ce056-116">如需詳細資訊，請參閱高可用性和嚴重損壞修復拓撲及功能，請參閱在[Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ce056-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="ce056-117">規劃前端集區的管理</span><span class="sxs-lookup"><span data-stu-id="ce056-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="ce056-118">針對前端集區，請遵循本節中的指導方針。</span><span class="sxs-lookup"><span data-stu-id="ce056-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="ce056-119">確定集區運作正常</span><span class="sxs-lookup"><span data-stu-id="ce056-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="ce056-120">使用前端集區的新分散式模型，集區的伺服器必須執行某些號碼，集區才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="ce056-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="ce056-121">集區有兩個遺失模式</span><span class="sxs-lookup"><span data-stu-id="ce056-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="ce056-122">路由群組層級仲裁遺失，因為特定路由群組的副本伺服器不足。</span><span class="sxs-lookup"><span data-stu-id="ce056-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="ce056-123">路由群組是駐留在集區中之一組使用者的集合。</span><span class="sxs-lookup"><span data-stu-id="ce056-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="ce056-124">每個路由群組在集區中有三個複本：一個主要和兩個次要複本。</span><span class="sxs-lookup"><span data-stu-id="ce056-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="ce056-125">集區層級仲裁遺失，因為集區中沒有足夠的 seed 伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="ce056-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="ce056-126">路由群組層級仲裁遺失</span><span class="sxs-lookup"><span data-stu-id="ce056-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="ce056-127">第一次啟動新的前端集區時，85% 的伺服器已啟動且正在執行，這一點很重要，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ce056-127">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="ce056-128">如果有較少的伺服器正在執行，服務可能會停滯在啟動狀態，而且集區可能無法啟動。</span><span class="sxs-lookup"><span data-stu-id="ce056-128">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce056-129">集區中的伺服器總數</span><span class="sxs-lookup"><span data-stu-id="ce056-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="ce056-130">第一次啟動集區時必須執行的伺服器數目</span><span class="sxs-lookup"><span data-stu-id="ce056-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce056-131">2</span><span class="sxs-lookup"><span data-stu-id="ce056-131">2</span></span></p></td>
<td><p><span data-ttu-id="ce056-132">1</span><span class="sxs-lookup"><span data-stu-id="ce056-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-133">個</span><span class="sxs-lookup"><span data-stu-id="ce056-133">3</span></span></p></td>
<td><p><span data-ttu-id="ce056-134">個</span><span class="sxs-lookup"><span data-stu-id="ce056-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-135">4 </span><span class="sxs-lookup"><span data-stu-id="ce056-135">4</span></span></p></td>
<td><p><span data-ttu-id="ce056-136">個</span><span class="sxs-lookup"><span data-stu-id="ce056-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-137">5 </span><span class="sxs-lookup"><span data-stu-id="ce056-137">5</span></span></p></td>
<td><p><span data-ttu-id="ce056-138">4 </span><span class="sxs-lookup"><span data-stu-id="ce056-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-139">6 </span><span class="sxs-lookup"><span data-stu-id="ce056-139">6</span></span></p></td>
<td><p><span data-ttu-id="ce056-140">5 </span><span class="sxs-lookup"><span data-stu-id="ce056-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-141">7 </span><span class="sxs-lookup"><span data-stu-id="ce056-141">7</span></span></p></td>
<td><p><span data-ttu-id="ce056-142">5 </span><span class="sxs-lookup"><span data-stu-id="ce056-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-143">8 </span><span class="sxs-lookup"><span data-stu-id="ce056-143">8</span></span></p></td>
<td><p><span data-ttu-id="ce056-144">6 </span><span class="sxs-lookup"><span data-stu-id="ce056-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-145">9 </span><span class="sxs-lookup"><span data-stu-id="ce056-145">9</span></span></p></td>
<td><p><span data-ttu-id="ce056-146">7 </span><span class="sxs-lookup"><span data-stu-id="ce056-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-147">10 </span><span class="sxs-lookup"><span data-stu-id="ce056-147">10</span></span></p></td>
<td><p><span data-ttu-id="ce056-148">8 </span><span class="sxs-lookup"><span data-stu-id="ce056-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-149">11 </span><span class="sxs-lookup"><span data-stu-id="ce056-149">11</span></span></p></td>
<td><p><span data-ttu-id="ce056-150">9 </span><span class="sxs-lookup"><span data-stu-id="ce056-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-151">12 </span><span class="sxs-lookup"><span data-stu-id="ce056-151">12</span></span></p></td>
<td><p><span data-ttu-id="ce056-152">10 </span><span class="sxs-lookup"><span data-stu-id="ce056-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce056-153">每次後續的集區啟動時，應啟動85% 的伺服器 (，如上表) 所示。</span><span class="sxs-lookup"><span data-stu-id="ce056-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="ce056-154">若無法啟動此伺服器數目 (但是可以啟動足夠的伺服器，以致于您不會在集區層級仲裁遺失) ，您可以使用**Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** Cmdlet，讓集區能夠從此路由群組層級仲裁遺失中復原，並取得進展。</span><span class="sxs-lookup"><span data-stu-id="ce056-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="ce056-155">如需如何使用此 Cmdlet 的詳細資訊，請參閱[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。</span><span class="sxs-lookup"><span data-stu-id="ce056-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ce056-156">由於 Lync Server 使用主要 SQL 資料庫做為見證，所以如果您關閉主資料庫並切換至鏡像副本，並關閉足夠的前端伺服器，以便根據上表上的表格執行不夠的狀態，則整個集區將會關閉。</span><span class="sxs-lookup"><span data-stu-id="ce056-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="ce056-157">如需詳細資訊，請參閱<A href="https://go.microsoft.com/fwlink/?linkid=393672">資料庫鏡像見證</A>。</span><span class="sxs-lookup"><span data-stu-id="ce056-157">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="ce056-158">集區層級仲裁遺失</span><span class="sxs-lookup"><span data-stu-id="ce056-158">Pool-level quorum loss</span></span>

<span data-ttu-id="ce056-159">若要讓前端集區能夠運作，它無法在集區層級仲裁遺失。</span><span class="sxs-lookup"><span data-stu-id="ce056-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="ce056-160">如果執行中的伺服器數目低於功能層級，如下表所示，集區中的剩餘伺服器將停止所有的 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="ce056-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="ce056-161">請注意，下表中的數位會假定集區中的後端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="ce056-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce056-162">集區中的前端伺服器總數</span><span class="sxs-lookup"><span data-stu-id="ce056-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="ce056-163">集區執行運作所需的伺服器數目</span><span class="sxs-lookup"><span data-stu-id="ce056-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce056-164">2</span><span class="sxs-lookup"><span data-stu-id="ce056-164">2</span></span></p></td>
<td><p><span data-ttu-id="ce056-165">1</span><span class="sxs-lookup"><span data-stu-id="ce056-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-166">3-4</span><span class="sxs-lookup"><span data-stu-id="ce056-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="ce056-167">任何2</span><span class="sxs-lookup"><span data-stu-id="ce056-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-168">5-6</span><span class="sxs-lookup"><span data-stu-id="ce056-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="ce056-169">任何3</span><span class="sxs-lookup"><span data-stu-id="ce056-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-170">7 </span><span class="sxs-lookup"><span data-stu-id="ce056-170">7</span></span></p></td>
<td><p><span data-ttu-id="ce056-171">任何4</span><span class="sxs-lookup"><span data-stu-id="ce056-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce056-172">8-9</span><span class="sxs-lookup"><span data-stu-id="ce056-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="ce056-173">前7部伺服器的任何4個</span><span class="sxs-lookup"><span data-stu-id="ce056-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce056-174">10-12</span><span class="sxs-lookup"><span data-stu-id="ce056-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="ce056-175">前9部伺服器的任意5個</span><span class="sxs-lookup"><span data-stu-id="ce056-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce056-176">在上表中，第一次啟動集區時，"first servers" 是第一次啟動的伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="ce056-177">若要判斷這些伺服器，您可以使用具有 **– PoolFqdn**選項的**Get-CsComputer** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ce056-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="ce056-178">此 Cmdlet 會以拓撲中顯示的順序顯示伺服器，而位於清單頂端的伺服器是第一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="ce056-179">具有兩部前端伺服器的前端集區</span><span class="sxs-lookup"><span data-stu-id="ce056-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="ce056-180">建議您不要部署只包含兩部前端伺服器的前端集區。</span><span class="sxs-lookup"><span data-stu-id="ce056-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="ce056-181">若您曾經需要部署此類集區，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="ce056-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="ce056-182">如果兩部前端伺服器之一停機，您應該盡可能將失敗的伺服器重新備份。</span><span class="sxs-lookup"><span data-stu-id="ce056-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="ce056-183">同樣地，如果您需要升級兩部伺服器中的其中一部，請在升級完成後立即將其移回線上。</span><span class="sxs-lookup"><span data-stu-id="ce056-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="ce056-184">若由於某些原因，您必須同時讓這兩部伺服器停機，請在完成集區的停機時間時，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="ce056-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="ce056-185">最佳作法是同時重新開機這兩部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="ce056-186">若兩部伺服器不能同時重新開機，您應該以相反順序重新開機它們。</span><span class="sxs-lookup"><span data-stu-id="ce056-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="ce056-187">如果您無法以該順序重新備份，請在備份組區之前，先使用下列 Cmdlet：。</span><span class="sxs-lookup"><span data-stu-id="ce056-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="ce056-188">確定集區運作的其他步驟</span><span class="sxs-lookup"><span data-stu-id="ce056-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="ce056-189">您應注意其他一些因素，以確保前端集區仍可運作。</span><span class="sxs-lookup"><span data-stu-id="ce056-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="ce056-190">當您第一次將使用者移至集區時，請確定至少有三部前端伺服器正在執行。</span><span class="sxs-lookup"><span data-stu-id="ce056-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="ce056-191">如果您在此集區與其他集區之間建立配對關係，以進行嚴重損壞修復，則必須確定此集區在一段時間內有三部前端伺服器同時執行，才能正確地同步處理資料與備份組區。</span><span class="sxs-lookup"><span data-stu-id="ce056-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="ce056-192">如需有關集區配對和嚴重損壞修復功能的詳細資訊，請參閱[在 Lync Server 2013 中規劃高可用性和嚴重損壞修復](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ce056-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="ce056-193">改善集區升級的可靠性</span><span class="sxs-lookup"><span data-stu-id="ce056-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="ce056-194">當您需要升級或修補前端集區中的伺服器時，請遵循在[Lync Server 2013 的升級或更新前端伺服器中](lync-server-2013-upgrade-or-update-front-end-servers.md)顯示的工作流程，以及下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="ce056-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="ce056-195">當您從一個升級網域移至另一個升級網域以進行升級時 (請在[升級或更新 Lync Server 2013) 中的前端伺服器](lync-server-2013-upgrade-or-update-front-end-servers.md)之後，使用**Get-CsPoolUpgradeReadinessState** Cmdlet 並檢查 [就緒] 狀態。</span><span class="sxs-lookup"><span data-stu-id="ce056-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="ce056-196">在每個升級網域達到「就緒」狀態時，新增20分鐘的等待時間，可使升級更為可靠。</span><span class="sxs-lookup"><span data-stu-id="ce056-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="ce056-197">如果在此20分鐘內**未準備好**，請重新開機20分鐘計時器。</span><span class="sxs-lookup"><span data-stu-id="ce056-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="ce056-198">此外，您也可以在啟動20分鐘的間隔前後執行**Get-CsPoolFabricState** Cmdlet，並確定路由群組的 primaries 和輔助副本沒有任何變更。</span><span class="sxs-lookup"><span data-stu-id="ce056-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="ce056-199">若最後一次修補的升級網域中的任何伺服器都停滯或未重新開機，請勿移至下一個升級網域。</span><span class="sxs-lookup"><span data-stu-id="ce056-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="ce056-200">如果升級內的任何伺服器都無法啟動，也會套用這種情況。</span><span class="sxs-lookup"><span data-stu-id="ce056-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="ce056-201">請執行**Get-CsPoolFabricState** ，確定所有路由群組都有主要和至少一個次要;這會確認所有使用者是否都有服務。</span><span class="sxs-lookup"><span data-stu-id="ce056-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="ce056-202">如果有些使用者有服務，但其他使用者卻沒有服務，請以– Verbose 選項執行**Get-CsPoolFabricState** ，檢查是否有遺失複本的路由群組。</span><span class="sxs-lookup"><span data-stu-id="ce056-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="ce056-203">請不要重新開機整個集區做為第一個疑難排解步驟。</span><span class="sxs-lookup"><span data-stu-id="ce056-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="ce056-204">如需此 Cmdlet 的詳細資訊，請參閱[Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。</span><span class="sxs-lookup"><span data-stu-id="ce056-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="ce056-205">請確定已關閉事件檢視器或效能監視器視窗的所有實例，以進行 windows fabric 安裝/卸載。</span><span class="sxs-lookup"><span data-stu-id="ce056-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="ce056-206">變更前端集區的設定</span><span class="sxs-lookup"><span data-stu-id="ce056-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="ce056-207">每當您將前端伺服器新增至集區，或從集區中移除它們，然後發佈新的拓撲時，請遵循下列指導方針：</span><span class="sxs-lookup"><span data-stu-id="ce056-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="ce056-208">發行新的拓撲之後，您必須重新開機集區中的每一部前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="ce056-209">一次重新開機一個。</span><span class="sxs-lookup"><span data-stu-id="ce056-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="ce056-210">如果在設定變更期間整個集區都已停機，請在發佈新的拓撲之後，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ce056-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="ce056-211">如果前端伺服器失敗且不太可能取代一天以上，請從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce056-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="ce056-212">將新的前端伺服器新增至拓撲，當它再次可用時。</span><span class="sxs-lookup"><span data-stu-id="ce056-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

