---
title: 電話撥入會議的位置型路由的 Lync Server 2013： 需求
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
ms.openlocfilehash: 4ce41a338f3185f6f051da3df41e91c6b287af20
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="requirements-for-location-based-routing-for-conferencing-in-lync-server-2013"></a><span data-ttu-id="5b7f6-102">Lync Server 2013 中的會議位置型路由的需求</span><span class="sxs-lookup"><span data-stu-id="5b7f6-102">Requirements for Location-Based Routing for conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b7f6-103">_**上次修改主題：** 2013年-07-19_</span><span class="sxs-lookup"><span data-stu-id="5b7f6-103">_**Topic Last Modified:** 2013-07-19_</span></span>

<span data-ttu-id="5b7f6-104">所需的安裝與設定位置型路由會議應用程式的需求如下：</span><span class="sxs-lookup"><span data-stu-id="5b7f6-104">The following are the requirements needed for the installation and configuration of the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="5b7f6-105">必須在所有伺服器或集區拓撲中的部署 Lync Server 2013 累計更新 2年。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-105">Lync Server 2013 Cumulative Update 2 must be deployed on all servers or pools in your topology.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b7f6-106">如果在 Lync server 或集區拓撲中的不需要 Lync Server 2013 累計更新 2年或更新版本，不能保證的 Lync 會議的位置型路由的強制執行。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-106">If a Lync server or pool in your topology does not have Lync Server 2013 Cumulative Update 2 or higher installed, then enforcement of Location-Based Routing of Lync meetings cannot be guaranteed.</span></span>



</div>

  - <span data-ttu-id="5b7f6-107">Lync Server 2013 位置型路由是依位置路由會議應用程式的必要條件。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-107">Lync Server 2013 Location-Based Routing is a pre-requisite for Location-Based Routing Conferencing application.</span></span> <span data-ttu-id="5b7f6-108">如需設定 Lync Server 2013 Location-Based 路由的進一步資訊，請參閱[Configuring Location-Based 路由](lync-server-2013-configuring-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-108">For further information on configuring Lync Server 2013 Location-Based Routing, please refer to [Configuring Location-Based Routing](lync-server-2013-configuring-location-based-routing.md).</span></span>

  - <span data-ttu-id="5b7f6-109">位置型路由會議應用程式的需求都是 Lync Server 2013 Location-Based 路由的需求相同。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-109">Requirements of Location-Based Routing Conferencing application are the same as the requirements for Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="5b7f6-110">如需詳細資訊，請參閱[Planning for 位置型的路由](lync-server-2013-planning-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-110">For more information, please refer to [Planning for Location-Based Routing](lync-server-2013-planning-for-location-based-routing.md).</span></span>

<div>

## <a name="supported-servers"></a><span data-ttu-id="5b7f6-111">支援的伺服器</span><span class="sxs-lookup"><span data-stu-id="5b7f6-111">Supported Servers</span></span>

<span data-ttu-id="5b7f6-112">位置型路由會議應用程式需要上所有的前端集區和 Standard Edition 伺服器，在您的拓撲中已部署了 Lync Server 2013 累計更新 2年。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-112">The Location-Based Routing Conferencing application requires that Lync Server 2013 Cumulative Update 2 is deployed on all Front-End pools and Standard Edition Servers in your topology.</span></span> <span data-ttu-id="5b7f6-113">如果您的拓樸某些 Lync 伺服器上未安裝 Lync Server 2013 累計更新 2年，位置型路由限制無法完全強制在 Lync 會議和諮詢呼叫傳輸。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-113">If Lync Server 2013 Cumulative Update 2 is not installed on some Lync Servers in your topology, Location-Based Routing restrictions cannot be fully enforced on Lync meetings and consultative call transfers.</span></span>

