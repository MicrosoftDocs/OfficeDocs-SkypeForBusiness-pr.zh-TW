---
title: 商務用 Skype Server 的高級 Edge Server DNS 規劃
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 摘要：商務用 Skype Server 部署選項的審查案例。 不管您是想要單一伺服器或喜歡使用 DNS 或 HLB 的伺服器集區，本主題都應該有所説明。
ms.openlocfilehash: 8615e0111385163b73558e5b76130f670f5d2db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813823"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="27be1-104">商務用 Skype Server 的高級 Edge Server DNS 規劃</span><span class="sxs-lookup"><span data-stu-id="27be1-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="27be1-105">**摘要：** 查看商務用 Skype Server 部署選項的案例。</span><span class="sxs-lookup"><span data-stu-id="27be1-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="27be1-106">不管您是想要單一伺服器或喜歡使用 DNS 或 HLB 的伺服器集區，本主題都應該有所説明。</span><span class="sxs-lookup"><span data-stu-id="27be1-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="27be1-107">在網域名稱系統 (DNS) 規劃商務用 Skype Server 時，可能會有許多因素可納入您的決策。</span><span class="sxs-lookup"><span data-stu-id="27be1-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="27be1-108">如果您的組織的域結構已存在，這可能是複查您要繼續的方式。</span><span class="sxs-lookup"><span data-stu-id="27be1-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="27be1-109">我們將從以下找到的主題開始：</span><span class="sxs-lookup"><span data-stu-id="27be1-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="27be1-110">商務用 Skype 用戶端尋找服務的演練</span><span class="sxs-lookup"><span data-stu-id="27be1-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="27be1-111">裂腦 DNS</span><span class="sxs-lookup"><span data-stu-id="27be1-111">Split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="27be1-112">沒有 split-大腦 DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="27be1-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="27be1-113">DNS 災難修復</span><span class="sxs-lookup"><span data-stu-id="27be1-113">DNS disaster recovery</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="27be1-114">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="27be1-114">DNS load balancing</span></span>](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="27be1-115">商務用 Skype 用戶端尋找服務的演練</span><span class="sxs-lookup"><span data-stu-id="27be1-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="27be1-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="27be1-116"><a name="WalkthroughOfSkype"> </a></span></span>

