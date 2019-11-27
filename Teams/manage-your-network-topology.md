---
title: 在 Microsoft 團隊中管理雲端語音功能的網路拓撲
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1keywords: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何針對 Microsoft 團隊中的雲端語音功能設定網路設定。
ms.openlocfilehash: 72fb40b31b7881f550800bad5a2d2fca304431ae
ms.sourcegitcommit: 021c86bf579e315f15815dcddf232a0c651cbf6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615893"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a><span data-ttu-id="2a72e-103">在 Microsoft 團隊中管理雲端語音功能的網路拓撲</span><span class="sxs-lookup"><span data-stu-id="2a72e-103">Manage your network topology for cloud voice features in Microsoft Teams</span></span>

<span data-ttu-id="2a72e-104">如果您的組織要部署直接路由或[動態緊急通話](configure-dynamic-emergency-calling.md)[的位置路由](location-based-routing-plan.md)，您必須設定網路設定，以便與 Microsoft 團隊中的這些雲端語音功能搭配使用。</span><span class="sxs-lookup"><span data-stu-id="2a72e-104">If your organization is deploying [Location-Based Routing for Direct Routing](location-based-routing-plan.md) or [dynamic emergency calling](configure-dynamic-emergency-calling.md), you must configure network settings for use with these cloud voice features in Microsoft Teams.</span></span> <span data-ttu-id="2a72e-105">網路設定是用來判斷團隊用戶端的位置，包括網路區域、網路網站、子網及信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2a72e-105">Network settings are used to determine the location of a Teams client and include network regions, network sites, subnets, and trusted IP addresses.</span></span> <span data-ttu-id="2a72e-106">視您部署的雲端語音功能和功能而定，您可以設定部分或所有的設定。</span><span class="sxs-lookup"><span data-stu-id="2a72e-106">Depending on the cloud voice feature and capability that you're deploying, you configure some or all these settings.</span></span> <span data-ttu-id="2a72e-107">若要深入瞭解這些詞彙，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-107">To learn more about these terms, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="2a72e-108">您可以在 Microsoft 團隊系統管理中心的 [**網路拓撲**] 頁面或使用 Windows PowerShell 來設定網路設定。</span><span class="sxs-lookup"><span data-stu-id="2a72e-108">You configure network settings on the **Network topology** page of the Microsoft Teams admin center or by using Windows PowerShell.</span></span>

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2a72e-109">在 Microsoft 團隊系統管理中心設定網路設定</span><span class="sxs-lookup"><span data-stu-id="2a72e-109">Configure network settings in the Microsoft Teams admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="2a72e-110">您可以在 [**網路拓撲**] 頁面的 [**網路網站**] 索引標籤上定義網路區域、網路網站和子網。</span><span class="sxs-lookup"><span data-stu-id="2a72e-110">You define network regions, network sites, and subnets on the **Network sites** tab of the **Network topology** page.</span></span> <span data-ttu-id="2a72e-111">您可以在這裡建立或修改網路網站、將網站與網路區域建立關聯、將子網與網站建立關聯、開啟以位置為基礎的路由，以及將緊急原則指派給網站。</span><span class="sxs-lookup"><span data-stu-id="2a72e-111">Here, you can create or modify a network site, associate a site with a network region, associate a subnet to the site, turn on Location-based Routing, and assign emergency policies to the site.</span></span> <span data-ttu-id="2a72e-112">您也可以新增可全域用於所有網站的網路區域。</span><span class="sxs-lookup"><span data-stu-id="2a72e-112">You can also add network regions that can be used globally for all sites.</span></span>

#### <a name="add-and-configure-a-network-site"></a><span data-ttu-id="2a72e-113">新增及設定網路網站</span><span class="sxs-lookup"><span data-stu-id="2a72e-113">Add and configure a network site</span></span>

