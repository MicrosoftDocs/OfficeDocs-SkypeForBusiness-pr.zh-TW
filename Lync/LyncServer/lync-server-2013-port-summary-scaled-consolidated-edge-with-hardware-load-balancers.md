---
title: 連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6260a4ad7f2717e0b4eb2446fc5b17671c3e45a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="ff11e-102">Lync Server 2013 中的連接埠摘要 - 調整式合併 Edge (利用硬體負載平衡器)</span><span class="sxs-lookup"><span data-stu-id="ff11e-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff11e-103">_**主題上次修改日期：** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="ff11e-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="ff11e-104">此案例架構中所述的 Lync Server 2013、Edge 伺服器功能與 Lync Server 2010 中所實施的內容非常類似。</span><span class="sxs-lookup"><span data-stu-id="ff11e-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="ff11e-105">最顯著的新增是針對可擴展訊息和目前狀態通訊協定（XMPP）的**TCP 專案上**的埠5269。</span><span class="sxs-lookup"><span data-stu-id="ff11e-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="ff11e-106">Lync Server 2013 可選擇在 Edge 伺服器或 Edge 池以及前端伺服器或頂層端池中的 XMPP 閘道伺服器上部署 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="ff11e-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="ff11e-107">除了 IPv4，Edge 伺服器現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="ff11e-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="ff11e-108">為清楚起見，在案例中只使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="ff11e-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="ff11e-109">**使用硬體負載平衡來調整合並的邊緣**</span><span class="sxs-lookup"><span data-stu-id="ff11e-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="ff11e-110">![Edge Server 周邊網路連接埠與通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路連接埠與通訊協定")</span><span class="sxs-lookup"><span data-stu-id="ff11e-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="ff11e-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="ff11e-111">Port and Protocol Details</span></span>