<span data-ttu-id="5b7f6-114">下表列出伺服器角色和支援位置型路由的版本的組合。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-114">The following table identifies the combination of server roles and versions that support Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b7f6-115">前端集區版本</span><span class="sxs-lookup"><span data-stu-id="5b7f6-115">Front-End Pool version</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-116">中繼伺服器版本</span><span class="sxs-lookup"><span data-stu-id="5b7f6-116">Mediation Server version</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-117">支援</span><span class="sxs-lookup"><span data-stu-id="5b7f6-117">Supported</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b7f6-118">Lync Server 2013 累計更新 2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-118">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-119">Lync Server 2013 累計更新 2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-119">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-120">是</span><span class="sxs-lookup"><span data-stu-id="5b7f6-120">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b7f6-121">Lync Server 2013 累計更新 2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-121">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-122">Lync Server 2013 累計更新 1</span><span class="sxs-lookup"><span data-stu-id="5b7f6-122">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-123">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-123">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b7f6-124">Lync Server 2013 累計更新 2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-124">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-125">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5b7f6-125">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-126">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-126">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b7f6-127">Lync Server 2013 累計更新 2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-127">Lync Server 2013 Cumulative Update 2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-128">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-128">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-129">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-129">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b7f6-130">Lync Server 2013 累計更新 1</span><span class="sxs-lookup"><span data-stu-id="5b7f6-130">Lync Server 2013 Cumulative Update 1</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-131">任何</span><span class="sxs-lookup"><span data-stu-id="5b7f6-131">Any</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-132">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-132">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b7f6-133">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5b7f6-133">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-134">任何</span><span class="sxs-lookup"><span data-stu-id="5b7f6-134">Any</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-135">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-135">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b7f6-136">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5b7f6-136">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-137">任何</span><span class="sxs-lookup"><span data-stu-id="5b7f6-137">Any</span></span></p></td>
<td><p><span data-ttu-id="5b7f6-138">否</span><span class="sxs-lookup"><span data-stu-id="5b7f6-138">No</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients"></a><span data-ttu-id="5b7f6-139">支援的用戶端</span><span class="sxs-lookup"><span data-stu-id="5b7f6-139">Supported Clients</span></span>

<span data-ttu-id="5b7f6-140">支援的 Lync 會議的位置 Routing Lync 用戶端將相同的用戶端支援 Lync Server 2013 Location-Based 路由。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-140">The Lync clients that support Location-Based Routing of Lync meetings are the same clients that support Lync Server 2013 Location-Based Routing.</span></span> <span data-ttu-id="5b7f6-141">如需詳細資訊，請參閱[用戶端與伺服器支援位置型的路由](lync-server-2013-client-and-server-support-for-location-based-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-141">For more information, please refer to [Client and Server Support for Location-Based Routing](lync-server-2013-client-and-server-support-for-location-based-routing.md).</span></span>

</div>

<div>

## <a name="mediation-server-requirements-for-consultative-call-transfers"></a><span data-ttu-id="5b7f6-142">諮詢轉接的中繼伺服器需求</span><span class="sxs-lookup"><span data-stu-id="5b7f6-142">Mediation Server Requirements for Consultative Call Transfers</span></span>

<span data-ttu-id="5b7f6-143">位置型路由會議應用程式需要以強制執行諮詢轉接的位置型路由限制部署獨立中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-143">The Location-Based Routing Conferencing application requires deploying stand-alone Mediation Servers in order to enforce Location-Based Routing restrictions on consultative call transfers.</span></span>

