---
title: Lync Server 2013： 使用者的位置
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
ms.openlocfilehash: d18ef5092f0506951dd9b431c6a44945b87b7f92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140776"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="247aa-102">Lync Server 2013 中的使用者的位置</span><span class="sxs-lookup"><span data-stu-id="247aa-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="247aa-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="247aa-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="247aa-104">位置型路由的利用相同網路地區、 網站及子 E9-1-1 所使用的 Lync 伺服器中所定義，CAC 以及媒體旁路，將通話路由限制套用防範 PSTN 通話費略過。</span><span class="sxs-lookup"><span data-stu-id="247aa-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="247aa-105">使用者的位置取決於使用者的 Lync 從連線端點的 IP 子網路。</span><span class="sxs-lookup"><span data-stu-id="247aa-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="247aa-106">每個 IP 子網路是與網路網站，這會彙總成管理員所定義的網路地區相關聯。</span><span class="sxs-lookup"><span data-stu-id="247aa-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="247aa-107">位置型路由會強制執行根據使用者的網路網站。</span><span class="sxs-lookup"><span data-stu-id="247aa-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="247aa-108">位置型的路由規則會套用在每個網路網站為基礎，這表示一組指定的規則，將會套用至所有的端點啟用位置型路由位於相同的網路站台內。</span><span class="sxs-lookup"><span data-stu-id="247aa-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="247aa-109">系統管理員可以套用至需要的網路網站的位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="247aa-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="247aa-110">語音路由原則可定義統計網路站台定義特定的 PSTN 閘道應該位於網路網站的所有使用者用來呼叫 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="247aa-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="247aa-111">這類語音路由原則會優先於使用者位於網路網站啟用位置型的路由，而它會防止透過已啟用其他 PSTN 閘道的通話路由傳送時，使用者的語音原則所定義的路由依位置路由。</span><span class="sxs-lookup"><span data-stu-id="247aa-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="247aa-112">Lync 使用者將置於 PSTN 通話，當使用者的語音原則會決定使用者是否可以被授權撥打電話。</span><span class="sxs-lookup"><span data-stu-id="247aa-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="247aa-113">如果使用者的語音原則允許使用者撥打電話，位置型路由會決定從應該 egress 通話的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="247aa-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="247aa-114">位置型路由會判斷根據使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="247aa-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="247aa-115">使用者的位置可以分類方式如下：</span><span class="sxs-lookup"><span data-stu-id="247aa-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="247aa-116">使用者位於啟用位置型路由已知的網路網站，其 DID （直接向內撥號對應表） 號碼終止上放置在相同的網路網站 （亦即辦公室） 的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="247aa-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="247aa-117">路由撥出通話將會透過使用者所在的網路網站的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="247aa-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="247aa-118">給使用者的傳入 PSTN 通話路由傳送至位於與 PSTN 閘道位於相同網路站台的端點。</span><span class="sxs-lookup"><span data-stu-id="247aa-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="247aa-119">使用者位於已知的網路網站，位於不同的 PSTN 閘道的所在位置的網路網站。</span><span class="sxs-lookup"><span data-stu-id="247aa-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="247aa-120">（亦即使用者間傳送至其他公司辦公室）。</span><span class="sxs-lookup"><span data-stu-id="247aa-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="247aa-121">撥出電話路由傳送。 會使用使用者所在的網路網站的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="247aa-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="247aa-122">給使用者的傳入 PSTN 通話不會路由傳送至位於不同的站台比 PSTN 閘道，以避免 PSTN 通話費略過的端點。</span><span class="sxs-lookup"><span data-stu-id="247aa-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="247aa-123">當使用者位於未知至 Lync Server 部署的網路網站時的撥出電話路由會根據指派給使用者未繫結至位置型路由限制的 PSTN 閘道的語音原則。</span><span class="sxs-lookup"><span data-stu-id="247aa-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="247aa-124">傳入 PSTN 通話不會路由傳送至位於不明的網路網站，以防止 PSTN 通話費略過的端點。</span><span class="sxs-lookup"><span data-stu-id="247aa-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="247aa-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="247aa-125">See Also</span></span>


[<span data-ttu-id="247aa-126">依位置路由 Lync Server 2013 中的指引</span><span class="sxs-lookup"><span data-stu-id="247aa-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

