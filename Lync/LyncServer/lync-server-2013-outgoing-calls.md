---
title: Lync Server 2013：撥出電話
description: Lync Server 2013：撥出電話。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e14f19dec35a6da47a2ddd62657d5d087a854f16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546849"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="0dccc-103">Lync Server 2013 中的撥出電話</span><span class="sxs-lookup"><span data-stu-id="0dccc-103">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0dccc-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="0dccc-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0dccc-105">已啟用 Location-Based 路由之使用者的撥出電話路由會受到使用者端點之網路位置的影響。</span><span class="sxs-lookup"><span data-stu-id="0dccc-105">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="0dccc-106">下表說明 Location-Based 路由會如何影響撥出電話的路由，視來電者端點的位置而定。</span><span class="sxs-lookup"><span data-stu-id="0dccc-106">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="0dccc-107">來電者向 PSTN 撥出電話</span><span class="sxs-lookup"><span data-stu-id="0dccc-107">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0dccc-108">已啟用 Location-Based 路由之網路網站中的使用者端點</span><span class="sxs-lookup"><span data-stu-id="0dccc-108">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="0dccc-109">位於未知網路網站或未啟用 Location-Based 路由的使用者端點</span><span class="sxs-lookup"><span data-stu-id="0dccc-109">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0dccc-110">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="0dccc-110">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="0dccc-111">根據使用者的語音原則進行呼叫授權</span><span class="sxs-lookup"><span data-stu-id="0dccc-111">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="0dccc-112">根據使用者的語音原則進行呼叫授權</span><span class="sxs-lookup"><span data-stu-id="0dccc-112">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0dccc-113">路由撥出通話</span><span class="sxs-lookup"><span data-stu-id="0dccc-113">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="0dccc-114">根據網路網站的語音路由原則路由通話</span><span class="sxs-lookup"><span data-stu-id="0dccc-114">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0dccc-115">呼叫會根據使用者的語音原則進行路由傳送，且只有透過主幹未啟用 Location-Based 路由 (（如果有的話）) </span><span class="sxs-lookup"><span data-stu-id="0dccc-115">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0dccc-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0dccc-116">See Also</span></span>


[<span data-ttu-id="0dccc-117">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="0dccc-117">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

