---
title: Lync Server 2013：適用于會議的位置路由概覽
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895a89ee59edaf973ae5194658c4cdf12564542e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976131"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="1eb86-102">在 Lync Server 2013 中針對會議位置路由的概覽</span><span class="sxs-lookup"><span data-stu-id="1eb86-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eb86-103">_**主題上次修改日期：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="1eb86-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="1eb86-104">以位置為基礎的路由會議應用程式為 Lync 會議提供防範 PSTN 免付費旁路的機制。</span><span class="sxs-lookup"><span data-stu-id="1eb86-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="1eb86-105">應用程式會監視作用中的會議，並根據參與的 Lync 使用者的位置強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="1eb86-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="1eb86-106">如果符合下列條件，則以位置為基礎的路由會議應用程式會決定是否要在 Lync 會議上強制執行基於位置的路由：</span><span class="sxs-lookup"><span data-stu-id="1eb86-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="1eb86-107">會議召集人已啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="1eb86-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="1eb86-108">以位置為基礎的路由限制將只會套用至啟用位置式路由的使用者所組織的會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="1eb86-109">至少有一個會議參與者是 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="1eb86-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="1eb86-110">以位置為基礎的路由限制只適用于包含 PSTN 端點的會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="1eb86-111">PSTN 閘道用來將會議橋接至 PSTN 的網路網站，以及召集人與參與者的連線位置所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="1eb86-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="1eb86-112">[以位置為基礎的路由會議] 應用程式可防止 Lync 使用者和 PSTN 端點從不同的網路網站加入相同的會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="1eb86-113">如果啟用會議召集人進行位置式路由，會議應用程式會強制執行下列限制：</span><span class="sxs-lookup"><span data-stu-id="1eb86-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="1eb86-114">可以加入 Lync 會議的端點，取決於已加入會議的端點，而且這個限制會依加入的端點而調整，而新的端點則會加入會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="1eb86-115">如果召集人和參與者是從相同的網路網站加入 Lync 會議，則 PSTN 端點（來自相同網路網站的另一個參與者），另一個參與者從不同的網路網站或來自未知網路網站的參與者，都可以起來.</span><span class="sxs-lookup"><span data-stu-id="1eb86-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="1eb86-116">如果召集人和參與者是從不同或未知的網路網站加入會議，但如果 PSTN 呼叫 ingresses 來自 SIP 主幹系，且已啟用位置路由，則不允許 PSTN 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="1eb86-117">如果召集人與參與者全都從同一個網路網站加入會議，且有參與者從 PSTN 加入相同的會議，則不允許來自不同網路網站的 Lync 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="1eb86-118">下表摘要列出了這些會議位置的路由限制。</span><span class="sxs-lookup"><span data-stu-id="1eb86-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eb86-119">在任何指定點的會議中的使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="1eb86-120">允許使用者加入會議</span><span class="sxs-lookup"><span data-stu-id="1eb86-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="1eb86-121">不允許使用者加入會議</span><span class="sxs-lookup"><span data-stu-id="1eb86-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eb86-122">從單一網路網站 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="1eb86-123">從同一個網路網站 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="1eb86-124">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="1eb86-125">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="1eb86-126">聯盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="1eb86-127">從 PSTN 端點加入的使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1eb86-128">無</span><span class="sxs-lookup"><span data-stu-id="1eb86-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eb86-129">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="1eb86-130">來自任何網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="1eb86-131">來自未知網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="1eb86-132">聯盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="1eb86-133">透過 PSTN 端點加入的使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eb86-134">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="1eb86-135">來自任何網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="1eb86-136">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="1eb86-137">聯盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="1eb86-138">透過 PSTN 端點加入的使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eb86-139">從單一網路網站與從 PSTN 端點加入的使用者進行 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="1eb86-140">從同一個網路網站 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="1eb86-141">來自不同網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="1eb86-142">來自未知網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="1eb86-143">聯盟 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="1eb86-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1eb86-144">下列是 [以位置為基礎的路由會議] 應用程式的其他特性：</span><span class="sxs-lookup"><span data-stu-id="1eb86-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="1eb86-145">如果使用者不允許加入會議指定的位置路由限制，則使用者呼叫會議將會遭到拒絕，而他的 Lync 用戶端會報告通話未完成或已結束。</span><span class="sxs-lookup"><span data-stu-id="1eb86-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="1eb86-146">使用以位置為基礎的路由 enforcements 加入會議的 PSTN 端點不會限制加入會議，無論端點是透過不是以位置式路由的幹線來連接。</span><span class="sxs-lookup"><span data-stu-id="1eb86-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="1eb86-147">透過不是出局呼叫的 SIP 幹線連線至 Mediations 伺服器的 PBX 系統，將會擁有與在已定義 SIP 幹線之相同網路網站中的 Lync 使用者相同的 enforcements。</span><span class="sxs-lookup"><span data-stu-id="1eb86-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="1eb86-148">例如，PSTN 端點將能夠加入與 PBX 使用者和 Lync 使用者位於相同網路網站中的會議;否則，如果 PBX 使用者與 Lync 使用者不在不同的網路網站，則不允許 PSTN 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="1eb86-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

