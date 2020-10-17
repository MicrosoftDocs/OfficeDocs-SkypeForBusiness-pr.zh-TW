---
title: Lync Server 2013： PSTN 閘道的位置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway's location
ms:assetid: 49693a35-fad3-49ee-a71e-c7e4537b79aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994031(v=OCS.15)
ms:contentKeyID: 51803940
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29898244dc0e54da2586d0a58212148c493b96db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512440"
---
# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="0460f-102">Lync Server 2013 中的 PSTN 閘道位置</span><span class="sxs-lookup"><span data-stu-id="0460f-102">PSTN gateway's location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0460f-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0460f-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0460f-104">透過 PSTN 閘道路由傳送的來電和 PBXs 可能需要 Location-Based 路由限制，視這類系統的位置而定。</span><span class="sxs-lookup"><span data-stu-id="0460f-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="0460f-105">您可以在每個主幹基礎上啟用 Location-Based 路由的細微性。</span><span class="sxs-lookup"><span data-stu-id="0460f-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="0460f-106">當主幹上啟用時，Location-Based 路由會引進下列一組規則：</span><span class="sxs-lookup"><span data-stu-id="0460f-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="0460f-107">以每個主幹為基礎啟用 Location-Based 路由時，在該主幹上定義的規則只會套用到透過該主幹路由傳送的來電。</span><span class="sxs-lookup"><span data-stu-id="0460f-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="0460f-108">若要防止 PSTN 電話費旁路，其中的呼叫來自 PSTN 閘道所在的網路網站不同的網站，Location-Based 路由會引入網路網站與指定主幹的關聯。</span><span class="sxs-lookup"><span data-stu-id="0460f-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="0460f-109">這會定義允許通話路由傳送至指定主幹的網路網站。</span><span class="sxs-lookup"><span data-stu-id="0460f-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="0460f-110">您可以透過兩種方式，為 Location-Based 路由啟用主幹：</span><span class="sxs-lookup"><span data-stu-id="0460f-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="0460f-111">骨幹關是針對 egresses 對 PSTN 進行呼叫的 PSTN 閘道所定義。</span><span class="sxs-lookup"><span data-stu-id="0460f-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="0460f-112">以這種類型的主幹路由傳送的來電，只會路由傳送到與主幹位於相同網路網站內的端點。</span><span class="sxs-lookup"><span data-stu-id="0460f-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="0460f-113">主幹的定義是針對不會向 PSTN 和服務使用者提供靜態位置之舊版電話的轉送伺服器對等 (，例如 PBX 電話) 。</span><span class="sxs-lookup"><span data-stu-id="0460f-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="0460f-114">針對此特殊設定，所有由這種類型的主幹路由傳送的來電都會被視為與主幹產生來自相同的網路網站。</span><span class="sxs-lookup"><span data-stu-id="0460f-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="0460f-115">從 PBX 使用者撥打的 Location-Based 路由執行方式，會與與主幹位於相同網路網站的 Lync 使用者相同。</span><span class="sxs-lookup"><span data-stu-id="0460f-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="0460f-116">如果位於不同網路網站的兩個 PBX 系統是透過 Lync Server 連線，Location-Based 路由將允許從一個網路網站的一個 PBX 端點路由傳送到另一個網路網站中的另一個 PBX 端點。</span><span class="sxs-lookup"><span data-stu-id="0460f-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="0460f-117">Location-Based 路由將不會封鎖此案例。</span><span class="sxs-lookup"><span data-stu-id="0460f-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="0460f-118">除了這種情況，以及以相同位置的 Lync 使用者類似的方式，連接至具有此設定之轉送伺服器的端點，也可以撥打或接聽其他轉送伺服器對等的來電，而不是將通話路由傳送至 PSTN (亦即，不論轉送伺服器對等項的網路網站為何，都連接至不同 PBX 的端點) 。</span><span class="sxs-lookup"><span data-stu-id="0460f-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="0460f-119">涉及 PSTN 端點的所有撥入通話、撥出電話、來電轉接及來電，都要視位置為基礎，僅使用定義為本機至此類轉送伺服器對等的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="0460f-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0460f-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0460f-120">See Also</span></span>


[<span data-ttu-id="0460f-121">在 Lync Server 2013 中 Location-Based 路由的指導方針</span><span class="sxs-lookup"><span data-stu-id="0460f-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

