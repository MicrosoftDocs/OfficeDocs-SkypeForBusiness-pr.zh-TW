---
title: 啟用直接路由的依位置路由
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何針對直接路由啟用以位置為基礎的路由，包括為使用者、網路網站、閘道設定及呼叫原則啟用它。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69f2ee37e63f83d6fc1d19ea733ff44ad23e7011
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/07/2020
ms.locfileid: "44158990"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="41339-103">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-103">Enable Location-Based Routing for Direct Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="41339-104">在您按照本文中的步驟進行之前，請確定您已閱讀「[規劃位置」路由以進行直接路由](location-based-routing-plan.md)，並已完成[設定位置路由的網路設定](location-based-routing-configure-network-settings.md)中的步驟。</span><span class="sxs-lookup"><span data-stu-id="41339-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="41339-105">本文說明如何啟用直接路由的以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="41339-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="41339-106">在您部署手機系統直接路由並設定網路區域、網站和子網之後，您就可以開始啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="41339-107">若要完成本文中的步驟，您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="41339-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="41339-108">若要深入瞭解，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="41339-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="41339-109">您必須啟用下列各項的位置路由：</span><span class="sxs-lookup"><span data-stu-id="41339-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="41339-110">使用者</span><span class="sxs-lookup"><span data-stu-id="41339-110">Users</span></span>
- <span data-ttu-id="41339-111">網路網站</span><span class="sxs-lookup"><span data-stu-id="41339-111">Network sites</span></span>
- <span data-ttu-id="41339-112">閘道設定</span><span class="sxs-lookup"><span data-stu-id="41339-112">Gateway configurations</span></span>
- <span data-ttu-id="41339-113">通話原則</span><span class="sxs-lookup"><span data-stu-id="41339-113">Calling policies</span></span>

