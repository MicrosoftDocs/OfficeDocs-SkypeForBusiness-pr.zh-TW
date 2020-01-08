---
title: Lync Server 2013： M:N 幹線
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a99a76c2291b8ffcfcb1c68367ab6a999211c24f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a><span data-ttu-id="abea9-102">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="abea9-102">M:N trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abea9-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="abea9-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="abea9-104">Lync Server 2013 支援從先前的版本進行呼叫路由的主幹定義中有更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="abea9-104">Lync Server 2013 supports greater flexibility in the definition of a trunk for call routing purposes from previous releases.</span></span> <span data-ttu-id="abea9-105">主幹是在中繼伺服器與偵聽埠號碼之間的邏輯關聯，並具有閘道和偵聽埠號碼。</span><span class="sxs-lookup"><span data-stu-id="abea9-105">A trunk is a logical association between a Mediation Server and listening port number with a gateway and a listening port number.</span></span> <span data-ttu-id="abea9-106">這表示以下幾點：中繼伺服器可以有多個 trunks 至同一個閘道;中繼伺服器可以有多個 trunks 至不同的閘道;相反地，閘道可以有多個 trunks 給不同的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="abea9-106">This implies several things: A Mediation Server can have multiple trunks to the same gateway; a Mediation Server can have multiple trunks to different gateways; conversely a gateway can have multiple trunks to different Mediation Servers.</span></span>

