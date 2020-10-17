---
title: Lync Server 2013： Location-Based 路由和顧問式來電轉接
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
ms.openlocfilehash: 75284736af1307aff4e9c51c8118cf64dbd08568
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513810"
---
# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="d5b8c-102">在 Lync Server 2013 中 Location-Based 路由和顧問式來電轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5b8c-103">_**主題上次修改日期：** 2013-07-31_</span><span class="sxs-lookup"><span data-stu-id="d5b8c-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="d5b8c-104">除了強制 Location-Based 路由傳送至 Lync 會議之外，Location-Based 路由會議應用程式也會強制進行向 PSTN 端點出口的諮詢來電轉接 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="d5b8c-105">「諮詢通話轉移」是兩方間所建立的呼叫，其中一個團體會將來電轉接給新的使用者。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="d5b8c-106">例如，PSTN 端點會呼叫使用者 A (Lync 方程式) 。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="d5b8c-107">使用者 A 判斷 PSTN 使用者應轉寄給使用者 B (Lync 使用者) 。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="d5b8c-108">使用者 A 通話為 PSTN 使用者保留，並呼叫使用者 B。使用者 B 同意與 PSTN 使用者交談。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="d5b8c-109">使用者 A 將來電轉接至使用者 B。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="d5b8c-110">**諮詢通話轉接通話流程**</span><span class="sxs-lookup"><span data-stu-id="d5b8c-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="d5b8c-111">![會議圖表的位置基礎路由](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "會議圖表的位置基礎路由")</span><span class="sxs-lookup"><span data-stu-id="d5b8c-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="d5b8c-112">當啟用 Location-Based 路由的使用者啟動對 PSTN 端點的諮詢來電轉接時 (如前面的圖所示) 所示，這會建立兩個使用中的呼叫、PSTN 使用者和 Lync 使用者 A 之間的呼叫，以及 Lync 使用者 A 和 Lync 使用者 B 之間的另一個呼叫。下列行為是由 Location-Based 路由會議應用程式強制執行的：</span><span class="sxs-lookup"><span data-stu-id="d5b8c-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="d5b8c-113">如果您有權將 pstn 通話路由的 SIP 主幹路由，以將 PSTN 呼叫重新路由至網路網站（Lync 使用者 B (亦即轉接目標) 位於此位置），則會允許通話轉接;否則，將會封鎖「諮詢來電轉接」。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="d5b8c-114">這種授權是根據傳送方的位置，而不是以將使用中通話路由傳送至 PSTN 端點的 SIP 主幹所在的相同網路網站執行。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="d5b8c-115">若 SIP 主幹路由輸入 PSTN 來電未獲授權，無法將來電路由傳送至已傳送方 (Lync 使用者 B) 或已轉接的當事方位於未知的網路網站，則諮詢呼叫會轉接至 PSTN 端點 (亦即會封鎖來電轉接目標) 。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="d5b8c-116">下表說明 Location-Based 路由會議應用程式如何套用 Location-Based 路由限制以進行諮詢來電轉接。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="d5b8c-117">雖然 PBX 端點不會直接與網路產生關聯，但 PBX 的 SIP 主幹可被指派為網路網站。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="d5b8c-118">因此，PBX 端點可以與網路網站間接關聯。</span><span class="sxs-lookup"><span data-stu-id="d5b8c-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-119">通話轉移方的網路網站</span><span class="sxs-lookup"><span data-stu-id="d5b8c-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-120">來電轉接目標的網路網站</span><span class="sxs-lookup"><span data-stu-id="d5b8c-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-121">行為</span><span class="sxs-lookup"><span data-stu-id="d5b8c-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-122">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-123">相同網路網站中的 Lync 使用者 (亦即網站 1) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-124">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-125">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-126">不同網路網站中的 Lync 使用者 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-127">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-128">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-129">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="d5b8c-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-130">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-131">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-132">同盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="d5b8c-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-133">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-134">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-135">同一個網站中的 PBX 端點 (亦即，site 1) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-136">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-137">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-138">不同網站中的 PBX 端點 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-139">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-140">同一個網站中的 PBX 端點 (亦即，site 1) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-141">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-142">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-143">不同網站中的 PBX 端點 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-144">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-145">不允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-146">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-147">相同網路網站中的 Lync 使用者 (亦即網站 1) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-148">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-149">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-150">不同網路網站中的 Lync 使用者 (亦即 site 2) </span><span class="sxs-lookup"><span data-stu-id="d5b8c-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-151">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b8c-152">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-153">未知網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="d5b8c-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-154">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d5b8c-155">任何網站中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="d5b8c-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-156">同盟 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="d5b8c-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="d5b8c-157">允許顧問式轉接</span><span class="sxs-lookup"><span data-stu-id="d5b8c-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

