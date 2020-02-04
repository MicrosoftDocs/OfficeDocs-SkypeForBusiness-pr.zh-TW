---
title: Lync Server 2013：同時響鈴
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
ms.openlocfilehash: 1bcdb0d30bccfe628fd02861d257d79268046b77
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="11c82-102">Lync Server 2013 中的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="11c82-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11c82-103">_**主題上次修改日期：** 2013-03-09_</span><span class="sxs-lookup"><span data-stu-id="11c82-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="11c82-104">當呼叫方啟用同時撥打時，以位置為基礎的路由會分析呼叫方的位置，以及呼叫方的端點，判斷是否應該路由通話。</span><span class="sxs-lookup"><span data-stu-id="11c82-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="11c82-105">下表說明設定同時撥打的使用者，以及同時撥打的目標，是相同網路網站、不同網路網站或未知網路網站中的使用者。</span><span class="sxs-lookup"><span data-stu-id="11c82-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11c82-106">打入的 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="11c82-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="11c82-107">與被呼叫方位於相同的網路網站中</span><span class="sxs-lookup"><span data-stu-id="11c82-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="11c82-108">位於不同于被人的網路網站</span><span class="sxs-lookup"><span data-stu-id="11c82-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="11c82-109">位於未知的網路網站中，或未啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="11c82-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11c82-110">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="11c82-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="11c82-111">允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="11c82-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="11c82-112">不允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="11c82-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="11c82-113">不允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="11c82-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="11c82-114">下表說明 Lync 使用者（亦即 Lync 呼叫者）在同一個網路網站、不同網路網站或來自未知網路網站的呼叫。</span><span class="sxs-lookup"><span data-stu-id="11c82-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="11c82-115">被呼叫方有一個 PSTN 端點（亦即手機）設定為同時振鈴目標。</span><span class="sxs-lookup"><span data-stu-id="11c82-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="11c82-116">在這個案例中，以位置為基礎的路由會判斷是否應該將呼叫路由到被呼叫者的同時環目標（亦即手機）。</span><span class="sxs-lookup"><span data-stu-id="11c82-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="11c82-117">同時撥打目標</span><span class="sxs-lookup"><span data-stu-id="11c82-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="11c82-118">與被呼叫方位於相同的網路網站中</span><span class="sxs-lookup"><span data-stu-id="11c82-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="11c82-119">位於不同于被人的網路網站</span><span class="sxs-lookup"><span data-stu-id="11c82-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="11c82-120">位於未知的網路網站中，或未啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="11c82-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="11c82-121">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="11c82-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="11c82-122">透過來電者的網站語音路由策略允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="11c82-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="11c82-123">透過來電者的網站語音路由策略允許同時撥打</span><span class="sxs-lookup"><span data-stu-id="11c82-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="11c82-124">透過呼叫者的語音原則允許同時撥打，以進行位置式路由的 trunks</span><span class="sxs-lookup"><span data-stu-id="11c82-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="11c82-125">請參閱</span><span class="sxs-lookup"><span data-stu-id="11c82-125">See Also</span></span>


[<span data-ttu-id="11c82-126">Lync Server 2013 中的位置基礎路由案例</span><span class="sxs-lookup"><span data-stu-id="11c82-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

