---
title: Lync Server 2013：會議 Location-Based 路由的需求
description: Lync Server 2013：會議 Location-Based 路由的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements for Location-Based Routing for conferencing
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56335085
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbaa1af2690c3148d2ecfb173b13be288a21d80f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542519"
---
# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="c95f5-103">在 Lync Server 2013 中 Location-Based 路由進行會議的需求</span><span class="sxs-lookup"><span data-stu-id="c95f5-103">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c95f5-104">_**主題上次修改日期：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="c95f5-104">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="c95f5-105">以下是安裝和設定 Location-Based 路由會議應用程式所需的需求：</span><span class="sxs-lookup"><span data-stu-id="c95f5-105">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c95f5-106">Lync Server 2013 累計更新2必須部署在拓撲中的所有伺服器或集區上。</span><span class="sxs-lookup"><span data-stu-id="c95f5-106">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95f5-107">如果您拓撲中的 Lync server 或集區未安裝 Lync Server 2013 累計更新2或更新版本，則無法保證 Lync 會議的 Location-Based 路由的執行。</span><span class="sxs-lookup"><span data-stu-id="c95f5-107">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="c95f5-108">Lync Server 2013 Location-Based 路由是 Location-Based 路由會議應用程式的必要條件。</span><span class="sxs-lookup"><span data-stu-id="c95f5-108">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="c95f5-109">如需設定 Lync Server 2013 Location-Based 路由的詳細資訊，請參閱設定 [Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="c95f5-109">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="c95f5-110">Location-Based 路由會議應用程式的需求與 Lync Server 2013 Location-Based 路由的需求相同。</span><span class="sxs-lookup"><span data-stu-id="c95f5-110">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="c95f5-111">如需詳細資訊，請參閱 [規劃 Location-Based 路由](lync-server-2013-planning-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="c95f5-111">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="c95f5-112">支援的伺服器</span><span class="sxs-lookup"><span data-stu-id="c95f5-112">Supported Servers</span></span>

<span data-ttu-id="c95f5-113">Location-Based 路由會議應用程式要求在拓撲中的所有 Front-End 集區和 Standard Edition Server 上部署 Lync Server 2013 累計更新2。</span><span class="sxs-lookup"><span data-stu-id="c95f5-113">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="c95f5-114">如果您在拓撲中的某些 Lync Server 上未安裝 Lync Server 2013 累計更新2，則在 Lync 會議和顧問式來電轉接上，無法完全強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="c95f5-114">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="c95f5-115">下表識別伺服器角色與支援 Location-Based 路由的版本的組合。</span><span class="sxs-lookup"><span data-stu-id="c95f5-115">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c95f5-116">Front-End 集區版本</span><span class="sxs-lookup"><span data-stu-id="c95f5-116">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="c95f5-117">轉送伺服器版本</span><span class="sxs-lookup"><span data-stu-id="c95f5-117">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="c95f5-118">支援</span><span class="sxs-lookup"><span data-stu-id="c95f5-118">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95f5-119">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="c95f5-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-120">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="c95f5-120">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-121">是</span><span class="sxs-lookup"><span data-stu-id="c95f5-121">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95f5-122">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="c95f5-122">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-123">Lync Server 2013 累計更新1</span><span class="sxs-lookup"><span data-stu-id="c95f5-123">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="c95f5-124">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-124">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95f5-125">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="c95f5-125">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-126">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c95f5-126">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c95f5-127">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-127">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95f5-128">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="c95f5-128">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-129">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c95f5-129">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-130">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95f5-131">Lync Server 2013 累計更新1</span><span class="sxs-lookup"><span data-stu-id="c95f5-131">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="c95f5-132">任何</span><span class="sxs-lookup"><span data-stu-id="c95f5-132">Any</span></span></p></td>
<td><p><span data-ttu-id="c95f5-133">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c95f5-134">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="c95f5-134">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="c95f5-135">任何</span><span class="sxs-lookup"><span data-stu-id="c95f5-135">Any</span></span></p></td>
<td><p><span data-ttu-id="c95f5-136">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-136">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c95f5-137">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c95f5-137">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="c95f5-138">任何</span><span class="sxs-lookup"><span data-stu-id="c95f5-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c95f5-139">否</span><span class="sxs-lookup"><span data-stu-id="c95f5-139">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="c95f5-140">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="c95f5-140">Supported Clients</span></span>

