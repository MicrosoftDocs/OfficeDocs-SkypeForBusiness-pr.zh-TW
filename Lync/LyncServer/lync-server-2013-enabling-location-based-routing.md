---
title: Lync Server 2013：啟用位置基礎路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a66ced9530510ade4d91e8d76032a4260870530
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="aff8d-102">在 Lync Server 2013 中啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aff8d-103">_**主題上次修改日期：** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="aff8d-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="aff8d-104">部署 Enterprise Voice 並定義網路地區、網站和子網之後，您可以啟用位置型路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="aff8d-105">必須啟用下列 Enterprise Voice 元素的位置基礎路由：</span><span class="sxs-lookup"><span data-stu-id="aff8d-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="aff8d-106">網路網站</span><span class="sxs-lookup"><span data-stu-id="aff8d-106">Network sites</span></span>

  - <span data-ttu-id="aff8d-107">主幹設定</span><span class="sxs-lookup"><span data-stu-id="aff8d-107">Trunk configurations</span></span>

  - <span data-ttu-id="aff8d-108">語音原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-108">Voice policies</span></span>

  - <span data-ttu-id="aff8d-109">路由設定</span><span class="sxs-lookup"><span data-stu-id="aff8d-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="aff8d-110">啟用網站的位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="aff8d-111">部署企業語音及設定網路網站之後，即可設定位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="aff8d-112">首先，您會建立一個語音路由原則，以將網路網站與適當的 PSTN 使用方式產生關聯。</span><span class="sxs-lookup"><span data-stu-id="aff8d-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="aff8d-113">將 PSTN 使用方式指派至語音路由原則時，請務必只使用與使用 PSTN 閘道（在不需要以位置為基礎的路由限制所在之地區）之語音路由相關聯的 PSTN 使用方式。使用 [Lync Server Windows PowerShell] 命令、New-CsVoiceRoutingPolicy 或 Lync Server 控制台建立語音路由原則。</span><span class="sxs-lookup"><span data-stu-id="aff8d-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="aff8d-114">如需詳細資訊，請參閱[New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="aff8d-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="aff8d-115">在此範例中，下清單格和 Windows PowerShell 命令會說明兩個語音路由策略及其在此案例中定義的關聯 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="aff8d-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="aff8d-116">表格中只會包含針對位置基礎路由特有的設定，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="aff8d-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="aff8d-117">語音路由原則1</span><span class="sxs-lookup"><span data-stu-id="aff8d-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="aff8d-118">語音路由原則2</span><span class="sxs-lookup"><span data-stu-id="aff8d-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-119">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="aff8d-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="aff8d-120">新德里語音路由原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="aff8d-121">Hyderabad 語音路由原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-122">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="aff8d-123">新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="aff8d-124">Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="aff8d-125">接下來，針對適用的網站設定位置基礎路由，並將您的語音路由原則與它們關聯。</span><span class="sxs-lookup"><span data-stu-id="aff8d-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="aff8d-126">使用 [Lync Server Windows PowerShell] 命令 New-CsNetworkSite，啟用位置基礎路由，並將語音路由原則與必須強制執行路由限制的網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="aff8d-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="aff8d-127">在此範例中，下表說明使用 Lync Server Windows PowerShell 于此案例中定義的兩個不同網路網站（新德里和 Hyderabad）的位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="aff8d-128">表格中只會包含針對位置基礎路由特有的設定，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="aff8d-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="aff8d-129">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="aff8d-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="aff8d-130">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="aff8d-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-131">網站名稱 </span><span class="sxs-lookup"><span data-stu-id="aff8d-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="aff8d-132">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="aff8d-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="aff8d-133">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="aff8d-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="aff8d-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="aff8d-135">True</span><span class="sxs-lookup"><span data-stu-id="aff8d-135">True</span></span></p></td>