<span data-ttu-id="27be1-117">商務用 skype 用戶端與舊版的 Lync 用戶端類似于在商務用 Skype Server 中尋找及存取服務的方式。</span><span class="sxs-lookup"><span data-stu-id="27be1-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="27be1-118">本節詳細說明伺服器位置的處理常式。</span><span class="sxs-lookup"><span data-stu-id="27be1-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="27be1-119">lyncdiscoverinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="27be1-120">*這是內部 web 服務上的自動探索服務的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="27be1-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="27be1-121">lyncdiscover.\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="27be1-122">*這是外部 web 服務上的自動探索服務的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="27be1-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="27be1-123">_sipinternaltls _sipinternaltls._tcp。\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="27be1-124">*這是內部 TLS 連線的 SRV 記錄。*</span><span class="sxs-lookup"><span data-stu-id="27be1-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="27be1-125">_sip _sip._tls。\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="27be1-126">*這是外部 TLS 連線的 SRV 記錄。*</span><span class="sxs-lookup"><span data-stu-id="27be1-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="27be1-127">sipinternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="27be1-128">*這是前端集區或 Director 的主機記錄，只能在內部網路上加以解析。*</span><span class="sxs-lookup"><span data-stu-id="27be1-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="27be1-129">Sip。\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="27be1-130">*這是前端集區或 Director 的主機記錄，只能在內部網路上加以解析。*</span><span class="sxs-lookup"><span data-stu-id="27be1-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="27be1-131">sipexternal.\<domain\></span><span class="sxs-lookup"><span data-stu-id="27be1-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="27be1-132">*當用戶端為外部用戶端時，這是 Access Edge service 的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="27be1-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="27be1-133">自動探索服務的慣用習慣是服務位置的慣用方法，其他是 fallback 方法。</span><span class="sxs-lookup"><span data-stu-id="27be1-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27be1-134">當您建立 SRV 記錄時，請務必記住，如果您要使用 IPv6 定址) 在所建立 DNS SRV 記錄的相同網域中，則必須記住這些記錄必須指向 DNS A (和 AAAA。</span><span class="sxs-lookup"><span data-stu-id="27be1-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="27be1-135">例如，如果他們的 SRV 記錄在 contoso.com 中，則 (和 AAAA) 記錄會指向 fabrikam.com。</span><span class="sxs-lookup"><span data-stu-id="27be1-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="27be1-136">如果您很傾向這麼做，您可以將行動裝置設定為可供手動探索服務。</span><span class="sxs-lookup"><span data-stu-id="27be1-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="27be1-137">如果這是您想要做的事，每個使用者都必須使用完整的內部及外部自動探索服務 URIs （包括通訊協定和路徑）來設定其行動裝置設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="27be1-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="27be1-138">若為外部存取： HTTPs:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root</span><span class="sxs-lookup"><span data-stu-id="27be1-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="27be1-139">若為內部存取： HTTPs:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root</span><span class="sxs-lookup"><span data-stu-id="27be1-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="27be1-140">我們建議您使用「自動探索」，而非手動探索。</span><span class="sxs-lookup"><span data-stu-id="27be1-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="27be1-141">不過，如果您要進行一些疑難排解或測試，手動設定會非常有用。</span><span class="sxs-lookup"><span data-stu-id="27be1-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="27be1-142">裂腦 DNS</span><span class="sxs-lookup"><span data-stu-id="27be1-142">Split-brain DNS</span></span>
<span data-ttu-id="27be1-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="27be1-143"><a name="SplitBrainDNS"> </a></span></span>

<span data-ttu-id="27be1-144">這是您有兩個具有相同命名空間的 DNS 區域的 DNS 設定。</span><span class="sxs-lookup"><span data-stu-id="27be1-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="27be1-145">第一個 DNS 區域會處理內部要求，而第二個 DNS 區域會處理外部要求。</span><span class="sxs-lookup"><span data-stu-id="27be1-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="27be1-146">為什麼公司會這麼做？</span><span class="sxs-lookup"><span data-stu-id="27be1-146">Why would a company do this?</span></span> <span data-ttu-id="27be1-147">他們可能需要在內部和外部使用相同的命名空間，但當然，這會導致許多 DNS SRV 和記錄在某個區域或另一個區域中是唯一的，而且有重複的記錄，與這些記錄相關聯的 IP 位址會是唯一的。</span><span class="sxs-lookup"><span data-stu-id="27be1-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="27be1-148">這會帶來一些挑戰。</span><span class="sxs-lookup"><span data-stu-id="27be1-148">This presents some challenges.</span></span> <span data-ttu-id="27be1-149">最重要的是， **不支援** 行動性的大腦 DNS。</span><span class="sxs-lookup"><span data-stu-id="27be1-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="27be1-150">這是因為 LyncDiscover 和 LyncDiscoverInternal DNS 記錄 (LyncDiscover 必須在外部 DNS 伺服器上定義，而 LyncDiscoverInternal 必須在內部 DNS 伺服器上定義) 。</span><span class="sxs-lookup"><span data-stu-id="27be1-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="27be1-151">我們將在這裡列出內部及外部區域的 DNS 記錄，但您可以在 Edge Server 環境需求區段中尋找詳細的範例。</span><span class="sxs-lookup"><span data-stu-id="27be1-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="27be1-152">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="27be1-152">Internal DNS</span></span>

- <span data-ttu-id="27be1-153">包含名為 (的 DNS 區域，例如) contoso.com，其具有權威性。</span><span class="sxs-lookup"><span data-stu-id="27be1-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="27be1-154">這個內部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="27be1-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="27be1-155">DNS A 和 AAAA (如果您要使用 IPv6 定址) 前端集區、Director 集區或 Director 集區名稱，以及組織網路中執行商務用 Skype Server 的所有內部伺服器的記錄。</span><span class="sxs-lookup"><span data-stu-id="27be1-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="27be1-156">DNS A 和 AAAA (如果您為周邊網路中每個商務用 Skype Server Edge Server 的 Edge 內部介面使用 IPv6 定址) 記錄。</span><span class="sxs-lookup"><span data-stu-id="27be1-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="27be1-157">DNS A 和 AAAA (如果您要使用 IPv6 定址周邊 (網路中每個反向 proxy 伺服器的內部介面) 記錄，這是對反向 proxy) 的管理的 **選用** 。</span><span class="sxs-lookup"><span data-stu-id="27be1-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="27be1-158">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄供內部商務用 Skype Server 用戶端 (自動進行處理，則為 **選用** 的 ) 。</span><span class="sxs-lookup"><span data-stu-id="27be1-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="27be1-159">DNS A 和 AAAA (如果您使用 IPv6 定址) 或 CNAME 記錄來自動探索商務用 Skype Server Web 服務 (是 **選用** 的 ) 。</span><span class="sxs-lookup"><span data-stu-id="27be1-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="27be1-160">您周邊網路中的所有商務用 Skype 伺服器內部 Edge 介面都會使用此內部 DNS 區域來解析 contoso.com 的查詢。</span><span class="sxs-lookup"><span data-stu-id="27be1-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="27be1-161">所有執行商務用 Skype 伺服器的伺服器，而且在公司網路中執行商務用 Skype Server 的用戶端，指向內部 DNS 伺服器來解析對 contoso.com 的查詢，或在每個 Edge Server 上使用主機檔案，如果您要針對 Director 或 Director 集區 vip、前端集區 VIP 或 Standard Edition server) ，使用 IPv6 定址) 的下一個躍點伺服器的記錄，則為 A 和 AAAA ( (。</span><span class="sxs-lookup"><span data-stu-id="27be1-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="27be1-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="27be1-162">External DNS</span></span>

- <span data-ttu-id="27be1-163">包含名為 (的 DNS 區域，例如) contoso.com，其具有權威性。</span><span class="sxs-lookup"><span data-stu-id="27be1-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="27be1-164">此外部 contoso.com 包含：</span><span class="sxs-lookup"><span data-stu-id="27be1-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="27be1-165">如果您是使用 IPv6 定址) 或 CNAME 記錄來自動探索商務用 Skype Server web 服務，則 DNS A 和 AAAA (。</span><span class="sxs-lookup"><span data-stu-id="27be1-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="27be1-166">這與行動性搭配使用。</span><span class="sxs-lookup"><span data-stu-id="27be1-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="27be1-167">DNS A 和 AAAA (如果您要使用 IPv6 定址) 和 SRV 記錄，以供每個商務用 Skype Server Edge Server 或硬體負載平衡 (HLB) VIP 在周邊網路中。</span><span class="sxs-lookup"><span data-stu-id="27be1-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="27be1-168">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 記錄的反向 proxy 伺服器或 (VIP 集區的反向 proxy 伺服器集區（在周邊網路中) ）。</span><span class="sxs-lookup"><span data-stu-id="27be1-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="27be1-169">DNS A 和 AAAA (如果您使用 IPv6 定址) 和 SRV 的商務用 Skype Server 用戶端自動進行記錄 ( **選用** ) 。</span><span class="sxs-lookup"><span data-stu-id="27be1-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration ( **optional** ).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="27be1-170">沒有 split-大腦 DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="27be1-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="27be1-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="27be1-171"><a name="NoSplitBrainDNS"> </a></span></span>

<span data-ttu-id="27be1-172">如果您未使用「分裂大腦 DNS」，除非您使用我們在這裡提供的其中一個變通方法，否則執行商務用 Skype 之用戶端的內部自動設定將無法運作。</span><span class="sxs-lookup"><span data-stu-id="27be1-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="27be1-173">為什麼？</span><span class="sxs-lookup"><span data-stu-id="27be1-173">Why not?</span></span> <span data-ttu-id="27be1-174">由於商務用 Skype Server 需要使用者的 SIP URI，以符合為自動設定指定之前端集區的網域。</span><span class="sxs-lookup"><span data-stu-id="27be1-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="27be1-175">這尚未從舊版的 Lync Server 變更。</span><span class="sxs-lookup"><span data-stu-id="27be1-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="27be1-176">因此，如果您有兩個使用中的 SIP 網域，則需要下列 DNS SRV 記錄：</span><span class="sxs-lookup"><span data-stu-id="27be1-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="27be1-177">_sipinternaltls _sipinternaltls._tcp .com。</span><span class="sxs-lookup"><span data-stu-id="27be1-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="27be1-178">pool01.contoso.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="27be1-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="27be1-179">*如果使用者登入 bob@contoso.com，則此記錄可用於自動設定，因為使用者的 SIP 網域會符合前端集區的網域 (contoso.com) 。*</span><span class="sxs-lookup"><span data-stu-id="27be1-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="27be1-180">_sipinternaltls _sipinternaltls._tcp .com。</span><span class="sxs-lookup"><span data-stu-id="27be1-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="27be1-181">pool01.fabrikam.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="27be1-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="27be1-182">*如果使用者登入 alice@fabrikam.com，則此記錄會在第二個網域的自動設定中運作，因為 SIP 網域符合該網域的前端集區。*</span><span class="sxs-lookup"><span data-stu-id="27be1-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="27be1-183">若要進一步採取此範例，這將無法運作：</span><span class="sxs-lookup"><span data-stu-id="27be1-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="27be1-184">_sipinternaltls _sipinternaltls._tcp 的 litwareinc。</span><span class="sxs-lookup"><span data-stu-id="27be1-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="27be1-185">pool01.fabrikam.com SRV 0 0 5061 中的86400</span><span class="sxs-lookup"><span data-stu-id="27be1-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="27be1-186">*以 tim@litwareinc.com 登入的使用者無法自動設定，因為他的 SIP 網域 (litwareinc.com) 與集區中的網域不相符 (fabrikam.com) 。*</span><span class="sxs-lookup"><span data-stu-id="27be1-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="27be1-187">現在，我們已知道，如果您需要自動要求商務用 Skype 用戶端（不含分裂大腦 DNS），您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="27be1-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="27be1-188">**群組原則物件**</span><span class="sxs-lookup"><span data-stu-id="27be1-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="27be1-189">您可以使用「Gpo)  (的群組原則物件，以填入正確的伺服器值。</span><span class="sxs-lookup"><span data-stu-id="27be1-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="27be1-190">此選項不會啟用自動設定，但會自動進行手動設定。</span><span class="sxs-lookup"><span data-stu-id="27be1-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="27be1-191">若使用此方法，則不需要與自動設定相關聯的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="27be1-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="27be1-192">**相符的內部區域**</span><span class="sxs-lookup"><span data-stu-id="27be1-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="27be1-193">您必須在內部 DNS 中建立與您的外部 DNS 區域相符的區域 (例如，contoso.com) ， (然後在您使用 IPv6 位址) 記錄，而這些記錄對應到用於自動設定的商務用 Skype 伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="27be1-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="27be1-194">例如，如果您擁有位於 pool01.contoso.net 上的使用者，但登入商務用 Skype 的 bob@contoso.com，請建立名為 contoso.com 的內部 DNS 區域，並在此區域內建立 DNS A (和 AAAA （如果 IPv6 定址) pool01.contoso.com 的記錄）。</span><span class="sxs-lookup"><span data-stu-id="27be1-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="27be1-195">**Pin 點內部區域**</span><span class="sxs-lookup"><span data-stu-id="27be1-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="27be1-196">若在內部 DNS 中建立整個區域不是您的選項，您可以建立 pin 點 (專用的) 區域，該區域會對應至自動設定所需的 SRV 記錄，並使用 dnscmd.exe 填入這些區域。</span><span class="sxs-lookup"><span data-stu-id="27be1-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="27be1-197">因為 DNS 使用者介面不支援建立 pin 點區域，所以需要 Dnscmd.exe。</span><span class="sxs-lookup"><span data-stu-id="27be1-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="27be1-198">例如，如果您的 SIP 網域是 contoso.com，而且您有一個名為 pool01 的前端集區，其中包含兩部前端伺服器，則您必須在內部 DNS 中包含下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="27be1-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="27be1-199">在您的環境中，您可能會有第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="27be1-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="27be1-200">在此情況下，您必須在內部 DNS 中包含下列 pin 點區域和記錄：</span><span class="sxs-lookup"><span data-stu-id="27be1-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="27be1-201">您會看到前端集區 FQDN 顯示兩次，但有兩個不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="27be1-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="27be1-202">這是因為使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="27be1-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="27be1-203">如果使用 HLB，則只有一個前端集區專案。</span><span class="sxs-lookup"><span data-stu-id="27be1-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="27be1-204">此外，contoso.com 與 fabrikam.com 範例間的前端集區 FQDN 值也會變更，但 IP 位址仍然保持不變。</span><span class="sxs-lookup"><span data-stu-id="27be1-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="27be1-205">這是因為從任一 SIP 網域登入的使用者，將會使用相同的前端集區進行自動設定。</span><span class="sxs-lookup"><span data-stu-id="27be1-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="27be1-206">DNS 災難修復</span><span class="sxs-lookup"><span data-stu-id="27be1-206">DNS disaster recovery</span></span>
<span data-ttu-id="27be1-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="27be1-207"><a name="DNSDR"> </a></span></span>

<span data-ttu-id="27be1-208">若要設定 DNS 將商務用 Skype 伺服器網頁流量重新導向至您的嚴重損壞 (DR) 和容錯移轉網站，您必須使用支援 GeoDNS 的 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="27be1-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="27be1-209">您可以設定您的 DNS 記錄以支援嚴重損壞修復，這樣即使一個整個前端集區中斷時，使用 web 服務的功能仍會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="27be1-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="27be1-210">這項 DR 功能支援自動探索、符合和撥入簡易 URLs。</span><span class="sxs-lookup"><span data-stu-id="27be1-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="27be1-211">您可以定義及設定其他 DNS 主機 A (AAAA （如果使用 IPv6) GeoDNS 提供者的內部及外部 web 服務的記錄）。</span><span class="sxs-lookup"><span data-stu-id="27be1-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="27be1-212">下列詳細資料假設成對的集區、地理位置上的集區，以及您 **的提供者** 所支援的 GeoDNS 都具有迴圈 DNS， **或** 設定為使用 Pool1 做為主要，並在發生任何通信遺失或電源故障時，容錯移轉至 Pool2。</span><span class="sxs-lookup"><span data-stu-id="27be1-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="27be1-213">此表格中的所有 DNS 記錄皆為範例。</span><span class="sxs-lookup"><span data-stu-id="27be1-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="27be1-214">**GeoDNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="27be1-214">**GeoDNS record**</span></span>|<span data-ttu-id="27be1-215">**集區記錄**</span><span class="sxs-lookup"><span data-stu-id="27be1-215">**Pool records**</span></span>|<span data-ttu-id="27be1-216">**CNAME 記錄**</span><span class="sxs-lookup"><span data-stu-id="27be1-216">**CNAME records**</span></span>|<span data-ttu-id="27be1-217">**DNS 設定 (選取一個選項)**</span><span class="sxs-lookup"><span data-stu-id="27be1-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="27be1-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-221">Meet.contoso.com 至 Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-221">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="27be1-222">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-222">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-223">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-223">**OR**</span></span> <br/> <span data-ttu-id="27be1-224">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-224">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-225">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-225">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-226">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-226">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-227">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-227">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-228">Meet.contoso.com 至 Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-228">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>   <br/> |<span data-ttu-id="27be1-229">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-229">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-230">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-230">**OR**</span></span> <br/> <span data-ttu-id="27be1-231">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-231">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-232">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-232">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-233">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-233">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-234">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-234">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-235">Meet.contoso.com 至 Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-235">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="27be1-236">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-236">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-237">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-237">**OR**</span></span> <br/> <span data-ttu-id="27be1-238">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-238">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-239">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-239">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-240">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-240">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-241">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-241">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-242">Meet.contoso.com 至 Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-242">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="27be1-243">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-243">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-244">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-244">**OR**</span></span> <br/> <span data-ttu-id="27be1-245">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-245">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-246">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-246">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-247">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-247">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-248">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-248">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-249">Meet.contoso.com 至 Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-249">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>   <br/> |<span data-ttu-id="27be1-250">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-250">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-251">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-251">**OR**</span></span> <br/> <span data-ttu-id="27be1-252">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-252">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-253">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-253">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-254">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-254">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-255">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-255">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-256">Meet.contoso.com 至 Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-256">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>  <br/>  <br/> |<span data-ttu-id="27be1-257">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-257">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-258">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-258">**OR**</span></span> <br/> <span data-ttu-id="27be1-259">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-259">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-260">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-260">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-261">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-261">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-262">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-262">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-263">Meet.contoso.com 至 Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-263">Meet.contoso.com to Meet-int.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="27be1-264">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-264">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-265">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-265">**OR**</span></span> <br/> <span data-ttu-id="27be1-266">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-266">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="27be1-267">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-267">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-268">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-268">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="27be1-269">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-269">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-270">Meet.contoso.com 至 Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-270">Meet.contoso.com to Meet-ext.geolb.contoso.com</span></span>   <br/>  <br/> |<span data-ttu-id="27be1-271">集區間的迴圈</span><span class="sxs-lookup"><span data-stu-id="27be1-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="27be1-272">**OR**</span><span class="sxs-lookup"><span data-stu-id="27be1-272">**OR**</span></span> <br/> <span data-ttu-id="27be1-273">使用主要，如果發生故障，請連接至次要。</span><span class="sxs-lookup"><span data-stu-id="27be1-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="27be1-274">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="27be1-274">DNS load balancing</span></span>
<span data-ttu-id="27be1-275"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="27be1-275"><a name="DNSLB"> </a></span></span>

<span data-ttu-id="27be1-276">DNS 負載平衡通常是在應用層級實施。</span><span class="sxs-lookup"><span data-stu-id="27be1-276">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="27be1-277">應用程式 (例如，執行商務用 Skype) 的用戶端會嘗試連線至集區中從 DNS A 和 (AAAA 傳回的其中一個 IP 位址，但如果 IPv6 定址是用於集區 FQDN) 記錄查詢，則會嘗試連線至集區中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="27be1-277">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="27be1-278">例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="27be1-278">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="27be1-279">執行商務用 Skype For pool01.contoso.com 的用戶端查詢 DNS。</span><span class="sxs-lookup"><span data-stu-id="27be1-279">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="27be1-280">查詢會傳回三個 IP 位址，並將它們快取為 (依某些順序) ：</span><span class="sxs-lookup"><span data-stu-id="27be1-280">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="27be1-281">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-281">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-282">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="27be1-282">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="27be1-283">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-283">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-284">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="27be1-284">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="27be1-285">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="27be1-285">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="27be1-286">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="27be1-286">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="27be1-287">用戶端嘗試建立與其中一個 IP 位址的 TCP 連接。</span><span class="sxs-lookup"><span data-stu-id="27be1-287">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="27be1-288">如果失敗，它會嘗試從該清單快取的下一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="27be1-288">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="27be1-289">如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="27be1-289">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="27be1-290">如果用戶端嘗試所有快取的專案但沒有成功的連線，使用者會收到通知，指出目前沒有任何執行商務用 Skype Server 的伺服器可供使用。</span><span class="sxs-lookup"><span data-stu-id="27be1-290">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="27be1-291">DNS 的負載平衡不同于 DNS 迴圈 (DNS RR) ，它通常是指以 DNS 為集區中的伺服器提供不同的 IP 位址順序的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="27be1-291">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="27be1-292">通常，DNS RR 會啟用負載分配，但不會允許您啟用容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="27be1-292">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="27be1-293">例如，如果您在 IPv6 案例中的 DNS A (或 AAAA 所傳回的一個 IP 位址的連線) 查詢會失敗，該連線會失敗。</span><span class="sxs-lookup"><span data-stu-id="27be1-293">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="27be1-294">這會使 DNS RR 不如以 DNS 為基礎的負載平衡更可靠。</span><span class="sxs-lookup"><span data-stu-id="27be1-294">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="27be1-295">如果您需要這麼做，您仍然可以搭配 DNS 的負載平衡使用 DNS RR。</span><span class="sxs-lookup"><span data-stu-id="27be1-295">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="27be1-296">您可以使用 DNS 負載平衡來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="27be1-296">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="27be1-297">將伺服器對伺服器 SIP 的負載平衡至 Edge server。</span><span class="sxs-lookup"><span data-stu-id="27be1-297">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="27be1-298">負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留。</span><span class="sxs-lookup"><span data-stu-id="27be1-298">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="27be1-299">防止新的連線 UCAS 應用程式 (也稱為排出) 。</span><span class="sxs-lookup"><span data-stu-id="27be1-299">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="27be1-300">負載平衡用戶端和 Edge server 之間的所有用戶端對伺服器流量。</span><span class="sxs-lookup"><span data-stu-id="27be1-300">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="27be1-301">您不能使用的 DNS 負載平衡：</span><span class="sxs-lookup"><span data-stu-id="27be1-301">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="27be1-302">您的前端伺服器或 Director 的用戶端對伺服器網頁流量。</span><span class="sxs-lookup"><span data-stu-id="27be1-302">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="27be1-303">若要深入瞭解當查詢傳回 mutiple DNS 記錄時，如何選取 DNS SRV 記錄，Access Edge service 一定會以最低的數值優先順序來挑選記錄，而且如果需要斷詞，則最高的數值權重。</span><span class="sxs-lookup"><span data-stu-id="27be1-303">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="27be1-304">這與 [網際網路工程任務強制檔](https://www.ietf.org/rfc/rfc2782.txt)一致。</span><span class="sxs-lookup"><span data-stu-id="27be1-304">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="27be1-305">舉例來說，如果您的第一個 DNS SRV 記錄的權重為20，優先順序為40，而第二個 DNS SRV 記錄的權重為10，優先順序為50，則第一筆記錄會因其優先順序低於40而選取。</span><span class="sxs-lookup"><span data-stu-id="27be1-305">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="27be1-306">優先順序一定會先開始，也就是用戶端將優先進行目標的主機。</span><span class="sxs-lookup"><span data-stu-id="27be1-306">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="27be1-307">如果有兩個具有相同優先順序的目標，該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="27be1-307">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="27be1-308">在此情況下，會考慮重量。</span><span class="sxs-lookup"><span data-stu-id="27be1-308">In that case, weight comes into consideration.</span></span> <span data-ttu-id="27be1-309">在此情況下，應將較大的權重指定為非常高的概率。</span><span class="sxs-lookup"><span data-stu-id="27be1-309">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="27be1-310">DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。</span><span class="sxs-lookup"><span data-stu-id="27be1-310">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="27be1-311">當記錄中包含的權重大於0時，具有權重0的記錄會有極小的進入選擇狀態。</span><span class="sxs-lookup"><span data-stu-id="27be1-311">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="27be1-312">那麼，當傳回具有相同優先順序和權重的多個 DNS SRV 記錄時，會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="27be1-312">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="27be1-313">在此情況下，Access Edge service 會從 DNS 伺服器開始選擇它所獲得的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="27be1-313">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

