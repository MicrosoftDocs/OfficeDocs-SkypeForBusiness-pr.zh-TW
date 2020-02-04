---
title: Lync Server 2013 硬體負載平衡器需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="fec75-102">Lync Server 2013 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fec75-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fec75-103">_**主題上次修改日期：** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="fec75-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="fec75-104">Lync Server 2013 縮放的合併邊緣拓朴已針對新部署的 DNS 負載平衡進行優化，主要與使用 Lync Server 的其他組織聯盟。</span><span class="sxs-lookup"><span data-stu-id="fec75-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="fec75-105">如果下列任何案例都需要高可用性，則必須在 Edge 伺服器池中使用硬體負載平衡器，以進行下列作業：</span><span class="sxs-lookup"><span data-stu-id="fec75-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="fec75-106">與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟</span><span class="sxs-lookup"><span data-stu-id="fec75-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="fec75-107">在 Exchange 2010 之前使用 Exchange UM 的遠端使用者的 exchange UM 與 SP1</span><span class="sxs-lookup"><span data-stu-id="fec75-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="fec75-108">公用 IM 使用者的連線能力</span><span class="sxs-lookup"><span data-stu-id="fec75-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fec75-109">在一個介面上使用 DNS 負載平衡，而另一個介面上的硬體負載平衡則不受支援。</span><span class="sxs-lookup"><span data-stu-id="fec75-109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="fec75-110">您必須針對兩種介面或 DNS 負載平衡使用硬體負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fec75-110">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fec75-111">如果您使用的是硬體負載平衡器，則必須將與內部網路的連線所部署的負載平衡器設定為只進行負載平衡，以便只對執行存取邊緣服務和 A/V 邊緣服務的伺服器進行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fec75-111">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service.</span></span> <span data-ttu-id="fec75-112">它無法將流量負載平衡到內部網路會議邊緣服務或內部 XMPP Proxy 服務。</span><span class="sxs-lookup"><span data-stu-id="fec75-112">It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fec75-113">Lync Server 2013 不支援直接伺服器返回（DSR） NAT。</span><span class="sxs-lookup"><span data-stu-id="fec75-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fec75-114">若要判斷您的硬體負載平衡器是否支援 Lync Server 2013 所需的必要功能，請參閱「Lync Server 2010 負載[http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)平衡器合作夥伴」。</span><span class="sxs-lookup"><span data-stu-id="fec75-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="fec75-115">執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fec75-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="fec75-116">以下是執行 A/V 邊緣服務的邊緣伺服器的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="fec75-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="fec75-117">針對內部和外部埠443關閉 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="fec75-117">Turn off TCP nagling for both internal and external ports 443.</span></span> <span data-ttu-id="fec75-118">Nagling 是將數個小型資料包合併成單一、較大的資料包以獲得更有效率的傳輸的程式。</span><span class="sxs-lookup"><span data-stu-id="fec75-118">Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="fec75-119">關閉外部埠範圍50000–59999的 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="fec75-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="fec75-120">請勿在內部或外部防火牆上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="fec75-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="fec75-121">Edge 內部介面必須在不同的網路上，而不是 Edge 伺服器外部介面且必須停用它們之間的路由。</span><span class="sxs-lookup"><span data-stu-id="fec75-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="fec75-122">執行 A/V 邊緣服務的邊緣伺服器外部介面必須使用可公開路由的 IP 位址，而且任何邊緣外部 IP 位址都沒有 NAT 或埠轉譯。</span><span class="sxs-lookup"><span data-stu-id="fec75-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="fec75-123">硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fec75-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="fec75-124">在 Lync Server 2013 for Web 服務中，以 Cookie 為基礎的關聯需求大大減少。</span><span class="sxs-lookup"><span data-stu-id="fec75-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="fec75-125">如果您要部署 Lync Server 2013，且不會保留任何 Lync Server 2010 前端伺服器或前端池，則不需要以 cookie 為基礎的持久性。</span><span class="sxs-lookup"><span data-stu-id="fec75-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="fec75-126">不過，如果您要暫時或永久保留任何 Lync Server 2010 前端伺服器或前端池，您仍然會在針對 Lync Server 2010 部署和設定的情況下，使用以 cookie 為基礎的持久性。</span><span class="sxs-lookup"><span data-stu-id="fec75-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec75-127"><STRONG>如果您決定使用以 cookie 為基礎的關聯，即使您的部署不需要它</STRONG>，也不會有任何負面影響可執行此動作。</span><span class="sxs-lookup"><span data-stu-id="fec75-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="fec75-128">針對**將不會使用**cookie 的關聯的部署：</span><span class="sxs-lookup"><span data-stu-id="fec75-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="fec75-129">在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。</span><span class="sxs-lookup"><span data-stu-id="fec75-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="fec75-130">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="fec75-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="fec75-131">針對**將使用**以 cookie 為基礎的關聯性的部署：</span><span class="sxs-lookup"><span data-stu-id="fec75-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="fec75-132">在埠4443的反向 proxy 發佈規則中，將 [**轉寄主機頭**] 設定為 True。</span><span class="sxs-lookup"><span data-stu-id="fec75-132">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="fec75-133">這可確保原始 URL 已轉寄。</span><span class="sxs-lookup"><span data-stu-id="fec75-133">This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="fec75-134">硬體負載平衡器 cookie 不能標示為 HTTPOnly</span><span class="sxs-lookup"><span data-stu-id="fec75-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="fec75-135">硬體負載平衡器 cookie 不能有到期時間</span><span class="sxs-lookup"><span data-stu-id="fec75-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="fec75-136">硬體負載平衡器 cookie 必須命名為**MS-WSMAN** （這是 Web 服務預期的值，且無法變更）</span><span class="sxs-lookup"><span data-stu-id="fec75-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="fec75-137">硬體負載平衡器 cookie 必須在每一個 HTTP 回應中設定（無論是否已在相同的 TCP 連線中先前的 HTTP 回應都已取得 cookie）。</span><span class="sxs-lookup"><span data-stu-id="fec75-137">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie.</span></span> <span data-ttu-id="fec75-138">如果負載平衡器針對每個 TCP 連線優化 cookie 插入，則不一定要使用該優化</span><span class="sxs-lookup"><span data-stu-id="fec75-138">If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fec75-139">典型的硬體負載平衡器設定使用來源位址關聯和20分鐘的 TCP 會話存留期，這對 Lync Server 和 Lync 2013 用戶端來說是很好的，因為會話狀態是透過用戶端使用量和/或應用程式互動來維護。</span><span class="sxs-lookup"><span data-stu-id="fec75-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="fec75-140">如果您要部署行動裝置，您的硬體負載平衡器必須能夠在 TCP 會話中的個別要求之間進行負載平衡（事實上，您必須能夠根據目標 IP 位址來載入個別的要求）。</span><span class="sxs-lookup"><span data-stu-id="fec75-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fec75-141">F5 硬體負載平衡器具有一個名為 [OneConnect] 的功能，可確保 TCP 連線中的每個要求都有個別的負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fec75-141">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="fec75-142">如果您要部署行動裝置，請確保您的硬體負載平衡器供應商支援相同的功能。</span><span class="sxs-lookup"><span data-stu-id="fec75-142">If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality.</span></span> <span data-ttu-id="fec75-143">最新的 Apple iOS 行動裝置 app 需要傳輸層安全性（TLS）版本1.2。</span><span class="sxs-lookup"><span data-stu-id="fec75-143">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span> <span data-ttu-id="fec75-144">F5 會針對此提供特定設定。</span><span class="sxs-lookup"><span data-stu-id="fec75-144">F5 provides specific settings for this.</span></span><BR><span data-ttu-id="fec75-145">如需協力廠商硬體負載平衡器的詳細資料，請參閱<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="fec75-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="fec75-146">以下是控制器和前臺端池 Web 服務的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="fec75-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="fec75-147">針對內部 Web 服務 Vip，請在\_硬體負載平衡器上設定源位址持久性（內部埠80，443）。</span><span class="sxs-lookup"><span data-stu-id="fec75-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="fec75-148">在 Lync Server 2013 中，\_來源位址暫留代表來自單一 IP 位址的多個連線，會一直傳送到一個伺服器，以維持會話狀態。</span><span class="sxs-lookup"><span data-stu-id="fec75-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="fec75-149">使用1800秒的 TCP 空閒超時。</span><span class="sxs-lookup"><span data-stu-id="fec75-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="fec75-150">在反向 proxy 與下一個躍點池的硬體負載平衡器之間，建立規則來允許 HTTPs：埠4443上的流量，從反向 proxy 傳送到硬體負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="fec75-150">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="fec75-151">硬體負載平衡器必須設定為在埠80、443和4443上聆聽。</span><span class="sxs-lookup"><span data-stu-id="fec75-151">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fec75-152">如需進一步瞭解硬體負載平衡器的設定，請參閱<A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-在 Lync Server 2013 中使用硬體負載平衡器進行合併的合併邊緣</A>。</span><span class="sxs-lookup"><span data-stu-id="fec75-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="fec75-153">硬體負載平衡器關聯需求摘要</span><span class="sxs-lookup"><span data-stu-id="fec75-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec75-154">用戶端/使用者位置</span><span class="sxs-lookup"><span data-stu-id="fec75-154">Client/user location</span></span></th>
<th><span data-ttu-id="fec75-155">外部 web 服務 FQDN 關聯需求</span><span class="sxs-lookup"><span data-stu-id="fec75-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="fec75-156">內部 web 服務 FQDN 關聯需求</span><span class="sxs-lookup"><span data-stu-id="fec75-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec75-157">Lync Web App （內部與外部使用者）</span><span class="sxs-lookup"><span data-stu-id="fec75-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="fec75-158">行動裝置（內部和外部使用者）</span><span class="sxs-lookup"><span data-stu-id="fec75-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="fec75-159">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="fec75-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fec75-160">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="fec75-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec75-161">Lync Web App （僅限外部使用者）</span><span class="sxs-lookup"><span data-stu-id="fec75-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="fec75-162">行動裝置（內部和外部使用者）</span><span class="sxs-lookup"><span data-stu-id="fec75-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="fec75-163">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="fec75-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fec75-164">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="fec75-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fec75-165">Lync Web App （僅限內部使用者）</span><span class="sxs-lookup"><span data-stu-id="fec75-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="fec75-166">行動裝置（未部署）</span><span class="sxs-lookup"><span data-stu-id="fec75-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="fec75-167">沒有關聯性</span><span class="sxs-lookup"><span data-stu-id="fec75-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fec75-168">來源位址關聯</span><span class="sxs-lookup"><span data-stu-id="fec75-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="fec75-169">硬體負載平衡器的埠監控</span><span class="sxs-lookup"><span data-stu-id="fec75-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="fec75-170">您可以在硬體負載平衡器上定義埠監視，以判斷因硬體或通訊失敗而無法使用特定服務的時間。</span><span class="sxs-lookup"><span data-stu-id="fec75-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="fec75-171">例如，如果前端伺服器或前端池發生故障，[前端伺服器服務（RTCSRV）] 停止，則 HLB 監視也應該停止在 Web 服務上接收流量。</span><span class="sxs-lookup"><span data-stu-id="fec75-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="fec75-172">您可以在 HLB 上執行埠監視，以監視下列各項：</span><span class="sxs-lookup"><span data-stu-id="fec75-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="fec75-173">前端伺服器使用者池– HLB 內部介面</span><span class="sxs-lookup"><span data-stu-id="fec75-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec75-174">虛擬 IP/埠</span><span class="sxs-lookup"><span data-stu-id="fec75-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="fec75-175">節點埠</span><span class="sxs-lookup"><span data-stu-id="fec75-175">Node Port</span></span></th>
<th><span data-ttu-id="fec75-176">節點電腦/監視器</span><span class="sxs-lookup"><span data-stu-id="fec75-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="fec75-177">持久性設定檔</span><span class="sxs-lookup"><span data-stu-id="fec75-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="fec75-178">筆記</span><span class="sxs-lookup"><span data-stu-id="fec75-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec75-179">&lt;網路&gt;池網頁-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="fec75-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="fec75-180">443</span><span class="sxs-lookup"><span data-stu-id="fec75-180">443</span></span></p></td>
<td><p><span data-ttu-id="fec75-181">443</span><span class="sxs-lookup"><span data-stu-id="fec75-181">443</span></span></p></td>
<td><p><span data-ttu-id="fec75-182">前端</span><span class="sxs-lookup"><span data-stu-id="fec75-182">Front End</span></span></p>
<p><span data-ttu-id="fec75-183">5061</span><span class="sxs-lookup"><span data-stu-id="fec75-183">5061</span></span></p></td>
<td><p><span data-ttu-id="fec75-184">從源</span><span class="sxs-lookup"><span data-stu-id="fec75-184">Source</span></span></p></td>
<td><p><span data-ttu-id="fec75-185">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec75-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec75-186">&lt;網路&gt;池網頁-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="fec75-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="fec75-187">80</span><span class="sxs-lookup"><span data-stu-id="fec75-187">80</span></span></p></td>
<td><p><span data-ttu-id="fec75-188">80</span><span class="sxs-lookup"><span data-stu-id="fec75-188">80</span></span></p></td>
<td><p><span data-ttu-id="fec75-189">前端</span><span class="sxs-lookup"><span data-stu-id="fec75-189">Front End</span></span></p>
<p><span data-ttu-id="fec75-190">5061</span><span class="sxs-lookup"><span data-stu-id="fec75-190">5061</span></span></p></td>
<td><p><span data-ttu-id="fec75-191">從源</span><span class="sxs-lookup"><span data-stu-id="fec75-191">Source</span></span></p></td>
<td><p><span data-ttu-id="fec75-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="fec75-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="fec75-193">前端伺服器使用者池– HLB 外部介面</span><span class="sxs-lookup"><span data-stu-id="fec75-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fec75-194">虛擬 IP/埠</span><span class="sxs-lookup"><span data-stu-id="fec75-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="fec75-195">節點埠</span><span class="sxs-lookup"><span data-stu-id="fec75-195">Node Port</span></span></th>
<th><span data-ttu-id="fec75-196">節點電腦/監視器</span><span class="sxs-lookup"><span data-stu-id="fec75-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="fec75-197">持久性設定檔</span><span class="sxs-lookup"><span data-stu-id="fec75-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="fec75-198">筆記</span><span class="sxs-lookup"><span data-stu-id="fec75-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fec75-199">&lt;pool&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="fec75-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="fec75-200">443</span><span class="sxs-lookup"><span data-stu-id="fec75-200">443</span></span></p></td>
<td><p><span data-ttu-id="fec75-201">4443</span><span class="sxs-lookup"><span data-stu-id="fec75-201">4443</span></span></p></td>
<td><p><span data-ttu-id="fec75-202">前端</span><span class="sxs-lookup"><span data-stu-id="fec75-202">Front End</span></span></p>
<p><span data-ttu-id="fec75-203">5061</span><span class="sxs-lookup"><span data-stu-id="fec75-203">5061</span></span></p></td>
<td><p><span data-ttu-id="fec75-204">無</span><span class="sxs-lookup"><span data-stu-id="fec75-204">None</span></span></p></td>
<td><p><span data-ttu-id="fec75-205">IP-HTTPS</span><span class="sxs-lookup"><span data-stu-id="fec75-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fec75-206">&lt;pool&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="fec75-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="fec75-207">80</span><span class="sxs-lookup"><span data-stu-id="fec75-207">80</span></span></p></td>
<td><p><span data-ttu-id="fec75-208">8080</span><span class="sxs-lookup"><span data-stu-id="fec75-208">8080</span></span></p></td>
<td><p><span data-ttu-id="fec75-209">前端</span><span class="sxs-lookup"><span data-stu-id="fec75-209">Front End</span></span></p>
<p><span data-ttu-id="fec75-210">5061</span><span class="sxs-lookup"><span data-stu-id="fec75-210">5061</span></span></p></td>
<td><p><span data-ttu-id="fec75-211">無</span><span class="sxs-lookup"><span data-stu-id="fec75-211">None</span></span></p></td>
<td><p><span data-ttu-id="fec75-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="fec75-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

