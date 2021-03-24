---
title: 在 Microsoft Teams 中管理雲端語音功能的網路拓撲
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中設定雲端語音功能的網路設定。
ms.openlocfilehash: c77f1e6d31953ce529bff1fab6aa16e1d889e29f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101059"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="03ae0-103">在 Microsoft Teams 中管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="03ae0-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="03ae0-104">如果貴組織正在部署直接[](location-based-routing-plan.md)路由或動態緊急通話的以位置[](configure-dynamic-emergency-calling.md)為基礎的路由，您必須設定網路設定，以在 Microsoft Teams 中使用這些雲端語音功能。</span><span class="sxs-lookup"><span data-stu-id="03ae0-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="03ae0-105">網路設定可用來判斷 Teams 用戶端的位置，並包含網路區域、網路網站、子網和受信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="03ae0-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="03ae0-106">根據您部署的雲端語音功能，您可以設定部分或所有設定。</span><span class="sxs-lookup"><span data-stu-id="03ae0-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="03ae0-107">若要深入瞭解這些條款，請參閱雲端 [語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="03ae0-108">您可以在 Microsoft Teams 系統管理中心的網路 **拓撲** 頁面上，或使用 Windows PowerShell 設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="03ae0-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="03ae0-109">在 Microsoft Teams 系統管理中心設定網路設定</span><span class="sxs-lookup"><span data-stu-id="03ae0-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="03ae0-110">您可以在網路拓撲頁面的網路網站選項卡上定義網路區域、網路 **網站\*\*\*\*和** 子網。</span><span class="sxs-lookup"><span data-stu-id="03ae0-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="03ae0-111">您可以在這裡建立或修改網路網站、將網站與網路區域建立關聯、將子網與網站建立關聯、開啟位置式路由，以及指派緊急策略至網站。</span><span class="sxs-lookup"><span data-stu-id="03ae0-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="03ae0-112">您也可以新增可全域用於所有網站的網路區域。</span><span class="sxs-lookup"><span data-stu-id="03ae0-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="03ae0-113">新增及設定網路網站</span><span class="sxs-lookup"><span data-stu-id="03ae0-113">Add and configure a network site</span></span>

