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
description: 瞭解如何在雲端連接器版本中部署多個 PSTN 網站。
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799693"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="d71cd-103">在 Cloud Connector 中部署多個網站</span><span class="sxs-lookup"><span data-stu-id="d71cd-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="d71cd-104">瞭解如何在雲端連接器版本中部署多個 PSTN 網站。</span><span class="sxs-lookup"><span data-stu-id="d71cd-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="d71cd-105">本節說明如何部署多個公用交換電話網絡（PSTN）網站。</span><span class="sxs-lookup"><span data-stu-id="d71cd-105">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="d71cd-106">使用與部署單一網站相同的步驟，一次部署一個網站。</span><span class="sxs-lookup"><span data-stu-id="d71cd-106">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="d71cd-107">本主題說明多重網站部署中的網站與差異的考慮。</span><span class="sxs-lookup"><span data-stu-id="d71cd-107">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="d71cd-108">多個公用交換電話網絡（PSTN）網站</span><span class="sxs-lookup"><span data-stu-id="d71cd-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="d71cd-109">下列顯示部署不同 PSTN 網站之商務用 Skype 雲端連接器版的範例配置。</span><span class="sxs-lookup"><span data-stu-id="d71cd-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="d71cd-110">開始部署前，請確定您的設定正確無誤。</span><span class="sxs-lookup"><span data-stu-id="d71cd-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="d71cd-111">PSTN 網站1</span><span class="sxs-lookup"><span data-stu-id="d71cd-111">PSTN Site 1</span></span>
  
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

<span data-ttu-id="d71cd-112">PSTN 網站2</span><span class="sxs-lookup"><span data-stu-id="d71cd-112">PSTN Site 2</span></span>
  
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