<span data-ttu-id="abea9-107">使用拓撲建立器在 Lync 拓撲中新增閘道時，仍需要建立根幹線。</span><span class="sxs-lookup"><span data-stu-id="abea9-107">A root trunk is still required to be created when a gateway is added to the Lync topology using Topology Builder.</span></span> <span data-ttu-id="abea9-108">指定的中繼伺服器可以處理的閘道數目，取決於高峰期繁忙期間內伺服器的處理能力。</span><span class="sxs-lookup"><span data-stu-id="abea9-108">The number of gateways that a given Mediation Server can handle depends on the processing capacity of the server during peak busy hours.</span></span> <span data-ttu-id="abea9-109">如果您在硬體上部署超過 Lync Server 2013 最低硬體需求的中繼伺服器，請參閱可支援檔中的[Lync server 2013 支援硬體](lync-server-2013-supported-hardware.md)中所述，然後估計在獨立的中繼伺服器可以處理的情況大約是1000個通話。</span><span class="sxs-lookup"><span data-stu-id="abea9-109">If you deploy a Mediation Server on hardware that exceeds the minimum hardware requirements for Lync Server 2013, as described in [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation, then the estimate of how many active non-bypass calls a stand-alone Mediation Server can handle is approximately 1000 calls.</span></span> <span data-ttu-id="abea9-110">當您在硬體上部署這些規範時，轉送伺服器應該會執行轉碼，但仍會傳送多個閘道的呼叫，即使閘道不支援媒體旁路也一樣。</span><span class="sxs-lookup"><span data-stu-id="abea9-110">When deployed on hardware meeting these specifications, the Mediation Server is expected to perform transcoding, but still route calls for multiple gateways even if the gateways do not support media bypass.</span></span>

<span data-ttu-id="abea9-111">定義通話路線時，您可以指定與該路線相關聯的 trunks，但不會指定哪些中繼伺服器與該路由相關聯。</span><span class="sxs-lookup"><span data-stu-id="abea9-111">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with that route.</span></span> <span data-ttu-id="abea9-112">相反地，您可以使用拓撲建立器，將 trunks 與中繼伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="abea9-112">Instead, you use Topology Builder to associate trunks with Mediation Servers.</span></span> <span data-ttu-id="abea9-113">換句話說，路由會決定要使用哪個幹線來進行通話，然後再將與該主幹相關的中繼伺服器傳送給該通話。</span><span class="sxs-lookup"><span data-stu-id="abea9-113">In other words, routing determines which trunk to use for a call, and, subsequently, the Mediation Server associated with that trunk is sent the signaling for that call.</span></span>

<span data-ttu-id="abea9-114">您可以將中繼伺服器部署成一個池;此池可以與前端池 collocated，也可以將它部署為獨立的池。</span><span class="sxs-lookup"><span data-stu-id="abea9-114">The Mediation Server can be deployed as a pool; this pool can be collocated with a Front End pool, or it can be deployed as a stand-alone pool.</span></span> <span data-ttu-id="abea9-115">當使用前端池 collocated 轉送伺服器時，池子大小最多可以是12（註冊機構池大小的限制）。</span><span class="sxs-lookup"><span data-stu-id="abea9-115">When a Mediation Server is collocated with a Front End pool, the pool size can be at most 12 (the limit of the Registrar pool size).</span></span> <span data-ttu-id="abea9-116">總之，這些新功能可提高中繼伺服器的可靠性和部署靈活性，但在下列對等實體中需要相關的功能：</span><span class="sxs-lookup"><span data-stu-id="abea9-116">Taken together, these new capabilities increase the reliability and deployment flexibility for Mediation Servers, but they require associated capabilities in the following peer entities:</span></span>

  - <span data-ttu-id="abea9-117">**PSTN 閘道。**</span><span class="sxs-lookup"><span data-stu-id="abea9-117">**PSTN gateway.**</span></span> <span data-ttu-id="abea9-118">Lync Server 2013 合格的閘道必須實現 DNS 負載平衡，這可讓合格的公用交換電話網絡（PSTN）閘道充當一個中繼伺服器池的負載平衡器，進而在整個池中進行負載平衡通話。</span><span class="sxs-lookup"><span data-stu-id="abea9-118">A Lync Server 2013 qualified gateway must implement DNS load balancing, which enables a qualified public switched telephone network (PSTN) gateway to act as a load balancer for one pool of Mediation Servers, and thereby to load-balance calls across the pool.</span></span>

  - <span data-ttu-id="abea9-119">**會話邊界控制器。**</span><span class="sxs-lookup"><span data-stu-id="abea9-119">**Session Border Controller.**</span></span> <span data-ttu-id="abea9-120">對 SIP 主幹而言，對等實體是網際網路電話服務提供者的會話邊界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="abea9-120">For a SIP trunk, the peer entity is a Session Border Controller (SBC) at an Internet telephony service provider.</span></span> <span data-ttu-id="abea9-121">從中繼伺服器池到 SBC 的方向，SBC 可以從池中的任何中繼伺服器接收連線。</span><span class="sxs-lookup"><span data-stu-id="abea9-121">In the direction from the Mediation Server pool to the SBC, the SBC can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="abea9-122">從 SBC 到該池的方向，流量可以傳送到池中的任何中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="abea9-122">In the direction from the SBC to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="abea9-123">完成這項工作的其中一個方法是透過 DNS 負載平衡（如果服務提供者和 SBC 支援）。</span><span class="sxs-lookup"><span data-stu-id="abea9-123">One method of achieving this is through DNS load balancing, if supported by the service provider and SBC.</span></span> <span data-ttu-id="abea9-124">另一種方法是為服務提供者提供池中所有中繼伺服器的 IP 位址，而服務提供者將在其 SBC 中將這些資源設定為每個中繼伺服器的個別 SIP 幹線。</span><span class="sxs-lookup"><span data-stu-id="abea9-124">An alternative is to give the service provider the IP addresses of all Mediation Servers in the pool, and the service provider will provision these in their SBC as a separate SIP trunk for each Mediation Server.</span></span> <span data-ttu-id="abea9-125">然後服務提供者就會處理自己伺服器的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="abea9-125">The service provider will then handle the load balancing for its own servers.</span></span> <span data-ttu-id="abea9-126">並非所有服務提供者或 SBCs 都可能支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="abea9-126">Not all service providers or SBCs may support these capabilities.</span></span> <span data-ttu-id="abea9-127">此外，服務提供者可能會針對這項功能收取額外費用。</span><span class="sxs-lookup"><span data-stu-id="abea9-127">Furthermore, the service provider may charge extra for this capability.</span></span> <span data-ttu-id="abea9-128">一般來說，SBC 的每個 SIP 幹線都會產生每月費用。</span><span class="sxs-lookup"><span data-stu-id="abea9-128">Typically, each SIP trunk to the SBC incurs a monthly fee.</span></span>

  - <span data-ttu-id="abea9-129">**IP-PBX。**</span><span class="sxs-lookup"><span data-stu-id="abea9-129">**IP-PBX.**</span></span> <span data-ttu-id="abea9-130">從中繼伺服器池到 IP PBX SIP 終止方向，IP PBX 可以從池中的任何中繼伺服器接收連線。</span><span class="sxs-lookup"><span data-stu-id="abea9-130">In the direction from the Mediation Server pool to the IP-PBX SIP termination, the IP-PBX can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="abea9-131">從 IP PBX 到池中的方向，流量可以傳送到池中的任何中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="abea9-131">In the direction from the IP-PBX to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="abea9-132">因為大部分的 IP Pbx 不支援 DNS 負載平衡，所以建議您從 IP PBX 將個別的直接 SIP 連線定義到池中的每個轉送伺服器。</span><span class="sxs-lookup"><span data-stu-id="abea9-132">Because most IP-PBXs do not support DNS load balancing, we recommend that individual direct SIP connections be defined from the IP-PBX to each Mediation Server in the pool.</span></span> <span data-ttu-id="abea9-133">然後，IP PBX 會透過將流量散佈到幹線群組來處理自己的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="abea9-133">The IP-PBX will then handle its own load balancing by distributing traffic over the trunk group.</span></span> <span data-ttu-id="abea9-134">假設 [幹線] 群組在 IP-PBX 中有一致的一組路由規則。</span><span class="sxs-lookup"><span data-stu-id="abea9-134">The assumption is that the trunk group has a consistent set of routing rules at the IP-PBX.</span></span> <span data-ttu-id="abea9-135">特定的 IP PBX 是否支援此幹線群組概念，以及它與 IP PBX 本身的冗余和群集架構的交集，必須先加以決定，才能判斷出轉送伺服器叢集是否可以正確地與 IP PBX 進行互動。</span><span class="sxs-lookup"><span data-stu-id="abea9-135">Whether a particular IP-PBX supports this trunk group concept and how it intersects with the IP-PBX’s own redundancy and clustering architecture needs to be determined before you can decide whether a Mediation Server cluster can interact correctly with an IP-PBX.</span></span>

<span data-ttu-id="abea9-136">中繼伺服器池必須具有與其互動之對等閘道的統一視圖。</span><span class="sxs-lookup"><span data-stu-id="abea9-136">A Mediation Server pool must have a uniform view of the peer gateway with which it interacts.</span></span> <span data-ttu-id="abea9-137">這表示該資源的所有成員都能從 [配置] 存放區存取相同的對等閘道定義，而且與撥出通話一樣很可能與它互動。</span><span class="sxs-lookup"><span data-stu-id="abea9-137">This means that all members of the pool access the same definition of the peer gateway from the configuration store and are equally likely to interact with it for outgoing calls.</span></span> <span data-ttu-id="abea9-138">因此，您無法分割池，因此有些中繼伺服器只會與特定閘道對等的撥出電話進行通訊。</span><span class="sxs-lookup"><span data-stu-id="abea9-138">Therefore, there is no way to segment the pool so that some Mediation Servers communicate with only certain gateway peers for outgoing calls.</span></span> <span data-ttu-id="abea9-139">如果這類分段是必要的，則必須使用單獨的中繼伺服器池。</span><span class="sxs-lookup"><span data-stu-id="abea9-139">If such segmentation is necessary, a separate pool of Mediation Servers must be used.</span></span> <span data-ttu-id="abea9-140">例如，如果 PSTN 閘道、SIP trunks 或 IP-Pbx 中的相關功能與某個池互動（如本主題前面所述），就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="abea9-140">This would be the case, for example, if the associated capabilities in PSTN gateways, SIP trunks, or IP-PBXs to interact with a pool as detailed earlier in this topic are not present.</span></span>

<span data-ttu-id="abea9-141">特定 PSTN 閘道、IP PBX 或 SIP 中繼對等可以傳送到多個中繼伺服器或 trunks。</span><span class="sxs-lookup"><span data-stu-id="abea9-141">A particular PSTN gateway, IP-PBX, or SIP trunk peer can route to multiple Mediation Servers or trunks.</span></span> <span data-ttu-id="abea9-142">特定的中繼伺服器池可以控制的閘道數目，視使用媒體旁路的呼叫數量而定。</span><span class="sxs-lookup"><span data-stu-id="abea9-142">The number of gateways that a particular pool of Mediation Servers can control depends on the number of calls that use media bypass.</span></span> <span data-ttu-id="abea9-143">如果大量的呼叫使用媒體旁路，則池中的中繼伺服器可以處理更多的呼叫，因為只需要傳輸圖層處理。</span><span class="sxs-lookup"><span data-stu-id="abea9-143">If a large number of calls use media bypass, a Mediation Server in the pool can handle many more calls, because only signaling layer processing is necessary.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

