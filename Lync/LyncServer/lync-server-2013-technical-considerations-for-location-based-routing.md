---
title: Lync Server 2013： Location-Based 路由的技術考慮
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
ms.openlocfilehash: 80364f35ffaf361353815988bcae12f29bca019c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536180"
---
# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f3fc4-102">在 Lync Server 2013 中 Location-Based 路由的技術考慮</span><span class="sxs-lookup"><span data-stu-id="f3fc4-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f3fc4-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f3fc4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f3fc4-104">規劃 Location-Based 路由時，您應該考慮對下列案例的影響。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="f3fc4-105">嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="f3fc4-105">Disaster Recovery</span></span>

<span data-ttu-id="f3fc4-106">在從主要集區容錯移轉至備份組區，以及將一般作業還原至主要集區時，Location-Based 路由會在發生災難和復原程式期間的任何時間保持強制執行。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="f3fc4-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="f3fc4-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="f3fc4-108">設定 Location-Based 路由會影響部署 Survivable 分支裝置相關聯之閘道的規劃。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="f3fc4-109">與您的 SBA 關聯的閘道，必須位於與 Survivable Branch 裝置相同的網路網站中;否則，位於 Survivable Branch 裝置的使用者將不會在設定 Location-Based 路由的情況下，撥打撥出電話。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="f3fc4-110">當您的 Survivable 分支裝置與中央網站之間的 WAN 連線已停機時，Location-Based 路由限制仍會執行。</span><span class="sxs-lookup"><span data-stu-id="f3fc4-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f3fc4-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f3fc4-111">See Also</span></span>


[<span data-ttu-id="f3fc4-112">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="f3fc4-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

