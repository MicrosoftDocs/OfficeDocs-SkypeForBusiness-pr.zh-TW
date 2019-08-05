---
title: 在商務用 Skype 中部署網路區域、網站和子網
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: '在商務用 Skype Server 中建立或修改網路區域、網路網站, 以及建立網路子網的關聯。 所有這些都適用于高級企業語音功能: [媒體旁路]、[通話許可控制] 和 [位置] 路由。'
ms.openlocfilehash: 3ce0f4dcf011f57e25c4741c34135bc4ba62085a
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/25/2019
ms.locfileid: "36193956"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="dabee-104">在商務用 Skype 中部署網路區域、網站和子網</span><span class="sxs-lookup"><span data-stu-id="dabee-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="dabee-105">在商務用 Skype Server 中建立或修改網路區域、網路網站, 以及建立網路子網的關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="dabee-106">所有這些都適用于高級企業語音功能: [媒體旁路]、[通話許可控制] 和 [位置] 路由。</span><span class="sxs-lookup"><span data-stu-id="dabee-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="dabee-107">[高級企業語音功能] 是 [[呼叫許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)]、[[媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)]、[[位置] 路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), 以及[E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。</span><span class="sxs-lookup"><span data-stu-id="dabee-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="dabee-108">這些功能全都需要您建立網路區域、網路網站和子網。</span><span class="sxs-lookup"><span data-stu-id="dabee-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="dabee-109">例如, 所有這些功能都要求拓撲中的每個子網都與特定的網路網站相關聯, 且每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="dabee-110">如需這些詞彙的詳細資訊, 請參閱[商務用 Skype Server 中的 [高級企業語音功能網路設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)]。</span><span class="sxs-lookup"><span data-stu-id="dabee-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="dabee-111">[通話許可控制] 和 [E9-1-1] 有網路網站的其他配置需求:</span><span class="sxs-lookup"><span data-stu-id="dabee-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="dabee-112">呼叫許可控制要求為受 WAN 頻寬限制所限制的每個網站指定頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="dabee-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="dabee-113">如果您打算部署通話許可控制, 您必須先[在商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md), 然後才能設定您的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="dabee-114">E9-1-1-1 需要為每個網站指定位置原則。</span><span class="sxs-lookup"><span data-stu-id="dabee-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="dabee-115">如果您打算部署 E9-1-1, 您必須先[在商務用 Skype Server 中建立位置原則](create-location-policies.md), 然後才能設定您的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="dabee-116">建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="dabee-116">Create or modify a Network Region</span></span>

<span data-ttu-id="dabee-117">如果您已經為其中一個功能建立網路區域, 則不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="dabee-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="dabee-118">不過, 您可能需要修改現有的網路區域定義, 才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="dabee-119">例如, 如果您已建立 E9 的網路區域 (不需要關聯的中央網站), 而您想要部署 [呼叫許可控制], 您必須修改網路區域定義, 以指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dabee-120">使用商務用 Skype Server Management Shell 建立網路區域</span><span class="sxs-lookup"><span data-stu-id="dabee-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dabee-121">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dabee-122">執行新的 CsNetworkRegion Cmdlet 來建立網路區域:</span><span class="sxs-lookup"><span data-stu-id="dabee-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="dabee-123">例如：</span><span class="sxs-lookup"><span data-stu-id="dabee-123">For example:</span></span>

   ```
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="dabee-124">在這個範例中, 您建立了一個名為「北美洲」的網路區域, 該區域與含「網站 ID 芝加哥」的中央網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="dabee-125">若要為您的拓撲建立網路區域, 請對每個網路區域重複步驟2的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dabee-126">使用商務用 Skype Server [控制台] 建立網路區域</span><span class="sxs-lookup"><span data-stu-id="dabee-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dabee-127">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dabee-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="dabee-128">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="dabee-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="dabee-129">按一下 [**地區**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-129">Click **Region**.</span></span>

4. <span data-ttu-id="dabee-130">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-130">Click **New**.</span></span>

5. <span data-ttu-id="dabee-131">在 [**新區域**] 頁面上, 按一下 [**名稱**], 然後輸入網路區域的名稱。</span><span class="sxs-lookup"><span data-stu-id="dabee-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="dabee-132">按一下 [**中央網站**], 然後按一下清單中的中央網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="dabee-133">或者, 按一下 [**描述**], 然後輸入說明此網路網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dabee-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="dabee-134">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dabee-134">Click **Commit**.</span></span>

9. <span data-ttu-id="dabee-135">若要為您的拓撲建立網路區域, 請重複步驟4至8及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dabee-136">使用商務用 Skype Server Management Shell 來修改網路區域</span><span class="sxs-lookup"><span data-stu-id="dabee-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dabee-137">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dabee-138">執行 CsNetworkRegion Cmdlet 來修改現有的網路區域:</span><span class="sxs-lookup"><span data-stu-id="dabee-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="dabee-139">例如：</span><span class="sxs-lookup"><span data-stu-id="dabee-139">For example:</span></span>

   ```
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="dabee-140">在這個範例中, 您修改了「北美」 (使用本主題先前的程式建立) 的現有網路區域, 方法是變更說明。</span><span class="sxs-lookup"><span data-stu-id="dabee-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="dabee-141">如果「北美」區域的描述存在, 這個命令會以這個值覆寫;如果沒有設定描述, 則這個命令會將其設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="dabee-142">若要修改其他網路區域, 請對其他地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="dabee-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dabee-143">使用商務用 Skype Server [控制台] 修改網路區域</span><span class="sxs-lookup"><span data-stu-id="dabee-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dabee-144">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dabee-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="dabee-145">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="dabee-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="dabee-146">按一下 [**地區**] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="dabee-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="dabee-147">在表格中, 按一下您要修改的網路區域。</span><span class="sxs-lookup"><span data-stu-id="dabee-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="dabee-148">按一下 [**編輯**], 然後按一下 [**顯示詳細資料 ...**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="dabee-149">在 [**編輯區域**] 頁面上, 視需要變更這個網路區域設定的值。</span><span class="sxs-lookup"><span data-stu-id="dabee-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="dabee-150">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dabee-150">Click **Commit**.</span></span>

8. <span data-ttu-id="dabee-151">若要完成修改網路區域, 請重複步驟4至7及其他地區的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="dabee-152">建立或修改網站</span><span class="sxs-lookup"><span data-stu-id="dabee-152">Create or modify a network site</span></span>

<span data-ttu-id="dabee-153">如果您已經為其中一個功能建立網路網站, 就不需要建立新的網路網站;其他高級企業語音功能將會使用相同的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="dabee-154">不過, 您可能需要修改現有的網路網站定義, 才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="dabee-155">例如, 如果您已建立 E9 的網路網站-1-1, 您需要在部署通話許可控制期間修改網路網站, 以套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="dabee-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dabee-156">使用商務用 Skype Server Management Shell 建立網路網站</span><span class="sxs-lookup"><span data-stu-id="dabee-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dabee-157">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dabee-158">執行新的 CsNetworkSite Cmdlet 來建立網路網站:</span><span class="sxs-lookup"><span data-stu-id="dabee-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="dabee-159">例如：</span><span class="sxs-lookup"><span data-stu-id="dabee-159">For example:</span></span>

   ```
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="dabee-160">在這個範例中, 您已建立名為「芝加哥」的網路網站, 該網路網站是「北美」網路區域。</span><span class="sxs-lookup"><span data-stu-id="dabee-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dabee-161">[北美] 網路區域必須已經存在, 此命令才能順利執行。</span><span class="sxs-lookup"><span data-stu-id="dabee-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="dabee-162">若要為拓撲建立網路網站, 請對 [其他網站] 的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="dabee-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dabee-163">使用商務用 Skype Server [控制台] 建立網路網站</span><span class="sxs-lookup"><span data-stu-id="dabee-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dabee-164">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dabee-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="dabee-165">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="dabee-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="dabee-166">按一下 [**網站導航**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="dabee-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="dabee-167">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-167">Click **New**.</span></span>

5. <span data-ttu-id="dabee-168">在 [**新網站**] 頁面上, 按一下 [**名稱**], 然後輸入網路網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="dabee-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="dabee-169">按一下 [**地區**], 然後按一下清單中的區域。</span><span class="sxs-lookup"><span data-stu-id="dabee-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="dabee-170">或者, 按一下 [**頻寬原則**], 然後按一下清單中的頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="dabee-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dabee-171">只有當您在網站上部署 [通話許可控制] 時, 才需要頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="dabee-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="dabee-172">或者, 按一下 [**位置原則**], 然後按一下清單中的位置原則。</span><span class="sxs-lookup"><span data-stu-id="dabee-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dabee-173">只有當您在網站上部署 E9-1-1 時, 才需要位置原則。</span><span class="sxs-lookup"><span data-stu-id="dabee-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="dabee-174">或者, 按一下 [**描述**], 然後輸入說明此網路網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dabee-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="dabee-175">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dabee-175">Click **Commit**.</span></span>

11. <span data-ttu-id="dabee-176">若要為您的拓撲建立網路網站, 請重複步驟4至 10, 並使用 [其他網站] 的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dabee-177">使用商務用 Skype Server Management Shell 來修改網路網站</span><span class="sxs-lookup"><span data-stu-id="dabee-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dabee-178">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dabee-179">執行 CsNetworkSite Cmdlet 來修改網路網站:</span><span class="sxs-lookup"><span data-stu-id="dabee-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="dabee-180">例如：</span><span class="sxs-lookup"><span data-stu-id="dabee-180">For example:</span></span>

   ```
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="dabee-181">在這個範例中, 名為 "Albuquerque" 的網站會移至 [北美] 網路區域。</span><span class="sxs-lookup"><span data-stu-id="dabee-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="dabee-182">若要修改網路網站設定以部署呼叫許可控制、E9-1 或媒體旁路, 請分別執行設定 CsNetworkSite Cmdlet 及 BWPolicyProfileID 或 LocationPolicy 參數, 以修改網路網站設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dabee-183">雖然 BypassID 參數存在於媒體旁路, 但我們強烈建議您不要覆寫自動產生的旁路 Id。</span><span class="sxs-lookup"><span data-stu-id="dabee-183">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs.</span></span> <span data-ttu-id="dabee-184">您不需要指定其他參數, 即可設定媒體旁路的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-184">You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="dabee-185">若要完成拓撲的網路網站修改, 請對 [其他網站] 的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="dabee-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dabee-186">使用商務用 Skype Server [控制台] 修改網路網站</span><span class="sxs-lookup"><span data-stu-id="dabee-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dabee-187">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dabee-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="dabee-188">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="dabee-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="dabee-189">按一下 [**網站導航**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="dabee-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="dabee-190">在表格中, 按一下您要修改的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="dabee-191">按一下 [**編輯**], 然後按一下 [**顯示詳細資料 ...**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="dabee-192">在 [**編輯網站**] 頁面上, 視需要變更此網路網站設定的值。</span><span class="sxs-lookup"><span data-stu-id="dabee-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="dabee-193">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dabee-193">Click **Commit**.</span></span>

8. <span data-ttu-id="dabee-194">若要完成修改網路網站, 請重複步驟4至7及 [其他網站] 的設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="dabee-195">建立子網路與網路站台的關聯</span><span class="sxs-lookup"><span data-stu-id="dabee-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="dabee-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="dabee-196"></span></span>

<span data-ttu-id="dabee-197">您網路中的每個子網都必須與特定的網路網站相關聯, 因為子網資訊是用來判斷在啟動新的會話時, 端點所在的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="dabee-198">當會話中每一方的位置已知時, 高級企業語音功能可以套用該資訊來決定如何處理通話設定或路由。</span><span class="sxs-lookup"><span data-stu-id="dabee-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="dabee-199">您必須將部署中音訊/視頻邊緣伺服器的所有已設定公用 IP 位址新增至您的網路設定。</span><span class="sxs-lookup"><span data-stu-id="dabee-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="dabee-200">這些 IP 位址會新增成遮罩為32的子網。</span><span class="sxs-lookup"><span data-stu-id="dabee-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="dabee-201">相關的網路網站應該對應至適當設定的網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="dabee-202">例如, 與中央網站芝加哥中的 A/V Edge 服務相對應的公用 IP 位址會是 NetworkSiteID 芝加哥。</span><span class="sxs-lookup"><span data-stu-id="dabee-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="dabee-203">使用商務用 Skype Server Management 命令介面將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="dabee-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="dabee-204">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="dabee-205">執行**新的 CsNetworkSubnet** Cmdlet, 以將子網與網路網站建立關聯:</span><span class="sxs-lookup"><span data-stu-id="dabee-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="dabee-206">例如：</span><span class="sxs-lookup"><span data-stu-id="dabee-206">For example:</span></span>

   ```
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="dabee-207">在這個範例中, 您已在子網172.11.12.13 和網路網站 "芝加哥" 之間建立關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="dabee-208">針對您的拓撲中的所有子網, 重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="dabee-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="dabee-209">匯入 CSV 檔案以將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="dabee-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="dabee-210">建立包含您要新增之所有子網的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="dabee-210">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="dabee-211">例如, 建立名為**subnet**的檔案, 並提供下列內容:</span><span class="sxs-lookup"><span data-stu-id="dabee-211">For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="dabee-212">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="dabee-213">執行下列 Cmdlet 以匯入**子網 .csv**, 然後將其內容儲存在 Lync Server 管理儲存區:</span><span class="sxs-lookup"><span data-stu-id="dabee-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="dabee-214">使用商務用 Skype Server [控制台] 將子網與網路網站建立關聯</span><span class="sxs-lookup"><span data-stu-id="dabee-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="dabee-215">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="dabee-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="dabee-216">在左側導覽列中, 按一下 [**網路**設定]。</span><span class="sxs-lookup"><span data-stu-id="dabee-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="dabee-217">按一下**子網**導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="dabee-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="dabee-218">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="dabee-218">Click **New**.</span></span>

5. <span data-ttu-id="dabee-219">在 [**新的子網**] 頁面上, 按一下 [**子網識別碼**], 然後在您想要與網路網站建立關聯的子網所定義的 IP 位址範圍中輸入第一個位址。</span><span class="sxs-lookup"><span data-stu-id="dabee-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="dabee-220">按一下 [**遮罩**], 然後輸入要套用至子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="dabee-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="dabee-221">按一下 [**網路網站識別碼**], 然後選取您要新增此子網的網站的 [網站識別碼]。</span><span class="sxs-lookup"><span data-stu-id="dabee-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="dabee-222">如果您尚未建立網路網站, 此清單將會是空白的。</span><span class="sxs-lookup"><span data-stu-id="dabee-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="dabee-223">如需程式的詳細資訊, 請參閱[建立或修改網路網站](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dabee-223">For details about the procedure, see [Create or Modify a Network Site](https://technet.microsoft.com/library/14e24856-9996-4da4-9f31-300940bdf5aa.aspx).</span></span> <span data-ttu-id="dabee-224">您也可以執行**CsNetworkSite** Cmdlet, 以取得您的部署的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="dabee-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="dabee-225">如需詳細資訊, 請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="dabee-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="dabee-226">或者, 按一下 [**描述**], 然後輸入說明這個子網上的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="dabee-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="dabee-227">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dabee-227">Click **Commit**.</span></span>

<span data-ttu-id="dabee-228">重複這些步驟, 將其他子網新增至網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="dabee-229">會產生一個金鑰健康情況指標 (KHI) 警示, 指定您網路中存在的 IP 位址清單, 但不與子網建立關聯, 或者包含 IP 位址的子網不與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="dabee-230">在8小時內, 不會多次引發此通知。</span><span class="sxs-lookup"><span data-stu-id="dabee-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="dabee-231">相關的警示資訊和範例如下所示:</span><span class="sxs-lookup"><span data-stu-id="dabee-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="dabee-232">**來源**: CS 頻寬原則服務 (核心)</span><span class="sxs-lookup"><span data-stu-id="dabee-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="dabee-233">**事件號碼**: 36034</span><span class="sxs-lookup"><span data-stu-id="dabee-233">**Event number**: 36034</span></span>

 <span data-ttu-id="dabee-234">**層級**: 2</span><span class="sxs-lookup"><span data-stu-id="dabee-234">**Level**: 2</span></span>

 <span data-ttu-id="dabee-235">**描述**: 下列 ip 位址的子網: \<未設定 ip 位址\>清單, 或子網不與網路網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="dabee-236">**原因**: 網路設定中缺少對應 IP 位址的子網, 或子網不會與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="dabee-237">**解決**方式: 將與 IP 位址清單相對應的子網新增至 [網路設定], 並將每個子網與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="dabee-238">例如, 如果警示中的 IP 位址清單指定10.121.248.226 和 10.121.249.20, 則這些 IP 位址不會與子閘道聯, 或與其相關聯的子網不屬於網路網站。</span><span class="sxs-lookup"><span data-stu-id="dabee-238">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="dabee-239">如果 10.121.248.0/24 和 10.121.249.0/24 是這些位址對應的子網, 您可以解決此問題, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="dabee-239">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="dabee-240">請確定 IP 位址10.121.248.226 已與 10.121.249.0/24 子網相關聯的 10.121.248.0/24 子網和 IP 位址10.121.249.20 相關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="dabee-241">請確定 10.121.248.0/24 和 10.121.249.0/24 子網分別與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="dabee-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="dabee-242">另請參閱</span><span class="sxs-lookup"><span data-stu-id="dabee-242">See also</span></span>
<span data-ttu-id="dabee-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="dabee-243"></span></span>


[<span data-ttu-id="dabee-244">新-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="dabee-244">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="dabee-245">CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="dabee-245">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="dabee-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="dabee-246">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="dabee-247">移除-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="dabee-247">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="dabee-248">新-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dabee-248">New-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="dabee-249">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dabee-249">Get-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="dabee-250">Set-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dabee-250">Set-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="dabee-251">移除-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="dabee-251">Remove-CsNetworkSubnet</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)

