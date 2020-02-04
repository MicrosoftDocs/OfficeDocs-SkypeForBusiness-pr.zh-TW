---
title: Lync Server 2013：連接埠摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)
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
ms.openlocfilehash: f67a12b05d8724d31f8ef83bfa4aa704b41cee13
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="976a2-102">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用公用 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="976a2-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="976a2-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="976a2-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="976a2-104">此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。</span><span class="sxs-lookup"><span data-stu-id="976a2-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="976a2-105">最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。</span><span class="sxs-lookup"><span data-stu-id="976a2-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="976a2-106">Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="976a2-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="976a2-107">除了 IPv4，Edge 伺服器現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="976a2-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="976a2-108">為清楚起見，在案例中只使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="976a2-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="976a2-109">**企業周邊網路可調整整合的邊緣，使用公用 IP 位址進行 DNS 負載平衡**</span><span class="sxs-lookup"><span data-stu-id="976a2-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="976a2-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="976a2-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="976a2-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="976a2-111">Port and Protocol Details</span></span>

<span data-ttu-id="976a2-112">建議您只開啟支援您提供外部存取的功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="976a2-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="976a2-113">若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="976a2-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="976a2-114">換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="976a2-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="976a2-115">針對調整後邊緣的防火牆摘要、使用公用 IP 位址的 DNS 負載平衡：外部介面–節點1和節點2（範例）</span><span class="sxs-lookup"><span data-stu-id="976a2-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="976a2-116">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="976a2-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="976a2-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-117">Source IP address</span></span></th>
<th><span data-ttu-id="976a2-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-118">Destination IP address</span></span></th>
<th><span data-ttu-id="976a2-119">筆記</span><span class="sxs-lookup"><span data-stu-id="976a2-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976a2-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="976a2-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="976a2-121">每</span><span class="sxs-lookup"><span data-stu-id="976a2-121">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-122">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="976a2-123">XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="976a2-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="976a2-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="976a2-125">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-126">每</span><span class="sxs-lookup"><span data-stu-id="976a2-126">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-127">憑證吊銷/CRL 檢查及檢索</span><span class="sxs-lookup"><span data-stu-id="976a2-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="976a2-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="976a2-129">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-130">每</span><span class="sxs-lookup"><span data-stu-id="976a2-130">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-131">TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="976a2-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="976a2-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="976a2-133">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-134">每</span><span class="sxs-lookup"><span data-stu-id="976a2-134">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-135">經由 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="976a2-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-136">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-137">每</span><span class="sxs-lookup"><span data-stu-id="976a2-137">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-138">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-139">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="976a2-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-140">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-141">每</span><span class="sxs-lookup"><span data-stu-id="976a2-141">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-142">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-143">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="976a2-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-145">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-146">每</span><span class="sxs-lookup"><span data-stu-id="976a2-146">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-147">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="976a2-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-148">網路會議/PSOM （TLS） TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-149">每</span><span class="sxs-lookup"><span data-stu-id="976a2-149">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-150">Edge 伺服器網路會議 Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-151">網路會議媒體</span><span class="sxs-lookup"><span data-stu-id="976a2-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="976a2-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="976a2-153">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-154">每</span><span class="sxs-lookup"><span data-stu-id="976a2-154">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-155">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</span><span class="sxs-lookup"><span data-stu-id="976a2-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="976a2-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="976a2-157">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-158">每</span><span class="sxs-lookup"><span data-stu-id="976a2-158">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-159">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="976a2-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="976a2-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="976a2-161">每</span><span class="sxs-lookup"><span data-stu-id="976a2-161">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-162">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-163">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="976a2-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="976a2-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="976a2-165">每</span><span class="sxs-lookup"><span data-stu-id="976a2-165">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-166">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-167">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="976a2-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="976a2-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="976a2-169">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-170">每</span><span class="sxs-lookup"><span data-stu-id="976a2-170">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-171">3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="976a2-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="976a2-172">使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</span><span class="sxs-lookup"><span data-stu-id="976a2-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="976a2-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="976a2-174">每</span><span class="sxs-lookup"><span data-stu-id="976a2-174">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-175">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-176">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="976a2-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-178">每</span><span class="sxs-lookup"><span data-stu-id="976a2-178">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-179">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-180">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="976a2-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-182">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-183">每</span><span class="sxs-lookup"><span data-stu-id="976a2-183">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-184">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="976a2-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="976a2-185">針對調整後邊緣的防火牆摘要、使用公用 IP 位址的 DNS 負載平衡：內部介面–節點1和節點2（範例）</span><span class="sxs-lookup"><span data-stu-id="976a2-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="976a2-186">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="976a2-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="976a2-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-187">Source IP address</span></span></th>
<th><span data-ttu-id="976a2-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-188">Destination IP address</span></span></th>
<th><span data-ttu-id="976a2-189">批註</span><span class="sxs-lookup"><span data-stu-id="976a2-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976a2-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="976a2-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="976a2-191">[任何] （可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="976a2-192">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-193">在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="976a2-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-195">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="976a2-196">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-197">輸出 SIP 流量（從控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）到邊緣伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-199">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-200">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="976a2-201">來自 Edge 伺服器內部介面的入站 SIP 流量（到控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="976a2-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="976a2-203">Any （可定義為前端伺服器 IP 位址，或前端池中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="976a2-204">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-205">從前臺伺服器或每個前端伺服器的網路會議流量（如果在池中）到 Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="976a2-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="976a2-207">[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="976a2-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="976a2-208">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-209">使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</span><span class="sxs-lookup"><span data-stu-id="976a2-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="976a2-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="976a2-211">每</span><span class="sxs-lookup"><span data-stu-id="976a2-211">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-212">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-213">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="976a2-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-215">每</span><span class="sxs-lookup"><span data-stu-id="976a2-215">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-216">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-217">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="976a2-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="976a2-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="976a2-219">[任何] （可定義為 [前端伺服器 IP 位址] 或 [擁有中央管理儲存區的池）]</span><span class="sxs-lookup"><span data-stu-id="976a2-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="976a2-220">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-221">從中央管理儲存體將變更複製到 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="976a2-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="976a2-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="976a2-223">每</span><span class="sxs-lookup"><span data-stu-id="976a2-223">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-224">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-225">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="976a2-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="976a2-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="976a2-227">每</span><span class="sxs-lookup"><span data-stu-id="976a2-227">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-228">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-229">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="976a2-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="976a2-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="976a2-231">每</span><span class="sxs-lookup"><span data-stu-id="976a2-231">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-232">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="976a2-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="976a2-233">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="976a2-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="976a2-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="976a2-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="976a2-235">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="976a2-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="976a2-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-236">Source IP address</span></span></th>
<th><span data-ttu-id="976a2-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-237">Destination IP address</span></span></th>
<th><span data-ttu-id="976a2-238">筆記</span><span class="sxs-lookup"><span data-stu-id="976a2-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976a2-239">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-240">存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-241">每</span><span class="sxs-lookup"><span data-stu-id="976a2-241">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-242">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="976a2-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="976a2-243">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="976a2-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="976a2-244">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="976a2-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="976a2-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-245">Source IP address</span></span></th>
<th><span data-ttu-id="976a2-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-246">Destination IP address</span></span></th>
<th><span data-ttu-id="976a2-247">筆記</span><span class="sxs-lookup"><span data-stu-id="976a2-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976a2-248">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-249">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="976a2-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="976a2-250">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-251">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="976a2-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="976a2-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="976a2-253">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-254">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="976a2-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="976a2-255">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="976a2-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-256">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="976a2-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="976a2-257">台</span><span class="sxs-lookup"><span data-stu-id="976a2-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="976a2-258">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-259">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="976a2-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="976a2-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="976a2-261">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-262">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="976a2-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="976a2-263">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="976a2-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="976a2-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="976a2-265">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-266">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="976a2-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="976a2-267">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="976a2-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="976a2-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="976a2-269">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="976a2-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="976a2-270">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="976a2-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="976a2-271">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="976a2-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="976a2-272">可擴展訊息和目前狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="976a2-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="976a2-273">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="976a2-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="976a2-274">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="976a2-275">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="976a2-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="976a2-276">批註</span><span class="sxs-lookup"><span data-stu-id="976a2-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="976a2-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="976a2-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="976a2-278">每</span><span class="sxs-lookup"><span data-stu-id="976a2-278">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-279">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-280">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="976a2-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="976a2-281">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="976a2-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="976a2-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="976a2-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="976a2-283">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="976a2-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="976a2-284">每</span><span class="sxs-lookup"><span data-stu-id="976a2-284">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-285">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="976a2-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="976a2-286">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="976a2-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="976a2-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="976a2-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="976a2-288">每</span><span class="sxs-lookup"><span data-stu-id="976a2-288">Any</span></span></p></td>
<td><p><span data-ttu-id="976a2-289">每個內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="976a2-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="976a2-290">從前端伺服器或前端池的 XMPP 閘道到 Edge 伺服器內部 IP 位址或每個邊緣池成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="976a2-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