1. <span data-ttu-id="2a72e-114">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置** > **網路拓撲**]，然後按一下 [**網路網站**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a72e-114">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="2a72e-115">按一下 [**新增**]，然後輸入網站的名稱和描述。</span><span class="sxs-lookup"><span data-stu-id="2a72e-115">Click **New**, and then enter a name and description for the site.</span></span>

    ![[新增網路] 網站頁面的螢幕擷取畫面](media/manage-network-topology-add-site.png)

3. <span data-ttu-id="2a72e-117">若要將網站與網路區域建立關聯，請按一下 [**連結網路區域**]，選取現有的區域，或按一下 [**新增**] 以新增區域，然後按一下 [**連結**]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-117">To associate the site with a network region, click **Link network region**, select an existing region or click **Add** to add a region, and then click **Link**.</span></span>  
4. <span data-ttu-id="2a72e-118">若要啟用網站的位置路由，請開啟 [以位置為**基礎的路由**]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-118">To enable Location-Based Routing for the site, turn on **Location based routing**.</span></span>
5. <span data-ttu-id="2a72e-119">若要指派緊急服務原則至網站，請執行下列其中一項或兩項操作：</span><span class="sxs-lookup"><span data-stu-id="2a72e-119">To assign emergency services policies to the site, do one or both of the following:</span></span>

    - <span data-ttu-id="2a72e-120">如果您的組織使用的是通話方案或部署的電話系統直接路由，請在 [**緊急通話原則**] 底下，選取您要的原則。</span><span class="sxs-lookup"><span data-stu-id="2a72e-120">If your organization uses Calling Plans or deployed Phone System Direct Routing, under **Emergency calling policy**, select the policy that you want.</span></span>
    - <span data-ttu-id="2a72e-121">如果您的組織已部署 [電話系統直傳送]，請在 [**緊急呼叫路由策略**] 底下，選取您要的原則。</span><span class="sxs-lookup"><span data-stu-id="2a72e-121">If your organization deployed Phone System Direct Routing, under **Emergency call routing policy**, select the  policy that you want.</span></span>

6. <span data-ttu-id="2a72e-122">若要將子網與網站建立關聯，請按一下 [**子網**] 底下的 [**新增子網**]</span><span class="sxs-lookup"><span data-stu-id="2a72e-122">To associate a subnet to the site, under **Subnets**, click **Add subnets**.</span></span> <span data-ttu-id="2a72e-123">指定 [IP 版本]、[IP 位址]、[網路範圍]、[新增描述]，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-123">Specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span> <span data-ttu-id="2a72e-124">每個子網都必須與特定網站相關聯。</span><span class="sxs-lookup"><span data-stu-id="2a72e-124">Each subnet must be associated with a specific site.</span></span>
7. <span data-ttu-id="2a72e-125">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-125">Click **Save**.</span></span>

#### <a name="modify-a-network-site"></a><span data-ttu-id="2a72e-126">修改網路網站</span><span class="sxs-lookup"><span data-stu-id="2a72e-126">Modify a network site</span></span>

1. <span data-ttu-id="2a72e-127">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置** > **網路拓撲**]，然後按一下 [**網路網站**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a72e-127">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Network sites** tab.</span></span>
2. <span data-ttu-id="2a72e-128">按一下網站名稱左邊的，然後按一下 [**編輯**]，選取網站。</span><span class="sxs-lookup"><span data-stu-id="2a72e-128">Select the site by clicking to the left of the site name, and then click **Edit**.</span></span>
3. <span data-ttu-id="2a72e-129">進行您想要的變更，然後按一下 [**儲存]。**</span><span class="sxs-lookup"><span data-stu-id="2a72e-129">Make the changes that you want, and then click **Save.**</span></span>

### <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="2a72e-130">管理外部信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2a72e-130">Manage external trusted IP addresses</span></span>

<span data-ttu-id="2a72e-131">您可以在 Microsoft 團隊系統管理中心的 [**網路拓撲**] 頁面上的 [**信任**的 ip] 索引標籤上，管理外部信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="2a72e-131">You manage external trusted IP addresses on the **Trusted IPs** tab on the **Network topology** page of the Microsoft Teams admin center.</span></span> <span data-ttu-id="2a72e-132">您可以新增不受限制的外部信任 IP 位址數目。</span><span class="sxs-lookup"><span data-stu-id="2a72e-132">You can add an unlimited number of external trusted IP addresses.</span></span>

#### <a name="add-a-trusted-ip-address"></a><span data-ttu-id="2a72e-133">新增信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2a72e-133">Add a trusted IP address</span></span>

1. <span data-ttu-id="2a72e-134">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置** > **網路拓朴**]，然後按一下 [**信任的 IPs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a72e-134">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="2a72e-135">按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-135">Click **New**.</span></span>
3. <span data-ttu-id="2a72e-136">在 [**新增信任的 IP 位址**] 窗格中，指定 [ip 版本]、[ip 位址]、[網路範圍]、[新增描述]，**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-136">In the **Add trusted IP address** pane, specify the IP version, IP address, network range, add a description, and then click **Apply**.</span></span>

    ![[新增信任的 IP 位址] 窗格的螢幕擷取畫面](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a><span data-ttu-id="2a72e-138">編輯信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="2a72e-138">Edit a trusted IP address</span></span>

1. <span data-ttu-id="2a72e-139">在 Microsoft 團隊系統管理中心的左導覽中，移至 [**位置** > **網路拓朴**]，然後按一下 [**信任的 IPs** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a72e-139">In the left navigation of the Microsoft Teams admin center, go to **Locations** > **Network topology**, and then click the **Trusted IPs** tab.</span></span>
2. <span data-ttu-id="2a72e-140">按一下 IP 位址左邊的，然後按一下 [**編輯**] 來選取它。</span><span class="sxs-lookup"><span data-stu-id="2a72e-140">Select the IP address by clicking to the left of it, and then click **Edit**.</span></span>
3. <span data-ttu-id="2a72e-141">在 [**編輯信任的 IP 位址**] 窗格中，進行您要的變更，然後**按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="2a72e-141">In the **Edit trusted IP address** pane, make the changes that you want, and then click **Apply**.</span></span>

## <a name="configure-network-settings-using-powershell"></a><span data-ttu-id="2a72e-142">使用 PowerShell 設定網路設定</span><span class="sxs-lookup"><span data-stu-id="2a72e-142">Configure network settings using PowerShell</span></span>

<span data-ttu-id="2a72e-143">若要完成本節中的步驟，您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2a72e-143">To complete the steps in this section, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="2a72e-144">若要深入瞭解，請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-144">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="2a72e-145">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="2a72e-145">Define network regions</span></span>

 <span data-ttu-id="2a72e-146">使用[新的-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) Cmdlet 來定義網路區域。</span><span class="sxs-lookup"><span data-stu-id="2a72e-146">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) cmdlet to define network regions.</span></span> <span data-ttu-id="2a72e-147">請注意，RegionID 參數是代表區域地理位置的邏輯名稱，沒有相依性或限制，且 CentralSite &lt;site ID&gt;參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="2a72e-147">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="2a72e-148">在這個範例中，我們會建立一個名為「印度」的網路區域。</span><span class="sxs-lookup"><span data-stu-id="2a72e-148">In this example, we create a network region named India.</span></span>
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

<span data-ttu-id="2a72e-149">另請參閱[設定-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-149">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).</span></span>

### <a name="define-network-sites"></a><span data-ttu-id="2a72e-150">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="2a72e-150">Define network sites</span></span>

<span data-ttu-id="2a72e-151">使用[新的-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。</span><span class="sxs-lookup"><span data-stu-id="2a72e-151">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> <span data-ttu-id="2a72e-152">每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2a72e-152">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="2a72e-153">在這個範例中，我們會在印度區域中建立兩個新的網路網站、新德里與 Hyderabad。</span><span class="sxs-lookup"><span data-stu-id="2a72e-153">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span>
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```
<span data-ttu-id="2a72e-154">下表顯示在這個範例中定義的網路網站。</span><span class="sxs-lookup"><span data-stu-id="2a72e-154">The following table shows the network sites defined in this example.</span></span>

||<span data-ttu-id="2a72e-155">網站1</span><span class="sxs-lookup"><span data-stu-id="2a72e-155">Site 1</span></span> |<span data-ttu-id="2a72e-156">網站2</span><span class="sxs-lookup"><span data-stu-id="2a72e-156">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2a72e-157">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="2a72e-157">Site ID</span></span>    |    <span data-ttu-id="2a72e-158">Site 1 （新德里）</span><span class="sxs-lookup"><span data-stu-id="2a72e-158">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="2a72e-159">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="2a72e-159">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="2a72e-160">地區識別碼</span><span class="sxs-lookup"><span data-stu-id="2a72e-160">Region ID</span></span>  |     <span data-ttu-id="2a72e-161">地區1（印度）</span><span class="sxs-lookup"><span data-stu-id="2a72e-161">Region 1 (India)</span></span>    |   <span data-ttu-id="2a72e-162">地區1（印度）</span><span class="sxs-lookup"><span data-stu-id="2a72e-162">Region 1 (India)</span></span>      |

<span data-ttu-id="2a72e-163">另請參閱[設定-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-163">See also [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).</span></span>

### <a name="define-network-subnets"></a><span data-ttu-id="2a72e-164">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="2a72e-164">Define network subnets</span></span>

<span data-ttu-id="2a72e-165">使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 來定義網路子網，並將它們與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2a72e-165">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="2a72e-166">每個網路子網只能與一個網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2a72e-166">Each network subnet can only be associated with one site.</span></span>

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="2a72e-167">在這個範例中，我們會在子網192.168.0.0 與新德里 network 網站之間以及子網2001之間建立關聯：4898： e8：25：844e：926f：85ad： dd8e 和 Hyderabad 網路網站。</span><span class="sxs-lookup"><span data-stu-id="2a72e-167">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```

New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"

```
<span data-ttu-id="2a72e-168">下表顯示在這個範例中定義的子網。</span><span class="sxs-lookup"><span data-stu-id="2a72e-168">The following table shows the subnets defined in this example.</span></span>

||<span data-ttu-id="2a72e-169">網站1</span><span class="sxs-lookup"><span data-stu-id="2a72e-169">Site 1</span></span> |<span data-ttu-id="2a72e-170">網站2</span><span class="sxs-lookup"><span data-stu-id="2a72e-170">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="2a72e-171">子網識別碼</span><span class="sxs-lookup"><span data-stu-id="2a72e-171">Subnet ID</span></span>   |    <span data-ttu-id="2a72e-172">含</span><span class="sxs-lookup"><span data-stu-id="2a72e-172">192.168.0.0</span></span>     |  <span data-ttu-id="2a72e-173">2001：4898： e8：25：844e：926f：85ad： dd8e</span><span class="sxs-lookup"><span data-stu-id="2a72e-173">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="2a72e-174">遮罩</span><span class="sxs-lookup"><span data-stu-id="2a72e-174">Mask</span></span>  |     <span data-ttu-id="2a72e-175">24</span><span class="sxs-lookup"><span data-stu-id="2a72e-175">24</span></span>    |   <span data-ttu-id="2a72e-176">120</span><span class="sxs-lookup"><span data-stu-id="2a72e-176">120</span></span>      |
|<span data-ttu-id="2a72e-177">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="2a72e-177">Site ID</span></span>  | <span data-ttu-id="2a72e-178">Site （新德里）</span><span class="sxs-lookup"><span data-stu-id="2a72e-178">Site (Delhi)</span></span> | <span data-ttu-id="2a72e-179">Site 2 （Hyderabad）</span><span class="sxs-lookup"><span data-stu-id="2a72e-179">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="2a72e-180">針對多個子網，您可以使用如下的腳本匯入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="2a72e-180">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="2a72e-181">在這個範例中，CSV 檔案看起來像這樣：</span><span class="sxs-lookup"><span data-stu-id="2a72e-181">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

<span data-ttu-id="2a72e-182">另請參閱[設定-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-182">See also [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).</span></span>

### <a name="define-external-subnets-external-trusted-ip-addresses"></a><span data-ttu-id="2a72e-183">定義外部子網（外部信任的 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="2a72e-183">Define external subnets (external trusted IP addresses)</span></span>

<span data-ttu-id="2a72e-184">使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Cmdlet 來定義外部子網，並將其指派給租使用者。</span><span class="sxs-lookup"><span data-stu-id="2a72e-184">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="2a72e-185">您可以為租使用者定義不受限制的外部子網數。</span><span class="sxs-lookup"><span data-stu-id="2a72e-185">You can define an unlimited number of external subnets for a tenant.</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="2a72e-186">例如：</span><span class="sxs-lookup"><span data-stu-id="2a72e-186">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

<span data-ttu-id="2a72e-187">另請參閱[設定-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)。</span><span class="sxs-lookup"><span data-stu-id="2a72e-187">See also [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a72e-188">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a72e-188">Related topics</span></span>

- [<span data-ttu-id="2a72e-189">小組中雲端語音功能的網路設定</span><span class="sxs-lookup"><span data-stu-id="2a72e-189">Network settings for cloud voice features in Teams</span></span>](cloud-voice-network-settings.md)
