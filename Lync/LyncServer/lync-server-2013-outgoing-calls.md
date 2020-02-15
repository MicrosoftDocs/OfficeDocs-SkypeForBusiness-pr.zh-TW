---
title: Lync Server 2013： 撥出電話
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
ms.openlocfilehash: ca0cdc7781143b0e76ff83a980f00da58c814f02
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="0fcc7-102">Lync Server 2013 中的撥出電話</span><span class="sxs-lookup"><span data-stu-id="0fcc7-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fcc7-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="0fcc7-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="0fcc7-104">路由撥出電話的使用者啟用位置型路由是受影響使用者的端點的網路位置。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="0fcc7-105">下表說明如何以位置為主的路由會影響路由撥出通話根據發話者端點的位置。</span><span class="sxs-lookup"><span data-stu-id="0fcc7-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="0fcc7-106">來電者將放至 PSTN 撥出電話</span><span class="sxs-lookup"><span data-stu-id="0fcc7-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="0fcc7-107">位於啟用位置型路由的網路網站的使用者端點</span><span class="sxs-lookup"><span data-stu-id="0fcc7-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="0fcc7-108">使用者端點位於不明的網路網站，或未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="0fcc7-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fcc7-109">撥出電話的授權</span><span class="sxs-lookup"><span data-stu-id="0fcc7-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="0fcc7-110">呼叫是根據授權的使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="0fcc7-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="0fcc7-111">呼叫是根據授權的使用者的語音原則</span><span class="sxs-lookup"><span data-stu-id="0fcc7-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fcc7-112">撥出電話路由</span><span class="sxs-lookup"><span data-stu-id="0fcc7-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="0fcc7-113">通話路由傳送根據網路網站的語音路由原則</span><span class="sxs-lookup"><span data-stu-id="0fcc7-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="0fcc7-114">通話路由傳送，根據使用者的語音原則，以及只能透過主幹 （如果有的話） 未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="0fcc7-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="0fcc7-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0fcc7-115">See Also</span></span>


[<span data-ttu-id="0fcc7-116">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="0fcc7-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

