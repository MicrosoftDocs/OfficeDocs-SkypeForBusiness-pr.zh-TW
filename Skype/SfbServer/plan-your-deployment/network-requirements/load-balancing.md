---
title: 商務用 Skype 的負載平衡需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 摘要：在實施商務用 Skype Server 之前，請先檢查負載平衡考慮。
ms.openlocfilehash: 5790ef1ba0d32774ced45be5af257f70fc4cf594
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834373"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a><span data-ttu-id="58cea-103">商務用 Skype 的負載平衡需求</span><span class="sxs-lookup"><span data-stu-id="58cea-103">Load balancing requirements for Skype for Business</span></span>
 
<span data-ttu-id="58cea-104">**摘要：** 在實施商務用 Skype Server 之前，請先複查負載平衡考慮。</span><span class="sxs-lookup"><span data-stu-id="58cea-104">**Summary:** Review the load balancing considerations before implementing Skype for Business Server.</span></span>
  
<span data-ttu-id="58cea-105">負載平衡會在集區中的伺服器之間散佈流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-105">Load balancing distributes traffic among the servers in a pool.</span></span> <span data-ttu-id="58cea-106">如果您有前端集區、轉送伺服器集區或 Edge Server 集區，則需要為這些集區部署負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-106">If you have Front End pools, Mediation Server pools, or Edge Server pools, you need to deploy load balancing for these pools.</span></span>
  
<span data-ttu-id="58cea-107">商務用 Skype 伺服器支援用戶端對伺服器流量的兩種負載平衡解決方案：網域名稱系統 (DNS) 負載平衡與硬體負載平衡 (通常縮寫為 HLB) 。</span><span class="sxs-lookup"><span data-stu-id="58cea-107">Skype for Business Server supports two types of load balancing solutions for client-to-server traffic: Domain Name System (DNS) load balancing and hardware load balancing (often abbreviated as HLB).</span></span> <span data-ttu-id="58cea-108">DNS 負載平衡提供數種優點，包括簡化管理、更有效率的疑難排解，以及隔離任何可能的硬體負載平衡器問題的商務用 Skype 伺服器流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-108">DNS load balancing offers several advantages including simpler administration, more efficient troubleshooting, and the ability to isolate much of your Skype for Business Server traffic from any potential hardware load balancer problems.</span></span>
  
<span data-ttu-id="58cea-109">決定您的部署中每個集區適用的負載平衡解決方案，但切記下列限制：</span><span class="sxs-lookup"><span data-stu-id="58cea-109">Decide for yourself which load balancing solution is appropriate for each pool in your deployment, but keep in mind the following restrictions:</span></span> 
  
- <span data-ttu-id="58cea-110">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-110">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="58cea-111">您無法在一個介面上使用 DNS 負載平衡，另一個在另一個介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-111">You cannot use DNS load balancing on one interface and hardware load balancing on the other.</span></span>
    
- <span data-ttu-id="58cea-112">某些類型的流量需要硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="58cea-112">Some types of traffic require a hardware load balancer.</span></span> <span data-ttu-id="58cea-113">例如，HTTP 流量需要硬體負載平衡器，而不是使用 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-113">For example, HTTP traffic requires a hardware load balancer instead of DNS load balancing.</span></span> <span data-ttu-id="58cea-114">DNS 負載平衡無法搭配用戶端對伺服器的 web 流量使用。</span><span class="sxs-lookup"><span data-stu-id="58cea-114">DNS load balancing does not work with client-to-server web traffic.</span></span>
    
