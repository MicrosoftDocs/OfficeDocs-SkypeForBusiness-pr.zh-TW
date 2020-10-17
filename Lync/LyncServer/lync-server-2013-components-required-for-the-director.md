---
title: Lync Server 2013： Director 所需的元件
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
ms.openlocfilehash: 1a1461e7edb0b90d7cb3bf3a7238e764a900e50b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502410"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="e3900-102">Lync Server 2013 中的 Director 所需的元件</span><span class="sxs-lookup"><span data-stu-id="e3900-102">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3900-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="e3900-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="e3900-104">建立及設定 Director 所需的唯一元件是部署 Director 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e3900-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="e3900-105">您可以使用拓撲產生器，在 Director 集區節點中定義單一電腦集區或多部電腦集區，以執行這項作業。</span><span class="sxs-lookup"><span data-stu-id="e3900-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="e3900-106">在您定義 Director 或 Director 集區之後，請在將要成為 Director 的電腦上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="e3900-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="e3900-107">在 Director 集區的情況下，您會在將成為集區成員的每台伺服器上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="e3900-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="e3900-108">拓撲</span><span class="sxs-lookup"><span data-stu-id="e3900-108">Topologies</span></span>

<span data-ttu-id="e3900-109">您可以執行單一 Director 伺服器或 Director 集區。</span><span class="sxs-lookup"><span data-stu-id="e3900-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="e3900-110">Director 永遠都是個別的伺服器或集區，而不是組合在 Lync Server 2013 中的任何其他伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="e3900-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3900-111">如果您不部署 Director，前端伺服器或前端集區將會擔當 Director 角色。</span><span class="sxs-lookup"><span data-stu-id="e3900-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="e3900-112">Director 集區必須進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e3900-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="e3900-113">您可以執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="e3900-113">You can do one of the following:</span></span>

  - <span data-ttu-id="e3900-114">建立拓撲，針對其他流量類型的 Web 服務和網域名稱系統 (DNS) 負載平衡，使用硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="e3900-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="e3900-115">Lync Server 2013 中的調整式 Director 集區-DNS 負載平衡與硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="e3900-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="e3900-116">使用硬體負載平衡器建立拓撲，以用於 Director 集區所需的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="e3900-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="e3900-117">Lync Server 2013 中的調整式 Director 集區-硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="e3900-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

