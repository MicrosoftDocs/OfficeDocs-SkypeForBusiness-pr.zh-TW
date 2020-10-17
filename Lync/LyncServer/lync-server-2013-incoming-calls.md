---
title: Lync Server 2013：傳入通話
description: Lync Server 2013：傳入通話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Incoming calls
ms:assetid: 65b9c1b4-6af7-4527-8c33-22c4442bd209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994038(v=OCS.15)
ms:contentKeyID: 51803948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a72c7fc378240f9751eae8e6c24e9cc601b08d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547729"
---
# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="7e1c9-103">Lync Server 2013 中的傳入通話</span><span class="sxs-lookup"><span data-stu-id="7e1c9-103">Incoming calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e1c9-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="7e1c9-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="7e1c9-105">對啟用 Location-Based 路由的使用者進行撥入電話的路由，取決於使用者端點的位置。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-105">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="7e1c9-106">傳入通話的路由會以下列方式受到影響。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-106">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="7e1c9-107">如果使用者對位於啟用網路功能的 Location-Based 路由的網站中的端點進行來電，而該端點位於與 PSTN 閘道相同的網路網站中，則會路由傳送通話。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="7e1c9-108">如果使用者對位於啟用 Location-Based 路由的網路網站中的端點進行來電，而該端點位於與 PSTN 閘道不同的網路網站中，則不會路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-108">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="7e1c9-109">當使用者沒有與撥入電話來源所在的 PSTN 閘道位於相同網路網站時，撥入電話會直接路由傳送至使用者的語音信箱，而且會將未接來電通知傳送給呼叫方。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-109">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="7e1c9-110">已啟用 Location-Based 路由之使用者的「來電轉接」設定會繼續強制執行，不過轉接的來電會受到使用者 Location-Based 路由限制的制約。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-110">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="7e1c9-111">下表說明 Location-Based 路由會如何影響傳入通話的路由，視受話者端點的位置而定。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-111">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="7e1c9-112">PSTN 閘道的網路網站會為 Location-Based 路由啟用，而且 Location-Based 路由只允許將 PSTN 呼叫路由傳送至相同網路網站內的端點。</span><span class="sxs-lookup"><span data-stu-id="7e1c9-112">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="7e1c9-113">被呼叫者從 PSTN 接收輸入呼叫</span><span class="sxs-lookup"><span data-stu-id="7e1c9-113">Callee receiving an inbound call from the PSTN</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="7e1c9-114">被呼叫者的端點位於與 PSTN 閘道相同的網路網站中</span><span class="sxs-lookup"><span data-stu-id="7e1c9-114">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="7e1c9-115">受話者的端點與 PSTN 閘道不位於相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="7e1c9-115">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="7e1c9-116">受話者的端點位於未知的網路網站中，或是未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="7e1c9-116">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7e1c9-117">傳入 PSTN 通話的路由</span><span class="sxs-lookup"><span data-stu-id="7e1c9-117">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="7e1c9-118">撥入電話會路由傳送至受話者的端點</span><span class="sxs-lookup"><span data-stu-id="7e1c9-118">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="7e1c9-119">傳入的呼叫未路由至受話者的端點</span><span class="sxs-lookup"><span data-stu-id="7e1c9-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="7e1c9-120">傳入的呼叫未路由至受話者的端點</span><span class="sxs-lookup"><span data-stu-id="7e1c9-120">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="7e1c9-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7e1c9-121">See Also</span></span>


[<span data-ttu-id="7e1c9-122">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="7e1c9-122">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

