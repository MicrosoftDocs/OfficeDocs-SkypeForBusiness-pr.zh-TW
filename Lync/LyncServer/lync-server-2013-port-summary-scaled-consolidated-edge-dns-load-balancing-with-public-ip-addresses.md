---
title: Lync Server 2013：埠摘要-調整式合併 edge （利用公用 IP 位址進行 DNS 負載平衡）
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
ms.openlocfilehash: 5318f418c2bbd0876999aedcb33b559c5572b20a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534120"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="33dd3-102">Lync Server 2013 中的埠摘要-調整式合併 edge （透過公用 IP 位址進行 DNS 負載平衡）</span><span class="sxs-lookup"><span data-stu-id="33dd3-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33dd3-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="33dd3-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="33dd3-104">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="33dd3-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="33dd3-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="33dd3-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="33dd3-106">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="33dd3-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="33dd3-107">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="33dd3-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="33dd3-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="33dd3-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="33dd3-109">**調整式合併 Edge 的企業周邊網路（透過公用 IP 位址進行 DNS 負載平衡）**</span><span class="sxs-lookup"><span data-stu-id="33dd3-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="33dd3-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="33dd3-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="33dd3-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="33dd3-111">Port and Protocol Details</span></span>

<span data-ttu-id="33dd3-112">建議您只開啟支援您提供外部存取之功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="33dd3-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="33dd3-113">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="33dd3-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="33dd3-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="33dd3-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="33dd3-115">調整式合併 Edge （利用公用 IP 位址進行 DNS 負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="33dd3-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dd3-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="33dd3-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33dd3-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-117">Source IP address</span></span></th>
<th><span data-ttu-id="33dd3-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-118">Destination IP address</span></span></th>
<th><span data-ttu-id="33dd3-119">注意事項</span><span class="sxs-lookup"><span data-stu-id="33dd3-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="33dd3-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="33dd3-121">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-121">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-122">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="33dd3-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-124">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="33dd3-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="33dd3-125">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-126">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-126">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-127">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="33dd3-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-128">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="33dd3-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="33dd3-129">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-130">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-130">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-131">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="33dd3-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-132">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="33dd3-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="33dd3-133">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-134">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-134">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-135">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="33dd3-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-136">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-137">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-137">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-138">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-139">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-140">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-141">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-141">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-142">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-143">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-144">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-145">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-146">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-146">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-148">Web 會議/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-149">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-149">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-150">Edge Server Web 會議 Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-151">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="33dd3-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="33dd3-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="33dd3-153">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-154">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-155">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="33dd3-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="33dd3-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="33dd3-157">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-158">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-158">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-159">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="33dd3-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="33dd3-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="33dd3-161">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-161">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-162">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-163">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="33dd3-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="33dd3-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="33dd3-165">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-165">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-166">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-167">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="33dd3-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="33dd3-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="33dd3-169">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-170">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-170">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-171">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="33dd3-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="33dd3-172">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="33dd3-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="33dd3-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="33dd3-174">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-174">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-175">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-176">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="33dd3-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-178">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-178">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-179">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-180">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="33dd3-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-182">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-183">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-183">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="33dd3-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="33dd3-185">調整式合併 Edge （透過公用 IP 位址進行 DNS 負載平衡）的防火牆摘要：內部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="33dd3-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dd3-186">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="33dd3-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33dd3-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-187">Source IP address</span></span></th>
<th><span data-ttu-id="33dd3-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-188">Destination IP address</span></span></th>
<th><span data-ttu-id="33dd3-189">註解</span><span class="sxs-lookup"><span data-stu-id="33dd3-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="33dd3-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="33dd3-191">任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="33dd3-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-193">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-195">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="33dd3-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-197"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-199">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-200">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="33dd3-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-201">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="33dd3-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="33dd3-203">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="33dd3-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-204">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-205">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="33dd3-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="33dd3-207">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="33dd3-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-209">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="33dd3-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="33dd3-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="33dd3-211">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-211">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-213">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="33dd3-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-215">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-215">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-217">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="33dd3-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="33dd3-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-219">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="33dd3-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="33dd3-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-221">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="33dd3-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="33dd3-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="33dd3-223">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-223">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-225">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="33dd3-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="33dd3-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="33dd3-227">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-227">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-229">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="33dd3-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="33dd3-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="33dd3-231">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-231">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="33dd3-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="33dd3-233">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="33dd3-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="33dd3-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="33dd3-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dd3-235">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="33dd3-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33dd3-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-236">Source IP address</span></span></th>
<th><span data-ttu-id="33dd3-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-237">Destination IP address</span></span></th>
<th><span data-ttu-id="33dd3-238">注意事項</span><span class="sxs-lookup"><span data-stu-id="33dd3-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-239">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-240">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-241">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-241">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-242">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="33dd3-243">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dd3-244">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="33dd3-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33dd3-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-245">Source IP address</span></span></th>
<th><span data-ttu-id="33dd3-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="33dd3-246">Destination IP address</span></span></th>
<th><span data-ttu-id="33dd3-247">注意事項</span><span class="sxs-lookup"><span data-stu-id="33dd3-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-248">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-249">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="33dd3-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="33dd3-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-251">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-252">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="33dd3-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="33dd3-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-254">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="33dd3-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="33dd3-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="33dd3-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-256">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="33dd3-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="33dd3-257">用戶端</span><span class="sxs-lookup"><span data-stu-id="33dd3-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="33dd3-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-259">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="33dd3-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="33dd3-261">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-262">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="33dd3-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="33dd3-263">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="33dd3-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="33dd3-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="33dd3-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="33dd3-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="33dd3-267">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="33dd3-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="33dd3-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="33dd3-269">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="33dd3-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="33dd3-270">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="33dd3-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="33dd3-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="33dd3-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="33dd3-272">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="33dd3-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33dd3-273">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="33dd3-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="33dd3-274">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="33dd3-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="33dd3-275">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="33dd3-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="33dd3-276">註解</span><span class="sxs-lookup"><span data-stu-id="33dd3-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="33dd3-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="33dd3-278">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-278">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-279">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="33dd3-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-280">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="33dd3-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="33dd3-281">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="33dd3-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33dd3-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="33dd3-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="33dd3-283">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="33dd3-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="33dd3-284">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-284">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-285">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="33dd3-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="33dd3-286">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="33dd3-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33dd3-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="33dd3-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="33dd3-288">任何</span><span class="sxs-lookup"><span data-stu-id="33dd3-288">Any</span></span></p></td>
<td><p><span data-ttu-id="33dd3-289">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="33dd3-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="33dd3-290">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="33dd3-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

