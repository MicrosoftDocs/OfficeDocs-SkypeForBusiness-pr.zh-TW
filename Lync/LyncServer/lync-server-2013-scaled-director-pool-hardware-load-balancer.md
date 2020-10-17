---
title: Lync Server 2013：調整式 Director 集區-硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c812f1276a4f8ac9a23298e3b747e9ba97085378
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510950"
---
# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="c4109-102">Lync Server 2013 中的調整式 Director 集區-硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="c4109-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4109-103">_**主題上次修改日期：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c4109-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c4109-104">調整式 Director 集區，其中有多個 Director 可用於處理其他容量並提供高可用性，需要負載平衡才能將用戶端和伺服器通訊散佈至集區中的所有成員。</span><span class="sxs-lookup"><span data-stu-id="c4109-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="c4109-105">Director 主控 web 服務的方式很像前端集區。</span><span class="sxs-lookup"><span data-stu-id="c4109-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="c4109-106">Web 服務需要硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="c4109-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="c4109-107">下列主題說明使用硬體負載平衡來部署 Director 集區的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="c4109-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="c4109-108">如果您想要使用硬體負載平衡及 Director 集區的 DNS 負載平衡，請參閱 [Lync Server 2013 中的「調整式 Director 集區-DNS 負載平衡與硬體負載平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) 」，描述該拓撲的規劃需求。</span><span class="sxs-lookup"><span data-stu-id="c4109-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="c4109-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="c4109-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c4109-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="c4109-110">In This Section</span></span>

  - [<span data-ttu-id="c4109-111">Lync Server 2013 中的憑證摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="c4109-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="c4109-112">Lync Server 2013 中的埠摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="c4109-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="c4109-113">Lync Server 2013 中的 DNS 摘要-調整式 Director 集區（硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="c4109-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

