---
title: 埠摘要-含公用 IP 位址的單一合併 edge
description: 埠摘要-含公用 IP 位址的單一合併 edge。
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
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566399"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="0d2bd-103">Lync Server 2013 中的埠摘要-含公用 IP 位址的單一合併 edge</span><span class="sxs-lookup"><span data-stu-id="0d2bd-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d2bd-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="0d2bd-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="0d2bd-105">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="0d2bd-106">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="0d2bd-107">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="0d2bd-108">在 [Lync server 2013 的反向 Proxy 案例](lync-server-2013-scenarios-for-reverse-proxy.md) 中，以及在 [ [lync server 2013] 區段中規劃 SIP、XMPP 同盟和公用立即訊息](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 的情況中，均會找到反向 proxy 和同盟的規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="0d2bd-109">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="0d2bd-110">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="0d2bd-111">**具有公用 IP 位址之單一合併 edge 的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="0d2bd-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="0d2bd-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="0d2bd-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="0d2bd-113">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="0d2bd-113">Port and Protocol Details</span></span>

<span data-ttu-id="0d2bd-114">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="0d2bd-p103">若要啟用任何 Edge Service 的遠端存取，則必須允許 SIP 流量雙向流動，如輸入/輸出 Edge 流量圖中所說明。換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="0d2bd-117">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d2bd-118">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0d2bd-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0d2bd-119">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-119">Source IP address</span></span></th>
<th><span data-ttu-id="0d2bd-120">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-120">Destination IP address</span></span></th>
<th><span data-ttu-id="0d2bd-121">注意事項</span><span class="sxs-lookup"><span data-stu-id="0d2bd-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="0d2bd-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-123">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-123">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-124">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-125">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-126">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="0d2bd-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-127">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-128">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-128">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-129">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="0d2bd-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-130">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="0d2bd-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-131">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-132">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-132">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-133">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="0d2bd-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-134">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="0d2bd-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-135">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-136">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-136">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-137">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="0d2bd-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-138">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-139">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-139">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-140">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-141">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-142">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-143">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-143">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-144">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-145">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-146">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-147">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-148">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-148">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-149">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-150">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-151">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-151">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-152">Edge Server Web 會議 Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-153">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="0d2bd-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-154">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0d2bd-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-155">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-156">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-156">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-157">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-158">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0d2bd-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-159">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-160">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-160">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-161">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="0d2bd-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-162">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0d2bd-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-163">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-163">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-164">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-165">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-166">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0d2bd-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-167">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-167">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-168">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-169">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-170">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0d2bd-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-171">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-172">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-172">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-173">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="0d2bd-174">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-175">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0d2bd-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-176">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-176">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-177">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-178">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="0d2bd-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-179">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-180">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-180">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-181">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-182">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="0d2bd-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-183">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-184">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-185">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-185">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-186">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="0d2bd-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="0d2bd-187">具有公用 IP 位址之單一合併的 Edge，其防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d2bd-188">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0d2bd-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0d2bd-189">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-189">Source IP address</span></span></th>
<th><span data-ttu-id="0d2bd-190">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-190">Destination IP address</span></span></th>
<th><span data-ttu-id="0d2bd-191">註解</span><span class="sxs-lookup"><span data-stu-id="0d2bd-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="0d2bd-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-193">任何 (都可以定義為 Standard Edition server IP、Standard Edition server IP 位址，或執行 XMPP 閘道服務的集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-194">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-195">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-197">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-198">Edge Server IP 或容納內部介面的集區</span><span class="sxs-lookup"><span data-stu-id="0d2bd-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-199"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-201">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-202">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區位址) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-203">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="0d2bd-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-205">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-206">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-207">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="0d2bd-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-209">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-210">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-211">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="0d2bd-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0d2bd-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-213">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-213">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-214">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-215">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="0d2bd-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-217">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-217">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-218">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-219">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="0d2bd-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-221">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="0d2bd-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-222">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-223">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="0d2bd-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="0d2bd-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-225">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-225">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-226">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-227">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="0d2bd-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="0d2bd-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-229">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-229">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-230">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-231">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="0d2bd-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="0d2bd-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-233">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-233">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-234">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="0d2bd-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-235">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="0d2bd-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="0d2bd-236">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="0d2bd-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d2bd-237">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0d2bd-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0d2bd-238">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-238">Source IP address</span></span></th>
<th><span data-ttu-id="0d2bd-239">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-239">Destination IP address</span></span></th>
<th><span data-ttu-id="0d2bd-240">注意事項</span><span class="sxs-lookup"><span data-stu-id="0d2bd-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-241">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-242">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-243">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-243">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-244">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="0d2bd-245">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d2bd-246">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0d2bd-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0d2bd-247">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-247">Source IP address</span></span></th>
<th><span data-ttu-id="0d2bd-248">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="0d2bd-248">Destination IP address</span></span></th>
<th><span data-ttu-id="0d2bd-249">注意事項</span><span class="sxs-lookup"><span data-stu-id="0d2bd-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-250">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-251">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="0d2bd-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-252">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-253">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-254">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="0d2bd-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-255">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-256">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="0d2bd-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-257">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="0d2bd-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-258">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="0d2bd-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-259">用戶端</span><span class="sxs-lookup"><span data-stu-id="0d2bd-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-260">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-261">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-262">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="0d2bd-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-263">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-264">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0d2bd-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-265">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="0d2bd-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-266">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0d2bd-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-267">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-268">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0d2bd-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-269">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="0d2bd-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-270">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="0d2bd-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-271">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="0d2bd-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-272">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="0d2bd-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-273">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="0d2bd-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="0d2bd-274">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="0d2bd-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d2bd-275">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="0d2bd-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="0d2bd-276">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="0d2bd-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="0d2bd-277">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="0d2bd-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="0d2bd-278">註解</span><span class="sxs-lookup"><span data-stu-id="0d2bd-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="0d2bd-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-280">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-280">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-281">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="0d2bd-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-282">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="0d2bd-283">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="0d2bd-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d2bd-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="0d2bd-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-285">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="0d2bd-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-286">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-286">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-287">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="0d2bd-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="0d2bd-288">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="0d2bd-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d2bd-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="0d2bd-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-290">任何</span><span class="sxs-lookup"><span data-stu-id="0d2bd-290">Any</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-291">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="0d2bd-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="0d2bd-292">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="0d2bd-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

