---
title: Lync Server 2013：以位置為基礎的路由與諮詢式來電轉接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e433baf180b8e4abf50ec374848204bf6628eb0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="6ca82-102">Lync Server 2013 中的位置路由與諮詢式來電轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ca82-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="6ca82-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="6ca82-104">除了強制將位置路由到 Lync 會議之外，以位置為基礎的路由會議應用程式會在諮詢通話中強制執行以位置為基礎的路由限制，將出局傳送到 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="6ca82-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="6ca82-105">「諮詢式來電轉接」是雙方在其中一方傳送呼叫給新使用者的兩方之間所建立的通話。</span><span class="sxs-lookup"><span data-stu-id="6ca82-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="6ca82-106">例如，PSTN 端點會呼叫使用者 A （Lync 被呼叫者）。</span><span class="sxs-lookup"><span data-stu-id="6ca82-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="6ca82-107">使用者 A 決定應將 PSTN 使用者轉寄到使用者 B （Lync 使用者）。</span><span class="sxs-lookup"><span data-stu-id="6ca82-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="6ca82-108">使用者 A 將呼叫與 PSTN 使用者保留通話，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。</span><span class="sxs-lookup"><span data-stu-id="6ca82-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="6ca82-109">使用者 A 將來電轉接到使用者 B。</span><span class="sxs-lookup"><span data-stu-id="6ca82-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="6ca82-110">**諮詢式通話轉移通話流程**</span><span class="sxs-lookup"><span data-stu-id="6ca82-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="6ca82-111">![會議圖表的以位置為基礎的路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "會議圖表的以位置為基礎的路由")</span><span class="sxs-lookup"><span data-stu-id="6ca82-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="6ca82-112">當啟用位置路由的使用者啟動 PSTN 端點的諮詢式來電轉接時（如上圖所示），這會產生兩個作用中的通話、PSTN 使用者與 Lync 使用者 A 之間的呼叫，以及 Lync 使用者 A 和 Lync 使用者 B 之間的另一個通話。下列行為是由以位置為基礎的路由會議應用程式強制執行：</span><span class="sxs-lookup"><span data-stu-id="6ca82-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="6ca82-113">如果 SIP 中繼路由 PSTN 呼叫已獲授權，可將 PSTN 呼叫重新路由至 Lync 使用者 B （亦即傳輸目標）所在的網路網站，則允許來電轉接;否則，將會封鎖諮詢式來電轉接。</span><span class="sxs-lookup"><span data-stu-id="6ca82-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="6ca82-114">這項授權是依據已傳送的參與方的位置，而不是將作用中的呼叫路由至 PSTN 端點的 SIP 主幹來執行。</span><span class="sxs-lookup"><span data-stu-id="6ca82-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="6ca82-115">如果 SIP 中繼路由未獲授權將呼叫路由至傳送方（Lync 使用者 B）所在的網路網站，或轉移的參與方位於未知的網路網站中，請諮詢來電轉接到 PSTN將會封鎖端點（亦即來電轉接目標）。</span><span class="sxs-lookup"><span data-stu-id="6ca82-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="6ca82-116">下表說明諮詢式來電轉接的位置式路由會議應用程式如何套用以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="6ca82-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="6ca82-117">雖然 PBX 端點並不與網路網站直接關聯，但 PBX 的 SIP 幹線已連接至可指派網路網站。</span><span class="sxs-lookup"><span data-stu-id="6ca82-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="6ca82-118">因此，PBX 端點可以與網路網站間接關聯。</span><span class="sxs-lookup"><span data-stu-id="6ca82-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-119">來電轉接方的網路網站</span><span class="sxs-lookup"><span data-stu-id="6ca82-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="6ca82-120">來電轉接目標的網路網站</span><span class="sxs-lookup"><span data-stu-id="6ca82-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="6ca82-121">行為</span><span class="sxs-lookup"><span data-stu-id="6ca82-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-122">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-123">同一網路網站中的 Lync 使用者（亦即 site 1）</span><span class="sxs-lookup"><span data-stu-id="6ca82-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-124">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-125">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-126">不同網路網站中的 Lync 使用者（亦即 site 2）</span><span class="sxs-lookup"><span data-stu-id="6ca82-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-127">不允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-128">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-129">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="6ca82-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-130">不允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-131">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-132">聯盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="6ca82-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="6ca82-133">不允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-134">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-135">同一網站中的 PBX 端點（亦即 site 1）</span><span class="sxs-lookup"><span data-stu-id="6ca82-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-136">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-137">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-138">不同網站中的 PBX 端點（亦即 site 2）</span><span class="sxs-lookup"><span data-stu-id="6ca82-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-139">不允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-140">同一網站中的 PBX 端點（亦即 site 1）</span><span class="sxs-lookup"><span data-stu-id="6ca82-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-141">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-142">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-143">不同網站中的 PBX 端點（亦即 site 2）</span><span class="sxs-lookup"><span data-stu-id="6ca82-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-144">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="6ca82-145">不允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-146">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-147">同一網路網站中的 Lync 使用者（亦即 site 1）</span><span class="sxs-lookup"><span data-stu-id="6ca82-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-148">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-149">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-150">不同網路網站中的 Lync 使用者（亦即 site 2）</span><span class="sxs-lookup"><span data-stu-id="6ca82-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="6ca82-151">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6ca82-152">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-153">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="6ca82-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-154">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6ca82-155">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="6ca82-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="6ca82-156">聯盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="6ca82-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="6ca82-157">允許使用顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="6ca82-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

