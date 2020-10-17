---
title: Lync Server 2013：規劃 Location-Based 路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Location-Based Routing
ms:assetid: bb035924-6b52-4f0f-8e05-b76864fb9ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994068(v=OCS.15)
ms:contentKeyID: 51803979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 114f92d0963e8d61c4b0854862ff7ebd59a12b64
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522040"
---
# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="a0c9d-102">在 Lync Server 2013 中規劃 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="a0c9d-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0c9d-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="a0c9d-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="a0c9d-104">本主題中的資訊適用于 Lync Server 2013 的累計更新：二月份2013。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="a0c9d-105">Location-Based 路由可讓您根據通話中各方的位置，限制 VoIP 端點和 PSTN 端點之間通話的路由。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="a0c9d-106">Location-Based 路由是 Lync Server 2013 Enterprise Voice 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="a0c9d-107">Location-Based 路由是通話管理功能，可控制 Lync Server 2013 CU1 路由傳送通話的方式。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="a0c9d-108">它會根據 Lync 來電者的地理位置，強制執行呼叫授權規則，以判斷通話是否可以路由傳送至 PBX 或 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="a0c9d-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0c9d-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="a0c9d-109">In This Section</span></span>

  - [<span data-ttu-id="a0c9d-110">在 Lync Server 2013 中 Location-Based 路由的概覽</span><span class="sxs-lookup"><span data-stu-id="a0c9d-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-111">在 Lync Server 2013 中 Location-Based 路由的指導方針</span><span class="sxs-lookup"><span data-stu-id="a0c9d-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-112">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="a0c9d-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-113">在 Lync Server 2013 中 Location-Based 路由的技術考慮</span><span class="sxs-lookup"><span data-stu-id="a0c9d-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-114">Lync Server 2013 中的 Location-Based 路由的用戶端和伺服器支援</span><span class="sxs-lookup"><span data-stu-id="a0c9d-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-115">Lync Server 2013 中 Location-Based 路由不支援的功能</span><span class="sxs-lookup"><span data-stu-id="a0c9d-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-116">Lync Server 2013 中 Location-Based 路由的部署程式</span><span class="sxs-lookup"><span data-stu-id="a0c9d-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="a0c9d-117">Lync Server 2013 中以位置為基礎的會議路由</span><span class="sxs-lookup"><span data-stu-id="a0c9d-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0c9d-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a0c9d-118">See Also</span></span>


[<span data-ttu-id="a0c9d-119">在 Lync Server 2013 中規劃 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="a0c9d-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

