---
title: 'Lync Server 2013: PSTN 閘道的位置'
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
ms.openlocfilehash: ef9c58115349e8fedaf25d6f8bc4e1991b65a963
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="pstn-gateways-location-in-lync-server-2013"></a><span data-ttu-id="d4115-102">Lync Server 2013 中的 PSTN 閘道的位置</span><span class="sxs-lookup"><span data-stu-id="d4115-102">PSTN gateway's location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4115-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="d4115-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d4115-104">透過 PSTN 閘道的通話路由傳送，且 Pbx 可能需要根據這類系統的位置的位置型路由限制。</span><span class="sxs-lookup"><span data-stu-id="d4115-104">Calls routed via PSTN gateways and PBXs might require Location-Based Routing restrictions depending on the location of such systems.</span></span> <span data-ttu-id="d4115-105">在每個主幹為基礎的資料粒度，可以啟用位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="d4115-105">Location-Based Routing can be enabled at the granularity on a per trunk basis.</span></span>

<span data-ttu-id="d4115-106">位置型路由引進下列一組規則在主幹上啟用時：</span><span class="sxs-lookup"><span data-stu-id="d4115-106">Location-Based Routing introduces the following set of rules when enabled on a trunk:</span></span>

  - <span data-ttu-id="d4115-107">每個主幹根據啟用位置型路由時，規則會定義上的主幹將只會套用至來電路由傳送到該主幹。</span><span class="sxs-lookup"><span data-stu-id="d4115-107">When Location-Based Routing is enabled on a per trunk basis, the rules define on that trunk will be applied only to calls routed through that trunk.</span></span>

  - <span data-ttu-id="d4115-108">若要防止 PSTN tolls 略過其中呼叫源自網路網站不同的 PSTN 閘道的所在位置的網路網站，位置型路由會介紹指定主幹網路網站的關聯。</span><span class="sxs-lookup"><span data-stu-id="d4115-108">To prevent PSTN tolls bypass where calls originate from a network site different that the network site where the PSTN gateway is located, Location-Based Routing introduces the association of a network site to a given trunk.</span></span> <span data-ttu-id="d4115-109">這是定義網路網站，可讓呼叫路由傳送至指定的主幹。</span><span class="sxs-lookup"><span data-stu-id="d4115-109">This defines the network site that allows calls to be routed to a given trunk.</span></span>

<span data-ttu-id="d4115-110">主幹可以啟用位置型的路由，以兩種方式：</span><span class="sxs-lookup"><span data-stu-id="d4115-110">Trunks can be enabled for Location-Based Routing in two ways:</span></span>

  - <span data-ttu-id="d4115-111">主幹被定義 PSTN 閘道 egresses 撥打至 PSTN。</span><span class="sxs-lookup"><span data-stu-id="d4115-111">The trunk is defined for a PSTN gateway that egresses calls to the PSTN.</span></span> <span data-ttu-id="d4115-112">這種類型的主幹路由傳送來電會路由傳送僅至位於相同網路站台為主幹的端點。</span><span class="sxs-lookup"><span data-stu-id="d4115-112">Incoming calls routed by a trunk of this type will be routed only to endpoints located within the same network site as the trunk.</span></span>

  - <span data-ttu-id="d4115-113">主幹被定義中繼伺服器對等不會輸出通話的 PSTN 和服務的使用者與舊版電話靜態位置 （亦即 PBX 電話）。</span><span class="sxs-lookup"><span data-stu-id="d4115-113">The trunk is defined for a Mediation Server peer that doesn’t egress calls to the PSTN and services users with legacy phones in a static locations (i.e. PBX phones).</span></span> <span data-ttu-id="d4115-114">此特定的組態，這種類型的主幹路由傳送所有來電會被都視為至源自於相同的網路站主幹。</span><span class="sxs-lookup"><span data-stu-id="d4115-114">For this particular configuration, all incoming calls routed by a trunk of this type will be considered to be originating from the same network site as the trunk.</span></span> <span data-ttu-id="d4115-115">PBX 使用者的來電將會有相同的位置型路由強制執行為 Lync 使用者都位於相同網路站台為主幹。</span><span class="sxs-lookup"><span data-stu-id="d4115-115">Calls from PBX users will have the same Location-Based Routing enforcement as Lync users who are located in the same network site as the trunk.</span></span> <span data-ttu-id="d4115-116">如果兩個位於不同的網路站台的 PBX 系統連線到 Lync Server，位置型路由會允許從一個網路站台中的一個 PBX 端點路由傳送至其他網路站台中的另一個 PBX 端點。</span><span class="sxs-lookup"><span data-stu-id="d4115-116">If two PBX systems located in separate network sites are connected through Lync Server, Location-Based Routing will allow routing from one PBX endpoint in one network site to another PBX endpoint in the other network site.</span></span> <span data-ttu-id="d4115-117">此案例不會遭到位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="d4115-117">This scenario will not be blocked by Location-Based Routing.</span></span> <span data-ttu-id="d4115-118">除了此案例中，為 Lync 使用者在相同位置以類似方式連線至與此組態的中繼伺服器對等的端點將能夠撥打或接聽電話到及傳送自其他中繼伺服器對等網路，請勿不將通話路由傳送至 PSTN (i。e.端點連接至不同的 PBX) 不論要將中繼伺服器對等網路相關聯的網站。</span><span class="sxs-lookup"><span data-stu-id="d4115-118">In addition to this scenario and in a similar way as a Lync user in the same location, endpoints connected to a Mediation Server peer with this configuration will be able to make or receive calls to and from other Mediation Server peer that do not route calls to the PSTN (i.e. an endpoint connected to a different PBX) regardless of the network site to which the Mediation Server peer is associated.</span></span> <span data-ttu-id="d4115-119">所有撥入的通話，撥出通話，通話轉接和通話的轉寄涉及 PSTN 端點會受到位置型路由傳送至使用這類中繼伺服器對等的本機定義的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d4115-119">All inbound calls, outbound calls, call transfers and call forwards involving PSTN endpoints will be subject to Location Based Routing to use only PSTN gateways that are defined as local to such Mediation Server peer.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="d4115-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d4115-120">See Also</span></span>


[<span data-ttu-id="d4115-121">依位置路由 Lync Server 2013 中的指引</span><span class="sxs-lookup"><span data-stu-id="d4115-121">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

