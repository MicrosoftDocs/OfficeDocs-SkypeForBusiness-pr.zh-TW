---
title: 針對直接路由啟用以位置為基礎的路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何針對直接路由啟用以位置為基礎的路由。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 160a4646ba212c9e654ec06fca2fdd107b2671c7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245125"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="d9cec-103">針對直接路由啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="d9cec-104">在您按照本文中的步驟進行之前, 請確定您已閱讀「[規劃位置」路由以進行直接路由](location-based-routing-plan.md), 並已完成[設定位置路由的網路設定](location-based-routing-configure-network-settings.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="d9cec-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="d9cec-105">本文說明如何啟用直接路由的以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="d9cec-106">在您部署手機系統直接路由並設定網路區域、網站和子網之後, 您就可以開始啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="d9cec-107">若要完成本文中的步驟, 您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9cec-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="d9cec-108">若要深入瞭解, 請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d9cec-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="d9cec-109">您必須啟用下列各項的位置路由:</span><span class="sxs-lookup"><span data-stu-id="d9cec-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="d9cec-110">使用者</span><span class="sxs-lookup"><span data-stu-id="d9cec-110">Users</span></span>
- <span data-ttu-id="d9cec-111">網路網站</span><span class="sxs-lookup"><span data-stu-id="d9cec-111">Network sites</span></span>
- <span data-ttu-id="d9cec-112">閘道設定</span><span class="sxs-lookup"><span data-stu-id="d9cec-112">Gateway configurations</span></span>
- <span data-ttu-id="d9cec-113">通話原則</span><span class="sxs-lookup"><span data-stu-id="d9cec-113">Calling policies</span></span>

