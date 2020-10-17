---
title: Lync Server 2013：會議 Location-Based 路由的概述
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dd3508221babdd9c503e21d5662a1bbe60d4ce0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520950"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="be9d2-102">在 Lync Server 2013 中 Location-Based 用於會議之路由的概述</span><span class="sxs-lookup"><span data-stu-id="be9d2-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be9d2-103">_**主題上次修改日期：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="be9d2-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="be9d2-104">Location-Based 路由會議應用程式可讓 Lync 會議防護 PSTN 收費旁路的機制。</span><span class="sxs-lookup"><span data-stu-id="be9d2-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="be9d2-105">應用程式會監控使用中的會議，並根據 Lync 使用者參與的位置，強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="be9d2-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="be9d2-106">Location-Based 路由會議應用程式會在符合下列準則時，決定是否要在 Lync 會議上強制執行 Location-Based 路由：</span><span class="sxs-lookup"><span data-stu-id="be9d2-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="be9d2-107">已啟用會議召集人的 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="be9d2-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="be9d2-108">Location-Based 路由限制只會套用至已啟用 Location-Based 路由之使用者所組織的會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="be9d2-109">至少有一個會議參與者為 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="be9d2-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="be9d2-110">Location-Based 路由限制只適用于包括 PSTN 端點的會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="be9d2-111">PSTN 閘道用來將會議加入 PSTN 的網路網站，以及召集人和參與者連線所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="be9d2-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="be9d2-112">Location-Based 路由會議應用程式可防止 Lync 使用者和 PSTN 端點從不同的網路網站加入相同的會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="be9d2-113">如果為 Location-Based 路由啟用會議召集人，會議應用程式會強制執行下列限制：</span><span class="sxs-lookup"><span data-stu-id="be9d2-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="be9d2-114">可以加入 Lync 會議的端點取決於已加入會議的端點，而且此限制會調整為加入的端點，並且將新的端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="be9d2-115">如果召集人和參與者從相同的網路網站加入 Lync 會議，則來自相同網路網站的另一位參與者，允許來自不同網路網站或來自未知網路網站之參與者的另一位參與者加入。</span><span class="sxs-lookup"><span data-stu-id="be9d2-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="be9d2-116">如果召集人和參與者從不同或未知的網路網站加入會議，則不允許 PSTN 端點加入會議（如果 PSTN 通話 ingresses 從為 Location-Based 路由啟用的 SIP 主幹）。</span><span class="sxs-lookup"><span data-stu-id="be9d2-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="be9d2-117">如果召集人和參與者全都從相同的網路網站加入會議，且有參與者加入來自 PSTN 的相同會議，則不允許來自不同網路網站的 Lync 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="be9d2-118">下表摘要說明這些會議 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="be9d2-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be9d2-119">在會議中，任何指定點的使用者 (s) </span><span class="sxs-lookup"><span data-stu-id="be9d2-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="be9d2-120">允許加入會議的使用者 (s) </span><span class="sxs-lookup"><span data-stu-id="be9d2-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="be9d2-121">不允許使用者 (s) 加入會議</span><span class="sxs-lookup"><span data-stu-id="be9d2-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be9d2-122">Lync VoIP 用戶端使用者 (s) 從單一網路網站</span><span class="sxs-lookup"><span data-stu-id="be9d2-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="be9d2-123">來自相同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="be9d2-124">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="be9d2-125">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="be9d2-126">同盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="be9d2-127">從 PSTN 端點加入的使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="be9d2-128">無</span><span class="sxs-lookup"><span data-stu-id="be9d2-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be9d2-129">Lync VoIP 用戶端使用者 (s) 從未知的網路網站</span><span class="sxs-lookup"><span data-stu-id="be9d2-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="be9d2-130">任何網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="be9d2-131">來自未知網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="be9d2-132">同盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="be9d2-133">透過 PSTN 端點加入使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be9d2-134">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="be9d2-135">任何網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="be9d2-136">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="be9d2-137">同盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="be9d2-138">透過 PSTN 端點加入使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be9d2-139">Lync VoIP 用戶端使用者 (s) 從單一網路網站，以及從 PSTN 端點加入的使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="be9d2-140">來自相同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="be9d2-141">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="be9d2-142">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="be9d2-143">同盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="be9d2-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="be9d2-144">以下是 Location-Based 路由會議應用程式的其他特性：</span><span class="sxs-lookup"><span data-stu-id="be9d2-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="be9d2-145">當使用者因 Location-Based 路由限制而不允許加入會議時，會拒絕使用者呼叫會議，而 Lync 用戶端會報告呼叫未完成或已結束。</span><span class="sxs-lookup"><span data-stu-id="be9d2-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="be9d2-146">在加入具有 Location-Based 路由 enforcements 之會議的 PSTN 端點時，如果端點透過未啟用 Location-Based 路由的主幹加入，則不會限制加入會議的狀態。</span><span class="sxs-lookup"><span data-stu-id="be9d2-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="be9d2-147">透過 SIP 主幹（未向 PSTN 撥出電話）連接至 Mediations Server 的 PBX 系統，將會與位於定義 SIP 主幹的相同網路網站中的 Lync 使用者具有相同的 enforcements。</span><span class="sxs-lookup"><span data-stu-id="be9d2-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="be9d2-148">例如，當 PSTN 端點可以加入具有 PBX 使用者的會議，以及 Lync 使用者位於相同的網站時，它會與其共用;否則，如果 PBX 使用者位於不同的網路網站（Lync 使用者除外），將不允許 PSTN 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="be9d2-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