<span data-ttu-id="ff11e-112">建議您只開啟支援您提供外部存取的功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="ff11e-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="ff11e-113">若要讓遠端存取作用於任何 edge 服務，必須具備 SIP 流量來流動雙向，如入站/出站邊緣流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="ff11e-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="ff11e-114">換句話說，在「立即訊息（IM）」、「目前狀態」、「web 會議」、音訊/視頻（A/V）及同盟中，都會涉及來自存取邊緣服務的 SIP 訊息。</span><span class="sxs-lookup"><span data-stu-id="ff11e-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="ff11e-115">已調整合並邊緣的防火牆摘要、硬體負載平衡：外部介面–節點1和節點2（範例）</span><span class="sxs-lookup"><span data-stu-id="ff11e-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff11e-116">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="ff11e-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ff11e-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-117">Source IP address</span></span></th>
<th><span data-ttu-id="ff11e-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-118">Destination IP address</span></span></th>
<th><span data-ttu-id="ff11e-119">筆記</span><span class="sxs-lookup"><span data-stu-id="ff11e-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="ff11e-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="ff11e-121">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-122">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-122">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-123">憑證吊銷/CRL 檢查及檢索</span><span class="sxs-lookup"><span data-stu-id="ff11e-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="ff11e-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="ff11e-125">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-126">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-126">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-127">TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="ff11e-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="ff11e-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="ff11e-129">Edge 伺服器存取邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-130">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-130">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-131">經由 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="ff11e-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ff11e-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ff11e-133">Edge 伺服器 A/V 邊緣的服務 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-134">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-134">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-135">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行聯盟時需要。</span><span class="sxs-lookup"><span data-stu-id="ff11e-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ff11e-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ff11e-137">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-138">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-138">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-139">只有與執行 Office 通訊伺服器2007之夥伴的同盟才需要。</span><span class="sxs-lookup"><span data-stu-id="ff11e-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ff11e-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ff11e-141">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-141">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-142">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-143">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="ff11e-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="ff11e-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="ff11e-145">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-145">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-146">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-147">僅限執行 Office 通訊伺服器2007之合作夥伴的同盟所需</span><span class="sxs-lookup"><span data-stu-id="ff11e-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ff11e-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ff11e-149">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-150">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-150">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-151">3478 [輸出] 是用來判斷 Lync Server 所與之通訊的邊緣伺服器版本，也是從邊緣伺服器到邊緣伺服器的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="ff11e-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="ff11e-152">使用 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 進行聯盟所需，以及在公司中部署了多個 Edge 池的情況。</span><span class="sxs-lookup"><span data-stu-id="ff11e-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-153">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ff11e-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ff11e-154">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-154">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-155">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-156">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="ff11e-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-157">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-158">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-158">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-159">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-160">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="ff11e-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-161">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-162">Edge 伺服器 A/V 邊緣服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-163">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-163">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-164">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="ff11e-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="ff11e-165">用於調整合並邊緣的防火牆摘要、硬體負載平衡：內部介面節點1和節點2</span><span class="sxs-lookup"><span data-stu-id="ff11e-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff11e-166">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="ff11e-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ff11e-167">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-167">Source IP address</span></span></th>
<th><span data-ttu-id="ff11e-168">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-168">Destination IP address</span></span></th>
<th><span data-ttu-id="ff11e-169">筆記</span><span class="sxs-lookup"><span data-stu-id="ff11e-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="ff11e-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="ff11e-171">[任何] （可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端池虛擬 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="ff11e-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-172">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-173">在前端伺服器或前端池上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="ff11e-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="ff11e-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-175">[任何] （可定義為擁有中央管理儲存區的前端伺服器伺服器 IP 或池）</span><span class="sxs-lookup"><span data-stu-id="ff11e-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-176">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-177">從中央管理儲存體將變更複製到 Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="ff11e-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="ff11e-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="ff11e-179">[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</span><span class="sxs-lookup"><span data-stu-id="ff11e-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-180">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-181">從內部部署到內部邊緣伺服器介面的網路會議流量</span><span class="sxs-lookup"><span data-stu-id="ff11e-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ff11e-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ff11e-183">[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</span><span class="sxs-lookup"><span data-stu-id="ff11e-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-184">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-185">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑、Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="ff11e-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-187">[任何] （可以定義為 [控制器 IP]、[前端伺服器 IP] 或 [池虛擬 IP]）</span><span class="sxs-lookup"><span data-stu-id="ff11e-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-188">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-189">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑、Survivable 分支裝置或 Survivable 分支伺服器如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="ff11e-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="ff11e-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="ff11e-191">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-191">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-192">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-193">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="ff11e-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="ff11e-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="ff11e-195">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-195">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-196">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-197">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="ff11e-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="ff11e-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="ff11e-199">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-199">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-200">Edge 伺服器內部介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-201">使用 Lync Server 管理命令介面與集中式記錄服務 Cmdlet、ClsController 命令列（ClsController）或 agent （ClsAgent .exe）命令和記錄集合的集中式記錄服務控制器</span><span class="sxs-lookup"><span data-stu-id="ff11e-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff11e-202">硬體負載平衡器在部署時有特定的需求，以提供 Lync Server 的可用性與負載平衡。</span><span class="sxs-lookup"><span data-stu-id="ff11e-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="ff11e-203">這些需求是在下圖和資料表中定義。</span><span class="sxs-lookup"><span data-stu-id="ff11e-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="ff11e-204">協力廠商廠商對於此處定義的需求，可能會使用不同的術語。</span><span class="sxs-lookup"><span data-stu-id="ff11e-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="ff11e-205">您必須將 Lync Server 的需求對應到您的硬體負載平衡器提供者所提供的功能和設定選項。</span><span class="sxs-lookup"><span data-stu-id="ff11e-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="ff11e-206">配置硬體負載平衡器時，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="ff11e-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="ff11e-207">您可以在硬體負載平衡器（HLB）上設定來源網路位址轉譯（SNAT），以存取邊緣服務和網路會議 Edge 服務</span><span class="sxs-lookup"><span data-stu-id="ff11e-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="ff11e-208">SNAT 不能在 A/V 邊緣服務上設定-A/V Edge 服務必須回應實際的伺服器位址，而不是 HLB 的虛擬 IP （VIP），以便透過 NAT （STUN）/traversal 使用中繼 NAT （關閉）/federation 轉彎（FTURN）來正常運作</span><span class="sxs-lookup"><span data-stu-id="ff11e-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="ff11e-209">如果用戶端傳送要求給 HLB，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="ff11e-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="ff11e-210">如果用戶端傳送要求給邊緣，回應必須從邊緣 IP 傳回</span><span class="sxs-lookup"><span data-stu-id="ff11e-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="ff11e-211">公用 IP 位址是在每個伺服器介面和 HLB 的 Vip 上使用，而您的公用 IP 位址需求是 N + 1，其中包含每個真實伺服器介面的公用 IP 位址，以及每個 HLB VIP 的一個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ff11e-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="ff11e-212">如果您在池中有2台邊緣伺服器，這會產生9個公用 IP 位址，其中3個是用於 HLB Vip，另一個用於每個 Edge 伺服器介面（在伺服器上總共6個）</span><span class="sxs-lookup"><span data-stu-id="ff11e-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="ff11e-213">針對 [存取邊緣服務] 和 [Web 會議 Edge 服務] （以及在 HLB 上使用 NAT），用戶端會與 VIP 進行聯絡，而 VIP 會將來源 IP 位址從用戶端變更為自己的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="ff11e-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="ff11e-214">伺服器介面會將寄件者位址定址至 VIP，而 VIP 會從伺服器介面 IP 位址變更來源位址，並將資料包傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="ff11e-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="ff11e-215">在 A/V 邊緣服務中，VIP 不能變更來源 IP 位址，而真正的伺服器位址會直接傳回用戶端–您無法在 HLB 上設定 NAT 以進行 AV 流量</span><span class="sxs-lookup"><span data-stu-id="ff11e-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="ff11e-216">如果用戶端傳送要求至 HLB VIP，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="ff11e-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="ff11e-217">如果用戶端傳送要求至 Edge IP，回應必須從邊緣 IP 傳回</span><span class="sxs-lookup"><span data-stu-id="ff11e-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="ff11e-218">針對 AV，外部防火牆會保留所有資料包的真實伺服器公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="ff11e-219">一旦建立，用戶端到 A/V 邊緣服務通訊就是真實的伺服器，而不是 HLB</span><span class="sxs-lookup"><span data-stu-id="ff11e-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="ff11e-220">內部邊緣至內部伺服器和用戶端必須路由，且為主機伺服器或用戶端的所有內部網路設定持久路由</span><span class="sxs-lookup"><span data-stu-id="ff11e-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="ff11e-221">HLB 存取邊緣服務 VIP 將充當每個 Edge 伺服器介面的預設閘道</span><span class="sxs-lookup"><span data-stu-id="ff11e-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ff11e-222">如需有關 NAT 規劃與功能的進一步資訊，請參閱<A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬體負載平衡器需求</A>。</span><span class="sxs-lookup"><span data-stu-id="ff11e-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ff11e-223">![Edge Server 連接埠與通訊協定詳細資訊](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 連接埠與通訊協定詳細資訊")</span><span class="sxs-lookup"><span data-stu-id="ff11e-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="ff11e-224">已調整的合併邊緣所需的外部埠設定、硬體負載平衡：外部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="ff11e-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff11e-225">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="ff11e-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ff11e-226">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-226">Source IP address</span></span></th>
<th><span data-ttu-id="ff11e-227">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-227">Destination IP address</span></span></th>
<th><span data-ttu-id="ff11e-228">筆記</span><span class="sxs-lookup"><span data-stu-id="ff11e-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ff11e-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ff11e-230">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-230">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-231">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="ff11e-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-232">XMPP Proxy service 接受來自已定義 XMPP 聯合體中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="ff11e-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="ff11e-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="ff11e-234">XMPP Proxy service （與存取邊緣服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="ff11e-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-235">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-235">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-236">XMPP Proxy service 會傳送流量給已定義 XMPP 聯合體中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="ff11e-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-237">Access/SIP （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-238">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-238">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-239">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-240">外部使用者存取的用戶端到伺服器 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="ff11e-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-241">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ff11e-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ff11e-242">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-242">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-243">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-244">使用 SIP 的 SIP 信號、同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ff11e-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-245">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ff11e-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ff11e-246">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-247">聯盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="ff11e-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="ff11e-248">使用 SIP 的 SIP 信號、同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="ff11e-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-249">網路會議/PSOM （TLS）/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-250">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-250">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-251">Edge 伺服器網路會議 Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-252">網路會議媒體</span><span class="sxs-lookup"><span data-stu-id="ff11e-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-253">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ff11e-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ff11e-254">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-254">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-255">Edge 伺服器 A/V 邊緣服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-256">STUN/開啟候選人對 UDP/3478 的協商</span><span class="sxs-lookup"><span data-stu-id="ff11e-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-257">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-258">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-258">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-259">Edge 伺服器 A/V 邊緣服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="ff11e-260">STUN/開啟候選人對 TCP/443 的協商</span><span class="sxs-lookup"><span data-stu-id="ff11e-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="ff11e-261">用於調整合並邊緣的防火牆摘要、硬體負載平衡：內部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="ff11e-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff11e-262">角色/通訊協定/TCP 或 UDP/埠</span><span class="sxs-lookup"><span data-stu-id="ff11e-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="ff11e-263">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-263">Source IP address</span></span></th>
<th><span data-ttu-id="ff11e-264">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="ff11e-264">Destination IP address</span></span></th>
<th><span data-ttu-id="ff11e-265">筆記</span><span class="sxs-lookup"><span data-stu-id="ff11e-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-266">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ff11e-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ff11e-267">[任何] （可定義為 [控制器]、[控制器池] 虛擬 IP 位址、[前端伺服器] 或 [前端池虛擬 IP 位址]）</span><span class="sxs-lookup"><span data-stu-id="ff11e-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-268">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-269">輸出 SIP 流量（從控制器、控制器池虛擬 IP 位址、前端伺服器或前端池虛擬 IP 位址）到內部邊緣 VIP</span><span class="sxs-lookup"><span data-stu-id="ff11e-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-270">Access/SIP （MTLS）/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="ff11e-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="ff11e-271">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-272">[任何] （可定義為 [控制器]、[控制器池] 虛擬 IP 位址、[前端伺服器] 或 [前端池虛擬 IP 位址]）</span><span class="sxs-lookup"><span data-stu-id="ff11e-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-273">來自 Edge 伺服器內部介面的入站 SIP 流量（針對控制器、控制器池虛擬 IP 位址、前端伺服器或前端池虛擬 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="ff11e-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="ff11e-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="ff11e-275">[任何] （可以使用此 Edge 伺服器定義為前端伺服器 IP 位址或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器）</span><span class="sxs-lookup"><span data-stu-id="ff11e-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="ff11e-276">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-277">使用此 Edge 伺服器從前端伺服器或前端池 IP 位址或任何 Survivable 分支裝置或 Survivable 分支伺服器驗證 A/V 使用者（A/V 驗證服務）</span><span class="sxs-lookup"><span data-stu-id="ff11e-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="ff11e-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="ff11e-279">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-279">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-280">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-281">內部與外部使用者之間的 A/V 媒體傳輸的首選路徑</span><span class="sxs-lookup"><span data-stu-id="ff11e-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff11e-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-283">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-283">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-284">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-285">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="ff11e-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff11e-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="ff11e-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="ff11e-287">Edge 伺服器內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="ff11e-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="ff11e-288">每</span><span class="sxs-lookup"><span data-stu-id="ff11e-288">Any</span></span></p></td>
<td><p><span data-ttu-id="ff11e-289">內部與外部使用者之間的 A/V 媒體傳輸的回退路徑如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸與桌面共用</span><span class="sxs-lookup"><span data-stu-id="ff11e-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

