---
title: Lync Server 2013： 連接埠摘要-調整式合併 edge，使用 NAT 的私人 IP 位址使用 DNS 負載平衡
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a90da0679fb48396cf3441464646a27bd2e0caa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9f988-102">連接埠摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9f988-103">_**主題上次修改日期：** 2012年-12-04_</span><span class="sxs-lookup"><span data-stu-id="9f988-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="9f988-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="9f988-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9f988-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="9f988-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9f988-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="9f988-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9f988-107">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="9f988-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9f988-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="9f988-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9f988-109">**企業周邊網路的調整式合併的 edge，具有使用 NAT 的私人 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="9f988-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="9f988-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="9f988-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9f988-111">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="9f988-111">Port and Protocol Details</span></span>

<span data-ttu-id="9f988-112">建議您開啟支援所提供給外部存取的功能所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="9f988-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9f988-113">適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="9f988-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="9f988-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="9f988-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="9f988-115">使用 NAT 的調整式合併 Edge，透過私人 IP DNS 負載平衡的防火牆摘要地址： 外部介面 – 節點 1 與節點 2 (Example)</span><span class="sxs-lookup"><span data-stu-id="9f988-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f988-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9f988-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f988-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-117">Source IP address</span></span></th>
<th><span data-ttu-id="9f988-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-118">Destination IP address</span></span></th>
<th><span data-ttu-id="9f988-119">附註</span><span class="sxs-lookup"><span data-stu-id="9f988-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f988-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9f988-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9f988-121">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-122">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9f988-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="9f988-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9f988-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9f988-125">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9f988-126">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-127">XMPP Proxy 服務將流量傳送至已定義之 XMPP 同盟中 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="9f988-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9f988-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9f988-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-130">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-130">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-131">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="9f988-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9f988-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9f988-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-134">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-135">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="9f988-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9f988-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9f988-137">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-138">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-138">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-139">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="9f988-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-140">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-141">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-143">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="9f988-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-144">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-145">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-145">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-146">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9f988-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-148">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-149">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-150">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-150">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-151">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9f988-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-152">Web 會議 /PSOM (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-153">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-153">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-154">Edge Server Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-155">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="9f988-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9f988-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9f988-157">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-158">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-159">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="9f988-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9f988-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9f988-161">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-162">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-162">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-163">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="9f988-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9f988-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9f988-165">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-166">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-167">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9f988-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9f988-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9f988-169">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-169">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-170">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-171">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="9f988-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-172">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9f988-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9f988-173">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-174">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-175">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="9f988-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9f988-176">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="9f988-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-177">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9f988-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9f988-178">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-179">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-180">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="9f988-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-181">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-182">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-182">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-183">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="9f988-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-185">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-186">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-187">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-187">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-188">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="9f988-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="9f988-189">使用 NAT 的調整式合併 Edge，透過私人 IP DNS 負載平衡的防火牆摘要地址： 內部介面 – 節點 1 與節點 2 (Example)</span><span class="sxs-lookup"><span data-stu-id="9f988-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f988-190">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9f988-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f988-191">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-191">Source IP address</span></span></th>
<th><span data-ttu-id="9f988-192">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-192">Destination IP address</span></span></th>
<th><span data-ttu-id="9f988-193">註解</span><span class="sxs-lookup"><span data-stu-id="9f988-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f988-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9f988-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9f988-195">任何 （可定義為前端伺服器位址或執行 XMPP 閘道服務的前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9f988-196">Edge Server 內部介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9f988-197">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="9f988-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-199">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9f988-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-201">輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-203">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-204">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9f988-205">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9f988-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9f988-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9f988-207">任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="9f988-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9f988-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-209">從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="9f988-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9f988-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9f988-211">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="9f988-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9f988-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-213">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="9f988-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9f988-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9f988-215">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-215">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-217">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="9f988-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-219">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-219">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-221">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="9f988-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9f988-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9f988-223">任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="9f988-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9f988-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-225">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="9f988-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9f988-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9f988-227">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-227">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-229">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="9f988-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9f988-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9f988-231">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-231">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-233">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="9f988-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9f988-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9f988-235">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-235">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-236">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="9f988-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9f988-237">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="9f988-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9f988-238">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="9f988-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f988-239">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9f988-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f988-240">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-240">Source IP address</span></span></th>
<th><span data-ttu-id="9f988-241">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-241">Destination IP address</span></span></th>
<th><span data-ttu-id="9f988-242">附註</span><span class="sxs-lookup"><span data-stu-id="9f988-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f988-243">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-244">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9f988-245">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-245">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-246">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9f988-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9f988-247">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="9f988-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f988-248">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9f988-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f988-249">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-249">Source IP address</span></span></th>
<th><span data-ttu-id="9f988-250">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-250">Destination IP address</span></span></th>
<th><span data-ttu-id="9f988-251">附註</span><span class="sxs-lookup"><span data-stu-id="9f988-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f988-252">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-253">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="9f988-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9f988-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9f988-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-256">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9f988-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9f988-257">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-258">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="9f988-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9f988-259">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="9f988-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-260">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="9f988-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9f988-261">用戶端</span><span class="sxs-lookup"><span data-stu-id="9f988-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="9f988-262">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-263">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="9f988-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9f988-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9f988-265">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="9f988-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9f988-267">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="9f988-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-268">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9f988-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9f988-269">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-270">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="9f988-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9f988-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="9f988-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-272">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9f988-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9f988-273">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="9f988-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9f988-274">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="9f988-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9f988-275">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="9f988-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9f988-276">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="9f988-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9f988-277">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="9f988-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9f988-278">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9f988-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="9f988-279">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="9f988-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9f988-280">註解</span><span class="sxs-lookup"><span data-stu-id="9f988-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9f988-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9f988-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9f988-282">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-282">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-283">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9f988-284">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="9f988-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9f988-285">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="9f988-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9f988-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9f988-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9f988-287">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9f988-288">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-288">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-289">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="9f988-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9f988-290">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="9f988-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9f988-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9f988-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9f988-292">任何</span><span class="sxs-lookup"><span data-stu-id="9f988-292">Any</span></span></p></td>
<td><p><span data-ttu-id="9f988-293">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="9f988-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="9f988-294">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="9f988-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

