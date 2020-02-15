---
title: Lync Server 2013： 內送呼叫
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
ms.openlocfilehash: c153af6e14c291189f714f7054f72301d6859a88
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="incoming-calls-in-lync-server-2013"></a><span data-ttu-id="8d0f1-102">Lync Server 2013 中的來電</span><span class="sxs-lookup"><span data-stu-id="8d0f1-102">Incoming calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d0f1-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="8d0f1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="8d0f1-104">路由傳送來電至使用者啟用位置型的路由，取決於使用者的端點的位置。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-104">The routing of incoming calls to users enabled for Location-Based Routing depends on the location of the user’s endpoint.</span></span> <span data-ttu-id="8d0f1-105">以下列方式，受影響的內送呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-105">The routing of incoming calls is affected in the following way.</span></span> <span data-ttu-id="8d0f1-106">如果使用者有來電轉接至位於位置型的路由端點已啟用的網路網站，並端點位於相同網路網站與 PSTN 閘道，來電會路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-106">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in the same network site as the PSTN gateway, the call will be routed.</span></span> <span data-ttu-id="8d0f1-107">如果使用者有來電轉接至位於位置型的路由端點已啟用的網路網站，並端點位於不同的網路站台比 PSTN 閘道，不會路由傳送來電。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-107">If a user has an incoming call to an endpoint located in a Location-Based Routing enabled network site, and the endpoint is located in a different network site than the PSTN gateway, the call will not be routed.</span></span> <span data-ttu-id="8d0f1-108">當使用者不具有位於相同的網路網站與 PSTN 閘道來電源自其中任何端點時，來電會被直接路由傳送至使用者的語音信箱和未接的來電通知會傳送給受話方。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-108">When a user has no endpoints located in the same network site as the PSTN gateway where the incoming call is originating from, the incoming call will be routed directly to the user’s voicemail and a missed call notification will be sent to the called party.</span></span>

<span data-ttu-id="8d0f1-109">來電轉接設定已啟用位置型路由的使用者仍可強制執行，不過，轉接電話會受到位置型路由限制的使用者。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-109">The call forwarding settings of a user that is enabled for Location-Based Routing will continue to be enforced, however, calls forwarded will be subject to Location-Based Routing restrictions of the user.</span></span>

<span data-ttu-id="8d0f1-110">下表說明如何以位置為主的路由會影響根據受話者端點的位置的撥入通話路由傳送。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-110">The following table illustrates how Location-Based Routing affects the routing of inbound calls depending on the location of the callee’s endpoint.</span></span> <span data-ttu-id="8d0f1-111">PSTN 閘道的網路網站啟用位置型的路由，以及位置型路由只允許路由傳送至相同的網路站台內的端點的 PSTN 通話。</span><span class="sxs-lookup"><span data-stu-id="8d0f1-111">The network site of the PSTN gateway is enabled for Location-Based Routing, and Location-Based Routing only permits routing of PSTN calls to endpoints within the same network site.</span></span>

### <a name="callee-receiving-an-inbound-call-from-the-pstn"></a><span data-ttu-id="8d0f1-112">受話者接收來自 PSTN 的輸入的呼叫</span><span class="sxs-lookup"><span data-stu-id="8d0f1-112">Callee receiving an inbound call from the PSTN</span></span>

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
<th><span data-ttu-id="8d0f1-113">位於相同網路網站與 PSTN 閘道的受話者端點</span><span class="sxs-lookup"><span data-stu-id="8d0f1-113">Callee’s endpoint located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="8d0f1-114">並非位於相同網路網站與 PSTN 閘道的受話者端點</span><span class="sxs-lookup"><span data-stu-id="8d0f1-114">Callee’s endpoint not located in the same network site as PSTN gateway</span></span></th>
<th><span data-ttu-id="8d0f1-115">受話者端點位於不明的網路網站，或未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="8d0f1-115">Callee’s endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8d0f1-116">路由傳送內送 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="8d0f1-116">Routing of inbound PSTN call</span></span></p></td>
<td><p><span data-ttu-id="8d0f1-117">來電會路由傳送至受話者端點</span><span class="sxs-lookup"><span data-stu-id="8d0f1-117">Incoming call is routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="8d0f1-118">來電不會路由至受話者端點</span><span class="sxs-lookup"><span data-stu-id="8d0f1-118">Incoming call is not routed to callee’s endpoints</span></span></p></td>
<td><p><span data-ttu-id="8d0f1-119">來電不會路由至受話者端點</span><span class="sxs-lookup"><span data-stu-id="8d0f1-119">Incoming call is not routed to callee’s endpoints</span></span></p></td>
</tr>
</tbody>
</table>

  

<div>

## <a name="see-also"></a><span data-ttu-id="8d0f1-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8d0f1-120">See Also</span></span>


[<span data-ttu-id="8d0f1-121">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="8d0f1-121">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

