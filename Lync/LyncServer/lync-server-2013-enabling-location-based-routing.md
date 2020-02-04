---
title: Lync Server 2013：啟用以位置為基礎的路由
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="468ce-102">在 Lync Server 2013 啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="468ce-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="468ce-103">_**主題上次修改日期：** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="468ce-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="468ce-104">部署企業語音並定義網路區域、網站和子網之後，您就可以啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="468ce-105">必須針對下列 Enterprise Voice 元素啟用位置路由：</span><span class="sxs-lookup"><span data-stu-id="468ce-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="468ce-106">網路網站</span><span class="sxs-lookup"><span data-stu-id="468ce-106">Network sites</span></span>

  - <span data-ttu-id="468ce-107">幹線設定</span><span class="sxs-lookup"><span data-stu-id="468ce-107">Trunk configurations</span></span>

  - <span data-ttu-id="468ce-108">語音原則</span><span class="sxs-lookup"><span data-stu-id="468ce-108">Voice policies</span></span>

  - <span data-ttu-id="468ce-109">路由設定</span><span class="sxs-lookup"><span data-stu-id="468ce-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="468ce-110">啟用從位置路由至網路網站</span><span class="sxs-lookup"><span data-stu-id="468ce-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="468ce-111">部署企業語音及設定網路網站之後，您就可以開始設定以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="468ce-112">首先，您要建立語音路由策略，以將網路網站與適當的 PSTN 用途進行關聯。</span><span class="sxs-lookup"><span data-stu-id="468ce-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="468ce-113">將 PSTN 用途指派給語音路由策略時，請務必只使用與您在其位置使用 PSTN 閘道的語音路由所關聯的 PSTN 使用，或者是位於不需要以位置為基礎的路由限制的區域中的 PSTN 閘道。使用 Lync Server Windows PowerShell 命令、新 CsVoiceRoutingPolicy 或 Lync Server [控制台] 來建立語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="468ce-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="468ce-114">如需詳細資訊，請參閱[新 CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy)。</span><span class="sxs-lookup"><span data-stu-id="468ce-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="468ce-115">在這個範例中，下清單格和 Windows PowerShell 命令說明在這個案例中定義的兩個語音路由策略及其關聯 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="468ce-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="468ce-116">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="468ce-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="468ce-117">語音路由原則1</span><span class="sxs-lookup"><span data-stu-id="468ce-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="468ce-118">語音路由策略2</span><span class="sxs-lookup"><span data-stu-id="468ce-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="468ce-119">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="468ce-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="468ce-120">新德里語音路由原則</span><span class="sxs-lookup"><span data-stu-id="468ce-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="468ce-121">Hyderabad 語音路由策略</span><span class="sxs-lookup"><span data-stu-id="468ce-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-122">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="468ce-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="468ce-123">新德里使用量、PBX Del 用法、PBX Hyd 使用量</span><span class="sxs-lookup"><span data-stu-id="468ce-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="468ce-124">Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="468ce-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="468ce-125">接下來，針對適用的網路網站設定以位置為基礎的路由，並將您的語音路由策略與它們建立關聯。</span><span class="sxs-lookup"><span data-stu-id="468ce-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="468ce-126">使用 Lync Server Windows PowerShell 命令（CsNetworkSite）啟用以位置為基礎的路由，並將語音路由策略與您必須強制執行路由限制的網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="468ce-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="468ce-127">在這個範例中，下表說明在這個案例中使用 Lync Server Windows PowerShell 定義的兩個不同網路網站、新德里及 Hyderabad 的位置路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="468ce-128">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="468ce-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="468ce-129">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="468ce-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="468ce-130">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="468ce-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="468ce-131">網站名稱</span><span class="sxs-lookup"><span data-stu-id="468ce-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="468ce-132">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="468ce-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="468ce-133">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="468ce-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="468ce-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="468ce-135">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-135">True</span></span></p></td>
