---
title: 調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="1e201-102">Lync Server 2013 中的調整式 Director 集區 - DNS 負載平衡與硬體負載平衡器</span><span class="sxs-lookup"><span data-stu-id="1e201-102">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e201-103">_**主題上次修改日期：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1e201-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1e201-104">已縮放的控制器池（已部署一個以上的控制器來處理額外的容量並提供高可用性）需要負載平衡，才能將用戶端與伺服器通訊發佈到該池的所有成員。</span><span class="sxs-lookup"><span data-stu-id="1e201-104">A scaled Director pool, where there are more than one Director deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="1e201-105">控制器主機 web 服務的方式與前端池非常類似。</span><span class="sxs-lookup"><span data-stu-id="1e201-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="1e201-106">若要提供負載平衡，您可以使用硬體負載平衡或網域名稱系統（DNS）負載平衡與硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1e201-106">To provide the load balancing, you can use either hardware load balancing or domain name system (DNS) load balancing and hardware load balancing.</span></span> <span data-ttu-id="1e201-107">對於 web 服務來說，硬體負載平衡是必要的，而且 DNS 負載平衡本身並不提供 web 服務所需的功能。</span><span class="sxs-lookup"><span data-stu-id="1e201-107">Hardware load balancing is required for the web services, and DNS load balancing alone does not provide the capabilities required for the web services.</span></span>

<span data-ttu-id="1e201-108">下列主題說明使用 DNS 負載平衡結合硬體負載平衡來部署控制器池的規劃考慮。</span><span class="sxs-lookup"><span data-stu-id="1e201-108">The following topics describe the planning considerations for deploying a Director pool using DNS load balancing in conjunction with hardware load balancing.</span></span> <span data-ttu-id="1e201-109">如果您想要使用硬體負載平衡，但不是主管池的 DNS 負載平衡，請參閱[Lync Server 2013 中的 [縮放後的控制器池-硬體負載平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)]，描述該拓撲的規劃需求。</span><span class="sxs-lookup"><span data-stu-id="1e201-109">If you intend to use hardware load balancing, but not DNS load balancing for the Director pool, see the topic [Scaled Director pool - hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="1e201-110">已縮放的![控制器池](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "縮放控制器池")</span><span class="sxs-lookup"><span data-stu-id="1e201-110">![Scaled Director Pool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Scaled Director Pool")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1e201-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="1e201-111">In This Section</span></span>

  - [<span data-ttu-id="1e201-112">Lync Server 2013 中的憑證摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1e201-112">Certificate summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="1e201-113">Lync Server 2013 中的連接埠摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1e201-113">Port summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [<span data-ttu-id="1e201-114">Lync Server 2013 中的 DNS 摘要 - DNS 與 HLB 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1e201-114">DNS summary - DNS and HLB load balanced in Lync Server 2013</span></span>](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

