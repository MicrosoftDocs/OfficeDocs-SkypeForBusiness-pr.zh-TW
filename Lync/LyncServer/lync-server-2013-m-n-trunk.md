---
title: 'Lync Server 2013: M:N 主幹'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: M:N trunk
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398971(v=OCS.15)
ms:contentKeyID: 48185592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e18bff7fa6031101f73ba4b5ce11f5a0d3c015
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mn-trunk-in-lync-server-2013"></a><span data-ttu-id="45649-102">Lync Server 2013 中的 M:N 主幹</span><span class="sxs-lookup"><span data-stu-id="45649-102">M:N trunk in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="45649-103">_**主題上次修改日期：** 2012年-10-01_</span><span class="sxs-lookup"><span data-stu-id="45649-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="45649-104">Lync Server 2013 從舊版的通話路由用途定義中的主幹支援較大的彈性。</span><span class="sxs-lookup"><span data-stu-id="45649-104">Lync Server 2013 supports greater flexibility in the definition of a trunk for call routing purposes from previous releases.</span></span> <span data-ttu-id="45649-105">主幹是邏輯和之間的關聯的中繼伺服器接聽連接埠號碼與閘道的聆聽連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="45649-105">A trunk is a logical association between a Mediation Server and listening port number with a gateway and a listening port number.</span></span> <span data-ttu-id="45649-106">這意味著幾件事： 中繼伺服器可以有多個主幹至相同的閘道。中繼伺服器可以有多個主幹不同閘道;相反地閘道可以有多個主幹至不同的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-106">This implies several things: A Mediation Server can have multiple trunks to the same gateway; a Mediation Server can have multiple trunks to different gateways; conversely a gateway can have multiple trunks to different Mediation Servers.</span></span>

<span data-ttu-id="45649-107">仍需要閘道 」 新增至使用拓撲產生器 Lync 拓撲時要建立根主幹。</span><span class="sxs-lookup"><span data-stu-id="45649-107">A root trunk is still required to be created when a gateway is added to the Lync topology using Topology Builder.</span></span> <span data-ttu-id="45649-108">指定的中繼伺服器可以處理的閘道器數目取決於伺服器的處理容量離峰忙線中。</span><span class="sxs-lookup"><span data-stu-id="45649-108">The number of gateways that a given Mediation Server can handle depends on the processing capacity of the server during peak busy hours.</span></span> <span data-ttu-id="45649-109">如果您在部署中繼伺服器中所述的[Lync Server 2013 支援硬體](lync-server-2013-supported-hardware.md)支援文件，然後多少作用中的非旁路呼叫獨立中繼伺服器可以處理的估計值超過 Lync Server 2013 的基本硬體需求的硬體是大約 1000年通話。</span><span class="sxs-lookup"><span data-stu-id="45649-109">If you deploy a Mediation Server on hardware that exceeds the minimum hardware requirements for Lync Server 2013, as described in [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) in the Supportability documentation, then the estimate of how many active non-bypass calls a stand-alone Mediation Server can handle is approximately 1000 calls.</span></span> <span data-ttu-id="45649-110">當部署這些規格，中繼伺服器預期會在執行轉碼，但仍將通話路由傳送多個閘道即使閘道不支援的硬體會議媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="45649-110">When deployed on hardware meeting these specifications, the Mediation Server is expected to perform transcoding, but still route calls for multiple gateways even if the gateways do not support media bypass.</span></span>

<span data-ttu-id="45649-111">時定義電話路由，請指定該路由，相關聯的主幹，但未指定此中繼伺服器相關聯的路由。</span><span class="sxs-lookup"><span data-stu-id="45649-111">When defining a call route, you specify the trunks associated with that route, but you do not specify which Mediation Servers are associated with that route.</span></span> <span data-ttu-id="45649-112">相反地，您可以使用拓撲產生器主幹建立關聯的中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-112">Instead, you use Topology Builder to associate trunks with Mediation Servers.</span></span> <span data-ttu-id="45649-113">換句話說，路由會判斷哪一個主幹，用於通話，並接著，與該主幹相關聯之中繼伺服器會傳送該通話的訊號。</span><span class="sxs-lookup"><span data-stu-id="45649-113">In other words, routing determines which trunk to use for a call, and, subsequently, the Mediation Server associated with that trunk is sent the signaling for that call.</span></span>

