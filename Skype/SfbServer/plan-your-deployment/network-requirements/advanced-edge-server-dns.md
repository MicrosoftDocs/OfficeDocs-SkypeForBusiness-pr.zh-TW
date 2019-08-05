---
title: 商務用 Skype Server 的高級邊緣伺服器 DNS 規劃
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: '摘要: 查看商務用 Skype Server 部署選項的案例。 無論您是要使用單一伺服器或慣用伺服器池 (含 DNS 或 HLB), 本主題都應該有所協助。'
ms.openlocfilehash: 6507f0ae0cae0712b261bfb772d5da9e528d3994
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2019
ms.locfileid: "36194097"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a><span data-ttu-id="1616a-104">商務用 Skype Server 的高級邊緣伺服器 DNS 規劃</span><span class="sxs-lookup"><span data-stu-id="1616a-104">Advanced Edge Server DNS planning for Skype for Business Server</span></span>
 
<span data-ttu-id="1616a-105">**摘要:** 查看商務用 Skype Server 部署選項的案例。</span><span class="sxs-lookup"><span data-stu-id="1616a-105">**Summary:** Review scenarios for Skype for Business Server deployment options.</span></span> <span data-ttu-id="1616a-106">無論您是要使用單一伺服器或慣用伺服器池 (含 DNS 或 HLB), 本主題都應該有所協助。</span><span class="sxs-lookup"><span data-stu-id="1616a-106">Whether you want a single server or prefer a server pool with DNS or HLB, this topic should help.</span></span>
  
<span data-ttu-id="1616a-107">當您參與商務用 Skype Server 的網域名稱系統 (DNS) 規劃時, 可能會有許多因素可供您決定。</span><span class="sxs-lookup"><span data-stu-id="1616a-107">When it comes to Domain Name System (DNS) planning for Skype for Business Server, there are a lot of factors that may play into your decision.</span></span> <span data-ttu-id="1616a-108">如果貴組織的網域結構已經存在, 這可能是審查您要如何繼續進行的一個重要做法。</span><span class="sxs-lookup"><span data-stu-id="1616a-108">If your organization's domain structure's already in place, this may be a matter of reviewing how you're going to proceed.</span></span> <span data-ttu-id="1616a-109">我們將從以下所述的主題開始:</span><span class="sxs-lookup"><span data-stu-id="1616a-109">We'll begin with the topics found below:</span></span>
  
