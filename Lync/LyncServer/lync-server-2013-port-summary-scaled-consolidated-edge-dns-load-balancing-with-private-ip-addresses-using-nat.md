---
title: Lync Server 2013：連接埠摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d7e9a142e478674f4be369ace5551b2b628db83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="47c09-102">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (使用 NAT 透過私人 IP 位址進行 DNS 負載平衡)</span><span class="sxs-lookup"><span data-stu-id="47c09-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47c09-103">_**主題上次修改日期：** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="47c09-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="47c09-104">此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。</span><span class="sxs-lookup"><span data-stu-id="47c09-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="47c09-105">最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。</span><span class="sxs-lookup"><span data-stu-id="47c09-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="47c09-106">Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="47c09-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="47c09-107">除了 IPv4，Edge 伺服器現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="47c09-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="47c09-108">為清楚起見，在案例中只使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="47c09-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="47c09-109">**使用 NAT 利用私人 IP 位址調整合並邊緣的企業周邊網路**</span><span class="sxs-lookup"><span data-stu-id="47c09-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="47c09-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="47c09-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="47c09-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="47c09-111">Port and Protocol Details</span></span>

<span data-ttu-id="47c09-112">建議您只開啟支援您提供外部存取的功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="47c09-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="47c09-113">若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="47c09-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="47c09-114">換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="47c09-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="47c09-115">針對調整後邊緣的防火牆摘要、使用 NAT 的私人 IP 位址進行 DNS 負載平衡：外部介面–節點1和節點2（範例）</span><span class="sxs-lookup"><span data-stu-id="47c09-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c09-116">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="47c09-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="47c09-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-117">Source IP address</span></span></th>
<th><span data-ttu-id="47c09-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-118">Destination IP address</span></span></th>
<th><span data-ttu-id="47c09-119">筆記</span><span class="sxs-lookup"><span data-stu-id="47c09-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c09-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="47c09-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="47c09-121">每</span><span class="sxs-lookup"><span data-stu-id="47c09-121">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-122">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="47c09-123">XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="47c09-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="47c09-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="47c09-125">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="47c09-126">每</span><span class="sxs-lookup"><span data-stu-id="47c09-126">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-127">XMPP Proxy service 會傳送流量給已定義 XMPP 聯合體中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="47c09-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="47c09-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="47c09-129">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-130">每</span><span class="sxs-lookup"><span data-stu-id="47c09-130">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-131">憑證吊銷/CRL 檢查及檢索</span><span class="sxs-lookup"><span data-stu-id="47c09-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="47c09-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="47c09-133">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-134">每</span><span class="sxs-lookup"><span data-stu-id="47c09-134">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-135">TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="47c09-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="47c09-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="47c09-137">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-138">每</span><span class="sxs-lookup"><span data-stu-id="47c09-138">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-139">經由 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="47c09-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-140">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-141">每</span><span class="sxs-lookup"><span data-stu-id="47c09-141">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-142">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-143">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="47c09-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-144">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-145">每</span><span class="sxs-lookup"><span data-stu-id="47c09-145">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-146">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-147">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="47c09-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-148">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-149">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-150">每</span><span class="sxs-lookup"><span data-stu-id="47c09-150">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-151">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="47c09-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-152">網路會議/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-153">每</span><span class="sxs-lookup"><span data-stu-id="47c09-153">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-154">Edge 伺服器網路會議 Edge 服務</span><span class="sxs-lookup"><span data-stu-id="47c09-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-155">網路會議媒體</span><span class="sxs-lookup"><span data-stu-id="47c09-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="47c09-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="47c09-157">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-158">每</span><span class="sxs-lookup"><span data-stu-id="47c09-158">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-159">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</span><span class="sxs-lookup"><span data-stu-id="47c09-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="47c09-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="47c09-161">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-162">每</span><span class="sxs-lookup"><span data-stu-id="47c09-162">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-163">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="47c09-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="47c09-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="47c09-165">每</span><span class="sxs-lookup"><span data-stu-id="47c09-165">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-166">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-167">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="47c09-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="47c09-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="47c09-169">每</span><span class="sxs-lookup"><span data-stu-id="47c09-169">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-170">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-171">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="47c09-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-172">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="47c09-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="47c09-173">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-174">每</span><span class="sxs-lookup"><span data-stu-id="47c09-174">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-175">3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="47c09-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="47c09-176">使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</span><span class="sxs-lookup"><span data-stu-id="47c09-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-177">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="47c09-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="47c09-178">每</span><span class="sxs-lookup"><span data-stu-id="47c09-178">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-179">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-180">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="47c09-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-182">每</span><span class="sxs-lookup"><span data-stu-id="47c09-182">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-183">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-184">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="47c09-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-185">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-186">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-187">每</span><span class="sxs-lookup"><span data-stu-id="47c09-187">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-188">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="47c09-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="47c09-189">針對調整後邊緣的防火牆摘要、使用 NAT 將 DNS 負載平衡與私人 IP 位址進行整合：內部介面–節點1和節點2（範例）</span><span class="sxs-lookup"><span data-stu-id="47c09-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c09-190">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="47c09-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="47c09-191">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-191">Source IP address</span></span></th>
<th><span data-ttu-id="47c09-192">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-192">Destination IP address</span></span></th>
<th><span data-ttu-id="47c09-193">批註</span><span class="sxs-lookup"><span data-stu-id="47c09-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c09-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="47c09-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="47c09-195">[任何] （可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="47c09-196">Edge 伺服器內部介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="47c09-197">在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="47c09-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-199">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="47c09-200">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-201">輸出 SIP 流量（從控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）到邊緣伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-203">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-204">[任何] （可以定義為 Director、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="47c09-205">來自 Edge 伺服器內部介面的入站 SIP 流量（到控制器、控制器池 IP 位址、前端伺服器或前端池 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="47c09-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="47c09-207">Any （可定義為前端伺服器 IP 位址，或前端池中的每個前端伺服器 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="47c09-208">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-209">從前臺伺服器或每個前端伺服器的網路會議流量（如果在池中）到 Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="47c09-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="47c09-211">[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="47c09-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="47c09-212">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-213">使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</span><span class="sxs-lookup"><span data-stu-id="47c09-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="47c09-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="47c09-215">每</span><span class="sxs-lookup"><span data-stu-id="47c09-215">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-216">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-217">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="47c09-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-219">每</span><span class="sxs-lookup"><span data-stu-id="47c09-219">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-220">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-221">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="47c09-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="47c09-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="47c09-223">[任何] （可定義為 [前端伺服器 IP 位址] 或 [擁有中央管理儲存區的池）]</span><span class="sxs-lookup"><span data-stu-id="47c09-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="47c09-224">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-225">從中央管理儲存體將變更複製到 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="47c09-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="47c09-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="47c09-227">每</span><span class="sxs-lookup"><span data-stu-id="47c09-227">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-228">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-229">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="47c09-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="47c09-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="47c09-231">每</span><span class="sxs-lookup"><span data-stu-id="47c09-231">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-232">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-233">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="47c09-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="47c09-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="47c09-235">每</span><span class="sxs-lookup"><span data-stu-id="47c09-235">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-236">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="47c09-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="47c09-237">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="47c09-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="47c09-238">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="47c09-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c09-239">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="47c09-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="47c09-240">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-240">Source IP address</span></span></th>
<th><span data-ttu-id="47c09-241">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-241">Destination IP address</span></span></th>
<th><span data-ttu-id="47c09-242">筆記</span><span class="sxs-lookup"><span data-stu-id="47c09-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c09-243">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-244">存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="47c09-245">每</span><span class="sxs-lookup"><span data-stu-id="47c09-245">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-246">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="47c09-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="47c09-247">防火牆摘要–公用立即訊息連線能力</span><span class="sxs-lookup"><span data-stu-id="47c09-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c09-248">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="47c09-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="47c09-249">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-249">Source IP address</span></span></th>
<th><span data-ttu-id="47c09-250">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-250">Destination IP address</span></span></th>
<th><span data-ttu-id="47c09-251">筆記</span><span class="sxs-lookup"><span data-stu-id="47c09-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c09-252">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-253">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="47c09-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="47c09-254">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-255">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="47c09-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-256">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="47c09-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="47c09-257">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-258">公用 IM 連線性合作夥伴</span><span class="sxs-lookup"><span data-stu-id="47c09-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="47c09-259">使用 SIP 進行聯盟及公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="47c09-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-260">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="47c09-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="47c09-261">台</span><span class="sxs-lookup"><span data-stu-id="47c09-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="47c09-262">Edge 伺服器存取邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-263">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="47c09-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="47c09-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="47c09-265">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-266">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="47c09-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="47c09-267">在已設定公用 IM 連線的情況中，使用 Windows Live Messenger 進行 A/V 會話。</span><span class="sxs-lookup"><span data-stu-id="47c09-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="47c09-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="47c09-269">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-270">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="47c09-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="47c09-271">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="47c09-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-272">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="47c09-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="47c09-273">即時 Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="47c09-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="47c09-274">Edge 伺服器 A/V 邊緣服務</span><span class="sxs-lookup"><span data-stu-id="47c09-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="47c09-275">與 Windows Live Messenger 的公用 IM 連線所需</span><span class="sxs-lookup"><span data-stu-id="47c09-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="47c09-276">可擴展訊息和目前狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="47c09-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="47c09-277">通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="47c09-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="47c09-278">來源（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="47c09-279">目的地（IP 位址）</span><span class="sxs-lookup"><span data-stu-id="47c09-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="47c09-280">批註</span><span class="sxs-lookup"><span data-stu-id="47c09-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="47c09-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="47c09-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="47c09-282">每</span><span class="sxs-lookup"><span data-stu-id="47c09-282">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-283">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="47c09-284">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="47c09-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="47c09-285">允許從聯盟 XMPP 合作夥伴與 Edge 伺服器 XMPP proxy 進行通訊</span><span class="sxs-lookup"><span data-stu-id="47c09-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="47c09-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="47c09-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="47c09-287">Edge 伺服器存取邊緣服務介面 IP 位址</span><span class="sxs-lookup"><span data-stu-id="47c09-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="47c09-288">每</span><span class="sxs-lookup"><span data-stu-id="47c09-288">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-289">XMPP 的標準伺服器與伺服器通訊埠。</span><span class="sxs-lookup"><span data-stu-id="47c09-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="47c09-290">允許從 Edge 伺服器 XMPP proxy 到聯盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="47c09-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="47c09-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="47c09-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="47c09-292">每</span><span class="sxs-lookup"><span data-stu-id="47c09-292">Any</span></span></p></td>
<td><p><span data-ttu-id="47c09-293">每個內部邊緣伺服器介面 IP</span><span class="sxs-lookup"><span data-stu-id="47c09-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="47c09-294">從前端伺服器或前端池的 XMPP 閘道到 Edge 伺服器內部 IP 位址或每個邊緣池成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="47c09-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