<span data-ttu-id="45649-114">中繼伺服器可部署為集區;此集區可以組合與前端集區，或其可部署為獨立集區。</span><span class="sxs-lookup"><span data-stu-id="45649-114">The Mediation Server can be deployed as a pool; this pool can be collocated with a Front End pool, or it can be deployed as a stand-alone pool.</span></span> <span data-ttu-id="45649-115">當中繼伺服器已組合與前端集區時，集區的大小可以是大小的最多 12 （登錄器集區限制）。</span><span class="sxs-lookup"><span data-stu-id="45649-115">When a Mediation Server is collocated with a Front End pool, the pool size can be at most 12 (the limit of the Registrar pool size).</span></span> <span data-ttu-id="45649-116">數位簽章這些新功能增加的可靠性與部署彈性的中繼伺服器，但他們需要下列的對等實體中相關聯的功能：</span><span class="sxs-lookup"><span data-stu-id="45649-116">Taken together, these new capabilities increase the reliability and deployment flexibility for Mediation Servers, but they require associated capabilities in the following peer entities:</span></span>

  - <span data-ttu-id="45649-117">**PSTN 閘道。**</span><span class="sxs-lookup"><span data-stu-id="45649-117">**PSTN gateway.**</span></span> <span data-ttu-id="45649-118">Lync Server 2013 合格的閘道必須實作 DNS 負載平衡，以便做為一個集區的中繼伺服器，進而負載達到負載平衡呼叫負載平衡器集區之間之合格公用交換的電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="45649-118">A Lync Server 2013 qualified gateway must implement DNS load balancing, which enables a qualified public switched telephone network (PSTN) gateway to act as a load balancer for one pool of Mediation Servers, and thereby to load-balance calls across the pool.</span></span>

  - <span data-ttu-id="45649-119">**工作階段邊界控制器。**</span><span class="sxs-lookup"><span data-stu-id="45649-119">**Session Border Controller.**</span></span> <span data-ttu-id="45649-120">SIP 主幹，對等實體為網際網路電話語音服務提供者的工作階段邊界控制器 (SBC)。</span><span class="sxs-lookup"><span data-stu-id="45649-120">For a SIP trunk, the peer entity is a Session Border Controller (SBC) at an Internet telephony service provider.</span></span> <span data-ttu-id="45649-121">在 SBC 的中繼伺服器集區的方向，SBC 可以接收來自集區中任何中繼伺服器的連線。</span><span class="sxs-lookup"><span data-stu-id="45649-121">In the direction from the Mediation Server pool to the SBC, the SBC can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="45649-122">在集區的方向從 SBC，流量可以傳送至集區中任何中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-122">In the direction from the SBC to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="45649-123">達成這的一種方法是透過 DNS 負載平衡，如果服務提供者和 SBC 支援。</span><span class="sxs-lookup"><span data-stu-id="45649-123">One method of achieving this is through DNS load balancing, if supported by the service provider and SBC.</span></span> <span data-ttu-id="45649-124">另一種方法是讓服務提供者的集區] 中的所有中繼伺服器的 IP 位址和服務提供者會佈建這些中其 SBC 為個別的 SIP 主幹的每一部中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-124">An alternative is to give the service provider the IP addresses of all Mediation Servers in the pool, and the service provider will provision these in their SBC as a separate SIP trunk for each Mediation Server.</span></span> <span data-ttu-id="45649-125">服務提供者會接著處理負載平衡的本身伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-125">The service provider will then handle the load balancing for its own servers.</span></span> <span data-ttu-id="45649-126">並非所有服務提供者或 Sbc 可能都支援這些功能。</span><span class="sxs-lookup"><span data-stu-id="45649-126">Not all service providers or SBCs may support these capabilities.</span></span> <span data-ttu-id="45649-127">此外，服務提供者可能額外收費的這項功能。</span><span class="sxs-lookup"><span data-stu-id="45649-127">Furthermore, the service provider may charge extra for this capability.</span></span> <span data-ttu-id="45649-128">一般而言，每個 SIP 主幹，以將 SBC 會帶來月費。</span><span class="sxs-lookup"><span data-stu-id="45649-128">Typically, each SIP trunk to the SBC incurs a monthly fee.</span></span>

  - <span data-ttu-id="45649-129">**IP PBX。**</span><span class="sxs-lookup"><span data-stu-id="45649-129">**IP-PBX.**</span></span> <span data-ttu-id="45649-130">在 IP PBX SIP 終止的中繼伺服器集區的方向，IP PBX 可以接收來自集區中任何中繼伺服器的連線。</span><span class="sxs-lookup"><span data-stu-id="45649-130">In the direction from the Mediation Server pool to the IP-PBX SIP termination, the IP-PBX can receive connections from any Mediation Server in the pool.</span></span> <span data-ttu-id="45649-131">在集區的方向從 IP PBX，流量可以傳送至集區中任何中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-131">In the direction from the IP-PBX to the pool, traffic can be sent to any Mediation Server in the pool.</span></span> <span data-ttu-id="45649-132">因為大部分的 Ip-pbx 不支援 DNS 負載平衡，我們建議從 IP-PBX 定義個別的直接 SIP 連線，為集區中每個中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="45649-132">Because most IP-PBXs do not support DNS load balancing, we recommend that individual direct SIP connections be defined from the IP-PBX to each Mediation Server in the pool.</span></span> <span data-ttu-id="45649-133">IP PBX 會再處理自己負載平衡流量分散至透過 [主幹] 群組。</span><span class="sxs-lookup"><span data-stu-id="45649-133">The IP-PBX will then handle its own load balancing by distributing traffic over the trunk group.</span></span> <span data-ttu-id="45649-134">假設是主幹群組在 IP PBX 有一致的路由規則集合。</span><span class="sxs-lookup"><span data-stu-id="45649-134">The assumption is that the trunk group has a consistent set of routing rules at the IP-PBX.</span></span> <span data-ttu-id="45649-135">是否特定 IP PBX 支援此主幹群組概念，以及如何它與 IP PBX 的自己備援交集和叢集架構需要判斷之前您可以決定的中繼伺服器叢集與 IP PBX 可以正確進行互動。</span><span class="sxs-lookup"><span data-stu-id="45649-135">Whether a particular IP-PBX supports this trunk group concept and how it intersects with the IP-PBX’s own redundancy and clustering architecture needs to be determined before you can decide whether a Mediation Server cluster can interact correctly with an IP-PBX.</span></span>

