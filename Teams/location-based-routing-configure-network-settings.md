---
title: 設定以位置為基礎的路由的網路設定
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何針對直接路由建立及設定以位置為基礎的路由的網路區域、網站和子網。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7f6f6f1e74cc50b37ade03e97106d2befe36a6dd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245103"
---
# <a name="configure-network-settings-for-location-based-routing"></a><span data-ttu-id="79b1b-103">設定以位置為基礎的路由的網路設定</span><span class="sxs-lookup"><span data-stu-id="79b1b-103">Configure network settings for Location-Based Routing</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

<span data-ttu-id="79b1b-104">如果您尚未這麼做, 請參閱[直接路由的 [規劃位置] 路由](location-based-routing-plan.md), 以查看在設定位置式路由的網路設定之前, 您必須採取的其他步驟。</span><span class="sxs-lookup"><span data-stu-id="79b1b-104">If you haven't already done so, read [Plan Location-Based Routing for Direct Routing](location-based-routing-plan.md) to review other steps you'll need to take before you configure network settings for Location-Based Routing.</span></span>

<span data-ttu-id="79b1b-105">本文說明如何設定以位置為基礎的路由的網路設定。</span><span class="sxs-lookup"><span data-stu-id="79b1b-105">This article describes how to configure network settings for Location-Based Routing.</span></span> <span data-ttu-id="79b1b-106">在貴組織中部署手機系統直接路由之後, 接下來的步驟是建立及設定網路區域、網路網站和網路子網。</span><span class="sxs-lookup"><span data-stu-id="79b1b-106">After you deploy Phone System Direct Routing in your organization, the next steps are to create and set up network regions, network sites, and network subnets.</span></span> <span data-ttu-id="79b1b-107">若要完成本文中的步驟, 您需要熟悉 PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="79b1b-107">To complete the steps in this article, you'll need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="79b1b-108">若要深入瞭解, 請參閱[團隊 PowerShell 概覽](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="79b1b-108">To learn more, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

## <a name="define-network-regions"></a><span data-ttu-id="79b1b-109">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="79b1b-109">Define network regions</span></span>
 <span data-ttu-id="79b1b-110">網路區域跨多個地理區域互連網路的各個部分。</span><span class="sxs-lookup"><span data-stu-id="79b1b-110">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="79b1b-111">使用[新的-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) Cmdlet 來定義網路區域。</span><span class="sxs-lookup"><span data-stu-id="79b1b-111">Use the [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion?view=skype-ps) cmdlet to define network regions.</span></span> <span data-ttu-id="79b1b-112">請注意, RegionID 參數是代表區域地理位置的邏輯名稱, 沒有相依性或限制, 且 CentralSite &lt;site ID&gt;參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="79b1b-112">Note that the RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions and the CentralSite &lt;site ID&gt; parameter is optional.</span></span> 

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="79b1b-113">在這個範例中, 我們會建立一個名為「印度」的網路區域。</span><span class="sxs-lookup"><span data-stu-id="79b1b-113">In this example, we create a network region named India.</span></span> 
```
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

## <a name="define-network-sites"></a><span data-ttu-id="79b1b-114">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="79b1b-114">Define network sites</span></span>

<span data-ttu-id="79b1b-115">使用[新的-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Cmdlet 來定義網路網站。</span><span class="sxs-lookup"><span data-stu-id="79b1b-115">Use the [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) cmdlet to define network sites.</span></span> 

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```
<span data-ttu-id="79b1b-116">在這個範例中, 我們會在印度區域中建立兩個新的網路網站、新德里與 Hyderabad。</span><span class="sxs-lookup"><span data-stu-id="79b1b-116">In this example, we create two new network sites, Delhi and Hyderabad, in the India region.</span></span> 
```
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India" 
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India" 
```
<span data-ttu-id="79b1b-117">下表顯示在這個範例中定義的網路網站。</span><span class="sxs-lookup"><span data-stu-id="79b1b-117">The following table shows the network sites defined in this example.</span></span> 

||<span data-ttu-id="79b1b-118">網站1</span><span class="sxs-lookup"><span data-stu-id="79b1b-118">Site 1</span></span> |<span data-ttu-id="79b1b-119">網站2</span><span class="sxs-lookup"><span data-stu-id="79b1b-119">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="79b1b-120">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="79b1b-120">Site ID</span></span>    |    <span data-ttu-id="79b1b-121">Site 1 (新德里)</span><span class="sxs-lookup"><span data-stu-id="79b1b-121">Site 1 (Delhi)</span></span>     |  <span data-ttu-id="79b1b-122">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79b1b-122">Site 2 (Hyderabad)</span></span>       |
|<span data-ttu-id="79b1b-123">地區識別碼</span><span class="sxs-lookup"><span data-stu-id="79b1b-123">Region ID</span></span>  |     <span data-ttu-id="79b1b-124">地區 1 (印度)</span><span class="sxs-lookup"><span data-stu-id="79b1b-124">Region 1 (India)</span></span>    |   <span data-ttu-id="79b1b-125">地區 1 (印度)</span><span class="sxs-lookup"><span data-stu-id="79b1b-125">Region 1 (India)</span></span>      |

## <a name="define-network-subnets"></a><span data-ttu-id="79b1b-126">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="79b1b-126">Define network subnets</span></span>

