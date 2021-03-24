---
title: 在商務用 Skype 中部署網路地區、網站和子網
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
description: 在商務用 Skype Server 中建立或修改網路地區、網路網站及建立網路子網。 所有這些皆用於高級 Enterprise Voice 功能：媒體旁路、通話許可控制和位置基礎路由。
ms.openlocfilehash: adfcf418fd2b1ef607947687afb766fee6b64715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103519"
---
# <a name="deploy-network-regions-sites-and-subnets-in-skype-for-business"></a><span data-ttu-id="ddc0e-104">在商務用 Skype 中部署網路地區、網站和子網</span><span class="sxs-lookup"><span data-stu-id="ddc0e-104">Deploy network regions, sites and subnets in Skype for Business</span></span>

<span data-ttu-id="ddc0e-105">在商務用 Skype Server 中建立或修改網路地區、網路網站及建立網路子網。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-105">Create or modify network regions, network sites, and associate network subnets in Skype for Business Server.</span></span> <span data-ttu-id="ddc0e-106">所有這些皆用於高級 Enterprise Voice 功能：媒體旁路、通話許可控制和位置基礎路由。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-106">All these are used for the advanced Enterprise Voice features: media bypass, call admission control, and location-based routing.</span></span>

<span data-ttu-id="ddc0e-107">「高級 Enterprise Voice」功能是 [通話許可控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)、 [媒體旁路](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)、 [位置基礎路由](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md)和 [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-107">The advanced Enterprise Voice features are [call admission control](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md), [media bypass](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md), [location-based routing](../../plan-your-deployment/enterprise-voice-solution/location-based-routing.md), and [E9-1-1](../../plan-your-deployment/enterprise-voice-solution/emergency-services.md).</span></span> <span data-ttu-id="ddc0e-108">這些功能全部都需要您建立網路地區、網路網站和子網。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-108">These features all require you to create network regions, network sites, and subnets.</span></span> <span data-ttu-id="ddc0e-109">例如，所有這些功能都要求拓撲中的每個子網都與特定網路網站相關聯，而且每個網路網站都必須與網路地區產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-109">For example, all of these features require that each subnet in your topology be associated with a specific network site, and each network site must be associated with a network region.</span></span> <span data-ttu-id="ddc0e-110">如需這些字詞的詳細資訊，請參閱 [商務用 Skype Server 中的高級 Enterprise Voice 功能網路設定](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-110">For more information on these terms, see [Network settings for the advanced Enterprise Voice features in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/network-settings-for-advanced-features.md).</span></span>

<span data-ttu-id="ddc0e-111">通話許可控制及 E9-1-1 具有其他的網站設定需求：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-111">Call admission control and E9-1-1 have additional configuration requirements for network sites:</span></span>

- <span data-ttu-id="ddc0e-112">通話許可控制需要指定透過 WAN 頻寬限制所限制之每個網站的「頻寬原則設定檔」。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-112">Call admission control requires that a bandwidth policy profile be specified for each site that is constrained by WAN bandwidth limitations.</span></span> <span data-ttu-id="ddc0e-113">如果您打算部署通話許可控制，您必須先 [在商務用 Skype Server 中建立頻寬原則設定檔](create-bandwidth-policy-profiles.md) ，再設定網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-113">If you plan to deploy call admission control, you must [Create bandwidth policy profiles in Skype for Business Server](create-bandwidth-policy-profiles.md) before you configure your network sites.</span></span>

- <span data-ttu-id="ddc0e-114">E9-1-1 需要指定每個網站的「位置原則」。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-114">E9-1-1 requires that a location policy be specified for each site.</span></span> <span data-ttu-id="ddc0e-115">如果您打算部署 E9-1-1，您必須先 [在商務用 Skype Server 中建立位置原則](create-location-policies.md) ，再設定網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-115">If you plan to deploy E9-1-1, you must [Create location policies in Skype for Business Server](create-location-policies.md) before you configure your network sites.</span></span>

## <a name="create-or-modify-a-network-region"></a><span data-ttu-id="ddc0e-116">建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ddc0e-116">Create or modify a Network Region</span></span>

<span data-ttu-id="ddc0e-117">如果您已經為這些功能之一建立網路地區，則不需要建立新的網路地區;其他的高級 Enterprise Voice 功能會使用相同的網路地區。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-117">If you have already created network regions for one of these features, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span>

<span data-ttu-id="ddc0e-118">不過，您必須修改現有的網路區域定義，以套用功能特定的設定。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-118">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ddc0e-119">例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-119">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ddc0e-120">使用商務用 Skype Server 管理命令介面建立網路地區</span><span class="sxs-lookup"><span data-stu-id="ddc0e-120">To create a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ddc0e-121">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-121">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddc0e-122">執行 New-CsNetworkRegion Cmdlet 來建立網路地區：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-122">Run the New-CsNetworkRegion cmdlet to create network regions:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="ddc0e-123">例如：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-123">For example:</span></span>

   ```powershell
   New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
   ```

    <span data-ttu-id="ddc0e-124">在此範例中，您會建立一個名為「NorthAmerica」的網路地區，該網路地區與網站識別碼芝加哥相關聯的中央網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-124">In this example, you created a network region called "NorthAmerica" that is associated with a central site with site ID CHICAGO.</span></span>

3. <span data-ttu-id="ddc0e-125">若要完成建立拓撲的網路地區，請使用每個網路地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-125">To finish creating network regions for your topology, repeat step 2 with settings for each network region.</span></span>

### <a name="to-create-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ddc0e-126">使用商務用 Skype Server 控制台建立網路地區</span><span class="sxs-lookup"><span data-stu-id="ddc0e-126">To create a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ddc0e-127">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-127">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ddc0e-128">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-128">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ddc0e-129">按一下 [ **地區**]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-129">Click **Region**.</span></span>

4. <span data-ttu-id="ddc0e-130">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-130">Click **New**.</span></span>

5. <span data-ttu-id="ddc0e-131">在 [ **新地區** ] 頁面上，按一下 [ **名稱** ]，然後輸入網路地區的名稱。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-131">On the **New Region** page, click **Name** and then type a name for the network region.</span></span>

6. <span data-ttu-id="ddc0e-132">按一下 [ **中央網站**]，然後按一下清單中的中央網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-132">Click **Central site**, and then click a central site in the list.</span></span>

7. <span data-ttu-id="ddc0e-133">(選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-133">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

8. <span data-ttu-id="ddc0e-134">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-134">Click **Commit**.</span></span>

9. <span data-ttu-id="ddc0e-135">若要完成建立拓撲的網路地區，請使用其他地區的設定重複步驟4到8。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-135">To finish creating network regions for your topology, repeat steps 4 through 8 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ddc0e-136">使用商務用 Skype Server 管理命令介面來修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ddc0e-136">To modify a network region using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ddc0e-137">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-137">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddc0e-138">執行 Set-CsNetworkRegion Cmdlet 以修改現有的網路地區：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-138">Run the Set-CsNetworkRegion cmdlet to modify an existing network region:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity <String> -CentralSite <String>
   ```

    <span data-ttu-id="ddc0e-139">例如：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-139">For example:</span></span>

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
   ```

    <span data-ttu-id="ddc0e-140">在此範例中，您會使用本) 主題稍早的程式（透過變更描述）來建立名為「NorthAmerica」 (的現有網路地區。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-140">In this example, you modified an existing network region called "NorthAmerica" (created using the procedures earlier in this topic) by changing the description.</span></span> <span data-ttu-id="ddc0e-141">如果「NorthAmerica」區域的描述存在，此命令會以此值覆寫該描述。如果未設定任何描述，則此命令會將其設定。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-141">If a description existed for the "NorthAmerica" region, this command overwrites it with this value; if no description had been set, then this command sets it.</span></span>

3. <span data-ttu-id="ddc0e-142">若要修改其他網路地區，請使用其他地區的設定重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-142">To modify other network regions, repeat step 2 with settings for other regions.</span></span>

### <a name="to-modify-a-network-region-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ddc0e-143">使用商務用 Skype Server 控制台修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ddc0e-143">To modify a network region using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ddc0e-144">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-144">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ddc0e-145">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-145">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ddc0e-146">按一下 [ **地區** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-146">Click the **Region** navigation button.</span></span>

4. <span data-ttu-id="ddc0e-147">在表格中，按一下您要修改的網路地區。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-147">In the table, click the network region that you want to modify.</span></span>

5. <span data-ttu-id="ddc0e-148">按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-148">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="ddc0e-149">在 [ **編輯地區** ] 頁面上，視需要變更此網路地區的設定值。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-149">On the **Edit Region** page, change the values for this network region's settings as appropriate.</span></span>

7. <span data-ttu-id="ddc0e-150">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-150">Click **Commit**.</span></span>

8. <span data-ttu-id="ddc0e-151">若要完成修改網路地區，請使用其他地區的設定重複步驟4到7。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-151">To finish modify network regions, repeat steps 4 through 7 with settings for other regions.</span></span>

## <a name="create-or-modify-a-network-site"></a><span data-ttu-id="ddc0e-152">建立或修改網路網站</span><span class="sxs-lookup"><span data-stu-id="ddc0e-152">Create or modify a network site</span></span>

<span data-ttu-id="ddc0e-153">如果您已建立這些功能的網站，則不需要建立新的網路網站;其他的「高級 Enterprise 語音功能」會使用相同的網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-153">If you have already created network sites for one of these features, you do not need to create new network sites; other advanced Enterprise Voice features will use those same network sites.</span></span> <span data-ttu-id="ddc0e-154">不過，您可能需要修改現有網站定義，以便套用特定的功能設定。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-154">You may, however, need to modify an existing network site definition to apply feature-specific settings.</span></span> <span data-ttu-id="ddc0e-155">例如，如果已為 E9-1-1 建立了網站，在部署通話許可控制期間需要修改網站，以便套用頻寬原則設定檔。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-155">For example, if you created a network site for E9-1-1, you need to modify the network site during deployment of call admission control to apply a bandwidth policy profile.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ddc0e-156">使用商務用 Skype Server 管理命令介面建立網路網站</span><span class="sxs-lookup"><span data-stu-id="ddc0e-156">To create a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ddc0e-157">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-157">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddc0e-158">執行 New-CsNetworkSite Cmdlet 建立網站：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-158">Run the New-CsNetworkSite cmdlet to create network sites:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID <string>
   ```

    <span data-ttu-id="ddc0e-159">例如：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-159">For example:</span></span>

   ```powershell
   New-CsNetworkSite -NetworkSiteID Chicago -Description "Corporate headquarters"-NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="ddc0e-160">在此範例中，您已在「NorthAmerica」網路地區中建立名為 "芝加哥" 的網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-160">In this example, you created a network site called "Chicago" that is in the "NorthAmerica" network region.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddc0e-161">「北美地區」網路地區必須已經存在，此命令才能成功執行。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-161">The NorthAmerica network region must already exist for this command to run successfully.</span></span>

3. <span data-ttu-id="ddc0e-162">使用其他網站的設定重複執行步驟 2，完成建立拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-162">To finish creating network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-create-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ddc0e-163">使用商務用 Skype Server 控制台建立網路網站</span><span class="sxs-lookup"><span data-stu-id="ddc0e-163">To create a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ddc0e-164">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-164">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ddc0e-165">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-165">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ddc0e-166">按一下 **[站台]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-166">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="ddc0e-167">按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-167">Click **New**.</span></span>

5. <span data-ttu-id="ddc0e-168">在 **[新增站台]** 頁面上，按一下 **[名稱]**，然後為網站輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-168">On the **New Site** page, click **Name** and then type a name for the network site.</span></span>

6. <span data-ttu-id="ddc0e-169">按一下 **[地區]**，然後按一下清單中的地區。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-169">Click **Region**, and then click a region in the list.</span></span>

7. <span data-ttu-id="ddc0e-170">(選用) 按一下 **[頻寬原則]**，然後按一下清單中的頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-170">Optionally, click **Bandwidth policy**, and then click a bandwidth policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddc0e-171">如果您要在網站部署通話許可控制，才需要頻寬原則。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-171">Bandwidth policy is required only if you deploy call admission control at the site.</span></span>

8. <span data-ttu-id="ddc0e-172">(選用) 按一下 **[位置原則]**，然後按一下清單中的位置原則。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-172">Optionally, click **Location policy**, and then click a location policy in the list.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddc0e-173">如果您要在網站部署 E9-1-1，才需要位置原則。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-173">Location policy is required only if you deploy E9-1-1 at the site.</span></span>

9. <span data-ttu-id="ddc0e-174">(選用) 按一下 **[描述]**，然後輸入用來描述此網站的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-174">Optionally, click **Description**, and then type additional information to describe this network site.</span></span>

10. <span data-ttu-id="ddc0e-175">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-175">Click **Commit**.</span></span>

11. <span data-ttu-id="ddc0e-176">使用其他網站的設定重複執行步驟 4 至 10，完成建立拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-176">To finish creating network sites for your topology, repeat steps 4 through 10 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ddc0e-177">使用商務用 Skype Server 管理命令介面來修改網路網站</span><span class="sxs-lookup"><span data-stu-id="ddc0e-177">To modify a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ddc0e-178">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-178">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddc0e-179">執行 Set-CsNetworkSite Cmdlet 以修改網站：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-179">Run the Set-CsNetworkSite cmdlet to modify network sites:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity <string>
   ```

    <span data-ttu-id="ddc0e-180">例如：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-180">For example:</span></span>

   ```powershell
   Set-CsNetworkSite -Identity Albuquerque -NetworkRegionID NorthAmerica
   ```

    <span data-ttu-id="ddc0e-181">在此範例中，名為 "阿布奎基" 的網站會移至「NorthAmerica」網路地區。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-181">In this example, the site called "Albuquerque" is moved to the "NorthAmerica" network region.</span></span> <span data-ttu-id="ddc0e-182">若要修改網站設定以便部署通話許可控制、E9-1-1 或媒體旁路，請執行 Set-CsNetworkSite Cmdlet 並分別搭配 BWPolicyProfileID 或 LocationPolicy 參數，修改網站設定。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-182">To modify the network site configuration to deploy call admission control, E9-1-1, or media bypass, modify the network site settings by running the Set-CsNetworkSite cmdlet with the BWPolicyProfileID or LocationPolicy parameter, respectively.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddc0e-p110">媒體旁路還有一個 BypassID 參數，但強烈建議您不要覆寫自動產生的旁路 ID。為媒體旁路設定網站時，不需要指定其他參數。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-p110">Although the BypassID parameter exists for media bypass, we strongly recommend that you do not override automatically generated bypass IDs. You do not need to specify additional parameters to configure a network site for media bypass.</span></span>

3. <span data-ttu-id="ddc0e-185">使用其他網站的設定重複執行步驟 2，完成修改拓撲的網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-185">To finish modifying network sites for your topology, repeat step 2 with settings for other sites.</span></span>

### <a name="to-modify-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ddc0e-186">使用商務用 Skype Server 控制台修改網路網站</span><span class="sxs-lookup"><span data-stu-id="ddc0e-186">To modify a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ddc0e-187">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-187">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ddc0e-188">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-188">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ddc0e-189">按一下 **[站台]** 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-189">Click the **Site** navigation button.</span></span>

4. <span data-ttu-id="ddc0e-190">在表格中，按一下您要修改的網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-190">In the table, click the network site that you want to modify.</span></span>

5. <span data-ttu-id="ddc0e-191">按一下 **[編輯]**，然後按一下 **[顯示詳細資料...]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-191">Click **Edit**, and then click **Show details…**.</span></span>

6. <span data-ttu-id="ddc0e-192">在 [ **編輯網站** ] 頁面上，視需要變更此網路網站的設定值。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-192">On the **Edit Site** page, change the values for this network site's settings as appropriate.</span></span>

7. <span data-ttu-id="ddc0e-193">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-193">Click **Commit**.</span></span>

8. <span data-ttu-id="ddc0e-194">使用其他網站的設定重複執行步驟 4 至 7，完成修改網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-194">To finish modify network sites, repeat steps 4 through 7 with settings for other sites.</span></span>

## <a name="associate-a-subnet-with-a-network-site"></a><span data-ttu-id="ddc0e-195">建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="ddc0e-195">Associate a subnet with a network site</span></span>
<span data-ttu-id="ddc0e-196"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="ddc0e-196"><a name="BKMK_AssociateSubnets"> </a></span></span>

<span data-ttu-id="ddc0e-197">您網路中的每個子網都必須與特定網路網站產生關聯，因為子網資訊是用來決定端點所在的網路網站，而啟動新的會話時。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-197">Every subnet in your network must be associated with a specific network site, because subnet information is used to determine the network site on which an endpoint is located while a new session is initiated.</span></span> <span data-ttu-id="ddc0e-198">在會話中每一方的位置已知時，「高級 Enterprise 語音功能」可以套用該資訊，決定如何處理通話設定或路由傳送。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-198">When the location of each party in a session is known, advanced Enterprise Voice features can apply that information to determine how to handle the call setup or routing.</span></span>

<span data-ttu-id="ddc0e-199">您部署中 Audio/Video Edge Server 的所有已設定公用 IP 位址，都必須新增至您的網路設定。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-199">All configured public IP addresses of the Audio/Video Edge Servers in your deployment must be added to your network configuration settings.</span></span> <span data-ttu-id="ddc0e-200">這兩個 IP 位址會新增為遮罩為32的子網。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-200">These IP addresses are added as subnets with a mask of 32.</span></span> <span data-ttu-id="ddc0e-201">相關聯的網路網站應該對應至適當設定的網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-201">The associated network site should correspond to the appropriate configured network site.</span></span> <span data-ttu-id="ddc0e-202">例如，與中央網站芝加哥的 A/V Edge service 對應的公用 IP 位址，將會 NetworkSiteID 芝加哥。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-202">For example, the public IP address that corresponds to the A/V Edge service in central site Chicago would be NetworkSiteID Chicago.</span></span>

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ddc0e-203">使用商務用 Skype Server 管理命令介面建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="ddc0e-203">To associate a subnet with a network site by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ddc0e-204">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-204">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="ddc0e-205">執行 **New-CsNetworkSubnet** Cmdlet 以將子網與網路網站產生關聯：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-205">Run the **New-CsNetworkSubnet** cmdlet to associate a subnet with a network site:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID <String> -MaskBits <Int32> -NetworkSiteID <String>
   ```

    <span data-ttu-id="ddc0e-206">例如：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-206">For example:</span></span>

   ```powershell
   New-CsNetworkSubnet -SubnetID 172.11.12.13 - MaskBits 20 -NetworkSiteID Chicago
   ```

    <span data-ttu-id="ddc0e-207">在此範例中，您已建立子網172.11.12.13 與網路網站 "芝加哥" 之間的關聯性。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-207">In this example, you created an association between the subnet 172.11.12.13 and the network site "Chicago".</span></span>

3. <span data-ttu-id="ddc0e-208">對拓撲中的所有子網重複步驟2。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-208">Repeat step 2 for all subnets in your topology.</span></span>

### <a name="to-associate-subnets-with-network-sites-by-importing-a-csv-file"></a><span data-ttu-id="ddc0e-209">若要將子網與網站結合匯入 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="ddc0e-209">To associate subnets with network sites by importing a CSV file</span></span>

1. <span data-ttu-id="ddc0e-210">建立包含您要新增之所有子網的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-210">Create a CSV file that includes all of the subnets you want to add.</span></span> <span data-ttu-id="ddc0e-211">例如，使用下列內容建立名為 **subnet.csv** 的檔案：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-211">For example, create a file named **subnet.csv** with the following content:</span></span>

     `IPAddress, mask, description, NetworkSiteID`

     `172.11.12.0, 24, "NA:Subnet in Portland", Portland`

     `172.11.13.0, 24, "NA:Subnet in Reno", Reno`

     `172.11.14.0, 25, "EMEA:Subnet in Warsaw", Warsaw`

     `172.11.15.0, 31, "EMEA:Subnet in Paris", Paris`

2. <span data-ttu-id="ddc0e-212">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-212">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="ddc0e-213">執行下列 Cmdlet 以匯入 **subnet.csv**，然後將其內容儲存在 Lync Server management store 中：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-213">Run the following cmdlet to import **subnet.csv**, and then store its contents in the Lync Server management store:</span></span>

   ```powershell
   import-csv subnet.csv | foreach {New-CsNetworkSubnet -Identity $_.IPAddress -MaskBits $_.mask -Description $_.description -NetworkSiteID $_.NetworkSiteID}
   ```

### <a name="to-associate-a-subnet-with-a-network-site-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ddc0e-214">使用商務用 Skype Server 控制台建立子網與網路網站的關聯</span><span class="sxs-lookup"><span data-stu-id="ddc0e-214">To associate a subnet with a network site by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ddc0e-215">開啟商務用 Skype Server 控制台。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-215">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="ddc0e-216">在左導覽列中，按一下 **[網路組態]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-216">In the left navigation bar, click **Network Configuration**.</span></span>

3. <span data-ttu-id="ddc0e-217">按一下 [ **子網** ] 導覽按鈕。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-217">Click the **Subnet** navigation button.</span></span>

4. <span data-ttu-id="ddc0e-218">按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-218">Click **New**.</span></span>

5. <span data-ttu-id="ddc0e-219">在 [ **新建子網上** ] 頁面上，按一下 [ **子網識別碼**]，然後輸入您要與網路網站建立關聯之子網所定義之 IP 位址範圍中的第一個位址。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-219">On the **New Subnet** page, click **Subnet ID**, and then type the first address in the IP address range defined by the subnet you want to associate with a network site.</span></span>

6. <span data-ttu-id="ddc0e-220">按一下 [ **遮罩**]，然後輸入要套用至子網的位元遮罩。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-220">Click **Mask**, and then type the bitmask to apply to the subnet.</span></span>

7. <span data-ttu-id="ddc0e-221">按一下 [ **網路網站識別碼**]，然後選取您要新增此子網的網站的網站識別碼。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-221">Click **Network site ID**, and then select the site ID of the site to which you are adding this subnet.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ddc0e-222">如果您尚未建立網路網站，此清單將會是空的。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-222">If you have not yet created network sites, this list will be empty.</span></span> <span data-ttu-id="ddc0e-223">如需程式的詳細資訊，請參閱 [建立或修改網路網站](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site)。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-223">For details about the procedure, see [Create or Modify a Network Site](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-network-site).</span></span> <span data-ttu-id="ddc0e-224">您也可以執行 **Get-CsNetworkSite** Cmdlet，以取得部署的網站 IDs。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-224">You can also retrieve site IDs for your deployment by running the **Get-CsNetworkSite** cmdlet.</span></span> <span data-ttu-id="ddc0e-225">如需詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-225">For details, see the Skype for Business Server Management Shell documentation.</span></span>

8. <span data-ttu-id="ddc0e-226">（選用）按一下 [ **描述**]，然後輸入其他資訊以描述這個子網。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-226">Optionally, click **Description**, and then type additional information to describe this subnet.</span></span>

9. <span data-ttu-id="ddc0e-227">按一下 **[認可]**。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-227">Click **Commit**.</span></span>

<span data-ttu-id="ddc0e-228">重複這些步驟，將其他子網新增至網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-228">Repeat these steps to add other subnets to a network site.</span></span>
> [!NOTE]
> <span data-ttu-id="ddc0e-229">會引發重要狀態指示器 (KHI) 通知，指定存在於您的網路中，但未與子網路相關聯，或包含 IP 位址的子網路未與網站相關聯的 IP 位址清單。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-229">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="ddc0e-230">在8小時內，將不會多次引發此警示。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-230">This alert will not be raised more than once within an 8-hour period.</span></span>

<span data-ttu-id="ddc0e-231">以下是相關的通知資訊與範例：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-231">The relevant alert information and an example are as follows:</span></span>

 <span data-ttu-id="ddc0e-232">**來源**：CS 頻寬原則服務 (核心)</span><span class="sxs-lookup"><span data-stu-id="ddc0e-232">**Source**: CS Bandwidth Policy Service (Core)</span></span>

 <span data-ttu-id="ddc0e-233">**事件號碼**：36034</span><span class="sxs-lookup"><span data-stu-id="ddc0e-233">**Event number**: 36034</span></span>

 <span data-ttu-id="ddc0e-234">**層級**：2</span><span class="sxs-lookup"><span data-stu-id="ddc0e-234">**Level**: 2</span></span>

 <span data-ttu-id="ddc0e-235">**描述**：下列 IP 位址的子網： \<List of IP Addresses\> 未設定，或子網未與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-235">**Description**: The subnets for the following IP addresses: \<List of IP Addresses\> are either not configured or the subnets are not associated to a Network Site.</span></span>

 <span data-ttu-id="ddc0e-236">**原因**：網路組態設定中遺漏對應 IP 位址的子網路，或是子網路未與網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-236">**Cause**: The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span>

 <span data-ttu-id="ddc0e-237">**解決** 方式：將對應至 IP 位址清單的子網新增至網路設定設定，並將每個子網與網路網站產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-237">**Resolution**: Add subnets corresponding to the list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span>

<span data-ttu-id="ddc0e-238">例如，如果警示中的 IP 位址清單指定10.121.248.226 和10.121.249.20，則這些 IP 位址不會與子網產生關聯，或與其相關聯的子網不屬於網路網站。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-238">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet or the subnet they are associated with does not belong to a network site.</span></span> <span data-ttu-id="ddc0e-239">如果 10.121.248.0/24 與 10.121.249.0/24 是這些位址的對應子網路，您可以透過下列方式解決此問題：</span><span class="sxs-lookup"><span data-stu-id="ddc0e-239">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span>

1. <span data-ttu-id="ddc0e-240">確定 IP 位址 10.121.248.226 與 10.121.248.0/24 子網路相關聯，而 IP 位址 10.121.249.20 與 10.121.249.0/24 子網路相關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-240">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span>

2. <span data-ttu-id="ddc0e-241">確定 10.121.248.0/24 與 10.121.249.0/24 兩個子網路分別與一個網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="ddc0e-241">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddc0e-242">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ddc0e-242">See also</span></span>
<span data-ttu-id="ddc0e-243"><a name="BKMK_AssociateSubnets"> </a></span><span class="sxs-lookup"><span data-stu-id="ddc0e-243"><a name="BKMK_AssociateSubnets"> </a></span></span>


[<span data-ttu-id="ddc0e-244">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ddc0e-244">New-CsNetworkRegion</span></span>](/powershell/module/skype/new-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ddc0e-245">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ddc0e-245">Get-CsNetworkRegion</span></span>](/powershell/module/skype/get-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ddc0e-246">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ddc0e-246">Set-CsNetworkRegion</span></span>](/powershell/module/skype/set-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ddc0e-247">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="ddc0e-247">Remove-CsNetworkRegion</span></span>](/powershell/module/skype/remove-csnetworkregion?view=skype-ps)

[<span data-ttu-id="ddc0e-248">New-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ddc0e-248">New-CsNetworkSubnet</span></span>](/powershell/module/skype/new-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ddc0e-249">Get-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ddc0e-249">Get-CsNetworkSubnet</span></span>](/powershell/module/skype/get-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ddc0e-250">CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ddc0e-250">Set-CsNetworkSubnet</span></span>](/powershell/module/skype/set-csnetworksubnet?view=skype-ps)

[<span data-ttu-id="ddc0e-251">Remove-CsNetworkSubnet</span><span class="sxs-lookup"><span data-stu-id="ddc0e-251">Remove-CsNetworkSubnet</span></span>](/powershell/module/skype/remove-csnetworksubnet?view=skype-ps)