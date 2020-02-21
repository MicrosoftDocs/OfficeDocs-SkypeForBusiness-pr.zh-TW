---
title: Lync Server 2013： 規劃依位置路由
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
ms.openlocfilehash: ef077c82a273a480977a21ca1e2e8b14043cae46
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="0ac98-102">規劃 Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="0ac98-102">Planning for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ac98-103">_**上次修改主題：** 2013年-07-31_</span><span class="sxs-lookup"><span data-stu-id="0ac98-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="0ac98-104">本主題中的資訊適用於 Lync Server 2013 的累計更新： 2 月 2013年。</span><span class="sxs-lookup"><span data-stu-id="0ac98-104">The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.</span></span>

<span data-ttu-id="0ac98-105">位置型的路由可讓您可以限制的 VoIP 端點與位置的呼叫方為基礎的 PSTN 端點之間的通話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="0ac98-105">Location-Based Routing makes it possible to restrict the routing of calls between VoIP endpoints and PSTN endpoints based on the location of the parties in the call.</span></span> <span data-ttu-id="0ac98-106">位置型路由是 Lync Server 2013 Enterprise Voice 基礎結構的一部分。</span><span class="sxs-lookup"><span data-stu-id="0ac98-106">Location-Based Routing is part of the Lync Server 2013 Enterprise Voice infrastructure.</span></span> <span data-ttu-id="0ac98-107">位置型路由會控制如何來電會路由傳送的 Lync Server 2013 CU1 通話管理功能。</span><span class="sxs-lookup"><span data-stu-id="0ac98-107">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="0ac98-108">它會強制執行上是否來電可被路由傳送至 PBX 或 PSTN 端點根據 Lync 發話者的地理位置的通話授權規則。</span><span class="sxs-lookup"><span data-stu-id="0ac98-108">It enforces call authorization rules on whether calls can be routed to PBX or PSTN endpoints based on the Lync caller’s geographic location.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ac98-109">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0ac98-109">In This Section</span></span>

  - [<span data-ttu-id="0ac98-110">Overview of Lync Server 2013 中依位置路由</span><span class="sxs-lookup"><span data-stu-id="0ac98-110">Overview of Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-overview-of-location-based-routing.md)

  - [<span data-ttu-id="0ac98-111">依位置路由 Lync Server 2013 中的指引</span><span class="sxs-lookup"><span data-stu-id="0ac98-111">Guidance for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-guidance-for-location-based-routing.md)

  - [<span data-ttu-id="0ac98-112">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="0ac98-112">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)

  - [<span data-ttu-id="0ac98-113">Lync Server 2013 中的位置型路由的技術考量</span><span class="sxs-lookup"><span data-stu-id="0ac98-113">Technical considerations for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-technical-considerations-for-location-based-routing.md)

  - [<span data-ttu-id="0ac98-114">Lync Server 2013 中的位置型路由的用戶端與伺服器支援</span><span class="sxs-lookup"><span data-stu-id="0ac98-114">Client and server support for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-client-and-server-support-for-location-based-routing.md)

  - [<span data-ttu-id="0ac98-115">不支援的 Lync Server 2013 中的位置型路由功能</span><span class="sxs-lookup"><span data-stu-id="0ac98-115">Capabilities not supported by Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-capabilities-not-supported-by-location-based-routing.md)

  - [<span data-ttu-id="0ac98-116">Lync Server 2013 中的位置型路由的部署程序</span><span class="sxs-lookup"><span data-stu-id="0ac98-116">Deployment process for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-location-based-routing.md)

  - [<span data-ttu-id="0ac98-117">Lync Server 2013 中的會議位置型路由</span><span class="sxs-lookup"><span data-stu-id="0ac98-117">Location-Based Routing for conferencing in Lync Server 2013</span></span>](lync-server-2013-location-based-routing-for-conferencing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ac98-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0ac98-118">See Also</span></span>


[<span data-ttu-id="0ac98-119">規劃 Lync Server 2013 中的 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="0ac98-119">Planning for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-planning-for-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

