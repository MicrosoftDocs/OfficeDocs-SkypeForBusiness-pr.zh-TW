---
title: Lync Server 2013： Location-Based 路由和顧問式來電轉接
description: Lync Server 2013： Location-Based 路由和顧問式來電轉接。
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
ms.openlocfilehash: 0d07cf6a33ff4d6ad57f8913a798fac3bc393a00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567669"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="27581-103">在 Lync Server 2013 中 Location-Based 路由和顧問式來電轉接</span><span class="sxs-lookup"><span data-stu-id="27581-103">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="27581-104">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="27581-104">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="27581-105">除了強制 Location-Based 路由傳送至 Lync 會議之外，Location-Based 路由會議應用程式也會強制進行向 PSTN 端點出口的諮詢來電轉接 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="27581-105">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="27581-106">「諮詢通話轉移」是兩方間所建立的呼叫，其中一個團體會將來電轉接給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="27581-106">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="27581-107">例如，PSTN 端點會呼叫使用者 A (Lync 方程式) 。</span><span class="sxs-lookup"><span data-stu-id="27581-107">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="27581-108">使用者 A 判斷 PSTN 使用者應轉寄給使用者 B (Lync 使用者) 。</span><span class="sxs-lookup"><span data-stu-id="27581-108">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="27581-109">使用者 A 通話為 PSTN 使用者保留，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。</span><span class="sxs-lookup"><span data-stu-id="27581-109">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="27581-110">使用者 A 將來電轉接至使用者 B。</span><span class="sxs-lookup"><span data-stu-id="27581-110">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="27581-111">**諮詢通話轉接通話流程**</span><span class="sxs-lookup"><span data-stu-id="27581-111">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="27581-112">![會議圖表的位置基礎路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "會議圖表的位置基礎路由")</span><span class="sxs-lookup"><span data-stu-id="27581-112">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="27581-113">當啟用 Location-Based 路由的使用者啟動對 PSTN 端點的諮詢來電轉接時 (如前面的圖所示) 所示，這會建立兩個使用中的呼叫、PSTN 使用者和 Lync 使用者 A 之間的呼叫，以及 Lync 使用者 A 和 Lync 使用者 B 之間的另一個呼叫。下列行為是由 Location-Based 路由會議應用程式強制執行的：</span><span class="sxs-lookup"><span data-stu-id="27581-113">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="27581-114">如果您有權將 pstn 通話路由的 SIP 主幹路由，以將 PSTN 呼叫重新路由至網路網站（Lync 使用者 B (亦即轉接目標) 位於此位置），則會允許通話轉接;否則，將會封鎖「諮詢來電轉接」。</span><span class="sxs-lookup"><span data-stu-id="27581-114">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="27581-115">這種授權是根據傳送方的位置，而不是以將使用中通話路由傳送至 PSTN 端點的 SIP 主幹所在的相同網路網站執行。</span><span class="sxs-lookup"><span data-stu-id="27581-115">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="27581-116">若 SIP 主幹路由輸入 PSTN 來電未獲授權，無法將來電路由傳送至已傳送方 (Lync 使用者 B) 或已轉接的當事方位於未知的網路網站，則諮詢呼叫會轉接至 PSTN 端點 (亦即會封鎖來電轉接目標) 。</span><span class="sxs-lookup"><span data-stu-id="27581-116">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="27581-117">下表說明 Location-Based 路由會議應用程式如何套用 Location-Based 路由限制以進行諮詢來電轉接。</span><span class="sxs-lookup"><span data-stu-id="27581-117">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="27581-118">雖然 PBX 端點不會直接與網路產生關聯，但 PBX 的 SIP 主幹可被指派為網路網站。</span><span class="sxs-lookup"><span data-stu-id="27581-118">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="27581-119">因此，PBX 端點可以與網路網站間接關聯。</span><span class="sxs-lookup"><span data-stu-id="27581-119">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="27581-120">通話轉移方的網路網站</span><span class="sxs-lookup"><span data-stu-id="27581-120">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="27581-121">來電轉接目標的網路網站</span><span class="sxs-lookup"><span data-stu-id="27581-121">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="27581-122">行為</span><span class="sxs-lookup"><span data-stu-id="27581-122">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-123">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-123">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-124">相同網路網站中的 Lync 使用者 (亦即網站 1) </span><span class="sxs-lookup"><span data-stu-id="27581-124">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="27581-125">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-125">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-126">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-126">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-127">不同網路網站中的 Lync 使用者 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="27581-127">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="27581-128">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-128">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-129">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-129">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-130">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="27581-130">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="27581-131">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-131">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-132">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-132">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-133">同盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="27581-133">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="27581-134">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-134">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-135">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-135">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-136">同一個網站中的 PBX 端點 (亦即，site 1) </span><span class="sxs-lookup"><span data-stu-id="27581-136">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="27581-137">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-137">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-138">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-138">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-139">不同網站中的 PBX 端點 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="27581-139">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="27581-140">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-140">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-141">同一個網站中的 PBX 端點 (亦即，site 1) </span><span class="sxs-lookup"><span data-stu-id="27581-141">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="27581-142">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-142">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-143">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-143">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-144">不同網站中的 PBX 端點 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="27581-144">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="27581-145">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="27581-145">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="27581-146">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-146">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-147">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="27581-147">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="27581-148">相同網路網站中的 Lync 使用者 (亦即網站 1) </span><span class="sxs-lookup"><span data-stu-id="27581-148">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="27581-149">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-149">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-150">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="27581-150">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="27581-151">不同網路網站中的 Lync 使用者 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="27581-151">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="27581-152">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-152">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="27581-153">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="27581-153">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="27581-154">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="27581-154">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="27581-155">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-155">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="27581-156">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="27581-156">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="27581-157">同盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="27581-157">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="27581-158">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="27581-158">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

