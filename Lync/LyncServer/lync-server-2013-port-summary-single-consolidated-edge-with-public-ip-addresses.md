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
ms.openlocfilehash: 9020821da26c39094e7c04f3cbf72875b91ffaff
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043135"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="f418a-102">連接埠摘要-單一合併邊緣搭配 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f418a-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="f418a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f418a-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="f418a-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="f418a-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="f418a-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="f418a-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="f418a-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="f418a-107">反向 proxy 和同盟的規劃資訊中找到[的案例反向 proxy 在 Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md)和[規劃 SIP 的 pbx、 XMPP 同盟和公用立即訊息處理 Lync Server 2013 中](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)各節中，分別。</span><span class="sxs-lookup"><span data-stu-id="f418a-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="f418a-108">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="f418a-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="f418a-109">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="f418a-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="f418a-110">**使用公用 IP 位址的單一合併 edge 的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="f418a-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="f418a-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="f418a-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="f418a-112">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="f418a-112">Port and Protocol Details</span></span>

<span data-ttu-id="f418a-113">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="f418a-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="f418a-p103">若要啟用任何 Edge Service 的遠端存取，則必須允許 SIP 流量雙向流動，如輸入/輸出 Edge 流量圖中所說明。換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="f418a-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="f418a-116">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f418a-117">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="f418a-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f418a-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-118">Source IP address</span></span></th>
<th><span data-ttu-id="f418a-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-119">Destination IP address</span></span></th>
<th><span data-ttu-id="f418a-120">附註</span><span class="sxs-lookup"><span data-stu-id="f418a-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f418a-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f418a-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f418a-122">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-122">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-123">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="f418a-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="f418a-124">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="f418a-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="f418a-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="f418a-126">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-127">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-127">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-128">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="f418a-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="f418a-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="f418a-130">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-131">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-132">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="f418a-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="f418a-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="f418a-134">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-135">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-135">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-136">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="f418a-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-137">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-138">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-139">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-140">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="f418a-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-141">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-142">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-142">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-143">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-144">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f418a-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-145">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-146">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-147">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-147">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-148">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f418a-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-149">Web 會議 /PSOM (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-150">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-150">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-151">Edge Server Web Conferencing Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-152">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="f418a-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f418a-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f418a-154">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-155">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-155">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-156">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f418a-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f418a-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f418a-158">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-159">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-159">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-160">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="f418a-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f418a-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f418a-162">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-162">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-163">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-164">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="f418a-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f418a-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f418a-166">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-166">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-167">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-168">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="f418a-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-169">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f418a-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f418a-170">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-171">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-171">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-172">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="f418a-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="f418a-173">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="f418a-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-174">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f418a-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f418a-175">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-175">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-176">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-177">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="f418a-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-178">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-179">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-179">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-180">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-181">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="f418a-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-182">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-183">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-184">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-184">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-185">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="f418a-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="f418a-186">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f418a-187">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="f418a-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f418a-188">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-188">Source IP address</span></span></th>
<th><span data-ttu-id="f418a-189">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-189">Destination IP address</span></span></th>
<th><span data-ttu-id="f418a-190">註解</span><span class="sxs-lookup"><span data-stu-id="f418a-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f418a-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="f418a-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="f418a-192">任何 （可定義為 Standard Edition server IP、 Standard Edition server IP 位址或執行 XMPP 閘道服務的集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="f418a-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="f418a-193">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-194">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="f418a-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-196">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="f418a-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="f418a-197">Edge Server IP 或主控內部介面的集區</span><span class="sxs-lookup"><span data-stu-id="f418a-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-198">輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-201">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區位址）</span><span class="sxs-lookup"><span data-stu-id="f418a-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="f418a-202">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="f418a-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="f418a-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="f418a-204">任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="f418a-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="f418a-205">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-206">從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="f418a-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="f418a-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="f418a-208">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="f418a-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="f418a-209">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-210">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="f418a-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f418a-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f418a-212">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-212">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-213">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-214">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="f418a-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-216">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-216">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-217">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-218">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="f418a-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="f418a-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="f418a-220">任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="f418a-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="f418a-221">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-222">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="f418a-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="f418a-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="f418a-224">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-224">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-225">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-226">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="f418a-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="f418a-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="f418a-228">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-228">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-229">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-230">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="f418a-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="f418a-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="f418a-232">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-232">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-233">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="f418a-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="f418a-234">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="f418a-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="f418a-235">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="f418a-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f418a-236">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="f418a-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f418a-237">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-237">Source IP address</span></span></th>
<th><span data-ttu-id="f418a-238">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-238">Destination IP address</span></span></th>
<th><span data-ttu-id="f418a-239">附註</span><span class="sxs-lookup"><span data-stu-id="f418a-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f418a-240">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-241">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-242">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-242">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-243">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f418a-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="f418a-244">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="f418a-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f418a-245">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="f418a-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f418a-246">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-246">Source IP address</span></span></th>
<th><span data-ttu-id="f418a-247">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-247">Destination IP address</span></span></th>
<th><span data-ttu-id="f418a-248">附註</span><span class="sxs-lookup"><span data-stu-id="f418a-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f418a-249">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-250">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="f418a-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f418a-251">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-252">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f418a-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-253">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="f418a-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="f418a-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-255">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="f418a-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="f418a-256">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="f418a-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-257">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="f418a-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="f418a-258">用戶端</span><span class="sxs-lookup"><span data-stu-id="f418a-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="f418a-259">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-260">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="f418a-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="f418a-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="f418a-262">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-263">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="f418a-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f418a-264">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="f418a-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-265">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f418a-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f418a-266">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-267">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="f418a-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f418a-268">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="f418a-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-269">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="f418a-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="f418a-270">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="f418a-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="f418a-271">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="f418a-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="f418a-272">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="f418a-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="f418a-273">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="f418a-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f418a-274">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="f418a-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="f418a-275">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="f418a-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="f418a-276">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="f418a-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="f418a-277">註解</span><span class="sxs-lookup"><span data-stu-id="f418a-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f418a-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f418a-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f418a-279">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-279">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-280">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-281">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="f418a-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f418a-282">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="f418a-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f418a-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="f418a-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="f418a-284">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="f418a-285">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-285">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-286">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="f418a-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="f418a-287">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="f418a-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f418a-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="f418a-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="f418a-289">任何</span><span class="sxs-lookup"><span data-stu-id="f418a-289">Any</span></span></p></td>
<td><p><span data-ttu-id="f418a-290">每個內部的 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="f418a-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="f418a-291">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="f418a-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