<span data-ttu-id="58cea-115">如果您選擇針對集區使用 DNS 負載平衡，但仍需要針對流量（例如 HTTP 流量）執行硬體負載平衡器，則可大幅簡化硬體負載平衡器的管理。</span><span class="sxs-lookup"><span data-stu-id="58cea-115">If you choose to use DNS load balancing for a pool but still need to implement hardware load balancers for traffic such as HTTP traffic, the administration of the hardware load balancers is greatly simplified.</span></span> <span data-ttu-id="58cea-116">例如，設定硬體負載平衡器會變得更簡單，因為它只會管理 HTTP 和 HTTPS 流量，而所有其他通訊協定都會透過 DNS 負載平衡來管理。</span><span class="sxs-lookup"><span data-stu-id="58cea-116">For example, configuring the hardware load balancer will be simpler as it will only manage the HTTP and HTTPS traffic, while all other protocols will be managed by DNS load balancing.</span></span> <span data-ttu-id="58cea-117">如需詳細資訊，請參閱 [DNS 負載平衡](load-balancing.md#BKMK_DNSLoadBalancing)。</span><span class="sxs-lookup"><span data-stu-id="58cea-117">For details, see [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing).</span></span> 
  
<span data-ttu-id="58cea-118">針對伺服器對伺服器流量，商務用 Skype 伺服器使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-118">For server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="58cea-119">伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-119">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="58cea-120">管理員不需要設定或管理這種類型的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-120">Administrators do not need to set up or manage this type of load balancing.</span></span> 
  
<span data-ttu-id="58cea-121">如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="58cea-121">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="58cea-122">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="58cea-122">You must remove the DNS entry for the computer as well.</span></span> 
  
## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="58cea-123">硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="58cea-123">Hardware load balancer requirements</span></span>

<span data-ttu-id="58cea-124">商務用 Skype 伺服器調整式合併 Edge 拓撲已針對新的部署，針對 DNS 負載平衡進行優化，主要與使用商務用 Skype Server 或 Lync Server 的其他組織合作。</span><span class="sxs-lookup"><span data-stu-id="58cea-124">The Skype for Business Server scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Skype for Business Server or Lync Server.</span></span> <span data-ttu-id="58cea-125">如果在下列任一情況下需要高可用性，則必須在 Edge Server 集區上使用硬體負載平衡器予以因應：</span><span class="sxs-lookup"><span data-stu-id="58cea-125">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span> 
  
- <span data-ttu-id="58cea-126">與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟</span><span class="sxs-lookup"><span data-stu-id="58cea-126">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>
    
- <span data-ttu-id="58cea-127">Exchange 2010 與 SP1 前使用 Exchange UM 的遠端使用者 exchange UM</span><span class="sxs-lookup"><span data-stu-id="58cea-127">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>
    
- <span data-ttu-id="58cea-128">公用 IM 使用者的連線</span><span class="sxs-lookup"><span data-stu-id="58cea-128">Connectivity to public IM users</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="58cea-p109">不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-p109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58cea-p110">在您使用硬體負載平衡器時，針對內部網路的連線所部署的負載平衡器必須經過設定，使其僅對流向執行 Access Edge Service 與 A/V Edge Service 之伺服器的流量執行負載平衡。對於流向內部 Web Conferencing Edge Service 或內部 XMPP Proxy 服務的流量，不可執行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-p110">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58cea-133">商務用 Skype Server 不支援 direct server 傳回 (DSR) NAT。</span><span class="sxs-lookup"><span data-stu-id="58cea-133">The direct server return (DSR) NAT is not supported with Skype for Business Server.</span></span> 
  
<span data-ttu-id="58cea-134">若要判斷您的硬體負載平衡器是否支援商務用 Skype Server 所需的功能，請參閱 [商務用 skype 的基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="58cea-134">To determine whether your hardware load balancer supports the necessary features required by Skype for Business Server, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span> 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="58cea-135">執行 A/V Edge Service 之 Edge Server 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="58cea-135">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="58cea-136">以下是執行 A/V Edge service 之 Edge Server 的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="58cea-136">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>
  
- <span data-ttu-id="58cea-p111">關閉內部及外部連接埠 443 的 TCP Nagling。Nagling 是一種程序，將數個小型封包合併為較大型的單一封包以進行有效傳輸。</span><span class="sxs-lookup"><span data-stu-id="58cea-p111">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>
    
- <span data-ttu-id="58cea-139">關閉外部埠範圍 50000-59999 的 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="58cea-139">Turn off TCP nagling for external port range 50,000 - 59,999.</span></span> 
    
- <span data-ttu-id="58cea-140">不要在內部或外部防火牆上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="58cea-140">Do not use NAT on the internal or external firewall.</span></span> 
    
- <span data-ttu-id="58cea-141">Edge 內部介面必須與 Edge 外部介面位在不同的網路上，而且必須停用在它們之間進行的路由傳送作業。</span><span class="sxs-lookup"><span data-stu-id="58cea-141">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span> 
    
- <span data-ttu-id="58cea-142">執行 A/V Edge Service 之 Edge Server 的外部介面必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。</span><span class="sxs-lookup"><span data-stu-id="58cea-142">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span> 
    
- <span data-ttu-id="58cea-143">負載平衡器不得變更用戶端的來源位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-143">The load balancer must not change the source address of the client.</span></span>
    
### <a name="other-hardware-load-balancer-requirements"></a><span data-ttu-id="58cea-144">其他硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="58cea-144">Other Hardware Load Balancer requirements</span></span>

<span data-ttu-id="58cea-145">在 Web 服務的商務用 Skype Server 中，Cookie 基礎的親近性需求會大幅減少。</span><span class="sxs-lookup"><span data-stu-id="58cea-145">Cookie-based affinity requirements are greatly reduced in Skype for Business Server for Web services.</span></span> <span data-ttu-id="58cea-146">如果您要部署商務用 Skype Server，但不會保留任何 Lync Server 2010 前端伺服器或前端集區，則不需要以 cookie 為基礎的持久性集。</span><span class="sxs-lookup"><span data-stu-id="58cea-146">If you are deploying Skype for Business Server and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="58cea-147">不過，如果您暫時或永久保留任何 Lync Server 2010 前端伺服器或前端集區，您仍會使用以 cookie 為基礎的持久性，因為它是針對 Lync Server 2010 部署及設定。</span><span class="sxs-lookup"><span data-stu-id="58cea-147">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="58cea-148">**如果您決定使用 Cookie 型相似性 (即使您的部署不需要它)**，則這樣做並不會產生任何負面影響。</span><span class="sxs-lookup"><span data-stu-id="58cea-148">**If you decide to use cookie-based affinity even though your deployment does not require it**, there is no negative impact to doing so.</span></span> 
  
<span data-ttu-id="58cea-149">針對 **不使用** Cookie 型相似性的部署：</span><span class="sxs-lookup"><span data-stu-id="58cea-149">For deployments that **will not use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="58cea-p113">在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。</span><span class="sxs-lookup"><span data-stu-id="58cea-p113">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
<span data-ttu-id="58cea-152">針對 **將使用** Cookie 型相似性的部署：</span><span class="sxs-lookup"><span data-stu-id="58cea-152">For deployments that **will use** cookie-based affinity:</span></span>
  
- <span data-ttu-id="58cea-p114">在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。</span><span class="sxs-lookup"><span data-stu-id="58cea-p114">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>
    
- <span data-ttu-id="58cea-155">硬體負載平衡器 Cookie「絕不能」標示為 httpOnly</span><span class="sxs-lookup"><span data-stu-id="58cea-155">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>
    
- <span data-ttu-id="58cea-156">硬體負載平衡器 Cookie「絕不能」有到期時間</span><span class="sxs-lookup"><span data-stu-id="58cea-156">Hardware load balancer cookie MUST NOT have an expiration time</span></span>
    
- <span data-ttu-id="58cea-157">硬體負載平衡器 Cookie「必須」命名為 **MS-WSMAN** (此為 Web 服務預期的值且無法變更)</span><span class="sxs-lookup"><span data-stu-id="58cea-157">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>
    
- <span data-ttu-id="58cea-p115">無論該相同 TCP 連線上先前的 HTTP 回應是否已取得 Cookie，在傳入 HTTP 要求沒有 Cookie 的每個 HTTP 回應中，都「必須」設定硬體負載平衡器 Cookie。如果負載平衡器將 Cookie 插入最佳化成針對每個 TCP 連線只出現一次，則「絕不能」使用該最佳化</span><span class="sxs-lookup"><span data-stu-id="58cea-p115">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>
    
> [!NOTE]
> <span data-ttu-id="58cea-160">一般硬體負載平衡器設定會使用來源位址親近性和20分鐘的 TCP 會話壽命，這對 Lync Server 和 Lync 2013 用戶端而言是很好的，因為會話狀態是透過用戶端使用方式和/或應用程式互動來維護。</span><span class="sxs-lookup"><span data-stu-id="58cea-160">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span> 
  
<span data-ttu-id="58cea-161">如果您正在部署行動裝置，硬體負載平衡器就必須能夠在 TCP 工作階段中負載平衡個別要求 (實際上，您必須能夠根據目標 IP 位址來負載平衡個別要求)。</span><span class="sxs-lookup"><span data-stu-id="58cea-161">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="58cea-162">如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 連線中個別地對每個要求進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-162">If you are deploying mobile devices, your hardware load balancer must be able to individually load balance each request within a TCP connection.</span></span> <span data-ttu-id="58cea-163">最新版的 Apple iOS 行動應用程式需要傳輸層安全性 (TLS) 版本 1.2。</span><span class="sxs-lookup"><span data-stu-id="58cea-163">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="58cea-164">如需協力廠商硬體負載平衡器的詳細資訊，請參閱適用于 [商務用 Skype 的基礎結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。</span><span class="sxs-lookup"><span data-stu-id="58cea-164">For details on third party hardware load balancers, see [Infrastructure for Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).</span></span>  
  
<span data-ttu-id="58cea-165">下面是 Director 與前端集區 Web 服務的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="58cea-165">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>
  
- <span data-ttu-id="58cea-166">針對內部 Web 服務 VIP，在硬體負載平衡器上設定 Source_addr 持續性 (內部連接埠 80、443)。</span><span class="sxs-lookup"><span data-stu-id="58cea-166">For internal Web Services VIPs, set Source_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="58cea-167">若為商務用 Skype Server，Source_addr 持續性表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器以維護會話狀態。</span><span class="sxs-lookup"><span data-stu-id="58cea-167">For Skype for Business Server, Source_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>
    
- <span data-ttu-id="58cea-168">使用 TCP 閒置逾時：1800 秒。</span><span class="sxs-lookup"><span data-stu-id="58cea-168">Use TCP idle timeout of 1800 seconds.</span></span>
    
- <span data-ttu-id="58cea-169">在反向 proxy 與下一個躍點集區之硬體負載平衡器之間的防火牆上，建立規則以允許從反向 proxy 到硬體負載平衡器的埠4443上的 HTTPs：流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-169">On the firewall between the reverse proxy and the next hop pool's hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="58cea-170">硬體負載平衡器必須設定成接聽連接埠 80、443 及 4443。</span><span class="sxs-lookup"><span data-stu-id="58cea-170">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="58cea-171">硬體負載平衡器相似性需求摘要</span><span class="sxs-lookup"><span data-stu-id="58cea-171">Summary of Hardware Load Balancer Affinity Requirements</span></span>

|<span data-ttu-id="58cea-172">**用戶端/使用者位置**</span><span class="sxs-lookup"><span data-stu-id="58cea-172">**Client/user location**</span></span>|<span data-ttu-id="58cea-173">**外部 Web 服務 FQDN 相似性需求**</span><span class="sxs-lookup"><span data-stu-id="58cea-173">**External web services FQDN affinity requirements**</span></span>|<span data-ttu-id="58cea-174">**內部 Web 服務 FQDN 相似性需求**</span><span class="sxs-lookup"><span data-stu-id="58cea-174">**Internal web services FQDN affinity requirements**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="58cea-175">Lync Web App (內部及外部使用者) </span><span class="sxs-lookup"><span data-stu-id="58cea-175">Lync Web App (internal and external users)</span></span>  <br/> <span data-ttu-id="58cea-176">行動裝置 (內部和外部使用者)</span><span class="sxs-lookup"><span data-stu-id="58cea-176">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="58cea-177">無相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-177">No affinity</span></span>  <br/> |<span data-ttu-id="58cea-178">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-178">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="58cea-179">Lync Web App (僅限外部使用者) </span><span class="sxs-lookup"><span data-stu-id="58cea-179">Lync Web App (external users only)</span></span>  <br/> <span data-ttu-id="58cea-180">行動裝置 (內部和外部使用者)</span><span class="sxs-lookup"><span data-stu-id="58cea-180">Mobile device (internal and external users)</span></span>  <br/> |<span data-ttu-id="58cea-181">無相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-181">No affinity</span></span>  <br/> |<span data-ttu-id="58cea-182">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-182">Source address affinity</span></span>  <br/> |
|<span data-ttu-id="58cea-183">Lync Web App (僅限內部使用者) </span><span class="sxs-lookup"><span data-stu-id="58cea-183">Lync Web App (internal users only)</span></span>  <br/> <span data-ttu-id="58cea-184">行動裝置 (未部署)</span><span class="sxs-lookup"><span data-stu-id="58cea-184">Mobile device (not deployed)</span></span>  <br/> |<span data-ttu-id="58cea-185">無相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-185">No affinity</span></span>  <br/> |<span data-ttu-id="58cea-186">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="58cea-186">Source address affinity</span></span>  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="58cea-187">適用於硬體負載平衡器的連接埠監控</span><span class="sxs-lookup"><span data-stu-id="58cea-187">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="58cea-188">您可以在硬體負載平衡器上定義連接埠監控，以判斷特定的服務何時因為發生硬體或通訊失敗而無法使用。</span><span class="sxs-lookup"><span data-stu-id="58cea-188">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="58cea-189">例如，如果前端伺服器服務 (RTCSRV) 停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-189">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="58cea-190">您可以在 HLB 上實作連接埠監控以監控下列各項：</span><span class="sxs-lookup"><span data-stu-id="58cea-190">You implement port monitoring on the HLB to monitor the following:</span></span>
  
<span data-ttu-id="58cea-191">**前端伺服器使用者集區-HLB 內部介面**</span><span class="sxs-lookup"><span data-stu-id="58cea-191">**Front End Server User Pool - HLB Internal Interface**</span></span>

|<span data-ttu-id="58cea-192">**虛擬 IP/連接埠**</span><span class="sxs-lookup"><span data-stu-id="58cea-192">**Virtual IP/Port**</span></span>|<span data-ttu-id="58cea-193">**節點連接埠**</span><span class="sxs-lookup"><span data-stu-id="58cea-193">**Node Port**</span></span>|<span data-ttu-id="58cea-194">**節點電腦/監視器**</span><span class="sxs-lookup"><span data-stu-id="58cea-194">**Node Machine/Monitor**</span></span>|<span data-ttu-id="58cea-195">**持續性設定檔**</span><span class="sxs-lookup"><span data-stu-id="58cea-195">**Persistence Profile**</span></span>|<span data-ttu-id="58cea-196">**附註**</span><span class="sxs-lookup"><span data-stu-id="58cea-196">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58cea-197">\<pool\>web int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="58cea-197">\<pool\>web-int_mco_443_vs</span></span>  <br/> <span data-ttu-id="58cea-198">443</span><span class="sxs-lookup"><span data-stu-id="58cea-198">443</span></span>  <br/> |<span data-ttu-id="58cea-199">443</span><span class="sxs-lookup"><span data-stu-id="58cea-199">443</span></span>  <br/> |<span data-ttu-id="58cea-200">前端</span><span class="sxs-lookup"><span data-stu-id="58cea-200">Front End</span></span>  <br/> <span data-ttu-id="58cea-201">5061</span><span class="sxs-lookup"><span data-stu-id="58cea-201">5061</span></span>  <br/> |<span data-ttu-id="58cea-202">來源</span><span class="sxs-lookup"><span data-stu-id="58cea-202">Source</span></span>  <br/> |<span data-ttu-id="58cea-203">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="58cea-203">HTTPS</span></span>  <br/> |
|<span data-ttu-id="58cea-204">\<pool\>web int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="58cea-204">\<pool\>web-int_mco_80_vs</span></span>  <br/> <span data-ttu-id="58cea-205">80</span><span class="sxs-lookup"><span data-stu-id="58cea-205">80</span></span>  <br/> |<span data-ttu-id="58cea-206">80</span><span class="sxs-lookup"><span data-stu-id="58cea-206">80</span></span>  <br/> |<span data-ttu-id="58cea-207">前端</span><span class="sxs-lookup"><span data-stu-id="58cea-207">Front End</span></span>  <br/> <span data-ttu-id="58cea-208">5061</span><span class="sxs-lookup"><span data-stu-id="58cea-208">5061</span></span>  <br/> |<span data-ttu-id="58cea-209">來源</span><span class="sxs-lookup"><span data-stu-id="58cea-209">Source</span></span>  <br/> |<span data-ttu-id="58cea-210">HTTP:</span><span class="sxs-lookup"><span data-stu-id="58cea-210">HTTP</span></span>  <br/> |
   
<span data-ttu-id="58cea-211">**前端伺服器使用者集區-HLB 外部介面**</span><span class="sxs-lookup"><span data-stu-id="58cea-211">**Front End Server User Pool - HLB External Interface**</span></span>

|<span data-ttu-id="58cea-212">**虛擬 IP/連接埠**</span><span class="sxs-lookup"><span data-stu-id="58cea-212">**Virtual IP/Port**</span></span>|<span data-ttu-id="58cea-213">**節點連接埠**</span><span class="sxs-lookup"><span data-stu-id="58cea-213">**Node Port**</span></span>|<span data-ttu-id="58cea-214">**節點電腦/監視器**</span><span class="sxs-lookup"><span data-stu-id="58cea-214">**Node Machine/Monitor**</span></span>|<span data-ttu-id="58cea-215">**持續性設定檔**</span><span class="sxs-lookup"><span data-stu-id="58cea-215">**Persistence Profile**</span></span>|<span data-ttu-id="58cea-216">**附註**</span><span class="sxs-lookup"><span data-stu-id="58cea-216">**Notes**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="58cea-217">\<pool\>web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="58cea-217">\<pool\>web_mco_443_vs</span></span>  <br/> <span data-ttu-id="58cea-218">443</span><span class="sxs-lookup"><span data-stu-id="58cea-218">443</span></span>  <br/> |<span data-ttu-id="58cea-219">4443</span><span class="sxs-lookup"><span data-stu-id="58cea-219">4443</span></span>  <br/> |<span data-ttu-id="58cea-220">前端</span><span class="sxs-lookup"><span data-stu-id="58cea-220">Front End</span></span>  <br/> <span data-ttu-id="58cea-221">5061</span><span class="sxs-lookup"><span data-stu-id="58cea-221">5061</span></span>  <br/> |<span data-ttu-id="58cea-222">無</span><span class="sxs-lookup"><span data-stu-id="58cea-222">None</span></span>  <br/> |<span data-ttu-id="58cea-223">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="58cea-223">HTTPS</span></span>  <br/> |
|<span data-ttu-id="58cea-224">\<pool\>web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="58cea-224">\<pool\>web_mco_80_vs</span></span>  <br/> <span data-ttu-id="58cea-225">80</span><span class="sxs-lookup"><span data-stu-id="58cea-225">80</span></span>  <br/> |<span data-ttu-id="58cea-226">8080</span><span class="sxs-lookup"><span data-stu-id="58cea-226">8080</span></span>  <br/> |<span data-ttu-id="58cea-227">前端</span><span class="sxs-lookup"><span data-stu-id="58cea-227">Front End</span></span>  <br/> <span data-ttu-id="58cea-228">5061</span><span class="sxs-lookup"><span data-stu-id="58cea-228">5061</span></span>  <br/> |<span data-ttu-id="58cea-229">無</span><span class="sxs-lookup"><span data-stu-id="58cea-229">None</span></span>  <br/> |<span data-ttu-id="58cea-230">HTTP:</span><span class="sxs-lookup"><span data-stu-id="58cea-230">HTTP</span></span>  <br/> |
   
## <a name="dns-load-balancing"></a><span data-ttu-id="58cea-231">DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-231">DNS Load Balancing</span></span>
<span data-ttu-id="58cea-232"><a name="BKMK_DNSLoadBalancing"> </a></span><span class="sxs-lookup"><span data-stu-id="58cea-232"><a name="BKMK_DNSLoadBalancing"> </a></span></span>

<span data-ttu-id="58cea-233">商務用 Skype Server 可讓您在網路上大幅減少負載平衡之管理負荷的軟體解決方案，以進行 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-233">Skype for Business Server enables DNS load balancing, a software solution that can greatly reduce the administration overhead for load balancing on your network.</span></span> <span data-ttu-id="58cea-234">DNS 負載平衡會平衡商務用 Skype 伺服器特有的網路流量，例如 SIP 流量和媒體流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-234">DNS load balancing balances the network traffic that is unique to Skype for Business Server, such as SIP traffic and media traffic.</span></span>
  
<span data-ttu-id="58cea-235">如果您部署 DNS 負載平衡，您組織的硬體負載平衡器的管理系統開銷將會降到最低。</span><span class="sxs-lookup"><span data-stu-id="58cea-235">If you deploy DNS load balancing, your organization's administration overhead for hardware load balancers will be minimized.</span></span> <span data-ttu-id="58cea-236">此外，負載平衡器中針對 SIP 流量的設定錯誤問題所涉及的複雜疑難排解也得以排除。</span><span class="sxs-lookup"><span data-stu-id="58cea-236">Additionally, complex troubleshooting of problems related to misconfiguration of load balancers for SIP traffic will be eliminated.</span></span> <span data-ttu-id="58cea-237">您也可以防止伺服器連線，以便將伺服器離線。</span><span class="sxs-lookup"><span data-stu-id="58cea-237">You can also prevent server connections so that you can take servers offline.</span></span> <span data-ttu-id="58cea-238">DNS 負載平衡也可以確保硬體負載平衡器問題不會影響基本通話路由等這類 SIP 流量元素。</span><span class="sxs-lookup"><span data-stu-id="58cea-238">DNS load balancing also ensures that hardware load balancer problems do not affect elements of SIP traffic such as basic call routing.</span></span>

<span data-ttu-id="58cea-239">下圖顯示一個範例，其中包括內部和外部 DNS 負載平衡：</span><span class="sxs-lookup"><span data-stu-id="58cea-239">The following diagram shows an example that includes both internal and external DNS load balancing:</span></span> 
  
<span data-ttu-id="58cea-240">**使用公用 IPv4 位址的 Edge network 圖表**</span><span class="sxs-lookup"><span data-stu-id="58cea-240">**Edge network diagram using Public IPv4 addresses**</span></span>

![DNS 網狀圖表範例](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
<span data-ttu-id="58cea-242">相較於將硬體負載平衡器用於全部的流量類型，如果使用 DNS 負載平衡也能讓您購買成本較低的硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="58cea-242">If you use DNS load balancing, you may also be able to purchase lower-cost hardware load balancers than if you used the hardware load balancers for all types of traffic.</span></span> <span data-ttu-id="58cea-243">您應該使用已透過商務用 Skype 伺服器進行互通性資格測試的負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="58cea-243">You should use load balancers that have passed interoperability qualification testing with Skype for Business Server.</span></span> <span data-ttu-id="58cea-244">如需負載平衡器互通性測試的詳細資訊，請參閱 [Lync Server 2010 負載平衡器合作夥伴](https://go.microsoft.com/fwlink/p/?linkId=202452)。</span><span class="sxs-lookup"><span data-stu-id="58cea-244">For details about load balancer interoperability testing, see [Lync Server 2010 Load Balancer Partners](https://go.microsoft.com/fwlink/p/?linkId=202452).</span></span> <span data-ttu-id="58cea-245">適用于商務用 Skype Server 的內容。</span><span class="sxs-lookup"><span data-stu-id="58cea-245">The content there applies to Skype for Business Server.</span></span>
  
<span data-ttu-id="58cea-246">DNS 負載平衡支援前端集區、Edge Server 集區、Director 集區和獨立中繼伺服器集區。</span><span class="sxs-lookup"><span data-stu-id="58cea-246">DNS load balancing is supported for Front End pools, Edge Server pools, Director pools, and stand-alone Mediation Server pools.</span></span>
  
<span data-ttu-id="58cea-247">DNS 負載平衡通常是在應用層級實施。</span><span class="sxs-lookup"><span data-stu-id="58cea-247">DNS load balancing is typically implemented at the application level.</span></span> <span data-ttu-id="58cea-248">應用程式 (例如，執行商務用 Skype) 的用戶端，會嘗試連線至伺服器集區中從 DNS A 和 (AAAA 傳回的其中一個 IP 位址，如果 IPv6 定址是用於集區完整功能變數名稱) FQDN (的記錄查詢。</span><span class="sxs-lookup"><span data-stu-id="58cea-248">The application (for example, a client running Skype for Business), tries to connect to a server in a pool by connecting to one of the IP addresses returned from the DNS A and AAAA (if IPv6 addressing is used) record query for the pool fully qualified domain name (FQDN).</span></span> 
  
<span data-ttu-id="58cea-249">例如，如果名為 pool01.contoso.com 的集區中有三部前端伺服器，則會發生下列情況：</span><span class="sxs-lookup"><span data-stu-id="58cea-249">For example, if there are three front end servers in a pool named pool01.contoso.com, the following will happen:</span></span>
  
- <span data-ttu-id="58cea-250">執行商務用 Skype For pool01.contoso.com 的用戶端查詢 DNS。</span><span class="sxs-lookup"><span data-stu-id="58cea-250">Clients running Skype for Business query DNS for pool01.contoso.com.</span></span> <span data-ttu-id="58cea-251">查詢會傳回三個 IP 位址，並將其快取如下 (不一定要依此順序) ：</span><span class="sxs-lookup"><span data-stu-id="58cea-251">The query returns three IP addresses and caches them as follows (not necessarily in this order):</span></span>
    
    <span data-ttu-id="58cea-252">pool01.contoso.com 192.168.10.90</span><span class="sxs-lookup"><span data-stu-id="58cea-252">pool01.contoso.com 192.168.10.90</span></span>
    
    <span data-ttu-id="58cea-253">pool01.contoso.com 192.168.10.91</span><span class="sxs-lookup"><span data-stu-id="58cea-253">pool01.contoso.com 192.168.10.91</span></span>
    
    <span data-ttu-id="58cea-254">pool01.contoso.com 192.168.10.92</span><span class="sxs-lookup"><span data-stu-id="58cea-254">pool01.contoso.com 192.168.10.92</span></span>
    
- <span data-ttu-id="58cea-255">用戶端會嘗試建立傳輸控制通訊協定 (TCP) 連接至其中一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-255">The client attempts to establish a Transmission Control Protocol (TCP) connection to one of the IP addresses.</span></span> <span data-ttu-id="58cea-256">如果失敗，用戶端會嘗試在快取中的下一個 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-256">If that fails, the client tries the next IP address in the cache.</span></span>
    
- <span data-ttu-id="58cea-257">如果 TCP 連線成功，用戶端會協商 TLS，以連線至 pool01.contoso.com 上的主要註冊機構。</span><span class="sxs-lookup"><span data-stu-id="58cea-257">If the TCP connection succeeds, the client negotiates TLS to connect to the primary registrar on pool01.contoso.com.</span></span>
    
- <span data-ttu-id="58cea-258">如果用戶端嘗試所有的快取專案，但連線失敗，則會通知使用者目前沒有執行商務用 Skype 伺服器的伺服器。</span><span class="sxs-lookup"><span data-stu-id="58cea-258">If the client tries all cached entries without a successful connection, the user is notified that no servers running Skype for Business Server are available at the moment.</span></span>
    
> [!NOTE]
> <span data-ttu-id="58cea-259">DNS 的負載平衡與 DNS 迴圈使用不同 (DNS RR) ，其主要指的是透過 DNS 提供與集區中伺服器對應的不同順序的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-259">DNS-based load balancing is different from DNS round robin (DNS RR) which typically refers to load balancing by relying on DNS to provide a different order of IP addresses corresponding to the servers in a pool.</span></span> <span data-ttu-id="58cea-260">通常 DNS RR 只會啟用負載分配，但不會啟用容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="58cea-260">Typically DNS RR only enables load distribution, but does not enable failover.</span></span> <span data-ttu-id="58cea-261">例如，如果您在使用 IPv6 定址) 查詢失敗時，由 DNS A 和 AAAA (所傳回的一個 IP 位址進行連線，連接就會失敗。</span><span class="sxs-lookup"><span data-stu-id="58cea-261">For example, if the connection to the one IP address returned by the DNS A and AAAA (if you are using IPv6 addressing) query fails, the connection fails.</span></span> <span data-ttu-id="58cea-262">因此，來自于 DNS 的負載平衡，其本身的 [DNS] 迴圈是不夠可靠的。</span><span class="sxs-lookup"><span data-stu-id="58cea-262">Therefore, DNS round robin by itself is less reliable than DNS-based load balancing.</span></span> <span data-ttu-id="58cea-263">您可以搭配 DNS 負載平衡使用 DNS 迴圈。</span><span class="sxs-lookup"><span data-stu-id="58cea-263">You can use DNS round robin in conjunction with DNS load balancing.</span></span> 
  
<span data-ttu-id="58cea-264">DNS 負載平衡用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="58cea-264">DNS load balancing is used for the following:</span></span>
  
- <span data-ttu-id="58cea-265">將伺服器對伺服器的 SIP 負載平衡至 Edge server</span><span class="sxs-lookup"><span data-stu-id="58cea-265">Load balancing server-to-server SIP to the Edge Servers</span></span>
    
- <span data-ttu-id="58cea-266">負載平衡整合通訊應用程式服務 (UCAS) 應用程式，例如會議自動語音應答、回應群組和通話駐留</span><span class="sxs-lookup"><span data-stu-id="58cea-266">Load balancing Unified Communications Application Services (UCAS) applications such as Conferencing Auto Attendant, Response Group, and Call Park</span></span>
    
- <span data-ttu-id="58cea-267">防止新連線 UCAS 應用程式 (也稱為「耗盡」 ) </span><span class="sxs-lookup"><span data-stu-id="58cea-267">Preventing new connections to UCAS applications (also known as "draining")</span></span>
    
- <span data-ttu-id="58cea-268">在用戶端和 Edge server 之間負載平衡所有用戶端對伺服器流量</span><span class="sxs-lookup"><span data-stu-id="58cea-268">Load balancing all client-to-server traffic between clients and Edge Servers</span></span>
    
<span data-ttu-id="58cea-269">DNS 負載平衡無法用於下列專案：</span><span class="sxs-lookup"><span data-stu-id="58cea-269">DNS load balancing cannot be used for the following:</span></span>
  
- <span data-ttu-id="58cea-270">對 Director 或前端伺服器的用戶端對伺服器網頁流量</span><span class="sxs-lookup"><span data-stu-id="58cea-270">Client-to-server web traffic to Director or Front End Servers</span></span>
    
<span data-ttu-id="58cea-271">DNS 負載平衡及同盟流量：</span><span class="sxs-lookup"><span data-stu-id="58cea-271">DNS load balancing and federated traffic:</span></span>
  
<span data-ttu-id="58cea-272">如果 DNS SRV 查詢傳回多個 DNS 記錄，Access Edge service 一定會選取具有最低的數值優先順序和最高數值權重的 DNS SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="58cea-272">If multiple DNS records are returned by a DNS SRV query, the Access Edge service always picks the DNS SRV record with the lowest numeric priority and highest numeric weight.</span></span> <span data-ttu-id="58cea-273">網際網路工程工作強制檔「用於指定服務位置 (DNS SRV) " [RFC 2782，DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) 會指定如果已定義多個 DNS srv 記錄，則會先使用優先順序，然後再使用「加權」。</span><span class="sxs-lookup"><span data-stu-id="58cea-273">The Internet Engineering Task Force document "A DNS RR for specifying the location of services (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) specifies that if there are multiple DNS SRV records defined, priority is first used, then weight.</span></span> <span data-ttu-id="58cea-274">例如，DNS SRV 記錄 A 的權重為20，優先順序為40，而 DNS SRV 記錄 B 的權重為10，優先順序為50。</span><span class="sxs-lookup"><span data-stu-id="58cea-274">For example DNS SRV record A has a weight of 20 and a priority of 40 and DNS SRV record B has a weight of 10 and priority of 50.</span></span> <span data-ttu-id="58cea-275">將會選取具有優先順序40的 DNS SRV 記錄 A。</span><span class="sxs-lookup"><span data-stu-id="58cea-275">DNS SRV record A with priority 40 will be selected.</span></span> <span data-ttu-id="58cea-276">下列規則適用于 DNS SRV 記錄選取：</span><span class="sxs-lookup"><span data-stu-id="58cea-276">The following rules apply to DNS SRV record selection:</span></span>
  
- <span data-ttu-id="58cea-277">優先順序會先考慮。</span><span class="sxs-lookup"><span data-stu-id="58cea-277">Priority is considered first.</span></span> <span data-ttu-id="58cea-278">用戶端必須嘗試聯繫 DNS SRV 記錄所定義的目標主機，其可達到的最低優先順序。</span><span class="sxs-lookup"><span data-stu-id="58cea-278">A client MUST attempt to contact the target host defined by the DNS SRV record with the lowest numbered priority it can reach.</span></span> <span data-ttu-id="58cea-279">應以「加權」欄位所定義的順序，嘗試相同優先順序的目標。</span><span class="sxs-lookup"><span data-stu-id="58cea-279">Targets with the same priority SHOULD be tried in an order defined by the weight field.</span></span>
    
- <span data-ttu-id="58cea-280">[加權] 欄位會指定具有相同優先順序之專案的相對權重。</span><span class="sxs-lookup"><span data-stu-id="58cea-280">The weight field specifies a relative weight for entries with the same priority.</span></span> <span data-ttu-id="58cea-281">應將較大的權重按比例增加選取的概率。</span><span class="sxs-lookup"><span data-stu-id="58cea-281">Larger weights SHOULD be given a proportionately higher probability of being selected.</span></span> <span data-ttu-id="58cea-282">DNS 管理員應該在沒有任何要執行的伺服器選擇時使用權重0。</span><span class="sxs-lookup"><span data-stu-id="58cea-282">DNS administrators SHOULD use Weight 0 when there isn't any server selection to do.</span></span> <span data-ttu-id="58cea-283">當記錄中包含的權重大於0時，具有權重0的記錄應該會有很小的可能被選取。</span><span class="sxs-lookup"><span data-stu-id="58cea-283">In the presence of records containing weights greater than 0, records with weight 0 should have a very small chance of being selected.</span></span>
    
<span data-ttu-id="58cea-284">若傳回多個具有相同優先順序和權重的 DNS SRV 記錄，Access Edge service 會選取最先從 DNS 伺服器接收的 SRV 記錄。</span><span class="sxs-lookup"><span data-stu-id="58cea-284">If multiple DNS SRV records with equal priority and weight are returned, the Access Edge service will select the SRV record that was received first from the DNS server.</span></span>
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="58cea-285">前端集區和 Director 集區上的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-285">DNS Load Balancing on Front End Pools and Director Pools</span></span>

<span data-ttu-id="58cea-p130">您可以針對前端集區和 Director 集區上的 SIP 流量使用 DNS 負載平衡。部署 DNS 負載平衡之後，這些集區還是需要使用硬體負載平衡器，但只限用戶端到伺服器的 HTTPS 流量。硬體負載平衡器會用於用戶端透過連接埠 443 和 80 送出的 HTTPS 流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-p130">You can use DNS load balancing for the SIP traffic on Front End pools and Director pools. With DNS load balancing deployed, you still need to also use hardware load balancers for these pools, but only for client-to-server HTTPS traffic. The hardware load balancer is used for HTTPS traffic from clients over ports 443 and 80.</span></span> 
  
<span data-ttu-id="58cea-289">雖然這些集區仍然需要硬體負載平衡器，但是其設定和系統管理主要是針對 HTTPS 流量，這也是硬體負載平衡器的系統管理員比較熟悉的領域。</span><span class="sxs-lookup"><span data-stu-id="58cea-289">Although you still need hardware load balancers for these pools, their setup and administration will be primarily for HTTPS traffic, which the administrators of hardware load balancers are accustomed to.</span></span>
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a><span data-ttu-id="58cea-290">DNS 負載平衡以及支援的舊版用戶端和伺服器</span><span class="sxs-lookup"><span data-stu-id="58cea-290">DNS Load Balancing and Supporting Older Clients and Servers</span></span>

<span data-ttu-id="58cea-291">僅針對執行商務用 Skype 伺服器或 Lync Server 2010 的伺服器，以及 Lync 2013 和商務用 Skype 用戶端，DNS 負載平衡只支援自動容錯移轉。</span><span class="sxs-lookup"><span data-stu-id="58cea-291">DNS load balancing supports automatic failover only for servers running Skype for Business Server or Lync Server 2010, and for Lync 2013 and Skype for Business clients.</span></span> <span data-ttu-id="58cea-292">較舊版本的用戶端和 Office 通訊伺服器仍然可以連線到執行 DNS 負載平衡的集區，但如果這些集區無法連線至 DNS 負載平衡所參照的第一部伺服器，則他們無法容錯移轉至集區中的另一部伺服器。</span><span class="sxs-lookup"><span data-stu-id="58cea-292">Earlier versions of clients and Office Communications Server can still connect to pools running DNS load balancing, but if they cannot make a connection to the first server that DNS load balancing refers them to, they are unable to fail over to another server in the pool.</span></span> 
  
<span data-ttu-id="58cea-293">此外，如果您使用 Exchange UM，您必須至少使用 Exchange 2010 SP1 以取得商務用 Skype 伺服器的 DNS 負載平衡支援。</span><span class="sxs-lookup"><span data-stu-id="58cea-293">Additionally, if you are using Exchange UM, you must use a minimum of Exchange 2010 SP1 to get support for Skype for Business Server DNS load balancing.</span></span> <span data-ttu-id="58cea-294">如果您使用舊版的 Exchange，您的使用者將不會有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="58cea-294">If you use an earlier version of Exchange, your users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="58cea-295">在電話上播放企業語音信箱</span><span class="sxs-lookup"><span data-stu-id="58cea-295">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="58cea-296">從 Exchange UM 自動語音應答轉接通話</span><span class="sxs-lookup"><span data-stu-id="58cea-296">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="58cea-297">所有其他 Exchange UM 案例則會正常運作。</span><span class="sxs-lookup"><span data-stu-id="58cea-297">All other Exchange UM scenarios will work properly.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a><span data-ttu-id="58cea-298">在前端集區和 Director 集區上部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-298">Deploying DNS Load Balancing on Front End Pools and Director Pools</span></span>
<span data-ttu-id="58cea-299"><a name="BK_FE_Dir"> </a></span><span class="sxs-lookup"><span data-stu-id="58cea-299"><a name="BK_FE_Dir"> </a></span></span>

<span data-ttu-id="58cea-300">在前端集區和 Director 集區上部署 DNS 負載平衡，需要您對 FQDN 和 DNS 記錄執行一些額外步驟。</span><span class="sxs-lookup"><span data-stu-id="58cea-300">Deploying DNS load balancing on Front End pools and Director pools requires you to perform a couple of extra steps with FQDNs and DNS records.</span></span>
  
- <span data-ttu-id="58cea-301">使用 DNS 負載平衡的集區必須有兩個 Fqdn： DNS 負載平衡 (所使用的一般集區 FQDN，例如 pool01.contoso.com) ，並解析為集區中伺服器的實體 Ip，以及集區 Web 服務的另一個 FQDN (例如，web01.contoso.com) ，可解析為集區的虛擬 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-301">A pool that uses DNS load balancing must have two FQDNs: the regular pool FQDN that is used by DNS load balancing (such as pool01.contoso.com), and resolves to the physical IPs of the servers in the pool, and another FQDN for the pool's Web services (such as web01.contoso.com), which resolves to virtual IP address of the pool.</span></span> 
    
    <span data-ttu-id="58cea-302">在 [拓撲產生器] 中，如果您想要為集區部署 DNS 負載平衡，若要為集區的 Web 服務建立額外的 FQDN，您必須選取 [覆 **寫內部 Web 服務集區 FQDN** ] 核取方塊，然後在 [ **指定 Web 服務 URLs 中為此集** 區] 頁面中輸入 FQDN。</span><span class="sxs-lookup"><span data-stu-id="58cea-302">In Topology Builder, if you want to deploy DNS load balancing for a pool, to create this extra FQDN for the pool's Web services you must select the **Override internal Web Services pool FQDN** check box and type the FQDN, in the **Specify the Web Services URLs for this Pool** page.</span></span>
    
- <span data-ttu-id="58cea-p133">若要支援 DNS 負載平衡所使用的 FQDN，您必須佈建 DNS，以將集區 FQDN (如 pool01.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。您應該只包含目前部署之伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-p133">To support the FQDN used by DNS load balancing, you must provision DNS to resolve the pool FQDN (such as pool01.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on). You should include only the IP addresses of servers that are currently deployed.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="58cea-305">如果您有一個以上的前端集區或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="58cea-305">If you have more than one Front End pool or Front End Server the external Web services FQDN must be unique.</span></span> <span data-ttu-id="58cea-306">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為 **pool01.contoso.com**，則無法將 **pool01.contoso.com** 用於另一個前端集區或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="58cea-306">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="58cea-307">如果您也要部署 Director，則為任何 Director 或 Director 集區定義的外部 Web 服務 FQDN，都必須與任何其他 Director 或 Director 集區以及任何前端集區或前端伺服器都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="58cea-307">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool as well as any Front End pool or Front End Server.</span></span> <span data-ttu-id="58cea-308">如果決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 必須與其他任何前端集區、Director 或 Director 集區是唯一的。</span><span class="sxs-lookup"><span data-stu-id="58cea-308">If decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director or a Director pool.</span></span>
  
### <a name="dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="58cea-309">Edge Server 集區上的 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-309">DNS Load Balancing on Edge Server Pools</span></span>
<span data-ttu-id="58cea-310"><a name="BK_Edge"> </a></span><span class="sxs-lookup"><span data-stu-id="58cea-310"><a name="BK_Edge"> </a></span></span>

<span data-ttu-id="58cea-p135">您可以在 Edge Server 集區上部署 DNS 負載平衡。如果這麼做，則必須注意下列考量。</span><span class="sxs-lookup"><span data-stu-id="58cea-p135">You can deploy DNS load balancing on Edge Server pools. If you do, you must be aware of some considerations.</span></span>
  
<span data-ttu-id="58cea-313">在 Edge Server 上使用 DNS 負載平衡，會導致下列案例喪失容錯移轉能力：</span><span class="sxs-lookup"><span data-stu-id="58cea-313">Using DNS load balancing on your Edge Servers causes a loss of failover ability in the following scenarios:</span></span>
  
- <span data-ttu-id="58cea-314">與執行 Lync Server 2010 之前發行之商務用 Skype Server 版本之組織的同盟。</span><span class="sxs-lookup"><span data-stu-id="58cea-314">Federation with organizations that are running versions of Skype for Business Server released prior to Lync Server 2010.</span></span>
    
- <span data-ttu-id="58cea-315">透過 XMPP IM) 服務 AOL 和 Yahoo！，除了型提供者和伺服器（如 Google 談話）之外的立即訊息 (交換，您也是目前唯一支援的 XMPP 合作夥伴。</span><span class="sxs-lookup"><span data-stu-id="58cea-315">Instant message exchange with users of public instant messaging (IM) services AOL and Yahoo!, in addition to XMPP-based providers and servers, such as Google Talk, currently the only supported XMPP partner.</span></span>
    
<span data-ttu-id="58cea-316">只要集區中的所有 Edge Server 都啟動並執行，這些案例就能運作，但是如果其中一個 Edge Server 無法使用，則在這些案例中任何傳送給該 Edge Server 的要求都會失敗，而不是路由至另一個 Edge Server。</span><span class="sxs-lookup"><span data-stu-id="58cea-316">These scenarios will work as long as all Edge Servers in the pool are up and running, but if one Edge Server is unavailable, any requests for these scenarios that are sent to it will fail, instead of routing to another Edge Server.</span></span>
  
 <span data-ttu-id="58cea-317">如果您使用的是 Exchange UM，您必須至少使用 Exchange 2013，以取得對 Edge 的商務用 Skype 伺服器 DNS 負載平衡支援。</span><span class="sxs-lookup"><span data-stu-id="58cea-317">If you are using Exchange UM, you must use a minimum of Exchange 2013 to get support for Skype for Business Server DNS load balancing on Edge.</span></span> <span data-ttu-id="58cea-318">如果您使用舊版的 Exchange，您的遠端使用者將不會有這些 Exchange UM 案例的容錯移轉功能：</span><span class="sxs-lookup"><span data-stu-id="58cea-318">If you use an earlier version of Exchange, your remote users will not have failover capabilities for these Exchange UM scenarios:</span></span>
  
- <span data-ttu-id="58cea-319">在電話上播放企業語音信箱</span><span class="sxs-lookup"><span data-stu-id="58cea-319">Playing their Enterprise voicemail on their phone</span></span>
    
- <span data-ttu-id="58cea-320">從 Exchange UM 自動語音應答轉接通話</span><span class="sxs-lookup"><span data-stu-id="58cea-320">Transferring calls from an Exchange UM Auto Attendant</span></span>
    
<span data-ttu-id="58cea-321">所有其他 Exchange UM 案例則會正常運作。</span><span class="sxs-lookup"><span data-stu-id="58cea-321">All other Exchange UM scenarios will work properly.</span></span>
  
<span data-ttu-id="58cea-p137">內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-p137">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a><span data-ttu-id="58cea-324">在 Edge Server 集區上部署 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-324">Deploying DNS Load Balancing on Edge Server Pools</span></span>

<span data-ttu-id="58cea-325">若要在 Edge Server 集區的外部介面上部署 DNS 負載平衡，您需要下列 DNS 項目：</span><span class="sxs-lookup"><span data-stu-id="58cea-325">To deploy DNS load balancing on the external interface of your Edge Server pool, you need the following DNS entries:</span></span>
  
- <span data-ttu-id="58cea-326">對於 Access Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="58cea-326">For the Access Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="58cea-327">每個專案都必須解析 Access Edge service (的 FQDN，例如，sip.contoso.com) 到集區中某一部 Edge Server 上的 Access Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-327">Each entry must resolve the FQDN of the Access Edge service (for example, sip.contoso.com) to the IP address of the Access Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="58cea-328">針對 Web 會議 Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="58cea-328">For the Web Conferencing Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="58cea-329">每個專案都必須解析 Web 會議 Edge service (的 FQDN，例如，webconf.contoso.com) 至集區中某一部 Edge Server 上的 Web 會議 Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-329">Each entry must resolve the FQDN of the Web Conferencing Edge service (for example, webconf.contoso.com) to the IP address of the Web Conferencing Edge service on one of the Edge Servers in the pool.</span></span>
    
- <span data-ttu-id="58cea-330">針對 Audio/Video Edge service，集區中的每一部伺服器都需要一個專案。</span><span class="sxs-lookup"><span data-stu-id="58cea-330">For the Audio/Video Edge service, you need one entry for each server in the pool.</span></span> <span data-ttu-id="58cea-331">每個專案都必須解析 Audio/Video Edge service 的 FQDN (例如，av.contoso.com) 至集區中某一部 Edge Server 上的 A/V Edge service 的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-331">Each entry must resolve the FQDN of the Audio/Video Edge service (for example, av.contoso.com) to the IP address of the A/V Edge service on one of the Edge Servers in the pool.</span></span>
    
<span data-ttu-id="58cea-332">若要在 Edge Server 集區的內部介面上部署 DNS 負載平衡，您必須新增一筆 DNS A 記錄，並讓它將 Edge Server 集區的內部 FQDN 解析為集區中每部伺服器的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="58cea-332">To deploy DNS load balancing on the internal interface of your Edge Server pool, you must add one DNS A record, which resolves the internal FQDN of the Edge Server pool to the IP address of each server in the pool.</span></span>
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a><span data-ttu-id="58cea-333">在中繼伺服器集區上使用 DNS 負載平衡</span><span class="sxs-lookup"><span data-stu-id="58cea-333">Using DNS Load Balancing on Mediation Server Pools</span></span>
<span data-ttu-id="58cea-334"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="58cea-334"><a name="BK_Mediation"> </a></span></span>

<span data-ttu-id="58cea-p141">您可以在獨立中繼伺服器集區上使用 DNS 負載平衡，所有 SIP 和媒體流量都是透過 DNS 負載平衡進行平衡處理。</span><span class="sxs-lookup"><span data-stu-id="58cea-p141">You can use DNS load balancing on stand-alone Mediation Server pools. All SIP and media traffic is balanced by DNS load balancing.</span></span>
  
<span data-ttu-id="58cea-337">若要在中繼伺服器集區上部署 DNS 負載平衡，您必須佈建 DNS，以將集區 FQDN (例如，mediationpool1.contoso.com) 解析為集區中所有伺服器的 IP 位址 (例如，192.168.1.1、192.168.1.2 等)。</span><span class="sxs-lookup"><span data-stu-id="58cea-337">To deploy DNS load balancing on a Mediation Server pool, you must provision DNS to resolve the pool FQDN (for example, mediationpool1.contoso.com) to the IP addresses of all the servers in the pool (for example, 192.168.1.1, 192.168.1.2, and so on).</span></span>
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a><span data-ttu-id="58cea-338">使用 DNS 負載平衡封鎖伺服器的流量</span><span class="sxs-lookup"><span data-stu-id="58cea-338">Blocking Traffic to a Server With DNS Load Balancing</span></span>
<span data-ttu-id="58cea-339"><a name="BK_Mediation"> </a></span><span class="sxs-lookup"><span data-stu-id="58cea-339"><a name="BK_Mediation"> </a></span></span>

<span data-ttu-id="58cea-340">如果您使用 DNS 負載平衡，而且需要封鎖特定電腦的流量，只是移除集區 FQDN 的 IP 位址專案是不夠的。</span><span class="sxs-lookup"><span data-stu-id="58cea-340">If you use DNS load balancing and you need to block traffic to a specific computer, it is not sufficient to just remove the IP address entries from the Pool FQDN.</span></span> <span data-ttu-id="58cea-341">您也必須移除電腦的 DNS 專案。</span><span class="sxs-lookup"><span data-stu-id="58cea-341">You must remove the DNS entry for the computer as well.</span></span> 
  
<span data-ttu-id="58cea-342">請注意，針對伺服器對伺服器的流量，商務用 Skype 伺服器使用拓撲感知負載平衡。</span><span class="sxs-lookup"><span data-stu-id="58cea-342">Note that for server-to-server traffic, Skype for Business Server uses topology-aware load balancing.</span></span> <span data-ttu-id="58cea-343">伺服器讀取中央管理存放區中已發佈的拓撲，以取得拓撲中的伺服器 Fqdn，並在伺服器間自動散佈流量。</span><span class="sxs-lookup"><span data-stu-id="58cea-343">Servers read the published topology in the Central Management store to obtain the FQDNs of servers in the topology, and automatically distribute the traffic among the servers.</span></span> <span data-ttu-id="58cea-344">若要封鎖伺服器接收伺服器對伺服器的流量，您必須從拓撲中移除伺服器。</span><span class="sxs-lookup"><span data-stu-id="58cea-344">To block a server from receiving server-to-server traffic, you must remove the server from the topology.</span></span> 
  

