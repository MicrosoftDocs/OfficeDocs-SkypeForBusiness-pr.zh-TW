---
title: 移轉階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。 網站是一組電腦，這些電腦是由高速、低延遲網路（例如單一局域網（LAN）或由高速光纖網路連接的兩個網路來連接。
ms.openlocfilehash: b7d7fbddfe77c1303f0f6bde95827d94d7483f32
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813421"
---
# <a name="migration-phases"></a><span data-ttu-id="3c4a5-104">移轉階段</span><span class="sxs-lookup"><span data-stu-id="3c4a5-104">Migration phases</span></span>

<span data-ttu-id="3c4a5-105">在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="3c4a5-106">網站是一組電腦，這些電腦是由高速、低延遲網路（例如單一局域網（LAN）或由高速光纖網路連接的兩個網路來連接。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="3c4a5-107">[前端] 池是一組前端伺服器，其配置相同，且共同合作，為一組共同使用者提供服務。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="3c4a5-108">[池] 可為您的使用者提供可伸縮性及容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="3c4a5-109">池中的每個伺服器都必須執行相同的伺服器角色或角色。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="3c4a5-110">專為小型組織設計的標準版伺服器也會定義一個池，並在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="3c4a5-111">這可讓您使用商務用 Skype Server 2019 功能來支付較低的費用，但不會提供真正的高可用性方案。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="3c4a5-112">下列階段描述的是將池遷移到商務用 Skype Server 2019 的進程。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="3c4a5-113">針對包含多個池的多個網站，每個個別的池都應該遵循這個分階段的方法。</span><span class="sxs-lookup"><span data-stu-id="3c4a5-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="3c4a5-114">階段 1：規劃移轉</span><span class="sxs-lookup"><span data-stu-id="3c4a5-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="3c4a5-115">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="3c4a5-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="3c4a5-116">階段3：部署商務用 Skype Server 2019 試生產池</span><span class="sxs-lookup"><span data-stu-id="3c4a5-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. <span data-ttu-id="3c4a5-117">[階段4：將測試使用者移至 [試驗] 池](phase-4-move-test-users-to-the-pilot-pool.md)</span><span class="sxs-lookup"><span data-stu-id="3c4a5-117">[Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md)</span></span>
    
5. <span data-ttu-id="3c4a5-118">[階段5：將商務用 Skype Server 2019 Edge 伺服器新增到 [試驗] 池](phase-5-add-edge-server-to-pilot-pool.md)</span><span class="sxs-lookup"><span data-stu-id="3c4a5-118">[Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool](phase-5-add-edge-server-to-pilot-pool.md)</span></span>
    
6. [<span data-ttu-id="3c4a5-119">階段 6：從試驗部署移至生產</span><span class="sxs-lookup"><span data-stu-id="3c4a5-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="3c4a5-120">階段 7：完成移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="3c4a5-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="3c4a5-121">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="3c4a5-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

