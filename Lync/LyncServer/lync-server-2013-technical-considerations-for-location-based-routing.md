---
title: Lync Server 2013：位置基礎路由的技術考量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical considerations for Location-Based Routing
ms:assetid: 2e2a9199-7c6f-48d3-9adb-3873fc4f8c4e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994027(v=OCS.15)
ms:contentKeyID: 51803936
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 978590484cbb6bd3c23fac26422c186847662e49
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="8b9bc-102">Lync Server 2013 中的位置基礎路由的技術考量</span><span class="sxs-lookup"><span data-stu-id="8b9bc-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b9bc-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="8b9bc-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8b9bc-104">規劃位置路由時，您應該考慮下列案例的影響。</span><span class="sxs-lookup"><span data-stu-id="8b9bc-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="8b9bc-105">嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="8b9bc-105">Disaster Recovery</span></span>

<span data-ttu-id="8b9bc-106">在從主要池到備份池的容錯移轉期間，以及將一般作業還原到主要池時，在災難與恢復程式期間一直都要執行位置式路由。</span><span class="sxs-lookup"><span data-stu-id="8b9bc-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="8b9bc-107">Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="8b9bc-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="8b9bc-108">設定以位置為基礎的路由會影響您部署與 Survivable 分支裝置相關聯之閘道的位置規劃。</span><span class="sxs-lookup"><span data-stu-id="8b9bc-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="8b9bc-109">與您的 SBA 關聯的閘道必須與您的 Survivable 分支裝置位於同一個網路網站;否則，駐留在您 Survivable 分支裝置的使用者將不能在以位置為基礎的路由設定的情況下，發出出站通話。</span><span class="sxs-lookup"><span data-stu-id="8b9bc-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="8b9bc-110">當您的 Survivable 分支裝置與中央網站之間的 WAN 連線為關閉狀態時，會繼續強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="8b9bc-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b9bc-111">請參閱</span><span class="sxs-lookup"><span data-stu-id="8b9bc-111">See Also</span></span>


[<span data-ttu-id="8b9bc-112">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="8b9bc-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

