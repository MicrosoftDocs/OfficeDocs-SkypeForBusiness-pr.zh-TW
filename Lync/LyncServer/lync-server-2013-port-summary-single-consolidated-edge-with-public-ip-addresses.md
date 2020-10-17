---
title: 埠摘要-含公用 IP 位址的單一合併 edge
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
ms.openlocfilehash: 6aa6c3e2ad475cb641a2df50c1dc0016a5ac2fd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534010"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="73465-102">Lync Server 2013 中的埠摘要-含公用 IP 位址的單一合併 edge</span><span class="sxs-lookup"><span data-stu-id="73465-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73465-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="73465-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="73465-104">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="73465-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="73465-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="73465-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="73465-106">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="73465-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="73465-107">在 [Lync server 2013 的反向 Proxy 案例](lync-server-2013-scenarios-for-reverse-proxy.md) 中，以及在 [ [lync server 2013] 區段中規劃 SIP、XMPP 同盟和公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 的情況中，均會找到反向 proxy 和同盟的規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="73465-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="73465-108">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="73465-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="73465-109">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="73465-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="73465-110">**具有公用 IP 位址之單一合併 edge 的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="73465-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="73465-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="73465-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="73465-112">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="73465-112">Port and Protocol Details</span></span>

<span data-ttu-id="73465-113">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="73465-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="73465-p103">若要啟用任何 Edge Service 的遠端存取，則必須允許 SIP 流量雙向流動，如輸入/輸出 Edge 流量圖中所說明。換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="73465-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="73465-116">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="73465-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73465-117">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="73465-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73465-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-118">Source IP address</span></span></th>
<th><span data-ttu-id="73465-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-119">Destination IP address</span></span></th>
<th><span data-ttu-id="73465-120">注意事項</span><span class="sxs-lookup"><span data-stu-id="73465-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73465-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="73465-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="73465-122">任何</span><span class="sxs-lookup"><span data-stu-id="73465-122">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-123">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="73465-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="73465-124">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="73465-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-125">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="73465-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="73465-126">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-127">任何</span><span class="sxs-lookup"><span data-stu-id="73465-127">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-128">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="73465-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-129">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="73465-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="73465-130">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-131">任何</span><span class="sxs-lookup"><span data-stu-id="73465-131">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-132">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="73465-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-133">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="73465-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="73465-134">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-135">任何</span><span class="sxs-lookup"><span data-stu-id="73465-135">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-136">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="73465-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-137">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-138">任何</span><span class="sxs-lookup"><span data-stu-id="73465-138">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-139">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-140">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="73465-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-141">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-142">任何</span><span class="sxs-lookup"><span data-stu-id="73465-142">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-143">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-144">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="73465-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-145">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-146">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-147">任何</span><span class="sxs-lookup"><span data-stu-id="73465-147">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-148">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="73465-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-149">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-150">任何</span><span class="sxs-lookup"><span data-stu-id="73465-150">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-151">Edge Server Web 會議 Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-152">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="73465-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="73465-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73465-154">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-155">任何</span><span class="sxs-lookup"><span data-stu-id="73465-155">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-156">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="73465-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="73465-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73465-158">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-159">任何</span><span class="sxs-lookup"><span data-stu-id="73465-159">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-160">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="73465-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="73465-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73465-162">任何</span><span class="sxs-lookup"><span data-stu-id="73465-162">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-163">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-164">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="73465-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="73465-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73465-166">任何</span><span class="sxs-lookup"><span data-stu-id="73465-166">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-167">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-168">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="73465-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-169">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73465-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73465-170">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-171">任何</span><span class="sxs-lookup"><span data-stu-id="73465-171">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-172">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="73465-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="73465-173">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="73465-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-174">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73465-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73465-175">任何</span><span class="sxs-lookup"><span data-stu-id="73465-175">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-176">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-177">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="73465-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-178">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-179">任何</span><span class="sxs-lookup"><span data-stu-id="73465-179">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-180">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-181">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="73465-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-183">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-184">任何</span><span class="sxs-lookup"><span data-stu-id="73465-184">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-185">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="73465-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="73465-186">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73465-187">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="73465-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73465-188">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-188">Source IP address</span></span></th>
<th><span data-ttu-id="73465-189">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-189">Destination IP address</span></span></th>
<th><span data-ttu-id="73465-190">註解</span><span class="sxs-lookup"><span data-stu-id="73465-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73465-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="73465-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="73465-192">任何 (都可以定義為 Standard Edition server IP、Standard Edition server IP 位址，或執行 XMPP 閘道服務的集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="73465-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="73465-193">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-194">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="73465-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-196">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="73465-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="73465-197">Edge Server IP 或容納內部介面的集區</span><span class="sxs-lookup"><span data-stu-id="73465-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-198"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="73465-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-201">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區位址) </span><span class="sxs-lookup"><span data-stu-id="73465-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="73465-202">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="73465-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="73465-204">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="73465-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="73465-205">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-206">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="73465-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="73465-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="73465-208">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="73465-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="73465-209">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-210">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="73465-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73465-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73465-212">任何</span><span class="sxs-lookup"><span data-stu-id="73465-212">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-213">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-214">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="73465-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-216">任何</span><span class="sxs-lookup"><span data-stu-id="73465-216">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-217">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-218">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="73465-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="73465-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="73465-220">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="73465-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="73465-221">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-222">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="73465-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="73465-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="73465-224">任何</span><span class="sxs-lookup"><span data-stu-id="73465-224">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-225">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-226">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="73465-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="73465-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="73465-228">任何</span><span class="sxs-lookup"><span data-stu-id="73465-228">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-229">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-230">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="73465-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="73465-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="73465-232">任何</span><span class="sxs-lookup"><span data-stu-id="73465-232">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-233">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="73465-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="73465-234">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="73465-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="73465-235">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="73465-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73465-236">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="73465-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73465-237">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-237">Source IP address</span></span></th>
<th><span data-ttu-id="73465-238">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-238">Destination IP address</span></span></th>
<th><span data-ttu-id="73465-239">注意事項</span><span class="sxs-lookup"><span data-stu-id="73465-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73465-240">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-241">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-242">任何</span><span class="sxs-lookup"><span data-stu-id="73465-242">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-243">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="73465-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="73465-244">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="73465-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73465-245">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="73465-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73465-246">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-246">Source IP address</span></span></th>
<th><span data-ttu-id="73465-247">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="73465-247">Destination IP address</span></span></th>
<th><span data-ttu-id="73465-248">注意事項</span><span class="sxs-lookup"><span data-stu-id="73465-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73465-249">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-250">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="73465-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="73465-251">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-252">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="73465-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-253">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="73465-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="73465-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-255">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="73465-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="73465-256">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="73465-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-257">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="73465-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="73465-258">用戶端</span><span class="sxs-lookup"><span data-stu-id="73465-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="73465-259">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-260">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="73465-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="73465-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="73465-262">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-263">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="73465-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="73465-264">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="73465-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-265">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73465-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73465-266">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-267">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="73465-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="73465-268">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="73465-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="73465-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="73465-270">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="73465-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="73465-271">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="73465-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="73465-272">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="73465-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="73465-273">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="73465-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73465-274">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="73465-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="73465-275">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="73465-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="73465-276">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="73465-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="73465-277">註解</span><span class="sxs-lookup"><span data-stu-id="73465-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73465-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="73465-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="73465-279">任何</span><span class="sxs-lookup"><span data-stu-id="73465-279">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-280">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="73465-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-281">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="73465-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="73465-282">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="73465-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73465-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="73465-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="73465-284">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="73465-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="73465-285">任何</span><span class="sxs-lookup"><span data-stu-id="73465-285">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-286">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="73465-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="73465-287">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="73465-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73465-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="73465-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="73465-289">任何</span><span class="sxs-lookup"><span data-stu-id="73465-289">Any</span></span></p></td>
<td><p><span data-ttu-id="73465-290">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="73465-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="73465-291">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="73465-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

