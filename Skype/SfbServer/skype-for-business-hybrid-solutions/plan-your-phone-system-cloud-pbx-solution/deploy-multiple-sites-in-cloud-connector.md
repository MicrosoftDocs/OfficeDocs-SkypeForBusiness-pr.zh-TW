---
title: 在 Cloud Connector 中部署多個網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 瞭解如何在雲端連接器 Edition 中部署多個 PSTN 網站。
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358919"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="e2a4d-103">在 Cloud Connector 中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="e2a4d-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="e2a4d-104">雲端連接器 Edition 會于2021年7月31日和商務用 Skype Online 終止。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="e2a4d-105">當您的組織升級至小組後，請瞭解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話語音網路連線到小組。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="e2a4d-106">瞭解如何在雲端連接器 Edition 中部署多個 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="e2a4d-107">本節說明如何在多部公用交換電話網路 (PSTN) 網站上進行部署。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="e2a4d-108">使用與部署單一網站相同的步驟，一次部署一個網站。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="e2a4d-109">本主題說明多個網站部署中的網站之間的考慮和差異。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="e2a4d-110">多部公用交換電話網路 (PSTN) 網站</span><span class="sxs-lookup"><span data-stu-id="e2a4d-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="e2a4d-111">下列示範設定部署不同 PSTN 網站之商務用 Skype 雲端連接器 Edition 的範例設定。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="e2a4d-112">在您開始部署之前，請確定您的設定設定正確無誤。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="e2a4d-113">PSTN 網站1</span><span class="sxs-lookup"><span data-stu-id="e2a4d-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="e2a4d-114">PSTN Site 2</span><span class="sxs-lookup"><span data-stu-id="e2a4d-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="e2a4d-115">針對您要新增的每個 PSTN 網站，依照在 [雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2a4d-116">準備高可用性的共用資料夾 (的 HA) 是每個 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="e2a4d-117">PSTN 網站之間的共用資料夾 **必須** 不同。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="e2a4d-118">請勿對多個網站使用同一個共用資料夾。 ></span><span class="sxs-lookup"><span data-stu-id="e2a4d-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="e2a4d-119">與多網站部署相比，具有高可用性的單一網站 (HA) </span><span class="sxs-lookup"><span data-stu-id="e2a4d-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="e2a4d-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="e2a4d-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="e2a4d-121">下表列出具有 HA 支援的單一網站與多個網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="e2a4d-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="e2a4d-122">**類別**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-122">**Category**</span></span>|<span data-ttu-id="e2a4d-123">**項目**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-123">**Item**</span></span>|<span data-ttu-id="e2a4d-124">**具有高可用性的單一網站**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-124">**Single-Site with HA**</span></span>|<span data-ttu-id="e2a4d-125">**多網站**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2a4d-126">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-126">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-127">裝置主機名稱</span><span class="sxs-lookup"><span data-stu-id="e2a4d-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="e2a4d-128">各裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-129">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-130">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-130">Setup</span></span>  <br/> |<span data-ttu-id="e2a4d-131">共用資料夾</span><span class="sxs-lookup"><span data-stu-id="e2a4d-131">Shared folder</span></span>  <br/> |<span data-ttu-id="e2a4d-132">跨裝置需要 **相同** 的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="e2a4d-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-133">需要跨裝置使用 **不同** 的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="e2a4d-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="e2a4d-134">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-134">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="e2a4d-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="e2a4d-136">需要跨裝置的 **相同** 網域</span><span class="sxs-lookup"><span data-stu-id="e2a4d-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-137">需要跨 PSTN 網站的 **相同** 網域</span><span class="sxs-lookup"><span data-stu-id="e2a4d-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-138">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-138">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="e2a4d-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="e2a4d-140">跨裝置的功能變數名稱和順序應該**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-141">各 PSTN 網站的功能變數名稱和順序應該**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-142">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-142">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-143">網站名稱</span><span class="sxs-lookup"><span data-stu-id="e2a4d-143">Site name</span></span>  <br/> |<span data-ttu-id="e2a4d-144">**相同** 跨裝置的網站名稱</span><span class="sxs-lookup"><span data-stu-id="e2a4d-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-145">**不同** PSTN 網站上的網站名稱</span><span class="sxs-lookup"><span data-stu-id="e2a4d-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-146">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-146">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-147">伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="e2a4d-147">Server names</span></span>  <br/> |<span data-ttu-id="e2a4d-148">各裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-149">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-150">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-150">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-151">內部集區 Fqdn</span><span class="sxs-lookup"><span data-stu-id="e2a4d-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="e2a4d-152">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-153">跨 PSTN 網站**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-154">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-154">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-155">內部 Ip</span><span class="sxs-lookup"><span data-stu-id="e2a4d-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="e2a4d-156">各裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-157">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-158">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-158">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-159">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="e2a4d-159">External FQDN</span></span>  <br/> |<span data-ttu-id="e2a4d-160">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-161">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-162">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-162">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-163">外部 Ip</span><span class="sxs-lookup"><span data-stu-id="e2a4d-163">External IPs</span></span>  <br/> |<span data-ttu-id="e2a4d-164">各裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-165">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-166">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-166">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-167">PSTN GW 設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="e2a4d-168">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2a4d-169">各 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="e2a4d-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2a4d-170">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-170">Configure</span></span>  <br/> |<span data-ttu-id="e2a4d-171">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="e2a4d-171">DNS record</span></span>  <br/> |<span data-ttu-id="e2a4d-172">新增具有 **相同** 外部存取 fqdn 和 **不同** IP 位址的記錄</span><span class="sxs-lookup"><span data-stu-id="e2a4d-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="e2a4d-173">使用 **不同** 的外部存取 fqdn 和 **不同** 的 IP 位址新增記錄</span><span class="sxs-lookup"><span data-stu-id="e2a4d-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="e2a4d-174">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-174">Setup</span></span>  <br/> |<span data-ttu-id="e2a4d-175">混合租使用者</span><span class="sxs-lookup"><span data-stu-id="e2a4d-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="e2a4d-176">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="e2a4d-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="e2a4d-177">設定 PeerDestination 為 fallback</span><span class="sxs-lookup"><span data-stu-id="e2a4d-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="e2a4d-178">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="e2a4d-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="e2a4d-179">設定 PeerDestination 為 fallback</span><span class="sxs-lookup"><span data-stu-id="e2a4d-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="e2a4d-180">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-180">Setup</span></span>  <br/> |<span data-ttu-id="e2a4d-181">閘道</span><span class="sxs-lookup"><span data-stu-id="e2a4d-181">Gateway</span></span>  <br/> |<span data-ttu-id="e2a4d-182">此網站中的 MS GW **M:N** 對應</span><span class="sxs-lookup"><span data-stu-id="e2a4d-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="e2a4d-183">PSTN 閘道 (s) 在每個 PSTN 網站中應該只連接至相同網站的轉送伺服器 (s) </span><span class="sxs-lookup"><span data-stu-id="e2a4d-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="e2a4d-184">設定</span><span class="sxs-lookup"><span data-stu-id="e2a4d-184">Setup</span></span>  <br/> |<span data-ttu-id="e2a4d-185">使用者</span><span class="sxs-lookup"><span data-stu-id="e2a4d-185">User</span></span>  <br/> |<span data-ttu-id="e2a4d-186">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="e2a4d-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="e2a4d-187">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="e2a4d-187">Set UserPSTNSettings</span></span>  <br/> |
   

