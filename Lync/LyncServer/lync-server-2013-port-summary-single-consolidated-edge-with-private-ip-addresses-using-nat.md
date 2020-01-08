---
title: 連接埠摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7c908d52577375f9caaab974f059ffda17fb35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977599"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="54715-102">Lync Server 2013 中的連接埠摘要 - 單一合併 Edge (使用 NAT 透過私人 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="54715-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54715-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="54715-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="54715-104">此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。</span><span class="sxs-lookup"><span data-stu-id="54715-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="54715-105">最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。</span><span class="sxs-lookup"><span data-stu-id="54715-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="54715-106">Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="54715-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="54715-107">除了 IPv4，Edge 伺服器現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="54715-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="54715-108">為清楚起見，在案例中只使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="54715-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="54715-109">**使用 NAT 進行專用 IP 定址的單一整合邊緣伺服器的網路週邊**</span><span class="sxs-lookup"><span data-stu-id="54715-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="54715-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="54715-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="54715-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="54715-111">Port and Protocol Details</span></span>

<span data-ttu-id="54715-112">我們建議您只開啟支援您提供外部存取的功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="54715-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="54715-113">若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="54715-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="54715-114">換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="54715-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="54715-115">使用 NAT：外部介面的單一整合邊緣與私人 IP 位址的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="54715-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54715-116">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="54715-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="54715-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-117">Source IP address</span></span></th>
<th><span data-ttu-id="54715-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-118">Destination IP address</span></span></th>
<th><span data-ttu-id="54715-119">筆記</span><span class="sxs-lookup"><span data-stu-id="54715-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54715-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="54715-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="54715-121">每</span><span class="sxs-lookup"><span data-stu-id="54715-121">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-122">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="54715-123">XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="54715-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="54715-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="54715-125">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-126">每</span><span class="sxs-lookup"><span data-stu-id="54715-126">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-127">憑證吊銷/CRL 檢查及檢索</span><span class="sxs-lookup"><span data-stu-id="54715-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="54715-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="54715-129">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-130">每</span><span class="sxs-lookup"><span data-stu-id="54715-130">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-131">TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="54715-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="54715-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="54715-133">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-134">每</span><span class="sxs-lookup"><span data-stu-id="54715-134">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-135">經由 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="54715-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-136">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-137">每</span><span class="sxs-lookup"><span data-stu-id="54715-137">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-138">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-139">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="54715-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-140">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-141">每</span><span class="sxs-lookup"><span data-stu-id="54715-141">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-142">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-143">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="54715-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-145">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-146">每</span><span class="sxs-lookup"><span data-stu-id="54715-146">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-147">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="54715-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-148">網路會議/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-149">每</span><span class="sxs-lookup"><span data-stu-id="54715-149">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-150">Edge 伺服器網路會議 Edge 服務</span><span class="sxs-lookup"><span data-stu-id="54715-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-151">網路會議媒體</span><span class="sxs-lookup"><span data-stu-id="54715-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="54715-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="54715-153">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-154">每</span><span class="sxs-lookup"><span data-stu-id="54715-154">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-155">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</span><span class="sxs-lookup"><span data-stu-id="54715-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="54715-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="54715-157">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-158">每</span><span class="sxs-lookup"><span data-stu-id="54715-158">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-159">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="54715-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="54715-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="54715-161">每</span><span class="sxs-lookup"><span data-stu-id="54715-161">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-162">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-163">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="54715-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="54715-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="54715-165">每</span><span class="sxs-lookup"><span data-stu-id="54715-165">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-166">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-167">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="54715-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="54715-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="54715-169">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-170">每</span><span class="sxs-lookup"><span data-stu-id="54715-170">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-171">3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="54715-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="54715-172">使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</span><span class="sxs-lookup"><span data-stu-id="54715-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="54715-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="54715-174">每</span><span class="sxs-lookup"><span data-stu-id="54715-174">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-175">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-176">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="54715-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-178">每</span><span class="sxs-lookup"><span data-stu-id="54715-178">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-179">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-180">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="54715-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-182">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-183">每</span><span class="sxs-lookup"><span data-stu-id="54715-183">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-184">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="54715-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="54715-185">使用 NAT 的單一合併邊緣的防火牆摘要與私人 IP 位址：內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54715-186">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="54715-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="54715-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-187">Source IP address</span></span></th>
<th><span data-ttu-id="54715-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-188">Destination IP address</span></span></th>
<th><span data-ttu-id="54715-189">批註</span><span class="sxs-lookup"><span data-stu-id="54715-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54715-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="54715-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="54715-191">[任何] （可定義為標準版伺服器 IP、標準版伺服器 IP 位址或執行 XMPP 閘道服務的池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="54715-192">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-193">在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="54715-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-195">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="54715-196">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-197">輸出 SIP 流量（從控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）到邊緣伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-199">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-200">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="54715-201">來自 Edge 伺服器內部介面的入站 SIP 流量（到控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="54715-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="54715-203">Any （可定義為前端伺服器 IP 位址，或前端池中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="54715-204">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-205">從前臺伺服器或每個前端伺服器的網路會議流量（如果在池中）到 Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="54715-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="54715-207">[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="54715-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="54715-208">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-209">使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</span><span class="sxs-lookup"><span data-stu-id="54715-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="54715-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="54715-211">每</span><span class="sxs-lookup"><span data-stu-id="54715-211">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-212">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-213">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="54715-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-215">每</span><span class="sxs-lookup"><span data-stu-id="54715-215">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-216">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-217">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="54715-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="54715-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="54715-219">[任何] （可定義為 [前端伺服器 IP 位址] 或 [擁有中央管理儲存區的池）]</span><span class="sxs-lookup"><span data-stu-id="54715-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="54715-220">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-221">從中央管理儲存體將變更複製到 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="54715-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="54715-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="54715-223">每</span><span class="sxs-lookup"><span data-stu-id="54715-223">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-224">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-225">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="54715-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="54715-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="54715-227">每</span><span class="sxs-lookup"><span data-stu-id="54715-227">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-228">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-229">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="54715-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="54715-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="54715-231">每</span><span class="sxs-lookup"><span data-stu-id="54715-231">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-232">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="54715-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="54715-233">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="54715-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="54715-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="54715-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54715-235">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="54715-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="54715-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-236">Source IP address</span></span></th>
<th><span data-ttu-id="54715-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-237">Destination IP address</span></span></th>
<th><span data-ttu-id="54715-238">筆記</span><span class="sxs-lookup"><span data-stu-id="54715-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54715-239">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-240">存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="54715-241">每</span><span class="sxs-lookup"><span data-stu-id="54715-241">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-242">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="54715-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="54715-243">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="54715-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54715-244">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="54715-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="54715-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-245">Source IP address</span></span></th>
<th><span data-ttu-id="54715-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-246">Destination IP address</span></span></th>
<th><span data-ttu-id="54715-247">筆記</span><span class="sxs-lookup"><span data-stu-id="54715-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54715-248">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-249">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="54715-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="54715-250">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-251">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="54715-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="54715-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="54715-253">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-254">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="54715-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="54715-255">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="54715-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-256">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="54715-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="54715-257">台</span><span class="sxs-lookup"><span data-stu-id="54715-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="54715-258">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-259">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="54715-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="54715-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="54715-261">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-262">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="54715-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="54715-263">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="54715-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="54715-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="54715-265">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-266">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="54715-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="54715-267">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="54715-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="54715-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="54715-269">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="54715-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="54715-270">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="54715-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="54715-271">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="54715-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="54715-272">可擴展訊息和目前狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="54715-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="54715-273">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="54715-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="54715-274">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="54715-275">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="54715-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="54715-276">批註</span><span class="sxs-lookup"><span data-stu-id="54715-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="54715-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="54715-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="54715-278">每</span><span class="sxs-lookup"><span data-stu-id="54715-278">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-279">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="54715-280">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="54715-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="54715-281">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="54715-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="54715-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="54715-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="54715-283">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="54715-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="54715-284">每</span><span class="sxs-lookup"><span data-stu-id="54715-284">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-285">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="54715-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="54715-286">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="54715-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="54715-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="54715-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="54715-288">每</span><span class="sxs-lookup"><span data-stu-id="54715-288">Any</span></span></p></td>
<td><p><span data-ttu-id="54715-289">每個內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="54715-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="54715-290">從前端伺服器或前端池的 XMPP 閘道到 Edge 伺服器內部 IP 位址或每個邊緣池成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="54715-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

