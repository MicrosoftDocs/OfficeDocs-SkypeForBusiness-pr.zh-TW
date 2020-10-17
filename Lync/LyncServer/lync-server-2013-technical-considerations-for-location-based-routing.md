---
title: Lync Server 2013： Location-Based 路由的技術考慮
description: Lync Server 2013： Location-Based 路由的技術考慮。
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
ms.openlocfilehash: 54a025af81ab148ad41f95d0a8cf4f900beb7e00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568049"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="cc685-103">在 Lync Server 2013 中 Location-Based 路由的技術考慮</span><span class="sxs-lookup"><span data-stu-id="cc685-103">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc685-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="cc685-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="cc685-105">規劃 Location-Based 路由時，您應該考慮對下列案例的影響。</span><span class="sxs-lookup"><span data-stu-id="cc685-105">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="cc685-106">嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="cc685-106">Disaster Recovery</span></span>

<span data-ttu-id="cc685-107">在從主要集區容錯移轉至備份組區，以及將一般作業還原至主要集區時，Location-Based 路由會在發生災難和復原程式期間的任何時間保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="cc685-107">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="cc685-108">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="cc685-108">Survivable Branch Appliance</span></span>

<span data-ttu-id="cc685-109">設定 Location-Based 路由會影響部署 Survivable 分支裝置相關聯之閘道的規劃。</span><span class="sxs-lookup"><span data-stu-id="cc685-109">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="cc685-110">與您的 SBA 關聯的閘道，必須位於與 Survivable Branch 裝置相同的網路網站中;否則，位於 Survivable Branch 裝置的使用者將不會在設定 Location-Based 路由的情況下，撥打撥出電話。</span><span class="sxs-lookup"><span data-stu-id="cc685-110">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="cc685-111">當您的 Survivable 分支裝置與中央網站之間的 WAN 連線已停機時，Location-Based 路由限制仍會執行。</span><span class="sxs-lookup"><span data-stu-id="cc685-111">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cc685-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="cc685-112">See Also</span></span>


[<span data-ttu-id="cc685-113">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="cc685-113">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

