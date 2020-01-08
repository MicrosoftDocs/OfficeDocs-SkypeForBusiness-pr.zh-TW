---
title: Lync Server 2013：規劃位置基礎路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3873e8710d6ab70212de7780ef5f34d1436df1d2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="27cd5-102">在 Lync Server 2013 中規劃位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="27cd5-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27cd5-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="27cd5-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="27cd5-104">本主題中的資訊適用于 Lync Server 2013 的累積更新：2月2013。</span><span class="sxs-lookup"><span data-stu-id="27cd5-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="27cd5-105">以位置為基礎的路由可以根據通話中各方的位置，限制 VoIP 端點與 PSTN 端點之間的通話路由。</span><span class="sxs-lookup"><span data-stu-id="27cd5-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="27cd5-106">以位置為基礎的路由是 Lync Server 2013 企業語音結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="27cd5-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="27cd5-107">位置式路由是呼叫管理的功能，可控制 Lync Server 2013 CU1 路由呼叫的方式。</span><span class="sxs-lookup"><span data-stu-id="27cd5-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="27cd5-108">它會強制進行呼叫授權規則，讓您可以根據 Lync 來電者的地理位置，將呼叫路由到 PBX 或 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="27cd5-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="27cd5-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="27cd5-109">In This Section</span></span>

  - [<span data-ttu-id="27cd5-110">Lync Server 2013 中以位置為基礎的路由概覽</span><span class="sxs-lookup"><span data-stu-id="27cd5-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="27cd5-111">Lync Server 2013 中的位置基礎路由指引</span><span class="sxs-lookup"><span data-stu-id="27cd5-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="27cd5-112">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="27cd5-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="27cd5-113">Lync Server 2013 中的位置基礎路由的技術考量</span><span class="sxs-lookup"><span data-stu-id="27cd5-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="27cd5-114">Lync Server 2013 中的位置基礎路由的用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="27cd5-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="27cd5-115">Lync Server 2013 中未受位置基礎路由支援的功能</span><span class="sxs-lookup"><span data-stu-id="27cd5-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="27cd5-116">Lync Server 2013 中的位置基礎路由的部署程序</span><span class="sxs-lookup"><span data-stu-id="27cd5-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="27cd5-117">Lync Server 2013 中以位置為基礎的會議路由</span><span class="sxs-lookup"><span data-stu-id="27cd5-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="27cd5-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="27cd5-118">See Also</span></span>


[<span data-ttu-id="27cd5-119">在 Lync Server 2013 中規劃企業語音</span><span class="sxs-lookup"><span data-stu-id="27cd5-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