<span data-ttu-id="d71cd-113">針對您要新增的每個 PSTN 網站，按照在[雲端連接器中部署單一網站](deploy-a-single-site-in-cloud-connector.md)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d71cd-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d71cd-114">針對每個 PSTN 網站準備高可用性（HA）的共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="d71cd-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="d71cd-115">在 PSTN 網站之間，共用資料夾**必須**不同。</span><span class="sxs-lookup"><span data-stu-id="d71cd-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="d71cd-116">請勿對多個網站使用相同的共用資料夾。 ></span><span class="sxs-lookup"><span data-stu-id="d71cd-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="d71cd-117">高可用性（HA）與多網站部署的單一網站</span><span class="sxs-lookup"><span data-stu-id="d71cd-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="d71cd-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="d71cd-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="d71cd-119">下表列出單一網站與 HA 支援及多重網站部署之間的差異。</span><span class="sxs-lookup"><span data-stu-id="d71cd-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="d71cd-120">**類別**</span><span class="sxs-lookup"><span data-stu-id="d71cd-120">**Category**</span></span>|<span data-ttu-id="d71cd-121">**選項**</span><span class="sxs-lookup"><span data-stu-id="d71cd-121">**Item**</span></span>|<span data-ttu-id="d71cd-122">**含 HA 的單一網站**</span><span class="sxs-lookup"><span data-stu-id="d71cd-122">**Single-Site with HA**</span></span>|<span data-ttu-id="d71cd-123">**多網站**</span><span class="sxs-lookup"><span data-stu-id="d71cd-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d71cd-124">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-124">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-125">裝置主機名稱</span><span class="sxs-lookup"><span data-stu-id="d71cd-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="d71cd-126">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-127">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-128">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="d71cd-128">Setup</span></span>  <br/> |<span data-ttu-id="d71cd-129">共用資料夾</span><span class="sxs-lookup"><span data-stu-id="d71cd-129">Shared folder</span></span>  <br/> |<span data-ttu-id="d71cd-130">在多個裝置上需要**相同**的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="d71cd-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="d71cd-131">跨裝置需要**不同**的共用資料夾</span><span class="sxs-lookup"><span data-stu-id="d71cd-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="d71cd-132">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-132">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="d71cd-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="d71cd-134">跨裝置需要**相同**的網域</span><span class="sxs-lookup"><span data-stu-id="d71cd-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="d71cd-135">在 PSTN 網站上需要**同一個**網域</span><span class="sxs-lookup"><span data-stu-id="d71cd-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-136">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-136">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="d71cd-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="d71cd-138">網功能變數名稱稱和順序在各個裝置中應該是**相同**的</span><span class="sxs-lookup"><span data-stu-id="d71cd-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-139">網功能變數名稱稱和順序在 PSTN 網站中應該是**相同**的</span><span class="sxs-lookup"><span data-stu-id="d71cd-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-140">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-140">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-141">網站名稱</span><span class="sxs-lookup"><span data-stu-id="d71cd-141">Site name</span></span>  <br/> |<span data-ttu-id="d71cd-142">**相同**跨裝置的網站名稱</span><span class="sxs-lookup"><span data-stu-id="d71cd-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="d71cd-143">**不同**PSTN 網站上的網站名稱</span><span class="sxs-lookup"><span data-stu-id="d71cd-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-144">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-144">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-145">伺服器名稱</span><span class="sxs-lookup"><span data-stu-id="d71cd-145">Server names</span></span>  <br/> |<span data-ttu-id="d71cd-146">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-147">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-148">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-148">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-149">內部池 Fqdn</span><span class="sxs-lookup"><span data-stu-id="d71cd-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="d71cd-150">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-151">跨 PSTN 網站**相同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-152">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-152">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-153">內部 Ip</span><span class="sxs-lookup"><span data-stu-id="d71cd-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="d71cd-154">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-155">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-156">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-156">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-157">外部 FQDN</span><span class="sxs-lookup"><span data-stu-id="d71cd-157">External FQDN</span></span>  <br/> |<span data-ttu-id="d71cd-158">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-159">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-160">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-160">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-161">外部 Ip</span><span class="sxs-lookup"><span data-stu-id="d71cd-161">External IPs</span></span>  <br/> |<span data-ttu-id="d71cd-162">跨多個裝置**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-163">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-164">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-164">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-165">PSTN GW 設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="d71cd-166">跨裝置**相同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="d71cd-167">跨 PSTN 網站**不同**</span><span class="sxs-lookup"><span data-stu-id="d71cd-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="d71cd-168">設定</span><span class="sxs-lookup"><span data-stu-id="d71cd-168">Configure</span></span>  <br/> |<span data-ttu-id="d71cd-169">DNS 記錄</span><span class="sxs-lookup"><span data-stu-id="d71cd-169">DNS record</span></span>  <br/> |<span data-ttu-id="d71cd-170">使用**相同**的外部存取 fqdn 和**不同**的 IP 位址新增記錄</span><span class="sxs-lookup"><span data-stu-id="d71cd-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="d71cd-171">新增具有**不同**外部存取 fqdn 及**不同**IP 位址的記錄</span><span class="sxs-lookup"><span data-stu-id="d71cd-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="d71cd-172">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="d71cd-172">Setup</span></span>  <br/> |<span data-ttu-id="d71cd-173">混合式租使用者</span><span class="sxs-lookup"><span data-stu-id="d71cd-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="d71cd-174">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="d71cd-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="d71cd-175">設定 PeerDestination 以進行回退</span><span class="sxs-lookup"><span data-stu-id="d71cd-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="d71cd-176">設定 HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="d71cd-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="d71cd-177">設定 PeerDestination 以進行回退</span><span class="sxs-lookup"><span data-stu-id="d71cd-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="d71cd-178">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="d71cd-178">Setup</span></span>  <br/> |<span data-ttu-id="d71cd-179">關</span><span class="sxs-lookup"><span data-stu-id="d71cd-179">Gateway</span></span>  <br/> |<span data-ttu-id="d71cd-180">此網站中的 MS GW **M:N**對應</span><span class="sxs-lookup"><span data-stu-id="d71cd-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="d71cd-181">每個 PSTN 網站中的 PSTN 閘道應該只會連線到相同網站中的中繼伺服器（s）</span><span class="sxs-lookup"><span data-stu-id="d71cd-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="d71cd-182">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="d71cd-182">Setup</span></span>  <br/> |<span data-ttu-id="d71cd-183">使用者</span><span class="sxs-lookup"><span data-stu-id="d71cd-183">User</span></span>  <br/> |<span data-ttu-id="d71cd-184">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="d71cd-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="d71cd-185">設定 UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="d71cd-185">Set UserPSTNSettings</span></span>  <br/> |
   

