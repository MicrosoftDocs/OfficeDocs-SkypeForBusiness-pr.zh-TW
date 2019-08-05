---
title: 在雲端連接器中部署多個網站
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: 瞭解如何在雲端連接器版本中部署多個 PSTN 網站。
ms.openlocfilehash: ba6b76366b65a9febb9fab06e7cfb0fad759e5ee
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190846"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="3d3b1-103">在雲端連接器中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="3d3b1-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="3d3b1-104">瞭解如何在雲端連接器版本中部署多個 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="3d3b1-105">本節說明如何部署多個公用交換電話網絡 (PSTN) 網站。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-105">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="3d3b1-106">使用與部署單一網站相同的步驟, 一次部署一個網站。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-106">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="3d3b1-107">本主題說明多重網站部署中的網站與差異的考慮。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-107">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="3d3b1-108">多個公用交換電話網絡 (PSTN) 網站</span><span class="sxs-lookup"><span data-stu-id="3d3b1-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="3d3b1-109">下列顯示部署不同 PSTN 網站之商務用 Skype 雲端連接器版的範例配置。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="3d3b1-110">開始部署前, 請確定您的設定正確無誤。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="3d3b1-111">PSTN 網站1</span><span class="sxs-lookup"><span data-stu-id="3d3b1-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="3d3b1-112">PSTN 網站2</span><span class="sxs-lookup"><span data-stu-id="3d3b1-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="3d3b1-113">針對您要新增的每個 PSTN 網站, 按照在[雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="3d3b1-114">針對每個 PSTN 網站準備高可用性 (HA) 的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="3d3b1-115">在 PSTN 網站之間, 共用資料夾**必須**不同。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="3d3b1-116">請勿對多個網站使用相同的共用資料夾。 ></span><span class="sxs-lookup"><span data-stu-id="3d3b1-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="3d3b1-117">高可用性 (HA) 與多網站部署的單一網站</span><span class="sxs-lookup"><span data-stu-id="3d3b1-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="3d3b1-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="3d3b1-118"></span></span>

<span data-ttu-id="3d3b1-119">下表列出單一網站與 HA 支援及多重網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="3d3b1-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="3d3b1-120">**類別**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-120">**Category**</span></span>|<span data-ttu-id="3d3b1-121">**選項**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-121">**Item**</span></span>|<span data-ttu-id="3d3b1-122">**含 HA 的單一網站**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-122">**Single-Site with HA**</span></span>|<span data-ttu-id="3d3b1-123">**多網站**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d3b1-124">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-124">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-125">裝置主機名稱</span><span class="sxs-lookup"><span data-stu-id="3d3b1-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="3d3b1-126">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-127">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-128">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3d3b1-128">Setup</span></span>  <br/> |<span data-ttu-id="3d3b1-129">共用資料夾</span><span class="sxs-lookup"><span data-stu-id="3d3b1-129">Shared folder</span></span>  <br/> |<span data-ttu-id="3d3b1-130">在多個裝置上需要**相同**的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="3d3b1-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-131">跨裝置需要**不同**的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="3d3b1-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="3d3b1-132">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-132">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="3d3b1-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="3d3b1-134">跨裝置需要**相同**的網域</span><span class="sxs-lookup"><span data-stu-id="3d3b1-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-135">在 PSTN 網站上需要**同一個**網域</span><span class="sxs-lookup"><span data-stu-id="3d3b1-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-136">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-136">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="3d3b1-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="3d3b1-138">網功能變數名稱稱和順序在各個裝置中應該是**相同**的</span><span class="sxs-lookup"><span data-stu-id="3d3b1-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-139">網功能變數名稱稱和順序在 PSTN 網站中應該是**相同**的</span><span class="sxs-lookup"><span data-stu-id="3d3b1-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-140">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-140">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-141">網站名稱</span><span class="sxs-lookup"><span data-stu-id="3d3b1-141">Site name</span></span>  <br/> |<span data-ttu-id="3d3b1-142">**相同**跨裝置的網站名稱</span><span class="sxs-lookup"><span data-stu-id="3d3b1-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-143">**不同**PSTN 網站上的網站名稱</span><span class="sxs-lookup"><span data-stu-id="3d3b1-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-144">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-144">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-145">伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="3d3b1-145">Server names</span></span>  <br/> |<span data-ttu-id="3d3b1-146">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-147">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-148">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-148">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-149">內部池 Fqdn</span><span class="sxs-lookup"><span data-stu-id="3d3b1-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="3d3b1-150">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-151">跨 PSTN 網站**相同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-152">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-152">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-153">內部 Ip</span><span class="sxs-lookup"><span data-stu-id="3d3b1-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="3d3b1-154">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-155">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-156">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-156">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-157">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="3d3b1-157">External FQDN</span></span>  <br/> |<span data-ttu-id="3d3b1-158">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-159">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-160">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-160">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-161">外部 Ip</span><span class="sxs-lookup"><span data-stu-id="3d3b1-161">External IPs</span></span>  <br/> |<span data-ttu-id="3d3b1-162">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-163">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-164">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-164">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-165">PSTN GW 設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="3d3b1-166">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="3d3b1-167">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="3d3b1-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="3d3b1-168">設定</span><span class="sxs-lookup"><span data-stu-id="3d3b1-168">Configure</span></span>  <br/> |<span data-ttu-id="3d3b1-169">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="3d3b1-169">DNS record</span></span>  <br/> |<span data-ttu-id="3d3b1-170">使用**相同**的外部存取 fqdn 和**不同**的 IP 位址新增記錄</span><span class="sxs-lookup"><span data-stu-id="3d3b1-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="3d3b1-171">新增具有**不同**外部存取 fqdn 及**不同**IP 位址的記錄</span><span class="sxs-lookup"><span data-stu-id="3d3b1-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="3d3b1-172">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3d3b1-172">Setup</span></span>  <br/> |<span data-ttu-id="3d3b1-173">混合式租使用者</span><span class="sxs-lookup"><span data-stu-id="3d3b1-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="3d3b1-174">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="3d3b1-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="3d3b1-175">設定 PeerDestination 以進行回退</span><span class="sxs-lookup"><span data-stu-id="3d3b1-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="3d3b1-176">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="3d3b1-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="3d3b1-177">設定 PeerDestination 以進行回退</span><span class="sxs-lookup"><span data-stu-id="3d3b1-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="3d3b1-178">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3d3b1-178">Setup</span></span>  <br/> |<span data-ttu-id="3d3b1-179">關</span><span class="sxs-lookup"><span data-stu-id="3d3b1-179">Gateway</span></span>  <br/> |<span data-ttu-id="3d3b1-180">此網站中的 MS GW **M:N**對應</span><span class="sxs-lookup"><span data-stu-id="3d3b1-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="3d3b1-181">每個 PSTN 網站中的 PSTN 閘道應該只會連線到相同網站中的中繼伺服器 (s)</span><span class="sxs-lookup"><span data-stu-id="3d3b1-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="3d3b1-182">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="3d3b1-182">Setup</span></span>  <br/> |<span data-ttu-id="3d3b1-183">使用者名</span><span class="sxs-lookup"><span data-stu-id="3d3b1-183">User</span></span>  <br/> |<span data-ttu-id="3d3b1-184">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="3d3b1-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="3d3b1-185">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="3d3b1-185">Set UserPSTNSettings</span></span>  <br/> |
   

