---
title: Lync Server 2013： 來電轉接和來電轉接
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
ms.openlocfilehash: a78332e2fa24c4f718cb3cdb3cbc9dc93a03601d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="call-transfers-and-call-forwarding-in-lync-server-2013"></a><span data-ttu-id="378c7-102">來電轉接和 Lync Server 2013 中來電轉接</span><span class="sxs-lookup"><span data-stu-id="378c7-102">Call transfers and call forwarding in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="378c7-103">_**上次修改主題：** 2013年-03-09_</span><span class="sxs-lookup"><span data-stu-id="378c7-103">_**Topic Last Modified:** 2013-03-09_</span></span>

<span data-ttu-id="378c7-104">如果包含 PSTN 端點，位置型路由會分析 calle 端點及傳送或轉寄給 （亦即傳輸/順向目標） 通話的結束點的位置。</span><span class="sxs-lookup"><span data-stu-id="378c7-104">When a PSTN endpoint is involved, Location-Based Routing analyzes the location of the calle’s endpoint and the endpoint where the call will be transferred or forwarded to (i.e. transfer/forward target).</span></span> <span data-ttu-id="378c7-105">位置型路由會決定在呼叫是否應該轉接或轉寄根據這兩個端點的位置。</span><span class="sxs-lookup"><span data-stu-id="378c7-105">Location-Based Routing determines whether the call should be transferred or forwarded depending on the location of both endpoints.</span></span>

<span data-ttu-id="378c7-106">下表說明的案例中使用 PSTN 端點，呼叫 Lync 使用者與 Lync 使用者將轉接至另一位 Lync 使用者的呼叫。</span><span class="sxs-lookup"><span data-stu-id="378c7-106">The following table illustrates the scenario of a Lync user in a call with a PSTN endpoint, and the Lync user transfers the call to another Lync user.</span></span> <span data-ttu-id="378c7-107">未經的端點的網路站台位置，根據位置型路由會影響路由的來電轉接或轉寄。</span><span class="sxs-lookup"><span data-stu-id="378c7-107">Depending on the network site location of the transferee’s endpoint, Location-Based Routing affects the routing of the call transfer or forward.</span></span>

### <a name="initiating-call-transfer-or-forward"></a><span data-ttu-id="378c7-108">起始通話轉接或轉寄</span><span class="sxs-lookup"><span data-stu-id="378c7-108">Initiating call transfer or forward</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="378c7-109">使用者初始化通話轉接/轉寄</span><span class="sxs-lookup"><span data-stu-id="378c7-109">User initiating the call transfer/forward</span></span></th>
<th><span data-ttu-id="378c7-110">目標端點位於相同的網路網站，以初始化來電轉接或順向使用者</span><span class="sxs-lookup"><span data-stu-id="378c7-110">Target endpoint is in same network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="378c7-111">目標端點以初始化來電轉接或順向使用者位於不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="378c7-111">Target endpoint is in different network site as user initiating call transfer or forward</span></span></th>
<th><span data-ttu-id="378c7-112">目標端點無法辨識的網路站台或網路網站中未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="378c7-112">Target endpoint is in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="378c7-113">Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="378c7-113">Lync user</span></span></p></td>
<td><p><span data-ttu-id="378c7-114">轉接通話] 或 [允許傳輸</span><span class="sxs-lookup"><span data-stu-id="378c7-114">Call forward or transfer is allowed</span></span></p></td>
<td><p><span data-ttu-id="378c7-115">轉接通話] 或 [不允許轉接</span><span class="sxs-lookup"><span data-stu-id="378c7-115">Call forward or transfer is not allowed</span></span></p></td>
<td><p><span data-ttu-id="378c7-116">轉接通話] 或 [不允許轉接</span><span class="sxs-lookup"><span data-stu-id="378c7-116">Call forward or transfer is not allowed</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="378c7-117">例如： 與 PSTN 端點的呼叫中的 Lync 使用者將在相同的網路站台的另一位 Lync 使用者通話轉接。</span><span class="sxs-lookup"><span data-stu-id="378c7-117">For example: a Lync user in a call with a PSTN endpoint transfers the call to another Lync user that is in the same network site.</span></span> <span data-ttu-id="378c7-118">在此情況下，允許通話轉接。</span><span class="sxs-lookup"><span data-stu-id="378c7-118">In this case, the call transfer is allowed.</span></span>

<span data-ttu-id="378c7-119">下表說明的另一位 Lync 使用者，在呼叫 Lync 使用者的案例，並有一位使用者轉接至 PSTN 端點的呼叫。</span><span class="sxs-lookup"><span data-stu-id="378c7-119">The following table illustrates the scenario of a Lync user in a call with another Lync user, and one of the users transfers the call to a PSTN endpoint.</span></span> <span data-ttu-id="378c7-120">視呼叫會轉接至表格詳細資料如何之使用者的位置而定位置型路由會影響通話。</span><span class="sxs-lookup"><span data-stu-id="378c7-120">Depending on the location of the user the call is being transferred to, the table details how Location-Based Routing affects the call.</span></span>

### <a name="call-transfer-or-forward-to-pstn-endpoint"></a><span data-ttu-id="378c7-121">來電轉接或轉接至 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="378c7-121">Call transfer or forward to PSTN endpoint</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="378c7-122">呼叫傳輸/順向端點目標</span><span class="sxs-lookup"><span data-stu-id="378c7-122">Call transfer/forward endpoint target</span></span></th>
<th><span data-ttu-id="378c7-123">Lync 使用者在相同的網路網站</span><span class="sxs-lookup"><span data-stu-id="378c7-123">Lync users in same network site</span></span></th>
<th><span data-ttu-id="378c7-124">Lync 使用者在不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="378c7-124">Lync users in different network sites</span></span></th>
<th><span data-ttu-id="378c7-125">不明的網路站台或未啟用位置型路由的網路網站中的一或兩個 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="378c7-125">One or both Lync users in unknown network site or network site not enabled for Location-Based Routing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="378c7-126">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="378c7-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="378c7-127">轉接通話] 或 [傳送的使用者的網站語音路由原則所允許的轉接</span><span class="sxs-lookup"><span data-stu-id="378c7-127">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="378c7-128">轉接通話] 或 [傳送的使用者的網站語音路由原則所允許的轉接</span><span class="sxs-lookup"><span data-stu-id="378c7-128">Call forward or transfer allowed by the transferred user’s site voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="378c7-129">轉接通話] 或 [只能透過主幹傳送的使用者的語音原則允許傳輸未啟用位置型的路由</span><span class="sxs-lookup"><span data-stu-id="378c7-129">Call forward or transfer allowed by the transferred user’s voice policy only through trunks not enabled for Location-Based Routing</span></span></p></td>
</tr>
</tbody>
</table>

  
<span data-ttu-id="378c7-130">例如： Lync 使用者的呼叫中具有相同的網路站台中的另一位 Lync 使用者轉接至 PSTN 端點的呼叫，並允許來電轉接。</span><span class="sxs-lookup"><span data-stu-id="378c7-130">For example: a Lync user in a call with another Lync user that is in the same network site transfers the call to a PSTN endpoint and the call transfer is allowed.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="378c7-131">另請參閱</span><span class="sxs-lookup"><span data-stu-id="378c7-131">See Also</span></span>


[<span data-ttu-id="378c7-132">依位置路由 Lync Server 2013 中的案例</span><span class="sxs-lookup"><span data-stu-id="378c7-132">Scenarios for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