<span data-ttu-id="41339-114">您可以使用[Microsoft Team 管理中心](#using-the-microsoft-teams-admin-center)或[PowerShel](#using-powershell)l 來啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="41339-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="41339-115">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="41339-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="41339-116">針對使用者啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="41339-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="41339-117">建立語音路由策略，並將 PSTN 用途指派給原則。</span><span class="sxs-lookup"><span data-stu-id="41339-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="41339-118">當您將 PSTN 用途指派給原則時，請確定執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="41339-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="41339-119">使用與在網站使用 PSTN 閘道的語音路由相關的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="41339-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="41339-120">使用不需要以位置為基礎路由限制之區域中的 PSTN 閘道的語音路由所關聯的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="41339-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="41339-121">將語音路由原則指派給需要強制執行路由限制的使用者。</span><span class="sxs-lookup"><span data-stu-id="41339-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="41339-122">若要深入瞭解如何建立語音路由策略並指派給使用者，請參閱[在 Microsoft 團隊中管理語音路由原則](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="41339-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="41339-123">啟用網路網站的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="41339-124">針對必須強制執行路由限制的網站，啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="41339-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="41339-125">若要這樣做，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置** > **網路拓撲**]，選取網路網站，按一下 [**編輯**]，然後開啟 [以**位置為基礎的路由**]。</span><span class="sxs-lookup"><span data-stu-id="41339-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="41339-126">若要深入瞭解，請參閱[管理您的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="41339-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="41339-127">啟用閘道的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="41339-128">啟用將呼叫路由至 pstn 閘道，並將呼叫路由到 PSTN 的閘道，並將閘道所在的網路網站與網路網站建立關聯，以進行位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="41339-129">在左側導覽中，移至 [**語音** > **直式路由**]，然後按一下 [ **SBCs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="41339-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="41339-130">選取 SBC，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="41339-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="41339-131">在 [位置] 下的 [**路由及媒體優化**] 底下，開啟 [**啟用根據位置的路由**]。</span><span class="sxs-lookup"><span data-stu-id="41339-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="41339-132">指定閘道網站識別碼，然後設定 [略過模式]。</span><span class="sxs-lookup"><span data-stu-id="41339-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="41339-133">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="41339-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="41339-134">啟用呼叫原則的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="41339-135">若要針對特定的使用者強制執行以位置為基礎的路由，請設定使用者的通話原則，以避免 PSTN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="41339-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="41339-136">若要這樣做，請在通話原則中開啟 [**防止收費略過**] 設定。</span><span class="sxs-lookup"><span data-stu-id="41339-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="41339-137">若要深入瞭解，請參閱[在團隊中呼叫原則](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="41339-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="41339-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="41339-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="41339-139">針對使用者啟用以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="41339-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="41339-140">使用[CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="41339-140">Use the [Set-CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="41339-141">針對多種用途，請使用逗號來分隔每個用法。</span><span class="sxs-lookup"><span data-stu-id="41339-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="41339-142">例如：</span><span class="sxs-lookup"><span data-stu-id="41339-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="41339-143">使用[新的 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 來建立語音路由策略，以將使用者與適當的 PSTN 用法進行關聯。</span><span class="sxs-lookup"><span data-stu-id="41339-143">Use the [New-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="41339-144">當您將 PSTN 用途指派給語音路由策略時，請務必執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="41339-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="41339-145">使用與在網站使用 PSTN 閘道的語音路由相關聯的 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="41339-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="41339-146">使用不需要以位置為基礎路由限制之區域中的 PSTN 閘道的語音路由所關聯的 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="41339-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="41339-147">在這個範例中，我們會建立兩個新的語音路由策略，並將 PSTN 使用方式指派給它們。</span><span class="sxs-lookup"><span data-stu-id="41339-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="41339-148">下表顯示在這個範例中定義的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="41339-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="41339-149">語音路由原則1</span><span class="sxs-lookup"><span data-stu-id="41339-149">Voice routing policy 1</span></span>|<span data-ttu-id="41339-150">語音路由策略2</span><span class="sxs-lookup"><span data-stu-id="41339-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="41339-151">線上語音原則識別碼</span><span class="sxs-lookup"><span data-stu-id="41339-151">Online voice policy ID</span></span>   |<span data-ttu-id="41339-152">新德里線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="41339-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="41339-153">Hyderabad 線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="41339-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="41339-154">線上 PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="41339-154">Online PSTN usages</span></span>  |<span data-ttu-id="41339-155">長途</span><span class="sxs-lookup"><span data-stu-id="41339-155">Long Distance</span></span>  |<span data-ttu-id="41339-156">遠距離、本機、內部</span><span class="sxs-lookup"><span data-stu-id="41339-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="41339-157">使用[授與 CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet，將線上語音路由策略與需要強制執行路由限制的使用者建立關聯。</span><span class="sxs-lookup"><span data-stu-id="41339-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="41339-158">啟用網路網站的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="41339-159">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 來啟用以位置為基礎的路由，並將語音路由策略與您的網路網站進行關聯，而您必須強制執行路由限制。</span><span class="sxs-lookup"><span data-stu-id="41339-159">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="41339-160">在這個範例中，我們會針對新德里網站和 Hyderabad 網站啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="41339-161">下表顯示在這個範例中，針對位置路由啟用的網站。</span><span class="sxs-lookup"><span data-stu-id="41339-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="41339-162">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="41339-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="41339-163">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="41339-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="41339-164">網站名稱</span><span class="sxs-lookup"><span data-stu-id="41339-164">Site name</span></span>    |<span data-ttu-id="41339-165">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="41339-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="41339-166">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="41339-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="41339-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="41339-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="41339-168">滿足</span><span class="sxs-lookup"><span data-stu-id="41339-168">True</span></span>    |<span data-ttu-id="41339-169">滿足</span><span class="sxs-lookup"><span data-stu-id="41339-169">True</span></span>    |
    |<span data-ttu-id="41339-170">網</span><span class="sxs-lookup"><span data-stu-id="41339-170">Subnets</span></span>     |<span data-ttu-id="41339-171">Subnet 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="41339-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="41339-172">Subnet 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="41339-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="41339-173">啟用閘道的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="41339-174">使用[CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 來為每個閘道或網路網站建立閘道配置。</span><span class="sxs-lookup"><span data-stu-id="41339-174">Use the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="41339-175">如果有多個閘道與系統相關聯（例如，閘道或 PBX），請修改每個閘道以啟用以位置為基礎的路由限制。</span><span class="sxs-lookup"><span data-stu-id="41339-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="41339-176">在這個範例中，我們會為每個閘道建立一個閘道配置。</span><span class="sxs-lookup"><span data-stu-id="41339-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="41339-177">如需詳細資訊，請參閱[設定直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="41339-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="41339-178">使用[CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 來針對需要強制執行路由限制的閘道，啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="41339-178">Use the [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="41339-179">啟用將呼叫路由至 pstn 閘道，並將呼叫路由到 PSTN 的閘道，並將閘道所在的網路網站與網路網站建立關聯，以進行位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="41339-180">在這個範例中，我們為在新德里與 Hyderabad 網站中與 PSTN 閘道相關聯的每個閘道啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="41339-181">不要針對未將呼叫路由至 PSTN 的閘道啟用位置式路由。</span><span class="sxs-lookup"><span data-stu-id="41339-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="41339-182">不過，您仍然必須將閘道與系統所在的網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="41339-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="41339-183">這是因為以位置為基礎的路由限制需要針對透過此閘道所連線的端點而進行 PSTN 呼叫強制執行。</span><span class="sxs-lookup"><span data-stu-id="41339-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="41339-184">在這個範例中，對於與新德里與 Hyderabad 網站中的 PBX 系統相關聯的每個閘道，都不會啟用位置路由。</span><span class="sxs-lookup"><span data-stu-id="41339-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    <span data-ttu-id="41339-185">連接至不路由呼叫至 PSTN （例如 PBX）的系統的端點，將會有類似的限制，因為已啟用位置路由的團隊使用者的端點。</span><span class="sxs-lookup"><span data-stu-id="41339-185">Endpoints connected to systems that don't route calls to the PSTN (for example, a PBX) will have similar restrictions as endpoints of Teams users enabled for Location-Based Routing.</span></span> <span data-ttu-id="41339-186">這表示無論使用者的位置為何，這些使用者都可以對團隊使用者進行呼叫和接聽。</span><span class="sxs-lookup"><span data-stu-id="41339-186">This means that these users can place and receive calls to and from Teams users regardless of the user's location.</span></span> <span data-ttu-id="41339-187">他們也可以在不將呼叫路由至 PSTN 網路的其他系統（例如，連線到不同 PBX 的端點）撥打電話和接聽電話，而不論系統與哪個網路網站的關聯。</span><span class="sxs-lookup"><span data-stu-id="41339-187">They can also place and receive calls to and from other systems that don't route calls to the PSTN network (for example, an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="41339-188">所有的撥入通話、撥出通話、來電轉接及涉及 PSTN 端點的來電轉接，都會受到位置式路由 enforcements。</span><span class="sxs-lookup"><span data-stu-id="41339-188">All inbound calls, outbound calls, call transfers and call forwarding that involve PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="41339-189">這些通話只能使用定義為此類系統的本機的 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="41339-189">These calls must use only PSTN gateways that are defined as local to such systems.</span></span> 

    <span data-ttu-id="41339-190">下表顯示兩個不同網路網站中四個閘道的閘道設定：兩個連接至 PSTN 閘道的兩個閘道，以及兩個連線至 PBX 系統</span><span class="sxs-lookup"><span data-stu-id="41339-190">The following table shows the gateway configuration of four gateways in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span> 

    ||<span data-ttu-id="41339-191">GatewaySiteLbrEnabled</span><span class="sxs-lookup"><span data-stu-id="41339-191">GatewaySiteLbrEnabled</span></span>   |<span data-ttu-id="41339-192">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="41339-192">NetworkSiteID</span></span>  |
    |---------|---------|---------|
    |<span data-ttu-id="41339-193">PstnGateway：閘道 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="41339-193">PstnGateway:Gateway 1 DEL-GW</span></span>    |    <span data-ttu-id="41339-194">滿足</span><span class="sxs-lookup"><span data-stu-id="41339-194">True</span></span>     |   <span data-ttu-id="41339-195">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="41339-195">Site 1 (Delhi)</span></span>      |
    |<span data-ttu-id="41339-196">PstnGateway： Gateway 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="41339-196">PstnGateway:Gateway 2 HYD-GW</span></span>     |   <span data-ttu-id="41339-197">滿足</span><span class="sxs-lookup"><span data-stu-id="41339-197">True</span></span>      |      <span data-ttu-id="41339-198">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="41339-198">Site 2 (Hyderabad)</span></span>   |
    |<span data-ttu-id="41339-199">PstnGateway：閘道 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="41339-199">PstnGateway:Gateway 3 DEL-PBX</span></span>    |    <span data-ttu-id="41339-200">虛假</span><span class="sxs-lookup"><span data-stu-id="41339-200">False</span></span>     |     <span data-ttu-id="41339-201">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="41339-201">Site 1 (Delhi)</span></span>    |
    |<span data-ttu-id="41339-202">PstnGateway：閘道 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="41339-202">PstnGateway:Gateway 4 HYD-PBX</span></span>    |    <span data-ttu-id="41339-203">虛假</span><span class="sxs-lookup"><span data-stu-id="41339-203">False</span></span>     |    <span data-ttu-id="41339-204">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="41339-204">Site 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="41339-205">啟用呼叫原則的位置路由</span><span class="sxs-lookup"><span data-stu-id="41339-205">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="41339-206">若要針對特定的使用者強制執行以位置為基礎的路由，請設定使用者的語音原則來避免 PTSN 免付費旁路。</span><span class="sxs-lookup"><span data-stu-id="41339-206">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="41339-207">使用[授與 CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet，透過避免 PSTN 免付費旁路來啟用以位置為基礎的路由。</span><span class="sxs-lookup"><span data-stu-id="41339-207">Use the [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="41339-208">在這個範例中，我們將避免 PSTN 免付費旁路 User1's 通話原則。</span><span class="sxs-lookup"><span data-stu-id="41339-208">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="41339-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="41339-209">Related topics</span></span>

- [<span data-ttu-id="41339-210">小組中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="41339-210">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