<td><p><span data-ttu-id="468ce-136">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="468ce-137">語音路由策略</span><span class="sxs-lookup"><span data-stu-id="468ce-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="468ce-138">新德里語音路由原則</span><span class="sxs-lookup"><span data-stu-id="468ce-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="468ce-139">Hyderabad 語音路由策略</span><span class="sxs-lookup"><span data-stu-id="468ce-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-140">網</span><span class="sxs-lookup"><span data-stu-id="468ce-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="468ce-141">Subnet 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="468ce-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="468ce-142">Subnet 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="468ce-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="468ce-143">啟用以位置為基礎的路由至 Trunks</span><span class="sxs-lookup"><span data-stu-id="468ce-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="468ce-144">在針對位置路由啟用中繼設定之前，您必須為每個幹線或每個網路網站建立幹線設定。</span><span class="sxs-lookup"><span data-stu-id="468ce-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="468ce-145">使用 Lync Server Windows PowerShell 命令（New-cstrunkconfiguration）建立幹線設定。</span><span class="sxs-lookup"><span data-stu-id="468ce-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="468ce-146">如果有多個 trunks 與指定的系統（亦即閘道或 PBX）相關聯，則必須修改每個中繼設定，才能啟用以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="468ce-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="468ce-147">如需詳細資訊，請參閱[新 new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="468ce-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="468ce-148">在這個範例中，下列 Windows PowerShell 命令說明如何針對此案例中定義的部署中的每個主幹建立一個幹線設定。</span><span class="sxs-lookup"><span data-stu-id="468ce-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="468ce-149">針對每個幹線設定中繼設定之後，您就可以使用 Lync Server Windows PowerShell 命令（New-cstrunkconfiguration），以啟用要強制執行路由限制的 trunks 的位置路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="468ce-150">啟用以位置為基礎的路由，以便將呼叫路由到 pstn 閘道，並將呼叫路由至 PSTN，並建立閘道所在網路網站的關聯。</span><span class="sxs-lookup"><span data-stu-id="468ce-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="468ce-151">如需詳細資訊，請參閱[新 new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="468ce-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="468ce-152">在這個範例中，對於與新德里及 Hyderabad 中 PSTN 閘道相關聯的每個幹線，都會啟用以位置為基礎的路由：</span><span class="sxs-lookup"><span data-stu-id="468ce-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="468ce-153">請勿針對不將呼叫路由至 PSTN 的 trunks 啟用位置式路由;不過，您仍然必須將主幹與系統所處的網路網站進行關聯，以以位置為基礎的路由限制需要針對透過這種幹線連接端點的 PSTN 呼叫強制執行。</span><span class="sxs-lookup"><span data-stu-id="468ce-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="468ce-154">在這個範例中，對於與新德里與 Hyderabad 中的 PBX 系統相關聯的每個幹線，都不會啟用位置路由：</span><span class="sxs-lookup"><span data-stu-id="468ce-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="468ce-155">連接至不將呼叫路由至 PSTN （亦即 PBX）之系統的端點，將會有類似的限制，也就是啟用位置式路由的使用者 Lync 端點。</span><span class="sxs-lookup"><span data-stu-id="468ce-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="468ce-156">這表示無論使用者的位置為何，這些使用者都能在 Lync 使用者上撥打和接聽來電。</span><span class="sxs-lookup"><span data-stu-id="468ce-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="468ce-157">他們也可以在不將呼叫路由至 PSTN 網路的其他系統（亦即連接至不同 PBX 的端點）上，將接收呼叫與其他系統進行撥打，而不論與系統關聯的網路網站為何。</span><span class="sxs-lookup"><span data-stu-id="468ce-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="468ce-158">所有的撥入通話、撥出通話、來電轉接及涉及 PSTN 端點的來電轉接，都會受到位置式路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="468ce-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="468ce-159">此類通話只能使用定義為此類系統的本機的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="468ce-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="468ce-160">下表說明兩個不同網路網站中四個 trunks 的主幹設定：兩個已連接至 PSTN 閘道，以及兩個連線至 PBX 系統的兩個。</span><span class="sxs-lookup"><span data-stu-id="468ce-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="468ce-161">名稱</span><span class="sxs-lookup"><span data-stu-id="468ce-161">Name</span></span></th>
<th><span data-ttu-id="468ce-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="468ce-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="468ce-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="468ce-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="468ce-164">PstnGateway：幹線 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="468ce-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="468ce-165">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-165">True</span></span></p></td>
<td><p><span data-ttu-id="468ce-166">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="468ce-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-167">PstnGateway：主幹 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="468ce-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="468ce-168">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-168">True</span></span></p></td>
<td><p><span data-ttu-id="468ce-169">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="468ce-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="468ce-170">PstnGateway：幹線 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="468ce-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="468ce-171">虛假</span><span class="sxs-lookup"><span data-stu-id="468ce-171">False</span></span></p></td>
<td><p><span data-ttu-id="468ce-172">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="468ce-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-173">PstnGateway：幹線 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="468ce-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="468ce-174">虛假</span><span class="sxs-lookup"><span data-stu-id="468ce-174">False</span></span></p></td>
<td><p><span data-ttu-id="468ce-175">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="468ce-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="468ce-176">啟用以位置為基礎的路由到語音原則</span><span class="sxs-lookup"><span data-stu-id="468ce-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="468ce-177">若要強制將位置路由傳送給特定的使用者，請將這些使用者的語音原則設定為避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="468ce-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="468ce-178">使用 Lync Server Windows PowerShell 命令（CsVoicePolicy）建立新的語音原則，或設定 CsVoicePolicy （如果使用現有的原則），以透過避免 PSTN 免付費旁路來啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="468ce-179">如需詳細資訊，請參閱[新 CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy)。</span><span class="sxs-lookup"><span data-stu-id="468ce-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="468ce-180">在這個範例中，下清單格和 Windows PowerShell 命令說明如何防止在此案例中定義的 Hyderabad 語音原則中避開 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="468ce-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="468ce-181">只有針對位置式路由的特定設定才會包含在表格中，以供圖例之用。</span><span class="sxs-lookup"><span data-stu-id="468ce-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="468ce-182">語音原則1</span><span class="sxs-lookup"><span data-stu-id="468ce-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="468ce-183">語音原則2</span><span class="sxs-lookup"><span data-stu-id="468ce-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="468ce-184">語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="468ce-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="468ce-185">新德里語音原則</span><span class="sxs-lookup"><span data-stu-id="468ce-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="468ce-186">Hyderabad 語音原則</span><span class="sxs-lookup"><span data-stu-id="468ce-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="468ce-187">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="468ce-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="468ce-188">新德里使用量、PBX Del 用法、PBX Hyd 使用量</span><span class="sxs-lookup"><span data-stu-id="468ce-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="468ce-189">Hyderabad 使用方式、PBX Hyd 使用量、PBX Del 用法</span><span class="sxs-lookup"><span data-stu-id="468ce-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="468ce-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="468ce-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="468ce-191">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-191">True</span></span></p></td>
<td><p><span data-ttu-id="468ce-192">滿足</span><span class="sxs-lookup"><span data-stu-id="468ce-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="468ce-193">在路由設定中啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="468ce-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="468ce-194">最後，全域啟用路由設定的位置路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="468ce-195">使用 Lync Server Windows PowerShell 命令（CsRoutingConfiguration）來啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="468ce-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="468ce-196">如需詳細資訊，請參閱[設定 CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="468ce-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="468ce-197">雖然必須透過全域設定啟用位置路由，否則將只會針對此檔中已設定其配置的網站、使用者和 trunks，強制執行要套用的一組規則。</span><span class="sxs-lookup"><span data-stu-id="468ce-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="468ce-198">請參閱</span><span class="sxs-lookup"><span data-stu-id="468ce-198">See Also</span></span>


[<span data-ttu-id="468ce-199">在 Lync Server 2013 中設定位置基礎路由</span><span class="sxs-lookup"><span data-stu-id="468ce-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

