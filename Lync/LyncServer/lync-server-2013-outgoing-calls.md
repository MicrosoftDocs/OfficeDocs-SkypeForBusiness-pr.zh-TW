---
title: Lync Server 2013：撥出電話
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Outgoing calls
ms:assetid: 885ffe6f-cd51-4f21-8d4f-a1ff8d818858
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994049(v=OCS.15)
ms:contentKeyID: 51803960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2ccd095cfe27f173ff0fe7ac0dac92ca51a7c1d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="outgoing-calls-in-lync-server-2013"></a><span data-ttu-id="28ea1-102">在 Lync Server 2013 中撥出電話</span><span class="sxs-lookup"><span data-stu-id="28ea1-102">Outgoing calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28ea1-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="28ea1-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="28ea1-104">針對位置路由的使用者的出站呼叫路由會受到使用者端點的網路位置的影響。</span><span class="sxs-lookup"><span data-stu-id="28ea1-104">The routing of outbound calls of users enabled for Location-Based Routing is affected by the network location of the user’s endpoint.</span></span> <span data-ttu-id="28ea1-105">下表說明根據呼叫者終點的位置，以位置為基礎的路由會如何影響傳出通話的路由。</span><span class="sxs-lookup"><span data-stu-id="28ea1-105">The following table illustrates how Location-Based Routing affects the routing of outbound calls depending on the location of the caller’s endpoint.</span></span>

### <a name="caller-placing-an-outbound-call-to-the-pstn"></a><span data-ttu-id="28ea1-106">來電者撥入到 PSTN 的電話</span><span class="sxs-lookup"><span data-stu-id="28ea1-106">Caller placing an outbound call to the PSTN</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="28ea1-107">使用者端點位於已啟用位置路由的網路網站中</span><span class="sxs-lookup"><span data-stu-id="28ea1-107">User endpoint located in a network site enabled for Location-Based Routing</span></span></th>
<th><span data-ttu-id="28ea1-108">使用者端點位於未知的網路網站中，或未啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="28ea1-108">User endpoint located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="28ea1-109">撥出通話的授權</span><span class="sxs-lookup"><span data-stu-id="28ea1-109">Authorization of outbound calls</span></span></p></td>
<td><p><span data-ttu-id="28ea1-110">根據使用者的語音原則，進行撥號授權</span><span class="sxs-lookup"><span data-stu-id="28ea1-110">Call is authorized based on user’s voice policy</span></span></p></td>
<td><p><span data-ttu-id="28ea1-111">根據使用者的語音原則，進行撥號授權</span><span class="sxs-lookup"><span data-stu-id="28ea1-111">Call is authorized based on user’s voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="28ea1-112">傳送撥出通話</span><span class="sxs-lookup"><span data-stu-id="28ea1-112">Routing of outbound call</span></span></p></td>
<td><p><span data-ttu-id="28ea1-113">根據網路網站的語音路由策略來傳送通話</span><span class="sxs-lookup"><span data-stu-id="28ea1-113">Call is routed according to the network site’s voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="28ea1-114">通話是依據使用者的語音原則傳送，只能透過 trunks （如果有的話）啟用。</span><span class="sxs-lookup"><span data-stu-id="28ea1-114">Call is routed according to user’s voice policy and only through trunks not enabled for Location-Based Routing (if available)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="28ea1-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="28ea1-115">See Also</span></span>


[<span data-ttu-id="28ea1-116">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="28ea1-116">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

