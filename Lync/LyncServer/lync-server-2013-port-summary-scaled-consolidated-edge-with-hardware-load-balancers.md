---
title: 埠摘要-調整式合併 edge （使用硬體負載平衡器）
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
ms.openlocfilehash: dc4a56edb79d2eff52bf0d234aedcee1b3cdced4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534110"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="7c04c-102">Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="7c04c-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7c04c-103">_**主題上次修改日期：** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="7c04c-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="7c04c-104">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="7c04c-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="7c04c-105">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="7c04c-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="7c04c-106">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="7c04c-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="7c04c-107">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="7c04c-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="7c04c-108">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="7c04c-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="7c04c-109">**使用硬體負載平衡調整式合併 Edge**</span><span class="sxs-lookup"><span data-stu-id="7c04c-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="7c04c-110">![Edge Server 周邊網路埠和通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路埠和通訊協定")</span><span class="sxs-lookup"><span data-stu-id="7c04c-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="7c04c-111">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="7c04c-111">Port and Protocol Details</span></span>

<span data-ttu-id="7c04c-112">建議您只開啟支援您提供外部存取之功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="7c04c-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="7c04c-113">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="7c04c-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="7c04c-114">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="7c04c-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="7c04c-115">調整式合併 Edge （硬體負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="7c04c-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c04c-116">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7c04c-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c04c-117">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-117">Source IP address</span></span></th>
<th><span data-ttu-id="7c04c-118">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-118">Destination IP address</span></span></th>
<th><span data-ttu-id="7c04c-119">注意事項</span><span class="sxs-lookup"><span data-stu-id="7c04c-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-120">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="7c04c-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="7c04c-121">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-122">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-122">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-123">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="7c04c-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-124">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="7c04c-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="7c04c-125">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-126">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-126">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-127">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="7c04c-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-128">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="7c04c-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="7c04c-129">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-130">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-130">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-131">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="7c04c-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7c04c-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c04c-133">Edge Server A/V Edge service IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-134">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-134">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-135">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="7c04c-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7c04c-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c04c-137">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-138">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-138">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-139">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="7c04c-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7c04c-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c04c-141">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-141">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-142">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-143">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="7c04c-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="7c04c-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="7c04c-145">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-145">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-146">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-147">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="7c04c-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-148">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c04c-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c04c-149">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-150">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-150">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-151">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="7c04c-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="7c04c-152">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="7c04c-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-153">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c04c-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c04c-154">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-154">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-155">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-156">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7c04c-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-157">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-158">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-158">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-159">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-160">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7c04c-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-161">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-162">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-163">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-163">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-164">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7c04c-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="7c04c-165">調整式合併 Edge （硬體負載平衡）的防火牆摘要：內部介面節點1和節點2</span><span class="sxs-lookup"><span data-stu-id="7c04c-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c04c-166">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7c04c-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c04c-167">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-167">Source IP address</span></span></th>
<th><span data-ttu-id="7c04c-168">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-168">Destination IP address</span></span></th>
<th><span data-ttu-id="7c04c-169">注意事項</span><span class="sxs-lookup"><span data-stu-id="7c04c-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="7c04c-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="7c04c-171">任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7c04c-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-172">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-173">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="7c04c-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="7c04c-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-175">任何 (都可以定義為具有中央管理存放區的前端伺服器伺服器 IP 或集區) </span><span class="sxs-lookup"><span data-stu-id="7c04c-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-176">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-177">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="7c04c-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="7c04c-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="7c04c-179">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="7c04c-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-180">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-181">從內部部署至內部 Edge Server 介面的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="7c04c-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c04c-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c04c-183">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="7c04c-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-184">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-185">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="7c04c-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-187">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="7c04c-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-188">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-189">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="7c04c-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="7c04c-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="7c04c-191">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-191">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-192">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-193">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7c04c-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="7c04c-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="7c04c-195">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-195">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-196">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-197">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7c04c-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="7c04c-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="7c04c-199">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-199">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-200">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-201">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="7c04c-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7c04c-202">硬體負載平衡器在部署時有特定的需求，可提供 Lync Server 的可用性和負載平衡。</span><span class="sxs-lookup"><span data-stu-id="7c04c-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="7c04c-203">這些需求是在下圖和表格中定義的。</span><span class="sxs-lookup"><span data-stu-id="7c04c-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="7c04c-204">協力廠商廠商可能會針對這裡定義的需求使用不同的術語。</span><span class="sxs-lookup"><span data-stu-id="7c04c-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="7c04c-205">您必須將 Lync Server 的需求對應至硬體負載平衡器廠商所提供的功能和設定選項。</span><span class="sxs-lookup"><span data-stu-id="7c04c-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="7c04c-206">設定硬體負載平衡器時，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="7c04c-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="7c04c-207">您可以在 HLB 的硬體負載平衡器 () 上設定 [來源網路位址)  (轉譯]，以取得 Access Edge service 和 Web 會議 Edge service</span><span class="sxs-lookup"><span data-stu-id="7c04c-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="7c04c-208">無法在 A/V Edge service 上設定 SNAT – A/V Edge service 必須以實際伺服器位址（而非 HLB 虛擬 IP (VIP) ）回應，以透過 UDP over NAT 的簡單遍歷 (STUN) /traversal 使用轉送 NAT (將) /federation 關閉 (FTURN) 才能正常運作</span><span class="sxs-lookup"><span data-stu-id="7c04c-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="7c04c-209">如果用戶端將要求傳送給 HLB，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="7c04c-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="7c04c-210">如果用戶端將要求傳送給 Edge，回應必須從 Edge IP 傳回</span><span class="sxs-lookup"><span data-stu-id="7c04c-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="7c04c-211">公用 IP 位址會用於每個伺服器介面及 HLB 的 Vip 上，而您的公用 IP 位址需求為 N + 1，其中每個實際伺服器介面的公用 IP 位址，以及每個 HLB VIP 的一個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c04c-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="7c04c-212">在集區中有2部 Edge server 的地方，這會產生9個公用 IP 位址，其中3是用於 HLB Vip，另一個則用於每個 Edge server 介面， (伺服器總共六個) </span><span class="sxs-lookup"><span data-stu-id="7c04c-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="7c04c-213">針對 Access Edge service 和 Web 會議 Edge service， (和使用 HLB 上的 NAT) 用戶端會接觸 VIP，VIP 會將來源 IP 位址從用戶端變更為自己的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="7c04c-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="7c04c-214">伺服器介面會將寄件者位址定址至 VIP，VIP 會從伺服器介面 IP 位址變更來源位址，並將資料包傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="7c04c-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="7c04c-215">在 A/V Edge service 中，VIP 不得變更來源 IP 位址，而且實際伺服器位址會直接傳回用戶端–您無法在 HLB 上設定用於 AV 流量的 NAT。</span><span class="sxs-lookup"><span data-stu-id="7c04c-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="7c04c-216">如果用戶端將要求傳送至 HLB VIP，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="7c04c-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="7c04c-217">如果用戶端將要求傳送至 Edge IP，回應必須從 Edge IP 傳回</span><span class="sxs-lookup"><span data-stu-id="7c04c-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="7c04c-218">對於 AV，外部防火牆將保留所有資料包的實際伺服器公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="7c04c-219">在建立後，用戶端對 A/V Edge service 通訊是指實際伺服器，而非 HLB</span><span class="sxs-lookup"><span data-stu-id="7c04c-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="7c04c-220">內部 edge 至內部伺服器和用戶端必須路由傳送，且為主控伺服器或用戶端的所有內部網路設定持久路由</span><span class="sxs-lookup"><span data-stu-id="7c04c-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="7c04c-221">HLB Access Edge service VIP 將充當每個 Edge server 介面的預設閘道</span><span class="sxs-lookup"><span data-stu-id="7c04c-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7c04c-222">如需有關 NAT 規劃及功能的進一步資訊，請參閱 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬體負載平衡器需求</A>。</span><span class="sxs-lookup"><span data-stu-id="7c04c-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="7c04c-223">![Edge Server 埠與通訊協定詳細資料](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 埠與通訊協定詳細資料")</span><span class="sxs-lookup"><span data-stu-id="7c04c-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="7c04c-224">調整式合併 Edge （硬體負載平衡）的必要外部埠設定：外部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="7c04c-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c04c-225">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7c04c-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c04c-226">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-226">Source IP address</span></span></th>
<th><span data-ttu-id="7c04c-227">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-227">Destination IP address</span></span></th>
<th><span data-ttu-id="7c04c-228">注意事項</span><span class="sxs-lookup"><span data-stu-id="7c04c-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7c04c-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7c04c-230">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-230">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-231">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7c04c-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-232">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="7c04c-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="7c04c-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="7c04c-234">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7c04c-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-235">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-235">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-236">XMPP Proxy 服務會將流量傳送至已定義 XMPP 同盟中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="7c04c-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-237">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-238">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-238">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-239">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-240">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="7c04c-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-241">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c04c-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c04c-242">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-242">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-243">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-244">使用 SIP 的 SIP 信號、同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7c04c-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-245">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c04c-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c04c-246">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-247">同盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="7c04c-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="7c04c-248">使用 SIP 的 SIP 信號、同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="7c04c-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-249">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-250">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-250">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-251">Edge Server Web 會議 Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-252">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="7c04c-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-253">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c04c-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c04c-254">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-254">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-255">Edge Server A/V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-256">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7c04c-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-257">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-258">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-258">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-259">Edge Server A/V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="7c04c-260">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="7c04c-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="7c04c-261">調整式合併 Edge 的防火牆摘要（硬體負載平衡）：內部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="7c04c-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7c04c-262">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="7c04c-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="7c04c-263">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-263">Source IP address</span></span></th>
<th><span data-ttu-id="7c04c-264">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-264">Destination IP address</span></span></th>
<th><span data-ttu-id="7c04c-265">注意事項</span><span class="sxs-lookup"><span data-stu-id="7c04c-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-266">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c04c-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c04c-267">任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7c04c-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-268">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-269">從 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址 (到內部 Edge VIP 的輸出 SIP 流量) </span><span class="sxs-lookup"><span data-stu-id="7c04c-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-270">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="7c04c-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="7c04c-271">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-272">任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="7c04c-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-273">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址</span><span class="sxs-lookup"><span data-stu-id="7c04c-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="7c04c-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="7c04c-275">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="7c04c-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="7c04c-276">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-277">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="7c04c-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="7c04c-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="7c04c-279">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-279">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-280">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-281">內部與外部使用者之間 A/V 媒體傳輸的慣用路徑</span><span class="sxs-lookup"><span data-stu-id="7c04c-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7c04c-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-283">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-283">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-284">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-285">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="7c04c-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7c04c-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="7c04c-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="7c04c-287">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="7c04c-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="7c04c-288">任何</span><span class="sxs-lookup"><span data-stu-id="7c04c-288">Any</span></span></p></td>
<td><p><span data-ttu-id="7c04c-289">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="7c04c-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

