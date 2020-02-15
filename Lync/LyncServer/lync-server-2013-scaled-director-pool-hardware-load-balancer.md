---
title: Lync Server 2013： 調整式 Director 集區-硬體負載平衡器
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
ms.openlocfilehash: 63d690c224556953086128b8d7fc52f2d72f6b06
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="8feee-102">調整式的 Director 集區-Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="8feee-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8feee-103">_**主題上次修改日期：** 2012年-09-08_</span><span class="sxs-lookup"><span data-stu-id="8feee-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8feee-104">調整式的 Director 集區，其中有一個以上的處理更大的容量，並提供高可用性部署 Director 需要負載平衡來發佈至的集區的所有成員的用戶端和伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="8feee-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="8feee-105">Director 主機 web 服務非常類似的前端集區。</span><span class="sxs-lookup"><span data-stu-id="8feee-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="8feee-106">硬體負載平衡是必要的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="8feee-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="8feee-107">下列主題說明部署 Director 集區使用硬體負載平衡規劃的考量。</span><span class="sxs-lookup"><span data-stu-id="8feee-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="8feee-108">如果您想要使用硬體負載平衡和 DNS 負載平衡的 Director 集區，請參閱主題[調整式 Director 集區-DNS 負載平衡與硬體負載平衡器 Lync Server 2013 中的](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)，描述該拓撲的規劃需求。</span><span class="sxs-lookup"><span data-stu-id="8feee-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="8feee-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="8feee-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8feee-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="8feee-110">In This Section</span></span>

  - [<span data-ttu-id="8feee-111">憑證摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="8feee-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="8feee-112">連接埠摘要-調整式 Director 集區、 Lync Server 2013 中的硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="8feee-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="8feee-113">DNS 摘要-調整式 Director 集區、 硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8feee-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