<td><p><span data-ttu-id="aff8d-136">True</span><span class="sxs-lookup"><span data-stu-id="aff8d-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-137">語音路由原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="aff8d-138">新德里語音路由原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="aff8d-139">Hyderabad 語音路由原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-140">子網路</span><span class="sxs-lookup"><span data-stu-id="aff8d-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="aff8d-141">Subnet 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="aff8d-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="aff8d-142">Subnet 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="aff8d-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="aff8d-143">啟用主幹的位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="aff8d-144">您必須為每個主幹或每個網站建立主幹設定，才能啟用主幹設定以進行位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="aff8d-145">使用 Lync Server Windows PowerShell 命令 Get-cstrunkconfiguration 來建立主幹設定。</span><span class="sxs-lookup"><span data-stu-id="aff8d-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="aff8d-146">如果有多個主幹與指定的系統相關聯 (例如閘道或 PBX) ，必須修改每一個主幹設定以啟用位置型路由限制。</span><span class="sxs-lookup"><span data-stu-id="aff8d-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="aff8d-147">如需詳細資訊，請參閱[get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="aff8d-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="aff8d-148">在此範例中，下列 Windows PowerShell 命令會說明如何為此案例中定義的部署中的每個主幹建立一個主幹設定。</span><span class="sxs-lookup"><span data-stu-id="aff8d-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="aff8d-149">在每個主幹設定主幹設定之後，您可以使用 [Lync Server Windows PowerShell] 命令 Set-CsTrunkConfiguration，以啟用必須強制執行路由限制之主幹的位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="aff8d-150">啟用將來電路由傳送至 pstn 閘道的主幹，以將來電路由傳送至 pstn 閘道，並關聯閘道所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="aff8d-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="aff8d-151">如需詳細資訊，請參閱[get-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="aff8d-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="aff8d-152">在此範例中，會為每個與 Hyderabad 中的 PSTN 閘道相關聯的主幹啟用位置基礎路由：</span><span class="sxs-lookup"><span data-stu-id="aff8d-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="aff8d-153">不啟用不將通話路由傳送至 PSTN 之主幹的位置基礎路由;不過，您仍然必須將主幹與系統所在的網路網站產生關聯，因為此網站的位置是以位置為基礎的路由限制，必須針對透過此主幹連線的端點，強制執行 PSTN 通話的強制執行。</span><span class="sxs-lookup"><span data-stu-id="aff8d-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="aff8d-154">在此範例中，不會針對每個與 Hyderabad 中 PBX 系統相關聯的主幹，啟用位置基礎路由：</span><span class="sxs-lookup"><span data-stu-id="aff8d-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="aff8d-155">連接至不將通話路由傳送至 PSTN 的系統端點 (亦即，PBX) 會有類似的限制，例如啟用位置型路由之使用者的 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="aff8d-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="aff8d-156">這表示，不論使用者的位置為何，這些使用者都可以在 Lync 使用者上撥打和接聽電話。</span><span class="sxs-lookup"><span data-stu-id="aff8d-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="aff8d-157">他們也可以在未將通話路由傳送至 PSTN 網路的其他系統上撥打和撥出來電 (亦即，不論系統關聯的網站為何，連接至不同 PBX 的端點) 都會有所不同。</span><span class="sxs-lookup"><span data-stu-id="aff8d-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="aff8d-158">所有撥出電話、撥出電話、涉及 PSTN 端點的來電轉接及來電轉接都會受到位置基礎的路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="aff8d-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="aff8d-159">這類呼叫只能使用定義為此類系統之本機的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="aff8d-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="aff8d-160">下表說明兩個不同網路網站中四個主幹的主幹設定：兩個連接至 PSTN 閘道的兩個，以及兩個連接至 PBX 系統的主幹設定。</span><span class="sxs-lookup"><span data-stu-id="aff8d-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aff8d-161">姓名</span><span class="sxs-lookup"><span data-stu-id="aff8d-161">Name</span></span></th>
<th><span data-ttu-id="aff8d-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="aff8d-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="aff8d-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="aff8d-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-164">PstnGateway：主幹 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="aff8d-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="aff8d-165">對</span><span class="sxs-lookup"><span data-stu-id="aff8d-165">True</span></span></p></td>
<td><p><span data-ttu-id="aff8d-166">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="aff8d-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-167">PstnGateway：主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="aff8d-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="aff8d-168">對</span><span class="sxs-lookup"><span data-stu-id="aff8d-168">True</span></span></p></td>
<td><p><span data-ttu-id="aff8d-169">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="aff8d-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-170">PstnGateway：主幹 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="aff8d-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="aff8d-171">錯</span><span class="sxs-lookup"><span data-stu-id="aff8d-171">False</span></span></p></td>
<td><p><span data-ttu-id="aff8d-172">Site 1 (新德里) </span><span class="sxs-lookup"><span data-stu-id="aff8d-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-173">PstnGateway：主幹 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="aff8d-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="aff8d-174">錯</span><span class="sxs-lookup"><span data-stu-id="aff8d-174">False</span></span></p></td>
<td><p><span data-ttu-id="aff8d-175">Site 2 (Hyderabad) </span><span class="sxs-lookup"><span data-stu-id="aff8d-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="aff8d-176">啟用至語音原則的位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="aff8d-177">若要對特定使用者強制進行位置基礎路由，請設定使用者的語音原則，以防止 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="aff8d-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="aff8d-178">使用 [Lync Server Windows PowerShell] 命令 New-CsVoicePolicy，以建立新的語音原則或 Set-CsVoicePolicy （如果使用現有的原則），以透過防止 PSTN 免語音旁路來啟用位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="aff8d-179">如需詳細資訊，請參閱[New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。</span><span class="sxs-lookup"><span data-stu-id="aff8d-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="aff8d-180">在此範例中，下清單格和 Windows PowerShell 命令可讓您在此案例中所定義的新德里和 Hyderabad 語音原則中預防 PSTN 長途電話旁路。</span><span class="sxs-lookup"><span data-stu-id="aff8d-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="aff8d-181">表格中只會包含針對位置基礎路由特有的設定，以供說明之用。</span><span class="sxs-lookup"><span data-stu-id="aff8d-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="aff8d-182">語音原則1</span><span class="sxs-lookup"><span data-stu-id="aff8d-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="aff8d-183">語音原則2</span><span class="sxs-lookup"><span data-stu-id="aff8d-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-184">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="aff8d-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="aff8d-185">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="aff8d-186">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="aff8d-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aff8d-187">PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="aff8d-188">新德里使用狀況，pbx Del 用法，PBX Hyd 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="aff8d-189">Hyderabad 使用狀況，PBX Hyd 使用狀況，PBX Del 使用方式</span><span class="sxs-lookup"><span data-stu-id="aff8d-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aff8d-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="aff8d-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="aff8d-191">True</span><span class="sxs-lookup"><span data-stu-id="aff8d-191">True</span></span></p></td>
<td><p><span data-ttu-id="aff8d-192">True</span><span class="sxs-lookup"><span data-stu-id="aff8d-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="aff8d-193">啟用路由設定中的位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="aff8d-194">最後，全域啟用路由設定的位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="aff8d-195">使用 Lync Server Windows PowerShell 命令 CsRoutingConfiguration，以啟用位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="aff8d-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="aff8d-196">如需詳細資訊，請參閱[CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="aff8d-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aff8d-197">在位置基礎路由必須透過全域設定來啟用時，只會針對此檔中所指定的網站、使用者和主幹，強制執行所套用的規則集。</span><span class="sxs-lookup"><span data-stu-id="aff8d-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aff8d-198">另請參閱</span><span class="sxs-lookup"><span data-stu-id="aff8d-198">See Also</span></span>


[<span data-ttu-id="aff8d-199">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="aff8d-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