## <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="d9cec-114">針對使用者啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-114">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="d9cec-115">使用[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="d9cec-115">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="d9cec-116">針對多種用途, 請使用逗號來分隔每個用法。</span><span class="sxs-lookup"><span data-stu-id="d9cec-116">For multiple usages, separate each usage with a comma.</span></span>

    ```
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="d9cec-117">例如：</span><span class="sxs-lookup"><span data-stu-id="d9cec-117">For example:</span></span>
    ```
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="d9cec-118">使用[新的 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 來建立語音路由策略, 以將使用者與適當的 PSTN 用法進行關聯。</span><span class="sxs-lookup"><span data-stu-id="d9cec-118">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="d9cec-119">當您將 PSTN 用途指派給語音路由策略時, 請務必執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="d9cec-119">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="d9cec-120">使用與在網站使用 PSTN 閘道的語音路由相關聯的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="d9cec-120">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="d9cec-121">使用不需要以位置為基礎路由限制之區域中的 PSTN 閘道的語音路由所關聯的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="d9cec-121">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="d9cec-122">在這個範例中, 我們會建立兩個新的語音路由策略, 並將 PSTN 使用方式指派給它們。</span><span class="sxs-lookup"><span data-stu-id="d9cec-122">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="d9cec-123">下表顯示在這個範例中定義的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="d9cec-123">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="d9cec-124">語音路由原則1</span><span class="sxs-lookup"><span data-stu-id="d9cec-124">Voice routing policy 1</span></span>|<span data-ttu-id="d9cec-125">語音路由策略2</span><span class="sxs-lookup"><span data-stu-id="d9cec-125">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="d9cec-126">線上語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="d9cec-126">Online voice policy ID</span></span>   |<span data-ttu-id="d9cec-127">新德里線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="d9cec-127">Delhi online voice routing policy</span></span>   |<span data-ttu-id="d9cec-128">Hyderabad 線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="d9cec-128">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="d9cec-129">線上 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="d9cec-129">Online PSTN usages</span></span>  |<span data-ttu-id="d9cec-130">長途</span><span class="sxs-lookup"><span data-stu-id="d9cec-130">Long Distance</span></span>  |<span data-ttu-id="d9cec-131">遠距離、本機、內部</span><span class="sxs-lookup"><span data-stu-id="d9cec-131">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="d9cec-132">使用[授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet, 將線上語音路由策略與需要強制執行路由限制的使用者建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d9cec-132">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="d9cec-133">啟用網路網站的位置路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-133">Enable Location-Based Routing for network sites</span></span>
1.  <span data-ttu-id="d9cec-134">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 來啟用以位置為基礎的路由, 並將語音路由策略與您的網路網站進行關聯, 而您必須強制執行路由限制。</span><span class="sxs-lookup"><span data-stu-id="d9cec-134">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="d9cec-135">在這個範例中, 我們會針對新德里網站和 Hyderabad 網站啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-135">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="d9cec-136">下表顯示在這個範例中, 針對位置路由啟用的網站。</span><span class="sxs-lookup"><span data-stu-id="d9cec-136">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="d9cec-137">Site 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="d9cec-137">Site 1 (Delhi)</span></span>  |<span data-ttu-id="d9cec-138">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d9cec-138">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="d9cec-139">網站名稱</span><span class="sxs-lookup"><span data-stu-id="d9cec-139">Site name</span></span>    |<span data-ttu-id="d9cec-140">Site 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="d9cec-140">Site 1 (Delhi)</span></span>    |<span data-ttu-id="d9cec-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d9cec-141">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="d9cec-142">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="d9cec-142">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="d9cec-143">滿足</span><span class="sxs-lookup"><span data-stu-id="d9cec-143">True</span></span>    |<span data-ttu-id="d9cec-144">滿足</span><span class="sxs-lookup"><span data-stu-id="d9cec-144">True</span></span>    |
    |<span data-ttu-id="d9cec-145">網</span><span class="sxs-lookup"><span data-stu-id="d9cec-145">Subnets</span></span>     |<span data-ttu-id="d9cec-146">Subnet 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="d9cec-146">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="d9cec-147">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d9cec-147">Subnet 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="d9cec-148">啟用閘道的位置路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-148">Enable Location-Based Routing for gateways</span></span>
1. <span data-ttu-id="d9cec-149">使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 來為每個閘道或網路網站建立閘道配置。</span><span class="sxs-lookup"><span data-stu-id="d9cec-149">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignallingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="d9cec-150">如果有多個閘道與系統相關聯 (例如, 閘道或 PBX), 請修改每個閘道以啟用以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="d9cec-150">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="d9cec-151">在這個範例中, 我們會為每個閘道建立一個閘道配置。</span><span class="sxs-lookup"><span data-stu-id="d9cec-151">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignallingPort 5067 
    ```
    <span data-ttu-id="d9cec-152">如需詳細資訊, 請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="d9cec-152">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="d9cec-153">使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 來針對需要強制執行路由限制的閘道, 啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-153">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="d9cec-154">啟用將呼叫路由至 pstn 閘道, 並將呼叫路由到 PSTN 的閘道, 並將閘道所在的網路網站與網路網站建立關聯, 以進行位置路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-154">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="d9cec-155">在這個範例中, 我們為在新德里與 Hyderabad 網站中與 PSTN 閘道相關聯的每個閘道啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-155">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    <span data-ttu-id="d9cec-156">不要針對未將呼叫路由至 PSTN 的閘道啟用位置式路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-156">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="d9cec-157">不過, 您仍然必須將閘道與系統所在的網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d9cec-157">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="d9cec-158">這是因為以位置為基礎的路由限制需要針對透過此閘道所連線的端點而進行 PSTN 呼叫強制執行。</span><span class="sxs-lookup"><span data-stu-id="d9cec-158">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="d9cec-159">在這個範例中, 對於與新德里與 Hyderabad 網站中的 PBX 系統相關聯的每個閘道, 都不會啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-159">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="d9cec-160">連接至不路由呼叫至 PSTN (例如 PBX) 的系統的端點, 將會有類似的限制, 因為已啟用位置路由的團隊使用者的端點。</span><span class="sxs-lookup"><span data-stu-id="d9cec-160">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="d9cec-161">這表示無論使用者的位置為何, 這些使用者都可以對團隊使用者進行呼叫和接聽。</span><span class="sxs-lookup"><span data-stu-id="d9cec-161">This means that these users can place and receive calls to and from Teams users regardless of the user’s location.</span></span> <span data-ttu-id="d9cec-162">他們也可以在不將呼叫路由至 PSTN 網路的其他系統 (例如, 連線到不同 PBX 的端點) 撥打電話和接聽電話, 而不論系統與哪個網路網站的關聯。</span><span class="sxs-lookup"><span data-stu-id="d9cec-162">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="d9cec-163">所有的撥入通話、撥出通話、來電轉接及涉及 PSTN 端點的來電轉接, 都會受到位置式路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="d9cec-163">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="d9cec-164">這些通話只能使用定義為此類系統的本機的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="d9cec-164">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="d9cec-165">下表顯示兩個不同網路網站中四個閘道的閘道設定: 兩個連接至 PSTN 閘道的兩個閘道, 以及兩個連線至 PBX 系統</span><span class="sxs-lookup"><span data-stu-id="d9cec-165">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="d9cec-166">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="d9cec-166">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="d9cec-167">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="d9cec-167">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="d9cec-168">PstnGateway: 閘道 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d9cec-168">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="d9cec-169">滿足</span><span class="sxs-lookup"><span data-stu-id="d9cec-169">True</span></span>     |   <span data-ttu-id="d9cec-170">Site 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="d9cec-170">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="d9cec-171">PstnGateway: Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d9cec-171">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="d9cec-172">滿足</span><span class="sxs-lookup"><span data-stu-id="d9cec-172">True</span></span>      |      <span data-ttu-id="d9cec-173">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d9cec-173">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="d9cec-174">PstnGateway: 閘道 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d9cec-174">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="d9cec-175">虛假</span><span class="sxs-lookup"><span data-stu-id="d9cec-175">False</span></span>     |     <span data-ttu-id="d9cec-176">Site 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="d9cec-176">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="d9cec-177">PstnGateway: 閘道 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="d9cec-177">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="d9cec-178">虛假</span><span class="sxs-lookup"><span data-stu-id="d9cec-178">False</span></span>     |    <span data-ttu-id="d9cec-179">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="d9cec-179">Site 2 (Hyderabad)</span></span>     |

## <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="d9cec-180">啟用呼叫原則的位置路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-180">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="d9cec-181">若要針對特定的使用者強制執行以位置為基礎的路由, 請設定使用者的語音原則來避免 PTSN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="d9cec-181">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="d9cec-182">使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet, 透過避免 PSTN 免付費旁路來啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="d9cec-182">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="d9cec-183">在這個範例中, 我們將避免 PSTN 免付費旁路 User1's 通話原則。</span><span class="sxs-lookup"><span data-stu-id="d9cec-183">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

### <a name="related-topics"></a><span data-ttu-id="d9cec-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9cec-184">Related topics</span></span>
- [<span data-ttu-id="d9cec-185">規劃直接路由的以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="d9cec-185">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="d9cec-186">設定以位置為基礎的路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="d9cec-186">Configure network settings for Location-Based Routing</span></span>](location-based-routing-configure-network-settings.md)
- [<span data-ttu-id="d9cec-187">以位置為基礎的路由術語</span><span class="sxs-lookup"><span data-stu-id="d9cec-187">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
