---
title: Lync Server 2013：同時震鈴
description: Lync Server 2013：同時震鈴。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 595c8c1d4ce105e2189002f18733ffae92cff8bf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555659"
---
# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="f11bd-103">Lync Server 2013 中同時震鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-103">Simultaneous ringing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f11bd-104">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="f11bd-104">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="f11bd-105">當呼叫方啟用同時震鈴時，Location-Based 路由會分析呼叫方的位置，以及所叫方的端點，以判斷是否應路由傳送。</span><span class="sxs-lookup"><span data-stu-id="f11bd-105">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="f11bd-106">下表說明以同時震鈴方式設定的使用者，同時震鈴目標是在相同網路網站、不同網路網站或未知網路網站中的使用者。</span><span class="sxs-lookup"><span data-stu-id="f11bd-106">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f11bd-107">的傳入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="f11bd-107">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="f11bd-108">與被呼叫方位於相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="f11bd-108">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="f11bd-109">位於不同于被呼叫者的網路網站</span><span class="sxs-lookup"><span data-stu-id="f11bd-109">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="f11bd-110">位於未知的網路網站，或未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="f11bd-110">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f11bd-111">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="f11bd-111">Lync user</span></span></p></td>
<td><p><span data-ttu-id="f11bd-112">允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-112">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="f11bd-113">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-113">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="f11bd-114">不允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-114">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="f11bd-115">下表說明 Lync 使用者 (的呼叫，例如 Lync 來電者) 在同一部網路網站、不同的網路網站，或從未知的網路網站。</span><span class="sxs-lookup"><span data-stu-id="f11bd-115">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="f11bd-116">被呼叫方具有 PSTN 端點 (，cellphone) 設定為同時環的目標。</span><span class="sxs-lookup"><span data-stu-id="f11bd-116">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="f11bd-117">在此案例中，Location-Based 路由會判斷是否應將通話路由傳送至同時振鈴目標 (（亦即，被叫方的 cellphone) ）。</span><span class="sxs-lookup"><span data-stu-id="f11bd-117">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f11bd-118">同時環目標</span><span class="sxs-lookup"><span data-stu-id="f11bd-118">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="f11bd-119">與被呼叫方位於相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="f11bd-119">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="f11bd-120">位於不同于被呼叫者的網路網站</span><span class="sxs-lookup"><span data-stu-id="f11bd-120">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="f11bd-121">位於未知的網路網站，或未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="f11bd-121">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f11bd-122">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="f11bd-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="f11bd-123">透過來電者的網站語音路由原則允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f11bd-124">透過來電者的網站語音路由原則允許同時振鈴</span><span class="sxs-lookup"><span data-stu-id="f11bd-124">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f11bd-125">允許透過來電者語音原則進行同時振鈴，以主幹未啟用 Location-Based 路由</span><span class="sxs-lookup"><span data-stu-id="f11bd-125">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="f11bd-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="f11bd-126">See Also</span></span>


[<span data-ttu-id="f11bd-127">Lync Server 2013 中的 Location-Based 路由案例</span><span class="sxs-lookup"><span data-stu-id="f11bd-127">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

