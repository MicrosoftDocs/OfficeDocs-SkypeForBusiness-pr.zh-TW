---
title: Lync Server 2013： 同時響鈴
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
ms.openlocfilehash: da250e04b3547e7ce6f00a73028ac3fcd083c30d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a><span data-ttu-id="d2bda-102">同時響鈴的 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2bda-102">Simultaneous ringing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2bda-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="d2bda-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="d2bda-104">當受話的方具有已啟用同時響鈴時，位置型路由會分析的呼叫方的位置和受話方設定決定是否應路由傳送通話的端點。</span><span class="sxs-lookup"><span data-stu-id="d2bda-104">When the called party has simultaneous ringing enabled, Location-Based Routing analyzes the location of the calling party and the endpoints of the called parties to determine whether the call should be routed.</span></span>

<span data-ttu-id="d2bda-105">下表說明設定與同時響鈴的使用者，同時響鈴的目標是相同的網路站台、 不同的網路網站，或無法辨識的網路網站的使用者。</span><span class="sxs-lookup"><span data-stu-id="d2bda-105">The following table illustrates a user configured with simultaneous ringing, and the simultaneous ringing target is a user in the same network site, in a different network site, or in an unknown network site.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2bda-106">傳入 PSTN 通話</span><span class="sxs-lookup"><span data-stu-id="d2bda-106">Incoming PSTN call for</span></span></th>
<th><span data-ttu-id="d2bda-107">位於與受話者位於相同網路站台</span><span class="sxs-lookup"><span data-stu-id="d2bda-107">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="d2bda-108">位於比受話者的不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="d2bda-108">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="d2bda-109">位於不明的網路站台或未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="d2bda-109">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2bda-110">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="d2bda-110">Lync user</span></span></p></td>
<td><p><span data-ttu-id="d2bda-111">允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-111">Simultaneous ring allowed</span></span></p></td>
<td><p><span data-ttu-id="d2bda-112">不允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-112">Simultaneous ring not allowed</span></span></p></td>
<td><p><span data-ttu-id="d2bda-113">不允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-113">Simultaneous ring not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="d2bda-114">下表說明從 Lync 使用者 （亦即 Lync 呼叫者） 的呼叫中相同的網路網站，在不同的網路網站中，或從不明的網路網站。</span><span class="sxs-lookup"><span data-stu-id="d2bda-114">The following table illustrates a call from a Lync user (i.e. Lync caller) in the same network site, in a different network site, or from an unknown network site.</span></span> <span data-ttu-id="d2bda-115">受話者已設定為同時響鈴目標 PSTN 端點 （亦即行動電話）。</span><span class="sxs-lookup"><span data-stu-id="d2bda-115">The callee has a PSTN endpoint (i.e. cellphone) configured as a simultaneous ring target.</span></span> <span data-ttu-id="d2bda-116">在此案例中，位置型路由會決定是否在呼叫應被路由傳送至受話者的同時響鈴目標 (亦即 cellphone) 或不。</span><span class="sxs-lookup"><span data-stu-id="d2bda-116">In this scenario, Location-Based Routing will determine whether the call should be routed to the simultaneous ring target (i.e. cellphone) of the callee or not.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d2bda-117">同時響鈴目標</span><span class="sxs-lookup"><span data-stu-id="d2bda-117">Simultaneous ring target</span></span></th>
<th><span data-ttu-id="d2bda-118">位於與受話者位於相同網路站台</span><span class="sxs-lookup"><span data-stu-id="d2bda-118">Located in the same network site as callee</span></span></th>
<th><span data-ttu-id="d2bda-119">位於比受話者的不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="d2bda-119">Located in different network site than callee</span></span></th>
<th><span data-ttu-id="d2bda-120">位於不明的網路站台或未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="d2bda-120">Located in unknown network site or not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d2bda-121">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d2bda-121">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d2bda-122">透過發話者網站的語音路由原則所允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-122">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d2bda-123">透過發話者網站的語音路由原則所允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-123">Simultaneous ring allowed through the caller’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="d2bda-124">發話者的語音原則未啟用位置型路由的主幹，透過允許的同時響鈴</span><span class="sxs-lookup"><span data-stu-id="d2bda-124">Simultaneous ring allowed through the caller’s voice policy to trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="d2bda-125">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d2bda-125">See Also</span></span>


[<span data-ttu-id="d2bda-126">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="d2bda-126">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

