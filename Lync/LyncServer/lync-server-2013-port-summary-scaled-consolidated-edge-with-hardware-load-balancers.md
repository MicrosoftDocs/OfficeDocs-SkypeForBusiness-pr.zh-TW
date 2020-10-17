---
title: 埠摘要-調整式合併 edge （使用硬體負載平衡器）
description: 埠摘要-調整式合併 edge （使用硬體負載平衡器）。
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
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564589"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="df3cf-103">Lync Server 2013 中的埠摘要-調整式合併 edge （使用硬體負載平衡器）</span><span class="sxs-lookup"><span data-stu-id="df3cf-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df3cf-104">_**主題上次修改日期：** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="df3cf-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="df3cf-105">此案例架構中所述的 Lync Server 2013，Edge Server 功能非常類似于 Lync Server 2010 中所執行的功能。</span><span class="sxs-lookup"><span data-stu-id="df3cf-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="df3cf-106">最值得注意的是加入了可延伸訊息及目前狀態通訊協定 (XMPP) 的連接埠 **5269 over TCP** 項目。</span><span class="sxs-lookup"><span data-stu-id="df3cf-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="df3cf-107">Lync Server 2013 （選用）在 Edge Server 或 Edge 集區上部署 XMPP proxy，並在前端伺服器或前端集區上部署 XMPP 閘道伺服器。</span><span class="sxs-lookup"><span data-stu-id="df3cf-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="df3cf-108">除了 IPv4 之外，Edge Server 現在還支援 IPv6。</span><span class="sxs-lookup"><span data-stu-id="df3cf-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="df3cf-109">但為了清楚說明起見，此案例僅會使用 IPv4。</span><span class="sxs-lookup"><span data-stu-id="df3cf-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="df3cf-110">**使用硬體負載平衡調整式合併 Edge**</span><span class="sxs-lookup"><span data-stu-id="df3cf-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="df3cf-111">![Edge Server 周邊網路埠和通訊協定](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server 周邊網路埠和通訊協定")</span><span class="sxs-lookup"><span data-stu-id="df3cf-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="df3cf-112">埠與通訊協定詳細資料</span><span class="sxs-lookup"><span data-stu-id="df3cf-112">Port and Protocol Details</span></span>

<span data-ttu-id="df3cf-113">建議您只開啟支援您提供外部存取之功能所需的埠。</span><span class="sxs-lookup"><span data-stu-id="df3cf-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="df3cf-114">若要讓遠端存取可用於任何 edge service，必須保證 SIP 流量雙向流動，如輸入/輸出 edge 流量圖所示。</span><span class="sxs-lookup"><span data-stu-id="df3cf-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="df3cf-115">換句話說，來回 Access Edge Service 的 SIP 訊息會涉及立即訊息 (IM)、顯示狀態、Web 會議、音訊/視訊 (A/V) 與同盟等功能。</span><span class="sxs-lookup"><span data-stu-id="df3cf-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="df3cf-116">調整式合併 Edge （硬體負載平衡）的防火牆摘要：外部介面–節點1和節點 2 (範例) </span><span class="sxs-lookup"><span data-stu-id="df3cf-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df3cf-117">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df3cf-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df3cf-118">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-118">Source IP address</span></span></th>
<th><span data-ttu-id="df3cf-119">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-119">Destination IP address</span></span></th>
<th><span data-ttu-id="df3cf-120">注意事項</span><span class="sxs-lookup"><span data-stu-id="df3cf-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-121">存取/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="df3cf-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="df3cf-122">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-123">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-123">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-124">憑證撤銷/CRL 檢查及擷取</span><span class="sxs-lookup"><span data-stu-id="df3cf-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-125">存取/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="df3cf-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="df3cf-126">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-127">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-127">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-128">透過 TCP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="df3cf-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-129">存取/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="df3cf-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="df3cf-130">Edge Server Access Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-131">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-131">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-132">透過 UDP 的 DNS 查詢</span><span class="sxs-lookup"><span data-stu-id="df3cf-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-133">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="df3cf-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df3cf-134">Edge Server A/V Edge service IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-135">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-135">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-136">與執行 Office 通訊伺服器2007、Office 通訊伺服器 2007 R2、Lync Server 2010 和 Lync Server 2013 的合作夥伴進行同盟所需。</span><span class="sxs-lookup"><span data-stu-id="df3cf-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-137">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="df3cf-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df3cf-138">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-139">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-139">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-140">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟。</span><span class="sxs-lookup"><span data-stu-id="df3cf-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-141">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="df3cf-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df3cf-142">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-142">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-143">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-144">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="df3cf-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-145">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="df3cf-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="df3cf-146">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-146">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-147">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-148">僅適用于執行 Office 通訊伺服器2007之合作夥伴的同盟</span><span class="sxs-lookup"><span data-stu-id="df3cf-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-149">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df3cf-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df3cf-150">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-151">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-151">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-152">3478輸出可用來判斷與 Lync Server 進行通訊的 Edge Server 版本，以及來自 Edge Server 至 Edge Server 的媒體流量。</span><span class="sxs-lookup"><span data-stu-id="df3cf-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="df3cf-153">與 Lync Server 2010、Windows Live Messenger 和 Office 通訊伺服器 2007 R2 的同盟是必要的，此外，如果在公司內部署了多個 Edge 集區，也是必要的。</span><span class="sxs-lookup"><span data-stu-id="df3cf-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-154">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df3cf-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df3cf-155">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-155">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-156">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-157">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="df3cf-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-158">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-159">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-159">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-160">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-161">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="df3cf-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-162">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-163">Edge Server A/V Edge service 公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-164">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-164">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-165">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="df3cf-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="df3cf-166">調整式合併 Edge （硬體負載平衡）的防火牆摘要：內部介面節點1和節點2</span><span class="sxs-lookup"><span data-stu-id="df3cf-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df3cf-167">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df3cf-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df3cf-168">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-168">Source IP address</span></span></th>
<th><span data-ttu-id="df3cf-169">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-169">Destination IP address</span></span></th>
<th><span data-ttu-id="df3cf-170">注意事項</span><span class="sxs-lookup"><span data-stu-id="df3cf-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="df3cf-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="df3cf-172">任何 (都可以定義為前端伺服器位址，或執行 XMPP 閘道服務的前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="df3cf-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-173">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-174">來自前端伺服器或前端集區上執行之 XMPP 閘道服務的輸出 XMPP 流量</span><span class="sxs-lookup"><span data-stu-id="df3cf-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="df3cf-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-176">任何 (都可以定義為具有中央管理存放區的前端伺服器伺服器 IP 或集區) </span><span class="sxs-lookup"><span data-stu-id="df3cf-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-177">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-178">從中央管理存放區到 Edge Server 的變更複製</span><span class="sxs-lookup"><span data-stu-id="df3cf-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="df3cf-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="df3cf-180">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="df3cf-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-181">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-182">從內部部署至內部 Edge Server 介面的 Web 會議流量</span><span class="sxs-lookup"><span data-stu-id="df3cf-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df3cf-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df3cf-184">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="df3cf-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-185">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-186">內部與外部使用者之間的 A/V 媒體傳輸的慣用路徑，Survivable Branch 裝置或 Survivable Branch 伺服器</span><span class="sxs-lookup"><span data-stu-id="df3cf-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-188">任何 (都可以定義為 Director IP、前端伺服器 IP 或集區虛擬 IP) </span><span class="sxs-lookup"><span data-stu-id="df3cf-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-189">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-190">內部與外部使用者之間 A/V 媒體傳輸的回退路徑。 Survivable 分支裝置或 Survivable Branch Server 如果無法建立 UDP 通訊，則會使用 TCP 進行檔案傳輸和桌面共用</span><span class="sxs-lookup"><span data-stu-id="df3cf-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="df3cf-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="df3cf-192">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-192">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-193">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-194">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="df3cf-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="df3cf-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="df3cf-196">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-196">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-197">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-198">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="df3cf-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="df3cf-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="df3cf-200">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-200">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-201">Edge Server 內部介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-202">集中式記錄服務控制器使用 Lync Server 管理命令介面和集中式記錄服務 Cmdlet，ClsController 命令列 ( # A0) 或 agent ( # A1) 命令和記錄檔集合</span><span class="sxs-lookup"><span data-stu-id="df3cf-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="df3cf-203">硬體負載平衡器在部署時有特定的需求，可提供 Lync Server 的可用性和負載平衡。</span><span class="sxs-lookup"><span data-stu-id="df3cf-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="df3cf-204">這些需求是在下圖和表格中定義的。</span><span class="sxs-lookup"><span data-stu-id="df3cf-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="df3cf-205">協力廠商廠商可能會針對這裡定義的需求使用不同的術語。</span><span class="sxs-lookup"><span data-stu-id="df3cf-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="df3cf-206">您必須將 Lync Server 的需求對應至硬體負載平衡器廠商所提供的功能和設定選項。</span><span class="sxs-lookup"><span data-stu-id="df3cf-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="df3cf-207">設定硬體負載平衡器時，請考慮下列需求：</span><span class="sxs-lookup"><span data-stu-id="df3cf-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="df3cf-208">您可以在 HLB 的硬體負載平衡器 () 上設定 [來源網路位址)  (轉譯]，以取得 Access Edge service 和 Web 會議 Edge service</span><span class="sxs-lookup"><span data-stu-id="df3cf-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="df3cf-209">無法在 A/V Edge service 上設定 SNAT – A/V Edge service 必須以實際伺服器位址（而非 HLB 虛擬 IP (VIP) ）回應，以透過 UDP over NAT 的簡單遍歷 (STUN) /traversal 使用轉送 NAT (將) /federation 關閉 (FTURN) 才能正常運作</span><span class="sxs-lookup"><span data-stu-id="df3cf-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="df3cf-210">如果用戶端將要求傳送給 HLB，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="df3cf-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="df3cf-211">如果用戶端將要求傳送給 Edge，回應必須從 Edge IP 傳回</span><span class="sxs-lookup"><span data-stu-id="df3cf-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="df3cf-212">公用 IP 位址會用於每個伺服器介面及 HLB 的 Vip 上，而您的公用 IP 位址需求為 N + 1，其中每個實際伺服器介面的公用 IP 位址，以及每個 HLB VIP 的一個公用 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="df3cf-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="df3cf-213">在集區中有2部 Edge server 的地方，這會產生9個公用 IP 位址，其中3是用於 HLB Vip，另一個則用於每個 Edge server 介面， (伺服器總共六個) </span><span class="sxs-lookup"><span data-stu-id="df3cf-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="df3cf-214">針對 Access Edge service 和 Web 會議 Edge service， (和使用 HLB 上的 NAT) 用戶端會接觸 VIP，VIP 會將來源 IP 位址從用戶端變更為自己的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="df3cf-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="df3cf-215">伺服器介面會將寄件者位址定址至 VIP，VIP 會從伺服器介面 IP 位址變更來源位址，並將資料包傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="df3cf-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="df3cf-216">在 A/V Edge service 中，VIP 不得變更來源 IP 位址，而且實際伺服器位址會直接傳回用戶端–您無法在 HLB 上設定用於 AV 流量的 NAT。</span><span class="sxs-lookup"><span data-stu-id="df3cf-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="df3cf-217">如果用戶端將要求傳送至 HLB VIP，回應必須從 HLB VIP 傳回</span><span class="sxs-lookup"><span data-stu-id="df3cf-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="df3cf-218">如果用戶端將要求傳送至 Edge IP，回應必須從 Edge IP 傳回</span><span class="sxs-lookup"><span data-stu-id="df3cf-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="df3cf-219">對於 AV，外部防火牆將保留所有資料包的實際伺服器公用 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="df3cf-220">在建立後，用戶端對 A/V Edge service 通訊是指實際伺服器，而非 HLB</span><span class="sxs-lookup"><span data-stu-id="df3cf-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="df3cf-221">內部 edge 至內部伺服器和用戶端必須路由傳送，且為主控伺服器或用戶端的所有內部網路設定持久路由</span><span class="sxs-lookup"><span data-stu-id="df3cf-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="df3cf-222">HLB Access Edge service VIP 將充當每個 Edge server 介面的預設閘道</span><span class="sxs-lookup"><span data-stu-id="df3cf-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="df3cf-223">如需有關 NAT 規劃及功能的進一步資訊，請參閱 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013 的硬體負載平衡器需求</A>。</span><span class="sxs-lookup"><span data-stu-id="df3cf-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="df3cf-224">![Edge Server 埠與通訊協定詳細資料](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server 埠與通訊協定詳細資料")</span><span class="sxs-lookup"><span data-stu-id="df3cf-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="df3cf-225">調整式合併 Edge （硬體負載平衡）的必要外部埠設定：外部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="df3cf-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df3cf-226">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df3cf-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df3cf-227">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-227">Source IP address</span></span></th>
<th><span data-ttu-id="df3cf-228">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-228">Destination IP address</span></span></th>
<th><span data-ttu-id="df3cf-229">注意事項</span><span class="sxs-lookup"><span data-stu-id="df3cf-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="df3cf-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="df3cf-231">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-231">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-232">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="df3cf-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-233">XMPP Proxy 服務接受來自定義之 XMPP 同盟中 XMPP 連絡人的流量</span><span class="sxs-lookup"><span data-stu-id="df3cf-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="df3cf-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="df3cf-235">XMPP Proxy 服務 (與 Access Edge service 共用 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="df3cf-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-236">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-236">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-237">XMPP Proxy 服務會將流量傳送至已定義 XMPP 同盟中的 XMPP 連絡人</span><span class="sxs-lookup"><span data-stu-id="df3cf-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-238">Access/SIP (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-239">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-239">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-240">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-241">外部使用者存取從用戶端到伺服器的 SIP 流量</span><span class="sxs-lookup"><span data-stu-id="df3cf-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-242">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df3cf-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df3cf-243">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-243">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-244">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-245">使用 SIP 的 SIP 信號、同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="df3cf-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-246">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df3cf-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df3cf-247">Access Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-248">同盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="df3cf-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="df3cf-249">使用 SIP 的 SIP 信號、同盟和公用 IM 連線</span><span class="sxs-lookup"><span data-stu-id="df3cf-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-250">Web 會議/PSOM (TLS) /TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-251">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-251">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-252">Edge Server Web 會議 Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-253">Web 會議媒體</span><span class="sxs-lookup"><span data-stu-id="df3cf-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-254">A/V/STUN、MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df3cf-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df3cf-255">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-255">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-256">Edge Server A/V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-257">透過 UDP/3478 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="df3cf-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-258">A/V/STUN、MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-259">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-259">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-260">Edge Server A/V Edge service 公用 VIP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="df3cf-261">透過 UDP/443 之 STUN/TURN 候選的交涉</span><span class="sxs-lookup"><span data-stu-id="df3cf-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="df3cf-262">調整式合併 Edge 的防火牆摘要（硬體負載平衡）：內部介面虛擬 Ip</span><span class="sxs-lookup"><span data-stu-id="df3cf-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df3cf-263">角色/通訊協定/TCP 或 UDP/連接埠</span><span class="sxs-lookup"><span data-stu-id="df3cf-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="df3cf-264">來源 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-264">Source IP address</span></span></th>
<th><span data-ttu-id="df3cf-265">目的地 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-265">Destination IP address</span></span></th>
<th><span data-ttu-id="df3cf-266">注意事項</span><span class="sxs-lookup"><span data-stu-id="df3cf-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-267">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df3cf-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df3cf-268">任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="df3cf-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-269">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-270">從 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址 (到內部 Edge VIP 的輸出 SIP 流量) </span><span class="sxs-lookup"><span data-stu-id="df3cf-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-271">存取/SIP (MTLS) /TCP/5061</span><span class="sxs-lookup"><span data-stu-id="df3cf-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="df3cf-272">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-273">任何 (都可以定義為 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址) </span><span class="sxs-lookup"><span data-stu-id="df3cf-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-274">從 Edge Server 內部介面) 的輸入 SIP 流量 (到 Director、Director 集區虛擬 IP 位址、前端伺服器或前端集區虛擬 IP 位址</span><span class="sxs-lookup"><span data-stu-id="df3cf-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="df3cf-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="df3cf-276">任何 (都可以定義為前端伺服器的 IP 位址，或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable Branch 裝置或 Survivable Branch 伺服器) </span><span class="sxs-lookup"><span data-stu-id="df3cf-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="df3cf-277">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-278">A/V 使用者的驗證 (A/V 驗證服務) 來自前端伺服器或前端集區的 IP 位址，或是使用此 Edge Server 的任何 Survivable 分支裝置或 Survivable 分支伺服器</span><span class="sxs-lookup"><span data-stu-id="df3cf-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="df3cf-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="df3cf-280">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-280">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-281">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-282">內部與外部使用者之間 A/V 媒體傳輸的慣用路徑</span><span class="sxs-lookup"><span data-stu-id="df3cf-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df3cf-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-284">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-284">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-285">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-286">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="df3cf-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df3cf-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="df3cf-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="df3cf-288">Edge Server 內部 VIP 介面</span><span class="sxs-lookup"><span data-stu-id="df3cf-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="df3cf-289">任何</span><span class="sxs-lookup"><span data-stu-id="df3cf-289">Any</span></span></p></td>
<td><p><span data-ttu-id="df3cf-290">內部及外部使用者之間 A/V 媒體傳輸的後援路徑，如果無法建立 UDP 通訊，就會使用 TCP 進行檔案傳輸及桌面共用</span><span class="sxs-lookup"><span data-stu-id="df3cf-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

