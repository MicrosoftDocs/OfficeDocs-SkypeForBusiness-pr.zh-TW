---
title: 管理商務用 Skype Server 中的前端伺服器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：瞭解如何在商務用 Skype Server 中新增、移除、修補或更新前端伺服器。
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103189"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="c2af3-103">管理商務用 Skype Server 中的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c2af3-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="c2af3-104">本文說明如何新增或移除前端伺服器，以及如何對前端伺服器套用升級或修補程式。</span><span class="sxs-lookup"><span data-stu-id="c2af3-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="c2af3-105">商務用 Skype Server 2019 不支援 Enterprise Edition 前端集區與兩部前端伺服器，也不允許在該案例中發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="c2af3-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="c2af3-106">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c2af3-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="c2af3-107">當您將前端伺服器新增至集區，或從集區中移除前端伺服器時，您必須重新開機集區。</span><span class="sxs-lookup"><span data-stu-id="c2af3-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c2af3-108">當您在拓撲中新增或移除伺服器集區，然後發佈更新的拓撲時，會導致集區中的所有伺服器同時重新開機。</span><span class="sxs-lookup"><span data-stu-id="c2af3-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="c2af3-109">伺服器重新開機時，集區為離線狀態，這會中斷連接至該集區之使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="c2af3-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="c2af3-110">若要防止任何服務中斷給使用者，請規劃在非上班時間內，使用集區中的新伺服器發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="c2af3-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="c2af3-111">新增或移除前端伺服器時，您可以使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="c2af3-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2af3-112">若要將新伺服器新增至集區，請將新的集區伺服器更新成與集區中現有伺服器相同的累計更新層級。</span><span class="sxs-lookup"><span data-stu-id="c2af3-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="c2af3-113">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c2af3-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="c2af3-114">如果您要移除任何前端伺服器，請先停止這些伺服器的新連線。</span><span class="sxs-lookup"><span data-stu-id="c2af3-114">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="c2af3-115">若要這麼做，您可以使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c2af3-115">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="c2af3-116">開啟拓撲產生器，並新增或移除必要的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2af3-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="c2af3-117">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="c2af3-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c2af3-118">當您在拓撲中新增或移除伺服器集區，然後發佈更新的拓撲時，會導致集區中的所有伺服器同時重新開機。</span><span class="sxs-lookup"><span data-stu-id="c2af3-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="c2af3-119">伺服器重新開機時，集區為離線狀態，這會中斷連接至該集區之使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="c2af3-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="c2af3-120">若要防止任何服務中斷給使用者，請規劃在非上班時間內，使用集區中的新伺服器發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="c2af3-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="c2af3-121">此外，當您新增或移除伺服器至集區時，您必須在新增或移除的每一部電腦上執行商務用 Skype Server 部署嚮導。如需詳細資訊，請參閱在 [拓撲中的伺服器上安裝商務用 Skype server](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="c2af3-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span></span>
  
4. <span data-ttu-id="c2af3-122">如果您已以下列任何方式變更前端集區中的伺服器數目，請輸入下列 Cmdlet 以重設集區： Reset-CsPoolRegistrarState ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="c2af3-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="c2af3-123">2至任何</span><span class="sxs-lookup"><span data-stu-id="c2af3-123">2 to any</span></span>
    
     - <span data-ttu-id="c2af3-124">任何2</span><span class="sxs-lookup"><span data-stu-id="c2af3-124">Any to 2</span></span>
    
     - <span data-ttu-id="c2af3-125">3至任何</span><span class="sxs-lookup"><span data-stu-id="c2af3-125">3 to any</span></span>
    
     - <span data-ttu-id="c2af3-126">任意至3</span><span class="sxs-lookup"><span data-stu-id="c2af3-126">Any to 3</span></span>
    
5. <span data-ttu-id="c2af3-127">輸入下列 Cmdlet 以重新開機集區</span><span class="sxs-lookup"><span data-stu-id="c2af3-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="c2af3-128">修補或更新前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c2af3-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="c2af3-129">當您修補前端集區中的伺服器時，一次可執行一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2af3-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="c2af3-130">將升級套用至集區中的前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c2af3-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="c2af3-131">輸入下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c2af3-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="c2af3-132">如果此 Cmdlet 顯示任何遺失的複本，請執行下列 Cmdlet 來復原集區，再套用任何修補程式。</span><span class="sxs-lookup"><span data-stu-id="c2af3-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="c2af3-133">在您想要修補的第一部伺服器上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c2af3-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="c2af3-134">此 Cmdlet 會將所有服務移至集區中的其他前端伺服器，並將此伺服器離線。</span><span class="sxs-lookup"><span data-stu-id="c2af3-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="c2af3-135">將升級或修補程式套用至此伺服器。</span><span class="sxs-lookup"><span data-stu-id="c2af3-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="c2af3-136">在升級的伺服器上，執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c2af3-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="c2af3-137">伺服器會傳回服務。</span><span class="sxs-lookup"><span data-stu-id="c2af3-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="c2af3-138">針對需要升級的每一部伺服器，重複步驟2-4。</span><span class="sxs-lookup"><span data-stu-id="c2af3-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
