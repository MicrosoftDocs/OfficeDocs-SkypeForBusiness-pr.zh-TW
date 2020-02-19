---
title: Lync Server 2013： 位置型路由及諮詢轉接
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
ms.openlocfilehash: 2bf1f9ca57366a3fc5b2ac1d13bd44336f3e2aeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a><span data-ttu-id="51759-102">位置型路由及 Lync Server 2013 中的諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-102">Location-Based Routing and consultative call transfers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51759-103">_**上次修改主題：** 2013年-07-31_</span><span class="sxs-lookup"><span data-stu-id="51759-103">_**Topic Last Modified:** 2013-07-31_</span></span>

<span data-ttu-id="51759-104">除了強制執行位置型路由到 Lync 會議，位置型路由會議應用程式強制執行諮詢轉接，輸出至 PSTN 端點上的位置型路由限制。</span><span class="sxs-lookup"><span data-stu-id="51759-104">In addition to enforcing Location-Based Routing to Lync meetings, the Location-Based Routing Conferencing application enforces Location-Based Routing restrictions on consultative call transfers that egress to PSTN endpoints.</span></span> <span data-ttu-id="51759-105">諮詢的來電轉接是兩方的其中一方將通話轉接給新的使用者建立通話。</span><span class="sxs-lookup"><span data-stu-id="51759-105">A consultative call transfer is a call established between two parties where one of the parties transfers the call to a new user.</span></span> <span data-ttu-id="51759-106">例如，PSTN 端點撥話給使用者 （Lync 受話者）。</span><span class="sxs-lookup"><span data-stu-id="51759-106">For example, a PSTN endpoint calls user A (Lync callee).</span></span> <span data-ttu-id="51759-107">使用者的決定 PSTN 使用者應該轉寄給使用者 B （Lync 使用者）。</span><span class="sxs-lookup"><span data-stu-id="51759-107">User A determines the PSTN user should be forwarded to user B (Lync user).</span></span> <span data-ttu-id="51759-108">按下以講話 PSTN 使用者同意 PSTN 使用者保留狀態，並呼叫使用者 B 使用者的呼叫使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="51759-108">User A places the call with the PSTN user on hold, and calls user B. User B agrees to talk to the PSTN user.</span></span> <span data-ttu-id="51759-109">使用者的轉接通話上-保留給使用者 b。</span><span class="sxs-lookup"><span data-stu-id="51759-109">User A transfers the call on-hold to user B.</span></span>

<span data-ttu-id="51759-110">**諮詢的呼叫轉接通話流程**</span><span class="sxs-lookup"><span data-stu-id="51759-110">**Consultative call transfer call flow**</span></span>

