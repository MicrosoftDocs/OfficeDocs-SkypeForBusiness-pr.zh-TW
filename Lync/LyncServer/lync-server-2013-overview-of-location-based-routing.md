---
title: Lync Server 2013：根據位置的路由簡介
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing
ms:assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994032(v=OCS.15)
ms:contentKeyID: 51803941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07a7db57d506b892fd030efccfb304c7103e1e9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755507"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="38efa-102">Lync Server 2013 中以位置為基礎的路由概覽</span><span class="sxs-lookup"><span data-stu-id="38efa-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38efa-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="38efa-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="38efa-104">以位置為基礎的路由引進了一組新的規則，可修改國內和國際 PSTN 通話的路由，以防止避開長途電話。</span><span class="sxs-lookup"><span data-stu-id="38efa-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="38efa-105">以位置為基礎的路由提供了將這些規則限定為特定區域、特定閘道或只有特定使用者組的彈性。</span><span class="sxs-lookup"><span data-stu-id="38efa-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="38efa-106">下列案例說明主要可以強制執行的限制式基礎路由類型：</span><span class="sxs-lookup"><span data-stu-id="38efa-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="38efa-107">出局通話–以位置為基礎的路由可以強制撥出呼叫至位於與呼叫者避免 PSTN 免付費旁路之區域的 PSTN 閘道，避免從位於不同區域的 PSTN 閘道撥出電話呼叫.</span><span class="sxs-lookup"><span data-stu-id="38efa-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="38efa-108">入站通話–位置式路由可以防止撥出 PSTN 呼叫撥打 Lync 端點，如果 PSTN 閘道路由與呼叫的 Lync 使用者不在同一個區域中。</span><span class="sxs-lookup"><span data-stu-id="38efa-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="38efa-109">[未知區域]-以位置為基礎的路由會將傳入和傳出 PSTN 呼叫傳送給與不確定位置的使用者（亦即從網際網路連線或位於未知區域的遠端使用者）。</span><span class="sxs-lookup"><span data-stu-id="38efa-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="38efa-110">國際區域：以位置為基礎的路由：如果找不到使用者位置的閘道，就會透過國際 PSTN 閘道來傳送撥出通話。</span><span class="sxs-lookup"><span data-stu-id="38efa-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="38efa-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="38efa-111">See Also</span></span>


[<span data-ttu-id="38efa-112">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="38efa-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

