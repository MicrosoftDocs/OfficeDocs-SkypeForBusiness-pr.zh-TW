---
title: Lync Server 2013：使用者位置
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
ms.openlocfilehash: 9754b75b941944a445da33750190b9347aeb9313
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="users-location-in-lync-server-2013"></a><span data-ttu-id="d9103-102">Lync Server 2013 中的使用者位置</span><span class="sxs-lookup"><span data-stu-id="d9103-102">User's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9103-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="d9103-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d9103-104">以位置為基礎的路由利用由 E9 使用的 Lync Server 中定義的網路區域、網站和子網，以及由-1、CAC 和媒體旁路來套用呼叫路由限制，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="d9103-104">Location-Based Routing leverages the same network regions, sites and subnets as defined in Lync Server used by E9-1-1, CAC and Media Bypass to apply call routing restrictions to prevent PSTN toll bypass.</span></span> <span data-ttu-id="d9103-105">使用者的位置是由使用者的 Lync 端點的 IP 子網連線所決定。</span><span class="sxs-lookup"><span data-stu-id="d9103-105">A user’s location is determined by the IP subnet of the user’s Lync endpoint(s) are connected from.</span></span> <span data-ttu-id="d9103-106">每個 IP 子網都與一個網路網站相關聯，該網路網站匯總成系統管理員定義的網路區域。</span><span class="sxs-lookup"><span data-stu-id="d9103-106">Each IP subnet is associated to a network site, which are aggregated into network regions defined by the administrator.</span></span> <span data-ttu-id="d9103-107">根據使用者的網路網站，強制執行以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d9103-107">Location-Based Routing is enforced based on the user’s network site.</span></span>

<span data-ttu-id="d9103-108">根據每個網路網站，會套用以位置為基礎的路由規則，這表示一組指定的規則將會套用至在相同網路網站內以位置為基礎的路由所啟用的所有端點。</span><span class="sxs-lookup"><span data-stu-id="d9103-108">Location-Based Routing rules are applied on a per network site basis, meaning that a given set of rules will be applied to all endpoints enabled for Location-Based Routing that are located within the same network site.</span></span> <span data-ttu-id="d9103-109">系統管理員可以將以位置為基礎的路由套用到需要它的網路網站。</span><span class="sxs-lookup"><span data-stu-id="d9103-109">Administrators can apply Location-Based Routing to network sites that require it.</span></span>

<span data-ttu-id="d9103-110">您可以在每個網路網站上定義語音路由策略，以定義特定 PSTN 閘道，該區域應該由位於網路網站中的所有使用者使用，以呼叫 PSTN 電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d9103-110">Voice routing policies can be defined on a per network site basis to define a particular PSTN gateway that should be used by all users located in the network site to call PSTN phone numbers.</span></span> <span data-ttu-id="d9103-111">當使用者位於已啟用位置路由的網路網站時，此類語音路由策略會優先于使用者語音原則所定義的路由，而且會防止透過其他已啟用的 PSTN 閘道進行呼叫路由以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d9103-111">Such voice routing policies will take precedence over the routing defined by the user’s voice policy when the user is located in a network site enabled for Location-Based Routing, and it will prevent the routing of calls via other PSTN gateways that are enabled for Location-Based Routing.</span></span> <span data-ttu-id="d9103-112">當 Lync 使用者發出 PSTN 通話時，使用者的語音原則會判斷使用者是否有權撥打電話。</span><span class="sxs-lookup"><span data-stu-id="d9103-112">When a Lync user places a PSTN call, the user’s voice policy determines whether the user can be authorized to place the call.</span></span> <span data-ttu-id="d9103-113">如果使用者的語音原則允許使用者撥打電話，則以位置為基礎的路由決定要傳出撥打電話的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d9103-113">If the user’s voice policy allows the user to place the call, Location-Based Routing determines which PSTN gateway the call should egress from.</span></span> <span data-ttu-id="d9103-114">以位置為基礎的路由依據使用者的位置來決定此判斷。</span><span class="sxs-lookup"><span data-stu-id="d9103-114">Location-Based Routing makes this determination based on the user’s location.</span></span>

<span data-ttu-id="d9103-115">使用者位置可以使用下列方式進行分類：</span><span class="sxs-lookup"><span data-stu-id="d9103-115">A user location can be categorized in the following ways:</span></span>

  - <span data-ttu-id="d9103-116">使用者位於已啟用位置路由的已知網路網站，且其已執行（直向內撥號）號碼會在位於相同網路網站（亦即辦公室）的 PSTN 閘道上終止。</span><span class="sxs-lookup"><span data-stu-id="d9103-116">The user is located in a known network site enabled for Location-Based Routing and his DID (Direct Inward Dial) number terminates on a PSTN gateway placed in the same network site (i.e. office).</span></span> <span data-ttu-id="d9103-117">[撥出電話] 的路由將是透過使用者所在之網路網站的語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="d9103-117">The routing of outbound calls will be through the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="d9103-118">對使用者的內向 PSTN 呼叫會路由到與 PSTN 閘道位於相同網路網站的端點。</span><span class="sxs-lookup"><span data-stu-id="d9103-118">Incoming PSTN calls to the user are routed to endpoints that are located in the same network site as the PSTN gateway.</span></span>

  - <span data-ttu-id="d9103-119">使用者位於與 PSTN 閘道所在網路網站不同的已知網路網站中。</span><span class="sxs-lookup"><span data-stu-id="d9103-119">The user is located in a known network site that is in different from the network site where the PSTN gateway is located.</span></span> <span data-ttu-id="d9103-120">（亦即，使用者出差至其他公司辦公室）。</span><span class="sxs-lookup"><span data-stu-id="d9103-120">(i.e. the user traveled to another corporate office).</span></span> <span data-ttu-id="d9103-121">[撥出電話] 的路由將是使用使用者所在網路網站的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="d9103-121">The routing of outbound calls will be using the voice routing policy of the network site in which the user is located.</span></span> <span data-ttu-id="d9103-122">對使用者的內向 PSTN 呼叫將不會路由至 PSTN 閘道以外的端點，以避免 PSTN 長途電話。</span><span class="sxs-lookup"><span data-stu-id="d9103-122">Incoming PSTN calls to the user will not be routed to endpoints that are located in different sites than the PSTN gateway to prevent PSTN toll bypassing.</span></span>

  - <span data-ttu-id="d9103-123">當使用者位於 Lync Server 部署無法識別的網路網站時，傳出通話的路由將根據指派給使用者的語音原則，而不是系結到以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="d9103-123">When a user is located in a network site that is unknown to the Lync Server deployment, the routing of outbound calls will be based on the voice policy assigned to the user to PSTN gateways not bound to Location-Based Routing restrictions.</span></span> <span data-ttu-id="d9103-124">傳入的 PSTN 呼叫將不會路由至位於未知網路網站的端點，以避免 PSTN 長途電話繞過。</span><span class="sxs-lookup"><span data-stu-id="d9103-124">Incoming PSTN calls will not be routed to endpoints that are located in unknown network sites to prevent PSTN toll bypassing.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d9103-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="d9103-125">See Also</span></span>


[<span data-ttu-id="d9103-126">Lync Server 2013 中的位置基礎路由指引</span><span class="sxs-lookup"><span data-stu-id="d9103-126">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

