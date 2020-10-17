---
title: Lync Server 2013 硬體負載平衡器需求
description: Lync Server 2013 硬體負載平衡器需求。
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
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552919"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="fe46c-103">Lync Server 2013 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fe46c-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe46c-104">_**主題上次修改日期：** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="fe46c-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="fe46c-105">Lync Server 2013 調整式合併 Edge 拓撲已針對新部署的 DNS 負載平衡進行優化，主要與使用 Lync Server 的其他組織合作。</span><span class="sxs-lookup"><span data-stu-id="fe46c-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="fe46c-106">如果在下列任一情況下需要高可用性，則必須在 Edge Server 集區上使用硬體負載平衡器予以因應：</span><span class="sxs-lookup"><span data-stu-id="fe46c-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="fe46c-107">與使用 Office 通訊伺服器 2007 R2 或 Office 通訊伺服器2007的組織同盟</span><span class="sxs-lookup"><span data-stu-id="fe46c-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="fe46c-108">Exchange 2010 與 SP1 前使用 Exchange UM 的遠端使用者 exchange UM</span><span class="sxs-lookup"><span data-stu-id="fe46c-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="fe46c-109">公用 IM 使用者的連線</span><span class="sxs-lookup"><span data-stu-id="fe46c-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe46c-p102">不支援在一個介面上使用 DNS 負載平衡，而在另一個介面上使用硬體負載平衡。您必須同時針對這兩個介面使用硬體負載平衡或 DNS 負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fe46c-p103">在您使用硬體負載平衡器時，針對內部網路的連線所部署的負載平衡器必須經過設定，使其僅對流向執行 Access Edge Service 與 A/V Edge Service 之伺服器的流量執行負載平衡。對於流向內部 Web Conferencing Edge Service 或內部 XMPP Proxy 服務的流量，不可執行負載平衡。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fe46c-114">Lync Server 2013 不支援 direct server return (DSR) NAT。</span><span class="sxs-lookup"><span data-stu-id="fe46c-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="fe46c-115">若要判斷您的硬體負載平衡器是否支援 Lync Server 2013 所需的必要功能，請參閱 at 中的「Lync Server 2010 負載平衡器合作夥伴」 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) 。</span><span class="sxs-lookup"><span data-stu-id="fe46c-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="fe46c-116">執行 A/V Edge Service 之 Edge Server 的硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fe46c-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="fe46c-117">以下是執行 A/V Edge service 之 Edge Server 的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="fe46c-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="fe46c-p104">關閉內部及外部連接埠 443 的 TCP Nagling。Nagling 是一種程序，將數個小型封包合併為較大型的單一封包以進行有效傳輸。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="fe46c-120">關閉外部連接埠範圍 50,000 - 59,999 的 TCP Nagling。</span><span class="sxs-lookup"><span data-stu-id="fe46c-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="fe46c-121">不要在內部或外部防火牆上使用 NAT。</span><span class="sxs-lookup"><span data-stu-id="fe46c-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="fe46c-122">Edge 內部介面必須與 Edge 外部介面位在不同的網路上，而且必須停用在它們之間進行的路由傳送作業。</span><span class="sxs-lookup"><span data-stu-id="fe46c-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="fe46c-123">執行 A/V Edge Service 之 Edge Server 的外部介面必須使用可公開路由傳送的 IP 位址，而且任何 Edge 外部 IP 位址上都沒有 NAT 或埠轉譯。</span><span class="sxs-lookup"><span data-stu-id="fe46c-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="fe46c-124">硬體負載平衡器需求</span><span class="sxs-lookup"><span data-stu-id="fe46c-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="fe46c-125">在 Web 服務的 Lync Server 2013 中，會大幅減少 Cookie 基礎的親近性需求。</span><span class="sxs-lookup"><span data-stu-id="fe46c-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="fe46c-126">如果您部署的是 Lync Server 2013，而且不會保留任何 Lync Server 2010 前端伺服器或前端集區，則不需要以 cookie 為基礎的持久性集。</span><span class="sxs-lookup"><span data-stu-id="fe46c-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="fe46c-127">不過，如果您暫時或永久保留任何 Lync Server 2010 前端伺服器或前端集區，您仍會使用以 cookie 為基礎的持久性，因為它是針對 Lync Server 2010 部署及設定。</span><span class="sxs-lookup"><span data-stu-id="fe46c-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe46c-128"><STRONG>如果您決定使用 Cookie 型相似性 (即使您的部署不需要它)</STRONG>，則這樣做並不會產生任何負面影響。</span><span class="sxs-lookup"><span data-stu-id="fe46c-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="fe46c-129">針對**不使用** Cookie 型相似性的部署：</span><span class="sxs-lookup"><span data-stu-id="fe46c-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="fe46c-p106">在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="fe46c-132">針對**將使用** Cookie 型相似性的部署：</span><span class="sxs-lookup"><span data-stu-id="fe46c-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="fe46c-p107">在連接埠 4443 的反向 Proxy 發行規則上，將 **[轉送主機標頭]** 設為 True。這會確保轉送原始 URL。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="fe46c-135">硬體負載平衡器 Cookie「絕不能」標示為 httpOnly</span><span class="sxs-lookup"><span data-stu-id="fe46c-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="fe46c-136">硬體負載平衡器 Cookie「絕不能」有到期時間</span><span class="sxs-lookup"><span data-stu-id="fe46c-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="fe46c-137">硬體負載平衡器 Cookie「必須」命名為 **MS-WSMAN** (此為 Web 服務預期的值且無法變更)</span><span class="sxs-lookup"><span data-stu-id="fe46c-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="fe46c-p108">無論該相同 TCP 連線上先前的 HTTP 回應是否已取得 Cookie，在傳入 HTTP 要求沒有 Cookie 的每個 HTTP 回應中，都「必須」設定硬體負載平衡器 Cookie。如果負載平衡器將 Cookie 插入最佳化成針對每個 TCP 連線只出現一次，則「絕不能」使用該最佳化</span><span class="sxs-lookup"><span data-stu-id="fe46c-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fe46c-140">一般硬體負載平衡器設定會使用來源位址親近性和20分鐘的 TCP 會話壽命，這對 Lync Server 和 Lync 2013 用戶端而言是很好的，因為會話狀態是透過用戶端使用方式和/或應用程式互動來維護。</span><span class="sxs-lookup"><span data-stu-id="fe46c-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="fe46c-141">如果您正在部署行動裝置，硬體負載平衡器就必須能夠在 TCP 工作階段中負載平衡個別要求 (實際上，您必須能夠根據目標 IP 位址來負載平衡個別要求)。</span><span class="sxs-lookup"><span data-stu-id="fe46c-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="fe46c-p109">F5 硬體負載平衡器有一項叫做 OneConnect 的功能，可以確保 TCP 連線中的每個要求都能個別負載平衡。如果您正在部署行動裝置，請確定硬體負載平衡器廠商支援相同的功能。最新版的 Apple iOS 行動應用程式需要傳輸層安全性 (TLS) 版本 1.2。F5 提供適用於此版本的特殊設定。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="fe46c-146">如需協力廠商硬體負載平衡器的詳細資訊，請參閱 <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="fe46c-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="fe46c-147">下面是 Director 與前端集區 Web 服務的硬體負載平衡器需求：</span><span class="sxs-lookup"><span data-stu-id="fe46c-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="fe46c-148">針對 [內部 Web 服務] Vip，設定 \_ 硬體負載平衡器上的 [來源位址] 持久性 (內部埠80，443) 。</span><span class="sxs-lookup"><span data-stu-id="fe46c-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="fe46c-149">針對 Lync Server 2013，來源 \_ 位址暫留表示來自單一 IP 位址的多個連線，永遠會傳送至一部伺服器以維護會話狀態。</span><span class="sxs-lookup"><span data-stu-id="fe46c-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="fe46c-150">使用 TCP 閒置逾時：1800 秒。</span><span class="sxs-lookup"><span data-stu-id="fe46c-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="fe46c-p111">在反向 Proxy 與下一個躍點集區之硬體負載平衡器間的防火牆上，建立允許 https 的規則：連接埠 4443 上從反向 Proxy 到硬體負載平衡器的流量。硬體負載平衡器必須設定成接聽連接埠 80、443 及 4443。</span><span class="sxs-lookup"><span data-stu-id="fe46c-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fe46c-153">如需硬體負載平衡器設定的進一步閱讀，請參閱通訊 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">埠摘要-調整式合併 edge （在 Lync Server 2013 中使用硬體負載平衡</A>器）。</span><span class="sxs-lookup"><span data-stu-id="fe46c-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="fe46c-154">硬體負載平衡器相似性需求摘要</span><span class="sxs-lookup"><span data-stu-id="fe46c-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe46c-155">用戶端/使用者位置</span><span class="sxs-lookup"><span data-stu-id="fe46c-155">Client/user location</span></span></th>
<th><span data-ttu-id="fe46c-156">外部 Web 服務 FQDN 相似性需求</span><span class="sxs-lookup"><span data-stu-id="fe46c-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="fe46c-157">內部 Web 服務 FQDN 相似性需求</span><span class="sxs-lookup"><span data-stu-id="fe46c-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe46c-158">Lync Web App (內部及外部使用者) </span><span class="sxs-lookup"><span data-stu-id="fe46c-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="fe46c-159">行動裝置 (內部和外部使用者)</span><span class="sxs-lookup"><span data-stu-id="fe46c-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="fe46c-160">無相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fe46c-161">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe46c-162">Lync Web App (僅限外部使用者) </span><span class="sxs-lookup"><span data-stu-id="fe46c-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="fe46c-163">行動裝置 (內部和外部使用者)</span><span class="sxs-lookup"><span data-stu-id="fe46c-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="fe46c-164">無相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fe46c-165">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe46c-166">Lync Web App (僅限內部使用者) </span><span class="sxs-lookup"><span data-stu-id="fe46c-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="fe46c-167">行動裝置 (未部署)</span><span class="sxs-lookup"><span data-stu-id="fe46c-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="fe46c-168">無相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="fe46c-169">來源位址相似性</span><span class="sxs-lookup"><span data-stu-id="fe46c-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="fe46c-170">適用於硬體負載平衡器的連接埠監控</span><span class="sxs-lookup"><span data-stu-id="fe46c-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="fe46c-171">您可以在硬體負載平衡器上定義連接埠監控，以判斷特定的服務何時因為發生硬體或通訊失敗而無法使用。</span><span class="sxs-lookup"><span data-stu-id="fe46c-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="fe46c-172">例如，如果前端伺服器服務 (RTCSRV) 停止，因為前端伺服器或前端集區失敗，則 HLB 監視也應停止接收 Web 服務的流量。</span><span class="sxs-lookup"><span data-stu-id="fe46c-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="fe46c-173">您可以在 HLB 上實作連接埠監控以監控下列各項：</span><span class="sxs-lookup"><span data-stu-id="fe46c-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="fe46c-174">前端伺服器使用者集區– HLB 內部介面</span><span class="sxs-lookup"><span data-stu-id="fe46c-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="fe46c-175">虛擬 IP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fe46c-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="fe46c-176">節點連接埠</span><span class="sxs-lookup"><span data-stu-id="fe46c-176">Node Port</span></span></th>
<th><span data-ttu-id="fe46c-177">節點電腦/監視器</span><span class="sxs-lookup"><span data-stu-id="fe46c-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="fe46c-178">持續性設定檔</span><span class="sxs-lookup"><span data-stu-id="fe46c-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="fe46c-179">注意事項</span><span class="sxs-lookup"><span data-stu-id="fe46c-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe46c-180">&lt;集區 &gt; web int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="fe46c-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="fe46c-181">443</span><span class="sxs-lookup"><span data-stu-id="fe46c-181">443</span></span></p></td>
<td><p><span data-ttu-id="fe46c-182">443</span><span class="sxs-lookup"><span data-stu-id="fe46c-182">443</span></span></p></td>
<td><p><span data-ttu-id="fe46c-183">前端</span><span class="sxs-lookup"><span data-stu-id="fe46c-183">Front End</span></span></p>
<p><span data-ttu-id="fe46c-184">5061</span><span class="sxs-lookup"><span data-stu-id="fe46c-184">5061</span></span></p></td>
<td><p><span data-ttu-id="fe46c-185">來源</span><span class="sxs-lookup"><span data-stu-id="fe46c-185">Source</span></span></p></td>
<td><p><span data-ttu-id="fe46c-186">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fe46c-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe46c-187">&lt;集區 &gt; web int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="fe46c-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="fe46c-188">80</span><span class="sxs-lookup"><span data-stu-id="fe46c-188">80</span></span></p></td>
<td><p><span data-ttu-id="fe46c-189">80</span><span class="sxs-lookup"><span data-stu-id="fe46c-189">80</span></span></p></td>
<td><p><span data-ttu-id="fe46c-190">前端</span><span class="sxs-lookup"><span data-stu-id="fe46c-190">Front End</span></span></p>
<p><span data-ttu-id="fe46c-191">5061</span><span class="sxs-lookup"><span data-stu-id="fe46c-191">5061</span></span></p></td>
<td><p><span data-ttu-id="fe46c-192">來源</span><span class="sxs-lookup"><span data-stu-id="fe46c-192">Source</span></span></p></td>
<td><p><span data-ttu-id="fe46c-193">HTTP:</span><span class="sxs-lookup"><span data-stu-id="fe46c-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="fe46c-194">前端伺服器使用者集區– HLB 外部介面</span><span class="sxs-lookup"><span data-stu-id="fe46c-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="fe46c-195">虛擬 IP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fe46c-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="fe46c-196">節點連接埠</span><span class="sxs-lookup"><span data-stu-id="fe46c-196">Node Port</span></span></th>
<th><span data-ttu-id="fe46c-197">節點電腦/監視器</span><span class="sxs-lookup"><span data-stu-id="fe46c-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="fe46c-198">持續性設定檔</span><span class="sxs-lookup"><span data-stu-id="fe46c-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="fe46c-199">注意事項</span><span class="sxs-lookup"><span data-stu-id="fe46c-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe46c-200">&lt;集區 &gt; web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="fe46c-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="fe46c-201">443</span><span class="sxs-lookup"><span data-stu-id="fe46c-201">443</span></span></p></td>
<td><p><span data-ttu-id="fe46c-202">4443</span><span class="sxs-lookup"><span data-stu-id="fe46c-202">4443</span></span></p></td>
<td><p><span data-ttu-id="fe46c-203">前端</span><span class="sxs-lookup"><span data-stu-id="fe46c-203">Front End</span></span></p>
<p><span data-ttu-id="fe46c-204">5061</span><span class="sxs-lookup"><span data-stu-id="fe46c-204">5061</span></span></p></td>
<td><p><span data-ttu-id="fe46c-205">無</span><span class="sxs-lookup"><span data-stu-id="fe46c-205">None</span></span></p></td>
<td><p><span data-ttu-id="fe46c-206">HTTPS:</span><span class="sxs-lookup"><span data-stu-id="fe46c-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe46c-207">&lt;集區 &gt; web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="fe46c-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="fe46c-208">80</span><span class="sxs-lookup"><span data-stu-id="fe46c-208">80</span></span></p></td>
<td><p><span data-ttu-id="fe46c-209">8080</span><span class="sxs-lookup"><span data-stu-id="fe46c-209">8080</span></span></p></td>
<td><p><span data-ttu-id="fe46c-210">前端</span><span class="sxs-lookup"><span data-stu-id="fe46c-210">Front End</span></span></p>
<p><span data-ttu-id="fe46c-211">5061</span><span class="sxs-lookup"><span data-stu-id="fe46c-211">5061</span></span></p></td>
<td><p><span data-ttu-id="fe46c-212">無</span><span class="sxs-lookup"><span data-stu-id="fe46c-212">None</span></span></p></td>
<td><p><span data-ttu-id="fe46c-213">HTTP:</span><span class="sxs-lookup"><span data-stu-id="fe46c-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

