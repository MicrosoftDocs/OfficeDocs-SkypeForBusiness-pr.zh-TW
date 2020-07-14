---
title: 直接路由本機媒體優化
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: 針對直接路由設定本機媒體優化
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121603"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="5f6b5-103">針對直接路由設定本機媒體優化</span><span class="sxs-lookup"><span data-stu-id="5f6b5-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="5f6b5-104">本機媒體優化的設定是以其他雲端語音功能（例如位置式路由和動態緊急通話）通用的網路設定為基礎。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="5f6b5-105">若要深入瞭解網路區域、網路網站、網路子網和信任的 IP 位址，請參閱[雲端語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="5f6b5-106">在您設定本機媒體優化之前，請參閱[直接路由的本機媒體優化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="5f6b5-107">若要設定本機媒體優化，必須執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="5f6b5-108">您可以使用 [團隊系統管理中心] 或 [PowerShell]。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="5f6b5-109">如需詳細資訊，請參閱[管理您的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="5f6b5-110">設定使用者和 SBC 網站（如本文所述）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="5f6b5-111">針對本機媒體優化設定 SBCs （視您的 SBC 供應商規格而有所不同）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="5f6b5-112">下圖顯示本文範例中所用的網路設定。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="5f6b5-113">![顯示網路設定範例的圖表](media/direct-routing-media-op-9.png "網路設定範例")</span><span class="sxs-lookup"><span data-stu-id="5f6b5-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="5f6b5-114">設定使用者和 SBC 網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="5f6b5-115">若要設定使用者與 SBC 網站，您將需要：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="5f6b5-116">[管理外部信任的 IP 位址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="5f6b5-117">您可以設定網路區域、網路網站和網路子網，以[定義網路拓撲](#define-the-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="5f6b5-118">將 SBC （s）指派給具有相關模式和 proxy SBC 值的網站，以[定義虛擬網路拓撲](#define-the-virtual-network-topology)。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="5f6b5-119">根據 SBC 廠商的規格，設定用於本機媒體優化的 SBC （s）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="5f6b5-120">本文將說明 Microsoft 元件的配置。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="5f6b5-121">如需 SBC 設定的相關資訊，請參閱您的 SBC 供應商檔。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="5f6b5-122">下列 SBC 廠商支援本機媒體優化：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="5f6b5-123">那裡</span><span class="sxs-lookup"><span data-stu-id="5f6b5-123">Vendor</span></span> | <span data-ttu-id="5f6b5-124">產品</span><span class="sxs-lookup"><span data-stu-id="5f6b5-124">Product</span></span> |    <span data-ttu-id="5f6b5-125">軟體版本</span><span class="sxs-lookup"><span data-stu-id="5f6b5-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="5f6b5-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="5f6b5-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="5f6b5-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="5f6b5-128">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="5f6b5-130">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="5f6b5-132">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="5f6b5-134">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="5f6b5-136">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="5f6b5-138">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-139">Mediant 虛擬版 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="5f6b5-140">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5f6b5-141">Mediant 雲端版 SBC</span><span class="sxs-lookup"><span data-stu-id="5f6b5-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="5f6b5-142">7.20 （256）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-142">7.20A.256</span></span> |
| [<span data-ttu-id="5f6b5-143">功能區 SBC 核心</span><span class="sxs-lookup"><span data-stu-id="5f6b5-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="5f6b5-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="5f6b5-144">SBC 5110</span></span>         | <span data-ttu-id="5f6b5-145">8.2</span><span class="sxs-lookup"><span data-stu-id="5f6b5-145">8.2</span></span>  |
|            |  <span data-ttu-id="5f6b5-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="5f6b5-146">SBC 5210</span></span>         | <span data-ttu-id="5f6b5-147">8.2</span><span class="sxs-lookup"><span data-stu-id="5f6b5-147">8.2</span></span>  |
|            |  <span data-ttu-id="5f6b5-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="5f6b5-148">SBC 5400</span></span>         | <span data-ttu-id="5f6b5-149">8.2</span><span class="sxs-lookup"><span data-stu-id="5f6b5-149">8.2</span></span>  |
|            |  <span data-ttu-id="5f6b5-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="5f6b5-150">SBC 7000</span></span>         | <span data-ttu-id="5f6b5-151">8.2</span><span class="sxs-lookup"><span data-stu-id="5f6b5-151">8.2</span></span>  |
|            |  <span data-ttu-id="5f6b5-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="5f6b5-152">SBC SWe</span></span>          | <span data-ttu-id="5f6b5-153">8.2</span><span class="sxs-lookup"><span data-stu-id="5f6b5-153">8.2</span></span>  |
| [<span data-ttu-id="5f6b5-154">功能區 SBC 邊緣</span><span class="sxs-lookup"><span data-stu-id="5f6b5-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="5f6b5-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="5f6b5-155">SBC SWe Lite</span></span> | <span data-ttu-id="5f6b5-156">8.1.5 （組建239）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="5f6b5-157">TE-系統</span><span class="sxs-lookup"><span data-stu-id="5f6b5-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="5f6b5-158">anynode</span><span class="sxs-lookup"><span data-stu-id="5f6b5-158">anynode</span></span>          | <span data-ttu-id="5f6b5-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="5f6b5-159">4.0.1+</span></span> |
| [<span data-ttu-id="5f6b5-160">聯手</span><span class="sxs-lookup"><span data-stu-id="5f6b5-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="5f6b5-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="5f6b5-161">AP 1100</span></span> | <span data-ttu-id="5f6b5-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5f6b5-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="5f6b5-163">AP 3900</span></span> | <span data-ttu-id="5f6b5-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5f6b5-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="5f6b5-165">AP 4600</span></span> | <span data-ttu-id="5f6b5-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5f6b5-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="5f6b5-167">AP 6300</span></span> | <span data-ttu-id="5f6b5-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5f6b5-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="5f6b5-169">AP 6350</span></span> | <span data-ttu-id="5f6b5-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5f6b5-171">VME</span><span class="sxs-lookup"><span data-stu-id="5f6b5-171">VME</span></span>     | <span data-ttu-id="5f6b5-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="5f6b5-173">管理外部信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5f6b5-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="5f6b5-174">外部信任的 Ip 是商業網路的網際網路外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="5f6b5-175">這些 IP 是 Microsoft 團隊用戶端連線至 Microsoft 365 時所使用的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="5f6b5-176">您必須針對每一個您有使用者使用本機媒體優化的網站，新增這些外部 Ip。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="5f6b5-177">若要為每個網站新增公用 IP 位址，請使用 CsTenantTrustedIPAddress Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="5f6b5-178">您可以為租使用者定義數量不受信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="5f6b5-179">如果 Microsoft 365 所看到的外部 IPs 都是 IPv4 與 IPv6 位址，則您必須新增這兩種類型的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="5f6b5-180">若是 IPv4，請使用 mask 32。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="5f6b5-181">若是 IPv6，請使用 mask 128。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="5f6b5-182">您可以在 Cmdlet 上指定不同的 MaskBits，以新增個別的外部 IP 位址和外部 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="5f6b5-183">新增信任的 IP 位址範例。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="5f6b5-184">定義網路拓撲</span><span class="sxs-lookup"><span data-stu-id="5f6b5-184">Define the network topology</span></span>

<span data-ttu-id="5f6b5-185">本節說明如何為您的網路拓撲定義網路區域、網路網站和網路子網。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="5f6b5-186">所有參數都是區分大小寫的，因此您必須確保您使用的是在安裝期間使用的相同大小寫。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="5f6b5-187">（例如，GatewaySiteID 值 "越南" 和 "越南" 將會被視為不同的網站）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="5f6b5-188">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="5f6b5-188">Define network regions</span></span>

<span data-ttu-id="5f6b5-189">若要定義網路區域，請使用 CsTenantNetworkRegion Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="5f6b5-190">RegionID 參數是代表區域地理位置的邏輯名稱，沒有相依性或限制。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="5f6b5-191">CentralSite <site ID> 參數是選擇性的。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5f6b5-192">下列範例會建立名為 APAC 的網路區域：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="5f6b5-193">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-193">Define network sites</span></span>

<span data-ttu-id="5f6b5-194">若要定義網路網站，請使用 CsTenantNetworkSite Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="5f6b5-195">每個網路網站都必須與一個網路區域建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="5f6b5-196">下列範例會在 APAC 區域中建立三個新的網路網站、越南、印尼及新加坡：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="5f6b5-197">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="5f6b5-197">Define network subnets</span></span>

<span data-ttu-id="5f6b5-198">若要定義網路子網並將它們與網路網站關聯，請使用 CsTenantNetworkSubnet Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5f6b5-199">每個網路子網只能與一個網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="5f6b5-200">下列範例定義三個網路子網，並將它們與三個網路網站進行關聯：越南、印尼及新加坡：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="5f6b5-201">定義虛擬網路拓撲</span><span class="sxs-lookup"><span data-stu-id="5f6b5-201">Define the virtual network topology</span></span> 

<span data-ttu-id="5f6b5-202">首先，租使用者管理員使用 CsOnlinePSTNGateway Cmdlet，為每個相關的 SBC 建立新的 SBC 設定。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="5f6b5-203">租使用者管理員使用 CsOnlinePSTNGateway Cmdlet 來指定 PSTN 閘道物件的網路網站，以定義虛擬網路拓朴：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="5f6b5-204">請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-204">Note the following:</span></span> 
   - <span data-ttu-id="5f6b5-205">如果客戶只有一個 SBC，則-ProxySBC 參數必須是強制性 $null 或 SBC FQDN 值（集中 trunks 案例的中央 SBC）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="5f6b5-206">-MediaBypass 參數必須設定為 $true，才能支援本機媒體優化。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="5f6b5-207">如果 SBC 沒有 BypassMode 參數集，則不會傳送 X MS 標頭。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="5f6b5-208">所有參數都區分大小寫，因此您需要確保您使用的是在安裝期間使用的相同大小寫。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="5f6b5-209">（例如，GatewaySiteID 值 "越南" 和 "越南" 將會被視為不同的網站）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="5f6b5-210">下列範例會將三個 SBCs 新增到 [APAC] 區域中的 [越南]、[印尼] 和 [新加坡]，且模式總是略過：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="5f6b5-211">注意：若要確保在同時設定本機媒體優化和位置式路由（LBR）時不間斷的操作，必須針對每個下游 SBC 將 GatewaySiteLbrEnabled 參數設定為 $true，才能啟用下游 SBCs LBR。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="5f6b5-212">（Proxy SBC 不強制此設定）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="5f6b5-213">根據上述資訊，直接路由會包含三個專有的 SIP 標頭至 SIP 邀請和重新邀請，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="5f6b5-214">如果定義了 BypassMode，則會直接在邀請和重新邀請上路由的 X MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="5f6b5-215">標題名稱</span><span class="sxs-lookup"><span data-stu-id="5f6b5-215">Header name</span></span> | <span data-ttu-id="5f6b5-216">相對值</span><span class="sxs-lookup"><span data-stu-id="5f6b5-216">Values</span></span> | <span data-ttu-id="5f6b5-217">註解</span><span class="sxs-lookup"><span data-stu-id="5f6b5-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="5f6b5-218">X 毫秒-UserLocation</span><span class="sxs-lookup"><span data-stu-id="5f6b5-218">X-MS-UserLocation</span></span> | <span data-ttu-id="5f6b5-219">內部/外部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-219">internal/external</span></span> | <span data-ttu-id="5f6b5-220">指出使用者是否為內部或外部使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="5f6b5-221">要求-URI 邀請 sip： + 84439263000@VNsbc.contoso.com SIP/2。0</span><span class="sxs-lookup"><span data-stu-id="5f6b5-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="5f6b5-222">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="5f6b5-222">SBC FQDN</span></span> | <span data-ttu-id="5f6b5-223">即使 SBC 未直接連線至直接佈線，也會以呼叫為目標的 FQDN</span><span class="sxs-lookup"><span data-stu-id="5f6b5-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="5f6b5-224">X 毫秒-MediaPath</span><span class="sxs-lookup"><span data-stu-id="5f6b5-224">X-MS-MediaPath</span></span> | <span data-ttu-id="5f6b5-225">範例： proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-226">應該用於使用者與目標 SBC 之間媒體路徑的 SBCs 順序。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="5f6b5-227">最後一個 SBC 永遠是最後一個</span><span class="sxs-lookup"><span data-stu-id="5f6b5-227">The final SBC is always last</span></span> |
| <span data-ttu-id="5f6b5-228">X 毫秒-UserSite</span><span class="sxs-lookup"><span data-stu-id="5f6b5-228">X-MS-UserSite</span></span> | <span data-ttu-id="5f6b5-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="5f6b5-229">usersiteID</span></span> | <span data-ttu-id="5f6b5-230">由租使用者管理員定義的字串</span><span class="sxs-lookup"><span data-stu-id="5f6b5-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="5f6b5-231">通話流程</span><span class="sxs-lookup"><span data-stu-id="5f6b5-231">Call flows</span></span> 

<span data-ttu-id="5f6b5-232">下列顯示兩種模式的通話流程：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="5f6b5-233">永遠略過</span><span class="sxs-lookup"><span data-stu-id="5f6b5-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="5f6b5-234">僅適用于本機使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="5f6b5-235">[Always 旁路] 模式</span><span class="sxs-lookup"><span data-stu-id="5f6b5-235">Always Bypass mode</span></span>

<span data-ttu-id="5f6b5-236">[Always 旁路模式] 是最簡單的設定選項。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="5f6b5-237">如果所有的 SBCs 都可從任何網站取得，租使用者管理員可以為所有使用者和 SBCs 設定單一網站。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="5f6b5-238">在下列情況下，這些範例會顯示 [總是繞過] 模式：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="5f6b5-239">呼出通話，且使用者與 SBC 位於相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5f6b5-240">輸入通話，且使用者與 SBC 位於相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- <span data-ttu-id="5f6b5-241">[[撥出通話] 和 [外部使用者]](#outbound-calls-and-the-user-is-external-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="5f6b5-241">[Outbound calls and the user is external](#outbound-calls-and-the-user-is-external-with-always-bypass)</span></span>
- [<span data-ttu-id="5f6b5-242">入站通話與使用者是外部的</span><span class="sxs-lookup"><span data-stu-id="5f6b5-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="5f6b5-243">下表顯示範例中使用的 FQDN 和 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="5f6b5-244">稱</span><span class="sxs-lookup"><span data-stu-id="5f6b5-244">FQDN</span></span> | <span data-ttu-id="5f6b5-245">SBC 外部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5f6b5-245">SBC external IP address</span></span> | <span data-ttu-id="5f6b5-246">SBC 內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5f6b5-246">SBC internal IP Address</span></span> | <span data-ttu-id="5f6b5-247">內部子網</span><span class="sxs-lookup"><span data-stu-id="5f6b5-247">Internal subnet</span></span> | <span data-ttu-id="5f6b5-248">位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-248">Location</span></span> | <span data-ttu-id="5f6b5-249">外部 NAT （信任的 IP）</span><span class="sxs-lookup"><span data-stu-id="5f6b5-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-251">無</span><span class="sxs-lookup"><span data-stu-id="5f6b5-251">None</span></span> | <span data-ttu-id="5f6b5-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="5f6b5-252">192.168.1.5</span></span> | <span data-ttu-id="5f6b5-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="5f6b5-253">192.168.1.0/24</span></span> | <span data-ttu-id="5f6b5-254">越南</span><span class="sxs-lookup"><span data-stu-id="5f6b5-254">Vietnam</span></span> | <span data-ttu-id="5f6b5-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="5f6b5-255">172.16.240.110</span></span> |
| <span data-ttu-id="5f6b5-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-257">無</span><span class="sxs-lookup"><span data-stu-id="5f6b5-257">None</span></span> | <span data-ttu-id="5f6b5-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="5f6b5-258">192.168.2.5</span></span> | <span data-ttu-id="5f6b5-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="5f6b5-259">192.168.2.0/24</span></span> | <span data-ttu-id="5f6b5-260">印尼</span><span class="sxs-lookup"><span data-stu-id="5f6b5-260">Indonesia</span></span> | <span data-ttu-id="5f6b5-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="5f6b5-261">172.16.240.120</span></span> |
| <span data-ttu-id="5f6b5-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="5f6b5-263">172.16.240.133</span></span> | <span data-ttu-id="5f6b5-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="5f6b5-264">192.168.3.5</span></span> | <span data-ttu-id="5f6b5-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="5f6b5-265">192.168.3.0/24</span></span> | <span data-ttu-id="5f6b5-266">新加坡</span><span class="sxs-lookup"><span data-stu-id="5f6b5-266">Singapore</span></span> | <span data-ttu-id="5f6b5-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="5f6b5-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5f6b5-268">[呼出通話]，而且使用者與使用永遠略過的 SBC 位於相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5f6b5-269">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-269">Mode</span></span> |    <span data-ttu-id="5f6b5-270">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-270">User</span></span> |  <span data-ttu-id="5f6b5-271">位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-271">Location</span></span> |  <span data-ttu-id="5f6b5-272">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="5f6b5-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f6b5-273">AlwaysBypass</span></span> |    <span data-ttu-id="5f6b5-274">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-274">Internal</span></span> |  <span data-ttu-id="5f6b5-275">與 SBC 相同的網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-275">The same site as SBC</span></span> |  <span data-ttu-id="5f6b5-276">發</span><span class="sxs-lookup"><span data-stu-id="5f6b5-276">Outbound</span></span> |

<span data-ttu-id="5f6b5-277">下表顯示使用者的設定和動作：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="5f6b5-278">使用者物理位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-278">User physical location</span></span>| <span data-ttu-id="5f6b5-279">使用者撥打或接聽電話號碼</span><span class="sxs-lookup"><span data-stu-id="5f6b5-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="5f6b5-280">使用者電話號碼</span><span class="sxs-lookup"><span data-stu-id="5f6b5-280">User phone number</span></span>  | <span data-ttu-id="5f6b5-281">線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="5f6b5-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="5f6b5-282">針對 SBC 設定的模式</span><span class="sxs-lookup"><span data-stu-id="5f6b5-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-283">越南</span><span class="sxs-lookup"><span data-stu-id="5f6b5-283">Vietnam</span></span> | <span data-ttu-id="5f6b5-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5f6b5-284">+84 4 3926 3000</span></span> | <span data-ttu-id="5f6b5-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5f6b5-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="5f6b5-286">優先順序1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5f6b5-287">優先順序2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="5f6b5-288">VNsbc.contoso.com –總是略過</span><span class="sxs-lookup"><span data-stu-id="5f6b5-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="5f6b5-289">proxysbc.contoso.com –總是略過</span><span class="sxs-lookup"><span data-stu-id="5f6b5-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="5f6b5-290">下圖顯示使用 [永遠繞過] 模式進行出站通話的 SIP 階梯，以及使用者與 SBC 位於相同位置的情況。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="5f6b5-291">![顯示出站通話的圖表](media/direct-routing-media-op-10.png "呼出通話")</span><span class="sxs-lookup"><span data-stu-id="5f6b5-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="5f6b5-292">下表顯示直接路由傳送的 X MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="5f6b5-293">參數</span><span class="sxs-lookup"><span data-stu-id="5f6b5-293">Parameter</span></span> | <span data-ttu-id="5f6b5-294">簡要</span><span class="sxs-lookup"><span data-stu-id="5f6b5-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="5f6b5-295">邀請 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-296">在線上語音路由策略中定義之 SBC 的目標 FQDN 是在要求 URI 中傳送</span><span class="sxs-lookup"><span data-stu-id="5f6b5-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="5f6b5-297">X-MS-UserLocation：內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="5f6b5-298">指出使用者位於公司網路內部的欄位</span><span class="sxs-lookup"><span data-stu-id="5f6b5-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="5f6b5-299">X-MS-MediaPath： VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="5f6b5-300">指定用戶端必須向目標 SBC 遍歷哪個 SBC。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5f6b5-301">在這種情況下，我們一直都略過，而用戶端則是以標題中的唯一名稱傳送的目標名稱。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="5f6b5-302">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="5f6b5-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="5f6b5-303">在使用者所在的網站中指示的欄位。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5f6b5-304">入站通話，且使用者與具有 Always 略過之 SBC 的位置相同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5f6b5-305">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-305">Mode</span></span> |    <span data-ttu-id="5f6b5-306">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-306">User</span></span> |  <span data-ttu-id="5f6b5-307">位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-307">Location</span></span> |  <span data-ttu-id="5f6b5-308">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f6b5-309">AlwaysBypass</span></span> |    <span data-ttu-id="5f6b5-310">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-310">Internal</span></span> | <span data-ttu-id="5f6b5-311">與 SBC 相同的網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-311">The same site as SBC</span></span> | <span data-ttu-id="5f6b5-312">進貨</span><span class="sxs-lookup"><span data-stu-id="5f6b5-312">Inbound</span></span> |


<span data-ttu-id="5f6b5-313">在撥入通話中，使用者的位置未知，而且 SBC 必須猜使用者在哪裡。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="5f6b5-314">如果 guess 不正確，就需要重新邀請。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="5f6b5-315">這個案例假設使用者是內部使用者，媒體可以直接流向，而且不需要進一步的動作（重新邀請）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="5f6b5-316">透過提供 Record 路由和連絡人欄位，連線至直接路由服務的 SBC 會報告原始的 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="5f6b5-317">根據這些欄位，媒體路徑是透過直接路由來計算。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="5f6b5-318">注意：假設使用者可以有多個端點，就不可能支援183。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="5f6b5-319">在這種情況下，直接路由將永遠使用180鈴聲。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="5f6b5-320">下圖顯示入站通話中 AlwaysBypass 模式的 SIP 階梯，且使用者與 SBC 位於相同的位置。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5f6b5-322">[呼出通話] 與 [永遠略過] 的使用者是外部的</span><span class="sxs-lookup"><span data-stu-id="5f6b5-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5f6b5-323">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-323">Mode</span></span> |    <span data-ttu-id="5f6b5-324">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-324">User</span></span> |  <span data-ttu-id="5f6b5-325">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-325">Site</span></span> |  <span data-ttu-id="5f6b5-326">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5f6b5-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f6b5-327">AlwaysBypass</span></span> |  <span data-ttu-id="5f6b5-328">外來</span><span class="sxs-lookup"><span data-stu-id="5f6b5-328">External</span></span> |  <span data-ttu-id="5f6b5-329">不適用</span><span class="sxs-lookup"><span data-stu-id="5f6b5-329">N/A</span></span> | <span data-ttu-id="5f6b5-330">發</span><span class="sxs-lookup"><span data-stu-id="5f6b5-330">Outbound</span></span> |


<span data-ttu-id="5f6b5-331">下圖顯示使用 AlwaysBypass 模式的出站呼叫的 SIP 階梯，且使用者是外部的：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-12.png)

<span data-ttu-id="5f6b5-333">下表顯示由直向路由服務傳送的 X MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="5f6b5-334">參數</span><span class="sxs-lookup"><span data-stu-id="5f6b5-334">Parameter</span></span> |   <span data-ttu-id="5f6b5-335">簡要</span><span class="sxs-lookup"><span data-stu-id="5f6b5-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="5f6b5-336">邀請 + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-337">在線上語音路由策略中定義之 SBC 的目標 FQDN 會在要求 URI 中傳送。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="5f6b5-338">X-MS-UserLocation：外部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="5f6b5-339">指出使用者位於公司網路以外的欄位。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="5f6b5-340">X-MS-MediaPath： proxysbc.contoso.com，VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="5f6b5-341">指定用戶端必須向目標 SBC 遍歷哪個 SBC。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5f6b5-342">在這種情況下，我們一直都略過，而用戶端則是外部的。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5f6b5-343">輸入通話，且使用者是使用永遠略過的外部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5f6b5-344">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-344">Mode</span></span> | <span data-ttu-id="5f6b5-345">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-345">User</span></span> | <span data-ttu-id="5f6b5-346">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-346">Site</span></span> |  <span data-ttu-id="5f6b5-347">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5f6b5-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5f6b5-348">AlwaysBypass</span></span> |  <span data-ttu-id="5f6b5-349">外來</span><span class="sxs-lookup"><span data-stu-id="5f6b5-349">External</span></span> |  <span data-ttu-id="5f6b5-350">不適用</span><span class="sxs-lookup"><span data-stu-id="5f6b5-350">N/A</span></span> |   <span data-ttu-id="5f6b5-351">進貨</span><span class="sxs-lookup"><span data-stu-id="5f6b5-351">Inbound</span></span> |

<span data-ttu-id="5f6b5-352">如果是撥入通話，則連接至直接路由的 SBC 必須傳送重新邀請（預設會提供本機媒體候選人）（如果使用者是外部的位置）。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="5f6b5-353">X-MediaPath 是根據記錄路由與指定的 SBC 使用者來計算。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="5f6b5-354">下圖顯示使用 AlwaysBypass 模式的入站呼叫的 SIP 階梯，且使用者是外部的。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="5f6b5-356">僅適用于 [本機使用者] 模式</span><span class="sxs-lookup"><span data-stu-id="5f6b5-356">Only for local users mode</span></span>

<span data-ttu-id="5f6b5-357">只有在使用者與 SBC 位於相同的位置時，才會提供目標 SBC 的本機媒體候選項目。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="5f6b5-358">在其他所有情況下，媒體會透過 proxy SBC 的內部或外部 IP 來傳送。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="5f6b5-359">描述下列案例：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="5f6b5-360">呼出通話，且使用者與 SBC 位於相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5f6b5-361">輸入通話，且使用者與 SBC 位於相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5f6b5-362">使用者與 SBC 不在同一個位置，但在商業網路中</span><span class="sxs-lookup"><span data-stu-id="5f6b5-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="5f6b5-363">輸入通話與使用者是內部的，但不在與 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="5f6b5-364">下表顯示最終使用者設定和動作：</span><span class="sxs-lookup"><span data-stu-id="5f6b5-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="5f6b5-365">使用者物理位置</span><span class="sxs-lookup"><span data-stu-id="5f6b5-365">User physical location</span></span> |  <span data-ttu-id="5f6b5-366">使用者撥打或接聽電話號碼</span><span class="sxs-lookup"><span data-stu-id="5f6b5-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="5f6b5-367">使用者電話號碼</span><span class="sxs-lookup"><span data-stu-id="5f6b5-367">User phone number</span></span> | <span data-ttu-id="5f6b5-368">線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="5f6b5-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="5f6b5-369">針對 SBC 設定的模式</span><span class="sxs-lookup"><span data-stu-id="5f6b5-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-370">越南</span><span class="sxs-lookup"><span data-stu-id="5f6b5-370">Vietnam</span></span> | <span data-ttu-id="5f6b5-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5f6b5-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="5f6b5-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5f6b5-372">+84 4 5555 5555</span></span> | <span data-ttu-id="5f6b5-373">優先順序1： ^ \+ 84 （\d {9} ） $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5f6b5-374">優先順序2：. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5f6b5-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="5f6b5-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com-Always 旁路</span><span class="sxs-lookup"><span data-stu-id="5f6b5-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f6b5-376">呼出通話，且使用者與 SBC 在相同的位置，且僅適用于本機使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f6b5-377">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-377">Mode</span></span> | <span data-ttu-id="5f6b5-378">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-378">User</span></span> | <span data-ttu-id="5f6b5-379">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-379">Site</span></span> | <span data-ttu-id="5f6b5-380">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f6b5-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5f6b5-382">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-382">Internal</span></span> |<span data-ttu-id="5f6b5-383">與 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-383">Same as SBC</span></span>   | <span data-ttu-id="5f6b5-384">發</span><span class="sxs-lookup"><span data-stu-id="5f6b5-384">Outbound</span></span> |

<span data-ttu-id="5f6b5-385">下圖顯示使用 OnlyForLocalUsers 模式的撥出電話，且使用者與 SBC 位於相同的位置。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5f6b5-386">[當使用者位於與 SBC 相同的位置時，在呼出通話](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)中會顯示相同的流程。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f6b5-388">輸入通話，且使用者與 SBC 在相同的位置，且僅適用于本機使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f6b5-389">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-389">Mode</span></span> | <span data-ttu-id="5f6b5-390">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-390">User</span></span> | <span data-ttu-id="5f6b5-391">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-391">Site</span></span> | <span data-ttu-id="5f6b5-392">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f6b5-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5f6b5-394">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-394">Internal</span></span> | <span data-ttu-id="5f6b5-395">與 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-395">Same as SBC</span></span> | <span data-ttu-id="5f6b5-396">進貨</span><span class="sxs-lookup"><span data-stu-id="5f6b5-396">Inbound</span></span> |

<span data-ttu-id="5f6b5-397">下圖顯示使用 OnlyForLocalUsers 模式的入站通話，且使用者與 SBC 位於同一個位置。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5f6b5-398">[當使用者與 SBC 位於同一個位置時](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)，這就是與入站通話中所示的相同流程。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="5f6b5-400">使用者與 SBC 不在同一個位置，但位於公司網路中，僅適用于本機使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="5f6b5-401">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-401">Mode</span></span> | <span data-ttu-id="5f6b5-402">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-402">User</span></span> | <span data-ttu-id="5f6b5-403">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-403">Site</span></span> |<span data-ttu-id="5f6b5-404">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f6b5-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="5f6b5-406">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-406">Internal</span></span> |   <span data-ttu-id="5f6b5-407">SBC 不同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-407">Different from SBC</span></span> | <span data-ttu-id="5f6b5-408">發</span><span class="sxs-lookup"><span data-stu-id="5f6b5-408">Outbound</span></span> |

<span data-ttu-id="5f6b5-409">[直接路由] 會根據在 SBC 上設定的使用者和模式的已報告位置來計算 X MediaPath。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="5f6b5-410">下圖顯示使用 OnlyForLocalUsers 模式的撥出電話，以及與 SBC 不在相同位置的內部使用者。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5f6b5-412">撥入通話且使用者是內部使用者，但不與僅供本機使用者使用的 SBC 位置相同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5f6b5-413">下</span><span class="sxs-lookup"><span data-stu-id="5f6b5-413">Mode</span></span> |    <span data-ttu-id="5f6b5-414">使用者</span><span class="sxs-lookup"><span data-stu-id="5f6b5-414">User</span></span> |  <span data-ttu-id="5f6b5-415">網站</span><span class="sxs-lookup"><span data-stu-id="5f6b5-415">Site</span></span> |  <span data-ttu-id="5f6b5-416">通話方向</span><span class="sxs-lookup"><span data-stu-id="5f6b5-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5f6b5-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5f6b5-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="5f6b5-418">內部</span><span class="sxs-lookup"><span data-stu-id="5f6b5-418">Internal</span></span> |    <span data-ttu-id="5f6b5-419">SBC 不同</span><span class="sxs-lookup"><span data-stu-id="5f6b5-419">Different from SBC</span></span> |    <span data-ttu-id="5f6b5-420">進貨</span><span class="sxs-lookup"><span data-stu-id="5f6b5-420">Inbound</span></span> |

<span data-ttu-id="5f6b5-421">下圖顯示使用 OnlyForLocalUsers 模式的入站通話，以及與 SBC 不在相同位置的內部使用者。</span><span class="sxs-lookup"><span data-stu-id="5f6b5-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![顯示 SIP 階梯的圖表](media/direct-routing-media-op-17.png)









