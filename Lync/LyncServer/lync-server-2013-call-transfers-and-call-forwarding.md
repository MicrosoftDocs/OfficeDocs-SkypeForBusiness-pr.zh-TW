---
title: Lync Server 2013：通話轉移和來電轉接
description: Lync Server 2013：通話轉接及來電轉接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9359cb64b386d022eab33e4523dfaccf784075b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565249"
---
# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="b92c1-103">Lync Server 2013 中的來電轉接和來電轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-103">Call transfers and call forwarding in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b92c1-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="b92c1-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="b92c1-105">當涉及 PSTN 端點時，Location-Based 路由會分析 calle 端點的位置，以及將來電轉接或轉接至 (（例如，傳輸/轉送目標) ）的端點。</span><span class="sxs-lookup"><span data-stu-id="b92c1-105">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="b92c1-106">Location-Based 路由決定是否應該根據這兩個端點的位置來轉移或轉寄通話。</span><span class="sxs-lookup"><span data-stu-id="b92c1-106">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="b92c1-107">下表說明 Lync 使用者在使用 PSTN 端點的呼叫中的情形，以及 Lync 使用者將通話轉接至另一個 Lync 使用者的情形。</span><span class="sxs-lookup"><span data-stu-id="b92c1-107">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="b92c1-108">根據 transferee 端點的網路網站位置，Location-Based 路由會影響來電轉接或轉寄的路由。</span><span class="sxs-lookup"><span data-stu-id="b92c1-108">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="b92c1-109">開始來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="b92c1-109">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92c1-110">使用者啟動通話轉接/轉寄</span><span class="sxs-lookup"><span data-stu-id="b92c1-110">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="b92c1-111">目標端點位於與使用者起始來電轉接或轉寄相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="b92c1-111">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="b92c1-112">目標端點位於不同的網路網站中，以供使用者開始來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="b92c1-112">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="b92c1-113">目標端點位於未知的網路網站，或未啟用 Location-Based 路由的網路網站</span><span class="sxs-lookup"><span data-stu-id="b92c1-113">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92c1-114">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="b92c1-114">Lync user</span></span></p></td>
<td><p><span data-ttu-id="b92c1-115">允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-115">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="b92c1-116">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-116">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="b92c1-117">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-117">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="b92c1-118">例如：使用 PSTN 端點通話中的 Lync 使用者，可將來電轉接至位於相同網路網站中的其他 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="b92c1-118">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="b92c1-119">在此情況下，允許通話轉接。</span><span class="sxs-lookup"><span data-stu-id="b92c1-119">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="b92c1-120">下表說明 Lync 使用者與其他 Lync 使用者通話的情況，以及其中一位使用者將來電轉接至 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="b92c1-120">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="b92c1-121">根據通話的轉接使用者位置，表格會詳細說明 Location-Based 路由會如何影響通話。</span><span class="sxs-lookup"><span data-stu-id="b92c1-121">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="b92c1-122">來電轉接或轉接至 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="b92c1-122">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b92c1-123">來電轉接/轉寄端點目標</span><span class="sxs-lookup"><span data-stu-id="b92c1-123">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="b92c1-124">相同網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="b92c1-124">Lync users in same network site</span></span></th>
<th><span data-ttu-id="b92c1-125">不同網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="b92c1-125">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="b92c1-126">未啟用 Location-Based 路由的未知網路網站或網站中的一或兩個 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="b92c1-126">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b92c1-127">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="b92c1-127">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="b92c1-128">轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b92c1-129">轉接使用者的網站語音路由原則所允許的呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="b92c1-129">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="b92c1-130">轉接使用者的語音原則所允許的呼叫轉寄或轉接只能透過主幹未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="b92c1-130">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="b92c1-131">例如：通話中的 Lync 使用者與另一個位於相同網路網站的 Lync 使用者，將來電轉接至 PSTN 端點，並且允許通話轉接。</span><span class="sxs-lookup"><span data-stu-id="b92c1-131">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b92c1-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="b92c1-132">See Also</span></span>


[<span data-ttu-id="b92c1-133">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="b92c1-133">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

