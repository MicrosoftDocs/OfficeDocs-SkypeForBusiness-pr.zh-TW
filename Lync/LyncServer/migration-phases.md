---
title: 遷移階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e877afc67e5dea1bc2feada22e5bbbbe81e15139
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a><span data-ttu-id="154c6-102">遷移階段</span><span class="sxs-lookup"><span data-stu-id="154c6-102">Migration phases</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="154c6-103">_**主題上次修改日期：** 2012年-09-17_</span><span class="sxs-lookup"><span data-stu-id="154c6-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="154c6-104">在 Lync Server 2013 中，您可以定義網站包含 Lync Server 2013 元件您網路上。</span><span class="sxs-lookup"><span data-stu-id="154c6-104">In Lync Server 2013, you define sites on your network that contain Lync Server 2013 components.</span></span> <span data-ttu-id="154c6-105">網站是一組已妥善連接高速、 低延遲的網路，例如單一區域網路 (LAN) 或透過高速光纖並網路連線的兩個網路的電腦。</span><span class="sxs-lookup"><span data-stu-id="154c6-105">A site is a set of computers that are well-connected by a high-speed, low-latency network, such as a single local area network (LAN) or two networks connected by a high-speed fiber optic network.</span></span>

<span data-ttu-id="154c6-106">*前端集區*是一組相同的方式設定的前端伺服器和工時來提供服務給一般使用者群組。</span><span class="sxs-lookup"><span data-stu-id="154c6-106">A *Front End pool* is a set of Front End Servers that are configured identically and work together to provide services for a common group of users.</span></span> <span data-ttu-id="154c6-107">集區可為您的使用者提供延展性及容錯移轉功能。</span><span class="sxs-lookup"><span data-stu-id="154c6-107">A pool provides scalability and failover capability to your users.</span></span> <span data-ttu-id="154c6-108">集區中的每部伺服器都必須執行一或多個相同的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="154c6-108">Each server in a pool must run an identical server role or roles.</span></span> <span data-ttu-id="154c6-109">Standard Edition server，專用於小型組織，也會定義集區，並在單一伺服器上執行。</span><span class="sxs-lookup"><span data-stu-id="154c6-109">A Standard Edition server, designed for small organizations, also defines a pool and runs on a single server.</span></span> <span data-ttu-id="154c6-110">這可讓您有較少的成本，適用於 Lync Server 2013 功能，但並不提供，則為 true 的高可用性解決方案。</span><span class="sxs-lookup"><span data-stu-id="154c6-110">This enables you to have Lync Server 2013 functionality for a lesser cost, but does not provide a true high-availability solution.</span></span>

<span data-ttu-id="154c6-111">下列階段說明從 Lync Server 2010 集區移轉至 Lync Server 2013 的程序。</span><span class="sxs-lookup"><span data-stu-id="154c6-111">The following phases describe the process of a pool migration from Lync Server 2010 to Lync Server 2013.</span></span> <span data-ttu-id="154c6-112">針對含有多個集區的多個站台，每一個集區都應該要遵循此階段式方法。</span><span class="sxs-lookup"><span data-stu-id="154c6-112">For multiple sites containing multiple pools, each individual pool should follow this phased approach.</span></span>

1.  [<span data-ttu-id="154c6-113">階段 1： 規劃從 Lync Server 2010 移轉</span><span class="sxs-lookup"><span data-stu-id="154c6-113">Phase 1: Plan your migration from Lync Server 2010</span></span>](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [<span data-ttu-id="154c6-114">階段 2： 準備移轉</span><span class="sxs-lookup"><span data-stu-id="154c6-114">Phase 2: Prepare for migration</span></span>](phase-2-prepare-for-migration.md)

3.  [<span data-ttu-id="154c6-115">階段 3： 部署 Lync Server 2013 試驗集區</span><span class="sxs-lookup"><span data-stu-id="154c6-115">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [<span data-ttu-id="154c6-116">階段 4： 將測試使用者移至試驗集區</span><span class="sxs-lookup"><span data-stu-id="154c6-116">Phase 4: Move test users to the pilot pool</span></span>](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [<span data-ttu-id="154c6-117">階段 5： 將 Lync Server 2013 Edge Server 新增至試驗集區</span><span class="sxs-lookup"><span data-stu-id="154c6-117">Phase 5: Add Lync Server 2013 Edge Server to pilot pool</span></span>](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [<span data-ttu-id="154c6-118">階段 6： 從試驗部署移至實際執行環境</span><span class="sxs-lookup"><span data-stu-id="154c6-118">Phase 6: Move from pilot deployment into production</span></span>](phase-6-move-from-pilot-deployment-into-production.md)

7.  [<span data-ttu-id="154c6-119">階段 7： 完成移轉後工作</span><span class="sxs-lookup"><span data-stu-id="154c6-119">Phase 7: Complete post-migration tasks</span></span>](phase-7-complete-post-migration-tasks.md)

8.  [<span data-ttu-id="154c6-120">第 8 階段： 解除委任舊版的集區</span><span class="sxs-lookup"><span data-stu-id="154c6-120">Phase 8: Decommission legacy pools</span></span>](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

