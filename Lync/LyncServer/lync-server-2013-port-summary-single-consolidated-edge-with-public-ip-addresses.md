---
title: 連接埠摘要 - 含公用 IP 位址的單一合併 Edge
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="19bf0-102">Lync Server 2013 中的連接埠摘要 - 含公用 IP 位址的單一合併 Edge</span><span class="sxs-lookup"><span data-stu-id="19bf0-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19bf0-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="19bf0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="19bf0-104">此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。</span><span class="sxs-lookup"><span data-stu-id="19bf0-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="19bf0-105">最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。</span><span class="sxs-lookup"><span data-stu-id="19bf0-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="19bf0-106">Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="19bf0-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="19bf0-107">在 lync server [2013 的反向 Proxy 案例中](lync-server-2013-scenarios-for-reverse-proxy.md)，以及在[lync server 2013 區段中規劃 SIP、XMPP 同盟及公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md)，都可在反向 proxy 與同盟的規劃資訊中找到。</span><span class="sxs-lookup"><span data-stu-id="19bf0-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="19bf0-108">除了 IPv4，Edge 伺服器現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="19bf0-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="19bf0-109">為清楚起見，在案例中只使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="19bf0-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="19bf0-110">**含公用 IP 位址的單一整合邊緣的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="19bf0-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="19bf0-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="19bf0-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="19bf0-112">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="19bf0-112">Port and Protocol Details</span></span>

