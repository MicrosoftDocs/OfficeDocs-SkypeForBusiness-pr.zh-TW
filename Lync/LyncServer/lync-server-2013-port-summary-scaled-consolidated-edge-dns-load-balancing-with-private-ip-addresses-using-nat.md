---
title: Lync Server 2013：埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）
description: Lync Server 2013：埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）。
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563939"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="e9285-103">在 Lync Server 2013 中，埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="e9285-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9285-104">_**主題上次修改日期：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="e9285-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="e9285-105">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="e9285-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="e9285-106">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="e9285-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="e9285-107">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="e9285-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="e9285-108">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="e9285-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="e9285-109">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="e9285-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="e9285-110">**使用 NAT 調整式合併 edge 的企業周邊網路與私人 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="e9285-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="e9285-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="e9285-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="e9285-112">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="e9285-112">Port and Protocol Details</span></span>

<span data-ttu-id="e9285-113">建議您只開啟支援您提供外部存取之功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="e9285-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="e9285-114">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="e9285-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="e9285-115">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="e9285-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="e9285-116">調整式合併 Edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="e9285-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9285-117">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="e9285-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e9285-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-118">Source IP address</span></span></th>
<th><span data-ttu-id="e9285-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-119">Destination IP address</span></span></th>
<th><span data-ttu-id="e9285-120">注意事項</span><span class="sxs-lookup"><span data-stu-id="e9285-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9285-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e9285-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e9285-122">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-122">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-123">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e9285-124">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="e9285-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e9285-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e9285-126">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="e9285-127">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-127">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-128">XMPP Proxy 服務會將流量傳送至已定義 XMPP 同盟中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="e9285-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-129">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="e9285-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="e9285-130">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-131">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-131">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-132">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="e9285-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-133">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="e9285-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="e9285-134">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-135">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-135">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-136">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="e9285-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-137">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="e9285-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="e9285-138">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-139">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-139">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-140">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="e9285-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-141">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-142">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-142">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-143">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-144">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="e9285-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-145">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-146">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-146">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-147">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-148">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e9285-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-149">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-150">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-151">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-151">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-152">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e9285-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-153">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-154">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-154">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-155">Edge Server Web 會議 Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-156">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="e9285-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-157">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e9285-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e9285-158">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-159">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-159">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-160">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="e9285-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-161">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e9285-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e9285-162">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-163">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-163">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-164">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="e9285-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-165">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e9285-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e9285-166">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-166">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-167">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-168">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="e9285-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-169">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e9285-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e9285-170">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-170">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-171">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-172">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="e9285-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e9285-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e9285-174">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-175">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-175">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-176">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="e9285-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="e9285-177">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="e9285-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-178">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e9285-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e9285-179">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-179">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-180">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-181">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="e9285-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-182">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-183">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-183">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-184">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-185">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="e9285-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-186">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-187">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-188">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-188">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-189">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="e9285-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="e9285-190">調整式合併 Edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）的防火牆摘要： Internal Interface – Node 1 and Node 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="e9285-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9285-191">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="e9285-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e9285-192">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-192">Source IP address</span></span></th>
<th><span data-ttu-id="e9285-193">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-193">Destination IP address</span></span></th>
<th><span data-ttu-id="e9285-194">註解</span><span class="sxs-lookup"><span data-stu-id="e9285-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9285-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e9285-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e9285-196">任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="e9285-197">Edge Server 內部介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e9285-198">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="e9285-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-200">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e9285-201">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-202"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="e9285-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-204">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-205">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="e9285-206">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="e9285-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="e9285-208">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="e9285-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="e9285-209">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-210">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="e9285-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="e9285-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="e9285-212">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="e9285-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="e9285-213">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-214">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="e9285-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e9285-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e9285-216">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-216">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-217">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-218">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="e9285-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-220">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-220">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-221">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-222">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="e9285-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="e9285-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="e9285-224">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="e9285-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="e9285-225">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-226">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="e9285-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="e9285-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="e9285-228">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-228">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-229">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-230">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="e9285-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="e9285-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="e9285-232">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-232">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-233">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-234">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="e9285-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="e9285-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="e9285-236">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-236">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-237">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="e9285-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="e9285-238">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="e9285-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="e9285-239">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="e9285-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9285-240">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="e9285-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e9285-241">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-241">Source IP address</span></span></th>
<th><span data-ttu-id="e9285-242">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-242">Destination IP address</span></span></th>
<th><span data-ttu-id="e9285-243">注意事項</span><span class="sxs-lookup"><span data-stu-id="e9285-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9285-244">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-245">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="e9285-246">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-246">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-247">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e9285-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="e9285-248">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="e9285-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9285-249">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="e9285-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e9285-250">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-250">Source IP address</span></span></th>
<th><span data-ttu-id="e9285-251">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="e9285-251">Destination IP address</span></span></th>
<th><span data-ttu-id="e9285-252">注意事項</span><span class="sxs-lookup"><span data-stu-id="e9285-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9285-253">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-254">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="e9285-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e9285-255">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-256">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e9285-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-257">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="e9285-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="e9285-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-259">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="e9285-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="e9285-260">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="e9285-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-261">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="e9285-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="e9285-262">用戶端</span><span class="sxs-lookup"><span data-stu-id="e9285-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="e9285-263">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-264">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="e9285-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-265">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="e9285-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="e9285-266">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-267">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e9285-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e9285-268">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="e9285-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-269">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e9285-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e9285-270">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-271">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e9285-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e9285-272">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="e9285-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-273">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="e9285-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="e9285-274">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="e9285-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="e9285-275">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="e9285-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="e9285-276">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="e9285-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="e9285-277">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="e9285-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9285-278">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="e9285-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="e9285-279">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="e9285-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="e9285-280">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="e9285-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="e9285-281">註解</span><span class="sxs-lookup"><span data-stu-id="e9285-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9285-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e9285-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e9285-283">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-283">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-284">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="e9285-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e9285-285">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="e9285-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e9285-286">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="e9285-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9285-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="e9285-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="e9285-288">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="e9285-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="e9285-289">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-289">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-290">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="e9285-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="e9285-291">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="e9285-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9285-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="e9285-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="e9285-293">任何</span><span class="sxs-lookup"><span data-stu-id="e9285-293">Any</span></span></p></td>
<td><p><span data-ttu-id="e9285-294">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="e9285-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="e9285-295">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="e9285-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

