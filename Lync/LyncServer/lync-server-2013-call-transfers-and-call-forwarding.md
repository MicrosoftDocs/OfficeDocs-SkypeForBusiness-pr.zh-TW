---
title: Lync Server 2013：通話轉接和來電轉接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call transfers and call forwarding
ms:assetid: 978610ec-63c7-4cf6-ad7a-9ef91559bf12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994051(v=OCS.15)
ms:contentKeyID: 51803962
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d5b0661cfaaef2e514f070260f44abc4ea00572
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="92d43-102">Lync Server 2013 中的通話轉接和來電轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92d43-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="92d43-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="92d43-104">在涉及 PSTN 端點時，以位置為基礎的路由會分析 calle 端點的位置，以及將來電轉接或轉接到哪個端點（亦即傳輸/轉寄目標）。</span><span class="sxs-lookup"><span data-stu-id="92d43-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="92d43-105">位置路由根據兩個端點的位置，決定要轉移還是轉寄通話。</span><span class="sxs-lookup"><span data-stu-id="92d43-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="92d43-106">下表說明 Lync 使用者在使用 PSTN 端點的通話中的情況，而 Lync 使用者將來電轉接到另一個 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="92d43-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="92d43-107">根據 transferee 端點的網路網站位置而定，以位置為基礎的路由會影響來電轉接或轉寄的傳送。</span><span class="sxs-lookup"><span data-stu-id="92d43-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="92d43-108">啟動來電轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="92d43-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92d43-109">使用者啟動來電轉接/轉寄</span><span class="sxs-lookup"><span data-stu-id="92d43-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="92d43-110">在使用者啟動來電轉接或轉寄時，目標端點位於相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="92d43-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="92d43-111">在使用者啟動來電轉接或轉寄時，目標端點位於不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="92d43-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="92d43-112">目標端點位於 [未知網路] 網站或 [網路網站] 未啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="92d43-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d43-113">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="92d43-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="92d43-114">允許呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="92d43-115">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="92d43-116">不允許來電轉接或轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="92d43-117">例如：與 PSTN 端點通話中的 Lync 使用者會將來電轉接到相同網路網站中的另一個 Lync 使用者。</span><span class="sxs-lookup"><span data-stu-id="92d43-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="92d43-118">在這種情況下，允許來電轉接。</span><span class="sxs-lookup"><span data-stu-id="92d43-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="92d43-119">下表說明 Lync 使用者在與另一個 Lync 使用者的通話中的情況，且其中一個使用者將來電轉接到 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="92d43-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="92d43-120">視通話的傳送物件位置而定，表格會詳細說明以位置為基礎的路由對通話的影響。</span><span class="sxs-lookup"><span data-stu-id="92d43-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="92d43-121">來電轉接或轉接至 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="92d43-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92d43-122">來電轉接/轉寄端點目標</span><span class="sxs-lookup"><span data-stu-id="92d43-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="92d43-123">同一網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="92d43-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="92d43-124">不同網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="92d43-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="92d43-125">無法在 [未知網路] 網站或 [網路] 網站中的一或兩個 Lync 使用者啟用位置路由</span><span class="sxs-lookup"><span data-stu-id="92d43-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92d43-126">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="92d43-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="92d43-127">已轉移使用者的網站語音路由策略允許呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="92d43-128">已轉移使用者的網站語音路由策略允許呼叫轉寄或轉接</span><span class="sxs-lookup"><span data-stu-id="92d43-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="92d43-129">轉移的使用者語音原則只允許來電轉接或轉接，只透過 trunks，不支援以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="92d43-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="92d43-130">例如：與同一網路網站中的另一個 Lync 使用者通話中的 Lync 使用者，會將來電轉接到 PSTN 端點，並允許來電轉接。</span><span class="sxs-lookup"><span data-stu-id="92d43-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="92d43-131">請參閱</span><span class="sxs-lookup"><span data-stu-id="92d43-131">See Also</span></span>


[<span data-ttu-id="92d43-132">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="92d43-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

