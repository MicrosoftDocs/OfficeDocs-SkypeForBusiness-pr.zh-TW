---
title: Lync Server 2013： 連接埠摘要-調整式合併 edge、 DNS 負載平衡與公用 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a2bbae2168362e8591b4dcdb765ae0d4cca85b4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="cf6db-102">連接埠摘要-調整式合併 edge、 DNS 負載平衡與 Lync Server 2013 中的公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf6db-103">_**上次修改主題：** 2013年-04-03_</span><span class="sxs-lookup"><span data-stu-id="cf6db-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="cf6db-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="cf6db-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="cf6db-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="cf6db-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="cf6db-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="cf6db-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="cf6db-107">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="cf6db-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="cf6db-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="cf6db-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="cf6db-109">**調整式合併 Edge，具有公用 IP 位址的 DNS 負載平衡的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="cf6db-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="cf6db-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="cf6db-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="cf6db-111">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="cf6db-111">Port and Protocol Details</span></span>

<span data-ttu-id="cf6db-112">建議您開啟支援所提供給外部存取的功能所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="cf6db-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="cf6db-113">適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="cf6db-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="cf6db-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="cf6db-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="cf6db-115">調整式合併 Edge，使用公用 IP 位址 DNS 負載平衡的防火牆摘要： 外部介面 – 節點 1 與節點 2 (Example)</span><span class="sxs-lookup"><span data-stu-id="cf6db-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6db-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="cf6db-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf6db-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-117">Source IP address</span></span></th>
<th><span data-ttu-id="cf6db-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-118">Destination IP address</span></span></th>
<th><span data-ttu-id="cf6db-119">附註</span><span class="sxs-lookup"><span data-stu-id="cf6db-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf6db-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf6db-121">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-121">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-122">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="cf6db-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="cf6db-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="cf6db-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="cf6db-125">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-126">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-126">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-127">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="cf6db-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="cf6db-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="cf6db-129">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-130">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-130">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-131">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="cf6db-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="cf6db-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="cf6db-133">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-134">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-134">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-135">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="cf6db-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-136">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-137">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-137">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-138">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-139">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="cf6db-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-140">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-141">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-141">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-142">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-143">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-144">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-145">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-146">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-146">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-148">Web 會議/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-149">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-149">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-150">Edge Server Web Conferencing Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-151">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="cf6db-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf6db-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf6db-153">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-154">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-154">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-155">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="cf6db-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf6db-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf6db-157">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-158">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-158">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-159">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="cf6db-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf6db-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf6db-161">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-161">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-162">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-163">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="cf6db-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf6db-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf6db-165">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-165">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-166">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-167">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="cf6db-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-168">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf6db-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf6db-169">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-170">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-170">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-171">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="cf6db-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="cf6db-172">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="cf6db-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-173">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf6db-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf6db-174">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-174">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-175">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-176">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="cf6db-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-177">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-178">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-178">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-179">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-180">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="cf6db-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-181">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-182">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-183">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-183">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="cf6db-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="cf6db-185">調整式合併 Edge，使用公用 IP 位址 DNS 負載平衡的防火牆摘要： 內部介面 – 節點 1 與節點 2 (Example)</span><span class="sxs-lookup"><span data-stu-id="cf6db-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6db-186">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="cf6db-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf6db-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-187">Source IP address</span></span></th>
<th><span data-ttu-id="cf6db-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-188">Destination IP address</span></span></th>
<th><span data-ttu-id="cf6db-189">註解</span><span class="sxs-lookup"><span data-stu-id="cf6db-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf6db-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf6db-191">任何 （可定義為前端伺服器位址或執行 XMPP 閘道服務的前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="cf6db-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-193">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="cf6db-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-195">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="cf6db-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-197">輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-199">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-200">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="cf6db-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-201">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="cf6db-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="cf6db-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="cf6db-203">任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="cf6db-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-204">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-205">從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="cf6db-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="cf6db-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="cf6db-207">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="cf6db-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-209">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="cf6db-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf6db-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf6db-211">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-211">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-213">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="cf6db-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-215">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-215">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-217">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="cf6db-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="cf6db-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-219">任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="cf6db-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="cf6db-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-221">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="cf6db-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="cf6db-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="cf6db-223">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-223">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-225">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="cf6db-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="cf6db-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="cf6db-227">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-227">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-229">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="cf6db-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="cf6db-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="cf6db-231">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-231">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="cf6db-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="cf6db-233">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="cf6db-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="cf6db-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="cf6db-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6db-235">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="cf6db-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf6db-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-236">Source IP address</span></span></th>
<th><span data-ttu-id="cf6db-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-237">Destination IP address</span></span></th>
<th><span data-ttu-id="cf6db-238">附註</span><span class="sxs-lookup"><span data-stu-id="cf6db-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-239">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-240">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-241">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-241">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-242">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="cf6db-243">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6db-244">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="cf6db-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf6db-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-245">Source IP address</span></span></th>
<th><span data-ttu-id="cf6db-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-246">Destination IP address</span></span></th>
<th><span data-ttu-id="cf6db-247">附註</span><span class="sxs-lookup"><span data-stu-id="cf6db-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-248">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-249">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="cf6db-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf6db-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-251">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-252">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="cf6db-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="cf6db-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-254">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="cf6db-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="cf6db-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="cf6db-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-256">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="cf6db-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="cf6db-257">用戶端</span><span class="sxs-lookup"><span data-stu-id="cf6db-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="cf6db-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-259">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="cf6db-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="cf6db-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="cf6db-261">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-262">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="cf6db-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf6db-263">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="cf6db-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-264">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf6db-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf6db-265">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="cf6db-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf6db-267">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="cf6db-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-268">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="cf6db-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="cf6db-269">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="cf6db-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="cf6db-270">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="cf6db-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="cf6db-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="cf6db-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="cf6db-272">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="cf6db-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cf6db-273">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="cf6db-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="cf6db-274">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="cf6db-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="cf6db-275">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="cf6db-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="cf6db-276">註解</span><span class="sxs-lookup"><span data-stu-id="cf6db-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf6db-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf6db-278">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-278">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-279">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-280">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="cf6db-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf6db-281">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="cf6db-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cf6db-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="cf6db-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="cf6db-283">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="cf6db-284">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-284">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-285">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="cf6db-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="cf6db-286">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="cf6db-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cf6db-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="cf6db-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="cf6db-288">任何</span><span class="sxs-lookup"><span data-stu-id="cf6db-288">Any</span></span></p></td>
<td><p><span data-ttu-id="cf6db-289">每個內部的 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="cf6db-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="cf6db-290">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="cf6db-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

