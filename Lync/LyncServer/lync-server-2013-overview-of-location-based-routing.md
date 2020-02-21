---
title: 'Lync Server 2013: Overview of 依位置路由'
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
ms.openlocfilehash: 85d24aeb94a0c16e93d885c5b6db20385cdf0f26
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="6ea0d-102">Overview of Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="6ea0d-102">Overview of Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ea0d-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="6ea0d-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="6ea0d-104">位置型路由引進了一組新的規則，修改可防止通話費略過的國內和國際 PSTN 通話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-104">Location-Based Routing introduces a new set of rules that modifies the routing of national and international PSTN calls to prevent toll bypass.</span></span> <span data-ttu-id="6ea0d-105">位置型路由提供的彈性來範圍至特定的區域，這些規則特定閘道或特定的使用者只有一組。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-105">Location-Based Routing provides the flexibility to scope these rules to specific regions, specific gateways or to specific set of users only.</span></span>

<span data-ttu-id="6ea0d-106">下列案例說明的限制位置型路由可以強制執行的主要類型：</span><span class="sxs-lookup"><span data-stu-id="6ea0d-106">The following scenarios illustrate the main types of restrictions Location-Based Routing can enforce:</span></span>

  - <span data-ttu-id="6ea0d-107">輸出通話 – 位置型路由可以強制執行輸出從位於同一個區域設為來電者為防止 PSTN 通話費略過，以防止透過 PSTN 閘道位於不同的地區，做為輸出呼叫 PSTN 閘道的撥出電話來電者。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-107">Egress calls – Location-Based Routing can enforce outgoing calls to egress from a PSTN gateway that is located in the same region as where the caller is to prevent PSTN toll bypass, which prevents calls to egress from a PSTN gateway located in a different region as the caller.</span></span>

  - <span data-ttu-id="6ea0d-108">輸入呼叫 – 位置型路由可以防止響鈴 Lync 端點傳入 PSTN 通話如果路由內送呼叫的 PSTN 閘道並非位於受話 Lync 使用者的相同區域。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-108">Ingress calls – Location-Based Routing can prevent incoming PSTN calls to ring Lync endpoints if the PSTN gateway routing the incoming call is not located in the same region as the called Lync user.</span></span>

  - <span data-ttu-id="6ea0d-109">未知的區域 – 位置型路由限制傳入和傳出 PSTN 通話到及傳送自位於未定位置 （亦即遠端使用者從網際網路連接或位於未知的地區） 的使用者。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-109">Unknown regions – Location-Based Routing restricts incoming and outgoing PSTN calls to and from users that are located in undetermined locations (i.e. remote users connecting from the Internet or located in unknown regions).</span></span>

  - <span data-ttu-id="6ea0d-110">國際區域 – 強制執行位置型的路由，路由傳送撥出電話通過國際 PSTN 閘道，如果找不到本機閘道到使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="6ea0d-110">International regions – Location-Based Routing enforces routing of outgoing calls through international PSTN gateways if a gateway local to the user’s location cannot be found.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="6ea0d-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6ea0d-111">See Also</span></span>


[<span data-ttu-id="6ea0d-112">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="6ea0d-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

