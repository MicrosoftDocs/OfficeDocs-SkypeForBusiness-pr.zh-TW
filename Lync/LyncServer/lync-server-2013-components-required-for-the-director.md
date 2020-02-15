---
title: Director 時所需的 Lync Server 2013： 元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4409632afc61aea4606864e7dd230ad4d295935
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="46023-102">Lync Server 2013 中 Director 的必要元件</span><span class="sxs-lookup"><span data-stu-id="46023-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46023-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="46023-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="46023-104">建立及設定 Director 所需的唯一元件是部署 Director 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="46023-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="46023-105">您執行此動作使用拓撲產生器，並定義 Director 集區] 節點中的 [單一電腦集區] 或 [多部電腦集區。</span><span class="sxs-lookup"><span data-stu-id="46023-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="46023-106">之後您已定義 Director 集區]，將會是 Director 的電腦上執行 Lync Server 部署精靈。</span><span class="sxs-lookup"><span data-stu-id="46023-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="46023-107">若是 Director 集區中，您可以執行 Lync Server 部署精靈將會是集區成員的每部伺服器上。</span><span class="sxs-lookup"><span data-stu-id="46023-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="46023-108">拓撲</span><span class="sxs-lookup"><span data-stu-id="46023-108">Topologies</span></span>

<span data-ttu-id="46023-109">您可以實作單一 Director 伺服器或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="46023-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="46023-110">Director 一定是另一部伺服器或集區，沒有與 Lync Server 2013 中的任何其他伺服器角色組合。</span><span class="sxs-lookup"><span data-stu-id="46023-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46023-111">如果您未部署 Director 的前端伺服器或前端集區將會採用 Director 角色。</span><span class="sxs-lookup"><span data-stu-id="46023-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="46023-112">Director 集區必須負載平衡。</span><span class="sxs-lookup"><span data-stu-id="46023-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="46023-113">您可以執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="46023-113">You can do one of the following:</span></span>

  - <span data-ttu-id="46023-114">建立拓撲，針對其他流量類型的 Web 服務和網域名稱系統 (DNS) 負載平衡，使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="46023-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="46023-115">調整式的 Director 集區-DNS 負載平衡與硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46023-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="46023-116">建立使用硬體負載平衡器的負載平衡所需的 Director 集區的拓撲。</span><span class="sxs-lookup"><span data-stu-id="46023-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="46023-117">調整式的 Director 集區-Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="46023-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

