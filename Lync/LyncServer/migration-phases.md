---
title: 遷移階段
description: 遷移階段。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547049"
---
# <a name="migration-phases"></a><span data-ttu-id="f7322-103">遷移階段</span><span class="sxs-lookup"><span data-stu-id="f7322-103">Migration phases</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7322-104">_**主題上次修改日期：** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="f7322-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="f7322-105">在 Lync Server 2013 中，您可以在網路上定義包含 Lync Server 2013 元件的網站。</span><span class="sxs-lookup"><span data-stu-id="f7322-105">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="f7322-106">網站是以高速度、低延遲網路連接的一組電腦，例如單一區域網路 (LAN) 或由高速光纖網路連接的兩個網路。</span><span class="sxs-lookup"><span data-stu-id="f7322-106">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="f7322-107">*前端集*區是一組前端伺服器，其設定方式相同，並且共同運作，為一般使用者群組提供服務。</span><span class="sxs-lookup"><span data-stu-id="f7322-107">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="f7322-108">集區可為您的使用者提供延展性及容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="f7322-108">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="f7322-109">集區中的每部伺服器都必須執行一或多個相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="f7322-109">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="f7322-110">專為小型組織設計的 Standard Edition 伺服器也會定義集區，並在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="f7322-110">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="f7322-111">這可讓您將 Lync Server 2013 功能設為較低的成本，但不會提供真正的高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="f7322-111">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="f7322-112">下列階段說明從 Lync Server 2010 到 Lync Server 2013 的集區遷移過程。</span><span class="sxs-lookup"><span data-stu-id="f7322-112">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="f7322-113">針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。</span><span class="sxs-lookup"><span data-stu-id="f7322-113">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="f7322-114">階段1：規劃從 Lync Server 2010 進行遷移</span><span class="sxs-lookup"><span data-stu-id="f7322-114">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="f7322-115">階段 2：準備移轉</span><span class="sxs-lookup"><span data-stu-id="f7322-115">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="f7322-116">階段3：部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="f7322-116">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="f7322-117">階段4：將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="f7322-117">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="f7322-118">第5階段：將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="f7322-118">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="f7322-119">階段 6：從試驗部署移至生產</span><span class="sxs-lookup"><span data-stu-id="f7322-119">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="f7322-120">階段 7：完成移轉後的工作</span><span class="sxs-lookup"><span data-stu-id="f7322-120">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="f7322-121">階段 8：解除委任舊版集區</span><span class="sxs-lookup"><span data-stu-id="f7322-121">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

