---
title: Lync Server 2013：適用于會議的位置路由需求
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
ms.openlocfilehash: ac57a32476d80ab1aca5d2ad0928e2862a4c8558
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="fb1f8-102">Lync Server 2013 中針對位置路由的會議需求</span><span class="sxs-lookup"><span data-stu-id="fb1f8-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb1f8-103">_**主題上次修改日期：** 2013-07-19_</span><span class="sxs-lookup"><span data-stu-id="fb1f8-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="fb1f8-104">以下是安裝與設定以位置為基礎的路由會議應用程式所需的需求：</span><span class="sxs-lookup"><span data-stu-id="fb1f8-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="fb1f8-105">Lync Server 2013 累計更新2必須部署在您拓撲中的所有伺服器或池上。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fb1f8-106">如果您拓撲中的 Lync server 或 pool 沒有安裝 Lync Server 2013 累積更新2或更新版本，則無法保證 Lync 會議的位置路由。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="fb1f8-107">Lync Server 2013 以位置為基礎的路由是位置路由會議應用程式的先決條件。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="fb1f8-108">如需有關設定 Lync Server 2013 位置路由的進一步資訊，請參閱設定以[位置為基礎的路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="fb1f8-109">以位置為基礎的路由會議應用程式的需求與 Lync Server 2013 位置路由的需求相同。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="fb1f8-110">如需詳細資訊，請參閱[規劃以位置為基礎的路由](lync-server-2013-planning-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="fb1f8-111">支援的伺服器</span><span class="sxs-lookup"><span data-stu-id="fb1f8-111">Supported Servers</span></span>

<span data-ttu-id="fb1f8-112">以位置為基礎的路由會議應用程式要求 Lync Server 2013 累計更新2部署在您拓撲中的所有前端池和標準版伺服器上。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="fb1f8-113">如果您在拓撲中的部分 Lync 伺服器上沒有安裝 Lync Server 2013 累積更新2，則無法在 Lync 會議和諮詢式來電轉接上完全強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="fb1f8-114">下表列出支援位置路由的伺服器角色與版本組合。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb1f8-115">前端池版本</span><span class="sxs-lookup"><span data-stu-id="fb1f8-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-116">中繼伺服器版本</span><span class="sxs-lookup"><span data-stu-id="fb1f8-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-117">受</span><span class="sxs-lookup"><span data-stu-id="fb1f8-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb1f8-118">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-119">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-120">是</span><span class="sxs-lookup"><span data-stu-id="fb1f8-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb1f8-121">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-122">Lync Server 2013 累計更新1</span><span class="sxs-lookup"><span data-stu-id="fb1f8-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-123">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb1f8-124">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fb1f8-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-126">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb1f8-127">Lync Server 2013 累計更新2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-128">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-129">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb1f8-130">Lync Server 2013 累計更新1</span><span class="sxs-lookup"><span data-stu-id="fb1f8-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-131">每</span><span class="sxs-lookup"><span data-stu-id="fb1f8-131">Any</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-132">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb1f8-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fb1f8-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-134">每</span><span class="sxs-lookup"><span data-stu-id="fb1f8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-135">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb1f8-136">Office 通訊伺服器 2007 R2</span><span class="sxs-lookup"><span data-stu-id="fb1f8-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-137">每</span><span class="sxs-lookup"><span data-stu-id="fb1f8-137">Any</span></span></p></td>
<td><p><span data-ttu-id="fb1f8-138">否</span><span class="sxs-lookup"><span data-stu-id="fb1f8-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="fb1f8-139">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="fb1f8-139">Supported Clients</span></span>

