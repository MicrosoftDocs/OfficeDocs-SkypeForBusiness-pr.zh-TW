---
title: 電話撥入會議的位置型路由的 Lync Server 2013： 概觀
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
ms.openlocfilehash: 1b280272d17cf40734a24b553ad00a7a485547c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="dfbf3-102">Lync Server 2013 中的會議位置型路由的概觀</span><span class="sxs-lookup"><span data-stu-id="dfbf3-102">Overview of Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfbf3-103">_**上次修改主題：** 2013年-07-19_</span><span class="sxs-lookup"><span data-stu-id="dfbf3-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="dfbf3-104">位置型路由會議應用程式提供 Lync 會議的 PSTN 通話費防護機制略過。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-104">The Location-Based Routing Conferencing application provides to Lync Conferences a mechanism for the prevention of PSTN toll bypass.</span></span> <span data-ttu-id="dfbf3-105">應用程式監視作用中的會議，並強制執行的位置型路由限制根據參與 Lync 使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-105">The application monitors active conferences and enforces Location-Based Routing restrictions based on the location of the Lync users participating.</span></span>

<span data-ttu-id="dfbf3-106">位置型路由會議應用程式會決定是否是如果符合下列準則，則會強制執行 Lync 會議位置型的路由：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-106">The Location-Based Routing Conferencing application determines whether Location-Based Routing is to be enforced on a Lync meeting if the following criteria are met:</span></span>

  - <span data-ttu-id="dfbf3-107">會議召集人會啟用位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-107">The meeting organizer is enabled for Location-Based Routing.</span></span> <span data-ttu-id="dfbf3-108">位置型路由限制將會是只套用至由位置型路由已啟用的使用者安排的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-108">Location-Based Routing restrictions will be applied only to conferences that are organized by users who are enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="dfbf3-109">至少一位會議參與者是 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-109">At least one meeting participant is a PSTN endpoint.</span></span> <span data-ttu-id="dfbf3-110">位置型路由限制將僅適用於包含 PSTN 端點的會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-110">Location-Based Routing restrictions are applicable only for conferences that include PSTN endpoints.</span></span>

  - <span data-ttu-id="dfbf3-111">用來橋接至 PSTN 會議的 PSTN 閘道的所在位置以及從何處網際網路連接參與者與召集人的網路站台的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-111">The network site where the PSTN gateway used to bridge the conference to the PSTN is located as well as the network sites where the organizers and participants are connecting from.</span></span>

