---
title: Lync Server 2013： Location-Based 路由的概述
description: Lync Server 2013： Location-Based 路由的概述。
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
ms.openlocfilehash: 0b1e026791a8562629231b91b58d7e7eff569ffa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562809"
---
# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2b86e-103">在 Lync Server 2013 中 Location-Based 路由的概覽</span><span class="sxs-lookup"><span data-stu-id="2b86e-103">Overview of Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b86e-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2b86e-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2b86e-105">Location-Based 路由引進一組新的規則，可修改國內和國際 PSTN 通話的路由，以避免收費旁路。</span><span class="sxs-lookup"><span data-stu-id="2b86e-105">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="2b86e-106">Location-Based 路由可讓您靈活地將這些規則的範圍設定為特定區域、特定閘道或特定使用者集。</span><span class="sxs-lookup"><span data-stu-id="2b86e-106">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="2b86e-107">下列案例說明 Location-Based 路由可強制執行的主要限制類型：</span><span class="sxs-lookup"><span data-stu-id="2b86e-107">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="2b86e-108">出局通話– Location-Based 路由可強制撥出呼叫至位於與來電者防止 PSTN 長途電話旁路之 PSTN 閘道的外撥，這可防止呼叫來自位於其他地區之 PSTN 閘道的外送。</span><span class="sxs-lookup"><span data-stu-id="2b86e-108">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="2b86e-109">進入通話– Location-Based 路由可在撥入電話所在的 PSTN 閘道與呼叫的 Lync 使用者不在相同地區時，防止傳入 PSTN 來電撥打 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="2b86e-109">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="2b86e-110">未知地區– Location-Based 路由會限制位於未決定位置之使用者傳入和傳出 PSTN 來電 (亦即從網際網路連線或位於未知地區) 的遠端使用者。</span><span class="sxs-lookup"><span data-stu-id="2b86e-110">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="2b86e-111">國際地區–如果找不到使用者位置的閘道，Location-Based 路由會透過國際 PSTN 閘道來傳送撥出電話。</span><span class="sxs-lookup"><span data-stu-id="2b86e-111">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="2b86e-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2b86e-112">See Also</span></span>


[<span data-ttu-id="2b86e-113">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="2b86e-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

