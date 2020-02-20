---
title: 位置型路由的 Lync Server 2013： 技術考量
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
ms.openlocfilehash: e672e35771ec3cc4ecbd3655af350231f1583b52
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-considerations-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="052d2-102">Lync Server 2013 中的位置型路由的技術考量</span><span class="sxs-lookup"><span data-stu-id="052d2-102">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="052d2-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="052d2-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="052d2-104">在規劃位置型的路由，您應該考慮下列案例的影響。</span><span class="sxs-lookup"><span data-stu-id="052d2-104">When planning Location-Based Routing, you should consider the impact to the following scenarios.</span></span>

<div>

## <a name="disaster-recovery"></a><span data-ttu-id="052d2-105">嚴重損壞修復</span><span class="sxs-lookup"><span data-stu-id="052d2-105">Disaster Recovery</span></span>

<span data-ttu-id="052d2-106">從主要集區容錯移轉至備份集區以及期間時還原至主要集區的正常作業，位置型路由維持不強制所有時間期間災害及復原程序。</span><span class="sxs-lookup"><span data-stu-id="052d2-106">During a failover from the primary pool to a backup pool as well as when restoring normal operations to the primary pool, Location-Based Routing remains enforced at all times during a disaster and recovery procedure.</span></span>

</div>

<div>

## <a name="survivable-branch-appliance"></a><span data-ttu-id="052d2-107">Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="052d2-107">Survivable Branch Appliance</span></span>

<span data-ttu-id="052d2-108">設定位置型的路由影響規劃的部署至您 Survivable Branch Appliance 相關聯的閘道。</span><span class="sxs-lookup"><span data-stu-id="052d2-108">Configuring Location-Based Routing impacts the planning of where you deploy the gateways associated to your Survivable Branch Appliances.</span></span> <span data-ttu-id="052d2-109">您 SBA 相關聯的閘道必須位於相同的網路網站，作為您 Survivable Branch Appliance;否則，隸屬於使用者不會允許您 Survivable Branch Appliance 撥打輸出呼叫，如果設定位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="052d2-109">The gateway associated to your SBA must be located in the same network site as your Survivable Branch Appliance; otherwise, users homed on your Survivable Branch Appliance will not be permitted to place outbound calls if Location-Based Routing is configured.</span></span> <span data-ttu-id="052d2-110">向下您 Survivable Branch Appliance 與中央網站之間的 WAN 連線時，會維持強制位置型路由限制。</span><span class="sxs-lookup"><span data-stu-id="052d2-110">When the WAN connection between your Survivable Branch Appliance and the central site is down, Location-Based Routing restrictions remains enforced.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="052d2-111">另請參閱</span><span class="sxs-lookup"><span data-stu-id="052d2-111">See Also</span></span>


[<span data-ttu-id="052d2-112">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="052d2-112">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