<span data-ttu-id="51759-111">![依位置路由會議圖表](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "依位置路由會議圖表")</span><span class="sxs-lookup"><span data-stu-id="51759-111">![Location-based routing for conferencing diagram](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Location-based routing for conferencing diagram")</span></span>

<span data-ttu-id="51759-112">當使用者啟用位置型路由啟始諮詢來電轉接的 PSTN 端點 （如如上圖所示） 時，這會建立兩個作用中呼叫、 一次呼叫之間 PSTN 使用者與 Lync 使用者的以及其他之間 Lync 使用者的與 Lync 使用者 b。下列行為是由位置型路由會議應用程式強制執行：</span><span class="sxs-lookup"><span data-stu-id="51759-112">When a user enabled for Location-Based Routing initiates a consultative call transfer of a PSTN endpoint (as shown in the preceding figure), this creates two active calls, one call between the PSTN user and Lync user A, and the other between Lync user A and Lync user B. the following behavior is enforced by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="51759-113">如果呼叫的 SIP 主幹路由 PSTN 重新路由傳送至網站 Lync 使用者 B （亦即轉接的目標） 位於、，然後將允許來電轉接; PSTN 通話授權否則請諮詢的來電轉接會被封鎖。</span><span class="sxs-lookup"><span data-stu-id="51759-113">If the SIP trunk routing the PSTN call is authorized to re-route the PSTN call to the network site where Lync user B (i.e. transfer target) is located,, then the call transfer will be allowed; otherwise, the consultative call transfer will be blocked.</span></span> <span data-ttu-id="51759-114">這項授權會根據傳送的方的位置路由至 PSTN 端點作用中的呼叫的 SIP 主幹與位於相同網路站台正在執行。</span><span class="sxs-lookup"><span data-stu-id="51759-114">This authorization is performed based on the transferred party’s location being in the same network site as the SIP trunk that is routing the active call to the PSTN endpoint.</span></span>

  - <span data-ttu-id="51759-115">如果 SIP 主幹路由內送的 PSTN 通話無法將通話路由傳送至網站： 轉移的方 （Lync 使用者 B） 位於或轉接的廠商位於不明的網路網站的權限，然後諮詢通話轉接至 PSTN端點 （亦即來電轉接的目標） 會被封鎖。</span><span class="sxs-lookup"><span data-stu-id="51759-115">If the SIP trunk routing the inbound PSTN call is not authorized to route calls to the network site where the transferred party (Lync user B) is located or the transferred party is located in an unknown network site, then the consultative call transfer to the PSTN endpoint (i.e. call transfer target) will be blocked.</span></span>

<span data-ttu-id="51759-116">下表說明如何以位置為主的路由限制會套用諮詢轉接位置型路由會議應用程式。</span><span class="sxs-lookup"><span data-stu-id="51759-116">The following table describes how Location-Based Routing restrictions are applied by the Location-Based Routing Conferencing application for consultative call transfers.</span></span> <span data-ttu-id="51759-117">雖然 PBX 端點不是直接與網路網站相關聯，PBX 連接至 SIP 主幹可被指派的網路網站。</span><span class="sxs-lookup"><span data-stu-id="51759-117">Although PBX endpoints are not directly associated with a network site, the SIP trunk the PBX is connected to can be assigned a network site.</span></span> <span data-ttu-id="51759-118">因此，PBX 端點可以間接網路與網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="51759-118">Therefore, the PBX endpoint can be indirectly associated with a network site.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51759-119">轉接的通話方的網路網站</span><span class="sxs-lookup"><span data-stu-id="51759-119">Network site of call transferred party</span></span></p></td>
<td><p><span data-ttu-id="51759-120">來電轉接的目標的網路網站</span><span class="sxs-lookup"><span data-stu-id="51759-120">Network site of call transfer target</span></span></p></td>
<td><p><span data-ttu-id="51759-121">行為</span><span class="sxs-lookup"><span data-stu-id="51759-121">Behavior</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-122">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-122">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-123">Lync 使用者在相同的網路網站 （亦即網站 1）</span><span class="sxs-lookup"><span data-stu-id="51759-123">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="51759-124">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-124">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-125">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-125">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-126">Lync 使用者在不同的網路網站 (亦即 site 2)</span><span class="sxs-lookup"><span data-stu-id="51759-126">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="51759-127">將不允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-127">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-128">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-128">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-129">不明的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="51759-129">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="51759-130">將不允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-130">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-131">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-131">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-132">同盟的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="51759-132">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="51759-133">將不允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-133">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-134">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-134">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-135">在相同的網站 （亦即網站 1） 的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-135">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="51759-136">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-136">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-137">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-137">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-138">在不同的站台 (亦即 site 2) 的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-138">PBX endpoint in a different sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="51759-139">將不允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-139">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-140">在相同的網站 （亦即網站 1） 的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-140">PBX endpoint in the same site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="51759-141">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-141">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-142">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-142">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-143">在不同的網站 (亦即 site 2) 的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-143">PBX endpoint in a different site (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="51759-144">PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="51759-144">PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="51759-145">將不允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-145">Consultative transfer will be disallowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-146">站台中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-146">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="51759-147">Lync 使用者在相同的網路網站 （亦即網站 1）</span><span class="sxs-lookup"><span data-stu-id="51759-147">Lync user in the same network site (i.e. site 1)</span></span></p></td>
<td><p><span data-ttu-id="51759-148">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-148">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-149">站台中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-149">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="51759-150">Lync 使用者在不同的網路網站 (亦即 site 2)</span><span class="sxs-lookup"><span data-stu-id="51759-150">Lync user in different network sites (i.e. site 2)</span></span></p></td>
<td><p><span data-ttu-id="51759-151">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-151">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51759-152">站台中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-152">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="51759-153">不明的網路網站中的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="51759-153">Lync user in an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="51759-154">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-154">Consultative transfer will be allowed</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51759-155">站台中的 PBX 端點</span><span class="sxs-lookup"><span data-stu-id="51759-155">PBX endpoint in any site</span></span></p></td>
<td><p><span data-ttu-id="51759-156">同盟的 Lync 使用者</span><span class="sxs-lookup"><span data-stu-id="51759-156">Federated Lync user</span></span></p></td>
<td><p><span data-ttu-id="51759-157">將允許諮詢轉接</span><span class="sxs-lookup"><span data-stu-id="51759-157">Consultative transfer will be allowed</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