<span data-ttu-id="45649-136">中繼伺服器集區必須有與它互動的對等閘道的統一檢視。</span><span class="sxs-lookup"><span data-stu-id="45649-136">A Mediation Server pool must have a uniform view of the peer gateway with which it interacts.</span></span> <span data-ttu-id="45649-137">這表示集區中的所有成員存取對等閘道的相同定義從設定存放區，並同樣也可能會與其互動的撥出電話。</span><span class="sxs-lookup"><span data-stu-id="45649-137">This means that all members of the pool access the same definition of the peer gateway from the configuration store and are equally likely to interact with it for outgoing calls.</span></span> <span data-ttu-id="45649-138">因此，沒有任何方法可以分割區，以便有些中繼伺服器與僅限撥出電話的特定閘道對等通訊。</span><span class="sxs-lookup"><span data-stu-id="45649-138">Therefore, there is no way to segment the pool so that some Mediation Servers communicate with only certain gateway peers for outgoing calls.</span></span> <span data-ttu-id="45649-139">如果這類分割為必要，必須使用獨立中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="45649-139">If such segmentation is necessary, a separate pool of Mediation Servers must be used.</span></span> <span data-ttu-id="45649-140">這是案例，例如，如果在 PSTN 閘道、 SIP 主幹或 IP Pbx 互動稍早在本主題中詳述的集區相關聯的功能不存在。</span><span class="sxs-lookup"><span data-stu-id="45649-140">This would be the case, for example, if the associated capabilities in PSTN gateways, SIP trunks, or IP-PBXs to interact with a pool as detailed earlier in this topic are not present.</span></span>

<span data-ttu-id="45649-141">特定的 PSTN 閘道、 IP PBX 或 SIP 主幹對等網路可以路由傳送至多個中繼伺服器或主幹。</span><span class="sxs-lookup"><span data-stu-id="45649-141">A particular PSTN gateway, IP-PBX, or SIP trunk peer can route to multiple Mediation Servers or trunks.</span></span> <span data-ttu-id="45649-142">特定中繼伺服器集區可以控制的閘道器數目取決於使用媒體旁路的通話數目。</span><span class="sxs-lookup"><span data-stu-id="45649-142">The number of gateways that a particular pool of Mediation Servers can control depends on the number of calls that use media bypass.</span></span> <span data-ttu-id="45649-143">如果大量通話使用媒體旁路，中繼伺服器集區中可以處理許多的多個呼叫，因為是必要的唯一信號層處理。</span><span class="sxs-lookup"><span data-stu-id="45649-143">If a large number of calls use media bypass, a Mediation Server in the pool can handle many more calls, because only signaling layer processing is necessary.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

