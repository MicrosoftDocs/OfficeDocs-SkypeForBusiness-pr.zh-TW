---
title: 遷移階段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。 網站是一組電腦，其連線速度很快，低延遲網路，例如單一局域網（LAN）或由高速光纖網路連接的兩個網路。
ms.openlocfilehash: d05fc0c4eb7d12a6d96b638fe7f59acc830fbcd1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752625"
---
# <a name="migration-phases"></a><span data-ttu-id="c2219-104">遷移階段</span><span class="sxs-lookup"><span data-stu-id="c2219-104">Migration phases</span></span>

<span data-ttu-id="c2219-105">在商務用 Skype Server 2019 中，您可以在網路上定義包含商務用 Skype Server 2019 元件的網站。</span><span class="sxs-lookup"><span data-stu-id="c2219-105">In Skype for Business Server 2019, you define sites on your network that contain Skype for Business Server 2019 components.</span></span> <span data-ttu-id="c2219-106">網站是一組電腦，其連線速度很快，低延遲網路，例如單一局域網（LAN）或由高速光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="c2219-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span> 
  
<span data-ttu-id="c2219-107">前端集區是一組前端伺服器，其設定方式相同，並且共同運作，為一般使用者群組提供服務。</span><span class="sxs-lookup"><span data-stu-id="c2219-107">A Front End pool is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="c2219-108">集區可為您的使用者提供延展性及容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="c2219-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="c2219-109">集區中的每部伺服器都必須執行一或多個相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="c2219-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="c2219-110">專為小型組織設計的 Standard Edition 伺服器也會定義集區，並在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="c2219-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="c2219-111">這可讓您將商務用 Skype Server 2019 功能的成本降低，但不會提供真正的高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="c2219-111">This enables you to have Skype for Business Server 2019 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span> 
  
<span data-ttu-id="c2219-112">下列階段說明進行商務用 Skype Server 2019 的集區遷移過程。</span><span class="sxs-lookup"><span data-stu-id="c2219-112">The following phases describe the process of a pool migration to Skype for Business Server 2019.</span></span> <span data-ttu-id="c2219-113">針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。</span><span class="sxs-lookup"><span data-stu-id="c2219-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>
  
1. [<span data-ttu-id="c2219-114">階段 1：規劃移轉</span><span class="sxs-lookup"><span data-stu-id="c2219-114">Phase 1: Plan your migration</span></span>](phase-1-plan-your-migration.md)
    
2. [<span data-ttu-id="c2219-115">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="c2219-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)
    
3. [<span data-ttu-id="c2219-116">階段3：部署商務用 Skype Server 2019 試驗集區</span><span class="sxs-lookup"><span data-stu-id="c2219-116">Phase 3: Deploy Skype for Business Server 2019 pilot pool</span></span>](phase-3-deploy-pilot-pool.md)
    
4. [<span data-ttu-id="c2219-117">階段4：將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="c2219-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)
    
5. [<span data-ttu-id="c2219-118">第5階段：將商務用 Skype Server 2019 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="c2219-118">Phase 5: Add Skype for Business Server 2019 Edge Server to pilot pool</span></span>](phase-5-add-edge-server-to-pilot-pool.md)
    
6. [<span data-ttu-id="c2219-119">階段 6：從試驗部署移至生產</span><span class="sxs-lookup"><span data-stu-id="c2219-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)
    
7. [<span data-ttu-id="c2219-120">階段 7：完成移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="c2219-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)
    
8. [<span data-ttu-id="c2219-121">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="c2219-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)
    

