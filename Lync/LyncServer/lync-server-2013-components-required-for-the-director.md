---
title: Lync Server 2013：Director 的必要元件
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
ms.openlocfilehash: 12db97a72a9882964727edd3084e0bd598527358
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="4ea9e-102">Lync Server 2013 中 Director 的必要元件</span><span class="sxs-lookup"><span data-stu-id="4ea9e-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4ea9e-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="4ea9e-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="4ea9e-104">建立及設定主管所需的唯一元件是部署控制器伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="4ea9e-105">您可以使用 [拓撲建立器] 來執行這項作業，並在 [控制器] 池節點中定義單一電腦池或多個電腦池。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="4ea9e-106">在您定義主管或主管池之後，請在將是主管的電腦上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="4ea9e-107">在主管池的情況下，您會在每個要成為該池成員的伺服器上執行 Lync Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="4ea9e-108">形</span><span class="sxs-lookup"><span data-stu-id="4ea9e-108">Topologies</span></span>

<span data-ttu-id="4ea9e-109">您可以執行單一控制器伺服器或主管池。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="4ea9e-110">Director 永遠是獨立的伺服器或池，而不是在 Lync Server 2013 中與任何其他伺服器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4ea9e-111">如果您不部署控制器，前端伺服器或前端池會假設主管角色。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="4ea9e-112">控制器池必須是負載平衡的。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="4ea9e-113">您可以執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="4ea9e-113">You can do one of the following:</span></span>

  - <span data-ttu-id="4ea9e-114">針對其他流量類型，建立使用硬體負載平衡器進行 web 服務和網域名稱系統（DNS）負載平衡的拓撲。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="4ea9e-115">Lync Server 2013 中的調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="4ea9e-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="4ea9e-116">針對主管池所需的負載平衡建立使用硬體負載平衡器的拓撲。</span><span class="sxs-lookup"><span data-stu-id="4ea9e-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="4ea9e-117">Lync Server 2013 中的調整式 Director 集區 - 硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="4ea9e-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