1. <span data-ttu-id="03ae0-114">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **[** 位置網路拓撲圖》，然後按一下 [  >  \*\*\*\*\*\*網路網站> 定位\*\* 點。</span><span class="sxs-lookup"><span data-stu-id="03ae0-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="03ae0-115">按一下 **[新增**」，然後輸入網站的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="03ae0-115">Click **Add**, and then enter a name and description for the site.</span></span>

    ![新增網路網站頁面的螢幕擷取畫面](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="03ae0-117">若要將網站與網路區域建立關聯，請按一下[新增網路區域，選取現有區域或按一下 [新增以新增區域，然後按一下 **[連結**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-117">To associate the site with a network region, click **Add network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="03ae0-118">若要啟用Location-Based路由，請開啟 **以位置為基礎的路由**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="03ae0-119">若要將緊急服務政策指派給網站，請執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="03ae0-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="03ae0-120">如果貴組織使用通話方案或部署的電話系統直接路由，請在緊急通話政策下，選取您想要的策略。</span><span class="sxs-lookup"><span data-stu-id="03ae0-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="03ae0-121">如果貴組織已部署電話系統直接路由，請在 **緊急通話路由** 策略下，選取您想要的策略。</span><span class="sxs-lookup"><span data-stu-id="03ae0-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="03ae0-122">若要將子網與網站關聯，請按一下 [ **子網>** 下的 [ **新增子網>**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="03ae0-123">指定 IP 版本、IP 位址、網路範圍、新增描述，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="03ae0-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="03ae0-124">每個子網都必須與特定網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="03ae0-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="03ae0-125">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="03ae0-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="03ae0-126">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="03ae0-126">Modify a network site</span></span>

1. <span data-ttu-id="03ae0-127">在 Microsoft Teams 系統管理中心的左側流覽中，前往 **[** 位置網路拓撲圖》，然後按一下 [  >  \*\*\*\*\*\*網路網站> 定位\*\* 點。</span><span class="sxs-lookup"><span data-stu-id="03ae0-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="03ae0-128">按一下網站名稱的左側以選取網站，然後按一下 [ **編輯**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="03ae0-129">進行您想要的變更，然後按一下 [ **儲存。**</span><span class="sxs-lookup"><span data-stu-id="03ae0-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="03ae0-130">管理外部信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="03ae0-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="03ae0-131">您可以在 Microsoft Teams 系統管理中心的網路拓撲頁面上的信任 **IP** 標籤上管理外部信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="03ae0-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="03ae0-132">您可以新增無限數量的外部信任 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="03ae0-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="03ae0-133">新增信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="03ae0-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="03ae0-134">在 Microsoft Teams 系統管理中心的左側導航中，前往 [位置網路拓撲圖》，  >  然後按一下 [**信任的 IP？**</span><span class="sxs-lookup"><span data-stu-id="03ae0-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="03ae0-135">按一下 **[新增**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-135">Click **New**.</span></span>
3. <span data-ttu-id="03ae0-136">在 [**新增信任的 IP 位址**> 窗格中，指定 IP 版本、IP 位址、網路範圍、新增描述，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="03ae0-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![新增信任 IP 位址窗格的螢幕擷取畫面](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="03ae0-138">編輯信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="03ae0-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="03ae0-139">在 Microsoft Teams 系統管理中心的左側導航中，前往 [位置網路拓撲圖》，然後按一下 [  >  \*\*\*\*\*\*信任的 IP？\*\*</span><span class="sxs-lookup"><span data-stu-id="03ae0-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="03ae0-140">按一下 IP 位址的左側，然後按一下 [編輯>，以 **選取該 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="03ae0-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="03ae0-141">在 [**編輯信任的 IP 位址** 窗格， 進行您想要的變更，然後按一下 **[Apply.**</span><span class="sxs-lookup"><span data-stu-id="03ae0-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="03ae0-142">使用 PowerShell 設定網路設定</span><span class="sxs-lookup"><span data-stu-id="03ae0-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="03ae0-143">若要完成本節中的步驟，您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="03ae0-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="03ae0-144">若要深入瞭解，請參閱 [Teams PowerShell 概觀](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="03ae0-145">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="03ae0-145">Define network regions</span></span>

 <span data-ttu-id="03ae0-146">使用 [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) Cmdlet 來定義網路區域。</span><span class="sxs-lookup"><span data-stu-id="03ae0-146">Use the [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="03ae0-147">請注意，RegionID 參數是一個邏輯名稱，代表地區的地理位置，而且沒有相依性或限制，而 CentralSite &lt; 網站識別碼參數 &gt; 是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="03ae0-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="03ae0-148">在此範例中，我們建立名為 India 的網路區域。</span><span class="sxs-lookup"><span data-stu-id="03ae0-148">In this example, we create a network region named India.</span></span>

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="03ae0-149">另請參閱 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-149">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="03ae0-150">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="03ae0-150">Define network sites</span></span>

<span data-ttu-id="03ae0-151">使用 [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。</span><span class="sxs-lookup"><span data-stu-id="03ae0-151">Use the [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="03ae0-152">每個網路網站都必須與網路區域相關聯。</span><span class="sxs-lookup"><span data-stu-id="03ae0-152">Each network site must be associated with a network region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="03ae0-153">在此範例中，我們在印度地區建立兩個新的網路網站，即印度地區的印度和海德拉巴。</span><span class="sxs-lookup"><span data-stu-id="03ae0-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

<span data-ttu-id="03ae0-154">下表顯示在此範例中定義的網路網站。</span><span class="sxs-lookup"><span data-stu-id="03ae0-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="03ae0-155">網站 1</span><span class="sxs-lookup"><span data-stu-id="03ae0-155">Site 1</span></span> |<span data-ttu-id="03ae0-156">網站 2</span><span class="sxs-lookup"><span data-stu-id="03ae0-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="03ae0-157">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="03ae0-157">Site ID</span></span>    |    <span data-ttu-id="03ae0-158">第 1 (裡) </span><span class="sxs-lookup"><span data-stu-id="03ae0-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="03ae0-159">網站 2 (海德拉巴) </span><span class="sxs-lookup"><span data-stu-id="03ae0-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="03ae0-160">地區識別碼</span><span class="sxs-lookup"><span data-stu-id="03ae0-160">Region ID</span></span>  |     <span data-ttu-id="03ae0-161">印度地區 1 () </span><span class="sxs-lookup"><span data-stu-id="03ae0-161">Region 1 (India)</span></span>    |   <span data-ttu-id="03ae0-162">印度地區 1 () </span><span class="sxs-lookup"><span data-stu-id="03ae0-162">Region 1 (India)</span></span>      |

<span data-ttu-id="03ae0-163">另請參閱 [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-163">See also [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="03ae0-164">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="03ae0-164">Define network subnets</span></span>

<span data-ttu-id="03ae0-165">使用 [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 定義網路子網，並將其與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="03ae0-165">Use the [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="03ae0-166">每個網路子網只能與一個網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="03ae0-166">Each network subnet can only be associated with one site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="03ae0-167">在此範例中，我們建立子網 192.168.0.0 與Deri 網路網站之間的關聯，以及子網 2001：4898：e8：25：844e：926f：85ad：dd8e 和 Hyderabad 網路網站之間的關聯。</span><span class="sxs-lookup"><span data-stu-id="03ae0-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

<span data-ttu-id="03ae0-168">下表顯示此範例中定義的子網。</span><span class="sxs-lookup"><span data-stu-id="03ae0-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="03ae0-169">網站 1</span><span class="sxs-lookup"><span data-stu-id="03ae0-169">Site 1</span></span> |<span data-ttu-id="03ae0-170">網站 2</span><span class="sxs-lookup"><span data-stu-id="03ae0-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="03ae0-171">子網識別碼</span><span class="sxs-lookup"><span data-stu-id="03ae0-171">Subnet ID</span></span>   |    <span data-ttu-id="03ae0-172">192.168.0.0</span><span class="sxs-lookup"><span data-stu-id="03ae0-172">192.168.0.0</span></span>     |  <span data-ttu-id="03ae0-173">2001：4898：e8：25：844e：926f：85ad：dd8e</span><span class="sxs-lookup"><span data-stu-id="03ae0-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="03ae0-174">面具</span><span class="sxs-lookup"><span data-stu-id="03ae0-174">Mask</span></span>  |     <span data-ttu-id="03ae0-175">24</span><span class="sxs-lookup"><span data-stu-id="03ae0-175">24</span></span>    |   <span data-ttu-id="03ae0-176">120</span><span class="sxs-lookup"><span data-stu-id="03ae0-176">120</span></span>      |
|<span data-ttu-id="03ae0-177">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="03ae0-177">Site ID</span></span>  | <span data-ttu-id="03ae0-178">在 (裡) </span><span class="sxs-lookup"><span data-stu-id="03ae0-178">Site (Delhi)</span></span> | <span data-ttu-id="03ae0-179">網站 2 (海德拉巴) </span><span class="sxs-lookup"><span data-stu-id="03ae0-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="03ae0-180">對於多個子網，您可以使用下列腳本來輸入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="03ae0-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

<span data-ttu-id="03ae0-181">在此範例中，CSV 檔案看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="03ae0-181">In this example, the CSV file looks something like this:</span></span>

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


<span data-ttu-id="03ae0-182">另請參閱 [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-182">See also [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).</span></span>


### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="03ae0-183">定義外部子網 (信任的 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="03ae0-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="03ae0-184">使用 [New-CsTenantTrustedIPAddress Cmdlet](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) 來定義外部子網，並將其指派給租使用者。</span><span class="sxs-lookup"><span data-stu-id="03ae0-184">Use the [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="03ae0-185">您可以為租使用者定義無限數量的外部子網。</span><span class="sxs-lookup"><span data-stu-id="03ae0-185">You can define an unlimited number of external subnets for a tenant.</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

<span data-ttu-id="03ae0-186">例如：</span><span class="sxs-lookup"><span data-stu-id="03ae0-186">For example:</span></span>

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="03ae0-187">另請參閱 [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress)。</span><span class="sxs-lookup"><span data-stu-id="03ae0-187">See also [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="03ae0-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="03ae0-188">Related topics</span></span>

- [<span data-ttu-id="03ae0-189">Teams 中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="03ae0-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