<span data-ttu-id="c95f5-141">支援 Lync 會議 Location-Based 路由的 Lync 用戶端，都是支援 Lync Server 2013 Location-Based 路由的相同用戶端。</span><span class="sxs-lookup"><span data-stu-id="c95f5-141">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="c95f5-142">如需詳細資訊，請參閱 [用戶端和伺服器支援，以取得 Location-Based 路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="c95f5-142">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="c95f5-143">顧問式來電轉接的轉送伺服器需求</span><span class="sxs-lookup"><span data-stu-id="c95f5-143">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="c95f5-144">Location-Based 路由會議應用程式需要部署獨立的轉送伺服器，才可在顧問式來電轉接上強制執行 Location-Based 路由限制。</span><span class="sxs-lookup"><span data-stu-id="c95f5-144">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="c95f5-145">若要強制 Location-Based 路由傳送諮詢來電轉接，轉送伺服器必須與網路地區的一個轉送伺服器對等 (（即 PBX、SIP 閘道等) ）相關聯，Location-Based 路由是必要的。</span><span class="sxs-lookup"><span data-stu-id="c95f5-145">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="c95f5-146">若其他轉送伺服器對等部署在相同的網路地區，則轉送伺服器必須與不同的轉送伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="c95f5-146">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="c95f5-147">這項需求如下所述：</span><span class="sxs-lookup"><span data-stu-id="c95f5-147">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="c95f5-148">每個轉送伺服器對等的單一轉送伺服器當諮詢來電轉接透過已設定多個 SIP 主幹至多個對等 (（亦即 PBXs 和閘道) ）的轉送伺服器路由傳送至轉送伺服器對等時，如果允許透過某些 SIP 主幹，但禁止透過其他 SIP 主幹進行諮詢來電轉接，便會封鎖諮詢來電轉接，以防止 PSTN 長途電話旁路。</span><span class="sxs-lookup"><span data-stu-id="c95f5-148">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="c95f5-149">例如，如果單一轉送伺服器服務于 PSTN 閘道轉送伺服器對等和 PBX 轉送伺服器對等專案，則會觀測下列行為：</span><span class="sxs-lookup"><span data-stu-id="c95f5-149">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="c95f5-150">指定網站的 Lync 使用者 (例如，site 1) 嘗試使用 PSTN 端點將來電轉接至不同網站中的 Lync 使用者 (亦即，site 2) 透過顧問式轉接，將不允許通話，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="c95f5-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="c95f5-151">指定的網站中的 Lync 使用者 (亦即，site 1) 會嘗試在相同網站 (網站 1) 將來電轉接至不同網站的 Lync 使用者 (亦例如，site 2) 透過諮詢轉接，即使不是出現在潛在的 PSTN 長途電話中，也不會允許通話。</span><span class="sxs-lookup"><span data-stu-id="c95f5-151">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="c95f5-152">每個轉送伺服器對等各有不同的轉送伺服器</span><span class="sxs-lookup"><span data-stu-id="c95f5-152">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="c95f5-153">當以轉送伺服器對等方式設定諮詢轉移時，系統會根據轉送伺服器所提供的單一轉送伺服器對等方式來評估顧問式轉接。</span><span class="sxs-lookup"><span data-stu-id="c95f5-153">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="c95f5-154">此呼叫會因其可能導致 PSTN 電話略過的情況而受到允許或允許，不論其他的轉送伺服器服務于網站中的所有其他 Mediations Server 對等專案。</span><span class="sxs-lookup"><span data-stu-id="c95f5-154">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="c95f5-155">例如，在為 PSTN 閘道轉送伺服器對等和 PBX 轉送伺服器對等的個別轉送伺服器提供服務時，會看到下列行為：</span><span class="sxs-lookup"><span data-stu-id="c95f5-155">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="c95f5-156">指定網站的 Lync 使用者 (例如，site 1) 嘗試使用 PSTN 端點將來電轉接至不同網站中的 Lync 使用者 (亦即，site 2) 透過顧問式轉接，將不允許通話，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="c95f5-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="c95f5-157">指定的網站中的 Lync 使用者 (亦即，site 1) 會嘗試在相同網站 (網站 1) 將來電轉接至不同網站的 Lync 使用者 (亦例如，site 2) 透過顧問式轉接，但會允許通話，但不是在潛在的 PSTN 長途電話略過。</span><span class="sxs-lookup"><span data-stu-id="c95f5-157">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="c95f5-158">Location-Based 路由會議應用程式不支援的功能</span><span class="sxs-lookup"><span data-stu-id="c95f5-158">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="c95f5-159">Location-Based 路由會議應用程式不支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="c95f5-159">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="c95f5-160">電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="c95f5-160">Dial-in conferencing.</span></span> <span data-ttu-id="c95f5-161">無法對電話撥入式會議強制執行 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="c95f5-161">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="c95f5-162">即使會議召集人是啟用 Location-Based 路由的 Lync 使用者，Location-Based 路由也不會限制任何對指定會議的撥入要求。</span><span class="sxs-lookup"><span data-stu-id="c95f5-162">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="c95f5-163">建議您不要在需要強制執行 Location-Based 路由限制的區域中布建會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="c95f5-163">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