<span data-ttu-id="5b7f6-144">強制執行的諮詢轉接位置型路由，中繼伺服器必須與只有一個中繼伺服器對等網路建立關聯 (亦即 PBX、 SIP 閘道等等) 其中位置型路由是必要的網路地區。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-144">To enforce Location-Based Routing of consultative call transfers, the Mediation Server must be associated with only one Mediation Server peer (i.e. PBX, SIP gateway, etc) in network regions where Location-Based Routing is required.</span></span> <span data-ttu-id="5b7f6-145">如果其他媒體伺服器對等會部署在相同的網路地區中，將中繼伺服器對等網路必須與不同的中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-145">If additional Mediation Server peers are deployed in the same network region, the Mediation Server peer must be associated with a different Mediation Server .</span></span> <span data-ttu-id="5b7f6-146">這項需求詳細說明，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5b7f6-146">This Requirement is detailed as follows:</span></span>

  - <span data-ttu-id="5b7f6-147">每個多個中繼伺服器的單一中繼伺服器對等時諮詢的來電轉接會路由傳送到已設定至多個對等 （亦即 Pbx 與閘道） 的多個 SIP 主幹與諮詢中繼伺服器到中繼伺服器對等網路若要防止諮詢的來電轉接為允許通過某些 SIP 主幹，但不允許透過其他 SIP 主幹的 PSTN 通話費略過會阻止來電轉接。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-147">Single Mediation Server per multiple Mediation Server peers When a consultative call transfer is routed to a Mediation Server peer through a Mediation Server that’s configured with multiple SIP trunks to multiple peers (i.e. PBXs and gateways), the consultative call transfer is blocked to prevent PSTN toll bypass if the consultative call transfer is permitted through some SIP trunks but disallowed through other SIP trunks.</span></span>
    
    <span data-ttu-id="5b7f6-148">例如，若是單一中繼伺服器 PSTN 閘道中繼伺服器對等和 PBX 中繼伺服器對等服務，將會遵守下列行為：</span><span class="sxs-lookup"><span data-stu-id="5b7f6-148">For example, in the case of a single Mediation Server servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="5b7f6-149">當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與 PSTN 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會不允許若要防止 PSTN 通話費略過。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-149">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="5b7f6-150">即使它不會造成潛在 PSTN 工具中，當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與中相同的網站 （網站 1） 的 PBX 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，將不允許通話l 略過。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-150">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed even if it doesn’t incur in potential PSTN toll bypassing.</span></span>

  - <span data-ttu-id="5b7f6-151">不同每中繼伺服器對等的中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="5b7f6-151">Separate Mediation Servers per Mediation Server peer</span></span>
    
    <span data-ttu-id="5b7f6-152">當諮詢轉接財經中繼伺服器對等網路時，針對單一中繼伺服器所服務的中繼伺服器對等會評估諮詢轉接。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-152">When a consultative transfer is targeted at a Mediation Server Peer, the consultative transfer will be evaluated against the single Mediation Server Peer serviced by the Mediation Server.</span></span> <span data-ttu-id="5b7f6-153">將不允許或允許通話總部在其可能會引起不論網站中所有其他 Mediations 伺服器對等的 PSTN 通話費略過，因為它們由不同的中繼伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-153">The call will be disallowed or allowed based in its potential to incur in PSTN toll bypass regardless of all other Mediations Server Peers in the site as they’re serviced by separate Mediation Servers.</span></span>
    
    <span data-ttu-id="5b7f6-154">例如，在不同的中繼伺服器 PSTN 閘道中繼伺服器對等和 PBX 中繼伺服器對等服務，將會遵守下列行為：</span><span class="sxs-lookup"><span data-stu-id="5b7f6-154">For example, in the case of a separate Mediation Servers servicing a PSTN Gateway Mediation Server Peer and a PBX Mediation Server Peer, the following behavior will be observed:</span></span>
    
      - <span data-ttu-id="5b7f6-155">當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與 PSTN 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會不允許若要防止 PSTN 通話費略過。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-155">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PSTN endpoint to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be disallowed to prevent PSTN toll bypass.</span></span>
    
      - <span data-ttu-id="5b7f6-156">當從指定的網站 （亦即網站 1） Lync 使用者嘗試將來電轉接與中相同的網站 （網站 1） 的 PBX 端點給 Lync 使用者從不同的網站 (亦即 site 2) 透過諮詢轉接時，通話會允許因為它不會造成潛在的 PSTN 通話費略過在ing。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-156">When a Lync user from a given site (i.e. site 1) attempts to transfer a call with a PBX endpoint in the same site (site 1) to a Lync user from a different site (i.e. site 2) via consultative transfer, the call will be allowed as it doesn’t incur in potential PSTN toll bypassing.</span></span>

</div>

<div>

## <a name="capabilities-not-supported-by-the-location-based-routing-conferencing-application"></a><span data-ttu-id="5b7f6-157">不受支援的位置型路由的會議應用程式的功能</span><span class="sxs-lookup"><span data-stu-id="5b7f6-157">Capabilities Not Supported by the Location-Based Routing Conferencing Application</span></span>

<span data-ttu-id="5b7f6-158">位置型路由會議應用程式不支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="5b7f6-158">The following capabilities are not supported by the Location-Based Routing Conferencing application:</span></span>

  - <span data-ttu-id="5b7f6-159">電話撥入式會議。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-159">Dial-in conferencing.</span></span> <span data-ttu-id="5b7f6-160">無法針對撥入式會議強制位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-160">Location-Based Routing cannot be enforced for Dial-in conferencing.</span></span> <span data-ttu-id="5b7f6-161">即使會議召集人 Lync 使用者啟用位置型的路由，指定會議的任何撥入要求不限制依位置型的路由。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-161">Any dial-in request to a given conference will not be restricted by Location-Based Routing even if the conference organizer is a Lync user enabled for Location-Based Routing.</span></span>

  - <span data-ttu-id="5b7f6-162">建議您不佈建位置型路由限制要強制執行的區域中的會議存取號碼。</span><span class="sxs-lookup"><span data-stu-id="5b7f6-162">It’s recommended not to provision conferencing access numbers in regions where Location-Based Routing restrictions need to be enforced.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

