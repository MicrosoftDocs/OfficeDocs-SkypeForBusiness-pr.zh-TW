---
title: 連接埠摘要-調整式合併邊緣搭配硬體負載平衡器
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
ms.openlocfilehash: 78196bab17af69d83bbeacf636b4b2ba4e972121
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="a3b33-102">連接埠摘要-調整式合併邊緣搭配硬體負載平衡器在 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3b33-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3b33-103">_**主題上次修改日期：** 2015 年 04 月 27 日_</span><span class="sxs-lookup"><span data-stu-id="a3b33-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="a3b33-104">Lync Server 2013 中，在此案例的架構中所述的 Edge Server 功能是非常類似於項目已在 Lync Server 2010 中實作。</span><span class="sxs-lookup"><span data-stu-id="a3b33-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a3b33-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="a3b33-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a3b33-106">Lync Server 2013 選擇性地部署 Edge Server 或 Edge 集區與前端伺服器或前端集區上的 XMPP 閘道伺服器上的 XMPP proxy。</span><span class="sxs-lookup"><span data-stu-id="a3b33-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a3b33-107">IPv4，除了 Edge Server 現在可支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="a3b33-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a3b33-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="a3b33-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a3b33-109">**調整式合併 Edge，使用硬體負載平衡**</span><span class="sxs-lookup"><span data-stu-id="a3b33-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="a3b33-110">![Edge Server 周邊網路連接埠和通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路連接埠和通訊協定")</span><span class="sxs-lookup"><span data-stu-id="a3b33-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a3b33-111">連接埠和通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="a3b33-111">Port and Protocol Details</span></span>

