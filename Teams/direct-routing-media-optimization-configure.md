---
title: 直接路由本地媒體優化
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
description: 設定直接路由的當地媒體優化
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576985"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="d3fa5-103">設定直接路由的當地媒體優化</span><span class="sxs-lookup"><span data-stu-id="d3fa5-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="d3fa5-104">Local Media 優化的設定是以其他雲端語音功能所常見的網路設定為基礎，例如Location-Based路由和動態緊急電話。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="d3fa5-105">若要深入瞭解網路區域、網路網站、網路子網和信任的 IP 位址，請參閱雲端 [語音功能的網路設定](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="d3fa5-106">設定 Local Media 優化之前，請參閱直接路由 [的當地媒體優化](direct-routing-media-optimization.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="d3fa5-107">若要設定 Local Media 優化，需要下列步驟。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="d3fa5-108">您可以使用系統管理Teams PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="d3fa5-109">詳細資料請參閱 [管理您的網路拓撲](manage-your-network-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="d3fa5-110">設定使用者和 SBC 網站 (如本文所述) 。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="d3fa5-111">根據 SBC 廠商規格 (設定 SBC 本地媒體優化) 。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="d3fa5-112">下圖顯示本文中範例中使用的網路設定。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="d3fa5-113">![顯示網路設定範例的圖表](media/direct-routing-media-op-9.png "範例的網路設定")</span><span class="sxs-lookup"><span data-stu-id="d3fa5-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="d3fa5-114">設定使用者和 SBC 網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="d3fa5-115">若要設定使用者和 SBC 網站，您必須：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="d3fa5-116">[管理外部信任的 IP 位址](#manage-external-trusted-ip-addresses)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="d3fa5-117">[建立網路區域、](#define-the-network-topology) 網路網站和網路子網，以定義網路拓撲。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="d3fa5-118">[使用相關的模式](#define-the-virtual-network-topology) 和 proxy SBC 值 (SBC) 網站 (定義) 拓撲。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="d3fa5-119">根據 SBC () 設定 SBC 的當地語系化媒體優化選項</span><span class="sxs-lookup"><span data-stu-id="d3fa5-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="d3fa5-120">本文將說明 Microsoft 元件的組組。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="d3fa5-121">有關 SBC 組建的資訊，請參閱您的 SBC 廠商檔。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="d3fa5-122">下列 SBC 廠商支援本地媒體優化：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="d3fa5-123">供應商</span><span class="sxs-lookup"><span data-stu-id="d3fa5-123">Vendor</span></span> | <span data-ttu-id="d3fa5-124">產品</span><span class="sxs-lookup"><span data-stu-id="d3fa5-124">Product</span></span> |    <span data-ttu-id="d3fa5-125">軟體版本</span><span class="sxs-lookup"><span data-stu-id="d3fa5-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="d3fa5-126">音訊代碼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="d3fa5-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="d3fa5-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="d3fa5-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="d3fa5-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="d3fa5-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="d3fa5-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="d3fa5-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="d3fa5-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="d3fa5-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="d3fa5-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="d3fa5-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="d3fa5-142">7.20A.256</span></span> |
| [<span data-ttu-id="d3fa5-143">功能區 SBC Core</span><span class="sxs-lookup"><span data-stu-id="d3fa5-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="d3fa5-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="d3fa5-144">SBC 5110</span></span>         | <span data-ttu-id="d3fa5-145">8.2</span><span class="sxs-lookup"><span data-stu-id="d3fa5-145">8.2</span></span>  |
|            |  <span data-ttu-id="d3fa5-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="d3fa5-146">SBC 5210</span></span>         | <span data-ttu-id="d3fa5-147">8.2</span><span class="sxs-lookup"><span data-stu-id="d3fa5-147">8.2</span></span>  |
|            |  <span data-ttu-id="d3fa5-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="d3fa5-148">SBC 5400</span></span>         | <span data-ttu-id="d3fa5-149">8.2</span><span class="sxs-lookup"><span data-stu-id="d3fa5-149">8.2</span></span>  |
|            |  <span data-ttu-id="d3fa5-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="d3fa5-150">SBC 7000</span></span>         | <span data-ttu-id="d3fa5-151">8.2</span><span class="sxs-lookup"><span data-stu-id="d3fa5-151">8.2</span></span>  |
|            |  <span data-ttu-id="d3fa5-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="d3fa5-152">SBC SWe</span></span>          | <span data-ttu-id="d3fa5-153">8.2</span><span class="sxs-lookup"><span data-stu-id="d3fa5-153">8.2</span></span>  |
| [<span data-ttu-id="d3fa5-154">功能區 SBC Edge</span><span class="sxs-lookup"><span data-stu-id="d3fa5-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="d3fa5-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="d3fa5-155">SBC SWe Lite</span></span> | <span data-ttu-id="d3fa5-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-156">8.1.5</span></span> |
|               | <span data-ttu-id="d3fa5-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="d3fa5-157">SBC 1000</span></span> | <span data-ttu-id="d3fa5-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-158">8.1.5</span></span>  |
|               | <span data-ttu-id="d3fa5-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="d3fa5-159">SBC 2000</span></span> | <span data-ttu-id="d3fa5-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-160">8.1.5</span></span>  |
| [<span data-ttu-id="d3fa5-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="d3fa5-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="d3fa5-162">anynode</span><span class="sxs-lookup"><span data-stu-id="d3fa5-162">anynode</span></span>          | <span data-ttu-id="d3fa5-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="d3fa5-163">4.0.1+</span></span> |
| [<span data-ttu-id="d3fa5-164">甲骨文</span><span class="sxs-lookup"><span data-stu-id="d3fa5-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="d3fa5-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="d3fa5-165">AP 1100</span></span> | <span data-ttu-id="d3fa5-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d3fa5-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="d3fa5-167">AP 3900</span></span> | <span data-ttu-id="d3fa5-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d3fa5-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="d3fa5-169">AP 4600</span></span> | <span data-ttu-id="d3fa5-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d3fa5-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="d3fa5-171">AP 6300</span></span> | <span data-ttu-id="d3fa5-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="d3fa5-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="d3fa5-173">AP 6350</span></span> | <span data-ttu-id="d3fa5-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="d3fa5-175">Vme</span><span class="sxs-lookup"><span data-stu-id="d3fa5-175">VME</span></span>     | <span data-ttu-id="d3fa5-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="d3fa5-177">管理外部信任的 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d3fa5-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="d3fa5-178">外部信任的 IP 是商業網路的網際網路外部 IP。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="d3fa5-179">這些 IP 是用戶端在Microsoft Teams時所使用的 IP 位址Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="d3fa5-180">您必須針對每個使用 Local Media 優化的使用者，新增這些外部 IP。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="d3fa5-181">若要新增每個網站的公用 IP 位址，請使用 New-CsTenantTrustedIPAddress Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="d3fa5-182">您可以為租使用者定義無限個信任的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="d3fa5-183">如果使用者看到的外部 IP Microsoft 365 IPv4 和 IPv6 位址，您必須新增這兩種類型的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="d3fa5-184">針對 IPv4，請使用遮罩 32。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="d3fa5-185">針對 IPv6，請使用遮罩 128。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="d3fa5-186">您可以在 Cmdlet 上指定不同的 MaskBit，以新增個別的外部 IP 位址和外部 IP 子網。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="d3fa5-187">新增信任 IP 位址的範例。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="d3fa5-188">定義網路拓撲</span><span class="sxs-lookup"><span data-stu-id="d3fa5-188">Define the network topology</span></span>

<span data-ttu-id="d3fa5-189">本節說明如何定義網路拓撲的網路區域、網路網站和網路子網。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="d3fa5-190">所有參數都是區分大小寫的，因此您必須確保您使用的大小寫與設定期間所使用的大小寫相同。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="d3fa5-191"> (例如，GatewaySiteID 值「越南」和「越南」會視為不同的網站。) </span><span class="sxs-lookup"><span data-stu-id="d3fa5-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="d3fa5-192">定義網路區域</span><span class="sxs-lookup"><span data-stu-id="d3fa5-192">Define network regions</span></span>

<span data-ttu-id="d3fa5-193">若要定義網路區域，請使用 New-CsTenantNetworkRegion Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="d3fa5-194">RegionID 參數是一個邏輯名稱，代表地區的地理位置，而且沒有相依性或限制。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="d3fa5-195">CentralSite <site ID> 參數為選擇性。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="d3fa5-196">下列範例會建立名為 APAC 的網路區域：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="d3fa5-197">定義網路網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-197">Define network sites</span></span>

<span data-ttu-id="d3fa5-198">若要定義網路網站，請使用 New-CsTenantNetworkSite Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="d3fa5-199">每個網路網站都必須與網路區域相關聯。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="d3fa5-200">下列範例在亞太地區建立三個新網路網站，越南、印尼和新加坡：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="d3fa5-201">定義網路子網</span><span class="sxs-lookup"><span data-stu-id="d3fa5-201">Define network subnets</span></span>

<span data-ttu-id="d3fa5-202">若要定義網路子網並將其與網路網站建立關聯，請使用 New-CsTenantNetworkSubnet Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="d3fa5-203">每個網路子網只能與一個網站建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="d3fa5-204">下列範例定義三個網路子網，並將它們與三個網路網站建立關聯：越南、印尼和新加坡：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="d3fa5-205">定義虛擬網路拓撲</span><span class="sxs-lookup"><span data-stu-id="d3fa5-205">Define the virtual network topology</span></span> 

<span data-ttu-id="d3fa5-206">首先，租使用者系統管理員會使用 Cmdlet 建立每個相關 SBC 的新 SBC New-CsOnlinePSTNGateway組。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="d3fa5-207">租使用者系統管理員使用 Cmdlet 指定 PSTN 閘道物件的網路網站，以定義Set-CsOnlinePSTNGateway拓撲：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="d3fa5-208">注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-208">Note the following:</span></span> 
   - <span data-ttu-id="d3fa5-209">如果客戶有單一 SBC，則 -ProxySBC 參數必須是強制 $null 或 SBC FQDN 值 (集中式主幹案例分析) 。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="d3fa5-210">-MediaBypass 參數必須設為 $true才能支援 Local Media 優化。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="d3fa5-211">如果 SBC 未設定 -BypassMode 參數，將不會送出 X-MS 標頭。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="d3fa5-212">所有參數都是區分大小寫的，因此您必須確保您使用的大小寫與設定期間所使用的大小寫相同。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="d3fa5-213"> (例如，GatewaySiteID 值「越南」和「越南」會視為不同的網站。) </span><span class="sxs-lookup"><span data-stu-id="d3fa5-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="d3fa5-214">下列範例會將三個 SBC 新越南 APAC 地區的網路網站中，且模式永遠會忽略：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="d3fa5-215">注意：若要確保同時設定本地媒體優化和 Location-Based 路由 (LBR) 時不間斷的作業，必須將 GatewaySiteLbrEnabled 參數設定為 $true，讓 LBR 啟用下游 SBC。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="d3fa5-216"> (Proxy SBC.) </span><span class="sxs-lookup"><span data-stu-id="d3fa5-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="d3fa5-217">根據上述資訊，直接路由會包含三個專屬 SIP 標題至 SIP 邀請和重新邀請，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="d3fa5-218">如果已定義 BypassMode，在邀請和 Re-Invites直接路由中引入的 X-MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="d3fa5-219">標題名稱</span><span class="sxs-lookup"><span data-stu-id="d3fa5-219">Header name</span></span> | <span data-ttu-id="d3fa5-220">值</span><span class="sxs-lookup"><span data-stu-id="d3fa5-220">Values</span></span> | <span data-ttu-id="d3fa5-221">註解</span><span class="sxs-lookup"><span data-stu-id="d3fa5-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="d3fa5-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="d3fa5-222">X-MS-UserLocation</span></span> | <span data-ttu-id="d3fa5-223">內部/外部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-223">internal/external</span></span> | <span data-ttu-id="d3fa5-224">指出使用者是內部使用者還是外部使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="d3fa5-225">Request-URI INVITE sip： +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="d3fa5-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="d3fa5-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="d3fa5-226">SBC FQDN</span></span> | <span data-ttu-id="d3fa5-227">目標為通話的 FQDN，即使 SBC 未直接連接到直接路由</span><span class="sxs-lookup"><span data-stu-id="d3fa5-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="d3fa5-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="d3fa5-228">X-MS-MediaPath</span></span> | <span data-ttu-id="d3fa5-229">範例：proxysbc.contoso.com、VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-230">應該用於使用者和目標 SBC 之間媒體路徑的 SBC 順序。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="d3fa5-231">最後一個 SBC 永遠為最後一個</span><span class="sxs-lookup"><span data-stu-id="d3fa5-231">The final SBC is always last</span></span> |
| <span data-ttu-id="d3fa5-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="d3fa5-232">X-MS-UserSite</span></span> | <span data-ttu-id="d3fa5-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="d3fa5-233">usersiteID</span></span> | <span data-ttu-id="d3fa5-234">租使用者系統管理員定義的字串</span><span class="sxs-lookup"><span data-stu-id="d3fa5-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="d3fa5-235">通話流程</span><span class="sxs-lookup"><span data-stu-id="d3fa5-235">Call flows</span></span> 

<span data-ttu-id="d3fa5-236">下列顯示兩種模式的通話流程：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="d3fa5-237">一直忽略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="d3fa5-238">僅適用于當地使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="d3fa5-239">永遠忽略模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-239">Always Bypass mode</span></span>

<span data-ttu-id="d3fa5-240">永遠忽略模式是最簡單的設定選項。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="d3fa5-241">如果所有 SBC 都可以從任何網站取得，租使用者系統管理員可以設定所有使用者和 SBC 的單一網站。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="d3fa5-242">下列範例顯示下列案例的一直忽略模式：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="d3fa5-243">外發通話與使用者位於 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d3fa5-244">來電和使用者位於 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="d3fa5-245">外接通話和使用者是外部使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="d3fa5-246">來電和使用者是外部使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="d3fa5-247">下表顯示範例中使用的 FQDN 和 IP 位址：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="d3fa5-248">Fqdn</span><span class="sxs-lookup"><span data-stu-id="d3fa5-248">FQDN</span></span> | <span data-ttu-id="d3fa5-249">SBC 外部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d3fa5-249">SBC external IP address</span></span> | <span data-ttu-id="d3fa5-250">SBC 內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="d3fa5-250">SBC internal IP Address</span></span> | <span data-ttu-id="d3fa5-251">內部子網</span><span class="sxs-lookup"><span data-stu-id="d3fa5-251">Internal subnet</span></span> | <span data-ttu-id="d3fa5-252">位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-252">Location</span></span> | <span data-ttu-id="d3fa5-253">外部 NAT (信任的 IP) </span><span class="sxs-lookup"><span data-stu-id="d3fa5-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-255">無</span><span class="sxs-lookup"><span data-stu-id="d3fa5-255">None</span></span> | <span data-ttu-id="d3fa5-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-256">192.168.1.5</span></span> | <span data-ttu-id="d3fa5-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="d3fa5-257">192.168.1.0/24</span></span> | <span data-ttu-id="d3fa5-258">越南</span><span class="sxs-lookup"><span data-stu-id="d3fa5-258">Vietnam</span></span> | <span data-ttu-id="d3fa5-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="d3fa5-259">172.16.240.110</span></span> |
| <span data-ttu-id="d3fa5-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-261">無</span><span class="sxs-lookup"><span data-stu-id="d3fa5-261">None</span></span> | <span data-ttu-id="d3fa5-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-262">192.168.2.5</span></span> | <span data-ttu-id="d3fa5-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="d3fa5-263">192.168.2.0/24</span></span> | <span data-ttu-id="d3fa5-264">印尼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-264">Indonesia</span></span> | <span data-ttu-id="d3fa5-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="d3fa5-265">172.16.240.120</span></span> |
| <span data-ttu-id="d3fa5-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="d3fa5-267">172.16.240.133</span></span> | <span data-ttu-id="d3fa5-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="d3fa5-268">192.168.3.5</span></span> | <span data-ttu-id="d3fa5-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="d3fa5-269">192.168.3.0/24</span></span> | <span data-ttu-id="d3fa5-270">新加坡</span><span class="sxs-lookup"><span data-stu-id="d3fa5-270">Singapore</span></span> | <span data-ttu-id="d3fa5-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="d3fa5-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d3fa5-272">外發通話和使用者位於與 SBC 相同的位置，且有一直旁路</span><span class="sxs-lookup"><span data-stu-id="d3fa5-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d3fa5-273">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-273">Mode</span></span> |    <span data-ttu-id="d3fa5-274">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-274">User</span></span> |  <span data-ttu-id="d3fa5-275">位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-275">Location</span></span> |  <span data-ttu-id="d3fa5-276">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="d3fa5-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d3fa5-277">AlwaysBypass</span></span> |    <span data-ttu-id="d3fa5-278">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-278">Internal</span></span> |  <span data-ttu-id="d3fa5-279">與 SBC 相同的網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-279">The same site as SBC</span></span> |  <span data-ttu-id="d3fa5-280">出境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-280">Outbound</span></span> |

<span data-ttu-id="d3fa5-281">下表顯示使用者組組和動作：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="d3fa5-282">使用者實際位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-282">User physical location</span></span>| <span data-ttu-id="d3fa5-283">使用者撥打或接收來電到/從號碼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="d3fa5-284">使用者電話號碼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-284">User phone number</span></span>  | <span data-ttu-id="d3fa5-285">線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="d3fa5-286">為 SBC 所配置的模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-287">越南</span><span class="sxs-lookup"><span data-stu-id="d3fa5-287">Vietnam</span></span> | <span data-ttu-id="d3fa5-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d3fa5-288">+84 4 3926 3000</span></span> | <span data-ttu-id="d3fa5-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d3fa5-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="d3fa5-290">優先順序 1：^ \+ 84 (\d) {9} $ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d3fa5-291">優先順序 2：.\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="d3fa5-292">VNsbc.contoso.com – 永遠忽略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="d3fa5-293">proxysbc.contoso.com – 永遠忽略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="d3fa5-294">下圖顯示使用 Always 旁路模式的外發通話的 SIP 梯級，以及使用者與 SBC 相同的位置。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="d3fa5-295">![顯示外線通話的圖表](media/direct-routing-media-op-10.png "外接通話")</span><span class="sxs-lookup"><span data-stu-id="d3fa5-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="d3fa5-296">下表顯示直接路由傳送的 X-MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="d3fa5-297">參數</span><span class="sxs-lookup"><span data-stu-id="d3fa5-297">Parameter</span></span> | <span data-ttu-id="d3fa5-298">解釋</span><span class="sxs-lookup"><span data-stu-id="d3fa5-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="d3fa5-299">邀請 +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-300">在線上語音路由策略中定義的 SBC 目標 FQDN 會以要求 URI 傳送</span><span class="sxs-lookup"><span data-stu-id="d3fa5-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="d3fa5-301">X-MS-UserLocation：內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="d3fa5-302">該欄位表示使用者位於公司網路內</span><span class="sxs-lookup"><span data-stu-id="d3fa5-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="d3fa5-303">X-MS-MediaPath：VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="d3fa5-304">指定用戶端必須橫穿到目標 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d3fa5-305">在此例中，由於我們一直有旁路，而且用戶端是內部的目標名稱，因此會以標題中的唯一名稱來送出。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="d3fa5-306">X-MS-UserSite：越南</span><span class="sxs-lookup"><span data-stu-id="d3fa5-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="d3fa5-307">使用者所在的網站內所指示的欄位。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="d3fa5-308">來電和使用者位於 SBC 的同一個位置，且有一直旁路</span><span class="sxs-lookup"><span data-stu-id="d3fa5-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="d3fa5-309">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-309">Mode</span></span> |    <span data-ttu-id="d3fa5-310">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-310">User</span></span> |  <span data-ttu-id="d3fa5-311">位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-311">Location</span></span> |  <span data-ttu-id="d3fa5-312">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d3fa5-313">AlwaysBypass</span></span> |    <span data-ttu-id="d3fa5-314">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-314">Internal</span></span> | <span data-ttu-id="d3fa5-315">與 SBC 相同的網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-315">The same site as SBC</span></span> | <span data-ttu-id="d3fa5-316">入境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-316">Inbound</span></span> |


<span data-ttu-id="d3fa5-317">在輸入通話中，使用者的位置不明，SBC 必須猜測使用者的位置。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="d3fa5-318">如果猜測不正確，將會需要重新邀請。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="d3fa5-319">此案例假設使用者是內部使用者，媒體可以直接流動，因此重新邀請 (不需要執行) 。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="d3fa5-320">連結至直接路由服務的 SBC 會提供 Record-Route和連絡人欄位，以報告原始 SBC 位置。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="d3fa5-321">根據這些欄位，媒體路徑是由直接路由計算。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="d3fa5-322">注意：由於使用者可以有多個端點，因此無法支援 183。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="d3fa5-323">在這種情況下，直接路由一定會使用 180 響鈴。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="d3fa5-324">下圖顯示使用 AlwaysBypass 模式進行輸入通話的 SIP 梯級，且使用者的位置與 SBC 相同。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d3fa5-326">外接通話，且使用者是外部使用者，且使用 Always Bypass</span><span class="sxs-lookup"><span data-stu-id="d3fa5-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d3fa5-327">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-327">Mode</span></span> |    <span data-ttu-id="d3fa5-328">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-328">User</span></span> |  <span data-ttu-id="d3fa5-329">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-329">Site</span></span> |  <span data-ttu-id="d3fa5-330">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d3fa5-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d3fa5-331">AlwaysBypass</span></span> |  <span data-ttu-id="d3fa5-332">外部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-332">External</span></span> |  <span data-ttu-id="d3fa5-333">不適用</span><span class="sxs-lookup"><span data-stu-id="d3fa5-333">N/A</span></span> | <span data-ttu-id="d3fa5-334">出境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-334">Outbound</span></span> |


<span data-ttu-id="d3fa5-335">下圖顯示使用 AlwaysBypass 模式的外發通話的 SIP 梯級，且使用者為外部使用者：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-12.png)

<span data-ttu-id="d3fa5-337">下表顯示直接路由服務傳送的 X-MS 標頭：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="d3fa5-338">參數</span><span class="sxs-lookup"><span data-stu-id="d3fa5-338">Parameter</span></span> |   <span data-ttu-id="d3fa5-339">解釋</span><span class="sxs-lookup"><span data-stu-id="d3fa5-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="d3fa5-340">邀請 +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-341">在線上語音路由策略中定義的 SBC 目標 FQDN 會傳送至要求 URI。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="d3fa5-342">X-MS-UserLocation：外部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="d3fa5-343">該欄位表示使用者位於公司網路外部。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="d3fa5-344">X-MS-MediaPath：proxysbc.contoso.com，VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="d3fa5-345">指定用戶端必須橫穿到目標 SBC 的 SBC。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="d3fa5-346">在此案例中，我們一直有旁路，而且用戶端是外部的。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="d3fa5-347">輸入通話，且使用者是外部使用者，且使用一直旁路</span><span class="sxs-lookup"><span data-stu-id="d3fa5-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="d3fa5-348">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-348">Mode</span></span> | <span data-ttu-id="d3fa5-349">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-349">User</span></span> | <span data-ttu-id="d3fa5-350">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-350">Site</span></span> |  <span data-ttu-id="d3fa5-351">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="d3fa5-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="d3fa5-352">AlwaysBypass</span></span> |  <span data-ttu-id="d3fa5-353">外部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-353">External</span></span> |  <span data-ttu-id="d3fa5-354">不適用</span><span class="sxs-lookup"><span data-stu-id="d3fa5-354">N/A</span></span> |   <span data-ttu-id="d3fa5-355">入境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-355">Inbound</span></span> |

<span data-ttu-id="d3fa5-356">如果是輸入通話，連接到直接路由的 SBC 預設需要傳送重新邀請 (如果使用者的位置是外部) 則一向會提供本地媒體候選者。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="d3fa5-357">X-MediaPath 是根據指定Record-Route SBC 使用者所計算。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="d3fa5-358">下圖顯示使用 AlwaysBypass 模式的輸入通話的 SIP 梯級，且使用者是外部使用者。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="d3fa5-360">僅適用于本地使用者模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-360">Only for local users mode</span></span>

<span data-ttu-id="d3fa5-361">只有在使用者與 SBC 位於同一個位置時，才能提供目標 SBC 的當地媒體候選者。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="d3fa5-362">在所有其他情況下，媒體會透過 Proxy SBC 的內部或外部 IP 進行。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="d3fa5-363">描述下列案例：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="d3fa5-364">外發通話與使用者位於 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d3fa5-365">來電和使用者位於 SBC 相同的位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="d3fa5-366">使用者與 SBC 不在同一個位置，但位於公司網路中</span><span class="sxs-lookup"><span data-stu-id="d3fa5-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="d3fa5-367">來電和使用者是內部通話，但與 SBC 不在同一個位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="d3fa5-368">下表顯示使用者組組和動作：</span><span class="sxs-lookup"><span data-stu-id="d3fa5-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="d3fa5-369">使用者實際位置</span><span class="sxs-lookup"><span data-stu-id="d3fa5-369">User physical location</span></span> |  <span data-ttu-id="d3fa5-370">使用者撥打或接收來電到/從號碼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="d3fa5-371">使用者電話號碼</span><span class="sxs-lookup"><span data-stu-id="d3fa5-371">User phone number</span></span> | <span data-ttu-id="d3fa5-372">線上語音路由策略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="d3fa5-373">為 SBC 所配置的模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-374">越南</span><span class="sxs-lookup"><span data-stu-id="d3fa5-374">Vietnam</span></span> | <span data-ttu-id="d3fa5-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="d3fa5-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="d3fa5-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="d3fa5-376">+84 4 5555 5555</span></span> | <span data-ttu-id="d3fa5-377">優先順序 1：^ \+ 84 (\d) {9} $ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="d3fa5-378">優先順序 2：.\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d3fa5-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="d3fa5-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – 永遠忽略</span><span class="sxs-lookup"><span data-stu-id="d3fa5-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d3fa5-380">外發通話和使用者位於 SBC 的同一個位置，且只供當地使用者使用</span><span class="sxs-lookup"><span data-stu-id="d3fa5-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d3fa5-381">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-381">Mode</span></span> | <span data-ttu-id="d3fa5-382">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-382">User</span></span> | <span data-ttu-id="d3fa5-383">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-383">Site</span></span> | <span data-ttu-id="d3fa5-384">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d3fa5-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d3fa5-386">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-386">Internal</span></span> |<span data-ttu-id="d3fa5-387">與 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="d3fa5-387">Same as SBC</span></span>   | <span data-ttu-id="d3fa5-388">出境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-388">Outbound</span></span> |

<span data-ttu-id="d3fa5-389">下圖顯示 OnlyForLocalUsers 模式的外發通話，而使用者的位置與 SBC 相同。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d3fa5-390">當使用者位於與 SBC 相同的位置時，此流程會顯示在外接 [通話中](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d3fa5-392">來電和使用者位於 SBC 的同一個位置，且僅適用于當地使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d3fa5-393">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-393">Mode</span></span> | <span data-ttu-id="d3fa5-394">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-394">User</span></span> | <span data-ttu-id="d3fa5-395">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-395">Site</span></span> | <span data-ttu-id="d3fa5-396">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d3fa5-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="d3fa5-398">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-398">Internal</span></span> | <span data-ttu-id="d3fa5-399">與 SBC 相同</span><span class="sxs-lookup"><span data-stu-id="d3fa5-399">Same as SBC</span></span> | <span data-ttu-id="d3fa5-400">入境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-400">Inbound</span></span> |

<span data-ttu-id="d3fa5-401">下圖顯示使用 OnlyForLocalUsers 模式的輸入通話，而使用者的位置與 SBC 相同。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="d3fa5-402">當使用者位於與 SBC 相同的位置時，此流程與 [輸入通話中顯示的流程相同](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="d3fa5-404">使用者與 SBC 不在同一個位置，但位於公司網路中，只有當地使用者才能使用</span><span class="sxs-lookup"><span data-stu-id="d3fa5-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="d3fa5-405">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-405">Mode</span></span> | <span data-ttu-id="d3fa5-406">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-406">User</span></span> | <span data-ttu-id="d3fa5-407">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-407">Site</span></span> |<span data-ttu-id="d3fa5-408">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d3fa5-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="d3fa5-410">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-410">Internal</span></span> |   <span data-ttu-id="d3fa5-411">與 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="d3fa5-411">Different from SBC</span></span> | <span data-ttu-id="d3fa5-412">出境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-412">Outbound</span></span> |

<span data-ttu-id="d3fa5-413">直接路由會根據使用者的報告位置，以及 SBC 上所配置的模式來計算 X-MediaPath。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="d3fa5-414">下圖顯示使用 OnlyForLocalUsers 模式的外發通話，以及與 SBC 不在同一個位置的內部使用者。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="d3fa5-416">輸入通話與使用者為內部，但位置與 SBC 不在同一個位置，只供當地使用者使用</span><span class="sxs-lookup"><span data-stu-id="d3fa5-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="d3fa5-417">模式</span><span class="sxs-lookup"><span data-stu-id="d3fa5-417">Mode</span></span> |    <span data-ttu-id="d3fa5-418">使用者</span><span class="sxs-lookup"><span data-stu-id="d3fa5-418">User</span></span> |  <span data-ttu-id="d3fa5-419">網站</span><span class="sxs-lookup"><span data-stu-id="d3fa5-419">Site</span></span> |  <span data-ttu-id="d3fa5-420">通話方向</span><span class="sxs-lookup"><span data-stu-id="d3fa5-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="d3fa5-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="d3fa5-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="d3fa5-422">內部</span><span class="sxs-lookup"><span data-stu-id="d3fa5-422">Internal</span></span> |    <span data-ttu-id="d3fa5-423">與 SBC 不同</span><span class="sxs-lookup"><span data-stu-id="d3fa5-423">Different from SBC</span></span> |    <span data-ttu-id="d3fa5-424">入境</span><span class="sxs-lookup"><span data-stu-id="d3fa5-424">Inbound</span></span> |

<span data-ttu-id="d3fa5-425">下圖顯示使用 OnlyForLocalUsers 模式的輸入通話，以及與 SBC 不在同一個位置的內部使用者。</span><span class="sxs-lookup"><span data-stu-id="d3fa5-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![顯示 SIP 梯形圖](media/direct-routing-media-op-17.png)