<span data-ttu-id="79b1b-127">使用[CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) Cmdlet 來定義網路子網, 並將它們與網路網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="79b1b-127">Use the [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) cmdlet to define network subnets and associate them to network sites.</span></span> <span data-ttu-id="79b1b-128">每個內部子網只能與一個網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="79b1b-128">Each internal subnet can only be associated with one site.</span></span> 
```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID> 
```
<span data-ttu-id="79b1b-129">在這個範例中, 我們會在子網192.168.0.0 與新德里 network 網站之間以及子網2001之間建立關聯: 4898: e8:25: 844e: 926f: 85ad: dd8e 和 Hyderabad 網路網站。</span><span class="sxs-lookup"><span data-stu-id="79b1b-129">In this example, we create an association between subnet 192.168.0.0 and the Delhi network site and between subnet 2001:4898:e8:25:844e:926f:85ad:dd8e and the Hyderabad network site.</span></span>
```
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi" 
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad" 
```
<span data-ttu-id="79b1b-130">下表顯示在這個範例中定義的子網。</span><span class="sxs-lookup"><span data-stu-id="79b1b-130">The following table shows the subnets defined in this example.</span></span> 

||<span data-ttu-id="79b1b-131">網站1</span><span class="sxs-lookup"><span data-stu-id="79b1b-131">Site 1</span></span> |<span data-ttu-id="79b1b-132">網站2</span><span class="sxs-lookup"><span data-stu-id="79b1b-132">Site 2</span></span> |
|---------|---------|---------|
|<span data-ttu-id="79b1b-133">子網識別碼</span><span class="sxs-lookup"><span data-stu-id="79b1b-133">Subnet ID</span></span>   |    <span data-ttu-id="79b1b-134">含</span><span class="sxs-lookup"><span data-stu-id="79b1b-134">192.168.0.0</span></span>     |  <span data-ttu-id="79b1b-135">2001: 4898: e8:25: 844e: 926f: 85ad: dd8e</span><span class="sxs-lookup"><span data-stu-id="79b1b-135">2001:4898:e8:25:844e:926f:85ad:dd8e</span></span>     |
|<span data-ttu-id="79b1b-136">遮罩</span><span class="sxs-lookup"><span data-stu-id="79b1b-136">Mask</span></span>  |     <span data-ttu-id="79b1b-137">24</span><span class="sxs-lookup"><span data-stu-id="79b1b-137">24</span></span>    |   <span data-ttu-id="79b1b-138">120</span><span class="sxs-lookup"><span data-stu-id="79b1b-138">120</span></span>      |
|<span data-ttu-id="79b1b-139">網站識別碼</span><span class="sxs-lookup"><span data-stu-id="79b1b-139">Site ID</span></span>  | <span data-ttu-id="79b1b-140">Site (新德里)</span><span class="sxs-lookup"><span data-stu-id="79b1b-140">Site (Delhi)</span></span> | <span data-ttu-id="79b1b-141">Site 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="79b1b-141">Site 2 (Hyderabad)</span></span> |

<span data-ttu-id="79b1b-142">針對多個子網, 您可以使用如下的腳本匯入 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="79b1b-142">For multiple subnets, you can import a CSV file by using a script such as the following.</span></span>
```
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```
<span data-ttu-id="79b1b-143">在這個範例中, CSV 檔案看起來像這樣:</span><span class="sxs-lookup"><span data-stu-id="79b1b-143">In this example, the CSV file looks something like this:</span></span>
```
Identity, Mask, SiteID 
172.11.12.0, 24, Redmond 
172.11.13.0, 24, Chicago 
172.11.14.0, 25, Vancouver 
172.11.15.0, 28, Paris
```
## <a name="define-external-subnets"></a><span data-ttu-id="79b1b-144">定義外部子網</span><span class="sxs-lookup"><span data-stu-id="79b1b-144">Define external subnets</span></span>
<span data-ttu-id="79b1b-145">使用[CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Cmdlet 來定義外部子網, 並將其指派給租使用者。</span><span class="sxs-lookup"><span data-stu-id="79b1b-145">Use the [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) cmdlet to define external subnets and assign them to the tenant.</span></span> <span data-ttu-id="79b1b-146">您可以為租使用者定義不受限制的子網數。</span><span class="sxs-lookup"><span data-stu-id="79b1b-146">You can define an unlimited number of subnets for a tenant.</span></span> 
```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```
<span data-ttu-id="79b1b-147">例如：</span><span class="sxs-lookup"><span data-stu-id="79b1b-147">For example:</span></span>
```
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

## <a name="next-steps"></a><span data-ttu-id="79b1b-148">後續步驟</span><span class="sxs-lookup"><span data-stu-id="79b1b-148">Next steps</span></span>
<span data-ttu-id="79b1b-149">移至 [[啟用直接路由的以位置為基礎的路由](location-based-routing-enable.md)]。</span><span class="sxs-lookup"><span data-stu-id="79b1b-149">Go to [Enable Location-Based Routing for Direct Routing](location-based-routing-enable.md).</span></span>

### <a name="related-topics"></a><span data-ttu-id="79b1b-150">相關主題</span><span class="sxs-lookup"><span data-stu-id="79b1b-150">Related topics</span></span>
- [<span data-ttu-id="79b1b-151">規劃直接路由的以位置為基礎的路由</span><span class="sxs-lookup"><span data-stu-id="79b1b-151">Plan Location-Based Routing for Direct Routing</span></span>](location-based-routing-plan.md)
- [<span data-ttu-id="79b1b-152">以位置為基礎的路由術語</span><span class="sxs-lookup"><span data-stu-id="79b1b-152">Location-Based Routing terminology</span></span>](location-based-routing-terminology.md)
