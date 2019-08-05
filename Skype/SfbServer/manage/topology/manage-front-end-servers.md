---
title: 在商務用 Skype Server 中管理前端伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '摘要: 瞭解如何在商務用 Skype Server 中新增、移除、修補或更新前端伺服器。'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187102"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="c067e-103">在商務用 Skype Server 中管理前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c067e-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="c067e-104">本文說明如何新增或移除前端伺服器, 以及如何將升級或修補程式套用到前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="c067e-105">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c067e-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="c067e-106">當您將前端伺服器新增到池中, 或從池中移除前端伺服器時, 您必須重新開機該池。</span><span class="sxs-lookup"><span data-stu-id="c067e-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="c067e-107">當您在拓撲結構中新增或移除伺服器到池中, 然後發佈更新的拓撲時, 系統會同時重新開機該池中的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-107">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="c067e-108">伺服器重新開機時, 該池處於離線狀態, 這將會中斷連接到該池的使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="c067e-108">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="c067e-109">若要避免任何服務中斷給使用者, 請在非商務時間內, 規劃將拓撲發佈到池中的新伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-109">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="c067e-110">在新增或移除前端伺服器時, 您可以使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="c067e-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c067e-111">如果您要新增伺服器至池中, 請將新的池伺服器更新為與池中現有伺服器相同的累加更新層級。</span><span class="sxs-lookup"><span data-stu-id="c067e-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="c067e-112">新增或移除前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c067e-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="c067e-113">如果您要移除任何前端伺服器, 請先停止與這些伺服器建立新連線。</span><span class="sxs-lookup"><span data-stu-id="c067e-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="c067e-114">若要這樣做, 您可以使用下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c067e-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="c067e-115">開啟拓撲建立器, 然後新增或移除必要的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="c067e-116">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="c067e-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="c067e-117">當您在拓撲結構中新增或移除伺服器到池中, 然後發佈更新的拓撲時, 系統會同時重新開機該池中的所有伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-117">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="c067e-118">伺服器重新開機時, 該池處於離線狀態, 這將會中斷連接到該池的使用者的服務。</span><span class="sxs-lookup"><span data-stu-id="c067e-118">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="c067e-119">若要避免任何服務中斷給使用者, 請在非商務時間內, 規劃將拓撲發佈到池中的新伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-119">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="c067e-120">此外, 當您新增或移除伺服器至池中時, 您必須在新增或移除的每一部電腦上執行商務用 Skype Server 部署嚮導, 如需詳細資訊, 請參閱在[拓撲中的伺服器上安裝商務用 Skype 伺服器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="c067e-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="c067e-121">如果您已使用下列任何一種方式變更了您前端池中的伺服器數目, 請輸入下列 Cmdlet 來重設池: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="c067e-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="c067e-122">2到任何</span><span class="sxs-lookup"><span data-stu-id="c067e-122">2 to any</span></span>
    
     - <span data-ttu-id="c067e-123">[任何] 到2</span><span class="sxs-lookup"><span data-stu-id="c067e-123">Any to 2</span></span>
    
     - <span data-ttu-id="c067e-124">3到任何</span><span class="sxs-lookup"><span data-stu-id="c067e-124">3 to any</span></span>
    
     - <span data-ttu-id="c067e-125">Any 到3</span><span class="sxs-lookup"><span data-stu-id="c067e-125">Any to 3</span></span>
    
5. <span data-ttu-id="c067e-126">輸入下列 Cmdlet 以重新開機該池</span><span class="sxs-lookup"><span data-stu-id="c067e-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="c067e-127">修補或更新前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c067e-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="c067e-128">當您在前端池中修補伺服器時, 您可以一次使用一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="c067e-129">在池中將升級套用到前端伺服器</span><span class="sxs-lookup"><span data-stu-id="c067e-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="c067e-130">輸入下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c067e-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="c067e-131">如果這個 Cmdlet 顯示任何遺失的複本, 請執行下列 Cmdlet 來復原池, 然後再套用任何修補程式。</span><span class="sxs-lookup"><span data-stu-id="c067e-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="c067e-132">在您想要修補程式的第一個伺服器上, 執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c067e-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="c067e-133">這個 Cmdlet 會將所有服務移至池中的其他前端伺服器, 並讓此伺服器離線。</span><span class="sxs-lookup"><span data-stu-id="c067e-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="c067e-134">將升級或修補程式套用至此伺服器。</span><span class="sxs-lookup"><span data-stu-id="c067e-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="c067e-135">在已升級的伺服器上, 執行下列 Cmdlet:</span><span class="sxs-lookup"><span data-stu-id="c067e-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="c067e-136">伺服器傳回服務。</span><span class="sxs-lookup"><span data-stu-id="c067e-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="c067e-137">針對需要升級的每個伺服器, 重複執行步驟2-4。</span><span class="sxs-lookup"><span data-stu-id="c067e-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
