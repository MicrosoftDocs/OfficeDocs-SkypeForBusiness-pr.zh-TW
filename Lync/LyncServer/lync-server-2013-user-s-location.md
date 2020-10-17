---
title: Lync Server 2013：使用者位置
description: Lync Server 2013：使用者的位置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User's location
ms:assetid: ce57941d-086b-448e-8ada-c7d636a2a1c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994073(v=OCS.15)
ms:contentKeyID: 51803984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a92ec780809cdb3e1ee582ce6c348c884bbb5890
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561209"
---
# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="41241-103">Lync Server 2013 中的使用者位置</span><span class="sxs-lookup"><span data-stu-id="41241-103">User's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41241-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="41241-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="41241-105">Location-Based 路由利用 E9-1-1、CAC 和媒體旁路所用的 Lync Server 中所定義的相同網路地區、網站和子網，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="41241-105">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="41241-106">使用者的位置取決於使用者 (s) 所連線的 Lync 端點的 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="41241-106">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="41241-107">每個 IP 子網都會與網路網站產生關聯，該網站會匯總成系統管理員所定義的網路地區。</span><span class="sxs-lookup"><span data-stu-id="41241-107">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="41241-108">Location-Based 會根據使用者的網路網站強制進行路由傳送。</span><span class="sxs-lookup"><span data-stu-id="41241-108">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="41241-109">Location-Based 路由規則會依每個網路網站套用，這表示一組指定的規則會套用至位於相同網路網站中 Location-Based 路由的所有啟用端點。</span><span class="sxs-lookup"><span data-stu-id="41241-109">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="41241-110">管理員可以將 Location-Based 路由套用到需要該網站的網站。</span><span class="sxs-lookup"><span data-stu-id="41241-110">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="41241-111">您可以在每個網路網站上定義語音路由策略，以定義特定的 PSTN 閘道，以供位於網路網站中的所有使用者用來呼叫 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="41241-111">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="41241-112">這類語音路由原則會優先于使用者語音原則所定義的路由，當使用者位於啟用 Location-Based 路由的網路網站時，它會防止透過已啟用 Location-Based 路由的其他 PSTN 閘道路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="41241-112">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="41241-113">當 Lync 使用者撥打 PSTN 電話時，使用者的語音原則會決定使用者是否有權進行通話。</span><span class="sxs-lookup"><span data-stu-id="41241-113">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="41241-114">如果使用者的語音原則允許使用者撥打電話，Location-Based 路由決定來電應來自哪個 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="41241-114">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="41241-115">Location-Based 路由會根據使用者的位置來決定這種情況。</span><span class="sxs-lookup"><span data-stu-id="41241-115">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="41241-116">使用者位置可依下列方式分類：</span><span class="sxs-lookup"><span data-stu-id="41241-116">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="41241-117">使用者位於為 Location-Based 路由啟用的已知網路網站，而且他 (直接向內撥號) 號碼會在置於相同網路網站 (的 PSTN 閘道上終止例如，office) 。</span><span class="sxs-lookup"><span data-stu-id="41241-117">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="41241-118">撥出電話的路由會透過使用者所在之網站的語音路由原則進行。</span><span class="sxs-lookup"><span data-stu-id="41241-118">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="41241-119">對使用者的傳入 PSTN 呼叫會路由至位於與 PSTN 閘道位於相同網路網站的端點。</span><span class="sxs-lookup"><span data-stu-id="41241-119">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="41241-120">使用者位於與 PSTN 閘道所在之網路網站不同的已知網路網站。</span><span class="sxs-lookup"><span data-stu-id="41241-120">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="41241-121"> (，亦即，使用者已前往另一部公司辦公室) 。</span><span class="sxs-lookup"><span data-stu-id="41241-121">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="41241-122">撥出電話的路由將使用使用者所在之網路網站的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="41241-122">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="41241-123">對使用者的內送 PSTN 通話不會路由到位於不同于 PSTN 閘道的端點，以避免 PSTN 收費繞過。</span><span class="sxs-lookup"><span data-stu-id="41241-123">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="41241-124">當使用者位於 Lync 伺服器部署無法識別的網站時，撥出電話的路由會根據指派給使用者的語音原則，而不是系結至 Location-Based 路由限制的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="41241-124">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="41241-125">傳入 PSTN 通話不會路由至位於未知網路網站的端點，以避免 PSTN 收費繞過。</span><span class="sxs-lookup"><span data-stu-id="41241-125">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="41241-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="41241-126">See Also</span></span>


[<span data-ttu-id="41241-127">在 Lync Server 2013 中 Location-Based 路由的指導方針</span><span class="sxs-lookup"><span data-stu-id="41241-127">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

