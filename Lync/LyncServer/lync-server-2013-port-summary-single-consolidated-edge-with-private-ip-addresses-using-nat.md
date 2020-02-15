---
title: 連接埠摘要-單一合併式 edge 具有使用 NAT 的私人 IP 位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 025e472da32afc9d865557c29836c66c0c1f5b18
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="5e8e4-102">連接埠摘要-單一合併式 edge 與 Lync Server 2013 中使用 NAT 的私人 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e8e4-103">_**上次修改主題：** 2013年-04-03_</span><span class="sxs-lookup"><span data-stu-id="5e8e4-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="5e8e4-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="5e8e4-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="5e8e4-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="5e8e4-107">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="5e8e4-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="5e8e4-109">**周邊網路之單一合併 Edge Server 與私人 IP 位址使用 NAT**</span><span class="sxs-lookup"><span data-stu-id="5e8e4-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="5e8e4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="5e8e4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="5e8e4-111">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="5e8e4-111">Port and Protocol Details</span></span>

<span data-ttu-id="5e8e4-112">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="5e8e4-113">適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="5e8e4-114">另一種方式，SIP 通訊所述，並從 Access Edge service 是否涉及立即訊息 (IM)、 目前狀態、 web 會議、 音訊/視訊 (A / V)，及同盟 >。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="5e8e4-115">具有使用 NAT 透過私人 IP 位址的單一合併 Edge 的防火牆摘要： 外部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e8e4-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5e8e4-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5e8e4-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-117">Source IP address</span></span></th>
<th><span data-ttu-id="5e8e4-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-118">Destination IP address</span></span></th>
<th><span data-ttu-id="5e8e4-119">附註</span><span class="sxs-lookup"><span data-stu-id="5e8e4-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5e8e4-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-121">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-121">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-122">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="5e8e4-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="5e8e4-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-125">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-126">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-126">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-127">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="5e8e4-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="5e8e4-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-130">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-130">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-131">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="5e8e4-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="5e8e4-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-134">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-134">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-135">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="5e8e4-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-136">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-137">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-137">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-138">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-139">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="5e8e4-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-140">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-141">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-141">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-143">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-144">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-145">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-146">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-146">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-148">Web 會議 /PSOM (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-149">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-149">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-150">Edge Server Web Conferencing Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-151">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="5e8e4-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="5e8e4-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-153">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-154">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-154">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-155">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="5e8e4-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-157">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-158">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-158">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-159">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="5e8e4-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-161">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-161">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-162">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-163">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="5e8e4-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="5e8e4-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-165">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-165">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-166">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-167">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="5e8e4-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-168">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5e8e4-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-169">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-170">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-170">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-171">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="5e8e4-172">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-173">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5e8e4-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-174">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-174">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-175">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-176">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="5e8e4-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-177">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-178">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-178">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-179">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-180">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="5e8e4-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-181">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-182">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-183">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-183">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="5e8e4-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="5e8e4-185">合併邊緣搭配使用 NAT 透過私人 IP 位址之單一的防火牆摘要： 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e8e4-186">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5e8e4-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5e8e4-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-187">Source IP address</span></span></th>
<th><span data-ttu-id="5e8e4-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-188">Destination IP address</span></span></th>
<th><span data-ttu-id="5e8e4-189">註解</span><span class="sxs-lookup"><span data-stu-id="5e8e4-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="5e8e4-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-191">任何 （可定義為 Standard Edition server IP、 Standard Edition server IP 位址或執行 XMPP 閘道服務的集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-193">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="5e8e4-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-195">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-197">輸出 SIP 流量 （來自 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址) 至 Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-199">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-200">任何 （可定義為 Director，Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-201">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區的 IP 位址、 前端伺服器或前端集區 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="5e8e4-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="5e8e4-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-203">任何 （可定義為前端伺服器 IP 位址或在前端集區中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-204">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-205">從前端伺服器或每個前端伺服器集區中, Edge Server 內部介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="5e8e4-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="5e8e4-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-207">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-209">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="5e8e4-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5e8e4-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-211">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-211">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-213">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="5e8e4-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-215">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-215">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-217">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="5e8e4-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-219">任何 （可定義為前端伺服器 IP 位址或主控的中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="5e8e4-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-221">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="5e8e4-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="5e8e4-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-223">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-223">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-225">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="5e8e4-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="5e8e4-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-227">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-227">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-229">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="5e8e4-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="5e8e4-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-231">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-231">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="5e8e4-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-233">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="5e8e4-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="5e8e4-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="5e8e4-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e8e4-235">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5e8e4-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5e8e4-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-236">Source IP address</span></span></th>
<th><span data-ttu-id="5e8e4-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-237">Destination IP address</span></span></th>
<th><span data-ttu-id="5e8e4-238">附註</span><span class="sxs-lookup"><span data-stu-id="5e8e4-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-239">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-240">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-241">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-241">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-242">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="5e8e4-243">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e8e4-244">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5e8e4-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5e8e4-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-245">Source IP address</span></span></th>
<th><span data-ttu-id="5e8e4-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-246">Destination IP address</span></span></th>
<th><span data-ttu-id="5e8e4-247">附註</span><span class="sxs-lookup"><span data-stu-id="5e8e4-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-248">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-249">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="5e8e4-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-251">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-252">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="5e8e4-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-254">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="5e8e4-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="5e8e4-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-256">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="5e8e4-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-257">用戶端</span><span class="sxs-lookup"><span data-stu-id="5e8e4-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-259">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="5e8e4-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="5e8e4-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-261">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-262">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="5e8e4-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-263">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="5e8e4-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-264">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5e8e4-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-265">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="5e8e4-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-267">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="5e8e4-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-268">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="5e8e4-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-269">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="5e8e4-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-270">Edge Server A / V Edge service</span><span class="sxs-lookup"><span data-stu-id="5e8e4-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="5e8e4-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="5e8e4-272">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="5e8e4-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e8e4-273">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="5e8e4-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="5e8e4-274">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="5e8e4-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="5e8e4-275">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="5e8e4-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="5e8e4-276">註解</span><span class="sxs-lookup"><span data-stu-id="5e8e4-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5e8e4-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-278">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-278">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-279">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-280">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5e8e4-281">允許從同盟 XMPP 協力廠商通訊的 Edge Server XMPP proxy</span><span class="sxs-lookup"><span data-stu-id="5e8e4-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e8e4-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="5e8e4-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-283">Edge Server Access Edge service 介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-284">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-284">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-285">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="5e8e4-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="5e8e4-286">可從 Edge Server XMPP proxy 的通訊，讓同盟 XMPP 協力廠商</span><span class="sxs-lookup"><span data-stu-id="5e8e4-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e8e4-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="5e8e4-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-288">任何</span><span class="sxs-lookup"><span data-stu-id="5e8e4-288">Any</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-289">每個內部的 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="5e8e4-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="5e8e4-290">內部 XMPP 流量從前端伺服器或前端集區上的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址</span><span class="sxs-lookup"><span data-stu-id="5e8e4-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