- [<span data-ttu-id="1616a-110">商務用 Skype 用戶端尋找服務的逐步解說</span><span class="sxs-lookup"><span data-stu-id="1616a-110">Walkthrough of Skype for Business clients locating services</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [<span data-ttu-id="1616a-111">分割大腦 DNS</span><span class="sxs-lookup"><span data-stu-id="1616a-111">Split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [<span data-ttu-id="1616a-112">不含分裂的 DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="1616a-112">Automatic configuration without split-brain DNS</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [<span data-ttu-id="1616a-113">DNS 災害復原</span><span class="sxs-lookup"><span data-stu-id="1616a-113">DNS disaster recovery</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [<span data-ttu-id="1616a-114">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1616a-114">DNS load balancing</span></span>](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a><span data-ttu-id="1616a-115">商務用 Skype 用戶端尋找服務的逐步解說</span><span class="sxs-lookup"><span data-stu-id="1616a-115">Walkthrough of Skype for Business clients locating services</span></span>
<span data-ttu-id="1616a-116"><a name="WalkthroughOfSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="1616a-116"></span></span>

<span data-ttu-id="1616a-117">商務用 skype 用戶端與舊版 Lync 用戶端類似于在商務用 Skype Server 中尋找及存取服務的方式。</span><span class="sxs-lookup"><span data-stu-id="1616a-117">Skype for Business clients are similar to previous versions of Lync clients in how they find and access services in Skype for Business Server.</span></span> <span data-ttu-id="1616a-118">本節詳細說明伺服器位置處理常式。</span><span class="sxs-lookup"><span data-stu-id="1616a-118">This section details the server location process.</span></span>
  
1. <span data-ttu-id="1616a-119">lyncdiscoverinternal.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-119">lyncdiscoverinternal.\<domain\></span></span>
    
     <span data-ttu-id="1616a-120">*這是內部 web 服務的自動探索服務的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="1616a-120">*This is an A host record for the Autodiscover service on the internal web services.*</span></span> 
    
2. <span data-ttu-id="1616a-121">lyncdiscover.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-121">lyncdiscover.\<domain\></span></span>
    
     <span data-ttu-id="1616a-122">*這是外部 web 服務的自動探索服務的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="1616a-122">*This is an A host record for the Autodiscover service on the external web services.*</span></span> 
    
3. <span data-ttu-id="1616a-123">_sipinternaltls._tcp.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-123">_sipinternaltls._tcp.\<domain\></span></span>
    
     <span data-ttu-id="1616a-124">*這是內部 TLS 連線的 SRV 記錄。*</span><span class="sxs-lookup"><span data-stu-id="1616a-124">*This is a SRV record for internal TLS connections.*</span></span> 
    
4. <span data-ttu-id="1616a-125">_sip._tls.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-125">_sip._tls.\<domain\></span></span>
    
     <span data-ttu-id="1616a-126">*這是外部 TLS 連線的 SRV 記錄。*</span><span class="sxs-lookup"><span data-stu-id="1616a-126">*This is a SRV record for external TLS connections.*</span></span> 
    
5. <span data-ttu-id="1616a-127">sipinternal.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-127">sipinternal.\<domain\></span></span>
    
     <span data-ttu-id="1616a-128">*這是前端池或控制器的主機記錄, 只能在內部網路上解析。*</span><span class="sxs-lookup"><span data-stu-id="1616a-128">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
6. <span data-ttu-id="1616a-129">呼吸.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-129">sip.\<domain\></span></span>
    
     <span data-ttu-id="1616a-130">*這是前端池或控制器的主機記錄, 只能在內部網路上解析。*</span><span class="sxs-lookup"><span data-stu-id="1616a-130">*This is an A host record for the Front End pool or Director, resolvable only on the internal network.*</span></span> 
    
7. <span data-ttu-id="1616a-131">sipexternal.\<網域\></span><span class="sxs-lookup"><span data-stu-id="1616a-131">sipexternal.\<domain\></span></span>
    
     <span data-ttu-id="1616a-132">*這是當用戶端為外部時, 存取邊緣服務的主機記錄。*</span><span class="sxs-lookup"><span data-stu-id="1616a-132">*This is an A host record for the Access Edge service, when the client is external.*</span></span> 
    
<span data-ttu-id="1616a-133">自動探索服務總是被認為是服務位置的首選方法, 而其他則是後備方法。</span><span class="sxs-lookup"><span data-stu-id="1616a-133">The Autodiscover service is always favored as that's the preferred method for service location, and the others are fallback methods.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1616a-134">當您建立 SRV 記錄時, 請務必記住, 必須在建立 DNS SRV 記錄的同一個網域中, 指向 DNS A (如果您使用的是 IPv6 定址, 則是 AAAA)。</span><span class="sxs-lookup"><span data-stu-id="1616a-134">When you're creating SRV records, it's important to remember that they need to point to a DNS A (and AAAA if you're using IPv6 addressing) in the same domain in which the DNS SRV record's being created.</span></span> <span data-ttu-id="1616a-135">例如, 如果其 SRV 記錄位於 contoso.com, 則其指向的 A (和 AAAA) 記錄不能位於 fabrikam.com 中。</span><span class="sxs-lookup"><span data-stu-id="1616a-135">For example, if they SRV record's in contoso.com, the A (and AAAA) record it points to can't be in fabrikam.com.</span></span> 
  
<span data-ttu-id="1616a-136">如果您傾向這樣做, 您可以將行動裝置設定為手動搜尋服務。</span><span class="sxs-lookup"><span data-stu-id="1616a-136">If you're inclined to do it, you can set your mobile device up for manual discovery of services.</span></span> <span data-ttu-id="1616a-137">如果這是您想要執行的動作, 每個使用者都需要使用完整的內部和外部自動探索服務 Uri 來設定其行動裝置設定, 包括通訊協定和路徑, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="1616a-137">If that's what you're looking to do, each user needs to configure their mobile device settings with the full internal and external Autodiscover service URIs, including the protocol and path, as follows:</span></span>
  
- <span data-ttu-id="1616a-138">外部存取: HTTPs://\<ExtPoolFQDN/Autodiscover/autodiscoverservice.svc/Root\></span><span class="sxs-lookup"><span data-stu-id="1616a-138">For external access: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root</span></span>
    
- <span data-ttu-id="1616a-139">內部存取: HTTPs://\<IntPoolFQDN/AutoDiscover/AutoDiscover.svc/Root\></span><span class="sxs-lookup"><span data-stu-id="1616a-139">For internal access: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root</span></span>
    
<span data-ttu-id="1616a-140">我們建議您使用 [自動探索], 而非手動搜尋。</span><span class="sxs-lookup"><span data-stu-id="1616a-140">We do recommend you use automatic discovery as opposed to manual discovery.</span></span> <span data-ttu-id="1616a-141">但如果您正在進行一些疑難排解或測試, 手動設定就很有説明。</span><span class="sxs-lookup"><span data-stu-id="1616a-141">But if you're doing some troubleshooting or testing, manual settings can be very helpful.</span></span>
  
## <a name="split-brain-dns"></a><span data-ttu-id="1616a-142">分割大腦 DNS</span><span class="sxs-lookup"><span data-stu-id="1616a-142">Split-brain DNS</span></span>
<span data-ttu-id="1616a-143"><a name="SplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="1616a-143"></span></span>

<span data-ttu-id="1616a-144">這是 DNS 配置, 您有兩個具有相同命名空間的 DNS 區域。</span><span class="sxs-lookup"><span data-stu-id="1616a-144">This is a DNS configuration where you have two DNS zones with the same namespace.</span></span> <span data-ttu-id="1616a-145">第一個 DNS 區域會處理內部要求, 而第二個 DNS 區域會處理外部要求。</span><span class="sxs-lookup"><span data-stu-id="1616a-145">The first DNS zone handles internal requests, while the second DNS zone handles external requests.</span></span>
  
<span data-ttu-id="1616a-146">公司為什麼要這麼做？</span><span class="sxs-lookup"><span data-stu-id="1616a-146">Why would a company do this?</span></span> <span data-ttu-id="1616a-147">它們可能需要在內部和外部使用相同的命名空間, 但當然這會造成許多 DNS SRV 與記錄在單一區域或另一個區域中都是唯一的, 而且有重複專案, 與這些記錄相關聯的 IP 位址將是唯一的。</span><span class="sxs-lookup"><span data-stu-id="1616a-147">They may have a requirement to use the same namespace internally and externally, but of course this will lead to many DNS SRV and A records being unique to one zone or another, and where there is duplication, the IP addresses associated with these records would be unique.</span></span>
  
<span data-ttu-id="1616a-148">這會帶來一些挑戰。</span><span class="sxs-lookup"><span data-stu-id="1616a-148">This presents some challenges.</span></span> <span data-ttu-id="1616a-149">最重要的是,**不支援**將分裂的 DNS 用於行動。</span><span class="sxs-lookup"><span data-stu-id="1616a-149">The most important is that split-brain DNS is **not supported** for Mobility.</span></span> <span data-ttu-id="1616a-150">這是因為 LyncDiscover 和 LyncDiscoverInternal 的 DNS 記錄 (LyncDiscover 必須在您的外部 DNS 伺服器上定義, 而 LyncDiscoverInternal 必須在您的內部 DNS 伺服器上定義)。</span><span class="sxs-lookup"><span data-stu-id="1616a-150">This is because of the LyncDiscover and LyncDiscoverInternal DNS records (LyncDiscover has to be defined on you external DNS server, while LyncDiscoverInternal has to be defined on your internal DNS server).</span></span>
  
<span data-ttu-id="1616a-151">我們將在這裡列出內部和外部區域的 DNS 記錄, 但您可以在 Edge 伺服器的 [環境需求] 區段中找到詳細範例。</span><span class="sxs-lookup"><span data-stu-id="1616a-151">We'll list the DNS records for the internal and external zones here, but you can find detailed examples on the Edge Server environmental requirements section.</span></span>
  
### <a name="internal-dns"></a><span data-ttu-id="1616a-152">內部 DNS</span><span class="sxs-lookup"><span data-stu-id="1616a-152">Internal DNS</span></span>

- <span data-ttu-id="1616a-153">包含名為 contoso.com 的 DNS 區域 (例如), 其為權威性。</span><span class="sxs-lookup"><span data-stu-id="1616a-153">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="1616a-154">這個內部 contoso.com 包含:</span><span class="sxs-lookup"><span data-stu-id="1616a-154">This internal contoso.com contains:</span></span>
    
  - <span data-ttu-id="1616a-155">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 適用于您的前端池、主管池或控制器池名稱, 以及在貴組織的網路中執行商務用 Skype 伺服器的所有內部伺服器。</span><span class="sxs-lookup"><span data-stu-id="1616a-155">DNS A and AAAA (if you're using IPv6 addressing) records for your Front End pool, Director pool or Director pool name, and all internal servers running Skype for Business Server in your organization's network.</span></span>
    
  - <span data-ttu-id="1616a-156">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 適用于周邊網路中每個商務用 Skype Server Edge 伺服器的邊緣內部介面的記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-156">DNS A and AAAA (if you're using IPv6 addressing) records for your Edge internal interface for each Skype for Business Server Edge Server in your perimeter network.</span></span>
    
  - <span data-ttu-id="1616a-157">DNS A 和 AAAA (如果您是使用 IPv6 定址), 用於提供周邊網路中每個反向 proxy 伺服器的內部介面 (這是對反向 proxy 管理的**選擇性**)。</span><span class="sxs-lookup"><span data-stu-id="1616a-157">DNS A and AAAA (if you're using IPv6 addressing) records for the internal interface of each reverse proxy server in your perimeter network (which is **optional** for management of a reverse proxy).</span></span>
    
  - <span data-ttu-id="1616a-158">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 以及內部商務用 Skype Server 用戶端自動設定 (**選用**) 的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-158">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for internal Skype for Business Server client autoconfiguration (which is **optional** ).</span></span>
    
  - <span data-ttu-id="1616a-159">DNS A 和 AAAA (如果您使用的是 IPv6 定址) 或 CNAME 記錄, 以自動探索商務用 Skype Server Web 服務 (**選用**)。</span><span class="sxs-lookup"><span data-stu-id="1616a-159">DNS A and AAAA (if you're using IPv6 addressing) or CNAME records for automatic discovery of Skype for Business Server Web Services (which is **optional** ).</span></span>
    
- <span data-ttu-id="1616a-160">您周邊網路中的所有商務用 Skype Server 內部邊緣介面都使用這個內部 DNS 區域來解析要 contoso.com 的查詢。</span><span class="sxs-lookup"><span data-stu-id="1616a-160">All your Skype for Business Server internal Edge interfaces in your perimeter network use this internal DNS zone for resolving queries to contoso.com.</span></span>
    
- <span data-ttu-id="1616a-161">所有執行商務用 Skype Server 的伺服器, 以及在商業網路中執行商務用 Skype Server 的用戶端, 指向 [內部 DNS 伺服器], 以便將查詢解析成 contoso.com, 或在每個 Edge 伺服器上使用主機檔案並列出 A 和 AAAA (如果您使用的是IPv6 定址) 適用于下一個躍點伺服器的記錄 (特別是主管或控制器池 VIP、前端池 VIP 或標準版伺服器)。</span><span class="sxs-lookup"><span data-stu-id="1616a-161">All servers running Skype for Business Server, and clients running Skype for Business Server in the corporate network, point to internal DNS servers for resolving queries to contoso.com, or they use the Host file on each Edge Server and list A and AAAA (if you're using IPv6 addressing) records for the next hop server (specifically for the Director or Director pool VIP, Front End pool VIP, or Standard Edition server).</span></span>
    
### <a name="external-dns"></a><span data-ttu-id="1616a-162">外部 DNS</span><span class="sxs-lookup"><span data-stu-id="1616a-162">External DNS</span></span>

- <span data-ttu-id="1616a-163">包含名為 contoso.com 的 DNS 區域 (例如), 其為權威性。</span><span class="sxs-lookup"><span data-stu-id="1616a-163">Contains a DNS zone called (for example) contoso.com, for which it's authoritative.</span></span>
    
- <span data-ttu-id="1616a-164">這個外部 contoso.com 包含:</span><span class="sxs-lookup"><span data-stu-id="1616a-164">This external contoso.com contains:</span></span>
    
  - <span data-ttu-id="1616a-165">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 或 CNAME 記錄, 以自動探索商務用 Skype Server web 服務。</span><span class="sxs-lookup"><span data-stu-id="1616a-165">DNS A and AAAA (if you're using IPv6 addressing), or CNAME records, for automatic discovery of Skype for Business Server web services.</span></span> <span data-ttu-id="1616a-166">這是與行動性搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1616a-166">This is for use with mobility.</span></span>
    
  - <span data-ttu-id="1616a-167">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 以及在周邊網路中每個商務用 Skype Server Edge 伺服器或硬體負載平衡 (HLB) VIP 的邊緣外部介面的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-167">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the Edge external interface of each Skype for Business Server Edge Server or hardware load balanced (HLB) VIP in the perimeter network.</span></span>
    
  - <span data-ttu-id="1616a-168">DNS A 和 AAAA (如果您使用的是 IPv6 定址), 以及適用于反向 proxy 伺服器的外部介面 (或反向 proxy 伺服器的 VIP), 請在周邊網路中取得。</span><span class="sxs-lookup"><span data-stu-id="1616a-168">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for the external interface of the Reverse proxy server or (VIP for a pool of Reverse proxy servers), in the perimeter network.</span></span>
    
  - <span data-ttu-id="1616a-169">DNS A 與 AAAA (如果您使用的是 IPv6 定址) 和商務用 Skype Server 用戶端自動設定的 SRV 記錄 (**選用**)。</span><span class="sxs-lookup"><span data-stu-id="1616a-169">DNS A and AAAA (if you're using IPv6 addressing) and SRV records for Skype for Business Server client autoconfiguration (**optional**).</span></span>
    
## <a name="automatic-configuration-without-split-brain-dns"></a><span data-ttu-id="1616a-170">不含分裂的 DNS 的自動設定</span><span class="sxs-lookup"><span data-stu-id="1616a-170">Automatic configuration without split-brain DNS</span></span>
<span data-ttu-id="1616a-171"><a name="NoSplitBrainDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="1616a-171"></span></span>

<span data-ttu-id="1616a-172">如果您不使用分割大腦 DNS, 除非您使用我們在這裡提供的其中一個因應措施, 否則執行商務用 Skype 之用戶端的內部自動設定將無法運作。</span><span class="sxs-lookup"><span data-stu-id="1616a-172">If you don't use split-brain DNS, internal automatic configuration of clients running Skype for Business won't work unless you're using one of the workarounds we have here.</span></span> <span data-ttu-id="1616a-173">為什麼不呢？</span><span class="sxs-lookup"><span data-stu-id="1616a-173">Why not?</span></span> <span data-ttu-id="1616a-174">因為商務用 Skype Server 需要使用者的 SIP URI, 以符合為自動設定所指定的前端池網域。</span><span class="sxs-lookup"><span data-stu-id="1616a-174">Because Skype for Business Server requires the user's SIP URI to match the domain of the Front End pool designated for automatic configuration.</span></span> <span data-ttu-id="1616a-175">這個版本沒有從舊版的 Lync Server 變更。</span><span class="sxs-lookup"><span data-stu-id="1616a-175">This hasn't changed from earlier versions of Lync Server.</span></span>
  
<span data-ttu-id="1616a-176">因此, 如果您有兩個 SIP 網域在使用中, 您就需要這些 DNS SRV 記錄:</span><span class="sxs-lookup"><span data-stu-id="1616a-176">So, if you have two SIP domains in use, you'd need these DNS SRV records:</span></span>
  
- <span data-ttu-id="1616a-177">_sipinternaltls _tcp。</span><span class="sxs-lookup"><span data-stu-id="1616a-177">_sipinternaltls._tcp.contoso.com.</span></span> <span data-ttu-id="1616a-178">在 SRV 0 0 5061 pool01.contoso.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1616a-178">86400 IN SRV 0 0 5061 pool01.contoso.com</span></span>
    
     <span data-ttu-id="1616a-179">*如果使用者登入 bob@contoso.com, 此記錄將可用於自動設定, 因為使用者的 SIP 網域會與前端池 (contoso.com) 的網域相符。*</span><span class="sxs-lookup"><span data-stu-id="1616a-179">*If a user signs in as bob@contoso.com, this record would work for automatic configuration, as the user's SIP domain matches the domain of the Front End pool (contoso.com).*</span></span> 
    
- <span data-ttu-id="1616a-180">_sipinternaltls _tcp。</span><span class="sxs-lookup"><span data-stu-id="1616a-180">_sipinternaltls._tcp.fabrikam.com.</span></span> <span data-ttu-id="1616a-181">在 SRV 0 0 5061 pool01.fabrikam.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1616a-181">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="1616a-182">*如果使用者登入 alice@fabrikam.com, 則此記錄將可用於自動設定第二個網域, 因為 SIP 網域符合該網域的 [前端] 池。*</span><span class="sxs-lookup"><span data-stu-id="1616a-182">*If a user signs in as alice@fabrikam.com, this record would work for automatic configuration of the second domain, again because the SIP domain matches the Front End pool for that domain.*</span></span> 
    
<span data-ttu-id="1616a-183">若要進一步執行這個範例, 這將無法運作:</span><span class="sxs-lookup"><span data-stu-id="1616a-183">To take the example further, this would not work:</span></span>
  
- <span data-ttu-id="1616a-184">_sipinternaltls _tcp。</span><span class="sxs-lookup"><span data-stu-id="1616a-184">_sipinternaltls._tcp.litwareinc.com.</span></span> <span data-ttu-id="1616a-185">在 SRV 0 0 5061 pool01.fabrikam.com 中的86400</span><span class="sxs-lookup"><span data-stu-id="1616a-185">86400 IN SRV 0 0 5061 pool01.fabrikam.com</span></span>
    
     <span data-ttu-id="1616a-186">*以 tim@litwareinc.com 登入的使用者無法使用自動設定, 因為其 SIP 網域 (litwareinc.com) 與池中的網域不相符 (fabrikam.com)。*</span><span class="sxs-lookup"><span data-stu-id="1616a-186">*A user signing in as tim@litwareinc.com won't work for automatic configuration, because his SIP domain (litwareinc.com) doesn't match the domain in the pool (fabrikam.com).*</span></span> 
    
<span data-ttu-id="1616a-187">現在我們知道, 如果您需要自動要求您的商務用 Skype 用戶端 (沒有分裂大腦 DNS), 您可以使用下列選項:</span><span class="sxs-lookup"><span data-stu-id="1616a-187">So now that we know all that, if you need automatic requirement for your Skype for Business clients without split-brain DNS, you have these options:</span></span>
  
- <span data-ttu-id="1616a-188">**群組原則物件**</span><span class="sxs-lookup"><span data-stu-id="1616a-188">**Group Policy Objects**</span></span>
    
    <span data-ttu-id="1616a-189">您可以使用群組原則物件 (Gpo) 來填入正確的伺服器值。</span><span class="sxs-lookup"><span data-stu-id="1616a-189">You can use Group Policy Objects (GPOs) to populate the correct server values.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1616a-190">這個選項不會啟用自動設定, 但會自動進行手動設定。</span><span class="sxs-lookup"><span data-stu-id="1616a-190">This option doesn't enable automatic configuration, but it does automate manual configuration.</span></span> <span data-ttu-id="1616a-191">如果使用這個方法, 就不需要與自動設定相關聯的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-191">If this approach is used, the SRV records associated with automatic configuration aren't required.</span></span> 
  
- <span data-ttu-id="1616a-192">**相符的內部區域**</span><span class="sxs-lookup"><span data-stu-id="1616a-192">**Matching internal zone**</span></span>
    
    <span data-ttu-id="1616a-193">您需要在內部 DNS 中建立與您的外部 DNS 區域相符的區域 (例如, contoso.com), 然後建立 DNS A (如果您使用的是 IPv6 定址) 與自動使用的商務用 Skype 伺服器池相對應的記錄 (如果您使用的是 AAAA)configuration.</span><span class="sxs-lookup"><span data-stu-id="1616a-193">You'll need to create a zone in your internal DNS that matches your external DNS zone (for example, contoso.com), and then create DNS A (and AAAA if you're using IPv6 addressing) records that correspond to the Skype for Business Server pool used for automatic configuration.</span></span>
    
    <span data-ttu-id="1616a-194">例如, 如果您的使用者是駐留在 pool01.contoso.net, 但登入商務用 Skype (bob@contoso.com), 請建立名為 contoso.com 的內部 DNS 區域, 並在其中建立 DNS A (以及 AAAA if IPv6 定址的使用) 記錄pool01.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="1616a-194">For example, if you have a user homed on pool01.contoso.net, but signs into Skype for Business as bob@contoso.com, create an internal DNS zone called contoso.com, and inside it you need to create a DNS A (and AAAA if IPv6 addressing's being used) record for pool01.contoso.com.</span></span>
    
- <span data-ttu-id="1616a-195">**固定點內部區域**</span><span class="sxs-lookup"><span data-stu-id="1616a-195">**Pin-point internal zone**</span></span>
    
    <span data-ttu-id="1616a-196">如果在內部 DNS 中建立整個區域不是您的選項, 您可以建立與自動設定所需的 SRV 記錄相對應的 pin 點 (專用) 區域, 並使用 dnscmd 填入這些區域。</span><span class="sxs-lookup"><span data-stu-id="1616a-196">If creating an entire zone in your internal DNS isn't an option for you, you can create pin-point (dedicated) zones that correspond to the SRV records required for automatic configuration, and populate those zones using dnscmd.exe.</span></span> <span data-ttu-id="1616a-197">Dnscmd .exe 是必要的, 因為 DNS 使用者介面不支援建立 pin 點區域。</span><span class="sxs-lookup"><span data-stu-id="1616a-197">Dnscmd.exe is required because the DNS user interface won't support the creation of pin-point zones.</span></span>
    
    <span data-ttu-id="1616a-198">例如, 如果您的 SIP 網域是 contoso.com, 而您有一個名為 pool01 的前端池 (其中包含兩個前端伺服器), 您將需要下列 pin 點區域及內部 DNS 中的記錄:</span><span class="sxs-lookup"><span data-stu-id="1616a-198">For example, if your SIP domain is contoso.com, and you have a Front End pool called pool01 that contains two Front End Servers, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    <span data-ttu-id="1616a-199">您的環境中可能會有第二個 SIP 網域。</span><span class="sxs-lookup"><span data-stu-id="1616a-199">You may have a second SIP domain in your environment.</span></span> <span data-ttu-id="1616a-200">在這種情況下, 您將需要下列 pin 點區域及內部 DNS 中的記錄:</span><span class="sxs-lookup"><span data-stu-id="1616a-200">In that case, you'll need the following pin-point zones and A records in your internal DNS:</span></span>
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> <span data-ttu-id="1616a-201">您會看到前端池 FQDN 出現了兩次, 但有兩個不同的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1616a-201">You'll see the Front End pool FQDN appears twice, but with two different IP addresses.</span></span> <span data-ttu-id="1616a-202">這是因為使用了 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1616a-202">That's because DNS load balancing is used.</span></span> <span data-ttu-id="1616a-203">如果使用 HLB, 則只有一個前端池專案。</span><span class="sxs-lookup"><span data-stu-id="1616a-203">If HLB is used, there'd only be a single Front End pool entry.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1616a-204">此外, 前端池 FQDN 值會在 contoso.com 與 fabrikam.com 範例之間變更, 但 IP 位址會保持不變。</span><span class="sxs-lookup"><span data-stu-id="1616a-204">Also, the Front End pool FQDN values change between the contoso.com and fabrikam.com examples, but the IP addresses remain the same.</span></span> <span data-ttu-id="1616a-205">這是因為從任一 SIP 網域登入的使用者將會使用相同的前端池來自動設定。</span><span class="sxs-lookup"><span data-stu-id="1616a-205">That's because users who're signing in from either SIP domain will be using the same Front End pool for automatic configuration.</span></span> 
  
## <a name="dns-disaster-recovery"></a><span data-ttu-id="1616a-206">DNS 災害復原</span><span class="sxs-lookup"><span data-stu-id="1616a-206">DNS disaster recovery</span></span>
<span data-ttu-id="1616a-207"><a name="DNSDR"> </a></span><span class="sxs-lookup"><span data-stu-id="1616a-207"></span></span>

<span data-ttu-id="1616a-208">若要設定 DNS 將商務用 Skype Server web 流量重新導向到災難復原 (DR) 及容錯移轉網站, 您必須使用支援 GeoDNS 的 DNS 提供者。</span><span class="sxs-lookup"><span data-stu-id="1616a-208">To configure DNS to redirect Skype for Business Server web traffic to your disaster recover (DR) and failover sites, you need to use a DNS provider that supports GeoDNS.</span></span> <span data-ttu-id="1616a-209">您可以設定您的 DNS 記錄以支援災難復原, 因此即使一個完整的前端池已停機, 使用 web 服務的功能仍會繼續。</span><span class="sxs-lookup"><span data-stu-id="1616a-209">You can set up your DNS records to support disaster recover, so that features that use web services continue even if one entire Front End pool goes down.</span></span> <span data-ttu-id="1616a-210">此 DR 功能支援自動探索、[符合] 和 [撥入] 簡單的 Url。</span><span class="sxs-lookup"><span data-stu-id="1616a-210">This DR feature supports the Autodiscover, Meet and Dial-in simple URLs.</span></span>
  
<span data-ttu-id="1616a-211">您可以在您的 GeoDNS 提供者處, 定義及設定其他 DNS 主機 A (如果使用 IPv6, 則是 AAAA) 的內部和外部解析 web 服務的記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-211">You define and configure additional DNS host A (AAAA if using IPv6) records for internal and external resolution of web services at your GeoDNS provider.</span></span> <span data-ttu-id="1616a-212">下列詳細資料假設成對式池、地理位置分散, 且您的提供者所支援的 GeoDNS**要麼**具有迴圈 DNS,**要麼**已設定為使用 Pool1 作為主要, 且會在任何通訊發生時, 容錯移轉至 Pool2。遺失或電源失敗。</span><span class="sxs-lookup"><span data-stu-id="1616a-212">The following details assume paired pools, geographically dispersed, and that the GeoDNS supported by your provider **either** has round-robin DNS **or** is configured to use Pool1 as primary and fails over to Pool2 in the event of any communications loss or power failure.</span></span>
  
<span data-ttu-id="1616a-213">此資料表中的所有 DNS 記錄都是範例。</span><span class="sxs-lookup"><span data-stu-id="1616a-213">All the DNS records in this table are examples.</span></span>
  
|<span data-ttu-id="1616a-214">**GeoDNS 記錄**</span><span class="sxs-lookup"><span data-stu-id="1616a-214">**GeoDNS record**</span></span>|<span data-ttu-id="1616a-215">**資源庫記錄**</span><span class="sxs-lookup"><span data-stu-id="1616a-215">**Pool records**</span></span>|<span data-ttu-id="1616a-216">**CNAME 記錄**</span><span class="sxs-lookup"><span data-stu-id="1616a-216">**CNAME records**</span></span>|<span data-ttu-id="1616a-217">**DNS 設定 (選取一個選項)**</span><span class="sxs-lookup"><span data-stu-id="1616a-217">**DNS settings (select one option)**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1616a-218">Meet-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-218">Meet-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-219">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-219">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-220">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-220">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-221">Meet.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-221">Meet.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-222">Meet.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-222">Meet.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-223">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-223">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-224">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-224">**OR**</span></span> <br/> <span data-ttu-id="1616a-225">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-225">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-226">Meet-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-226">Meet-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-227">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-227">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-228">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-228">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-229">Meet.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-229">Meet.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-230">Meet.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-230">Meet.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-231">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-231">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-232">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-232">**OR**</span></span> <br/> <span data-ttu-id="1616a-233">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-233">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-234">Dialin-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-234">Dialin-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-235">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-235">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-236">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-236">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-237">Dialin.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-237">Dialin.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-238">Dialin.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-238">Dialin.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-239">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-239">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-240">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-240">**OR**</span></span> <br/> <span data-ttu-id="1616a-241">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-241">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-242">Dialin-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-242">Dialin-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-243">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-243">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-244">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-244">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-245">Dialin.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-245">Dialin.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-246">Dialin.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-246">Dialin.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-247">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-247">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-248">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-248">**OR**</span></span> <br/> <span data-ttu-id="1616a-249">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-249">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-250">Lyncdiscoverint-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-250">Lyncdiscoverint-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-251">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-251">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-252">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-252">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-253">Lyncdiscoverinternal.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-253">Lyncdiscoverinternal.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-254">Lyncdiscoverinternal.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-254">Lyncdiscoverinternal.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-255">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-255">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-256">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-256">**OR**</span></span> <br/> <span data-ttu-id="1616a-257">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-257">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-258">Lyncdiscover-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-258">Lyncdiscover-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-259">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-259">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-260">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-260">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-261">Lyncdiscover.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-261">Lyncdiscover.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-262">Lyncdiscover.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-262">Lyncdiscover.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-263">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-263">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-264">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-264">**OR**</span></span> <br/> <span data-ttu-id="1616a-265">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-265">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-266">Scheduler-int.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-266">Scheduler-int.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-267">Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-267">Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-268">Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-268">Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-269">Scheduler.contoso.com 別名至 Pool1InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-269">Scheduler.contoso.com alias to Pool1InternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-270">Scheduler.contoso.com 別名至 Pool2InternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-270">Scheduler.contoso.com alias to Pool2InternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-271">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-271">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-272">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-272">**OR**</span></span> <br/> <span data-ttu-id="1616a-273">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-273">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
|<span data-ttu-id="1616a-274">Scheduler-ext.geolb.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-274">Scheduler-ext.geolb.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-275">Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-275">Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-276">Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-276">Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-277">Scheduler.contoso.com 別名至 Pool1ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-277">Scheduler.contoso.com alias to Pool1ExternalWebFQDN.contoso.com</span></span>  <br/> <span data-ttu-id="1616a-278">Scheduler.contoso.com 別名至 Pool2ExternalWebFQDN.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-278">Scheduler.contoso.com alias to Pool2ExternalWebFQDN.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-279">在池之間進行迴圈複用</span><span class="sxs-lookup"><span data-stu-id="1616a-279">Round Robin between pools</span></span>  <br/> <span data-ttu-id="1616a-280">**或**</span><span class="sxs-lookup"><span data-stu-id="1616a-280">**OR**</span></span> <br/> <span data-ttu-id="1616a-281">如果發生錯誤, 請使用 [主要], 連線到副</span><span class="sxs-lookup"><span data-stu-id="1616a-281">Use primary, connect to secondary if there's a failure</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="1616a-282">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="1616a-282">DNS load balancing</span></span>
<span data-ttu-id="1616a-283"><a name="DNSLB"> </a></span><span class="sxs-lookup"><span data-stu-id="1616a-283"></span></span>

<span data-ttu-id="1616a-284">DNS 負載平衡通常是在應用程式層級實現。</span><span class="sxs-lookup"><span data-stu-id="1616a-284">DNS load balancing is usually implemented at the application level.</span></span> <span data-ttu-id="1616a-285">應用程式 (例如, 執行商務用 Skype 的用戶端), 會連線至 [DNS A] 和 [AAAA] (如果使用 IPv6 定址) 中傳回的其中一個 IP 位址, 以針對 [池 FQDN] 進行記錄查詢, 連線至池中的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1616a-285">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool FQDN.</span></span>
  
<span data-ttu-id="1616a-286">例如, 如果一個名為 pool01.contoso.com 的池中有三個前端伺服器, 就會發生下列情況:</span><span class="sxs-lookup"><span data-stu-id="1616a-286">For example, if there are three Front End Servers in a pool named pool01.contoso.com, the following would happen:</span></span>
  
- <span data-ttu-id="1616a-287">執行商務用 Skype 查詢 pool01.contoso.com 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="1616a-287">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="1616a-288">查詢會傳回三個 IP 位址, 並以下列順序將它們緩存:</span><span class="sxs-lookup"><span data-stu-id="1616a-288">The query returns three IP addresses and caches them as follows (in some order):</span></span>
    
   |||
   |:-----|:-----|
   |<span data-ttu-id="1616a-289">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-289">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-290">192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="1616a-290">192.168.10.90</span></span>  <br/> |
   |<span data-ttu-id="1616a-291">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-291">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-292">192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="1616a-292">192.168.10.91</span></span>  <br/> |
   |<span data-ttu-id="1616a-293">pool01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1616a-293">pool01.contoso.com</span></span>  <br/> |<span data-ttu-id="1616a-294">192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="1616a-294">192.168.10.92</span></span>  <br/> |
   
- <span data-ttu-id="1616a-295">用戶端嘗試建立與其中一個 IP 位址的 TCP 連線。</span><span class="sxs-lookup"><span data-stu-id="1616a-295">The client tries to establish a TCP connection to one of the IP addresses.</span></span> <span data-ttu-id="1616a-296">如果失敗, 它會嘗試從該清單中快取的下一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="1616a-296">If that fails, it'll try the next IP address it's cached from that list.</span></span>
    
- <span data-ttu-id="1616a-297">如果 TCP 連線成功, 用戶端會協商 TLS, 連線到 pool01.contoso.com 上的主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="1616a-297">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="1616a-298">如果用戶端在未成功連線的情況下嘗試所有快取的專案, 使用者就會收到一則通知, 指出目前沒有任何伺服器執行商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="1616a-298">If the client tries all cached entries without a successful connection, the user receives a notification that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1616a-299">以 dns 為基礎的負載平衡與 DNS 迴圈 (DNS RR) 不同, 通常是依靠 DNS, 為您的池中的伺服器提供不同的 IP 位址順序來代表負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1616a-299">DNS-based load balancing is different from DNS round robin (DNS RR), which typically refers to load balancing by relying on DNS to give a different order of IP addresses for the servers in your pool.</span></span> <span data-ttu-id="1616a-300">通常, DNS RR 會啟用負載分配, 但不允許您啟用容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="1616a-300">Typically, DNS RR enables load distribution, but it won't allow you to enable failover.</span></span> <span data-ttu-id="1616a-301">例如, 如果連線到您的 DNS A (或 IPv6 案例中的 AAAA) 查詢所傳回的單一 IP 位址, 該連線就會失敗。</span><span class="sxs-lookup"><span data-stu-id="1616a-301">For example, if the connection to the one IP address returned by your DNS A (or AAAA in an IPv6 scenario) query fails, that connection will fail.</span></span> <span data-ttu-id="1616a-302">這可讓 DNS RR 比以 DNS 為基礎的負載平衡更可靠。</span><span class="sxs-lookup"><span data-stu-id="1616a-302">That makes DNS RR less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="1616a-303">如果您需要這麼做, 您仍然可以將 DNS RR 與 DNS 的負載平衡搭配使用。</span><span class="sxs-lookup"><span data-stu-id="1616a-303">You can still use DNS RR in conjunction with DNS-based load balancing if you need to do that.</span></span> 
  
<span data-ttu-id="1616a-304">您使用 DNS 負載平衡進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="1616a-304">You use DNS load balancing to:</span></span>
  
- <span data-ttu-id="1616a-305">將伺服器間 SIP 的負載平衡到邊緣伺服器。</span><span class="sxs-lookup"><span data-stu-id="1616a-305">Load balance server-to-server SIP to the Edge Servers.</span></span>
    
- <span data-ttu-id="1616a-306">[負載平衡] 的 [整合通訊應用程式服務 (UCAS)] 應用程式, 例如會議自動語音應答、回應群組, 以及電話寄存。</span><span class="sxs-lookup"><span data-stu-id="1616a-306">Load balance Unified Communication Application Services (UCAS) applications, such as Conferencing Auto Attendant, Response Group, and Call Park.</span></span>
    
- <span data-ttu-id="1616a-307">防止新連線至 UCAS 應用程式 (也稱為排出)。</span><span class="sxs-lookup"><span data-stu-id="1616a-307">Prevent new connections to UCAS applications (also known as draining).</span></span>
    
- <span data-ttu-id="1616a-308">在用戶端與邊緣伺服器之間, 對所有用戶端與伺服器流量進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="1616a-308">Load balance all client-to-server traffic between clients and Edge Servers.</span></span>
    
<span data-ttu-id="1616a-309">您無法使用 DNS 負載平衡進行下列作業:</span><span class="sxs-lookup"><span data-stu-id="1616a-309">You can't use DNS load balancing for:</span></span>
  
- <span data-ttu-id="1616a-310">從用戶端到伺服器的 web 流量到您的前端伺服器或主管。</span><span class="sxs-lookup"><span data-stu-id="1616a-310">Client-to-server web traffic to your Front End Servers or a Director.</span></span>
    
<span data-ttu-id="1616a-311">若要深入瞭解查詢傳回 mutiple DNS 記錄時所選取的 DNS SRV 記錄, Access Edge 服務會使用最低的數值優先順序來挑選該記錄, 而且如果需要一個交叉斷路器, 則是最高的數位寬度。</span><span class="sxs-lookup"><span data-stu-id="1616a-311">To go a little more in-depth on how a DNS SRV record's selected when mutiple DNS records are returned by a query, the Access Edge service always picks the record with the lowest numeric priority and, if a tie-breaker is needed, the highest numeric weight.</span></span> <span data-ttu-id="1616a-312">這與[網際網路工程工作強制檔](https://www.ietf.org/rfc/rfc2782.txt)是一致的。</span><span class="sxs-lookup"><span data-stu-id="1616a-312">This is consistent with [Internet Engineering Task Force documentation](https://www.ietf.org/rfc/rfc2782.txt).</span></span>
  
<span data-ttu-id="1616a-313">例如, 如果您的第一個 DNS SRV 記錄的權重是20且優先順序為 40, 而第二個 DNS SRV 記錄的權重為10且優先順序為 50, 則會選取第一筆記錄, 因為它具有較低優先順序的40。</span><span class="sxs-lookup"><span data-stu-id="1616a-313">So, for example, if your first DNS SRV record has a weight of 20 and a priority of 40, and your second DNS SRV record has a weight of 10 and a priority of 50, the first record's going to be chosen because it has the lower priority of 40.</span></span> <span data-ttu-id="1616a-314">優先順序總是最先生效, 而這是用戶端將最先進行目標的主機。</span><span class="sxs-lookup"><span data-stu-id="1616a-314">Priority always goes first, and that's the host that a client will target first.</span></span> <span data-ttu-id="1616a-315">如果有兩個具有相同優先順序的目標, 該怎麼辦？</span><span class="sxs-lookup"><span data-stu-id="1616a-315">What if there are two targets with the same priority?</span></span> 
  
<span data-ttu-id="1616a-316">在這種情況下, 會考慮負擔。</span><span class="sxs-lookup"><span data-stu-id="1616a-316">In that case, weight comes into consideration.</span></span> <span data-ttu-id="1616a-317">在這種情況下, 應為選取較大的權重。</span><span class="sxs-lookup"><span data-stu-id="1616a-317">Larger weights should be given a high probability, in this circumstance, of being selected.</span></span> <span data-ttu-id="1616a-318">如果沒有任何伺服器可供您選擇, DNS 管理員就應該使用權重0。</span><span class="sxs-lookup"><span data-stu-id="1616a-318">DNS administrators should use weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="1616a-319">如果記錄中包含的權重大於 0, 則權重為0的記錄會有極小的選擇機會。</span><span class="sxs-lookup"><span data-stu-id="1616a-319">In the presence of records containing weights greater than 0, records with weight 0 have a very small chance of bring selected.</span></span>
  
<span data-ttu-id="1616a-320">因此, 如果傳回的多個 DNS SRV 記錄具有相同的優先順序和權重, 就會發生什麼情況？</span><span class="sxs-lookup"><span data-stu-id="1616a-320">So, then, what happens if multiple DNS SRV records with equal priority and weight as returned?</span></span> <span data-ttu-id="1616a-321">在這種情況下, Access Edge 服務會先選擇它從 DNS 伺服器取得的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="1616a-321">In this situation the Access Edge service will choose the SRV record that it got from the DNS server first.</span></span>
  

