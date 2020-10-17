---
title: 埠摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）
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
ms.openlocfilehash: 4a5aaa4628a92174aca39579c5f2e6a8e4f31987
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534000"
---
# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="6d0d8-102">Lync Server 2013 中的埠摘要-單一合併 edge （使用 NAT 透過私人 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="6d0d8-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d0d8-103">_**主題上次修改日期：** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="6d0d8-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="6d0d8-104">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="6d0d8-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="6d0d8-106">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="6d0d8-107">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="6d0d8-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="6d0d8-109">**具有使用 NAT 的私人 IP 位址之單一合併 Edge Server 的網路周邊**</span><span class="sxs-lookup"><span data-stu-id="6d0d8-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="6d0d8-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="6d0d8-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="6d0d8-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="6d0d8-111">Port and Protocol Details</span></span>

<span data-ttu-id="6d0d8-112">建議您僅針對要提供給外部存取的功能，開啟支援所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="6d0d8-113">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="6d0d8-114">另一種方法，「Access Edge service」的 SIP 訊息會包含在立即訊息 (IM) 、顯示狀態、web 會議、音訊/視頻 (A/V) 和同盟中。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="6d0d8-115">具有使用 NAT 的私人 IP 位址之單一合併 Edge 的防火牆摘要：外部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d0d8-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="6d0d8-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d0d8-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-117">Source IP address</span></span></th>
<th><span data-ttu-id="6d0d8-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-118">Destination IP address</span></span></th>
<th><span data-ttu-id="6d0d8-119">注意事項</span><span class="sxs-lookup"><span data-stu-id="6d0d8-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d0d8-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-121">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-121">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-122">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-123">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-124">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="6d0d8-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-125">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-126">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-126">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-127">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="6d0d8-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-128">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="6d0d8-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-129">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-130">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-130">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-131">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="6d0d8-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-132">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="6d0d8-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-133">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-134">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-134">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-135">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="6d0d8-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-136">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-137">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-137">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-138">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-139">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-140">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-141">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-141">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-142">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-143">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-144">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-145">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-146">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-146">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-147">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-148">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-149">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-149">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-150">Edge Server Web 會議 Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-151">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="6d0d8-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6d0d8-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-153">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-154">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-154">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-155">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6d0d8-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-157">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-158">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-158">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-159">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6d0d8-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-161">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-161">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-162">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-163">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="6d0d8-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6d0d8-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-165">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-165">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-166">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-167">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="6d0d8-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-168">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d0d8-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-169">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-170">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-170">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-171">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="6d0d8-172">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-173">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d0d8-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-174">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-174">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-175">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-176">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="6d0d8-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-177">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-178">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-178">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-179">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-180">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="6d0d8-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-181">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-182">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-183">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-183">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-184">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="6d0d8-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="6d0d8-185">具有使用 NAT 的私人 IP 位址之單一合併 Edge 的防火牆摘要：內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d0d8-186">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="6d0d8-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d0d8-187">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-187">Source IP address</span></span></th>
<th><span data-ttu-id="6d0d8-188">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-188">Destination IP address</span></span></th>
<th><span data-ttu-id="6d0d8-189">註解</span><span class="sxs-lookup"><span data-stu-id="6d0d8-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6d0d8-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-191">任何 (都可以定義為 Standard Edition server IP、Standard Edition server IP 位址，或執行 XMPP 閘道服務的集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-193">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-195">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-197"> (從 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) 到 Edge Server 內部介面的輸出 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-199">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-200">任何 (都可以定義為 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-201">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區 IP 位址、前端伺服器或前端集區 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="6d0d8-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-203">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區中的每個前端伺服器 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-204">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-205">如果在集區中，則為 Edge Server 內部介面，來自前端伺服器或每一部前端伺服器的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="6d0d8-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-207">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-208">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-209">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="6d0d8-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d0d8-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-211">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-211">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-212">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-213">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="6d0d8-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-215">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-215">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-216">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-217">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="6d0d8-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-219">任何 (都可以定義為前端伺服器的 IP 位址，或存放中央管理存放區的集區) </span><span class="sxs-lookup"><span data-stu-id="6d0d8-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-220">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-221">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="6d0d8-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="6d0d8-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-223">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-223">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-224">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-225">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="6d0d8-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="6d0d8-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-227">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-227">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-228">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-229">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="6d0d8-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="6d0d8-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-231">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-231">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-232">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="6d0d8-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-233">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="6d0d8-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="6d0d8-234">同盟的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="6d0d8-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d0d8-235">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="6d0d8-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d0d8-236">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-236">Source IP address</span></span></th>
<th><span data-ttu-id="6d0d8-237">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-237">Destination IP address</span></span></th>
<th><span data-ttu-id="6d0d8-238">注意事項</span><span class="sxs-lookup"><span data-stu-id="6d0d8-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-239">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-240">Access Edge Service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-241">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-241">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-242">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="6d0d8-243">防火牆摘要 - 公用立即訊息連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d0d8-244">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="6d0d8-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d0d8-245">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-245">Source IP address</span></span></th>
<th><span data-ttu-id="6d0d8-246">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="6d0d8-246">Destination IP address</span></span></th>
<th><span data-ttu-id="6d0d8-247">注意事項</span><span class="sxs-lookup"><span data-stu-id="6d0d8-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-248">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-249">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="6d0d8-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-250">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-251">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-252">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="6d0d8-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-253">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-254">公用 IM 連線協力廠商</span><span class="sxs-lookup"><span data-stu-id="6d0d8-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-255">適用於使用 SIP 的同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="6d0d8-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-256">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="6d0d8-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-257">用戶端</span><span class="sxs-lookup"><span data-stu-id="6d0d8-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-258">Edge Server Access Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-259">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="6d0d8-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-261">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-262">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="6d0d8-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-263">如果有設定 IM 連線，可與 Windows Live Messenger 用於 A/V 工作階段</span><span class="sxs-lookup"><span data-stu-id="6d0d8-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-264">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d0d8-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-265">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-266">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="6d0d8-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-267">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="6d0d8-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-268">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="6d0d8-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-269">Live Messenger 用戶端</span><span class="sxs-lookup"><span data-stu-id="6d0d8-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-270">Edge Server A/V Edge service</span><span class="sxs-lookup"><span data-stu-id="6d0d8-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-271">與 Windows Live Messenger 進行公用 IM 連線時必須使用</span><span class="sxs-lookup"><span data-stu-id="6d0d8-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="6d0d8-272">可延伸訊息和顯示狀態通訊協定的防火牆摘要</span><span class="sxs-lookup"><span data-stu-id="6d0d8-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d0d8-273">通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="6d0d8-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="6d0d8-274">來源 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="6d0d8-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="6d0d8-275">目的地 (IP 位址)</span><span class="sxs-lookup"><span data-stu-id="6d0d8-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="6d0d8-276">註解</span><span class="sxs-lookup"><span data-stu-id="6d0d8-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d0d8-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-278">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-278">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-279">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="6d0d8-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-280">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6d0d8-281">允許來自同盟 XMPP 合作夥伴的 Edge Server XMPP proxy 的通訊</span><span class="sxs-lookup"><span data-stu-id="6d0d8-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d0d8-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="6d0d8-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-283">Edge Server Access Edge service interface IP address</span><span class="sxs-lookup"><span data-stu-id="6d0d8-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-284">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-284">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-285">XMPP 的標準伺服器對伺服器通訊連接埠。</span><span class="sxs-lookup"><span data-stu-id="6d0d8-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="6d0d8-286">允許從 Edge Server XMPP proxy 到同盟 XMPP 合作夥伴的通訊</span><span class="sxs-lookup"><span data-stu-id="6d0d8-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d0d8-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="6d0d8-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-288">任何</span><span class="sxs-lookup"><span data-stu-id="6d0d8-288">Any</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-289">每個內部 Edge Server 介面 IP</span><span class="sxs-lookup"><span data-stu-id="6d0d8-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="6d0d8-290">從前端伺服器或前端集區的 XMPP 閘道到 Edge Server 內部 IP 位址或每個 Edge 集區成員的內部 IP 位址的內部 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="6d0d8-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