<span data-ttu-id="dfbf3-112">位置型路由會議應用程式可防止 Lync 使用者和來自不同網路網站的 PSTN 端點，才能在同一場會議參與。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-112">The Location-Based Routing Conferencing application prevents the participation of Lync users and PSTN endpoints from different network sites to the same conference.</span></span> <span data-ttu-id="dfbf3-113">如果會議的召集人啟用位置型的路由，會議應用程式強制執行下列限制：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-113">If the organizer of a meeting is enabled for Location-Based Routing, the Conferencing application enforces the following restrictions:</span></span>

  - <span data-ttu-id="dfbf3-114">可加入 Lync 會議的端點取決於已加入會議的端點這項限制會調整以加入的端點離開和新端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-114">The endpoints that can join a Lync meeting depend on the endpoints that already joined the conference, and this restriction adjusts as joined endpoints leave and new endpoints join the conference.</span></span> <span data-ttu-id="dfbf3-115">如果召集人與參與者加入相同的網路網站，然後將 PSTN 端點的 Lync 會議，允許從相同網路站台、 從不同的網路網站的其他參與者或從不明的網路網站參與者的另一位參與者加入。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-115">If organizers and participants are joining a Lync meeting from the same network site, then a PSTN endpoint, another participant from the same network site, another participant from a different network site or a participant from an unknown network site are allowed to join.</span></span>

  - <span data-ttu-id="dfbf3-116">如果召集人與參與者加入會議從不同] 或 [未知的網路網站，不允許加入會議，如果 PSTN 通話 ingresses 從啟用位置型路由的 SIP 主幹的 PSTN 端點。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-116">If organizers and participants are joining the meeting from different or unknown network sites, a PSTN endpoint is not allowed to join the meeting if the PSTN call ingresses from a SIP trunk enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="dfbf3-117">如果召集人與參與者所有加入會議從相同網路網站，且沒有加入相同從 PSTN 會議的參與者，不允許從不同的網路網站的 Lync 端點加入會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-117">If organizers and participants are all joining the meeting from the same network site and there are participants joining the same meeting from the PSTN, a Lync endpoint from a different network site is not allowed to join the meeting.</span></span>

<span data-ttu-id="dfbf3-118">下表摘要說明這些會議位置型路由限制。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-118">These conferencing Location-Based Routing restrictions are summarized in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfbf3-119">在任何特定時間點會議中的使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-119">User(s) in a conference at any given point</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-120">允許加入會議的使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-120">User(s) allowed to join the conference</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-121">不允許加入會議的使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-121">User(s) not allowed to join the conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfbf3-122">從單一網路網站的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-122">Lync VoIP client user(s) from a single network site</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-123">Lync VoIP 用戶端使用者從相同網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-123">Lync VoIP client user from the same network site</span></span></p>
<p><span data-ttu-id="dfbf3-124">Lync VoIP 用戶端使用者從不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-124">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="dfbf3-125">Lync VoIP 用戶端使用者的未知的網路站台</span><span class="sxs-lookup"><span data-stu-id="dfbf3-125">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="dfbf3-126">同盟的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-126">Federated Lync VoIP client user</span></span></p>
<p><span data-ttu-id="dfbf3-127">使用者加入從 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="dfbf3-127">User joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-128">無</span><span class="sxs-lookup"><span data-stu-id="dfbf3-128">None</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfbf3-129">Lync VoIP 用戶端使用者的未知的網路站台</span><span class="sxs-lookup"><span data-stu-id="dfbf3-129">Lync VoIP client user(s) from an unknown network site</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-130">Lync VoIP 用戶端使用者從任何網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-130">Lync VoIP client user from any site</span></span></p>
<p><span data-ttu-id="dfbf3-131">Lync VoIP 用戶端使用者的未知的站台</span><span class="sxs-lookup"><span data-stu-id="dfbf3-131">Lync VoIP client user from an unknown site</span></span></p>
<p><span data-ttu-id="dfbf3-132">同盟的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-132">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-133">使用者加入透過 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="dfbf3-133">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfbf3-134">Lync VoIP 用戶端使用者從不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-134">Lync VoIP client users from different network sites</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-135">Lync VoIP 用戶端使用者從任何網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-135">Lync VoIP client user from any network site</span></span></p>
<p><span data-ttu-id="dfbf3-136">Lync VoIP 用戶端使用者的未知的網路站台</span><span class="sxs-lookup"><span data-stu-id="dfbf3-136">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="dfbf3-137">同盟的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-137">Federated Lync VoIP client user</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-138">使用者加入透過 PSTN 端點</span><span class="sxs-lookup"><span data-stu-id="dfbf3-138">User joining via a PSTN endpoint</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfbf3-139">從單一的網站和來自 PSTN 端點加入使用者的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-139">Lync VoIP client user(s) from a single network site and users joining from a PSTN endpoint</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-140">Lync VoIP 用戶端使用者從相同網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-140">Lync VoIP client user from the same network site</span></span></p></td>
<td><p><span data-ttu-id="dfbf3-141">Lync VoIP 用戶端使用者從不同的網路網站</span><span class="sxs-lookup"><span data-stu-id="dfbf3-141">Lync VoIP client user from a different network site</span></span></p>
<p><span data-ttu-id="dfbf3-142">Lync VoIP 用戶端使用者的未知的網路站台</span><span class="sxs-lookup"><span data-stu-id="dfbf3-142">Lync VoIP client user from an unknown network site</span></span></p>
<p><span data-ttu-id="dfbf3-143">同盟的 Lync VoIP 用戶端使用者</span><span class="sxs-lookup"><span data-stu-id="dfbf3-143">Federated Lync VoIP client user</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfbf3-144">以下是依位置路由會議應用程式的其他特性：</span><span class="sxs-lookup"><span data-stu-id="dfbf3-144">The following are additional characteristics of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="dfbf3-145">時不允許使用者加入會議，指定位置型路由限制時，會拒絕會議的使用者呼叫而其 Lync 用戶端將報告，在呼叫未完成，或已經結束。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-145">When a user is not allowed to join a conference given Location-Based Routing restrictions, the users call to the conference will be rejected and his Lync Client will report that the call was not completed or has ended.</span></span>

  - <span data-ttu-id="dfbf3-146">以位置為主的路由 enforcements 會議將不會限制為不論其狀態加入會議，如果將端點加入未啟用位置型路由主幹透過 PSTN 端點加入。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-146">A PSTN endpoint joining a conference with Location-Based Routing enforcements will not be restricted to join the conference regardless of its state if the endpoint joins via a trunk that is not enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="dfbf3-147">連接至 Mediations 伺服器透過 SIP 主幹，不會不輸出至 PSTN 通話的 PBX 系統會有相同的 enforcements 為 Lync 使用者位於相同網路站台定義 SIP 主幹的位置。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-147">A PBX system connected to a Mediations Server over a SIP trunk that does not egress calls to the PSTN will have the same enforcements as Lync users located in the same network site where the SIP trunk is defined.</span></span> <span data-ttu-id="dfbf3-148">例如，PSTN 端點將能夠加入 PBX 使用者與 Lync 使用者的會議，如果他們都位於相同的網路網站;否則，將不允許 PSTN 端點，如果 PBX 使用者位於不同的網路站台比 Lync 使用者加入會議。</span><span class="sxs-lookup"><span data-stu-id="dfbf3-148">For example, a PSTN endpoint will be able to join a conference with a PBX user and a Lync user if they are located in the same network site; otherwise, the PSTN endpoint will not be allowed to join the conference if the PBX user is in a different network site than the Lync user.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