<span data-ttu-id="fb1f8-140">支援 lync 會議以位置為基礎路由的 Lync 用戶端，是支援 Lync Server 2013 位置路由的相同用戶端。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="fb1f8-141">如需詳細資訊，請參閱[用戶端與伺服器支援的位置路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="fb1f8-142">針對諮詢式來電轉接的中繼伺服器需求</span><span class="sxs-lookup"><span data-stu-id="fb1f8-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="fb1f8-143">以位置為基礎的路由會議應用程式需要部署獨立的中繼伺服器，才能在諮詢式來電轉接上強制執行以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="fb1f8-144">若要強制進行依位置路由的諮詢式來電轉接，中繼伺服器必須與網路區域中的一個中繼伺服器對等（亦即 PBX、SIP 閘道等）建立關聯，且需要以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="fb1f8-145">如果有其他的轉送伺服器對等部署在相同的網路區域中，則必須將中繼伺服器對等專案與不同的中繼伺服器產生關聯。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="fb1f8-146">此需求如下所述：</span><span class="sxs-lookup"><span data-stu-id="fb1f8-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="fb1f8-147">在每個多個中繼伺服器對等的情況下，如果將諮詢式來電轉接傳送給中繼伺服器對多個對等（例如 Pbx 和閘道）所設定的轉送伺服器，請諮詢如果允許透過某些 SIP trunks 進行諮詢式來電轉接，但不允許透過其他 SIP trunks，通話轉移遭到封鎖，以避免 PSTN 長途電話旁路。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="fb1f8-148">例如，如果單一中繼伺服器提供服務于 PSTN 閘道伺服器對等與 PBX 轉送伺服器對等，則會觀察到下列行為：</span><span class="sxs-lookup"><span data-stu-id="fb1f8-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="fb1f8-149">當來自特定網站的 Lync 使用者（亦即網站1）嘗試透過諮詢式轉接從不同的網站（亦即 site 2），從另一個網站（亦稱為 site 2）的 PSTN 端點轉接來電時，該呼叫將不能避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="fb1f8-150">當來自特定網站的 Lync 使用者（亦即網站1）嘗試從另一個網站（網站1）的 PBX 端點將來電轉接至 Lync 使用者（亦即 site 2）從顧問式轉接傳送時，即使該通話不會出現在潛在的 PSTN tol 中，也不允許呼叫。l 略過。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="fb1f8-151">針對每個中繼伺服器對等不同的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="fb1f8-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="fb1f8-152">當導向式轉接以中繼伺服器對等為目標時，會針對中繼伺服器所服務的單一中繼伺服器對等來評估諮詢式轉移。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="fb1f8-153">如果網站中的所有其他 Mediations 伺服器對都是由個別的中繼伺服器提供服務，則會禁止或允許呼叫（根據其在 PSTN 免付費旁路中的可能性）。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="fb1f8-154">例如，在個別的中繼伺服器為 PSTN 閘道轉送伺服器對等，以及 PBX 轉送伺服器對等時，系統會觀察到下列行為：</span><span class="sxs-lookup"><span data-stu-id="fb1f8-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="fb1f8-155">當來自特定網站的 Lync 使用者（亦即網站1）嘗試透過諮詢式轉接從不同的網站（亦即 site 2），從另一個網站（亦稱為 site 2）的 PSTN 端點轉接來電時，該呼叫將不能避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="fb1f8-156">當來自特定網站的 Lync 使用者（亦即網站1）嘗試從另一個網站（網站1）的 PBX 端點將來電轉接至 Lync 使用者（亦即網站2）透過顧問式轉接傳送時，會允許通話，因為在潛在的 PSTN 免付費旁路中不會發生這種情況。運算.</span><span class="sxs-lookup"><span data-stu-id="fb1f8-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="fb1f8-157">以位置為基礎的路由會議應用程式不支援的功能</span><span class="sxs-lookup"><span data-stu-id="fb1f8-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="fb1f8-158">以位置為基礎的路由會議應用程式不支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="fb1f8-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="fb1f8-159">電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-159">Dial-in conferencing.</span></span> <span data-ttu-id="fb1f8-160">在電話撥入式會議中不能強制執行以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="fb1f8-161">即使會議召集人是啟用位置路由的 Lync 使用者，任何對指定會議的撥入要求不會受到依位置路由的限制。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="fb1f8-162">建議您不要在需要強制執行位置式路由限制的區域中，設定會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="fb1f8-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