<span data-ttu-id="a3b33-112">建議您開啟支援所提供給外部存取的功能所需的連接埠。</span><span class="sxs-lookup"><span data-stu-id="a3b33-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a3b33-113">適用於任何 edge service 的遠端存取，它是強制雙向輸入/輸出 edge 流量圖所示流向允許的 SIP 流量。</span><span class="sxs-lookup"><span data-stu-id="a3b33-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="a3b33-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="a3b33-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a3b33-115">調整式合併 Edge，硬體負載平衡的防火牆摘要： 外部介面 – 節點 1 與節點 2 (Example)</span><span class="sxs-lookup"><span data-stu-id="a3b33-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3b33-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a3b33-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3b33-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-117">Source IP address</span></span></th>
<th><span data-ttu-id="a3b33-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a3b33-119">附註</span><span class="sxs-lookup"><span data-stu-id="a3b33-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a3b33-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a3b33-121">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-122">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-122">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-123">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="a3b33-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a3b33-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a3b33-125">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-126">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-127">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="a3b33-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a3b33-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a3b33-129">Edge Server Access Edge 服務公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-130">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-131">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="a3b33-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a3b33-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3b33-133">Edge Server A / V Edge service IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-134">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-135">所需的同盟與協力廠商執行 Office Communications Server 2007、 Office Communications Server 2007 R2、 Lync Server 2010 和 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="a3b33-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a3b33-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3b33-137">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-138">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-139">僅適用於同盟需要與執行 Office Communications Server 2007 的協力廠商。</span><span class="sxs-lookup"><span data-stu-id="a3b33-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a3b33-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3b33-141">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-142">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-143">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a3b33-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a3b33-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a3b33-145">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-146">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-147">僅適用於同盟需要與協力廠商執行 Office Communications Server 2007</span><span class="sxs-lookup"><span data-stu-id="a3b33-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-148">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3b33-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3b33-149">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-150">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-151">3478 輸出用於判斷 Lync Server 與通訊，以及從 Edge Server 至 Edge Server 的媒體流量的 Edge Server 的版本。</span><span class="sxs-lookup"><span data-stu-id="a3b33-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a3b33-152">所需的 Lync Server 2010、 Windows Live Messenger 與 Office Communications Server 2007 R2，同盟，以及如果公司內部署多個 Edge 集區。</span><span class="sxs-lookup"><span data-stu-id="a3b33-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-153">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3b33-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3b33-154">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-155">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-156">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="a3b33-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-157">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-158">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-159">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-160">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="a3b33-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-161">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-162">Edge Server A / V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-163">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-164">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="a3b33-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="a3b33-165">調整式合併 Edge，硬體負載平衡的防火牆摘要： 內部介面節點 1 與節點 2</span><span class="sxs-lookup"><span data-stu-id="a3b33-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3b33-166">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a3b33-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3b33-167">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-167">Source IP address</span></span></th>
<th><span data-ttu-id="a3b33-168">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-168">Destination IP address</span></span></th>
<th><span data-ttu-id="a3b33-169">附註</span><span class="sxs-lookup"><span data-stu-id="a3b33-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a3b33-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a3b33-171">任何 （可定義為前端伺服器位址] 或 [前端集區虛擬 IP 位址執行 「 XMPP 閘道服務）</span><span class="sxs-lookup"><span data-stu-id="a3b33-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-172">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-173">從前端伺服器或前端集區上執行的 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="a3b33-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a3b33-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-175">任何 （可定義為前端伺服器 server IP 或保有中央管理存放區的集區）</span><span class="sxs-lookup"><span data-stu-id="a3b33-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-176">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-177">從中央管理存放區的 Edge server 的變更的複寫</span><span class="sxs-lookup"><span data-stu-id="a3b33-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a3b33-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a3b33-179">任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</span><span class="sxs-lookup"><span data-stu-id="a3b33-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-180">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-181">從內部部署至 Internal Edge Server 介面的 web 會議流量</span><span class="sxs-lookup"><span data-stu-id="a3b33-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3b33-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3b33-183">任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</span><span class="sxs-lookup"><span data-stu-id="a3b33-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-184">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-185">慣用的路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間</span><span class="sxs-lookup"><span data-stu-id="a3b33-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-187">任何 （可定義為 Director IP、 前端伺服器 IP 或集區虛擬 IP）</span><span class="sxs-lookup"><span data-stu-id="a3b33-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-188">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-189">後援路徑 a / V 媒體傳輸內部與外部使用者，Survivable Branch Appliance 或 Survivable Branch 伺服器之間，如果無法建立 UDP 通訊、 TCP 用於檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="a3b33-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a3b33-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a3b33-191">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-191">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-193">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="a3b33-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a3b33-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a3b33-195">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-195">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-197">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="a3b33-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a3b33-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a3b33-199">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-201">使用 Lync Server 管理命令介面和 Centralized Logging Service 指令程式、 ClsController 命令列 (ClsController.exe) 或代理程式 (ClsAgent.exe) 命令和記錄集合的集中式記錄服務控制站</span><span class="sxs-lookup"><span data-stu-id="a3b33-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a3b33-202">硬體負載平衡器有時提供可用性和負載平衡的 Lync Server 部署的特定需求。</span><span class="sxs-lookup"><span data-stu-id="a3b33-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="a3b33-203">下圖與資料表中定義的需求。</span><span class="sxs-lookup"><span data-stu-id="a3b33-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="a3b33-204">第三方廠商可能使用不同的術語，如以下所定義的需求。</span><span class="sxs-lookup"><span data-stu-id="a3b33-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="a3b33-205">您必須將 Lync Server 的需求對應至您的硬體負載平衡器廠商所提供的組態選項的功能。</span><span class="sxs-lookup"><span data-stu-id="a3b33-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="a3b33-206">當設定硬體負載平衡器，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="a3b33-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="a3b33-207">來源網路位址轉譯 (SNAT) 可以設定上的 Access Edge service 和 Web Conferencing Edge service 的硬體負載平衡器 (HLB)</span><span class="sxs-lookup"><span data-stu-id="a3b33-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="a3b33-208">SNAT 無法進行設定的 a / V Edge service – A / V Edge service 必須回應與實際的伺服器位址，不 HLB 虛擬 IP (VIP)，如簡單周遊 UDP 透過 NAT (STUN) / 周遊使用轉送 NAT （開啟） / 同盟開啟 (FTURN) 才能正常運作</span><span class="sxs-lookup"><span data-stu-id="a3b33-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="a3b33-209">如果用戶端會將要求傳送至 HLB，回應必須來自回 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a3b33-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a3b33-210">如果用戶端會將要求傳送至 Edge，回應必須來自回 Edge IP</span><span class="sxs-lookup"><span data-stu-id="a3b33-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a3b33-211">HLB Vip 和每個伺服器介面上使用公用 IP 位址和您的公用 IP 位址需求為 N + 1，其中有是實際的伺服器的每個介面，另一個用於每個 HLB VIP 公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a3b33-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="a3b33-212">其中您有 2 Edge server 集區，這會導致 9 公用 IP 位址，其中 3 及所用的 HLB Vip，一個用於每個 Edge server 介面 （6 的伺服器總計）</span><span class="sxs-lookup"><span data-stu-id="a3b33-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="a3b33-213">Access edge service 和 Web Conferencing Edge service] （和 HLB 上使用 NAT） 用戶端的連絡人的 VIP，來源 IP 位址從用戶端它自己的 IP 位址的 VIP 變更。</span><span class="sxs-lookup"><span data-stu-id="a3b33-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="a3b33-214">伺服器介面 vip，來源地址從伺服器介面 IP 位址的 VIP 變更位址的回覆地址，並將封包傳送到用戶端</span><span class="sxs-lookup"><span data-stu-id="a3b33-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="a3b33-215">A / V Edge service 為 VIP 不得變更來源 IP 位址，以及實際的伺服器位址直接傳回給用戶端 – 您不能用於 AV 流量 HLB 上設定 NAT</span><span class="sxs-lookup"><span data-stu-id="a3b33-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="a3b33-216">如果用戶端會將要求傳送至 HLB VIP，回應必須來自回 HLB VIP</span><span class="sxs-lookup"><span data-stu-id="a3b33-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a3b33-217">如果用戶端會將要求傳送至 Edge IP，回應必須來自回 Edge IP</span><span class="sxs-lookup"><span data-stu-id="a3b33-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a3b33-218">AV，如外部防火牆會保留所有的封包的實際的伺服器公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="a3b33-219">一次建立的用戶端 a / V Edge 服務通訊是實際的伺服器，不 HLB</span><span class="sxs-lookup"><span data-stu-id="a3b33-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="a3b33-220">必須路由傳送至內部伺服器和用戶端的內部邊緣，並在該主機伺服器或用戶端的所有內部網路設定持續路由</span><span class="sxs-lookup"><span data-stu-id="a3b33-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="a3b33-221">HLB Access Edge service VIP 做為預設閘道，以每個 Edge server 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a3b33-222">如需規劃 NAT 和功能的進一步資訊，請參閱<A href="lync-server-2013-hardware-load-balancer-requirements.md">硬體負載平衡器需求，針對 Lync Server 2013</A>。</span><span class="sxs-lookup"><span data-stu-id="a3b33-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a3b33-223">![Edge Server 的連接埠和通訊協定詳細資料](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 的連接埠和通訊協定詳細資料")</span><span class="sxs-lookup"><span data-stu-id="a3b33-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="a3b33-224">外部連接埠設定所需的調整式合併 Edge，硬體負載平衡： 外部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="a3b33-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3b33-225">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a3b33-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3b33-226">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-226">Source IP address</span></span></th>
<th><span data-ttu-id="a3b33-227">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-227">Destination IP address</span></span></th>
<th><span data-ttu-id="a3b33-228">附註</span><span class="sxs-lookup"><span data-stu-id="a3b33-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a3b33-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a3b33-230">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-230">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-231">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="a3b33-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-232">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="a3b33-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a3b33-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a3b33-234">XMPP Proxy 服務 （與 Access Edge 服務共用 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="a3b33-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-235">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-236">XMPP Proxy 服務將流量傳送至已定義之 XMPP 同盟中 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="a3b33-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-237">Access/SIP (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-238">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-238">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-239">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-240">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="a3b33-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-241">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3b33-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3b33-242">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-242">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-243">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-244">SIP 使用 SIP 信號、 同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="a3b33-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-245">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3b33-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3b33-246">Access Edge 服務公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-247">同盟協力廠商</span><span class="sxs-lookup"><span data-stu-id="a3b33-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="a3b33-248">SIP 使用 SIP 信號、 同盟與公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="a3b33-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-249">Web 會議 /PSOM (TLS) / TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-250">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-250">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-251">Edge Server Web Conferencing Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-252">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="a3b33-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-253">A/V/STUN，MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3b33-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3b33-254">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-254">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-255">Edge Server A / V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-256">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="a3b33-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-257">A/V/STUN，MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-258">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-258">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-259">Edge Server A / V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a3b33-260">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="a3b33-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="a3b33-261">調整式合併 Edge，硬體負載平衡的防火牆摘要： 內部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="a3b33-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a3b33-262">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="a3b33-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a3b33-263">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-263">Source IP address</span></span></th>
<th><span data-ttu-id="a3b33-264">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="a3b33-264">Destination IP address</span></span></th>
<th><span data-ttu-id="a3b33-265">附註</span><span class="sxs-lookup"><span data-stu-id="a3b33-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-266">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3b33-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3b33-267">任何 （可定義為 Director，Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="a3b33-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-268">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-269">輸出 SIP 流量 （來自 Director、 Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址) 內部 Edge VIP</span><span class="sxs-lookup"><span data-stu-id="a3b33-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-270">Access/SIP (MTLS) / TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a3b33-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a3b33-271">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-272">任何 （可定義為 Director，Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址）</span><span class="sxs-lookup"><span data-stu-id="a3b33-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-273">輸入從 Edge Server 內部介面的 SIP 流量 （至 Director、 Director 集區虛擬 IP 位址、 前端伺服器或前端集區虛擬 IP 位址)</span><span class="sxs-lookup"><span data-stu-id="a3b33-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a3b33-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a3b33-275">任何 （可定義為前端伺服器 IP 位址，或前端集區的 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server）</span><span class="sxs-lookup"><span data-stu-id="a3b33-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a3b33-276">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-277">驗證 A / V 使用者 (A / V 驗證服務) 從前端伺服器或前端集區 IP 位址或任何 Survivable Branch Appliance 或 Survivable Branch 伺服器使用此 Edge Server</span><span class="sxs-lookup"><span data-stu-id="a3b33-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a3b33-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a3b33-279">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-279">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-280">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-281">內部與外部使用者之間 A/V 媒體傳輸的慣用路徑</span><span class="sxs-lookup"><span data-stu-id="a3b33-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a3b33-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-283">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-283">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-284">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-285">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="a3b33-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a3b33-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a3b33-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a3b33-287">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="a3b33-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a3b33-288">任何</span><span class="sxs-lookup"><span data-stu-id="a3b33-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a3b33-289">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="a3b33-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

