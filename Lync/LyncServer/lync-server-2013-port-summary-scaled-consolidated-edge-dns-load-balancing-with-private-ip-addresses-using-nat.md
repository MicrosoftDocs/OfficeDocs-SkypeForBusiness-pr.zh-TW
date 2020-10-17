---
title: Lync Server 2013：埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）
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
ms.openlocfilehash: ff1cb9d559d3d6824882a87aaa4d45ad7254c276
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534140"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="7544b-102">在 Lync Server 2013 中，埠摘要-調整式合併 edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="7544b-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7544b-103">_**主題上次修改日期：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="7544b-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="7544b-104">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="7544b-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="7544b-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="7544b-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="7544b-106">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="7544b-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="7544b-107">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="7544b-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="7544b-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="7544b-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="7544b-109">**使用 NAT 調整式合併 edge 的企業周邊網路與私人 IP 位址**</span><span class="sxs-lookup"><span data-stu-id="7544b-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="7544b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="7544b-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="7544b-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="7544b-111">Port and Protocol Details</span></span>

<span data-ttu-id="7544b-112">建議您只開啟支援您提供外部存取之功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="7544b-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="7544b-113">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="7544b-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="7544b-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="7544b-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="7544b-115">調整式合併 Edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="7544b-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7544b-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7544b-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7544b-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-117">Source IP address</span></span></th>
<th><span data-ttu-id="7544b-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-118">Destination IP address</span></span></th>
<th><span data-ttu-id="7544b-119">注意事項</span><span class="sxs-lookup"><span data-stu-id="7544b-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7544b-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7544b-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7544b-121">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-121">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-122">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7544b-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="7544b-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7544b-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7544b-125">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7544b-126">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-127">XMPP Proxy 服務會將流量傳送至已定義 XMPP 同盟中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="7544b-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-128">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="7544b-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="7544b-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-130">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-130">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-131">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="7544b-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-132">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="7544b-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="7544b-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-134">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-135">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="7544b-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-136">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="7544b-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="7544b-137">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-138">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-138">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-139">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="7544b-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-140">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-141">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-143">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="7544b-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-144">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-145">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-145">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-146">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7544b-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-148">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-149">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-150">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-150">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-151">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7544b-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-152">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-153">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-153">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-154">Edge Server Web 會議 Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-155">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="7544b-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7544b-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7544b-157">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-158">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-158">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-159">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="7544b-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7544b-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7544b-161">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-162">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-162">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-163">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="7544b-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7544b-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7544b-165">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-165">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-166">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-167">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="7544b-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7544b-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7544b-169">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-169">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-170">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-171">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="7544b-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7544b-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7544b-173">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-174">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-174">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-175">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="7544b-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="7544b-176">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="7544b-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7544b-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7544b-178">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-178">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-179">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-180">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7544b-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-182">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-182">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-183">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7544b-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-186">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-187">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-187">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-188">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7544b-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="7544b-189">調整式合併 Edge （使用 NAT 透過私人 IP 位址進行 DNS 負載平衡）的防火牆摘要： Internal Interface – Node 1 and Node 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="7544b-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7544b-190">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7544b-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7544b-191">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-191">Source IP address</span></span></th>
<th><span data-ttu-id="7544b-192">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-192">Destination IP address</span></span></th>
<th><span data-ttu-id="7544b-193">註解</span><span class="sxs-lookup"><span data-stu-id="7544b-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7544b-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7544b-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7544b-195">任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="7544b-196">Edge Server 內部介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7544b-197">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="7544b-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-199">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7544b-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-201"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="7544b-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-203">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-204">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="7544b-205">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="7544b-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="7544b-207">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7544b-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="7544b-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-209">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="7544b-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="7544b-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="7544b-211">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="7544b-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="7544b-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-213">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="7544b-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7544b-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7544b-215">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-215">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-217">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="7544b-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-219">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-219">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-221">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="7544b-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="7544b-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="7544b-223">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="7544b-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="7544b-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-225">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="7544b-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="7544b-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="7544b-227">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-227">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-229">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7544b-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="7544b-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="7544b-231">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-231">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-233">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7544b-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="7544b-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="7544b-235">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-235">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-236">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7544b-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7544b-237">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7544b-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="7544b-238">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="7544b-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7544b-239">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7544b-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7544b-240">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-240">Source IP address</span></span></th>
<th><span data-ttu-id="7544b-241">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-241">Destination IP address</span></span></th>
<th><span data-ttu-id="7544b-242">注意事項</span><span class="sxs-lookup"><span data-stu-id="7544b-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7544b-243">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-244">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7544b-245">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-245">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-246">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7544b-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="7544b-247">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="7544b-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7544b-248">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7544b-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7544b-249">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-249">Source IP address</span></span></th>
<th><span data-ttu-id="7544b-250">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7544b-250">Destination IP address</span></span></th>
<th><span data-ttu-id="7544b-251">注意事項</span><span class="sxs-lookup"><span data-stu-id="7544b-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7544b-252">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-253">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="7544b-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7544b-254">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7544b-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-256">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7544b-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7544b-257">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-258">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="7544b-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="7544b-259">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7544b-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-260">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="7544b-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7544b-261">用戶端</span><span class="sxs-lookup"><span data-stu-id="7544b-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="7544b-262">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-263">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="7544b-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7544b-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7544b-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="7544b-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7544b-267">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="7544b-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7544b-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7544b-269">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-270">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="7544b-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7544b-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="7544b-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7544b-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7544b-273">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="7544b-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="7544b-274">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="7544b-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="7544b-275">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="7544b-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="7544b-276">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="7544b-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7544b-277">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7544b-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7544b-278">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="7544b-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="7544b-279">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="7544b-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="7544b-280">註解</span><span class="sxs-lookup"><span data-stu-id="7544b-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7544b-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7544b-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7544b-282">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-282">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-283">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="7544b-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7544b-284">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="7544b-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7544b-285">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="7544b-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7544b-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7544b-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7544b-287">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="7544b-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="7544b-288">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-288">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-289">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="7544b-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="7544b-290">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="7544b-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7544b-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7544b-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7544b-292">任何</span><span class="sxs-lookup"><span data-stu-id="7544b-292">Any</span></span></p></td>
<td><p><span data-ttu-id="7544b-293">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="7544b-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="7544b-294">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="7544b-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

