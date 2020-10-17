---
title: Lync Server 2013：撥出電話
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
ms.openlocfilehash: 6a77ddf0757cd463bb8f1b95dbecfe90fd1086c9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524400"
---
# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="4cde4-102">Lync Server 2013 中的撥出電話</span><span class="sxs-lookup"><span data-stu-id="4cde4-102">Outgoing calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cde4-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="4cde4-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="4cde4-104">已啟用 Location-Based 路由之使用者的撥出電話路由會受到使用者端點之網路位置的影響。</span><span class="sxs-lookup"><span data-stu-id="4cde4-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="4cde4-105">下表說明 Location-Based 路由會如何影響撥出電話的路由，視來電者端點的位置而定。</span><span class="sxs-lookup"><span data-stu-id="4cde4-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="4cde4-106">來電者向 PSTN 撥出電話</span><span class="sxs-lookup"><span data-stu-id="4cde4-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4cde4-107">已啟用 Location-Based 路由之網路網站中的使用者端點</span><span class="sxs-lookup"><span data-stu-id="4cde4-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="4cde4-108">位於未知網路網站或未啟用 Location-Based 路由的使用者端點</span><span class="sxs-lookup"><span data-stu-id="4cde4-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cde4-109">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="4cde4-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="4cde4-110">根據使用者的語音原則進行呼叫授權</span><span class="sxs-lookup"><span data-stu-id="4cde4-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="4cde4-111">根據使用者的語音原則進行呼叫授權</span><span class="sxs-lookup"><span data-stu-id="4cde4-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cde4-112">路由撥出通話</span><span class="sxs-lookup"><span data-stu-id="4cde4-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="4cde4-113">根據網路網站的語音路由原則路由通話</span><span class="sxs-lookup"><span data-stu-id="4cde4-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="4cde4-114">呼叫會根據使用者的語音原則進行路由傳送，且只有透過主幹未啟用 Location-Based 路由 (（如果有的話）) </span><span class="sxs-lookup"><span data-stu-id="4cde4-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4cde4-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="4cde4-115">See Also</span></span>


[<span data-ttu-id="4cde4-116">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="4cde4-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