<span data-ttu-id="19bf0-113">我們建議您只開啟支援您提供外部存取的功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="19bf0-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="19bf0-114">若要讓遠端存取作用於任何 edge 服務，必須 SIP 流量可以流過 bidirectionally，如入站/出站邊緣流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="19bf0-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="19bf0-115">換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="19bf0-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="19bf0-116">含公用 IP 位址之單一合併邊緣的防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bf0-117">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="19bf0-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="19bf0-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-118">Source IP address</span></span></th>
<th><span data-ttu-id="19bf0-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-119">Destination IP address</span></span></th>
<th><span data-ttu-id="19bf0-120">筆記</span><span class="sxs-lookup"><span data-stu-id="19bf0-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="19bf0-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="19bf0-122">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-122">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-123">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-124">XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="19bf0-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="19bf0-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="19bf0-126">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-127">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-127">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-128">憑證吊銷/CRL 檢查及檢索</span><span class="sxs-lookup"><span data-stu-id="19bf0-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="19bf0-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="19bf0-130">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-131">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-131">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-132">TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="19bf0-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="19bf0-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="19bf0-134">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-135">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-135">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-136">經由 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="19bf0-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-137">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-138">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-138">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-139">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-140">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="19bf0-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-141">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-142">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-142">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-143">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-144">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="19bf0-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-145">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-146">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-147">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-147">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-148">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="19bf0-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-149">網路會議/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-150">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-150">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-151">Edge 伺服器網路會議 Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-152">網路會議媒體</span><span class="sxs-lookup"><span data-stu-id="19bf0-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="19bf0-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="19bf0-154">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-155">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-155">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-156">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</span><span class="sxs-lookup"><span data-stu-id="19bf0-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="19bf0-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="19bf0-158">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-159">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-159">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-160">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="19bf0-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="19bf0-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="19bf0-162">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-162">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-163">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-164">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="19bf0-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="19bf0-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="19bf0-166">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-166">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-167">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-168">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="19bf0-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="19bf0-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="19bf0-170">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-171">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-171">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-172">3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="19bf0-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="19bf0-173">使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</span><span class="sxs-lookup"><span data-stu-id="19bf0-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="19bf0-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="19bf0-175">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-175">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-176">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-177">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="19bf0-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-178">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-179">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-179">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-180">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-181">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="19bf0-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-183">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-184">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-184">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-185">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="19bf0-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="19bf0-186">含公用 IP 位址之單一合併邊緣的防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bf0-187">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="19bf0-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="19bf0-188">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-188">Source IP address</span></span></th>
<th><span data-ttu-id="19bf0-189">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-189">Destination IP address</span></span></th>
<th><span data-ttu-id="19bf0-190">批註</span><span class="sxs-lookup"><span data-stu-id="19bf0-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="19bf0-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="19bf0-192">[任何] （可定義為標準版伺服器 IP、標準版伺服器 IP 位址或執行 XMPP 閘道服務的池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-193">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-194">在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="19bf0-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-196">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-197">包含內部介面的邊緣伺服器 IP 或池</span><span class="sxs-lookup"><span data-stu-id="19bf0-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-198">輸出 SIP 流量（從控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）到邊緣伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-200">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-201">[任何] （可以定義為 [控制器]、[控制器池] IP 位址、[前端伺服器] 或 [前端池] 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-202">來自 Edge 伺服器內部介面的入站 SIP 流量（到控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="19bf0-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="19bf0-204">Any （可定義為前端伺服器 IP 位址，或前端池中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-205">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-206">從前臺伺服器或每個前端伺服器的網路會議流量（如果在池中）到 Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="19bf0-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="19bf0-208">[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="19bf0-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-209">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-210">使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</span><span class="sxs-lookup"><span data-stu-id="19bf0-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="19bf0-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="19bf0-212">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-212">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-213">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-214">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="19bf0-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-216">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-216">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-217">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-218">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="19bf0-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="19bf0-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-220">[任何] （可定義為 [前端伺服器 IP 位址] 或 [擁有中央管理儲存區的池）]</span><span class="sxs-lookup"><span data-stu-id="19bf0-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="19bf0-221">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-222">從中央管理儲存體將變更複製到 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="19bf0-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="19bf0-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="19bf0-224">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-224">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-225">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-226">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="19bf0-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="19bf0-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="19bf0-228">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-228">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-229">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-230">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="19bf0-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="19bf0-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="19bf0-232">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-232">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-233">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="19bf0-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="19bf0-234">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="19bf0-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="19bf0-235">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="19bf0-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bf0-236">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="19bf0-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="19bf0-237">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-237">Source IP address</span></span></th>
<th><span data-ttu-id="19bf0-238">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-238">Destination IP address</span></span></th>
<th><span data-ttu-id="19bf0-239">筆記</span><span class="sxs-lookup"><span data-stu-id="19bf0-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-240">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-241">存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-242">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-242">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-243">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="19bf0-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="19bf0-244">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="19bf0-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bf0-245">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="19bf0-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="19bf0-246">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-246">Source IP address</span></span></th>
<th><span data-ttu-id="19bf0-247">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-247">Destination IP address</span></span></th>
<th><span data-ttu-id="19bf0-248">筆記</span><span class="sxs-lookup"><span data-stu-id="19bf0-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-249">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-250">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="19bf0-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="19bf0-251">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-252">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="19bf0-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-253">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="19bf0-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="19bf0-254">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-255">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="19bf0-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="19bf0-256">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="19bf0-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-257">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="19bf0-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="19bf0-258">台</span><span class="sxs-lookup"><span data-stu-id="19bf0-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="19bf0-259">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-260">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="19bf0-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="19bf0-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="19bf0-262">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-263">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="19bf0-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="19bf0-264">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="19bf0-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="19bf0-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="19bf0-266">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-267">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="19bf0-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="19bf0-268">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="19bf0-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="19bf0-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="19bf0-270">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="19bf0-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="19bf0-271">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="19bf0-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="19bf0-272">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="19bf0-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="19bf0-273">可擴展訊息和目前狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="19bf0-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19bf0-274">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="19bf0-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="19bf0-275">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="19bf0-276">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="19bf0-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="19bf0-277">批註</span><span class="sxs-lookup"><span data-stu-id="19bf0-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="19bf0-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="19bf0-279">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-279">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-280">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-281">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="19bf0-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="19bf0-282">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="19bf0-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19bf0-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="19bf0-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="19bf0-284">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="19bf0-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="19bf0-285">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-285">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-286">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="19bf0-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="19bf0-287">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="19bf0-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19bf0-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="19bf0-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="19bf0-289">每</span><span class="sxs-lookup"><span data-stu-id="19bf0-289">Any</span></span></p></td>
<td><p><span data-ttu-id="19bf0-290">每個內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="19bf0-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="19bf0-291">從前端伺服器或前端池的 XMPP 閘道到 Edge 伺服器內部 IP 位址或每個邊緣池成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="19bf0-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

