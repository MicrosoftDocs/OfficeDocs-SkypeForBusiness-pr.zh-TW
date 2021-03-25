---
title: 啟用直接路由的依位置路由
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 瞭解如何啟用直接Location-Based路由的路由，包括為使用者、網路網站、閘道組配置和通話規則啟用路由。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d43d650384dd538ff481ac9625c15b9a9f420d95
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120574"
---
# <a name="enable-location-based-routing-for-direct-routing"></a><span data-ttu-id="8cbac-103">啟用直接路由的依位置路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-103">Enable Location-Based Routing for Direct Routing</span></span>

<span data-ttu-id="8cbac-104">在您遵循本文中的步驟之前，請確定您閱讀了直接路由的規劃 [Location-Based 路由](location-based-routing-plan.md) ，並已完成設定路由的網路Location-Based [步驟](location-based-routing-configure-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-104">Before you follow the steps in this article, make sure you've read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) and completed the steps in [Configure network settings for Location-Based Routing](location-based-routing-configure-network-settings.md).</span></span>

<span data-ttu-id="8cbac-105">本文將說明如何啟用直接路由Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-105">This article describes how to enable Location-Based Routing for Direct Routing.</span></span> <span data-ttu-id="8cbac-106">部署電話系統直接路由並設定網路區域、網站和子網之後，就可以啟用 Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-106">After you deploy Phone System Direct Routing and set up network regions, sites, and subnets, you're ready to enable Location-Based Routing.</span></span> <span data-ttu-id="8cbac-107">若要完成本文中的步驟，您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8cbac-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="8cbac-108">若要深入瞭解，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

 <span data-ttu-id="8cbac-109">您必須啟用下列Location-Based路由：</span><span class="sxs-lookup"><span data-stu-id="8cbac-109">You have to enable Location-Based Routing for the following:</span></span>
- <span data-ttu-id="8cbac-110">使用者</span><span class="sxs-lookup"><span data-stu-id="8cbac-110">Users</span></span>
- <span data-ttu-id="8cbac-111">網路網站</span><span class="sxs-lookup"><span data-stu-id="8cbac-111">Network sites</span></span>
- <span data-ttu-id="8cbac-112">閘道配置</span><span class="sxs-lookup"><span data-stu-id="8cbac-112">Gateway configurations</span></span>
- <span data-ttu-id="8cbac-113">通話原則</span><span class="sxs-lookup"><span data-stu-id="8cbac-113">Calling policies</span></span>

<span data-ttu-id="8cbac-114">您可以使用 Microsoft [小組系統管理中心](#using-the-microsoft-teams-admin-center) 或 [PowerShel](#using-powershell)l 啟用Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-114">You can use the [Microsoft Team admin center](#using-the-microsoft-teams-admin-center) or [PowerShel](#using-powershell)l to enable Location-Based Routing.</span></span>

## <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8cbac-115">使用 Microsoft Teams 系統管理中心</span><span class="sxs-lookup"><span data-stu-id="8cbac-115">Using the Microsoft Teams admin center</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="8cbac-116">為Location-Based啟用路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-116">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="8cbac-117">建立語音路由策略，並將 PSTN 使用量指派給該策略。</span><span class="sxs-lookup"><span data-stu-id="8cbac-117">Create a voice routing policy and assign PSTN usages to the policy.</span></span> <span data-ttu-id="8cbac-118">當您將 PSTN 使用量指派給策略時，請務必執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8cbac-118">When you assign PSTN usages to a policy, make sure you do one of the following:</span></span>

    - <span data-ttu-id="8cbac-119">使用與使用 PSTN 閘道本地到網站的語音路由相關聯的 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="8cbac-119">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site.</span></span>
    - <span data-ttu-id="8cbac-120">使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，Location-Based不需要路由限制的地區。</span><span class="sxs-lookup"><span data-stu-id="8cbac-120">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>
2. <span data-ttu-id="8cbac-121">將語音路由策略指派給需要強制執行路由限制的使用者。</span><span class="sxs-lookup"><span data-stu-id="8cbac-121">Assign the voice routing policy to users who require routing restrictions to be enforced.</span></span>

<span data-ttu-id="8cbac-122">若要深入瞭解如何建立語音路由策略並將其指派給使用者，請參閱在 Microsoft Teams 中管理 [語音路由策略](manage-voice-routing-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-122">To learn more about how to create voice routing policies and assign them to users, see [Manage voice routing policies in Microsoft Teams](manage-voice-routing-policies.md).</span></span>

### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="8cbac-123">啟用Location-Based網站的路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-123">Enable Location-Based Routing for network sites</span></span>

<span data-ttu-id="8cbac-124">針對需要Location-Based路由限制的網站啟用路由路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-124">Enable Location-Based Routing for your sites that need to enforce routing restrictions.</span></span> <span data-ttu-id="8cbac-125">若要這麼做，請在 Microsoft Teams 系統管理中心的左側流覽中，前往[位置網路拓撲圖》，選取網路網站，按一下 [編輯，然後開啟位置  >  \*\*\*\*\*\*型路由\*\*。 </span><span class="sxs-lookup"><span data-stu-id="8cbac-125">To do this, in the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, select a network site, click **Edit**, and then turn on **Location based routing**.</span></span>  

<span data-ttu-id="8cbac-126">若要深入瞭解，請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-126">To learn more, see [Manage your network topology](manage-your-network-topology.md).</span></span>

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="8cbac-127">啟用Location-Based閘道的路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-127">Enable Location-Based Routing for gateways</span></span>

<span data-ttu-id="8cbac-128">啟用 Location-Based路由至閘道，將呼叫路由至將通話路由至 PSTN 的 PSTN 閘道，並將閘道所在的網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8cbac-128">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span> 

1. <span data-ttu-id="8cbac-129">在左側流覽中，前往 **[語音**  >  **直接路由**，然後按一下 **[SBC> 定位** 點。</span><span class="sxs-lookup"><span data-stu-id="8cbac-129">In the left navigation, go to **Voice** > **Direct Routing**, and then click the **SBCs** tab.</span></span>
2. <span data-ttu-id="8cbac-130">選取 SBC，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="8cbac-130">Select the SBC, and then click **Edit**.</span></span> 
3. <span data-ttu-id="8cbac-131">在 **位置路由和媒體優化下**，開啟啟用 **位置型路由**。</span><span class="sxs-lookup"><span data-stu-id="8cbac-131">Under **Location based routing and media optimization**, turn on **Enable location based routing**.</span></span>
4. <span data-ttu-id="8cbac-132">指定閘道網站識別碼，然後設定旁路模式。</span><span class="sxs-lookup"><span data-stu-id="8cbac-132">Specify the gateway site ID, and then set the bypass mode.</span></span>
5. <span data-ttu-id="8cbac-133">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="8cbac-133">Click **Save**.</span></span>

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="8cbac-134">針對Location-Based啟用路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-134">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="8cbac-135">若要針對Location-Based強制執行路由，請設定使用者的通話策略，以防止 PSTN 付費旁路。</span><span class="sxs-lookup"><span data-stu-id="8cbac-135">To enforce Location-Based Routing for specific users, set up the user's calling policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="8cbac-136">若要這麼做，請開啟通話政策中的防止付費旁路設定。</span><span class="sxs-lookup"><span data-stu-id="8cbac-136">To do this, turn on the **Prevent toll bypass** setting in the calling policy.</span></span>

<span data-ttu-id="8cbac-137">若要深入瞭解，請參閱 Teams [中的通話政策](teams-calling-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-137">To learn more, see [Calling policies in Teams](teams-calling-policy.md).</span></span>

## <a name="using-powershell"></a><span data-ttu-id="8cbac-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="8cbac-138">Using PowerShell</span></span>

### <a name="enable-location-based-routing-for-users"></a><span data-ttu-id="8cbac-139">為Location-Based啟用路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-139">Enable Location-Based Routing for users</span></span>

1. <span data-ttu-id="8cbac-140">使用 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) Cmdlet 來設定 PSTN 使用方式。</span><span class="sxs-lookup"><span data-stu-id="8cbac-140">Use the [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet to set PSTN usages.</span></span> <span data-ttu-id="8cbac-141">針對多個使用方式，請以逗號分隔每個使用方式。</span><span class="sxs-lookup"><span data-stu-id="8cbac-141">For multiple usages, separate each usage with a comma.</span></span>

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    <span data-ttu-id="8cbac-142">例如：</span><span class="sxs-lookup"><span data-stu-id="8cbac-142">For example:</span></span>
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. <span data-ttu-id="8cbac-143">使用 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 建立語音路由策略，讓使用者與適當的 PSTN 使用方式建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8cbac-143">Use the [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to create a voice routing policy to associate the user with the appropriate PSTN usages.</span></span>

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    <span data-ttu-id="8cbac-144">當您將 PSTN 使用量指派給語音路由策略時，請務必執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="8cbac-144">When you assign PSTN usages to a voice routing policy, make sure you do one of the following:</span></span>
    - <span data-ttu-id="8cbac-145">使用與使用 PSTN 閘道本地到網站的語音路由相關聯的 PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="8cbac-145">Use PSTN usages associated to voice routes that use a PSTN gateway local to the site</span></span>
    - <span data-ttu-id="8cbac-146">使用與使用 PSTN 閘道的語音路由相關聯的 PSTN 使用方式，Location-Based不需要路由限制的地區。</span><span class="sxs-lookup"><span data-stu-id="8cbac-146">Use PSTN usages associated to voice routes that use a PSTN gateway located in a region where Location-Based Routing restrictions aren't needed.</span></span>

    <span data-ttu-id="8cbac-147">在此範例中，我們建立兩個新的語音路由策略，並指派 PSTN 使用方式給他們。</span><span class="sxs-lookup"><span data-stu-id="8cbac-147">In this example, we create two new voice routing policies and assign PSTN usages to them.</span></span> 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    <span data-ttu-id="8cbac-148">下表顯示此範例中定義的語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="8cbac-148">The following table shows the voice routing policies defined in this example.</span></span> 
    
    ||<span data-ttu-id="8cbac-149">語音路由策略 1</span><span class="sxs-lookup"><span data-stu-id="8cbac-149">Voice routing policy 1</span></span>|<span data-ttu-id="8cbac-150">語音路由策略 2</span><span class="sxs-lookup"><span data-stu-id="8cbac-150">Voice routing policy 2</span></span>|
    |---------|---------|---------|
    |<span data-ttu-id="8cbac-151">線上語音策略識別碼</span><span class="sxs-lookup"><span data-stu-id="8cbac-151">Online voice policy ID</span></span>   |<span data-ttu-id="8cbac-152">印度線上語音路由政策</span><span class="sxs-lookup"><span data-stu-id="8cbac-152">Delhi online voice routing policy</span></span>   |<span data-ttu-id="8cbac-153">海德拉巴線上語音路由政策</span><span class="sxs-lookup"><span data-stu-id="8cbac-153">Hyderabad online voice routing policy</span></span>    |
    |<span data-ttu-id="8cbac-154">線上 PSTN 使用方式</span><span class="sxs-lookup"><span data-stu-id="8cbac-154">Online PSTN usages</span></span>  |<span data-ttu-id="8cbac-155">長距離</span><span class="sxs-lookup"><span data-stu-id="8cbac-155">Long Distance</span></span>  |<span data-ttu-id="8cbac-156">長距離、本地、內部</span><span class="sxs-lookup"><span data-stu-id="8cbac-156">Long Distance, Local, Internal</span></span>  |

3. <span data-ttu-id="8cbac-157">使用 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) Cmdlet 將線上語音路由策略關聯到需要強制執行路由限制的使用者。</span><span class="sxs-lookup"><span data-stu-id="8cbac-157">Use the [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet to associate online voice routing policies to users who require routing restrictions to be     enforced.</span></span>
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a><span data-ttu-id="8cbac-158">啟用Location-Based網站的路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-158">Enable Location-Based Routing for network sites</span></span>

1.  <span data-ttu-id="8cbac-159">使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) Cmdlet 啟用 Location-Based 路由，並將語音路由策略關聯到需要強制執行路由限制的網路網站。</span><span class="sxs-lookup"><span data-stu-id="8cbac-159">Use the [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet to enable Location-Based Routing and associate voice routing policies to your network sites that need to enforce routing restrictions.</span></span>
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    <span data-ttu-id="8cbac-160">在此範例中，我們Location-Based印度網站和海德拉巴網站的路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-160">In this example, we enable Location-Based Routing for the Delhi site and the Hyderabad site.</span></span> 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    <span data-ttu-id="8cbac-161">下表顯示在此範例中啟用 Location-Based路由的網站。</span><span class="sxs-lookup"><span data-stu-id="8cbac-161">The following table shows the sites enabled for Location-Based Routing in this example.</span></span>

    ||<span data-ttu-id="8cbac-162">第 1 (裡) </span><span class="sxs-lookup"><span data-stu-id="8cbac-162">Site 1 (Delhi)</span></span>  |<span data-ttu-id="8cbac-163">網站 2 (海德拉巴) </span><span class="sxs-lookup"><span data-stu-id="8cbac-163">Site 2 (Hyderabad)</span></span>  |
    |---------|---------|---------|
|<span data-ttu-id="8cbac-164">網站名稱</span><span class="sxs-lookup"><span data-stu-id="8cbac-164">Site name</span></span>    |<span data-ttu-id="8cbac-165">第 1 (裡) </span><span class="sxs-lookup"><span data-stu-id="8cbac-165">Site 1 (Delhi)</span></span>    |<span data-ttu-id="8cbac-166">網站 2 (海德拉巴) </span><span class="sxs-lookup"><span data-stu-id="8cbac-166">Site 2 (Hyderabad)</span></span>   
    |<span data-ttu-id="8cbac-167">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="8cbac-167">EnableLocationBasedRouting</span></span>    |<span data-ttu-id="8cbac-168">真</span><span class="sxs-lookup"><span data-stu-id="8cbac-168">True</span></span>    |<span data-ttu-id="8cbac-169">真</span><span class="sxs-lookup"><span data-stu-id="8cbac-169">True</span></span>    |
    |<span data-ttu-id="8cbac-170">子網</span><span class="sxs-lookup"><span data-stu-id="8cbac-170">Subnets</span></span>     |<span data-ttu-id="8cbac-171">第 1 (裡) </span><span class="sxs-lookup"><span data-stu-id="8cbac-171">Subnet 1 (Delhi)</span></span>     |<span data-ttu-id="8cbac-172">子網 2 (海德拉巴) </span><span class="sxs-lookup"><span data-stu-id="8cbac-172">Subnet 2 (Hyderabad)</span></span>     |

### <a name="enable-location-based-routing-for-gateways"></a><span data-ttu-id="8cbac-173">啟用Location-Based閘道的路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-173">Enable Location-Based Routing for gateways</span></span>

1. <span data-ttu-id="8cbac-174">使用 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) Cmdlet 為每個閘道或網路網站建立閘道組式。</span><span class="sxs-lookup"><span data-stu-id="8cbac-174">Use the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet to create a gateway configuration for each gateway or network site.</span></span> 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    <span data-ttu-id="8cbac-175">如果多個閘道與系統連結 (例如閘道或 PBX) ，請修改每個閘道，Location-Based路由限制。</span><span class="sxs-lookup"><span data-stu-id="8cbac-175">If multiple gateways are associated with a system (for example, Gateway or PBX), modify each gateway to enable Location-Based Routing restrictions.</span></span> 

    <span data-ttu-id="8cbac-176">在此範例中，我們會為每個閘道建立一個閘道組。</span><span class="sxs-lookup"><span data-stu-id="8cbac-176">In this example, we create one gateway configuration for each gateway.</span></span> 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    <span data-ttu-id="8cbac-177">詳細資訊，請參閱設定 [直接路由](direct-routing-configure.md)。</span><span class="sxs-lookup"><span data-stu-id="8cbac-177">For more information, see [Configure Direct Routing](direct-routing-configure.md).</span></span>
    
2. <span data-ttu-id="8cbac-178">使用 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) Cmdlet 為需要強制執行路由限制Location-Based閘道啟用 Location-Based路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-178">Use the [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet to enable Location-Based Routing for your gateways that need to enforce routing restrictions.</span></span> 

    <span data-ttu-id="8cbac-179">啟用 Location-Based路由至閘道，將呼叫路由至將通話路由至 PSTN 的 PSTN 閘道，並將閘道所在的網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8cbac-179">Enable Location-Based Routing to gateways that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    <span data-ttu-id="8cbac-180">在此範例中，我們針對Location-Based和海德拉巴網站中與 PSTN 閘道相關聯的每個閘道啟用 [路由路由>。</span><span class="sxs-lookup"><span data-stu-id="8cbac-180">In this example, we enable Location-Based Routing for each gateway that's associated to PSTN gateways in the Delhi and Hyderabad sites.</span></span> 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    <span data-ttu-id="8cbac-181">請勿針對不會將Location-Based路由到 PSTN 的閘道啟用路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-181">Don't enable Location-Based Routing for gateways that don't route calls to the PSTN.</span></span> <span data-ttu-id="8cbac-182">不過，您仍然需要將閘道與系統所在的網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="8cbac-182">However, you still have to associate the gateway to the network site where the system is located.</span></span> <span data-ttu-id="8cbac-183">這是因為必須Location-Based PSTN 通話到達經由此閘道連接的端點時，強制執行路由限制。</span><span class="sxs-lookup"><span data-stu-id="8cbac-183">This is because Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints that are connected via this gateway.</span></span> <span data-ttu-id="8cbac-184">在此範例中，Location-Based和海德拉巴網站中與 PBX 系統相關聯的每個閘道，不會啟用路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-184">In this example, Location-Based Routing isn't enabled for each gateway that's associated to PBX systems in the Delhi and Hyderabad sites.</span></span>

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a><span data-ttu-id="8cbac-185">針對Location-Based啟用路由</span><span class="sxs-lookup"><span data-stu-id="8cbac-185">Enable Location-Based Routing for calling policies</span></span>

<span data-ttu-id="8cbac-186">若要針對Location-Based強制路由，請設定使用者的語音策略，以防止 PTSN 付費旁路。</span><span class="sxs-lookup"><span data-stu-id="8cbac-186">To enforce Location-Based Routing for specific users, set up the users' voice policy to prevent PTSN toll bypass.</span></span> 

<span data-ttu-id="8cbac-187">使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) Cmdlet 來Location-Based PSTN 付費旁路來啟用路由。</span><span class="sxs-lookup"><span data-stu-id="8cbac-187">Use the [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet to enable Location-Based routing by preventing PSTN toll bypass.</span></span>

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
<span data-ttu-id="8cbac-188">在此範例中，我們防止 PSTN 付費旁路至 User1 的通話政策。</span><span class="sxs-lookup"><span data-stu-id="8cbac-188">In this example, we prevent PSTN toll bypass to User1's calling policies.</span></span> 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a><span data-ttu-id="8cbac-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="8cbac-189">Related topics</span></span>

- [<span data-ttu-id="8cbac-190">Teams 中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="8cbac-190">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)