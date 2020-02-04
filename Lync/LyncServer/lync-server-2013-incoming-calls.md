---
title: Lync Server 2013：來電
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
ms.openlocfilehash: e70e5a489cbfa581c666374e6535b898727e1fdc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="27a6e-102">Lync Server 2013 中的來電</span><span class="sxs-lookup"><span data-stu-id="27a6e-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27a6e-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="27a6e-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="27a6e-104">將來電路由至啟用位置路由的使用者，視使用者端點的位置而定。</span><span class="sxs-lookup"><span data-stu-id="27a6e-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="27a6e-105">傳入通話的路由會受到下列方式的影響。</span><span class="sxs-lookup"><span data-stu-id="27a6e-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="27a6e-106">如果使用者有來電至位於以位置為基礎的路由的網路網站中的端點，且端點與 PSTN 閘道位於相同的網路網站中，通話就會路由。</span><span class="sxs-lookup"><span data-stu-id="27a6e-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="27a6e-107">如果使用者有來電至位於支援位置路由的網路網站中的端點，且端點所在的網路網站與 PSTN 閘道不同，則不會路由該通話。</span><span class="sxs-lookup"><span data-stu-id="27a6e-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="27a6e-108">當使用者沒有位於與來電所在的 PSTN 閘道相同網路網站中的端點時，撥入電話會直接路由至使用者的語音信箱，而未接來電通知將會傳送給呼叫方。</span><span class="sxs-lookup"><span data-stu-id="27a6e-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="27a6e-109">已啟用針對位置路由的使用者的來電轉接設定將會繼續生效，不過，轉寄的呼叫將會受到使用者的位置式路由限制。</span><span class="sxs-lookup"><span data-stu-id="27a6e-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="27a6e-110">下表說明根據被呼叫者終點的位置，以位置為基礎的路由會如何影響輸入通話的路由。</span><span class="sxs-lookup"><span data-stu-id="27a6e-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="27a6e-111">PSTN 閘道的網路網站是針對位置路由而啟用，且以位置為基礎的路由只允許將 PSTN 呼叫路由至同一網路網站中的端點。</span><span class="sxs-lookup"><span data-stu-id="27a6e-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="27a6e-112">被呼叫者從 PSTN 接收入站通話</span><span class="sxs-lookup"><span data-stu-id="27a6e-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="27a6e-113">被呼叫者的端點位於與 PSTN 閘道相同的網路網站中</span><span class="sxs-lookup"><span data-stu-id="27a6e-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="27a6e-114">被呼叫者的端點與 PSTN 閘道不在同一個網路網站中</span><span class="sxs-lookup"><span data-stu-id="27a6e-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="27a6e-115">被呼叫方的端點位於未知的網路網站，或未啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="27a6e-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27a6e-116">傳送進貨 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="27a6e-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="27a6e-117">來電是路由到被叫方的端點</span><span class="sxs-lookup"><span data-stu-id="27a6e-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="27a6e-118">來電未路由至被叫方的端點</span><span class="sxs-lookup"><span data-stu-id="27a6e-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="27a6e-119">來電未路由至被叫方的端點</span><span class="sxs-lookup"><span data-stu-id="27a6e-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="27a6e-120">請參閱</span><span class="sxs-lookup"><span data-stu-id="27a6e-120">See Also</span></span>


[<span data-ttu-id="27a6e-121">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="27a6e-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

