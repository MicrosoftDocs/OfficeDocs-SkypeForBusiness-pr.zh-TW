---
title: 連接埠摘要-單一合併邊緣搭配公用 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c307ff7318a426610cf371a3d6f55591a7c6ed0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="fcbb2-102">連接埠摘要-單一合併邊緣搭配 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcbb2-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="fcbb2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fcbb2-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="fcbb2-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="fcbb2-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="fcbb2-107">反向 proxy 和同盟的規劃資訊中找到[的案例反向 proxy 在 Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md)和[規劃 SIP 的 pbx、 XMPP 同盟和公用立即訊息處理 Lync Server 2013 中](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)各節中，分別。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="fcbb2-108">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="fcbb2-109">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="fcbb2-110">**使用公用 IP 位址的單一合併 edge 的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="fcbb2-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="fcbb2-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="fcbb2-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="fcbb2-112">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="fcbb2-112">Port and Protocol Details</span></span>

<span data-ttu-id="fcbb2-113">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="fcbb2-p103">若要啟用任何 Edge Service 的遠端存取，則必須允許 SIP 流量雙向流動，如輸入/輸出 Edge 流量圖中所說明。換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="fcbb2-116">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcbb2-117">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fcbb2-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fcbb2-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-118">Source IP address</span></span></th>
<th><span data-ttu-id="fcbb2-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-119">Destination IP address</span></span></th>
<th><span data-ttu-id="fcbb2-120">附註</span><span class="sxs-lookup"><span data-stu-id="fcbb2-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="fcbb2-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-122">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-122">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-123">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-124">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="fcbb2-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="fcbb2-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-126">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-127">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-127">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-128">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="fcbb2-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="fcbb2-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-130">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-131">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-131">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-132">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="fcbb2-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="fcbb2-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-134">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-135">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-135">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-136">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="fcbb2-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-137">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-138">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-138">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-139">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-140">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="fcbb2-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-141">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-142">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-142">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-143">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-144">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-145">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-146">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-147">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-147">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-148">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-149">Web 會議 /PSOM (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-150">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-150">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-151">Edge Server Web Conferencing Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-152">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="fcbb2-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="fcbb2-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-154">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-155">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-155">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-156">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="fcbb2-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-158">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-159">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-159">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-160">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="fcbb2-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="fcbb2-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-162">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-162">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-163">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-164">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="fcbb2-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-166">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-166">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-167">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-168">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-169">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fcbb2-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-170">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-171">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-171">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-172">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="fcbb2-173">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-174">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fcbb2-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-175">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-175">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-176">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-177">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="fcbb2-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-178">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-179">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-179">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-180">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-181">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="fcbb2-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-182">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-183">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-184">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-184">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-185">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="fcbb2-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="fcbb2-186">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcbb2-187">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fcbb2-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fcbb2-188">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-188">Source IP address</span></span></th>
<th><span data-ttu-id="fcbb2-189">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-189">Destination IP address</span></span></th>
<th><span data-ttu-id="fcbb2-190">註解</span><span class="sxs-lookup"><span data-stu-id="fcbb2-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="fcbb2-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-192">任何 （可定義為 Standard Edition server IP、 Standard Edition server IP 位址或執行 XMPP 閘道服務的集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-193">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-194">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="fcbb2-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-196">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-197">Edge Server IP 或主控內部介面的集區</span><span class="sxs-lookup"><span data-stu-id="fcbb2-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-198">輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-201">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區位址）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-202">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="fcbb2-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="fcbb2-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-204">任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-205">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-206">從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="fcbb2-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="fcbb2-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-208">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-209">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-210">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="fcbb2-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fcbb2-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-212">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-212">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-213">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-214">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="fcbb2-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-216">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-216">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-217">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-218">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="fcbb2-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-220">任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="fcbb2-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-221">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-222">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="fcbb2-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="fcbb2-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-224">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-224">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-225">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-226">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="fcbb2-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="fcbb2-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-228">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-228">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-229">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-230">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="fcbb2-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="fcbb2-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-232">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-232">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-233">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="fcbb2-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-234">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="fcbb2-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="fcbb2-235">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="fcbb2-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcbb2-236">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fcbb2-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fcbb2-237">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-237">Source IP address</span></span></th>
<th><span data-ttu-id="fcbb2-238">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-238">Destination IP address</span></span></th>
<th><span data-ttu-id="fcbb2-239">附註</span><span class="sxs-lookup"><span data-stu-id="fcbb2-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-240">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-241">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-242">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-242">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-243">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="fcbb2-244">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcbb2-245">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fcbb2-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fcbb2-246">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-246">Source IP address</span></span></th>
<th><span data-ttu-id="fcbb2-247">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-247">Destination IP address</span></span></th>
<th><span data-ttu-id="fcbb2-248">附註</span><span class="sxs-lookup"><span data-stu-id="fcbb2-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-249">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-250">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="fcbb2-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-251">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-252">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-253">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="fcbb2-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-255">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="fcbb2-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-256">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="fcbb2-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-257">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="fcbb2-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-258">用戶端</span><span class="sxs-lookup"><span data-stu-id="fcbb2-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-259">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-260">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="fcbb2-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="fcbb2-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-262">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-263">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="fcbb2-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-264">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="fcbb2-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-265">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fcbb2-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-266">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-267">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="fcbb2-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-268">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="fcbb2-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-269">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="fcbb2-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-270">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="fcbb2-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-271">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="fcbb2-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-272">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="fcbb2-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="fcbb2-273">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="fcbb2-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fcbb2-274">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="fcbb2-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="fcbb2-275">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="fcbb2-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="fcbb2-276">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="fcbb2-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="fcbb2-277">註解</span><span class="sxs-lookup"><span data-stu-id="fcbb2-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="fcbb2-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-279">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-279">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-280">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-281">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="fcbb2-282">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="fcbb2-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fcbb2-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="fcbb2-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-284">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-285">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-285">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-286">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="fcbb2-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="fcbb2-287">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="fcbb2-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fcbb2-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="fcbb2-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-289">任何</span><span class="sxs-lookup"><span data-stu-id="fcbb2-289">Any</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-290">每個內部的 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="fcbb2-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="fcbb2-291">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="fcbb2-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

